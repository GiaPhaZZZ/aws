---
title: "Worklog Tuần 7"
date: 2025-10-26
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

### Mục tiêu tuần 7:

* Tiếp tục tìm hiểu về các dịch vụ của AWS
* Hiểu thêm các kiến thức về AWS Cloudformation và CDK

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc| Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                                                         |
| --- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ---------------------------------------------------------------------- |---------------------------------------------------------------------- |
| 2   | - Đánh giá mô hình đã đạt được yêu cầu cho bussiness problem hay chưa. <br> - Re-train lại model để nâng cao độ chính xác và đảm bảo các yêu cầu khác  | 20/10/2025   | 20/10/2025      |                                                                        |
| 3   | - Làm quen với Amazon Systems Manager và cơ chế quản lý tập trung tài nguyên AWS. <br> - Hiểu chức năng của Session Manager trong việc truy cập EC2 an toàn mà không cần SSH. <br> - Thực hành tạo VPC, subnet, EC2, IAM Role và kết nối thành công qua Session Manager.  | 21/10/2025   | 21/10/2025      | [https://000014.awsstudygroup.com/](https://000014.awsstudygroup.com/) |
| 4   | - Tìm hiểu AWS CloudFormation và cơ chế triển khai hạ tầng dưới dạng code. <br> - Hiểu cấu trúc CloudFormation Template và các Intrinsic Functions. <br> - Thực hành tạo Stack, cấp quyền cho Cloud9 Role và phát hiện Drift. | 22/10/2025   | 22/10/2025      | [https://000052.awsstudygroup.com/](https://000052.awsstudygroup.com/) |
| 5   | - Hiểu khái niệm AWS CDK và mối liên hệ với CloudFormation. <br> - Cài đặt môi trường CDK và khởi tạo project qua Cloud9. <br> - Thực hành tạo VPC, subnet, IAM Role, Security Group và triển khai EC2 qua CDK. | 23/10/2025   | 23/10/2025      | [https://000037.awsstudygroup.com/](https://000037.awsstudygroup.com/) |
| 6   | - Mở rộng triển khai hạ tầng CDK với API Gateway, ECS, ELB và Lambda. <br> - Thực hành tạo ECS Cluster, triển khai Nginx trên Fargate kèm Load Balancer. <br> - Kết nối API Gateway và Lambda với S3 để phản hồi dữ liệu động. | 24/10/2025   | 24/10/2025      | [https://000076.awsstudygroup.com/](https://000076.awsstudygroup.com/) |


### Kết quả đạt được tuần 7:

* A - Work with Amazon System Manager - Session Manager

  * Làm quen và thực hành với Amazon Systems Manager, nắm rõ cơ chế hoạt động và quản lý tập trung tài nguyên AWS.

  * Hiểu rõ chức năng của Session Manager trong việc truy cập và quản lý EC2 Instances an toàn mà không cần mở cổng SSH (port 22) hay sử dụng Bastion Host.

  * Thực hành tạo và cấu hình đầy đủ môi trường bao gồm:

    * VPC, Public Subnet, Private Subnet, Security Group
    * EC2 Instances (Linux & Windows)
    * IAM Role cho phép EC2 tương tác với Systems Manager

  * Kết nối thành công tới Public Instance qua Session Manager, xác nhận không phát sinh lưu lượng SSH mà chỉ dùng HTTPS, đảm bảo an toàn kết nối.

  * Cấu hình VPC Interface Endpoints (ssm, ssmmessages, ec2messages) để kết nối tới Private Instance mà không cần internet, tăng cường bảo mật mạng nội bộ.

  * Triển khai và kiểm thử Session Logs:

    * Tạo S3 Bucket lưu trữ nhật ký phiên làm việc và lệnh thực thi.
    * Tạo S3 Gateway Endpoint để truyền dữ liệu nội bộ.
    * Kiểm tra, xác minh log lưu trữ thành công.

  * Thực hành Port Forwarding qua AWS CLI:

    * Cấu hình chuyển tiếp cổng RDP từ máy cá nhân tới Windows Instance trong Private Subnet.
    * Đăng nhập thành công bằng Remote Desktop thông qua cổng nội bộ.


* B - AWS CloudFormation

  * Hiểu rõ về AWS CloudFormation – dịch vụ cho phép mô tả và triển khai hạ tầng AWS bằng mã (Infrastructure as Code), giúp tự động hoá việc tạo và quản lý tài nguyên một cách an toàn và lặp lại được.

  * Biết cách sử dụng CloudFormation Template để mô hình hoá hạ tầng thông qua các thành phần chính:

    * AWSTemplateFormatVersion
    * Description
    * Parameters
    * Resources
    * Outputs

  * Thực hành tạo và chỉnh sửa CloudFormation Template trên môi trường AWS Cloud9, một IDE dựa trên web hỗ trợ nhiều ngôn ngữ lập trình (Python, JavaScript, PHP,…).

  * Cài đặt và cấu hình các công cụ cần thiết trong Cloud9 Workspace bao gồm:

    * jq, gettext, bash-completion, moreutils
    * cfn-lint (kiểm tra cú pháp CloudFormation)
    * taskcat (kiểm thử template tự động)

  * Hiểu và áp dụng được các Intrinsic Functions trong CloudFormation:

    * !Ref – tham chiếu giá trị của tham số hoặc tài nguyên
    * !Sub – chèn biến động vào chuỗi ký tự
    * !GetAtt – lấy thuộc tính từ một tài nguyên đã tạo

  * Tạo thành công các tài nguyên cơ bản bằng CloudFormation Template:

    * Security Group mở port 80 cho HTTP
    * IAM Role & Instance Profile cho phép EC2 giao tiếp với SSM và CloudWatch
    * EC2 Instance tự động gán IAM Role và Network Interface

  * Thực hành tạo CloudFormation Stack trực tiếp từ Cloud9 thông qua AWS CLI, đồng thời cấp quyền cần thiết cho Cloud9 Role (AmazonEC2FullAccess, IAMFullAccess) để thực thi lệnh tạo Stack.

  * Nắm được khái niệm Drift Detection – phát hiện sự khác biệt giữa trạng thái hạ tầng thực tế và cấu hình trong CloudFormation Template.

  * Làm quen với các nội dung nâng cao: Custom Resources, Mapping, StackSet và Macro – giúp tự động hoá, mở rộng khả năng triển khai và quản lý hạ tầng phức tạp.

* C - CDK basic

  * Hiểu được khái niệm AWS CloudFormation và cách triển khai kiến trúc hạ tầng dưới dạng code (Infrastructure as Code).

  * Biết được mối quan hệ giữa CloudFormation và AWS CDK, trong đó CDK là lớp trừu tượng giúp lập trình hạ tầng AWS bằng ngôn ngữ lập trình phổ biến như Python, TypeScript, JavaScript, Java, C#.

  * Cài đặt và khởi tạo môi trường làm việc với AWS CDK thông qua Cloud9 IDE.

  * Thực hành khởi tạo project CDK 

  * Hiểu được cách thức CDK hoạt động thông qua quy trình:
    * Viết code hạ tầng bằng Python
    * CDK chuyển đổi code sang CloudFormation Template (bằng cdk synth)
    * Triển khai tài nguyên thực tế lên AWS qua cdk deploy

  * Thực hành khởi tạo VPC và subnet công khai bằng CDK.

  * Tạo và gán IAM Role cho EC2 Instance, cấu hình Security Group.

  * Thực hành triển khai EC2 Instance trên VPC đã tạo bằng AWS CDK.

  * Thực hành triển khai hạ tầng qua cdk deploy và xác nhận kết quả triển khai trên AWS Management Console.

  * Truy cập vào EC2 instance vừa tạo, kiểm tra hoạt động của Apache Web Server thông qua Public IP.

  * Hiểu được quy trình khép kín của CDK: định nghĩa – tổng hợp – kiểm tra – triển khai – xác thực.

* D - CDK Basic - 2

  * Hiểu được cách mở rộng việc triển khai hạ tầng AWS bằng CDK thông qua tích hợp nhiều dịch vụ như API Gateway, ECS, Elastic Load Balancer và Lambda.

  * Thực hành tạo ECS Cluster và triển khai ứng dụng mẫu Nginx trên Fargate kèm theo Application Load Balancer.

  * Cấu hình API Gateway để định tuyến yêu cầu đến dịch vụ ECS thông qua Load Balancer.

  * Tạo và cấu hình Lambda function truy cập vào S3 Bucket, đọc và liệt kê các đối tượng trong bucket.

  * Thực hành kết nối Lambda với API Gateway, kiểm tra phản hồi dữ liệu động từ S3.

  * Hiểu được cách quản lý môi trường Python ảo và cài đặt các gói phụ thuộc khi làm việc với CDK.

  * Nắm được khái niệm Nested Stack và cách chia nhỏ kiến trúc CDK thành các stack con nhằm tối ưu khả năng mở rộng và bảo trì.

  * Hoàn thành việc triển khai, kiểm tra hoạt động của toàn bộ kiến trúc CDK nâng cao trên AWS.


