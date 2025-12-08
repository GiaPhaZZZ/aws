---
title: "Worklog Tuần 3"
date: 2025-09-28
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

### Mục tiêu tuần 3:

* Tìm hiểu các khái niệm về Amazon Lightsail.
* Nắm rõ các bước scaling cho EC2.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Tìm hiểu ngọn nguồn và đặc điểm của data được chuẩn bị cho huấn luyện mô hình  <br> - Tiến hành đề xuất thuật toán da đạng hóa data để làm tăng độ phong phú pattern trong quá trình huấn luyện mô hình                                                                                          | 22/09/2025  | 22/09/2025      |
| 3   | - Tiến hành tìm hiểu về Amazon Lightsail Workshop và các thông tin liên quan <br> Thực hành thao tác với các tính năng của dịch vụ                                            | 23/09/2025  | 23/09/2025    | <https://000045.awsstudygroup.com/> |
| 4   | - Khám phá các chức năng của Amazon Lightsail Container <br> - Tạo các instance liên quan và thử nghiệm hoạt động | 24/09/2025   | 24/09/2025  | <https://000046.awsstudygroup.com/> |
| 5   | - Học về các khái niệm của EC2 Auto Scaling : <br>&emsp; + Manual Scalling <br>&emsp; + Dynamic Scalling <br>&emsp; + Scheduled Scalling <br>&emsp; + Predictive Scalling | 25/09/2025   | 25/09/2025     | <https://000006.awsstudygroup.com/> |
| 6   | - Dịch thuật cho technical blog với tựa đề 'Introducing universal installers for AWS CLI v2 on macOS'  | 26/09/2025   | 26/09/2025     | <https://aws.amazon.com/blogs/devops/introducing-universal-installers-for-aws-cli-v2-on-macos/> |


### Kết quả đạt được tuần 3:

* A – Amazon Lightsail Workshop

	* Tiến hành tìm hiểu về 3 applications trên lightsail:
		* WordPress
		* PrestaShop
		* Akaunting

	* Thực hiện triển khai database trên lightsail:
		* Tạo specify login credentials
		* Chọn standard database plan với mức giá 15$
		* Thiết lập tên, thêm key-value tag và hoàn thiện tạo database

	* Thử nghiệm tạo WordPress instance:
		* Chọn và triển khai wordpress server
		* Thiết lập các ubuntu và networking fonfiguration
		* Làm theo hướng dẫn để configure wordpress đã tạo và hoàn tất cài đặt WordPress

	* Tạo thử Prestashop E-Commerce Instace:
		*  Hiểu được sự tiện ích của Prestashop cho phép người dùng tạo online store và tích hợp với payment gateways mong muốn.
		* Tạo xong instance Prestashop 5$ theo hướng dẫn
		* Thiết lập các kết nối mạng và triển khai thành công

	* Thực nghiệm với Akaunting instance:
		* Biết các thông tin cơ bản về Akaunting là dành cho quản lý tài chính và tương tác với WordPress, PrestaShop.
		* Tiến hành tạo một instance từ plan $5
		* Thiết lập các kết nối và hoàn tất triển khai.

	* Thiết lập sercurity cho cả 3 instances vừa tạo, xem thêm về các gói lớn hơn của các instances và thêm Arlam.

* B – Amazon Lightsail Container

	* Hiểu được các khái niệm cơ bản về Lightsail Container dùng để chạy applications.

	* Thực hiện các bước chuẩn bị cần thiết

	* Tạo container service thành công

	* Triển khai thành công Container từ Public Image

	* Thử nghiệm triển khai container từ local system:
		*  Tạo Lightisail instance và thực thiện thiết lập AWS CLI theo hướng dẫn
		* Cài đặt Docker trên Ubuntu và xây dựng container image
		*  Push container image đã tạo và tiến hành deploy.
		* Dọn dẹp tài nguyên sau khi thực hành


* C – EC2 Auto Scaling

	* Tiến hành tìm hiểu về tính năng auto scaling của EC2 với các scaling strategies khác nhau:
		* Manual Scaling
		* Dynamic Scaling
		* Scheduled Scaling
		* Predictive Scaling

	* Thực hiện các bước chuẩn bị cần thiết:
		* Tạo VPC enviroment, EC2 instance và database instace với RDS
		* Setup dữ liệu cho Databse, triển khai webserver
		* Chuẩn bị data cho predictive scaling, tải lên cloudwatch và thực hiện xác thực.

	* Tìm hiểu về Amazon Machine Image và Launch Templates:
		*  Khởi tạo AMI từ instace EC2
		* Tạo Launch Template
		* Thực hiện các thiết lập cần thiết.

	* Cài đặt Load Balancer:
		* Tìm hiểu về Elastic Load Balancing
		* Tạo application của Load Balance Target Group
		* Tiến hành tạo Load Balance từ EC2

	* Thử nghiệm và hoàn thiện khởi tạo Auto Scaling Group để quản lý các EC2 instances

	* Tiến hành test các scaling solutions:
		* Test manual, scheduled, dynamic scaling
		* Đọc hiểu các thông số từ predictive scaling solution

