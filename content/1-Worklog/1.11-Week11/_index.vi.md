---
title: "Worklog Tuần 11"
date: 2025-11-23
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---

### Mục tiêu tuần 11:

* Làm quen với các dịch vụ AWS serverless
* Trải nghiệm thực hành qua AWS SAM, Cognito, ...

### Các công việc cần triển khai trong tuần này:
Dưới đây là phiên bản **ngắn gọn, tập trung ý chính** cho tuần từ thứ 2 đến thứ 6, dựa trên nội dung bạn cung cấp:

| Thứ | Công việc                                                                                                                                                                                    | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                                                         |
| --- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ---------------------------------------------------------------------- |
| 2   | - Tìm hiểu cách deploy ứng dụng Java SpringBoot Monolith TravelBuddy trên AWS           | 17/11/2025   | 17/11/2025      | [https://000050.awsstudygroup.com/](https://000050.awsstudygroup.com/) |
| 3   | - Tạo CloudFormation stack, Key Pair, RDS MySQL <br> - Import project TravelBuddy vào Eclipse và chạy thử local  | 18/11/2025   | 18/11/2025      | [https://000052.awsstudygroup.com/](https://000052.awsstudygroup.com/) |
| 4   | - Tìm hiểu Lambda và serverless microservices <br> - Tạo Lambda function Java, test cục bộ và upload lên AWS <br> - Kết nối Lambda với S3 trigger                                            | 19/11/2025   | 19/11/2025      | [https://000078.awsstudygroup.com/](https://000078.awsstudygroup.com/) |
| 5   | - Triển khai Node.js Lambda function xử lý S3 và DynamoDB <br> - Cấu hình với IAM role, memory, timeout, environment | 20/11/2025   | 20/11/2025      | [https://000080.awsstudygroup.com/](https://000080.awsstudygroup.com/) |
| 6   | - Triển khai SAM project, tạo API Gateway và Lambda functions <br> - Cấu hình front-end với REST API trên S3 <br> - Tạo User Pool Cognito, authentication flow và kiểm tra đăng ký/đăng nhập | 21/11/2025   | 21/11/2025      | [https://000081.awsstudygroup.com/](https://000081.awsstudygroup.com/) |


### Kết quả đạt được tuần 11:

* A - Monolith to Microservices Migration

  * Tìm hiểu cách triển khai ứng dụng Java Springboot TravelBuddy trên AWS.

  * Sử dụng CloudFormation để provision và xác minh các tài nguyên AWS.

  * Dùng AWS Tools for Eclipse và Elastic Beanstalk CLI để deploy và cập nhật ứng dụng.

  * Sử dụng AWS SDK để query và thao tác tài nguyên AWS thông qua code.

  * Chuẩn bị môi trường trước khi deploy:
    * Tạo Key Pair để truy cập instance
    * Tạo CloudFormation stack
    * Kết nối tới Windows Instance
    * Thiết lập cơ sở dữ liệu MySQL trên RDS
    * Download project TravelBuddy

  * Test project trên Eclipse IDE:
    * Import dự án Maven vào Eclipse
    * Cấu hình biến môi trường để kết nối RDS (JDBC_CONNECTION_STRING, JDBC_UID, JDBC_PWD)
    * Tạo Tomcat server nội bộ để chạy ứng dụng
    * Chạy thử ứng dụng và kiểm tra dữ liệu từ RDS

  * Deploy ứng dụng lên Elastic Beanstalk:
    * Export WAR file từ Eclipse
    * Tạo Elastic Beanstalk Application và Environment
    * Cấu hình môi trường: High availability, VPC, Load Balancer, Subnet, Security Groups, Instance type, EC2 Key Pair
    * Thiết lập biến môi trường Elastic Beanstalk tương ứng với RDS
    * Deploy WAR file và truy cập ứng dụng từ URL Elastic Beanstalk

  * Cập nhật ứng dụng (Update Application):
    * Sửa nội dung trong index.jsp
    * Build WAR file mới bằng Maven (mvn package)
    * Sử dụng Elastic Beanstalk CLI (eb init + eb deploy) để cập nhật ứng dụng
    * Xác nhận thay đổi hiển thị trên website

  * Query API và thao tác AWS bằng Eclipse IDE:
    * Import EC2Report Maven project
    * Sửa EC2Manager.java để truy vấn đúng region
    * Chạy JUnit Test để lấy thông tin EC2 instances
    * Thực hành đọc Tags, thông tin instance, và tạo instance mới bằng AWS SDK

  * Có khả năng quản lý toàn bộ quy trình từ local development, build, deploy tới quản lý và query tài nguyên AWS.


* B - Building Microservices

  * Hiểu được cách tạo và triển khai microservice serverless trên AWS sử dụng Lambda.

  * Chuẩn bị môi trường và cấu hình Eclipse IDE để phát triển Lambda function.

  * Tạo microservice Lambda và test cục bộ:
    * Tạo project Lambda Java trong Eclipse
    * Cập nhật pom.xml để sử dụng phiên bản Mockito mới
    * Chạy JUnit Test với payload JSON giả lập sự kiện S3
    * Xử lý các key URL-encoded trong LambdaFunctionHandler

  * Upload và test Lambda function trên AWS Lambda:
    * Tạo Lambda function mới với tên TestLambda
    * Upload code từ Eclipse và chọn IAM role LambdaRole
    * Kết nối Lambda function với S3 bucket để trigger tự động

  * Mở rộng serverless microservices:
    * Tạo Lambda ImageManager để tự động tạo thumbnail cho file ảnh JPG và xóa file khác
    * Sử dụng AWS SAM và CloudFormation để tự động triển khai Lambda, trigger và S3 bucket
    * (Optional) Cập nhật quyền cho Lambda nếu cần

  * Cấu hình orchestration với CodeStar:
    * Tạo branch mới và quản lý CI/CD pipeline
    * Redeploy microservice khi có cập nhật code
    * Cập nhật target region cho API


  * Optional Advanced Exercise:
    * Tạo Lambda function xử lý các loại file khác nhau, ví dụ chuyển file không hợp lệ sang thư mục khác
    * Tạo S3 trigger gọi Lambda function để xử lý ảnh khi upload
    * Triển khai và cấu hình Lambda function tự động
    * Tạo microservice kết nối với RDS trong VPC
    * Triển khai microservices bằng AWS Developer Tools và CI/CD automation

* C - Serverless Backend with Lambda, S3, and DynamoDB

  * Thực hành làm quen với serverless architecture và AWS Lambda.
  * Tạo Lambda function xử lý sự kiện từ S3 để resize và quản lý hình ảnh.
  * Cấu hình S3 bucket nguồn và đích, thiết lập event notification.
  * Thiết lập IAM role và policy để Lambda truy cập S3 với nguyên tắc least privilege.
  * Cài đặt memory, timeout, và môi trường biến cho Lambda function.
  * Thực hành triển khai Node.js Lambda function, kiểm tra pipeline xử lý hình ảnh, logging và CloudWatch monitoring.
  * Tạo bảng DynamoDB và thiết lập write capacity phù hợp.
  * Tạo Lambda function bằng Python để ghi dữ liệu vào DynamoDB.
  * Cấu hình function settings: runtime Python 3.11, function name book_create.
  * Viết code Lambda để nhận dữ liệu từ event["body"] và ghi vào bảng Books, xử lý lỗi và trả response HTTP.
  * Triển khai và deploy Lambda function, kiểm tra hoạt động ghi dữ liệu.
  * Cấu hình permission: gán IAM role cho Lambda để truy cập DynamoDB.
  * Áp dụng best practices serverless: error handling, logging, least privilege, throughput management.


* D - Deployment Automation with AWS SAM

  * Cài đặt SAM CLI và cấu hình AWS credentials cho người dùng sam-admin.

  * Tạo project SAM mẫu bằng lệnh sam init và chọn các tuỳ chọn cơ bản.

  * Tạo S3 bucket front-end với Static Web Hosting và chính sách truy cập công khai bằng SAM template.

  * Xây dựng, validate và deploy SAM application bằng lệnh sam build, sam validate và sam deploy --guided.

  * Tạo bảng DynamoDB phục vụ lưu trữ dữ liệu sách.

  * Tạo và triển khai Lambda function bằng Python:
    * Listing data từ DynamoDB
    * Writing data vào DynamoDB
    * Deleting data từ DynamoDB
    * Resizing ảnh và quản lý object trong S3

  * Cấu hình API Gateway với GET, POST, DELETE API để tương tác với Lambda functions.

  * Thử nghiệm APIs bằng Postman:
    * Kiểm tra listing API trả dữ liệu từ bảng Books
    * Kiểm tra writing API tạo mới item và upload ảnh vào S3
    * Kiểm tra deleting API xoá dữ liệu và ảnh tương ứng

  * Kết nối front-end với REST API:
    * Cập nhật APP_API_URL và isAdmin trong config.js và App.js
    * Build front-end, upload lên S3 và kiểm tra ứng dụng hiển thị thông tin sách
    * Thử writing và deleting dữ liệu trực tiếp từ front-end


* E - User Authentication with Amazon Cognito

  * Tiến hành tham khảo tài liệu, cài đặt và cấu hình SAM CLI, AWS CLI, AWS credentials để chuẩn bị môi trường.

  * Tải và build front-end từ repository FCJ-Serverless-Workshop, upload build folder lên S3 bucket fcj-book-shop-by-myself.

  * Tạo User Pool trên Amazon Cognito:

    * Chọn Traditional web application và email làm tuỳ chọn xác thực
    * Tạo App client cognito-fcj-book-shop, lưu lại Client ID và Client Secret
    * Bật Authentication flow ALLOW_USER_PASSWORD_AUTH

  * Cập nhật template.yaml với Cognito Client ID và Secret, triển khai Lambda function phục vụ đăng ký và đăng nhập.

  * Tạo Registration function trên SAM bằng tham số registerPathPart và thêm vào template.yaml.

  * Deploy Lambda function và API Gateway:

    * Build, validate và deploy SAM project
    * Lấy Invoke URL của API Gateway để kết nối với front-end

  * Kiểm tra front-end:
    * Thay APP_API_URL trong config.js bằng Invoke URL
    * Build và upload front-end lên S3
    * Thực hiện đăng ký người dùng, xác nhận email
    * Thực hiện đăng nhập, kiểm tra các tính năng: Create new book, Management, Order hiển thị đúng theo quyền truy cập

  * Hoàn thiện authentication flow với Cognito, Lambda và API Gateway, đảm bảo người dùng chỉ sử dụng tính năng khi đã đăng nhập.
