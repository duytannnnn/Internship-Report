+++
title = "Tự đánh giá"
date = 2026-06-01
weight = 6
pre = " <b> 6. </b> "
+++

## Tổng quan

Trong dự án Serverless AI Invoice Scanner, tôi đảm nhận vai trò AI Processing Developer (Thành viên 4). Nhiệm vụ chính của tôi là xây dựng quy trình xử lý hóa đơn bằng trí tuệ nhân tạo, từ khi người dùng tải hóa đơn lên hệ thống cho đến khi dữ liệu được trích xuất, chuẩn hóa và lưu vào Amazon DynamoDB.

Công việc này yêu cầu hiểu rõ kiến trúc Serverless theo mô hình Event-Driven, đồng thời biết cách tích hợp nhiều dịch vụ AWS để xây dựng một hệ thống xử lý tài liệu tự động và ổn định.

## Nhiệm vụ

Các công việc tôi phụ trách bao gồm:

- Cấu hình Amazon S3 ObjectCreated Trigger.
- Tích hợp Amazon Textract để thực hiện OCR.
- Làm sạch và tiền xử lý dữ liệu OCR.
- Tích hợp OpenAI API để chuyển dữ liệu OCR thành JSON có cấu trúc.
- Chuẩn hóa dữ liệu hóa đơn.
- Lưu dữ liệu vào Amazon DynamoDB.
- Xây dựng cơ chế xử lý lỗi và ghi log bằng Amazon CloudWatch.

## Quy trình xử lý AI

Quy trình xử lý hóa đơn được thực hiện theo các bước:

1. Người dùng tải hóa đơn lên Amazon S3.
2. Sự kiện ObjectCreated kích hoạt AWS Lambda.
3. Lambda gửi tài liệu sang Amazon Textract.
4. Textract trích xuất toàn bộ nội dung văn bản.
5. Dữ liệu OCR được làm sạch và tiền xử lý.
6. Nội dung được gửi đến OpenAI API.
7. OpenAI phân tích và chuyển đổi thành dữ liệu JSON chuẩn.
8. Dữ liệu được lưu vào Amazon DynamoDB.
9. Amazon CloudWatch ghi log để hỗ trợ giám sát và xử lý lỗi.

## Công nghệ sử dụng

Trong quá trình thực hiện, tôi đã làm việc với:

- AWS Lambda
- Amazon S3
- Amazon Textract
- Amazon DynamoDB
- Amazon CloudWatch
- AWS IAM
- OpenAI API
- JSON
- Python

## Khó khăn và cách giải quyết

Trong quá trình phát triển, tôi gặp một số khó khăn như sau.

### Độ chính xác của OCR

Một số hóa đơn có chất lượng ảnh thấp hoặc bố cục phức tạp khiến kết quả OCR chưa chính xác.

Để cải thiện chất lượng dữ liệu, tôi thực hiện bước làm sạch văn bản trước khi gửi sang AI nhằm giảm nhiễu và tăng độ chính xác.

### Chuẩn hóa dữ liệu

Mỗi nhà cung cấp sử dụng định dạng hóa đơn khác nhau.

OpenAI API được sử dụng để chuyển dữ liệu OCR thành cùng một cấu trúc JSON gồm:

- Invoice Number
- Customer Name
- Invoice Date
- Total Amount

Việc này giúp quá trình lưu trữ và truy vấn dữ liệu trở nên đơn giản hơn.

### Xử lý lỗi

Trong quá trình gọi Amazon Textract hoặc OpenAI API có thể xảy ra lỗi.

Để đảm bảo hệ thống hoạt động ổn định, tôi bổ sung cơ chế Exception Handling, kiểm tra dữ liệu đầu vào và ghi log bằng Amazon CloudWatch để thuận tiện cho việc theo dõi và xử lý lỗi.

## Kiến thức và kỹ năng đạt được

Dự án mang lại cho tôi nhiều kinh nghiệm thực tế về điện toán đám mây và kiến trúc Serverless.

Thông qua quá trình thực hiện, tôi hiểu rõ hơn cách các dịch vụ AWS phối hợp với nhau để xây dựng một hệ thống xử lý tài liệu tự động.

Những kiến thức và kỹ năng tôi học được bao gồm:

- Hiểu kiến trúc Serverless trên AWS.
- Hiểu mô hình Event-Driven Architecture.
- Sử dụng Amazon S3 để lưu trữ tài liệu.
- Làm việc với AWS Lambda để xử lý sự kiện tự động.
- Tìm hiểu Amazon Textract trong nhận dạng ký tự OCR.
- Quản lý dữ liệu bằng Amazon DynamoDB.
- Theo dõi hệ thống bằng Amazon CloudWatch.
- Quản lý quyền truy cập bằng AWS IAM.
- Tích hợp dịch vụ AI thông qua OpenAI API.
- Xử lý và chuẩn hóa dữ liệu JSON.
- Nâng cao kỹ năng Prompt Engineering.
- Hiểu quy trình triển khai ứng dụng trên nền tảng AWS.

Ngoài các kiến thức kỹ thuật, tôi còn cải thiện kỹ năng làm việc nhóm, sử dụng GitHub để quản lý mã nguồn, phối hợp với các thành viên khác và giải quyết các vấn đề phát sinh trong quá trình phát triển dự án.

## Cảm nhận cá nhân

Dự án giúp tôi hiểu rõ hơn cách kết hợp trí tuệ nhân tạo với các dịch vụ điện toán đám mây để xây dựng những hệ thống tự động hóa phục vụ doanh nghiệp.

Việc ứng dụng AWS Serverless giúp hệ thống dễ mở rộng, giảm chi phí vận hành và không cần quản lý máy chủ. Đồng thời, AI giúp giảm thời gian nhập liệu thủ công, hạn chế sai sót và nâng cao hiệu quả xử lý hóa đơn.

Sau khi hoàn thành dự án, tôi tích lũy được nhiều kinh nghiệm thực tế về AWS, AI, OCR và phát triển ứng dụng Serverless. Đây sẽ là nền tảng quan trọng để tôi tiếp tục nghiên cứu và phát triển các giải pháp Cloud và AI trong tương lai.