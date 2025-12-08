---
title: "Worklog Tuần 2"
date: 2025-09-21
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---

### Mục tiêu tuần 2:

* Tiếp tục trang bị thêm kiến thức cho xây dựng mô hình project.
* Nắm rõ các kiến thức về sử dụng EC2, Cloud 9, S3, …


### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                     | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                             |
| --- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ------------------------------------------ |
| 2   | - Tìm hiểu các thuật toán cần thiết cho project: <br>&emsp; + Hình học cầu <br>&emsp; + Đại số tuyến tính và xác suất thống kê <br>&emsp; + Các thuật toán machine learning <br>&emsp; + Dự đoán điểm mới từ điểm cũ + hướng + quãng đường | 15/09/2025   | 15/09/2025      |                                            |
| 3   | - Đọc hiểu các kiến thức về EC2 <br>&emsp; + Chức năng chính của dịch vụ <br>&emsp; + Thử nghiệm triển khai <br>&emsp; + Chi phí sử dụng                                                      | 16/09/2025   | 16/09/2025      | <https://000004.awsstudygroup.com/>        |
| 4   | - Khám phá dịch vụ hỗ trợ lập trình Cloud 9 <br>&emsp; + Triển khai và thực hiện các thiết lập cơ bản <br>&emsp; + Thử sử dụng dịch vụ                                                        | 17/09/2025   | 17/09/2025      | <https://000049.awsstudygroup.com/>        |
| 5   | - Tìm hiểu về dịch vụ lưu trữ Amazon S3 <br>&emsp; + Tạo S3 bucket và tải data lên <br>&emsp; + Dùng thử vài tính năng chính                                                                  | 18/09/2025   | 18/09/2025      | <https://000057.awsstudygroup.com/>        |
| 6   | - Dịch bài log "Implement network connectivity patterns for Oracle Database@AWS" từ tiếng Anh sang tiếng Việt                                                                                                                                               | 19/09/2025   | 19/09/2025      |<https://aws.amazon.com/blogs/database/implement-network-connectivity-patterns-for-oracle-databaseaws/>                                            | 


### Kết quả đạt được tuần 2:

* A – EC2

	* Tìm hiểu căn bản Elastic Compute Cloud (EC2)

	* Dịch vụ cung cấp tính toán và chạy (launch) server ảo mà không cần hardware upfront.

	* AMI (Amazon Machine Images) làm template cho các instances của EC2, bao gồm các hệ thống operating, aplication server, block device mapping, …

	* Các lựa chọn lưu trữ (storage cho EC2) gồm có Amzong EBS volumes và Instance store volumes.

	* Khám phá các chức năng chính của Amazon EC2:
		* Elastic Infrastructure
		* Khả năng kết nối mở rộng (Networking Capabilities)
		* Đa dạng Availability Zones để lựa chọn
		* Quản lý tài nguyên 
		* Theo dõi performance và cài đặt thông báo.

	* Thực hiện hoàn tất các bước chuẩn bị triển khai EC2:
		* Tạo VPC cho Windows Instance
		* Tạo Security Group cho Windows Intstance

	* Thành công khởi tạo Microsoft Window Instantce cho EC2 và kết nối tới máy tính.

	* Học sâu hơn về EC2
		* Chỉnh sửa loại Instance EC2
		* Tạo và quản lý EBS Snapshots
		* Tạo Custom AMI
		* Triển khai instances từ Custom AMI
		* Thử nghiệm recovering access từ Windows Instances

	* Thử deploy Node,js applications lên amazon EC2 windows

	* Hiểu rõ về phí sử dụng của EC2 thông qua restricting service usage và liming EC2 usage.
		* Kiểm soát tốt EC2 deployment
		* Quản lý EB2 volumn storage types
		* Giới hạn quyền xóa resource bởi IP adderess của công ty và theo time period.

	* Tiến hành dọn dẹp tài nguyên sau khi khởi tạo và sử dụng EC2
		*Xóa EC2 instances, AMIs, EBS Snapshots, …
		*Xóa sercurity group, key pairs, tài nguyên, VPC, …

* B – AWS CLOUD 9

	* Thực hiện khám phá các thông tin cơ bản về Cloud 9:
		* Biết về Cloud9 là môi trường pha triển (IDE) hoạt động trực tiếp trên web browser.
		* Cung cấp khả năng chạy, build, edit code và hỗ trợ triển khai lên cloud.
		* Cho phép thay đổi IDE theo mong muốn (màu sắc nền, keyborad shortcuts,...)

	* Tiến hành khởi tạo Cloud9 instance để sử dụng:
		* Tạo evnviroment trên dịch vụ Cloud9
		* Đặt tên, thực hiện các thiết lập cần thiết
		* Hoàn tất create enviroment và chờ cho hoàn tất khởi tạo.

	* Thử sử dụng các tính năng cơ bản:
		* Dùng terminal trong cloud9 cho comman line
		* Làm vài thử nghiệm với text files
		* Tự thử thêm các chức năng khác.

* C – Amazon S3

	* Biết về khái niệm Amazon Simple Storage Service (Amazon S3):
		* Cung cấp nơi lưu trữ thông tin tốt và an toàn
		* Được tạo ra để đáp ứng mọi data về kích thước và lĩnh vực của khách hàng.
		* Sử dụng nhiều trường hợp như data warehouse, website, mobile apps, …

	* Tiến hành tạo S3 bucket và tải data lên

	* Thực hiện các bước chỉnh sửa, mở rộng khả năng dùng S3:
		* Cho phép các chức năng của static website
		* Chỉnh sửa khối public access và public oject
		* Test lại website
		* Tăng tốc static website với cloudfront

	* Thử nghiệm vài tính năng khác của S3:
		* Sử dụng bucket versioning
		* Di chuyển các objects trong dịch vụ
		* Sao chép đối tượng nhiều vùng (Replication object multi-region)

	* Dọn dẹp tài nguyên sau khi thử nghiệm với S3







