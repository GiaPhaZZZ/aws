---
title: "Worklog Tuần 12"
date: 2025-11-30
weight: 12
chapter: false
pre: " <b> 1.12 </b> "
---

### Mục tiêu tuần 12:

* Hiểu khái niệm Data Lake và các thành phần cơ bản trên AWS (S3, Glue, Athena, QuickSight)

* Thực hành ingest, xử lý, truy vấn và trực quan hóa dữ liệu trên AWS

* Làm quen với serverless analytics và machine learning workflow bằng SageMaker

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                                                         |
| --- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ---------------------------------------------------------------------- |
| 2   | - Đọc về giới thiệu Data Lake trên AWS <br> | 24/11/2025   | 24/11/2025      | [https://000035.awsstudygroup.com/](https://000035.awsstudygroup.com/) |
| 3   | - Truy vấn dữ liệu bằng Athena <br> - Thực hành thống kê, phân tích dữ liệu | 25/11/2025   | 25/11/2025      | [https://000070.awsstudygroup.com/](https://000070.awsstudygroup.com/) |
| 4   | - Trực quan hóa dữ liệu bằng QuickSight <br> - Tạo Dataset, Visual, Analysis, Dashboard cơ bản <br> - Chia sẻ Dashboard với người dùng khác                                 | 26/11/2025   | 26/11/2025      | [https://000073.awsstudygroup.com/](https://000073.awsstudygroup.com/) |
| 5   | - Thực hành Athena Spark cho ETL và xử lý dữ liệu <br> - Tạo federated query kết nối nhiều nguồn <br> - Theo dõi session, DPU, lịch sử notebook                             | 27/11/2025   | 27/11/2025      | [https://000106.awsstudygroup.com/](https://000106.awsstudygroup.com/) |
| 6   | - Làm quen SageMaker Studio và Feature Store <br> - Feature engineering với Data Wrangler  | 28/11/2025   | 28/11/2025      | [https://000200.awsstudygroup.com/](https://000200.awsstudygroup.com/) |


### Kết quả đạt được tuần 12:

* A - Data Lake Fundamentals on AWS

    * Hiểu về Data Lake và nắm được các thành phần cơ bản:
      * Amazon S3 để lưu trữ dữ liệu
      * AWS Glue để quản lý dữ liệu và ETL
      * Amazon Athena để truy vấn dữ liệu
      * Amazon QuickSight để trực quan hóa dữ liệu

    * Tạo IAM role cho AWS Glue và attach chính sách cần thiết.

    * Tạo S3 bucket để lưu trữ dữ liệu và thiết lập Delivery Stream để thu thập dữ liệu.

    * Tạo dữ liệu mẫu để thử nghiệm quy trình ingest và phân tích dữ liệu.

    * Sử dụng AWS Glue Crawler để ingest dữ liệu từ S3 vào Data Catalog:
      * Tạo Crawler summitcrawler
      * Tạo database summitdb
      * Chạy Crawler và kiểm tra bảng dữ liệu raw đã xuất hiện

    * Sử dụng Amazon Athena để truy vấn dữ liệu:
      * Chạy các câu lệnh SQL kiểm tra dữ liệu
      * Thực hiện các truy vấn thống kê, ví dụ đếm số lượng theo activity_type

    * Tạo và sử dụng SageMaker Notebook để xử lý và biến đổi dữ liệu:
      * Khởi tạo Interactive Session
      * Chạy code Python để làm sạch, biến đổi và phân tích dữ liệu

    * Sử dụng Amazon QuickSight để trực quan hóa dữ liệu:
      * Tạo Data source và Dataset từ S3/Athena
      * Tạo Visual, Analysis và Dashboard
      * Chia sẻ Dashboard với người dùng khác

    * Có khả năng triển khai một quy trình Data Lake trên AWS, từ thu thập, ingest, xử lý, truy vấn đến trực quan hóa dữ liệu.

* B - Building a Data Lake with Your Own Data

  * Khám phá cách xây dựng Data Lake serverless trên AWS và nắm được các thành phần cơ bản:
    * Amazon S3 để lưu trữ dữ liệu gốc và dữ liệu đã xử lý
    * AWS Glue DataBrew để chuẩn hóa, làm sạch và biến đổi dữ liệu
    * AWS Glue Crawler và Jobs để tạo Data Catalog và chuyển đổi dữ liệu sang định dạng Parquet
    * Amazon Athena để truy vấn dữ liệu bằng SQL
    * Amazon QuickSight để trực quan hóa dữ liệu

  * Sử dụng Glue DataBrew để chuẩn hóa và biến đổi dữ liệu:
    * Data profiling, clean & transform
    * Chuẩn bị dataset tiếp theo
    * Upload dữ liệu đã xử lý sang S3 khác

  * Thiết lập AWS Glue cho quy trình ingest dữ liệu:
    * Tạo IAM Role với quyền cần thiết
    * Tạo Data Catalog với Glue Crawler
    * Chạy Glue Jobs để chuyển dữ liệu CSV sang Parquet
    * Tạo Data Catalog mới cho dữ liệu Parquet
    * Kiểm tra schema dữ liệu chuẩn bị cho Athena

  * Truy vấn dữ liệu với Amazon Athena:
    * Thực hiện các truy vấn cơ bản và nâng cao (join, partition, view)
    * So sánh dữ liệu theo columnar vs row-based

  * Trực quan hóa dữ liệu với Amazon QuickSight:
    * Đăng ký và cấu hình quyền truy cập
    * Kết nối dataset và chỉnh sửa dữ liệu
    * Tạo Visual, Analysis và Dashboard để trình bày dữ liệu

  * Thực hiện cleanup các tài nguyên sau workshop:
    * Hủy đăng ký QuickSight và xóa IAM Roles liên quan
    * Xóa Workflows, Jobs, Crawlers và Databases trên AWS Glue
    * Empty và xóa các S3 bucket
    * Xóa Cloud9 instance

* C - Business Intelligence with Amazon QuickSight

  * Tham khảo cách sử dụng Amazon QuickSight để xây dựng dashboard và trực quan hóa dữ liệu:
    * Nắm các khái niệm cơ bản: Data source, Dataset, Analysis, Visual, Dashboard
    * Biết cách kết nối dữ liệu từ S3, Athena hoặc các nguồn khác

  * Chuẩn bị môi trường QuickSight:
    * Tạo tài khoản QuickSight Enterprise
    * Kết nối và đăng ký dữ liệu mẫu (sales.csv)
    * Thiết lập quyền truy cập và vùng hoạt động (Region Singapore)

  * Xây dựng dashboard cơ bản:
    * Cập nhật Dataset
    * Tạo Line Chart, Pie Chart, Pivot Table và thống kê quan trọng
    * Hoàn thiện dashboard hiển thị tổng hợp thông tin

  * Cải tiến dashboard:
    * Sử dụng Sheets để tổ chức các trang thông tin
    * Áp dụng Theme để tùy chỉnh màu sắc, font chữ, khoảng cách hiển thị
    * Cấu hình định dạng trường (Field format) và định dạng trực quan (Visual format) cho từng chart
    * Thêm chi tiết bảng dữ liệu và biểu đồ phụ để nâng cao trực quan hóa

  * Tạo dashboard tương tác:
    * Lưu bản backup của dashboard
    * Thiết lập filter layers và navigation action để dashboard có thể tương tác
    * Xuất bản dashboard và chia sẻ với các người dùng khác

* D - Serverless Analytics with Amazon Athena

  * Tìm hiểu tổng quan về Amazon Athena và các tính năng chính:
    * Athena là dịch vụ phân tích tương tác serverless, hỗ trợ SQL và Python để truy vấn dữ liệu trực tiếp trên S3 hoặc các nguồn dữ liệu khác.
    * Hỗ trợ nhiều nguồn dữ liệu: S3, RDS, Redshift, on-premises, và các dịch vụ đám mây khác.
    * Tích hợp sẵn với AWS Glue Data Catalog để quản lý metadata và schema.

  * Chuẩn bị môi trường và quyền truy cập:
    * Tạo IAM Role cho Glue, CloudFormation và Athena Spark workgroup.
    * Sử dụng CloudFormation để triển khai các tài nguyên cần thiết nhanh chóng.

  * Sử dụng Amazon Athena for Apache Spark:
    * Tạo Workgroup sử dụng Spark engine.
    * Tạo Notebook, chạy các phép tính, sử dụng CloudWatch Logs để giám sát và debug.
    * Tương tác với dữ liệu từ Glue Data Catalog, S3 và các nguồn dữ liệu khác.
    * Thực hiện ETL, chuẩn hóa dữ liệu và lưu kết quả vào S3.

  * Trực quan hóa dữ liệu trong Athena Spark:
    * Sử dụng Matplotlib và Seaborn để tạo biểu đồ thống kê, phân tích dữ liệu và xuất báo cáo.
    * Tích hợp Python libraries bổ sung vào Athena Spark qua pip và S3 để mở rộng khả năng phân tích.

  * Quản lý phiên (Session) và Workgroup:
    * Theo dõi chi tiết phiên, lịch sử tính toán, DPU sử dụng, trạng thái thực thi, và kết quả của các notebook.
    * Sử dụng Workgroup để quản lý các Notebook, Session và các phép tính liên quan.

  * Athena Federation:
    * Thực hiện truy vấn liên kết (federated query) trên nhiều nguồn dữ liệu khác nhau bằng SQL quen thuộc.
    * Hỗ trợ các connector cho RDS, MySQL, PostgreSQL, Redshift.
    * Kết hợp dữ liệu từ nhiều nguồn, lưu kết quả về S3 để tiếp tục phân tích.
    * Tạo Lambda function và VPC endpoint để kết nối dữ liệu federated.

* E - Machine Learning with Amazon SageMaker

  * Biết được các kiến thức về Amazon SageMaker Immersion Day:
    * Giúp học viên nắm từ đầu đến cuối quá trình xây dựng workflow ML: feature engineering, train, tune, deploy model ML.
    * Hướng dẫn chuyển workload ML từ môi trường truyền thống sang SageMaker.
    * Cung cấp kiến thức cơ bản về Model Debugging, Model Monitoring, AutoML và đánh giá workload theo AWS ML Well-Architected lens.

  * Chuẩn bị môi trường SageMaker:
    * Tạo Amazon SageMaker Studio, chọn region Singapore.
    * Tạo user sagemakeruser và role Execution role mặc định.
    * Khởi tạo Notebook Python 3 đầu tiên và mở SageMaker Studio.
    * Tải GitHub repo amazon-sagemaker-immersion-day về Studio.

  * Feature Engineering với Data Wrangler:
    * Import dataset bank-additional-full.csv từ S3.
    * Khám phá dữ liệu, xác định kiểu dữ liệu, tạo phân tích summary.
    * Phân tích tương quan giữa các feature và biến mục tiêu `y`.

  * Sử dụng SageMaker Feature Store:
    * Lưu trữ các feature đã được chuẩn hóa để dùng chung trong team và cho training/inference.
    * Theo dõi metadata và versioning của các feature.
    * Export feature sang Feature Store offline để chuẩn bị dữ liệu train.

  * Export dữ liệu sang S3:
    * Truy xuất dữ liệu từ Feature Store vào Pandas DataFrame.
    * Chia dữ liệu thành train, test, validation.
    * Chuyển đổi dữ liệu về định dạng CSV/libSVM phù hợp với thuật toán XGBoost.
    * Upload dữ liệu lên S3 để chuẩn bị cho bước train.

  * Train, Tune và Deploy XGBoost:
    * Sử dụng thuật toán XGBoost tích hợp sẵn trên SageMaker.
    * Thực hiện training, hyperparameter tuning tự động.
    * Deploy model vào endpoint và đánh giá hiệu suất.
