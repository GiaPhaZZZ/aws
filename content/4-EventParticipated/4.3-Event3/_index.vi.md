---
title: "Reinventing DevSecOps with AWS Generative AI"
date: 2025-10-16
weight: 3
chapter: false
pre: " <b> 4.3. </b> "
---

# Bài thu hoạch “Reinventing DevSecOps with AWS Generative AI”

### Mục Đích Của Sự Kiện

- Chia sẽ về DevSecOps đã có những bước chuyển mình trong tự động hoá vận hành hệ thống bằng AI như thế nào.
- Cung cấp kiến thức chit tiết về quy trình DecSecOps 
- Giải đáp thắc mắc các kỹ sư DevSecOps đang ứng dụng AI như thế nào để tái định hình chu trình và kiến tạo những thay đổi ?

### Danh Sách Diễn Giả

- **Lê Thanh Đức** - Cloud Delivery Manager, CMC Global
- **Dư Quốc Thành** - Technical Leader, CMC Global
- **Văn Hoàng Kha** - Cloud Engineer, AWS Community Builder

### Nội Dung Nổi Bật

#### Giới thiệu tổng quan về Devsecops

- Framework Devsecops không chỉ là chu trình Devops thông thường.
- Tích hợp bảo mật cho nhiều part và cả vòng đời.

#### Debsecops Lifecycle

-  Vòng đời của Devsecops bao gồm bảy thành phần chính, bắt đầu từ lên kế hoạch cho đến triển khai vận hành. Chi tiết sẽ được nêu ở bên dưới:

Dưới đây là nội dung tất cả các bước trong **DEVSECOPS LIFECYCLE** được viết theo định dạng bạn yêu cầu:

- **1. PLAN - Lập kế hoạch:**
    - Xác định yêu cầu & rủi ro bảo mật ngay từ đầu.
    - Thống nhất mục tiêu giữa Dev-Sec-Ops.
    - Tạo security roadmap gắn với mục tiêu dự án.

- **2. CODE - Viết mã:**
    - Áp dụng secure coding standard & code review.
    - Dùng SAST để phát hiện lỗi sớm.
    - Hình thành tư duy "security-first" cho developer.

- **3. BUILD - Xây dựng:**
    - Tự động kiểm tra bảo mật trong CI/CD pipeline.
    - Thực hiện dependency & binary scan.
    - Đảm bảo build an toàn và nhất quán.

- **4. TEST - Kiểm thử:**
    - Chạy vulnerability scan, DAST, pen test.
    - Xác thực ứng dụng đáp ứng yêu cầu bảo mật.
    - Cập nhật test theo lỗ hổng mới phát sinh.

- **5. DEPLOY - Triển khai:**
    - Kiểm tra config & IaC trước khi deploy.
    - Tự động giám sát cấu hình runtime.
    - Giảm lỗi thủ công, đảm bảo deploy an toàn.

- **6. OPERATE - Vận hành:**
    - Tự động vá lỗi & cập nhật bảo mật liên tục.
    - Có incident response và theo dõi hiệu năng.
    - Duy trì ổn định và an toàn sau release.

- **7. MONITOR - Giám sát:**
    - Theo dõi liên tục hoạt động & mối đe dọa.
    - Dùng real-time analytics & alerting tools.
    - Phát hiện sớm, phản ứng nhanh với rủi ro.

#### Giới thiệu các công cụ cho DEVSECOPS TOOLCHAIN

- **Pre-commit & Code Quality** : 
    - SonarQube, Codacy, Semgrep (SAST), Gitleaks – kiểm tra code & secrets trước khi commit.

- **Dependency & SBOM Scanning** : 
    - Syft, Grype, Dependency-Track – quản lý package & lỗ hổng thư viện.

- **IaC & Policy-as-Code** : 
    - Checkov, TFsec – quét Terraform/Kubernetes config.
    - OPA Gatekeeper, Kyverno – enforce policy & compliance tự động.

- **SAST / DAST & Security Tests**
    - Trivy, Checkmarx, Semgrep, Codacy – phát hiện lỗ hổng ở code & runtime.

- **CI/CD Integration**
    - Jenkins, GitHub Actions, Gitlab CI, ArgoCD – tự động hoá build, test, deploy an toàn.

- **Monitoring & Logging**
    - Prometheus, Grafana, Loki, Promtail – giám sát & quan sát hệ thống real-time.

- **Alerting & Governance**
    - Slack webhook, Email alerts, AI anomaly detection – cảnh báo & phản ứng nhanh.
    - Centralized risk report – báo cáo và phân tích rủi ro tập trung.

#### Lợi ích của GENAI trong DevsecOps

- **1. Tự động hóa & tăng tốc quy trình DevSecOps**
    - Code review & Security scanning tự động
    - Pipeline Generation
    - IaC Generation

- **2. Tăng cường bảo mật chủ động**
    - Threat modeling bằng ngôn ngữ tự nhiên
    - Policy-as-code generation
    - Dynamic scanning augmentation

- **3. Tối ưu hóa quan sát và phản ứng sự cố**
    - Incident summary & Root cause analysis
    - ChatOps Integration
    - Anomaly Detection

### Những Gì Học Được

#### Chiến Lược tích hợp AI vào quy trình làm việc

- AI giúp phát hiện sự cố và phân tích lỗ hổng tốt hơn
- Về phản ứng và khắc phục lỗi cũng tiết kiệm được nhiều thời gian
- Giúp giảm tải công việc bản thân phải làm nhưng vẫn giữ kết quả tốt
- Cho phép chu trình Devsecops học liên tục và cải thiện theo thời gian

#### Ứng Dụng Amazon Q vào coding

- Sử dụng Amazon Q để hỗ trợ phần code.
- Cân nhắc kỹ lưỡng hơn có nên chấp thuận hành động tiếp theo của AI hay không
- Có thể sử dụng để tự tìm tài liệu từu nhiều nguồn và xem đề xuất

### Trải nghiệm trong sự kiện

Tham gia workshop **“Reinventing DevSecOps with AWS Generative AI”** mang lại cho tôi nhiều góc nhìn thực tế về cách AI đang thay đổi toàn bộ quy trình DevSecOps — từ lập kế hoạch, viết mã, kiểm thử, đến vận hành và giám sát hệ thống. Dưới đây là những trải nghiệm đáng nhớ nhất:

#### Trải nghiệm kỹ thuật thực tế

* Được nghe các chuyên gia trình bày chi tiết về **DevSecOps Lifecycle** với từng giai đoạn cụ thể, từ **Plan – Code – Build – Test – Deploy – Operate – Monitor**, giúp tôi hiểu rõ cách tích hợp bảo mật xuyên suốt toàn bộ quy trình phát triển phần mềm.
* Quan sát các ví dụ thực tế về **CI/CD pipeline có tích hợp kiểm tra bảo mật tự động**, giúp nhận thức được tầm quan trọng của việc phát hiện lỗ hổng sớm.

#### Ứng dụng công cụ hiện đại

* Được hướng dẫn sử dụng **Amazon Q** trong quy trình DevSecOps — từ hỗ trợ viết mã an toàn, tạo IaC, đến gợi ý khắc phục lỗi tự động.
* Tìm hiểu về **các công cụ trong DevSecOps toolchain** như SonarQube, Checkov, Trivy, Prometheus, Grafana,... và cách chúng phối hợp để xây dựng quy trình bảo mật end-to-end.
* Thấy rõ vai trò của **AI trong việc tạo, kiểm thử, và triển khai mã một cách an toàn hơn**, đặc biệt với **policy-as-code** và **threat modeling bằng ngôn ngữ tự nhiên**.

#### Kết nối và trao đổi

* Có cơ hội **thảo luận trực tiếp với các chuyên gia DevSecOps đến từ AWS và CMC Global**, qua đó học hỏi được kinh nghiệm triển khai thực tế trong các dự án lớn.
* Trao đổi cùng cộng đồng kỹ sư về cách **kết hợp AI vào DevSecOps pipeline**, giúp tôi có thêm ý tưởng ứng dụng AI trong công việc hằng ngày.

#### Bài học rút ra

* DevSecOps không chỉ là tự động hóa quy trình CI/CD, mà là **tích hợp bảo mật như một phần cốt lõi** của toàn bộ vòng đời phát triển phần mềm.
* Việc áp dụng **AI và GenAI** giúp tăng tốc phát hiện lỗ hổng, tự động hóa quy trình kiểm thử, và cải thiện khả năng phản ứng với sự cố.
* **Amazon Q** là công cụ tiềm năng giúp lập trình viên và kỹ sư bảo mật **tối ưu quy trình phát triển**, giảm khối lượng công việc thủ công, và nâng cao hiệu suất tổng thể.
* DevSecOps hiệu quả cần **sự phối hợp chặt chẽ giữa con người – quy trình – công nghệ**, với AI đóng vai trò là “trợ lý thông minh” hỗ trợ quyết định và hành động chính xác hơn.


#### Một số hình ảnh khi tham gia sự kiện

<p align="center">
  <img src="/images/4-EventParticipated/event_3/photo1.png" alt="Picture 1" />
  <br/>
  <strong style="font-size: 18px;">Hình 1</strong>
</p>

<p align="center">
  <img src="/images/4-EventParticipated/event_3/photo2.png" alt="Picture 2" />
  <br/>
  <strong style="font-size: 18px;">Hình 2</strong>
</p>

<p align="center">
  <img src="/images/4-EventParticipated/event_3/photo3.png" alt="Picture 3" />
  <br/>
  <strong style="font-size: 18px;">Hình 3</strong>
</p>

> Tổng thể, sự kiện đã cho tôi biết thêm rất nhiều về Devsecops cũng như sự tiện dụng của AI khi được tích hợp vào quy trình phát triễn.

