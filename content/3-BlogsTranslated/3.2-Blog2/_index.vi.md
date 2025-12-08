---
title: "Blog 2"
date: 2025-09-19
weight: 2
chapter: false
pre: " <b> 3.2. </b> "
---

# Triển khai network connectivity patterns cho Oracle Database@AWS

Sameer Malik, Anvesh Koganti, và Shubham Singh | vào ngày 11 Tháng 9 2025 | AWS Cloud WAN, AWS Transit Gateway, Expert (400), Networking & Content Delivery, Oracle Database@AWS, Technical How-to |

Oracle Database@AWS (ODB@AWS) là một dịch vụ cho phép khách hàng truy cập vào hạ tầng Oracle Exadata được quản lý bởi Oracle Cloud Infrastructure (OCI) trong các trung tâm dữ liệu của Amazon Web Services (AWS). Bạn có thể sử dụng ODB@AWS để di chuyển workloads Oracle Exadata của mình sang AWS trong khi vẫn duy trì cùng mức hiệu suất và tính năng như các triển khai Oracle Exadata on-premise. Tất nhiên, bạn được hưởng lợi từ việc giảm độ trễ ứng dụng bằng cách thiết lập low-latency connectivity giữa Oracle Exadata và các ứng dụng đang chạy trên AWS. Không những thế, bạn còn có thể tích hợp Oracle Database@AWS với các dịch vụ AWS khác để cải thiện availability và scalability cho các ứng dụng Oracle database của mình.

Trong bài viết lần này, chúng tôi sẽ trình bày cách triển khai các IP routing-based network connectivity patterns khác nhau cho kết nối giữa ODB network của bạn cùng những tài nguyên khác được triển khai trong AWS cũng như mạng on-premises của bạn. Các patterns này hoạt động tốt khi bạn có non-overlapping IP address spaces và cần traditional Layer 3 connectivity.

Các connectivity patterns được đề cập trong bài viết này bao gồm:

One-to-one connectivity giữa application virtual private cloud (VPC) và ODB network

Scalable single-Region connectivity giữa multi-VPC hoặc on-premises infrastructure và ODB network sử dụng AWS Transit Gateway

Scalable global connectivity giữa multi-VPC hoặc on-premises infrastructure và ODB network sử dụng AWS Cloud WAN

Trước khi đi tiếp, chúng tôi khuyến khích bạn nên làm quen với các dịch vụ AWS như Amazon Virtual Private Cloud (Amazon VPC), AWS Direct Connect, Amazon Route 53 Resolver endpoints, Transit Gateway, và AWS Cloud WAN.

## Thông tin cơ bản

Dưới đây là tổng quan chung về những thành phần chính trong ODB@AWS cần thiết cho kết nối mạng. Để biết thêm thông tin, vui lòng tham khảo Oracle Database@AWS User Guide.

  * **ODB network** – ODB network là một mạng private và cách ly, chứa Oracle infrastructure trong một AWS Availability Zone. Khác với VPC tiêu chuẩn, mạng ODB không có kết nối internet và chỉ hỗ trợ các tài nguyên ODB@AWS.

  * **ODB peering** – ODB peering thiết lập private network connectivity giữa ODB network của bạn và một Amazon VPC, cho phép các ứng dụng giao tiếp với Oracle databases như thể chúng nằm trên cùng một mạng. ODB peering kết nối mọi trường AWS và Oracle, đồng thời cung cấp khả năng hỗ trợ routing cho phép lưu lượng sử dụng các dịch vụ AWS networking cụ thể được kết nối tới peered VPC để đến ODB network. Hình minh họa sau đây thể hiện mối quan hệ peering này giữa một peered VPC và ODB network.

![](/images/3-TranslatedBlogs/blog2/fig1.jpeg)


  * **Kiểm soát truy cập với peered CIDRs** – Peered CIDRs là một cấu hình đóng vai trò như một danh sách kiểm soát truy cập (ACL) ở cấp độ mạng. Bạn có thể chỉ định và quản lý các IP CIDR ranges được phép truy cập vào Oracle database resources trong ODB network của bạn. Việc thiết lập peered CIDRs kích hoạt automation phía Oracle OCI để cấu hình route rules và security rules liên kết với Oracle Virtual Cloud Network (tương đương Amazon VPC) nơi các resources tồn tại, để cho phép traffic từ/tới các CIDRs cụ thể trên các protocols và ports nhất định. Bạn có thể chỉ định subnet CIDRs cụ thể thay vì toàn bộ VPC ranges, cung cấp kiểm soát bảo mật chi tiết. Tham khảo phần considerations ở cuối bài viết này để biết thêm chi tiết về peered CIDRs và OCI automation specifics.

  * **Peered VPC usage patterns** – Một peered VPC phục vụ nhiều mục đích. Nó có thể hoạt động như một ứng dụng trực tiếp VPC, cung cấp đường dẫn mạng đơn giản nhất cho các tác vụ Oracle chuyên dụng. Ngoài ra, nó có thể đóng vai trò như một VPC trung chuyển sử dụng transitive routing để cho phép mạng ODB truy cập từ nhiều VPC và on-premises networks thông qua Transit Gateway hoặc các hub-and-spoke architectures dựa trên AWS Cloud WAN. Một peered VPC cũng có thể đồng thời thực hiện cả hai vai trò, vừa làm VPC ứng dụng lưu trữ các tác vụ, vừa là VPC trung chuyển kết nối các mạng khác với mạng ODB.

## Thiết lập cấu Hình DNS

ODB@AWS tự động quản lý DNS trong ODB network, tạo ra Fully Qualified Domain Names (FQDNs) cho các cụm máy ảo (VM). Theo mặc định, các FQDN này sử dụng domain pattern *.oraclevcn.com (nơi mà bạn có thể chỉ định tiền tố được gắn thêm vào oraclevcn.com, ví dụ: myhost.oraclevcn.com). Ngoài ra, bạn còn có thể thiết lập tên miền tùy ý bằng cách sử dụng tên miền hoàn chỉnh của riêng mình (ví dụ: myhost.myodb.com). Dù chọn cấu hình tên miền nào, các truy vấn DNS từ VPC của bạn phải được chuyển tiếp đến hạ tầng DNS của mạng ODB để giải quyết các tên miền này.

Kiến trúc DNS bao gồm các thành phần sau:

* **Route 53 Resolver outbound endpoint** – Chuyển tiếp các truy vấn DNS từ VPC của bạn đến cơ sở hạ tầng DNS của mạng ODB. Sau khi mạng ODB được tạo, nó cung cấp địa chỉ IP của DNS listener IP mà điểm cuối ra ngoài phải có kết nối đến mạng.

* **Forwarding rules** – Chuyển giao các truy vấn trực tiếp đến các miền Oracle (ví dụ: client.xxxxx.oraclevcn.com) tới DNS listener IP của ODB network bằng outbound endpoint. Quy tắc này phải khớp với cả tên miền chính xác và các tên miền con của nó (ví dụ: nếu rule cho example.com, nó khớp cả example.com và sub.example.com). Bạn có thể chia sẻ các quy tắc này giữa các tài khoản AWS Resource Access Manager (AWS RAM)  và liên kết chúng với các VPC cần giải quyết tên miền Oracle. Để hiểu chi tiết hơn về domain matching, xem qua How Resolver determines whether the domain name in a query matches any rules.


Trong hình minh họa tiếp theo, outbound endpoint được triển khai trong application VPC để cấu hình đơn giản hơn và kết nối trực tiếp tới peered ODB network. Các tùy chọn triển khai thay thế và chiến lược quản lý DNS tập trung được thảo luận sau trong bài viết này. Để biết các bước cấu hình DNS chi tiết, xem Configuring DNS for Oracle Database@AWS.

![](/images/3-TranslatedBlogs/blog2/fig2.jpeg)

## Network connectivity patterns

Trong phần này, chúng ta sẽ thảo luận về ba patterns kết nối mạng phổ biến cho ODB@AWS, từ kết nối trực tiếp đơn giản đến các kiến trúc đa vùng có khả năng mở rộng. Mỗi mô hình sẽ đáp ứng được các nhu cầu kinh doanh và mở rộng khác nhau. Nhằm đơn giản hóa, các sơ đồ sẽ không hiển thị vị trí tài nguyên cấp tài khoản (account-level resource placement). Những cân nhắc về vị trí tài khoản cho từng mô hình sẽ được nêu chi tiết trong phần tiếp theo.

### Connectivity pattern 1: Kết nối trực tiếp giữa application VPC và ODB network

Pattern 1 sử dụng VPC được kết nối trực tiếp như một application VPC , lưu trữ các ứng dụng cơ sở dữ liệu trực tiếp trong VPC được kết nối với mạng ODB. Phương pháp này cung cấp đường dẫn mạng đơn giản nhất giữa các ứng dụng và cơ sở dữ liệu.

Pattern này hoạt động tốt khi Oracle databases chủ yếu phục vụ applications trong một VPC. Như hình dưới đây minh họa, ODB network được gắn với một Availability Zone duy nhất (được định nghĩa khi ODB network được tạo), trong khi application VPC và tài nguyên của nó có thể trải rộng qua nhiều Availability Zones. Đối với các kiến trúc multi-VPC hoặc hybrid, hãy xem xét các ODB transit VPC patterns ở những phần sau.

![](/images/3-TranslatedBlogs/blog2/fig3.jpeg)

Workflow bao gồm các thành phần:

  * A. Amazon Elastic Compute Cloud (Amazon EC2) instances trong application VPC giải quyết database hostname để lấy địa chỉ IP và sau đó thiết lập kết nối cơ sở dữ liệu sử dụng địa chỉ IP này.

  * B. VPC route tables điều hướng lưu lượng truy cập đến mạng ODB thông qua kết nối peering ODB.

  * C. Vì VPC CIDR được bao gồm trong danh sách peered CIDRs, các cấu hình phía Oracle OCI tồn tại để cho phép traffic này. Lưu lượng phản hồi theo đường dẫn ngược trở lại các instance EC2 ban đầu.

### Connectivity pattern 2: Single-Region scalable connectivity sử dụng Transit Gateway

Trong pattern này, chúng ta sẽ tìm hiểu về kết nối mạng tới ODB network ở quy mô lớn trong một AWS Region duy nhất. Tại thời điểm viết bài, ODB network chỉ hỗ trợ direct peering với một VPC duy nhất; one-to-many peering connection giữa một ODB network và nhiều VPCs chưa được hỗ trợ. Transit gateway là một thành phần mạng tập trung hoạt động đóng vai trò như điểm điểm kết nối cho nhiều VPCs và on-premises networks. Tại thời điểm bài viết, ODB network chưa hỗ trợ built-in transit gateway attachment. Tuy nhiên, bạn có thể thiết lập kết nối peering giữa mạng ODB và một VPC Transit duy nhất, sau đó kết nối VPC Transit đó với Transit Gateway, như minh họa trong hình dưới đây.

![](/images/3-TranslatedBlogs/blog2/fig4.jpeg)

Trong pattern này, peered VPC chỉ hoạt động như một VPC trung chuyển ODB  (đã mô tả trước đó). Tuy nhiên, như đã nhấn mạnh trong mô hình sử dụng VPC được kết nối, VPC được kết nối có thể đồng thời lưu trữ các tải công việc nếu cần thiết.
Transit gateway attachment tới transit VPC phải được tạo trong một Availability Zone duy nhất, cụ thể là Availability Zone nơi ODB network được tạo. Để nhấn mạnh điều này, trong hình trước, chúng tôi minh họa workloads trải rộng qua nhiều Availability Zones trong application VPC, nhưng transit VPC chỉ có một transit gateway attachment trong Availability Zone 1. Để biết thêm các bước cấu hình chi tiết, xem Configuring Amazon VPC Transit Gateways for Oracle Database@AWS.

Workflow bao gồm các thành phần:

  * EC2 instances trong application VPC giải quyết tên máy chủ cơ sở dữ liệu để lấy địa chỉ IP và sau đó thiết lập kết nối cơ sở dữ liệu sử dụng địa chỉ IP này. Bảng định tuyến của subnet VPC được tra cứu, và gói tin được chuyển tiếp tới transit gateway thông qua kết nối cổng chuyển tiếp.


  * Transit Gateway route table có một đường dẫn tĩnh cho mạng ODB CIDR với đích đến là kết nối VPC chuyển tiếp.


  * Lưu lượng từ transit VPC sử dụng ODB peering route trong VPC subnet route table và traffic được chuyển tiếp tới ODB network.


  * Vì VPC CIDR được bao gồm trong danh sách peered CIDRs, các cấu hình trên phía Oracle OCI đã được thiết lập để cho phép lưu lượng này. Lưu lượng phản hồi theo đường dẫn ngược trở lại các instance EC2 ban đầu.


### Connectivity pattern 3: Multi-Region scalable connectivity sử dụng AWS Cloud WAN

Trong pattern này, chúng ta xem xét network connectivity tới ODB từ nhiều vùng và on-premises networks. AWS Cloud WAN đơn giản hóa multi-Region connectivity thông qua dynamic route propagation. đơn giản hóa kết nối đa vùng thông qua việc truyền tải đường dẫn động. Bạn có thể sử dụng điều này để kết nối các trung tâm dữ liệu, branch offices và VPC của mình trên nhiều khu vực thành một mạng thống nhất, tất cả đều được kiểm soát thông qua một global policy duy nhất. AWS Cloud WAN hỗ trợ built-in segmentation, nghĩa là bạn có thể dễ dàng quản lý sự cách ly mạng giữa các Regions và on-premises locations. Bằng cách sử dụng network segments, bạn có thể chia global network thành các isolated networks riêng biệt. Để biết thêm thông tin, xem qua AWS Cloud WAN User Guide.

Tại thời điểm viết bài, tính năng kết nối tích hợp cho mạng ODB không được hỗ trợ với AWS Cloud WAN. Bằng cách kết nối mạng ODB của bạn với một VPC trung chuyển và sau đó kết nối VPC trung chuyển đó với mạng lõi AWS Cloud WAN, bạn có thể sử dụng AWS Cloud WAN để định tuyến lưu lượng mạng giữa mạng ODB của bạn và nhiều VPC trên các Regions cũng như on-premises locations. Trong pattern này, peered VPC đóng vai trò như transit VPC dựa trên peered VPC usage pattern. Bạn cần đảm bảo rằng transit VPC attachment tới AWS Cloud WAN core network được tạo trong một Availability Zone duy nhất — giống như ODB network.

Nhằm đơn giản hóa, chúng tôi đã hiển thị tất cả application VPCs cần truy cập ODB network được liên kết với ODB application VPC segment, trong khi Direct Connect gateway được liên kết với hybrid segment và segment sharing được bật giữa cả hai segments. Để hiểu rõ các bước cấu hình chi tiết, xem Configuring AWS Cloud WAN for Oracle Database@AWS.

![](/images/3-TranslatedBlogs/blog2/fig5.jpeg)

Workflow bao gồm các thành phần sau:

  * EC2 instances trong application VPC resolve database hostname nhằm lấy IP address và khởi tạo database connections bằng IP này. Việc tra cứu bảng định tuyến của subnet VPC diễn ra, và gói tin được chuyển tiếp đến AWS Cloud WAN core network thông qua kết nối VPC AWS Cloud WAN.


  * Application VPC 1 được liên kết với ODB application VPC segment, trong đó các attachment CIDRs liên kết được truyền động. Vì việc liên kết tích hợp với mạng ODB hiện chưa được hỗ trợ trên AWS Cloud WAN, chúng tôi tạo một đường dẫn tĩnh nối đến kết nối VPC trung chuyển.


  * Traffic từ VPC trung chuyển sử dụng đường dẫn kết nối ODB trong bảng định tuyến mạng con và lưu lượng được chuyển tiếp đến mạng ODB.


  * Như đã nêu trong phần trước, các CIDRs cần thiết cho application VPCs và on-premises network được thêm vào danh sách peered CIDR trên ODB network. Lưu lượng phản hồi theo đường dẫn ngược trở lại các instance EC2 gốc.


## Các yếu tố cần xem xét

Khi triển khai kết nối mạng ODB@AWS, hãy lưu ý các yếu tố kỹ thuật và thiết kế quan trọng sau đây để giúp bạn lập kế hoạch và triển khai một kiến trúc thành công:

* khi tạo ODB network, hãy cân nhắc các yêu cầu  IP address space requirements , bao gồm non-overlapping CIDRs với các connected networks và reserved IP ranges không thể sử dụng. Các CIDR ranges này không thể thay đổi sau khi ODB network được tạo.


* Thiết lập ODB peering không tự động thêm routes cho ODB network CIDRs (client CIDR hoặc backup CIDR) vào peered VPC route tables. Bạn phải thủ công chạy lệnh aws ec2 create-route để thêm các routes này vào VPC route tables khi cần. Xem thêm  configuring VPC route tables for ODB peering cho lệnh AWS Command Line Interface (AWS CLI) cụ thể.


* Khi thiết lập ODB peering với một VPC, primary VPC CIDR sẽ tự động được thêm vào danh sách peered CIDR. Secondary CIDRs của peered VPC phải được thêm thủ công. Hiện tại, bạn không thể chỉnh sửa primary CIDR được thêm tự động này để giới hạn nó chỉ với các subnet CIDRs cụ thể của VPC.


* Khi một entry được thêm vào danh sách peered CIDR, automation phía OCI sẽ diễn ra để hỗ trợ kết nối. Một static route mới được thêm vào trong route rules (tương đương VPC route table) gắn với Virtual Cloud Network (tương đương Amazon VPC) để cho phép traffic tới CIDR range đó. Ngoài ra, các entries cũng được thêm vào security rules (tương đương AWS security groups và network ACLs) để cho phép ICMP traffic (cho MTU path discovery và ping), TCP traffic trên port 22 (cho SSH), và các TCP ports khác cần cho database traffic.


* Route 53 Resolver outbound endpoints có thể được triển khai trong peered VPC hoặc một VPC riêng biệt do networking team của bạn quản lý. Nếu bạn đã có outbound endpoints để hỗ trợ  hybrid DNS resolution, bạn có thể sử dụng chúng. Trong cả hai trường hợp, hãy đảm bảo VPC CIDR chứa endpoint được thêm vào danh sách peered CIDRs của ODB và tồn tại network connectivity giữa endpoint VPC và peered VPC (thông qua Transit Gateway hoặc AWS Cloud WAN).


* Route 53 profiles có thể được sử dụng để  share resolver rules giữa nhiều AWS accounts thay vì chia sẻ trực tiếp từng rule riêng lẻ bằng AWS RAM.

* Multi-Region connectivity cũng có thể đạt được bằng cách sử dụng Transit Gateway  inter-Region peering thay vì Cloud WAN. Cách tiếp cận này yêu cầu static routing configuration giữa các peered transit gateways.


* Một transit VPC không thể đồng thời attach tới cả Transit Gateway và AWS Cloud WAN, hoặc nhiều transit gateways hay Cloud WAN core networks. Bạn phải chọn một transit service duy nhất cho connectivity.


* Với pattern 1 account placement, ODB network được cung cấp trong tài khoản của người mua và có thể được chia sẻ bằng AWS RAM với nhiều tài khoản khác. Tuy nhiên, tại thời điểm viết, chỉ một peering connection có thể được thiết lập tới ODB network. Điều này đồng nghĩa rằng bạn có thể chia sẻ ODB network bằng AWS RAM cho một tài khoản khác và tạo ODB peering connection với application VPC trong tài khoản đó, cung cấp sự linh hoạt cho cross-account application deployments. Xem thêm  Resource sharing in Oracle Database@AWS cho các thông tin chi tiết.

* Với pattern 2 và 3 account placements, khi triển khai Transit Gateway và AWS Cloud WAN connectivity, cả transit VPC và ODB network phải nằm trong cùng một tài khoản AWS — cụ thể là tài khoản của người mua nơi ODB network được cung cấp. Tuy nhiên, Transit Gateway và AWS Cloud WAN có thể nằm trong một tài khoản khác (chẳng hạn như central networking account) và được chia sẻ với tài khoản mua hàng bằng AWS RAM để thiết lập kết nối cần thiết.

Đó là các hạn chế tính đến thời điểm xuất bản blog hiện tại và có thể được cải thiện sớm trong tương lai.

## Kết Luận

Trong bài viết này, chúng tôi đã trình bày khả năng tích hợp mạng của Oracle Database@AWS, cung cấp một giải pháp mạnh mẽ và linh hoạt cho các doanh nghiệp để mở rộng sức mạnh của cơ sở dữ liệu Oracle Exadata một cách liền mạch trong AWS Cloud.
Oracle Database@AWS cung cấp cho các tổ chức nhiều tùy chọn linh hoạt để tích hợp các Oracle database deployments với AWS infrastructure rộng hơn và hybrid environments. Bằng cách lựa chọn peer trực tiếp ODB network với một VPC duy nhất, sử dụng Transit Gateway để kết nối nhiều VPCs, hoặc tận dụng kết nối tập trung của AWS Cloud WAN, bạn có thể chọn cấu hình mạng phù hợp nhất với yêu cầu cụ thể của mình.
Đối với các tổ chức cần IP-agnostic connectivity, hỗ trợ IP address space trùng lặp, hoặc các tích hợp chuyên biệt như zero-ETL và Amazon Simple Storage Service (Amazon S3) access, hãy tham khảo Oracle Database@AWS network connectivity Using Amazon VPC Lattice.

---

Về các tác giả

**Sameer Malik**

Sameer đã có hơn 23 năm kinh nghiệm làm việc với cơ sở dữ liệu quan hệ và hiện đang giữ vị trí Principal Database Solution Architect tại AWS, tập trung vào RDS và Aurora. Anh đã hỗ trợ nhiều khách hàng trong việc di chuyển và hiện đại hóa các tải công việc cơ sở dữ liệu của họ sang AWS.

**Anvesh Koganti**

Anvesh là Solutions Architect tại AWS chuyên về Networking. Anh tập trung vào việc giúp khách hàng xây dựng kiến trúc mạng cho các môi trường AWS có khả năng mở rộng cao và độ tin cậy. Ngoài công việc, Anvesh đam mê công nghệ tiêu dùng và thích nghe podcast về công nghệ và kinh doanh. Khi rời xa thế giới kỹ thuật số, Anvesh dành thời gian ngoài trời đi bộ đường dài và đạp xe.

**Shubham Singh**

Shubham là Senior Network Specialist Solutions Architect tại AWS. Anh giúp khách hàng thiết kế các giải pháp sáng tạo, bền vững và hiệu quả về chi phí bằng cách sử dụng các dịch vụ AWS. Anh đam mê công nghệ và thích xây dựng các giải pháp trong lĩnh vực Mạng và Bảo mật. Anh có bằng Thạc sĩ Telecommunication Systems Management từ Đại học Northeastern, chuyên ngành Computer Networking.



