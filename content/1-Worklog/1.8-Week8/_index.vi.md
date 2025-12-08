---
title: "Worklog Tuần 8"
date: 2025-11-02
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

### Mục tiêu tuần 8:

* Khám phá các kiến thức về Iac, Vpc flow logs, billing.
* Hoàn thiện phần thực hành được kèm theo trong các labs.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc                                                                                                                                                                                                                                                       | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                                                         |
| --- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ---------------------------------------------------------------------- |
| 2   | - Chạy so sánh kết quả của phương pháp STFA đề xuất với cac kỹ thuật khác <br> - Tiến hành đo lường trên nhiều thang đo error metrics bao gồm cả custom error.                                                                          | 27/10/2025   | 27/10/2025      |                                                                        |
| 3   | - Tìm hiểu khái niệm và lợi ích của Infrastructure as Code (IaC) trong quản lý hạ tầng tự động. <br> - Phân biệt CloudFormation, CDK, Terraform, Pulumi. <br> - Thực hành thiết lập Cloud9, tạo IAM Role và triển khai Lambda Function bằng CloudFormation. | 28/10/2025   | 28/10/2025      | [https://000111.awsstudygroup.com/](https://000111.awsstudygroup.com/) |
| 4   | - Cấu hình và giám sát tài nguyên EC2 bằng Amazon CloudWatch. <br> - Cài đặt CloudWatch Agent, thu thập metric CPU, bộ nhớ, mạng, ổ đĩa. <br> - Áp dụng AWS EC2 Resource Optimization và Compute Optimizer để đề xuất tối ưu chi phí.               | 29/10/2025   | 29/10/2025      | [https://000014.awsstudygroup.com/](https://000014.awsstudygroup.com/) |
| 5   | - Tìm hiểu VPC Flow Logs và cơ chế giám sát lưu lượng IP trong VPC. <br> - Triển khai hạ tầng giám sát mạng qua CloudFormation. <br> - Phân tích log bằng CloudWatch Log Insights để phát hiện sự cố và tối ưu hiệu suất mạng.                          | 30/10/2025   | 30/10/2025      | [https://000105.awsstudygroup.com/](https://000105.awsstudygroup.com/) |
| 6   | - Thực hành phân quyền truy cập Billing Console cho IAM User. <br> - Tạo IAM Policy tùy chỉnh (BillingViewAccess) và gán cho user/group. <br> - Kiểm tra quyền truy cập Billing Console và dọn dẹp tài nguyên sau thực hành.                                | 31/10/2025   | 31/10/2025      | [https://000106.awsstudygroup.com/](https://000106.awsstudygroup.com/) |


### Kết quả đạt được tuần 8:

* A - Infrastructure as Code

    * Hiểu được khái niệm và lợi ích của Infrastructure as Code (IaC) trong quản lý hạ tầng tự động bằng mã nguồn.

    * Phân biệt các framework IaC phổ biến như CloudFormation, CDK, Terraform, Pulumi và hiểu sự khác biệt trong cách triển khai.

    * Nắm được vai trò của IaC trong DevOps và CI/CD, giúp tăng năng suất và đảm bảo tính nhất quán khi triển khai hạ tầng.

    * Thực hành thiết lập môi trường Cloud9, tạo IAM Role với quyền AdministratorAccess và gán vào EC2 Instance.

    * Thực hành sử dụng CloudFormation Template để triển khai Lambda Function và xác nhận kết quả tạo tài nguyên thành công.

    * Triển khai mẫu VPC và EC2 bằng CloudFormation, hiểu rõ cấu trúc template gồm Parameters, Mappings, Resources, Outputs.

    * Kết nối EC2 Instance qua SSM, kiểm tra hoạt động thành công và xác nhận kết nối an toàn không cần mở cổng SSH.

    * Tìm hiểu mô hình triển khai kiến trúc ba tầng (Three-Tier Architecture) gồm Bastion Host, Web Tier, App Tier và Database Tier trên AWS CloudFormation.

    * Thực hành tạo Stack, kiểm tra truy cập giữa các tầng, và dọn dẹp tài nguyên sau khi hoàn tất triển khai.

* B - Right-sizing with EC2 Resource Optimization

    * Nắm vững quy trình thiết lập, cấu hình và giám sát tài nguyên EC2 bằng Amazon CloudWatch để theo dõi hiệu suất thực tế của máy ảo.

    * Tạo và gán thành công IAM Role cho EC2 nhằm kích hoạt CloudWatch Agent và thu thập đầy đủ các metric như CPU, bộ nhớ, mạng và ổ đĩa.

    * Cài đặt và cấu hình CloudWatch Agent để bổ sung các chỉ số tùy chỉnh giúp phân tích chính xác hơn.

    * Áp dụng AWS EC2 Resource Optimization để xác định các máy chủ hoạt động kém hiệu quả và đề xuất biện pháp giảm chi phí hợp lý.

    * Hiểu và thực hành các nguyên tắc right-sizing EC2, kết hợp với chiến lược Saving Plans để tối ưu chi phí.

    * Sử dụng AWS Compute Optimizer để phân tích và nhận đề xuất tối ưu cho EC2, Auto Scaling Group, EBS, Lambda và Fargate dựa trên dữ liệu thực tế.

    * Nắm được điều kiện và giới hạn của Compute Optimizer khi áp dụng cho các loại tài nguyên khác nhau.

* C - Network Monitoring with VPC Flows Logs

    * Hiểu rõ cơ chế hoạt động của VPC Flow Logs và cách thu thập thông tin lưu lượng IP giữa các network interfaces trong VPC.

    * Tạo và triển khai hạ tầng giám sát mạng tự động bằng CloudFormation, bao gồm VPC, subnet, IAM Role và CloudWatch Log Group.

    * Kích hoạt VPC Flow Logs và cấu hình gửi dữ liệu đến Amazon CloudWatch Logs để theo dõi lưu lượng mạng thời gian thực.

    * Thực hành phân tích dữ liệu log bằng CloudWatch Log Insights, giúp phát hiện các vấn đề về bảo mật, cấu hình và hiệu suất mạng.

    * Hoàn thiện quy trình giám sát hạ tầng mạng và hiểu rõ cách áp dụng trong việc tối ưu, kiểm soát, và khắc phục sự cố trong môi trường AWS.

* D - Billing Console Delegation

    * Biết đến quy trình phân quyền truy cập Billing Console trong AWS, giúp đảm bảo quản lý tài chính an toàn và tách biệt quyền giữa các tài khoản.

    * Thực hành kích hoạt quyền truy cập Billing cho IAM Users thông qua mục “IAM User and Role Access to Billing Information” bằng tài khoản root.

    * Tạo IAM Policy tùy chỉnh (BillingViewAccess) để giới hạn quyền truy cập chỉ trong phạm vi quản lý hóa đơn và chi phí.

    * Gán policy cho nhóm hoặc người dùng IAM, đảm bảo phân quyền chính xác và có kiểm soát.

    * Kiểm tra thành công quyền truy cập Billing Console bằng tài khoản IAM được cấp phép.

    * Hoàn tất việc xóa nhóm người dùng và policy, đảm bảo enviroment sạch sẽ sau khi thực hành.

