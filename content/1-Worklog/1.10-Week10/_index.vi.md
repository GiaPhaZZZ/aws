---
title: "Worklog Tuần 10"
date: 2025-11-16
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---

### Mục tiêu tuần 10:

* Hiểu quy trình container hóa ứng dụng với Docker và triển khai trên AWS Cloud.
* Làm quen với ECS, CDK và CodePipeline để tự động hóa triển khai hạ tầng và ứng dụng.

### Các công việc cần triển khai trong tuần này

| Thứ | Công việc                                                                                                                                                                                                                                                          | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                                                         |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------ | --------------- | ---------------------------------------------------------------------- |
| 2   | - Tìm hiểu khái niệm container và Docker <br>  + Docker Engine, Dockerfile, Docker Image, Container        | 10/11/2025   | 10/11/2025      | [https://000201.awsstudygroup.com/](https://000201.awsstudygroup.com/) |
| 3   | - Tìm hiểu cách push/pull image lên Docker Hub và Amazon ECR <br> - Cấu hình VPC, EC2, RDS để triển khai ứng dụng container hóa trên môi trường AWS                                     | 11/11/2025   | 11/11/2025      | [https://000202.awsstudygroup.com/](https://000202.awsstudygroup.com/) |
| 4   | - Tìm hiểu Amazon ECS và các launch type (Fargate, EC2) <br>  + Cấu hình ECS Cluster, Task Definition, Service <br>  + Triển khai frontend và backend trên ECS                                      | 12/11/2025   | 12/11/2025      | [https://000203.awsstudygroup.com/](https://000203.awsstudygroup.com/) |
| 5   | - Triển khai ECS bằng AWS CDK (IaC) <br>  + Tạo VPC, NAT Gateway, ECS Cluster bằng CDK <br>  + Xây dựng ECS Service và kết nối DynamoDB, API Gateway                                                          | 13/11/2025   | 13/11/2025      | [https://000204.awsstudygroup.com/](https://000204.awsstudygroup.com/) |
| 6   | - Thiết lập CI/CD pipeline với CodePipeline, CodeBuild, CodeDeploy <br>  + Tạo repository và build pipeline từ GitHub hoặc CodeCommit <br>  + Tự động build và deploy ứng dụng lên ECS Fargate hoặc EC2  | 14/11/2025   | 15/11/2025      | [https://000205.awsstudygroup.com/](https://000205.awsstudygroup.com/) |

---

Bạn có muốn mình thêm phần **“Kết quả đạt được tuần này”** tương tự như các tuần trước (tổng hợp tóm tắt các nội dung chính đã hoàn thành) để khớp định dạng báo cáo tuần không?


### Kết quả đạt được tuần 10:

* A - Containerization with Docker

    * Hiểu toàn bộ quy trình triển khai ứng dụng container hóa với Docker từ môi trường local đến AWS Cloud.

    * Cấu hình và vận hành thành công các dịch vụ AWS như VPC, EC2, RDS và ECR phục vụ cho triển khai ứng dụng.

    * Thực hành triển khai ứng dụng bằng Docker Image, so sánh hiệu quả giữa triển khai thủ công và Docker Compose.

    * Xây dựng và quản lý mạng lưới container giúp frontend, backend và cơ sở dữ liệu giao tiếp ổn định.

    * Đẩy và quản lý image trên Docker Hub và Amazon ECR, phục vụ cho tái sử dụng và triển khai tự động.

    * Hiểu rõ vai trò của Nginx trong điều phối luồng truy cập và cân bằng tải giữa các container.

    * Tối ưu hóa quy trình phát triển và triển khai thông qua việc tách biệt môi trường phát triển và sản xuất.

    * Nâng cao kỹ năng xử lý sự cố và kiểm tra hoạt động ứng dụng trên môi trường đám mây.


* B - Container Orchestration with Amazon ECS

    * Nắm vững quy trình triển khai ứng dụng container hóa trên Amazon ECS với cả hai loại launch type: Fargate và EC2.

    * Tạo và cấu hình thành công ECS Cluster, Task Definition cho frontend và backend, giúp dịch vụ hoạt động ổn định và tách biệt rõ ràng.

    * Ứng dụng kiến thức về Service Discovery trong AWS Cloud Map để kết nối các container nội bộ thông qua DNS name.

    * Thiết lập thành công Application Load Balancer, Target Group và Listener, đảm bảo cân bằng tải và khả năng mở rộng cho ứng dụng.

    * Thực hành triển khai dịch vụ backend với mô hình Blue/Green Deployment, đảm bảo quá trình cập nhật không gián đoạn.

    * Thực hiện Rolling Deployment cho frontend, giúp cập nhật phiên bản liên tục mà không gây downtime.

    * Quản lý và giám sát container thông qua ECS Console và CloudWatch Logs, hiểu rõ hoạt động của từng tác vụ trong cluster.

    * Kiểm thử và xác nhận ứng dụng hoạt động trơn tru trên ECS, từ giao diện frontend đến xử lý backend và kết nối cơ sở dữ liệu.

    * Tối ưu hóa quy trình CI/CD bằng việc tích hợp ECR, ECS và CodeDeploy, tạo nền tảng tự động hóa triển khai cho các dự án tương lai.


* C - Infrastructure as Code for ECS with CDK

    * Hiểu rõ quy trình triển khai ứng dụng Spring Boot trên AWS ECS Fargate bằng cách sử dụng AWS CDK.

    * Nắm được nguyên lý hạ tầng như Infrastructure as Code (IaC) và lợi ích khi sử dụng AWS CDK v2 để tự động hoá việc tạo tài nguyên.

    * Tạo và cấu hình thành công Amazon ECR Repository để lưu trữ Docker images.

    * Triển khai VPC và NAT Gateway bằng AWS CDK, thiết lập môi trường mạng an toàn và cô lập cho ứng dụng.

    * Xây dựng ECS Cluster, định nghĩa Task và ECS Service cho microservice backend.

    * Tạo API Gateway để quản lý endpoint REST, kết nối trực tiếp với ECS Service.

    * Thiết kế và triển khai DynamoDB Table để lưu trữ dữ liệu sản phẩm, sử dụng SDK v2 cho Java.

    * Thực hiện logging ứng dụng qua CloudWatch Logs và cấu hình AWS X-Ray để theo dõi và phân tích luồng truy cập.

    * Nâng cao kỹ năng quản lý, cấu hình và triển khai hạ tầng AWS một cách tự động, đồng bộ và có thể tái sử dụng.


* D - CI/CD Pipeline with AWS CodePipeline

    * Hiểu rõ khái niệm và quy trình hoạt động của CI/CD (Continuous Integration/Continuous Deployment) trong triển khai ứng dụng container trên AWS ECS.

    * Thiết lập và cấu hình thành công pipeline CI/CD sử dụng GitLab, GitHub Actions và AWS CodeBuild kết hợp với ECR, ECS, và CodeDeploy.

    * Tự động hoá toàn bộ quy trình build, test, và deploy ứng dụng từ source code lên môi trường ECS Fargate.

    * Biết cách tạo và quản lý GitLab Runner, định nghĩa pipeline thông qua file cấu hình .gitlab-ci.yml và .github/workflows.

    * Tích hợp thành công các dịch vụ AWS trong pipeline bao gồm CodeBuild, CodePipeline và CodeDeploy để triển khai ứng dụng liền mạch.

    * Sử dụng CloudWatch Container Insights để giám sát hoạt động của container, theo dõi CPU, memory, network, và trạng thái các ECS tasks.

    * Cấu hình FireLens trong ECS để thu thập và định tuyến log từ container đến Amazon S3, giúp dễ dàng phân tích và theo dõi hoạt động của ứng dụng.

    * Thực hành quản lý log, phát hiện sự cố và tối ưu hiệu năng ứng dụng thông qua CloudWatch và FireLens.

    * Hoàn thành quy trình dọn dẹp tài nguyên AWS (ECS, ECR, RDS, EC2, IAM, S3, VPC, NAT Gateway) để đảm bảo môi trường sạch và tối ưu chi phí.

    * Củng cố kiến thức DevOps, đặc biệt trong việc triển khai CI/CD hiện đại trên môi trường cloud-native với AWS.


* E - Automated Deployments with AWS CodePipeline

    * Hiểu được quy trình triển khai ứng dụng lên EC2 thông qua chuỗi CI/CD tự động hóa với AWS CodePipeline.

    * Nắm được vai trò và cách phối hợp của các dịch vụ trong pipeline gồm CodeCommit, CodeBuild, CodeDeploy, và CodePipeline.

    * Tạo thành công S3 bucket để lưu trữ artifact của quá trình build và deploy.

    * Cài đặt và cấu hình CodeDeploy Agent trên EC2 thông qua Session Manager hoặc User Data.

    * Thực hành tạo repository trên CodeCommit (hoặc GitHub thay thế) và thực hiện quy trình clone, mirror, và migrate mã nguồn.

    * Thiết lập dự án build với AWS CodeBuild, cấu hình source từ GitHub, thiết lập môi trường Linux, và tạo artifact đầu ra lưu vào S3.

    * Tạo ứng dụng và Deployment Group trong AWS CodeDeploy, cấu hình loại triển khai In-place và nhóm EC2 theo tag để tự động triển khai.

    * Thực hiện triển khai ứng dụng Node.js thành công lên EC2 thông qua CodeDeploy, xác minh hoạt động qua DNS của instance.

    * Thiết lập CodePipeline hoàn chỉnh với các giai đoạn Source – Build – Deploy, giúp tự động hóa quy trình khi có thay đổi mã nguồn.

    * Kiểm thử pipeline bằng cách chỉnh sửa mã trong repository, commit thay đổi và quan sát pipeline tự động thực thi toàn bộ quá trình build và 
    deploy.

    * Hiểu được quy trình CI/CD khép kín trên AWS: từ commit mã nguồn đến build, test, deploy và xác minh kết quả triển khai thực tế.