---
title: "Worklog Tuần 1"
date: 2025-09-14
weight: 1
chapter: false
pre: " <b> 1.1. </b> "
---


### 1. Mục tiêu tuần 1:

* Giao lưu và làm quen với các thành viên khác cùng tham gia FJC.
* Tìm hiểu về AWS và các dịch vụ được cung cấp. 
* Mở tài khoản và có khả năng thao tác các tính năng cơ bản.

### 2. Các công việc cần triển khai trong tuần này:

| Thứ | Công việc                                                                                                                                                                                                                                                               | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                  |
| --- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ------------------------------- |
| 2   | - Tiến hành tìm hiểu chuyên sâu về AWS và các dịch vụ hiện có: <br>&emsp; + Tạo tài khoản AWS đầu tiên <br>&emsp; + Thiết lập MFA <br>&emsp; + Thực hành thao tác với AWS management console <br>&emsp; + Tìm hiểu về các phương thức support                           | 08.09.2025   | 08.09.2025      | <https://000001.awsstudygroup.com/> |
| 3   | - Đọc và nghiên cứu nội quy của FJC AWS. <br>&emsp; + Gia nhập nhóm Facebook FJC và xem thêm các tài liệu về workshop của chương trình. <br>&emsp; + Đến văn phòng AWS trực buổi đầu. <br>&emsp; + Gặp gỡ, làm quen và lập nhóm. <br>&emsp; + Thực hiện buổi họp online đầu tiên, giao lưu thành viên, bầu nhóm trưởng. | 09.09.2025   | 09.09.2025      | <https://policies.fcjuni.com/>  |
| 4   | - Tìm hiểu về quản lý chi phí và các kiến thức khác: <br>&emsp; + Hiểu và sử dụng Billing and Cost Management <br>&emsp; + Thử nghiệm tạo group, user, policy, role với IAM                                                                                           | 10.09.2025   | 10.09.2025      | <https://000007.awsstudygroup.com/> |
| 5   | - Khám phá dịch vụ Amazon Virtual Private Cloud (VPC) và thực hành thử nghiệm với nó.                                                                                                                                                                                   | 11.09.2025   | 11.09.2025      | <https://000003.awsstudygroup.com/> |
| 6   | - Dịch bài log "Exploring Quantum Measurements, Observables and Operators: Practical insights with Amazon Braket" từ tiếng Anh sang tiếng Việt | 12.09.2025   | 12.09.2025      | <https://aws.amazon.com/blogs/quantum-computing/exploring-quantum-measurements-observables-and-operators-practical-insights-with-amazon-braket/> |



### 3. Kết quả đạt được tuần 1:

* A - Tạo thành công tài khoản AWS đầu tiên

  * Liên kết mail, xác minh tài khoản, thêm visa làm phương thức trả phí.
  * Quản lý đăng nhập IAM
  * Thử nghiệm tạo, xóa, chỉnh sửa Account Alias.

  * Hoàn tất thiết lập MFA
    * Sử dụng mật khẩu của thiết bị local cho MFA
    * Cho phép hoạt động U2F security key

  * Tạo Admin Group và Admin User sử dụng các chính sách đã thiết lập sẵn.
  * Tạo thử support case cho mục đích thử nghiệm.

  * Thử nghiệm sử dụng AWS management consule:
    * Chuyển đổi sang Region Singapore gần khu vực
    * Thử tìm kiếm các dịch vụ hiện có của AWS (EC2, Cloud9, Sercurity Lake, …) cùng các tài liệu và blogs khác.
    * Thêm/Loại bỏ service trong danh sách yêu thích
    * Thêm/Bớt widgets vào console home
    

* B - Tính toán chi phí và kiến thức thêm

  * Sử dụng dịch vụ Billing and cost management tạo Buget và dùng theo template monthly cost budget.
    
  * Hiểu về quản lý các loại chi phí (bao gồm cost, usage, R, … )

  * Hoàn tất tìm hiểu về các gói package hỗ trợ của AWS:
    * Basic
    * Developer
    * Bussiness
    * Enterprise
    

  * Tìm hiểu chuyên sâu về AWS Identity and Access Management (IAM)
    * Biết về các khái niệm và cách vận hàng của IAM Group, User, Policy, Role, …
    * Tiến hành tạo Group và các User
    * Thử nghiệm đổi vai trò của User được tạo.
    

* C - Amazon Virtual Private Cloud (VPC)

  * Hoàn thành tìm hiểu các khái niệm về Amazon Virtual Private Cloud (VPC)
    * Subnets
    * Route Table
    * Internet Gateway
    * NAT Gateway

  * Tạo thử VPC để test.

  * Thêm subnets, gateway, route table, sercurity group vào VPC đã tạo để hoàn chỉnh bản thử nghiệm.
