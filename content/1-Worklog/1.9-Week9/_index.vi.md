---
title: "Worklog Tuần 9"
date: 2025-11-09
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---

### Mục tiêu tuần 9:

* Tìm hiểu các module vể Security
* Làm quen với AWS single sign-on và security hub

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                                                         |
| --- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ---------------------------------------------------------------------- |
| 2   | - Tìm hiểu và chuẩn bị tích hợp mô hình sau khi train với các dịch vụ của AWS | 03/11/2025   | 03/11/2025      |                                                                        |
| 3   | - Tìm hiểu AWS IAM Identity Center (AWS SSO) <br>  + Khái niệm, vai trò và lợi ích <br>  + Thiết lập và cấu hình cơ bản  | 04/11/2025   | 04/11/2025      | [https://000121.awsstudygroup.com/](https://000121.awsstudygroup.com/) |
| 4   | - Thực hành IAM Identity Center <br>  + Tạo và gán Permission Set <br>  + Cấu hình truy cập đa tài khoản qua portal <br>  + Thiết lập Time-based Access Control   | 05/11/2025   | 05/11/2025      | [https://000122.awsstudygroup.com/](https://000122.awsstudygroup.com/) |
| 5   | - Tìm hiểu IAM Permission Boundaries <br>  + Cơ chế hoạt động và mục đích <br>  + So sánh với Identity-based Policy  | 06/11/2025   | 06/11/2025      | [https://000123.awsstudygroup.com/](https://000123.awsstudygroup.com/) |
| 6   | - Access Control with IAM Policies & Conditions <br> - Kích hoạt và cấu hình AWS Security Hub <br> | 07/11/2025   | 15/11/2025      | [https://000124.awsstudygroup.com/](https://000124.awsstudygroup.com/) |

### Kết quả đạt được tuần 9:

* A - Identity Federation with AWS Single sign-on

    * Hiểu rõ khái niệm và vai trò của AWS IAM Identity Center (trước đây là AWS Single Sign-On) trong việc quản lý danh tính tập trung và kiểm soát truy cập cho nhiều tài khoản AWS.

    * Nắm được quy trình thiết lập IAM Identity Center để quản lý quyền truy cập theo nguyên tắc tối thiểu đặc quyền, gán quyền dựa trên nhóm người dùng và vai trò dự án.

    * Triển khai thành công AWS Organization và tạo các Organizational Units (Security, Shared Services, Logging, Application) nhằm phân tách và quản lý tài nguyên hiệu quả.

    * Thực hành tạo và gán Permission Set cho người dùng, cấu hình truy cập đa tài khoản qua AWS IAM Identity Center.

    * Hiểu và áp dụng Time-based Access Control để giới hạn quyền truy cập theo khung thời gian định trước, phù hợp với vai trò kiểm toán hoặc dự án tạm thời.

    * Tạo, gán và kiểm tra nhóm người dùng (Groups) và người dùng (Users) trong IAM Identity Center; xác thực khả năng truy cập bằng portal URL và vai trò được chỉ định.

    * Thực hành truy cập AWS CLI thông qua IAM Identity Center bằng cơ chế xác thực tự động (OIDC), đảm bảo bảo mật và tuân thủ nguyên tắc Zero Trust.

    * Hiểu cách sử dụng Customer Managed Policies để tái sử dụng các chính sách tùy chỉnh giữa nhiều tài khoản AWS, giúp quản lý quyền linh hoạt và nhất quán.

    * Triển khai và kiểm thử các API của Identity Store (IdentityStore API) để tự động hóa việc tạo, cập nhật và kiểm tra người dùng, nhóm, và quan hệ thành viên.

    * Hoàn thiện quy trình kiểm toán người dùng và nhóm bằng các lệnh CLI, đảm bảo quyền truy cập được cấp phát đúng phạm vi và đúng thời gian, duy trì tuân thủ bảo mật.

* B - Permission Managemnet with IAM Permisson Boundaries 

    * Nắm được khái niệm và mục đích của IAM Permission Boundary trong việc giới hạn phạm vi tối đa quyền của người dùng hoặc nhóm người dùng.

    * Hiểu được cơ chế hoạt động của Permission Boundary — quyền hiệu lực là phần giao giữa chính sách người dùng (Identity-based Policy) và chính sách giới hạn (Permission Boundary).

    * Thực hành tạo Restriction Policy chỉ cho phép thao tác với dịch vụ EC2 trong vùng ap-southeast-1 (Singapore).

    * Tạo IAM user “ec2-admin” và gán quyền AmazonEC2FullAccess cùng Permission Boundary “ec2-admin-restrict-region”.

    * Kiểm tra và xác nhận người dùng “ec2-admin” chỉ có thể tạo và quản lý EC2 tại Singapore, không thể thao tác ở các vùng khác như Sydney.

    * Hiểu được lợi ích của Permission Boundary trong việc ngăn chặn privilege escalation và đơn giản hóa quản lý quyền trên quy mô lớn.

    * Thực hiện quy trình cleanup — xóa user và policy sau khi kiểm thử để đảm bảo môi trường sạch và an toàn.

* C - Access control with IAM Policies and Conditions

    * Hiểu và áp dụng nguyên tắc least privilege khi cấp quyền cho người dùng, đảm bảo chỉ truy cập đủ phạm vi cần thiết.

    * Nắm rõ khái niệm và quy trình Assume Role, cách IAM User lấy temporary credentials thông qua AWS STS.

    * Thực hành tạo IAM Group với quyền quản trị cho EC2 và RDS, giúp quản lý người dùng tập trung và an toàn hơn.

    * Tạo các IAM User có quyền khác nhau (EC2-admin-user, RDS-admin-user, Group-user, No-permission-user) để mô phỏng nhiều tình huống truy cập thực tế.

    * Cấu hình IAM Role có quyền Admin và thiết lập Trust Relationship cho phép các IAM User thực hiện Assume Role.

    * Thiết lập Condition trong IAM Role để giới hạn truy cập theo địa chỉ IP hoặc thời gian, nâng cao tính bảo mật và kiểm soát chi tiết quyền truy cập.

    * Xác minh thành công việc switch role của người dùng theo điều kiện đặt ra và dọn dẹp tài nguyên sau khi hoàn tất.

* D - AWS Security Hub

    * Hiểu được vai trò của AWS Security Hub trong việc tổng hợp, tổ chức và ưu tiên các cảnh báo bảo mật từ nhiều dịch vụ AWS như GuardDuty, Inspector và Macie.

    * Nắm được cơ chế hoạt động của Security Hub trong việc hiển thị rủi ro qua bảng điều khiển trực quan, giúp dễ dàng theo dõi tình trạng bảo mật và tuân thủ.

    * Biết cách kích hoạt Security Hub trên AWS Management Console và lựa chọn các bộ tiêu chuẩn bảo mật như AWS Foundational Security Best Practices, CIS AWS Foundations Benchmark và PCI DSS.

    * Theo dõi và đánh giá điểm Security Score của tài khoản AWS dựa trên từng bộ tiêu chuẩn, từ đó xác định các rủi ro và điểm yếu bảo mật cần khắc phục.

    * Hiểu mối quan hệ giữa Security Hub và AWS Config, biết cách bật AWS Config để ghi lại toàn bộ tài nguyên cần thiết cho việc đánh giá tuân thủ.

    * Thực hành loại bỏ các tiêu chí đánh giá không phù hợp, đồng thời quản lý việc kích hoạt hoặc vô hiệu hóa từng tiêu chuẩn bảo mật theo nhu cầu thực tế.

    * Hoàn thiện việc theo dõi, đánh giá và tối ưu mức độ an toàn của tài khoản AWS dựa trên các tiêu chuẩn bảo mật được áp dụng.
