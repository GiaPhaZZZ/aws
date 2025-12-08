---
title: "AWS Cloud Mastery Series #1"
date: 2025-11-15
weight: 4
chapter: false
pre: " <b> 4.4. </b> "
---

# Bài Thu Hoạch “AI/ML/GenAI on AWS Workshop”

### Mục Tiêu Của Sự Kiện

* Giới thiệu tổng quan về hệ sinh thái AI/ML của AWS
* Trình bày về Generative AI với Amazon Bedrock
* Khám phá các ứng dụng thực tế của Prompt Engineering và RAG
* Minh họa cách các dịch vụ AI tích hợp vào sản phẩm chạy trên nền tảng đám mây
* Giới thiệu AgentCore – nền tảng xây dựng AI agent quy mô lớn, sẵn sàng cho môi trường production

### Diễn Giả

* **Lam Tuấn Kiệt** – Senior DevOps Engineer, FPT Software
* **Đặng Hoàng Hiếu Nghi** – AI Engineer, Reonova Cloud
* **Đinh Lê Hoàng Anh** – Cloud Engineer Trainee, FCJ


### Nội Dung Nổi Bật

#### Chuyển Đổi Từ Traditonal ML Sang Foundation Models

**Traditional ML models**

* Giải quyết từng nhiệm vụ cụ thể
* Phụ thuộc vào dữ liệu đã được gắn nhãn
* Khả năng tổng quát kém

**Generative AI (Foundation Models)**

* Huấn luyện trên lượng lớn dữ liệu *không gắn nhãn*
* Học theo phương pháp tự giám sát
* Có thể thực hiện nhiều tác vụ chỉ thông qua **prompt**
* Bedrock hỗ trợ nhiều nhà cung cấp mô hình lớn:
  **OpenAI, DeepSeek, Anthropic Claude, Meta Llama, Amazon Titan**


#### Kiến Thức Cốt Lõi Về Prompt Engineering

**Prompt là gì?**
Tập hợp hướng dẫn để điều khiển kết quả của mô hình.

**Các kỹ thuật chính**

* **Zero-shot prompting**: Chỉ cung cấp yêu cầu → kết quả nhanh nhưng đôi khi sai
* **Few-shot prompting**: Đưa ví dụ mẫu để định hình phong cách trả lời
* **Chain-of-Thought prompting**: Hướng dẫn mô hình suy luận từng bước → đầu ra chi tiết và chất lượng cao


#### Retrieval-Augmented Generation (RAG)

* Tăng độ chính xác bằng cách bổ sung **kiến thức bên ngoài có liên quan**

**Quy trình:**

1. Người dùng đưa ra prompt
2. Hệ thống tìm tài liệu liên quan
3. Ghép nội dung vào ngữ cảnh
4. Mô hình tạo ra câu trả lời dựa trên thông tin đã bổ sung

**Embeddings**

* Chuyển văn bản → vector mang ý nghĩa ngữ nghĩa
* Giúp phân cụm các khái niệm tương tự
* **Titan Text Embeddings** hỗ trợ **hơn 100 ngôn ngữ**

RAG giúp giảm hallucination và tạo câu trả lời dựa trên dữ liệu thực tế.


#### Tổng Quan Dịch Vụ AI Trên AWS

Các API AI sẵn sàng dùng:

* **Rekognition** – Phát hiện đối tượng trong ảnh/video
* **Translate** – Dịch và nhận dạng ngôn ngữ
* **Textract** – Trích xuất văn bản và bố cục tài liệu
* **Transcribe** – Chuyển giọng nói thành văn bản, nhận dạng người nói
* **Polly** – Chuyển văn bản thành giọng nói
* **Comprehend** – NLP, phân tích cảm xúc
* **Kendra** – Tìm kiếm thông minh cho doanh nghiệp
* **Lookout Family** – Phát hiện bất thường: chỉ số, thiết bị, hình ảnh
* **Personalize** – Cá nhân hóa
* **Pipecat** – Framework phát triển pipeline AI agent

#### Amazon Bedrock AgentCore

Nền tảng giúp đơn giản hóa việc xây dựng và triển khai **AI agents**:

**Tự động hóa những phần phức tạp trong production GenAI**, bao gồm:

* Scaling
* Context memory
* Identity & access control
* Tích hợp công cụ và API
* Điều phối workflow
* Quan sát hệ thống & logging

**Các thành phần chính**

* **Runtime** – Thực thi tác vụ nhiều bước
* **Memory** – Lưu trữ tương tác trước đó
* **Identity** – Định nghĩa quyền truy cập
* **Gateway** – Truy cập tập trung các dịch vụ & công cụ
* **Code Interpreter** – Môi trường chạy code an toàn
* **Browser tool** – Truy xuất thông tin từ web
* **Observability** – Log, metric, debugging


### Những Điều Rút Ra Được

#### Tư Duy Phát Triển AI & Cloud

* Doanh nghiệp đang chuyển từ mô hình ML truyền thống sang **sản phẩm cloud-native tích hợp AI**
* Cần xây dựng **dự án thực tế**, không chỉ là bài tập trên trường
* Foundation Model + dịch vụ đám mây = phát triển sản phẩm nhanh hơn, tối ưu chi phí

#### Kiến Thức Kỹ Thuật

* Hiểu được tác động của **prompt engineering** đến chất lượng kết quả
* RAG nâng cao độ chính xác và bổ sung tri thức có cấu trúc
* Embeddings giúp tìm kiếm ngữ nghĩa và phân cụm mạnh mẽ
* Dịch vụ AI của AWS bao phủ end-to-end: giọng nói, văn bản, hình ảnh, phát hiện bất thường

#### Phát Triển Agent

* AgentCore giúp đơn giản hóa các workflow vốn đòi hỏi nhiều DevOps
* Hữu ích trong việc xây dựng:
  * Chatbots
  * Automation agents
  * Research assistants
  * Ứng dụng chuyên biệt


### Ứng Dụng Vào Công Việc

* Xây dựng **prototype sản phẩm thực** để đưa vào CV
* Dùng **RAG** cho các hệ thống AI theo domain
* Tích hợp API AI của AWS để tăng tốc độ phát triển tính năng
* Triển khai **Bedrock Agents** cho tác vụ nhiều bước
* Khai thác embeddings cho semantic search/phân loại
* Luyện tập prompt engineering để tối ưu đầu ra mô hình


### Trải Nghiệm Tại Sự Kiện

Tham gia workshop **“AI/ML/GenAI on AWS”** mang lại rất nhiều kiến thức thực tiễn về phát triển AI hiện đại trên đám mây AWS.

#### Kiến Thức Từ Các Diễn Giả

* Diễn giả từ FPT, Reonova Cloud và AWS chia sẻ cách doanh nghiệp triển khai AI tối ưu chi phí.
* Hiểu rõ cách AI được ứng dụng trong vision, text, speech và automation.

#### Thực Hành Kiến Thức GenAI

* Nắm rõ sự khác biệt giữa **Foundation Models** và ML truyền thống
* Hiểu các kiểu prompting và lý do chúng quan trọng
* Xem ví dụ thực tế về pipeline RAG giúp tăng độ chính xác

#### Trải Nghiệm Công Cụ AWS

* Hiểu vai trò của Rekognition, Textract, Transcribe, Translate, Comprehend
* Khám phá cách **Bedrock AgentCore** đơn giản hóa việc xây dựng ứng dụng GenAI quy mô lớn

#### Bài Học Rút Ra

* AI + Cloud giúp đẩy nhanh việc phát triển sản phẩm thực tế
* Prompt engineering và RAG là nền tảng cho GenAI doanh nghiệp
* AgentCore là bước tiến tiếp theo cho kiến trúc AI hiện đại


### Một Số Hình Ảnh Trong Sự Kiện

<p align="center">
  <img src="/images/4-EventParticipated/event_4/photo1.jpg" alt="Ảnh 1" />
  <br/>
  <strong style="font-size: 18px;">Hình 1</strong>
</p>

<p align="center">
  <img src="/images/4-EventParticipated/event_4/photo2.jpg" alt="Ảnh 2" />
  <br/>
  <strong style="font-size: 18px;">Hình 2</strong>
</p>

<p align="center">
  <img src="/images/4-EventParticipated/event_4/photo3.jpg" alt="Ảnh 3" />
  <br/>
  <strong style="font-size: 18px;">Hình 3</strong>
</p>

</p>

> Tổng quan, workshop mang lại góc nhìn chiến lược và kiến thức kỹ thuật thực tiễn, giúp củng cố nền tảng quan trọng cho việc phát triển AI/ML trên AWS.
