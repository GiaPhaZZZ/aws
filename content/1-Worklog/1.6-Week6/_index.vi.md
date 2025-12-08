---
title: "Worklog Tuần 6"
date: 2025-10-19
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

### Mục tiêu tuần 6:

* Học hỏi thêm kiến thức về Grafam Tags và quản lý AWS system manager
* Thực hành với các bài lab của FJC

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc| Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                                                         |
| --- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ---------------------------------------------------------------------- |
| 2   | - Tiến hành trainning model cho vấn đề dự đoán tọa độ tiếp theo, đánh giá, nhận xét các tích hợp mới vào mô hình | 13/10/2025   | 13/102025      |                                                                        |
| 3   | - Làm quen với Grafana và giám sát tài nguyên AWS bằng dashboard trực quan <br>   + Tìm hiểu khái niệm, chức năng và ứng dụng của Grafana trong giám sát hệ thống <br>   + Cài đặt và cấu hình Grafana trên EC2 instance <br>   + Kết nối Grafana với CloudWatch và tạo dashboard giám sát tài nguyên EC2                                    | 14/10/2025   | 14/10/2025      | <https://000029.awsstudygroup.com/> |
| 4   | - Tìm hiểu về Tags và Resource Groups trong AWS <br>   + Hiểu cơ chế key–value pair và vai trò của tagging trong tổ chức tài nguyên <br>   + Thực hành tạo, xóa, lọc tài nguyên theo tag qua AWS Console và CLI <br>   + Tạo Resource Group kiểu Tag-based với tiêu chí Key=BusinessUnit, Value=Marketing                                    | 15/10/2025   | 15/10/2025      | <https://000027.awsstudygroup.com/> |
| 5   | - Quản lý truy cập EC2 thông qua IAM và Resource Tags <br>   + Áp dụng nguyên tắc Least Privilege và tạo các IAM Policy điều kiện theo Region và Tag <br>   + Tạo nhóm quản trị (Admin Group), người dùng (Admin User) và role ec2-admin-team-alpha <br> | 16/10/2025   | 16/10/2025      | <https://000028.awsstudygroup.com/> |
| 6   | - Quản lý và tự động hóa nhiều máy chủ bằng AWS Systems Manager | 17/10/2025   | 17/10/2025      | <https://000031.awsstudygroup.com/> |


### Kết quả đạt được tuần 6:

* A - Làm quen với Grafana và giám sát tài nguyên AWS bằng dashboard trực quan

  * Tìm hiểu về công cụ Grafana:

    * Hiểu khái niệm, chức năng và ứng dụng của Grafana trong việc trực quan hóa dữ liệu và giám sát hệ thống.
    * Nắm được các tính năng chính như visualize, dashboard động, alerting và tích hợp nhiều nguồn dữ liệu.

  * Chuẩn bị môi trường AWS:

    * Tạo VPC, Subnet, Security Group, IAM User và IAM Role phục vụ cho việc cài đặt Grafana.
    * Khởi tạo EC2 instance để cài đặt Grafana Server.

  * Thực hành cài đặt Grafana trên EC2:

    * Kết nối đến instance qua PuTTY, thực hiện cập nhật hệ thống và thêm YUM repository.
    * Cài đặt Grafana bằng lệnh sudo yum install grafana và khởi động dịch vụ bằng systemctl start grafana-server.
    * Kiểm tra trạng thái hoạt động và thiết lập tự khởi động cùng hệ thống.

  * Đăng nhập và cấu hình ban đầu Grafana:

    * Truy cập giao diện qua địa chỉ <PublicIPv4>:3000, đăng nhập bằng tài khoản mặc định admin/admin.
    * Đặt lại mật khẩu mới và kiểm tra giao diện dashboard cơ bản.

  * Kết nối Grafana với CloudWatch:

    * Cấu hình data source CloudWatch bằng Access Key và Secret Key của IAM User.
    * Kiểm tra kết nối thành công và thực hiện truy vấn dữ liệu.

  * Tạo dashboard giám sát tài nguyên:

    * Thêm panel hiển thị chỉ số CPUUtilization của EC2 instance.
    * Lưu dashboard với tên Grafana-Monitoring và thực hiện chia sẻ qua liên kết.
    * Thử nghiệm tính năng Explore để truy vấn và trực quan hóa dữ liệu theo thời gian thực.

* B - Tìm hiểu về Tags và Resource Groups trong AWS.

  * Hiểu khái niệm key–value pair của tag và vai trò của việc gắn thẻ trong quản lý tài nguyên, chi phí, phân quyền và tự động hóa.

  * Thực hành thao tác với Tag thông qua giao diện AWS Management Console:

    * Tạo EC2 instance kèm tag khi khởi tạo.
    * Thêm, xóa và lọc tài nguyên theo tag.

  * Làm quen với cách sử dụng AWS CLI để quản lý tag:

    * Gán tag cho tài nguyên EC2 sẵn có bằng lệnh create-tags.
    * Tạo mới EC2 instance và EBS volume có sẵn tag qua run-instances và create-volume.
    * Dùng describe-instances để xem thông tin tài nguyên đã được gắn thẻ.

  * Tạo và quản lý Resource Group dựa trên tag:

    * Xây dựng nhóm tài nguyên kiểu *Tag-based* với tiêu chí Key=BusinessUnit, Value=Marketing.
    * Kiểm tra danh sách tài nguyên trong group vừa tạo trên giao diện Resource Groups Console.

  * Nắm được cách tổ chức, nhóm và truy xuất tài nguyên AWS hiệu quả bằng việc sử dụng tag và resource group.

* C - Tìm hiểu về cơ chế quản lý truy cập tài nguyên EC2 thông qua IAM và Resource Tags.

  * Hiểu rõ nguyên tắc Least Privilege trong IAM và cách áp dụng điều kiện trong IAM Policy để giới hạn quyền truy cập theo vùng và thẻ tài nguyên.

  * Thực hành tạo nhóm quản trị (Admin Group) và người dùng quản trị (Admin User) trong IAM Console.

  * Tạo các IAM Policy chuyên biệt cho quản lý EC2, bao gồm:
    * ec2-list-read: chỉ cho phép quyền đọc EC2 trong hai vùng us-east-1 và us-west-1
    * ec2-create-tags: cho phép gán thẻ khi tạo EC2 instance
    * ec2-create-tags-existing: cho phép gán thẻ nếu thẻ có giá trị Key=Team, Value=Alpha
    * ec2-run-instances: cho phép tạo EC2 instance khi đáp ứng điều kiện vùng và thẻ
    * ec2-manage-instances: cho phép thao tác khởi động, dừng, xóa EC2 khi điều kiện thẻ và vùng được đáp ứng

  * Tạo và gán IAM Role ec2-admin-team-alpha với các policy vừa tạo, đồng thời cấu hình Trust relationship để cho phép Assume Role.

  * Thực hành cơ chế Switch Role và xác minh quyền truy cập của người dùng theo từng chính sách IAM đã cấu hình.

  * Hiểu được cách kết hợp IAM và Resource Tags để kiểm soát truy cập theo nguyên tắc linh hoạt, bảo mật và có thể mở rộng cho mô hình quản trị phân tán.

* D - Tìm hiểu và thực hành quản lý nhiều máy chủ cùng lúc thông qua AWS Systems Manager.

  * Hiểu rõ chức năng của Systems Manager trong việc tập trung dữ liệu vận hành, tự động hóa quy trình và quản lý đồng bộ tài nguyên trên AWS.

  * Thực hành triển khai môi trường gồm 2 máy ảo Windows EC2:

    * Tạo VPC, subnet và cấu hình IAM Role cho phép Systems Manager truy cập và quản lý instance.
    * Gán IAM Role vào từng instance để kết nối được với Systems Manager.

  * Kiểm tra trạng thái Managed Nodes trong Fleet Manager, xác nhận 2 node (Windows-Lab-SSM-1 và Windows-Lab-SSM-2) hoạt động và có thể khởi tạo phiên terminal session thành công.

  * Sử dụng Patch Manager để quét và cài đặt bản vá cho hai Windows EC2 Instances:

    * Chọn chế độ “Scan and Install” để kiểm tra và cài đặt bản cập nhật.
    * Cấu hình không khởi động lại instance sau khi vá.
    * Theo dõi và xác minh kết quả cập nhật thành công.

  * Thực hành Run Command trên nhiều máy chủ cùng lúc bằng AWS Systems Manager:

    * Chạy lệnh “AWS-RunPowerShellScript” để thực thi câu lệnh PowerShell từ xa.
    * Chọn mục tiêu là 2 Windows EC2 Instances.
    * Bật tùy chọn lưu kết quả đầu ra về S3 Bucket để kiểm tra log và lỗi.

  * Hoàn tất quá trình kiểm tra đầu ra của từng instance, xác nhận lệnh được thực thi thành công và hệ thống phản hồi đúng với cấu hình.

  * Nắm vững quy trình quản lý tập trung và tự động hóa trên nhiều máy chủ, giúp tối ưu hóa bảo trì hệ thống, kiểm soát truy cập và giảm thiểu thao tác thủ công trong môi trường vận hành AWS.



