---
title: "AWS Cloud Mastery Series #3"
date: 2025-12-05
weight: 7
chapter: false
pre: " <b> 4.7. </b> "
---

# Summary Report: “Security - AWS Well-Architected Security Pillar”

### Mục Đích Của Sự Kiện

* Giới thiệu các nguyên tắc cốt lõi của **AWS Well-Architected Security Pillar**
* Tăng cường kiến thức nền tảng về indetity, giám sát và phản ứng khi gặp sự cố
* Thúc đẩy sự phát triển cộng đồng thông qua học tập, hợp tác và tạo nội dung

### Danh Sách Diễn Giả

* Lê Vũ Xuân An - FCJ Member
* Trần Đức Anh - FCJ Member
* Trần Đoàn Công Lý - FCJ Member
* Danh Hoàng Hiếu Nghi - FCJ Member

### Nội Dung Nổi Bật

#### Tổng quan về AWS Cloud Club — Security Track

* Lộ trình **badging** có cấu trúc giúp ghi nhận tiến bộ và đóng góp của thành viên
* **Core team** là nền tảng của câu lạc bộ, hỗ trợ thành viên mới và dẫn dắt các sáng kiến
* Thành viên nhận badge khi tham gia workshop và có thể đổi lấy phần thưởng
* Thành viên đóng góp bằng cách tạo **nội dung kỹ thuật** và bài đăng mạng xã hội
* Điểm nhấn lớn trong năm là sự kiện **Student Community Day**
* Lợi ích cho thành viên bao gồm:
  *Nâng cao kỹ năng
  *Xây dựng cộng đồng
  *Nhận thêm cơ hội việc làm

#### IAM (Identity & Access Management)

* Quản lý danh tính là nền tảng của mọi chiến lược bảo mật trên AWS
* Gán quyền dựa trên **least privilege**, chỉ cấp đúng những gì user/service cần
* Loại bỏ access key dài hạn; ưu tiên sử dụng **IAM roles**
* Bật **MFA** cho tất cả người dùng để tăng cường xác thực
* Sử dụng **AWS Single Sign-On (IAM Identity Center)** để quản lý truy cập đồng nhất
* Không phụ thuộc vào credit miễn phí để thử nghiệm; nên dùng AWS Organizations để quản lý tài khoản đúng cách
* **Service Control Policies (SCPs)** thiết lập guardrail cho nhiều tài khoản (tính năng cấp doanh nghiệp)
* Dùng **Permission Boundaries** để ngăn mở rộng quyền ngoài ý muốn
* Hạn chế tạo IAM user với thông tin đăng nhập dài hạn
* Hỗ trợ phương thức xác thực mạnh: **TOTP** và khóa cứng **FIDO2**
* **IAM Access Analyzer** giúp phát hiện truy cập công khai hoặc cross-account không mong muốn

#### Detection & Continuous Monitoring

* Triển khai **quan sát đa lớp** để hiểu điều gì đang xảy ra trong môi trường
* Dùng **Amazon EventBridge** để tự động gửi cảnh báo khi có hoạt động bất thường
* Áp dụng **Detection-as-Code**: quản lý rule và automation dưới dạng code để đảm bảo tính nhất quán
* Đảm bảo log từ CloudTrail, CloudWatch và VPC Flow Logs được tập trung để phân tích

#### Amazon GuardDuty

* Giải quyết các mối quan tâm quan trọng của doanh nghiệp:
  * Không biết hệ thống có đang bị tấn công hay không
  * Thời gian phản hồi chậm
  * Rủi ro về tuân thủ
  * Chi phí bất thường do hành vi độc hại

* GuardDuty sử dụng **machine learning** và threat intelligence để phát hiện hành vi đáng ngờ
* Tích hợp hoàn chỉnh với **EventBridge** để tự động hóa quy trình
* Tính năng nâng cao gồm **S3 Protection**, **RDS Protection**, và sơ đồ chuỗi tấn công
* Cung cấp **phát hiện thời gian thực**, gợi ý khắc phục và định tuyến sự kiện đa tài khoản

#### AWS Security Hub

* Quản lý nhiều dịch vụ AWS khiến việc theo dõi cảnh báo trở nên khó khăn
* **Security Hub** gom các alert từ mọi dịch vụ về một định dạng thống nhất
* Giúp duy trì tuân thủ theo tiêu chuẩn AWS và CIS
* Cung cấp **hướng dẫn khắc phục từng bước**
* Hỗ trợ quản lý **nhiều tài khoản** và **nhiều vùng (region)**

#### Network Layer Security

* Chiến lược phòng thủ nhiều lớp bắt đầu từ thiết kế VPC an toàn
* Sử dụng **Security Groups** và **Network ACLs** để giới hạn lưu lượng mạng
* Giám sát hành vi mạng bằng **VPC Flow Logs**
* Thiết kế mạng tách biệt, tối thiểu quyền và tránh phơi bày ra public nếu không cần thiết
* Tích hợp AWS Network Firewall hoặc PrivateLink khi cần

#### Incident Response

* Chuẩn bị các **playbook phản ứng sự cố** cho cô lập, điều tra, xử lý và phục hồi
* Tự động hóa bước phản ứng quan trọng bằng EventBridge, Lambda và Security Hub
* Thực hành tabletop để kiểm tra mức độ sẵn sàng
* Ghi lại quy trình escalations, thông tin liên lạc và đánh giá sau sự cố

### Những Gì Học Được

#### Tư duy bảo mật

* **Bảo mật là quá trình liên tục** — danh tính, giám sát và phản ứng sự cố phải phát triển theo hệ thống
* Least privilege và xác thực mạnh là cốt lõi của bảo mật IAM
* Quản trị đa tài khoản và đa vùng đảm bảo sự nhất quán

#### Thực hành kỹ thuật

* Dùng GuardDuty và Security Hub để có khả năng quan sát end-to-end
* Tự động cảnh báo và workflow bằng EventBridge
* Áp dụng Detection-as-Code để theo phiên bản và tái sử dụng
* Thiết kế bảo mật nhiều lớp và giới hạn truy cập không cần thiết

#### Phát triển & Cộng đồng

* Thành viên phát triển cả kỹ năng kỹ thuật lẫn kỹ năng lãnh đạo
* Câu lạc bộ khuyến khích hợp tác, chia sẻ và tạo nội dung
* Hệ thống badge thúc đẩy động lực và giúp thể hiện chuyên môn cloud

### Trải nghiệm trong event

Tham dự workshop **Master 3 — Security** mang lại cái nhìn toàn diện về thực hành bảo mật hiện đại trên AWS. Những trải nghiệm nổi bật:

#### Học từ chuyên gia

* Core team chia sẻ kinh nghiệm thực tế về IAM, công cụ giám sát và quản trị cloud
* Các ví dụ tình huống giúp củng cố best practice về IAM và bảo mật tổ chức

#### Hiểu sâu qua trải nghiệm trực quan

* Thảo luận về permission boundaries, SCP và IAM roles giúp giải quyết khó khăn thường gặp
* Demo GuardDuty và Security Hub giúp hình dung rõ cách AWS phát hiện và phản hồi đe dọa

#### Tự động hóa và khả năng quan sát

* Ví dụ EventBridge minh họa cách cảnh báo và workflow được tự động hóa
* Quan sát quá trình detection → remediation giúp nhấn mạnh tầm quan trọng của visibility trong kiến trúc bảo mật

#### Bài học kinh nghiệm

* Identity là tuyến phòng thủ đầu tiên
* Giám sát liên tục (Continuous Monitorign) là điều thiết yếu
* Tự động hóa giảm rủi ro và thời gian phản hồi
* Quản trị trên nhiều tài khoản và vùng là cần thiết trong môi trường thực tế

#### Một số hình ảnh khi tham gia sự kiện

<p align="center">
  <img src="/images/4-EventParticipated/event_7/photo1.jpg" alt="Picture 1" />
  <br/>
  <strong style="font-size: 18px;">Hình 1</strong>
</p>

<p align="center">
  <img src="/images/4-EventParticipated/event_7/photo2.jpg" alt="Picture 2" />
  <br/>
  <strong style="font-size: 18px;">Hình 2</strong>
</p>

<p align="center">
  <img src="/images/4-EventParticipated/event_7/photo3.jpg" alt="Picture 3" />
  <br/>
  <strong style="font-size: 18px;">Hình 3</strong>
</p>

> Tổng thể, sự kiện giúp tôi củng cố kiến thức về bảo mật cloud và nâng cao sự đánh giá đối với các best practice của AWS. Đồng thời, sự kiện cũng nhấn mạnh giá trị của cộng đồng học tập và hợp tác.
