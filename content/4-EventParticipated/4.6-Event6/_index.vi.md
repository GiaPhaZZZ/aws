---
title: "AWS Edge Services Wokrshop"
date: 2025-11-19
weight: 6
chapter: false
pre: " <b> 4.6. </b> "
---

# Bài Thu Hoạch “AWS Edge Services Workshop - Amazon CloudFront As Your Foundation”

### Mục Đích Của Sự Kiện

* Hiểu cách Amazon CloudFront nâng cao bảo mật, hiệu suất và tối ưu chi phí
* Học các best practices về edge caching, phân phối nội dung và bảo vệ origin
* Khám phá khả năng của CloudFront cho nội dung tĩnh, động và quy mô lớn
* Nhận kiến thức thực tiễn về triển khai edge logic và chiến lược failover

### Danh Sách Diễn Giả

* **Nguyễn Gia Hưng** – Head of Solutions Architect, Edge Technical Field Community, Amazon Web Services Việt Nam

### Nội Dung Nổi Bật

#### Gói giá ưu đãi mới

* **Chi Phí CDN Khó Lường:** Thanh toán dựa trên usage có thể dẫn đến hóa đơn cao khi traffic tăng hoặc bị tấn công
* **Giải Pháp:** Gói AWS Fixed-Price CDN + Security, giúp chi phí hàng tháng dự đoán được và giảm rủi ro tài chính
  * Gói gồm: CloudFront, WAF, Shield AMR, Route 53, CloudWatch Logging, S3 storage credits
  * Giá cố định hàng tháng bất kể usage

#### Khả Năng Của CloudFront

**Bảo Mật Và Bảo Vệ**

* **Hỗ Trợ HTTPS/TLS:**
  * Giảm kích thước key để tăng hiệu suất và giảm độ trễ
  * Sử dụng TLS library (s2n) để xác thực đích đến
  * Hỗ trợ TLS 1.3, chứng chỉ ECDSA, và tùy chọn sẵn sàng cho post-quantum

* **Mutual TLS (2-way):** Hỗ trợ xác thực client certificate, sắp triển khai trên CloudFront

* **Origin Cloaking:**
  * VPC Origin: ẩn origin khỏi internet, sử dụng ALB private
  * Origin Access Control (OAC): signed requests cho S3, Lambda, MediaPackage, không cần API Gateway
  * Custom Origins: giới hạn IP CloudFront, thêm header tùy chỉnh với secret định sẵn

* **Access Control:** Giới hạn theo địa lý, Signed URLs theo thời gian, đường dẫn URL và xác thực IP client

**Tối Ưu Chi Phí**
* Tự động nén object (đến 10 GB, bỏ qua file đã nén) - cần bật chế độ nén
* AWS miễn phí transfer từ origin đến CloudFront
* Giảm tải origin: giảm chi phí CPU và load balancer

**Độ Tin Cậy Và Khả Năng Phục Hồi**
* Caching với TTL và stale content delivery
* Built-in failover tới origin phụ còn khỏe
* Graceful failure: phục vụ nội dung cache hoặc trang lỗi tùy chỉnh

**Tăng Cường Hiệu Suất**
* Multi-layer caching: Regional Edge Caches + Origin Shield
* Request collapsing để giảm duplicate requests
* Persistent connections đến origin để tránh TCP handshakes thừa
* Edge logic thực thi với CloudFront Functions hoặc Lambda@Edge

#### Các Trường Hợp Sử Dụng

* **Trường Hợp Sử Dụng:**
  * Tài nguyên web tĩnh
  * Phân phối toàn bộ website (hiệu suất toàn cầu, bảo mật, high availability)
  * Tăng tốc API (reuse connection, giảm độ trễ)
  * Streaming media và tải file lớn (resumable, edge caching)

* **Best Practices:**
  1. Quan sát toàn bộ: monitor trải nghiệm người dùng và đường đi request
  2. Caching tối đa: chuẩn hóa cache keys, chọn TTL phù hợp, cache lỗi để chống brute-force
  3. Chặn request không mong muốn: detect malicious pattern, implement rate limiting
  4. Offload business logic: di chuyển processing nhẹ lên edge, ví dụ CloudFront Functions
  5. Failover tự động: cấu hình Route 53 health check hoặc CloudFront origin group

### Những Gì Học Được

* CloudFront là **nền tảng toàn diện** cho bảo mật, hiệu suất và tối ưu chi phí tại edge
* Edge caching và logic giúp giảm tải origin và cải thiện tốc độ phản hồi
* Các tính năng bảo mật (TLS, mutual TLS, origin cloaking, signed URLs) bảo vệ nội dung ở edge
* Thực hành best practices đảm bảo **high availability, caching tối ưu, và resilience**

### Ứng Dụng Vào Công Việc

* Bật nén và multi-layer caching cho nội dung tĩnh và động
* Triển khai Signed URLs và OAC cho nội dung nhạy cảm
* Di chuyển business logic nhẹ lên CloudFront Functions để tăng tốc phản hồi
* Monitor metrics và logs tại edge để duy trì visibility và phát hiện traffic không mong muốn
* Cấu hình failover để đảm bảo high availability

### Trải Nghiệm Trong Sự Kiện

Tham gia **AWS Edge Services Workshop** rất bổ ích, cung cấp cái nhìn sâu về **bảo mật, hiệu suất và khả năng vận hành của CloudFront**. Các trải nghiệm chính bao gồm:

#### Học Hỏi Từ Diễn Giả Chuyên Gia

* Hung Nguyen Gia chia sẻ **kinh nghiệm thực tế và ví dụ thực tiễn** về tối ưu edge
* Hiểu rõ **tất cả tính năng của CloudFront** để phân phối nội dung toàn cầu

#### Trải Nghiệm Kỹ Thuật Thực Tế

* Học cách cấu hình **origin cloaking** và **origin access control**
* Khám phá chiến lược compression, caching, và persistent connections
* Hiểu cách **edge logic** giảm độ trễ và cải thiện scalability

#### Ứng Dụng Best Practices

* Quan sát toàn bộ và chiến lược xử lý lỗi
* Cấu hình caching nâng cao để đạt hiệu quả tối đa
* Kỹ thuật chặn request độc hại và offload processing lên edge

#### Một Số Hình Ảnh Khi Tham Gia Sự Kiện

<p align="center">
  <img src="/images/4-EventParticipated/event_6/photo1.jpg" alt="Picture 1" />
  <br/>
  <strong style="font-size: 18px;">Hình 1</strong>
</p>

<p align="center">
  <img src="/images/4-EventParticipated/event_6/photo2.jpg" alt="Picture 2" />
  <br/>
  <strong style="font-size: 18px;">Hình 2</strong>
</p>

<p align="center">
  <img src="/images/4-EventParticipated/event_6/photo3.jpg" alt="Picture 3" />
  <br/>
  <strong style="font-size: 18px;">Hình 3</strong>
</p>

> Tổng thể, workshop nhấn mạnh tầm quan trọng của **bảo mật, hiệu suất và độ tin cậy tại edge**, đồng thời cung cấp các chiến lược thực tế để triển khai CloudFront trong môi trường doanh nghiệp.
