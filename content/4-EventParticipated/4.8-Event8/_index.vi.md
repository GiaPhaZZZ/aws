---
title: "CLOUDTHINKER"
date: 2025-12-05
weight: 8
chapter: false
pre: " <b> 4.8. </b> "
---

# Bào thu hoạch: “BUILDING AGENTIC AI - Context Optimization with Amazon Bedrock”

### Mục tiêu Sự kiện

* Cung cấp cái nhìn có hệ thống về **Agentic AI** và sự chuyển dịch sang các hệ thống AI tự động
* Giới thiệu **Amazon Bedrock AgentCore** và hệ sinh thái agentic của AWS
* Trình bày thiết kế **Agentic Workflow** trong các ứng dụng thực tế trên AWS
* Giới thiệu **CloudThinker Agentic Orchestration** và các kỹ thuật tối ưu hóa ngữ cảnh
* Hướng dẫn thực hành xây dựng ứng dụng agentic bằng AWS Bedrock
* Tạo không gian kết nối với các chuyên gia trong ngành AI và điện toán đám mây


### Diễn giả

* **Nguyễn Gia Hưng** – Head of Solutions Architect, AWS
* **Kiên Nguyễn** – Solutions Architect, AWS
* **Việt Phạm** – Founder & CEO, Diaflow
* **Thắng Tôn** – Co-founder & COO, CloudThinker
* **Henry Bùi** – Head of Engineering, *CloudThinker
* **Kha Van** – Community Leader, AWS


### Những điểm nổi bật

#### Sự phát triển của Agentic AI

**ML/AI truyền thống**

* Nhiệm vụ cố định, năng lực hạn chế
* Cần dữ liệu có cấu trúc và xử lý tiền đề phức tạp
* Khó mở rộng và kém linh hoạt

**Agentic AI hiện đại**

* Dựa trên Foundation Models và khả năng suy luận đa bước
* Tự động phân rã nhiệm vụ và sử dụng công cụ
* Có thể tích hợp API, thực thi workflow, truy xuất tri thức
* Linh hoạt và sẵn sàng sản xuất khi kết hợp với các dịch vụ AWS

#### Thách thức khi triển khai Agentic AI vào sản xuất

* Hiệu năng – độ trễ, suy luận song song, tốc độ xử lý token
* Khả năng mở rộng – multi-agent, quản lý ngữ cảnh
* Bảo mật – quản trị dữ liệu, luồng định danh, quyền truy cập
* Governance – khả năng quan sát, nhật ký, phạm vi nhiệm vụ

#### Bộ dịch vụ Agentic AI của AWS

* **Amazon Bedrock AgentCore** – identity, memory, runtime, tools, workflows
* **Agent Gateway** – tích hợp API và công cụ thống nhất
* **Tự do lựa chọn mô hình** – Anthropic, Meta Llama, Amazon Titan,...
* **Thiết kế hướng sản xuất** – khả năng mở rộng, guardrails, quan sát

#### Amazon Bedrock AgentCore (từ AWS)

* **Runtime** – Quản lý luồng thực thi đa bước
* **Memory** – Lưu trữ ngữ cảnh ngắn hạn và dài hạn
* **Identity Flow** – Kiểm soát quyền và các ranh giới bảo mật
* **Agent Gateway** – Kết nối công cụ, API, hệ thống nội bộ
* **Code Interpreter** – Môi trường chạy mã an toàn
* **Browser Tool** – Thu thập thông tin từ web
* **Observability** – Tracing, logs, metrics phục vụ quản trị & giám sát

#### Xây dựng Agentic Workflow trên AWS (Use Case bởi Diaflow)

* Phối hợp nhiều agent
* Truy xuất ngữ cảnh và function calling
* Kết nối agent với các nguồn dữ liệu doanh nghiệp
* Điều phối logic doanh nghiệp qua Bedrock & công cụ của Diaflow
* Các mô hình triển khai thực tế cho startup và SME

#### CloudThinker: Orchestration và Tối ưu hoá Ngữ cảnh

* Chiến lược điều phối giữa các agent
* Lọc và tối ưu hóa ngữ cảnh giúp giảm chi phí và tăng hiệu quả
* Thích nghi workflow theo thời gian thực
* Đánh giá độ tin cậy chain-of-thought
* Tích hợp CloudThinker vào Bedrock AgentCore

#### CloudThinker Hack: Phiên thực hành

* Cài đặt Bedrock agents
* Xây dựng pipeline agentic cơ bản
* Tích hợp công cụ bên ngoài vào workflow
* Debug và tối ưu hành vi agent
* Triển khai một bản proof-of-concept hoàn chỉnh

### Những điểm rút ra quan trọng

#### Tư duy Agentic AI

* AI đang dịch chuyển từ phản hồi → **hành động**
* Agent cần tích hợp memory, tools, orchestrator, và identity
* Foundation Models + Orchestration = Thế hệ ứng dụng AI mới
* AWS cung cấp môi trường sản xuất mạnh nhất cho Agentic AI

#### Hiểu biết kỹ thuật

* Tầm quan trọng của **tối ưu hóa ngữ cảnh**
* Cách tools và identity flow ảnh hưởng đến độ tin cậy
* Vì sao AgentCore đơn giản hóa reasoning nhiều bước
* Giá trị thực tế của các mô hình điều phối
* Kết nối FM với API, logic doanh nghiệp, kho dữ liệu

#### Kỹ năng phát triển thực hành

* Thiết kế workflow AI end-to-end
* Kết nối công cụ bên ngoài vào pipeline agent
* Quản lý tương tác multi-agent
* Hiểu rõ độ trễ, khả năng mở rộng, bảo mật
* Triển khai agent an toàn với guardrails & monitoring

### Ứng dụng vào công việc

Người tham gia có thể áp dụng ngay:

* Xây dựng **assistant dựa trên agent**, quy trình tự động hoặc copilots nội bộ
* Tích hợp mô hình Bedrock vào hệ thống doanh nghiệp
* Sử dụng AgentCore để tạo workflow nhiều bước có kiểm soát
* Tăng tốc prototyping mà **không cần hạ tầng DevOps phức tạp**
* Kết hợp diễn orchestration của CloudThinker để tối ưu hiệu năng
* Áp dụng mẫu thiết kế agentic cho startup hoặc dự án doanh nghiệp

### Trải nghiệm sự kiện

Sự kiện **“Agentic Build AI – Optimization with Amazon Bedrock”** mang lại góc nhìn sâu sắc về phát triển AI hiện đại.

#### Kiến thức từ chuyên gia

* Diễn giả từ **AWS, CloudThinker, Diaflow** chia sẻ kinh nghiệm triển khai thực tế
* Hướng dẫn rõ ràng về mở rộng sản phẩm GenAI
* Ví dụ thực tiễn về tự động hóa agent trong doanh nghiệp

#### Trải nghiệm thực hành

* Xây dựng pipeline agent hoàn chỉnh
* Hiểu cách memory, identity và tool phối hợp
* Thành thạo API và công cụ orchestration của Bedrock

#### Cơ hội giao lưu

* Gặp gỡ kiến trúc sư AWS, kỹ sư, founder và cộng đồng
* Thảo luận về nghề nghiệp và phát triển AI cloud-native

#### Bài học rút ra

* Agentic AI là bước tiếp theo sau chatbot và LLM
* Triển khai thực tế cần identity, scale và quan sát
* Bedrock + CloudThinker là con đường nhanh nhất đến sản xuất
* Dự án thực tế mang lại giá trị vượt xa lý thuyết

### Một số hình ảnh sự kiện

<p align="center">
  <img src="/images/4-EventParticipated/event_8/photo1.jpg" alt="Picture 1" />
  <br/>
  <strong style="font-size: 18px;">Hình 1</strong>
</p>

<p align="center">
  <img src="/images/4-EventParticipated/event_8/photo2.jpg" alt="Picture 2" />
  <br/>
  <strong style="font-size: 18px;">Hình 2</strong>
</p>

<p align="center">
  <img src="/images/4-EventParticipated/event_8/photo3.jpg" alt="Picture 3" />
  <br/>
  <strong style="font-size: 18px;">Hình 3</strong>
</p>

> Tóm lại, workshop “Agentic Build AI – Optimization with Amazon Bedrock” mang đến sự kết hợp mạnh mẽ giữa kiến thức chiến lược và trải nghiệm thực hành. Người tham gia nắm được kỹ năng triển khai agentic workflow, tối ưu ngữ cảnh, tích hợp công cụ, và xây dựng hệ thống AI có khả năng mở rộng và an toàn.
