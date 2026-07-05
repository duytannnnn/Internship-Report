+++
title = "Week 8 Worklog "
date = 2026-06-01
weight = 8
chapter = false
pre = " <b> 1.8. </b> "
+++

##  Thông tin cơ bản
- **Họ và tên**: Trương Lê Duy Tân
- **MSSV**: 2280602878
- **Lớp**: 22DTHH1
- **Ngành**: Công nghệ thông tin
- **Đơn vị thực tập**: AWS Cloud Training
- **Vị trí thực tập**: Thực tập sinh AWS Cloud
- **Ngày bắt đầu tuần**: 01/06/2026
- **Tuần thực tập**: Tuần thứ 8/12

##  Mục tiêu tuần này
- Nghiên cứu các dịch vụ cơ sở dữ liệu cốt lõi trên AWS bao gồm Amazon RDS và Amazon DynamoDB.
- Tìm hiểu kiến trúc phi máy chủ (Serverless) nâng cao với AWS Lambda và Amazon API Gateway.
- Tổng hợp toàn bộ kiến thức đã tích lũy để phác thảo sơ đồ kiến trúc cho Mini Project ứng dụng 3 tầng (3-Tier Architecture).

##  Công việc đã thực hiện

### 1. Triển khai Cơ sở dữ liệu đám mây và Kiến trúc Serverless
- **Mô tả**: Học lý thuyết về cơ sở dữ liệu quan hệ Amazon RDS (MySQL) và cơ sở dữ liệu NoSQL cấu trúc khóa-giá trị Amazon DynamoDB. Tiến hành khởi tạo thực tế một database instance trên RDS đặt cô lập trong vùng mạng Private Subnet. Đồng thời, tìm hiểu dịch vụ tính toán hướng sự kiện AWS Lambda và cách phơi bày các API ra ngoài Internet bằng Amazon API Gateway.
- **Kết quả**: Nắm vững cách thức vận hành hệ thống cơ sở dữ liệu đám mây an toàn, biết cách viết các hàm Lambda đơn giản để xử lý logic dữ liệu mà không cần bận tâm đến việc quản lý hệ điều hành máy chủ.

### 2. Thiết kế Sơ đồ Kiến trúc Mini Project 3-Tier
- **Mô tả**: Tổng hợp toàn bộ các khối kiến thức đã thực hành từ tuần 1 đến nay để phác thảo sơ đồ kiến trúc hệ thống hoàn chỉnh cho Mini Project cuối khóa. Hệ thống được thiết kế theo mô hình tiêu chuẩn bao gồm: Tầng giao diện (S3 Static Website Hosting kết hợp CloudFront) -> Tầng logic xử lý nghiệp vụ (ECS Fargate hoặc Application EC2 được bảo vệ phía sau Application Load Balancer) -> Tầng dữ liệu (Amazon RDS MySQL).
- **Kết quả**: Hoàn thành bản vẽ sơ đồ kiến trúc chi tiết, phân chia rõ ràng các dải IP mạng (Subnetting) và thiết lập mối quan hệ bảo mật giữa các nhóm Security Group chéo nhau để chuẩn bị triển khai thực tế.
- **Tools/Tech**: Amazon RDS, Amazon DynamoDB, AWS Lambda, Amazon API Gateway, Draw.io, AWS Architecture Icons.

##  Kiến thức học được

###  Technical Skills
- **AWS Services**: Amazon RDS (MySQL), Amazon DynamoDB, AWS Lambda, Amazon API Gateway.
- **System Design**: Kỹ năng thiết kế, phân rã kiến trúc hệ thống phần mềm 3 tầng đạt chuẩn bảo mật độc lập và tối ưu chi phí vận hành trên Cloud.

###  Concepts & Theory
- **New Concepts**: Tư duy Serverless (Không máy chủ) - lập trình viên hoàn toàn tập trung vào mã nguồn tối ưu logic, hệ thống Cloud tự động lo liệu hoàn toàn việc co giãn băng thông và vận hành hạ tầng bên dưới.
- **Best Practices**: Luôn bật tính năng Multi-AZ cho Amazon RDS trong môi trường Production để tự động backup, đồng bộ dữ liệu sang một Availability Zone khác phòng khi xảy ra sự cố thiên tai tại trung tâm dữ liệu chính.

##  Khó khăn và giải pháp
- **Vấn đề**: Hàm AWS Lambda không thể kết nối và truy vấn dữ liệu từ Amazon RDS instance vừa thiết lập.
- **Root Cause**: Theo mặc định, dịch vụ AWS Lambda chạy ngoài môi trường VPC nên không có đường nối trực tiếp nội bộ vào vùng Private Subnet của RDS, đồng thời Security Group của RDS đang chặn toàn bộ traffic từ bên ngoài internet.
- **Solution**: Tiến hành cấu hình gán VPC cho hàm Lambda, lựa chọn các Private Subnet tương ứng, đồng thời bổ sung một quy tắc Inbound rule vào Security Group của RDS cho phép nhận kết nối an toàn từ chính Security Group của Lambda.

##  Reflection & Insights
- Việc chuyển dịch kiến trúc sang Serverless giúp hệ thống trở nên cực kỳ gọn nhẹ và tiết kiệm chi phí cho doanh nghiệp, vì hệ thống chỉ tính tiền trên từng mili-giây mã nguồn thực thi thực tế thay vì phải trả tiền treo máy chủ liên tục.

##  Kế hoạch tuần tiếp theo
- Chuẩn bị theo dõi và tham gia cuộc thi tìm hiểu kiến thức dịch vụ AWS nội bộ dành cho thực tập sinh (Tuần 9).
- Đi sâu nghiên cứu mảng dịch vụ bảo mật nâng cao: Amazon Cognito, Trust Policy và các cơ chế cấu hình IAM Role phức tạp.

##  Self Assessment
- Productivity: 8.5/10
- Learning: 9/10
- Collaboration: 7/10