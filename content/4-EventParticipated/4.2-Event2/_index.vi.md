---
title: "Data Science on AWS"
date: 2025-10-16
weight: 2
chapter: false
pre: " <b> 4.2. </b> "
---

# Bài thu hoạch “Data Science on AWS”

### Mục Đích Của Sự Kiện

- Giới thiệu các dịch vụ chuyên dụng của AWS dành cho lĩnh vực AI

- Giải thích các khái niệm về học máy

- Demo sử dụng một vài dịch vụ

### Danh Sách Diễn Giả

- **Văn Hoàng Kha** - Cloud Solutions Architect, AWS Community Builder
- **Bạch Doãn Vương** - Cloud Develops Engineer, AWS Community Builder

### Nội Dung Nổi Bật

#### Các tiện ích của dịch vụ Cloud cho Data Science

- Cung cấp api cho các mô hình, giảm thời gian phải code.
- Hỗ trợ làm sạch, chuyển đổi dữ liệu hiệu quả
- Giúp xử lý hàng loạt, song song
- Huấn luyện mô hình trên AWS có nhiều nền tảng hỗ trợ
- Trợ giúp triển khai, dùng và đóng gói mô hình.

#### Các khái niệm cơ bản trong lĩnh vực Data Science

- **AI**: Kỹ thuật cho phép máy tính mimic trí tuệ ngươi bằng logic, mệnh đề if-then và học máy.
- **Machine Learning:** Là một tâp hợp con của AI, dùng máy để tìm kiếm pattern trong data và xây dựng logic model.
- **Deep Learning:** Tập hợp con của Machine Learning, bao gồm mạng neural nhiều lớp phục vụ được nhiều tác vụ.
- **Generative AI:** Mạng tạo sinh, học từ mô hình và bộ dữ liệu của các hãng công nghệ lớn, có khả năng sáng tạo và tạo mới hoàn toàn.

#### Amazon Comprehend

- Là dịch vụ của AWS giúp phân loại và phân tích văn bản.
- Hỗ trợ cá nhân hóa PII (Personal Identifile Information)
- Hiểu được nhiều ngôn ngữ và sentiment trong văn bản
- Chắt lọc được event và key phrase

#### Amazon Translate

- Chuyên về dịch thuật và tóm tắt thông tin, co thể dùng để tạo data cho chatbot.
- Dễ tương tác với các ứng dụng, có độ chính xác cao.
- Đây là dịch vụ fully-managed, hoàn toàn do người dùng kiểm soát.

#### Amazon Textract

- Hỗ trợ trích xuất văn bản, dữ liệu từ mọi virtally document.
- Giúp Chuyển đổi văn bản từ ngôn ngữ này sang ngôn ngữ khác.

#### Amazon Polly và Amazon Transcribe

- Là dịch vụ text-to-speech (Polly) và speech-to-text (Transcribe)
- Hỗ trợ khả năng chuyển đổi sang nhiều ngôn ngữ.

#### Amazon Lex

- Giúp tạo conversational interface cho bất cứ application nào
- Tạo giao diện nhanh chónh - đẹp, tiết kiệm thời gian.
- Dễ dùng, cho ra high-quality text với built-in intergration.

#### Amazon Rekognition

- Cho phép người dùng phân tích ảnh và video với độ chính xác cao
- Ví dụ như dùng để kiểm duyệt các chi tiết nhạy cảm trong phim ảnh.

#### Amazon Personalise

- Cá nhân hóa trải nghiệm của người dùng
- Không cần tích hợp machine learning
- Thu thập và dùng các user metadata, item metadata, ...

#### Feature Engineering

- Feature Engineering là quá trình làm cho máy hiểu dữ liệu được đưa vào.
- Giải quyết các vấn đề làm sao để encode, chuyển đổi về ngôn ngữ máy nhanh nhất - tốt nhất.
- Ví dụ như chỉnh sửa file dữ liệu thiếu, bị lỗi không hoàn chỉnh -> Làm sạch dữ liệu là một phần của feature engineering

#### Machine Learning Process

- Không chỉ đơn giản về xây dựng mô hình ML.
- Bao gồm cả các bước phân tích bussniness problem, đánh giá mô hình đã đạt được như mong muốn hay chưa.
- Kèm theo cả phần triển khai cho end-user dùng và cải thiện lâu dài.


### Những Gì Học Được

#### Hiểu rõ hơn về Data Science

- **Biết được định nghĩa kỹ thuật của nhiều khái niệm**: Artifical Intellegence, Machine Learning, Deep Learning, Generative AI.
- **Học về quy trình ML Process**: Đó không chỉ là code và tạo mô hình, mà còn gồm nhiều bước đánh giá và triển khai.
- **Hiểu được sự tiện ích khi sử dụng dịch vục AWS**: Giúp tiết kiệm thời gian hơn, cho ra kết quả tốt và tối ưu chi phí.

### Ứng Dụng Vào Công Việc

- **Áp dụng Amazon Translate** Tích hợp vào các dự án sắp tới trong tương lại
- **Dùng Amazon Textract**: Dùng để hỗ trợ trích xuất thông tin torng văn bản nhanh, tiết kiệm thời gian.
- **Chú tâm vào Feature Engineering**: Vì quá trình xử lý bài toàn và dữ liệu là bước đầu và khá quan trọng, sẽ ảnh hưởng đến những phần sau nên cần được chú ý nhiều hơn khi làm việc.


### Trải nghiệm trong event

Tham dự workshop **“Data Science on AWS”** là một cuộc phiêu lưu ấn tượng khi được dấn thân vào miền tri thức tràn đầy các kiến thức và dịch vụ cloud bổ ích sẽ hỗ trợ rất nhiều trong công việc và học tập.

#### Gặp gỡ các diễn giả có chuyên môn cao
- Hai anh diễn giả từ AWS đã mang lại phần trình bày tuyệt vời và đầy bổ ích, mang lại cho bản thân em sự hứng thú về nền tảng cloud cũng như các dịch vụ mà nó offer.
- Nhiều câu hỏi hay từ phía khán giả đã được đặt ra, giúp em hiểu sâu hơn về chuyên nghành mình đang theo học cùng xu hướng công nghệ hiện nay.

#### Trực tiếp xem qua Demo độc đáo
- Anh Kha đã cho xem một phần demo sử dụng các dịch vụ để xây dựng một mô hình machine learning là thế nào. 
- Phần demo rất dễ hiểu và gãy gọn, cho thấy được nhiều sự tiện ích của AWS.

#### Bài học rút ra
- Việc áp dụng các dịch vụ AWS cho xây dựng và triển khai mô hình ML hiện nay là không thể thiếu. Không chỉ tiết kiệm thời gian mà còn mang lại hiệu suất cao với độ chính xác tốt.
- Machine Learning Process không chỉ nằm ở quá trình xây dựng mô hình mà còn phải đi giải bài toán bussiness problem cho khách hàng cũng như phải tính toán việc triển khai, nâng cấp lâu dài cho sản phẩm sau khi ra mắt.
- Các dịch vụ như Amazon Regkognition có hỗ trợ api rất tiện lợi nếu được tích vào các project để sử dụng.

#### Một số hình ảnh khi tham gia sự kiện

<p align="center">
  <img src="/images/4-EventParticipated/event_2/photo1.jpg" alt="Picture 1" />
  <br/>
  <strong style="font-size: 18px;">Hình 1</strong>
</p>

<p align="center">
  <img src="/images/4-EventParticipated/event_2/photo2.jpg" alt="Picture 2" />
  <br/>
  <strong style="font-size: 18px;">Hình 2</strong>
</p>

<p align="center">
  <img src="/images/4-EventParticipated/event_2/photo3.jpg" alt="Picture 3" />
  <br/>
  <strong style="font-size: 18px;">Hình 3</strong>
</p>

<p align="center">
  <img src="/images/4-EventParticipated/event_2/photo4.jpg" alt="Picture 4" />
  <br/>
  <strong style="font-size: 18px;">Hình 4</strong>
</p>

> Tổng thể, sự kiện không chỉ cung cấp kiến thức kỹ thuật mà còn giúp em thay đổi cách tư duy về Machine Learning và Cloud Engineer.