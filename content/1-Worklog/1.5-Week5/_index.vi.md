---
title: "Worklog Tuần 5"
date: 2025-10-12
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

### Mục tiêu tuần 5:

* Tìm hiểu về các mục trong module "Migrate to AWS"
* Hiểu các tối ưu chi phí với AWS Lambda

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                                                         |
| --- | ---------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ---------------------------------------------------------------------- |
| 2   | - Tiếp tục tìm hiểu cho dự án, vẽ sơ đồ kiến trúc sơ bộ                                                                                  | 6/10/2025    | 6/10/2025       |                                                                        |
| 3   | - Thực hành VM Import/Export <br>  + Thử triển khai máy chủ ứng dụng <br>  + Upload và import VM lên AWS    | 7/10/2025    | 7/10/2025       | [https://000014.awsstudygroup.com/](https://000014.awsstudygroup.com/) |
| 4   | - Thực hành Database Schema Conversion & Migration <br>  + Cấu hình DMS và SCT <br>  + Thực hiện chuyển đổi schema và di chuyển dữ liệu | 8/10/2025    | 8/10/2025       | [https://000015.awsstudygroup.com/](https://000015.awsstudygroup.com/) |
| 5   | - Thực hành AWS Elastic Disaster Recovery Workshop <br>  + Cấu hình DRS <br>  + Cài đặt agent và kiểm tra quá trình failover         | 9/10/2025    | 9/10/2025       | [https://000016.awsstudygroup.com/](https://000016.awsstudygroup.com/) |
| 6   | - Thực hành Optimizing EC2 Costs with Lambda <br>  + Tạo hàm Lambda start/stop instance <br>  + Kết nối Slack để nhận thông báo      | 10/10/2025   | 10/10/2025      | [https://000017.awsstudygroup.com/](https://000017.awsstudygroup.com/) |

### Kết quả đạt được tuần 5:

* A - Tìm hiểu về VM Import/Export

  * Hiểu quy trình VM Import/Export trên AWS, bao gồm cả hướng di chuyển hai chiều giữa môi trường on-premises và AWS Cloud.

  * Triển khai thành công máy ảo Ubuntu trong môi trường VMWare Workstation:
    * Tạo mới máy ảo, cài hệ điều hành Ubuntu.
    * Cấu hình người dùng, dung lượng đĩa và dịch vụ OpenSSH Server để truy cập từ xa.

  * Thực hiện xuất máy ảo từ on-premises:

    * Dùng chức năng *Export to OVF* để tạo file .vmdk phục vụ cho quá trình nhập lên AWS.

  * Tạo và cấu hình S3 bucket để lưu trữ file máy ảo:
    * Đặt tên bucket duy nhất, chọn region phù hợp.
    * Cho phép public access và tải file .vmdk lên S3.

  * Tạo IAM Role “vmimport” và gán chính sách cần thiết để dịch vụ VM Import/Export có thể:
    * Truy cập S3 bucket chứa file máy ảo.
    * Thực hiện lệnh import-image trên AWS CLI để chuyển đổi máy ảo thành AMI.

  * Triển khai EC2 Instance từ AMI:
    * Truy cập EC2 Console, chọn AMI vừa import.
    * Tạo key pair, khởi tạo instance và SSH kết nối kiểm tra.

  * Thực hành quy trình xuất ngược (Export) từ AWS:
    * Tạo S3 bucket mới và cấu hình ACL cho phép quyền ghi/đọc.
    * Sử dụng AWS CLI để export từ Instance hoặc AMI ra định dạng .vhd / .vmdk.
    * Lưu file vào S3 và triển khai lại máy ảo trên hệ thống on-premise.

  * Nắm vững luồng thao tác hai chiều:
    * Import: On-premises → S3 → AMI → EC2
    * Export: EC2 / AMI → S3 → On-premises

  * Hoàn tất các bước kết nối CLI, xác minh AMI, kiểm tra tiến trình import/export và quản lý tài nguyên trên AWS Cloud.

* B - Xem qua Database Schema Conversion & Migration

  * Hiểu cách chuẩn bị môi trường AWS cho quá trình di trú cơ sở dữ liệu, bao gồm tạo key pair, cấu hình EC2 instance và thiết lập kết nối.

  * Nắm được cách lựa chọn và cấu hình các nguồn cơ sở dữ liệu khác nhau như Oracle và SQL Server cho AWS DMS.

  * Thực hành chuyển đổi schema bằng công cụ AWS Schema Conversion Tool (SCT) và hiểu cách chỉnh sửa mã thủ tục (procedural code) khi cần.

  * Tìm hiểu cách thiết lập quá trình di trú dữ liệu bằng AWS Database Migration Service (DMS), bao gồm tạo replication instance, endpoint và migration task.

  * Biết cách giám sát hoạt động di trú thông qua CloudWatch metrics, task logs và event notifications.

  * Hiểu cơ chế hoạt động của DMS Serverless và cách nó tự động mở rộng quy mô khi tải tăng.

  * Thực hành xử lý các sự cố thường gặp trong quá trình di trú như lỗi bộ nhớ hoặc lỗi bảng trong DMS task.

  * Hoàn thành các bước dọn dẹp môi trường sau khi di trú, bao gồm xóa migration task, replication instance và IAM roles.

* C - AWS Elastic Disaster Recovery Workshop

  * Hiểu tổng quan về AWS Elastic Disaster Recovery (AWS DRS), bao gồm mục đích, cách hoạt động và lợi ích trong việc giảm thiểu downtime và mất mát dữ liệu.

  * Nắm được cách chuẩn bị hạ tầng cho môi trường mô phỏng on-premises để thực hành DRS, bao gồm cấu hình các subnet, DNS, và máy chủ Bastion.

  * Thực hành kết nối đến Bastion Host thông qua RDP hoặc SSH, sử dụng thông tin đăng nhập được cung cấp.

  * Cấu hình các thiết lập mặc định của DRS trong AWS Management Console, bao gồm lựa chọn subnet, loại instance và nhóm bảo mật.

  * Tạo và cấu hình IAM User dành cho DRS Agent với quyền truy cập, đồng thời lưu thông tin Access Key phục vụ cho quá trình cài đặt.

  * Thực hành cài đặt DRS Agent trên các máy chủ nguồn (web và database) thông qua Bastion Host, thiết lập vùng AWS, Access Key, Secret Key và chọn ổ đĩa cần sao chép.

  * Theo dõi quá trình đồng bộ dữ liệu (initial sync) và xác minh trạng thái của DRS source servers là “Ready for recovery” và “Healthy”.

  * Thực hiện quy trình Failover, bao gồm khởi tạo recovery job, chọn dữ liệu gần nhất và kiểm tra quá trình phục hồi trên giao diện DRS cũng như EC2.

  * Hiểu cách kiểm tra log, theo dõi lịch sử job và xác nhận các instance đã được khởi chạy thành công trong môi trường AWS.

  * Hoàn thành việc làm quen với quy trình khôi phục hệ thống trong trường hợp thảm họa và đảm bảo tính sẵn sàng của hệ thống.


* D - Optimizing EC2 Costs with Lambda

  * Hiểu mục tiêu và nguyên lý của việc tối ưu chi phí EC2 bằng AWS Lambda, bao gồm tự động bật/tắt máy chủ và sử dụng Savings Plan cho các trường hợp hoạt động liên tục.

  * Thực hành tạo hạ tầng ban đầu bao gồm VPC, Security Group và EC2 instance phục vụ cho bài lab.

  * Cấu hình Slack Incoming Webhooks để nhận thông báo trạng thái hoạt động của instance trực tiếp trên kênh Slack.

  * Tạo Tag cho instance trong giao diện EC2 (key: environment_auto, value: true) để Lambda có thể nhận diện và thao tác chính xác.

  * Tạo IAM Role cho Lambda Function, gán quyền AmazonEC2FullAccess và CloudWatchFullAccess, đảm bảo Lambda có thể quản lý EC2 và ghi log theo dõi hoạt động.

  * Thực hành tạo hai hàm Lambda:
    * stop instance – tự động dừng EC2 khi không cần thiết.
    * start instance – tự động khởi động EC2 khi cần hoạt động.

  * Kiểm tra kết quả hoạt động bằng cách chạy thử các hàm Lambda trong giao diện AWS Management Console:
    * Khi chạy hàm start instance, EC2 được khởi động và Slack hiển thị thông báo “Starting instance”.
    * Khi chạy hàm stop instance, EC2 chuyển sang trạng thái “Stopped” và Slack hiển thị thông báo “Stopping instance”.

  * Hoàn thành toàn bộ quy trình kiểm thử và xác nhận Lambda hoạt động chính xác, giúp tối ưu chi phí vận hành hệ thống EC2.

  * Thực hiện bước dọn dẹp tài nguyên sau khi kiểm thử.
