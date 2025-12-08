---
title: "Worklog Tuần 4"
date: 2025-10-05
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

### Mục tiêu tuần 4:

* Nắm vững kiến thức về các khái niệm sơ bộ của cloud

* Tìm hiểu AWS Cloudwatch, Cloudfront, CLI, …

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Tìm hiểu về AWS CloudWatch và các khái niệm liên quan | 29/09/2025    | 29/09/2025      | <https://000008.awsstudygroup.com/> |
| 3   | - Làm quen với việc sử dụng AWS Command LineInterface, thử nghiệm thao tác với các dịch vụ <br>&emsp; + S3 Bucket <br>&emsp; + SNS <br>&emsp; + IAM <br>&emsp; + VPC <br>&emsp; + ... <br>  | 30/09/2025    | 30/09/2025      | <https://000011.awsstudygroup.com/> |
| 4   | - Tham khảo các thông tin về Cloudfront và cách sử dụng | 1/10/2025    | 1/10/2025       | <https://000094.awsstudygroup.com/> |
| 5   | - Tham khảo về dịch vụ Amazon DynamoDB và các tính năng của nó <br>&emsp; + Core components <br>&emsp; + Primary Keys <br>&emsp; + Secondary Index <br>&emsp; + Các quy tắc đặt tên và query data | 2/10/2025    | 2/10/2025       | <https://000060.awsstudygroup.com/> |
| 6   | - Chuẩn hóa và xử lý hoàn tất dữ liệu cho project <br> - Nghiên cứu mô hình Temporal Convolutional Network sẽ được sử dụng trong quá trình huấn luyện    | 3/10/2025   | 3/10/2025      | |

### Kết quả đạt được tuần 4:

* A – AWS CLOUDWATCH

	* Biết được AWS CloudWatch là dịch vụ theo dõi và quản lí dữ liệu, định hướng hành động cho tài nguyên AWS.

	* Làm việc với các Metrics, xem Logs từ các applications và tạo Alarms từ Metrics nhận được.
	
	* Thực hiện các bước chuẩn bị để làm việc với cloudwatch:
		* Tạo stack trong CloudFormation
		* Thiết lập cơ bản cho stack
		* Hoàn tất tạo dựng và deployment

	*Thao tác với mục xem metrics của cloudwatch:
		*  Xem thử metric của EC2
		* Phân tích cpu utilization
		* Chỉnh sửa chart visualiaztion

	* Tìm hiểu về search, math experessions và dynamic labels cùng thực hành thử nghiệm

	* Xem thông tin chi tiết về cloudwatch logs:
		* Xem blods của EC2 instance
		* Thực hành tạo thử log
		* Tạo metric filter để thu thập và chuyển hóa data sang cloudwatch metrics

	* Khám phá các tính năng của Cloudwatch Alarms và Cloudwatch Dashboards

* B – Làm quen với AWS Command Line Interface (CLI)

	* Hiểu được AWS CLI là open-source tool cho phép ngường dùng tương tác với các dịch vụ của aws trong command-line shell.

	* Tải AWS CLI về máy và thực hiện các bước chuẩn bị để thực hành thao tác

	* Thao tác với Amazon S3 qua AWS CLI:
		* Tạo S3 Bukcet
		* Xem list các bucket và object
		* Xóa object và bucket

	* Tiến hành thử nghiệm với dịch vụ SNS và IAM qua CLI:
		* Tạo thử SNS topic
		* Tạo IAM group, user, ..
		* Kiểm tra thông tin trong group, thêm/xóa access key

	* Dùng CLI thao tác với VPC:
		* Tạo VPC và các componets
		* Tạo thử internet gateway

	*Tham khảo qua các lỗi (Troubleshooting) trong quá trình thao tác với AWS CLI

* C – CLOUFRONT

	* Tiến hành tìm hiểu về CloudFront với S3 Bucket Origin

	* Tạo S3 Bucket để chuẩn bị cho các bước sau

	* Tải file index.html lên S3 Bucket vừa tạo

	* Thực hiện thiết lập các thông số cho Amazon CloudFront

	* Thử nghiệm xóa CloudFront khỏi S3 sau khi dùng.

* D – AMAZON DYNAMODB

	* Hiểu được Amazon DynamoDB là dịch vụ NoSQL Database hỗ trợ các performance nhanh và dễ đoán.

	* Tìm hiểu vài tính chất của DynamoDB:
		*Core components
		*Các key
		*Secondary Index
		*Quy tắc đặt tên và những loại dữ liệu
		*Tham khảo thêm về tính consistency và đọc/viết capacity mode

	* Thực hiện các bước chuẩn bị cần thiết:
		* Tạo acess key, table, đọc-viết và update dữ liệu
		* Tạo global scondary index và query với nó

	* Tiến hành thực hành với AWS SDK :
		* Thiết lập trước AWS CLI
		* Tạo table, đọc-viết-update-xóa data.	
		* Query và scan dữ liệu, xóa bảng sau khi dùng.
