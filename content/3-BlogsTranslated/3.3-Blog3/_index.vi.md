---
title: "Blog 3"
date: 2025-09-26
weight: 3
chapter: false
pre: " <b> 3.3. </b> "
---

# Ra mắt universal installers dành cho AWS CLI v2 trên macOS

bởi Andrew Asseily | on 11 THÁNG 9 2025 | in Announcements, AWS CLI |


Amazon Web Services (AWS) thông báo ra mắt universal macOS installers cho AWS Command Line Interface (AWS CLI) v2.

## Có gì mới !

Bắt đầu từ phiên bản phiên bản 2.30.0 của AWS CLI v2, các trình cài đặt AWS CLI sẽ hỗ trợ tệp nhị phân phổ quát (universal binary support) cho macOS, hoạt động trên cả chip Apple silicon và bộ xử lý Intel chỉ với một lần tải xuống. Điều này giúp loại bỏ nhu cầu sử dụng Rosetta, một compatibility layer cho phép các ứng dụng dựa trên Intel phải chạy trên máy Mac sử dụng chip Apple silicon.

## Cập nhật các bản cài đặt AWS CLI hiện có

Nếu bạn đang sử dụng AWS CLI v2 trên máy Mac với chip Apple silicon, chúng tôi khuyến nghị bạn nâng cấp lên phiên bản mới nhất để cài đặt các native binaries.
Những thay đổi này sẽ chỉ ảnh hưởng đến các trình cài đặt AWS CLI chính thức—việc biên dịch AWS CLI từ nguồn sẽ được tiếp tục hỗ trợ cho kiến trúc hệ thống chủ (host architecture).
Nếu có câu hỏi hoặc phản hồi, hãy liên hệ với chúng tôi ngay trên GitHub.


**Andrew Asseily**

Andrew hiện đang là Software Development Engineer tại AWS CLI team. Ngoài công việc, anh ta còn là người đam mê võ thuật Brazilian Jiu-Jitsu.
