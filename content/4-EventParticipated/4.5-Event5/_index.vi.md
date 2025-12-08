---
title: "AWS Cloud Mastery Series #2"
date: 2025-11-17
weight: 5
chapter: false
pre: " <b> 4.5. </b> "
---

# Bài thu hoạch “Devops on aws”

### Mục đích của sự kiện

* Giới thiệu các nguyên tắc DevOps và tư duy văn hóa đằng sau mô hình phát triển phần mềm hiện đại
* Trình diễn cách xây dựng pipeline CI/CD tự động trên AWS
* Hướng dẫn triển khai Infrastructure as Code (IaC)
* So sánh các dịch vụ container của AWS để triển khai ứng dụng hiện đại
* Trình bày các thực tiễn tốt nhất về khả năng quan sát và giám sát hệ thống

### Danh sách diễn giả

* **Bao Huynh** – AWS Community Builder
* **Thinh Nguyen** – AWS Community Builder
* **Vi Tran** – AWS Community Builder

### Nội dung nổi bật

#### Hiểu về tư duy devops

* Kết hợp giữa phát triển và vận hành → Tăng tốc độ release
* Tự động hóa giảm, thao tác thủ công và tăng tính nhất quán
* Vòng phản hồi liên tục → Hệ thống ổn định và đáng tin cậy hơn

#### Ci/cd pipeline trên aws

Pipeline tự động hoàn toàn gồm bốn giai đoạn:
* **source control**: CodeCommit quản lý và phiên bản hóa code
* **build & test**: CodeBuild biên dịch, kiểm thử và đóng gói ứng dụng
* **deployment**: CodeDeploy triển khai rolling, canary và blue/green
* **orchestration**: CodePipeline kết nối tất cả các bước thành workflow liên tục

#### Infrastructure as code (iac)

Chuyển từ thiết lập thủ công sang môi trường tự động, có kiểm soát version.

* **aws cloudformation**
  * Template YAML/JSON khai báo
  * Resources, parameters, conditions, outputs
  * Drift detection đảm bảo trạng thái môi trường nhất quán

* **aws cdk (cloud development kit)**
  * Định nghĩa hạ tầng bằng TypeScript, Python, Java, v.v.
  * L1/L2/L3 constructs cho mẫu reusable
  * CLI synthesize, diff và deploy stack

#### Containers trên aws

Tổng quan Docker và lựa chọn compute cho container:
* **amazon ecr**: registry bảo mật, hỗ trợ quét lỗ hổng
* **amazon ecs**: điều phối AWS-native, chạy trên EC2 hoặc Fargate
* **amazon eks**: Kubernetes được quản lý cho workloads chuẩn
* **aws app runner**: triển khai container đơn giản, ít vận hành

#### Observability và monitoring
Xây dựng khả năng quan sát hệ thống hiện đại:
* **amazon cloudwatch**
  * Metrics, logs, alarms, dashboards
* **aws x-ray**
  * Tracing phân tán để xác định bottleneck và microservice chậm

Tập trung vào cảnh báo hành động được, dashboards có ý nghĩa, và theo dõi chủ động.

### Những Gì Học Được

#### Thực hành devops

* Tự động hóa → tốc độ + độ tin cậy
* Đồng bộ văn hóa giữa dev và ops
* Sử dụng DORA để cải thiện
* Kết hợp phản hồi ở mọi giai đoạn phát triển

#### Infrastructure as code

* Giảm cấu hình thủ công trong production
* CloudFormation cho workflow khai báo AWS-native
* CDK cho định nghĩa hạ tầng linh hoạt, lập trình được
* Xem hạ tầng như phần mềm: test, version, automate

#### Triển khai ứng dụng

* Pipeline CI/CD giảm lỗi con người
* Chọn chiến lược deploy theo rủi ro (rolling, canary, blue/green)
* Tích hợp kiểm thử tự động ở mọi bước

#### Chiến lược container

* Container mang tính di động, nhất quán, kiến trúc modular
* ECS → mô hình vận hành đơn giản
* EKS → linh hoạt với Kubernetes
* App Runner → triển khai ít vận hành
* ECR là nền tảng quản lý image

#### Tăng cường kỹ năng của bản thân

* Kết hợp metrics, logs, traces cho cái nhìn 360°
* Dashboards CloudWatch + maps dịch vụ X-Ray để khắc phục sự cố
* Xây dựng cảnh báo chủ động, không phản ứng khi sự cố xảy ra

### Ứng dụng vào công việc
* **Tự động hóa CI/CD** với CodePipeline, CodeBuild, CodeDeploy để tối ưu release
* **Áp dụng IaC** với CloudFormation hoặc CDK thay thế thiết lập thủ công, đảm bảo nhất quán
* **Container hóa dịch vụ** và chọn ECS, EKS hoặc App Runner dựa trên workload
* **Nâng cao khả năng quan sát** với CloudWatch metrics, logs, alarms và dashboards tùy chỉnh
* **Kích hoạt distributed tracing** bằng AWS X-Ray để khắc phục sự cố microservice
* **Sử dụng DORA** để đo hiệu suất và cải thiện DevOps

### Trải nghiệm trong event

Tham gia workshop **“Cloud mastery series #2 – devops on aws”** mang lại cả hướng chiến lược và kiến thức thực tiễn để triển khai DevOps quy mô lớn.

#### Học hỏi từ các diễn giả có chuyên môn
* Diễn giả giải thích rõ CI/CD, container, IaC, monitoring
* Các case study thực tế minh họa DevOps hoạt động trong môi trường production

#### Trải nghiệm kỹ thuật thực tế

* Quan sát pipeline chạy từ commit → build → deploy
* Hiểu CloudFormation và CDK giúp enforce hạ tầng lặp lại
* Làm rõ trade-offs giữa ECS, EKS và App Runner cho orchestration container

#### Ứng dụng công cụ hiện đại

* IaC giúp nhất quán và giảm drift
* CloudWatch và X-Ray là nền tảng cho vận hành chuẩn hóa

#### Kết nối và thảo luận
* Cơ hội kết nối chuyên gia và đồng nghiệp
* Thảo luận nhấn mạnh văn hóa, tự động hóa và cải tiến đo lường được

#### Bài học rút ra
* Tự động hóa là nhân tố cải thiện chính
* Observability cần thiết cho sự ổn định
* Chọn compute/container phù hợp giảm gánh nặng vận hành

#### Một số hình ảnh sự kiện

<p align="center">
  <img src="/images/4-EventParticipated/event_5/photo1.jpg" alt="Ảnh 1" />
  <br/>
  <strong style="font-size: 18px;">Hình 1</strong>
</p>

<p align="center">
  <img src="/images/4-EventParticipated/event_5/photo2.jpg" alt="Ảnh 2" />
  <br/>
  <strong style="font-size: 18px;">Hình 2</strong>
</p>

<p align="center">
  <img src="/images/4-EventParticipated/event_5/photo3.jpg" alt="Ảnh 3" />
  <br/>
  <strong style="font-size: 18px;">Hình 3</strong>
</p>

> Tổng kết, workshop đã cung cấp kiến thức toàn diện và thực tiễn về DevOps, CI/CD, IaC, orchestration container và monitoring.