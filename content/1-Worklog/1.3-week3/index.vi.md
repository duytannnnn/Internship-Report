+++
title = "Week 3 Worklog "
date = 2026-04-27
weight = 3
chapter = false
pre = " <b> 1.3. </b> "
+++

##  Thông tin cơ bản
- **Họ và tên**: Trương Lê Duy Tân
- **MSSV**: 2280602878
- **Lớp**: 22DTHH1
- **Ngành**: Công nghệ thông tin
- **Đơn vị thực tập**: AWS Cloud Training
- **Vị trí thực tập**: Thực tập sinh AWS Cloud
- **Ngày bắt đầu tuần**: 27/04/2026
- **Tuần thực tập**: Tuần thứ 3/12

##  Mục tiêu tuần này
- Xem video playlist số 21 đến 30 về Amazon S3.
- Thực hành tạo S3 Bucket, upload/download và quản lý vòng đời đối tượng.
- Cấu hình S3 Static Website Hosting.

##  Công việc đã thực hiện

### 1. Nghiên cứu lý thuyết Amazon S3 (Simple Storage Service)
- **Mô tả**: Học về mô hình lưu trữ đối tượng (Object Storage), cấu trúc định danh toàn cầu của Bucket Name, các phân lớp lưu trữ (S3 Standard, Intelligent-Tiering, Standard-IA, Glacier) để tối ưu hóa chi phí dựa trên tần suất truy cập dữ liệu.

### 2. Lab cấu hình S3 và Phân quyền Đối tượng
- **Mô tả**: 
  - Tạo một S3 bucket với tên duy nhất trên toàn hệ thống: `tan-fcj-internship-bucket`.
  - Thực hành upload các file tài liệu và hình ảnh lên bucket thông qua AWS Console.
  - Bật tính năng Bucket Versioning để quản lý các phiên bản khác nhau của cùng một file khi bị ghi đè hoặc xóa nhầm.
  - Cấu hình Lifecycle Policy: Tự động chuyển các file sau 30 ngày không sử dụng từ Standard sang S3 Standard-IA để tiết kiệm chi phí.
- **Kết quả**: Bucket hoạt động chính xác, cơ chế Versioning lưu trữ đầy đủ lịch sử thay đổi của tệp tin.

### 3. Thực hành Triển khai Static Website trên S3
- **Mô tả**: Viết một file `index.html` và `error.html` đơn giản. Tải lên S3 bucket, tắt tính năng "Block all public access" và thêm Bucket Policy cho phép mọi người dùng Internet có quyền `s3:GetObject`. Bật tính năng Static website hosting.
- **Kết quả**: Truy cập thành công vào trang web tĩnh thông qua Endpoint URL do Amazon cung cấp.
- **Tools/Tech**: Amazon S3, HTML, AWS Bucket Policy.

##  Kiến thức học được

###  Technical Skills
- **AWS Services**: Amazon S3, S3 Object Versioning, S3 Lifecycle Rules.
- **Security**: Quản lý truy cập S3 qua Bucket Policy và Block Public Access.

###  Concepts & Theory
- **New Concepts**: Sự khác biệt giữa Block Storage (EBS gắn liền với EC2) và Object Storage (S3 độc lập, truy cập qua API/HTTP). Cách thiết kế một hệ thống lưu trữ phi cấu trúc tối ưu chi phí.

##  Khó khăn và giải pháp
- **Vấn đề**: Sau khi bật tính năng Static Website Hosting và bấm vào link Endpoint, trình duyệt trả về lỗi "403 Forbidden".
- **Root Cause**: Mặc dù đã tắt tính năng "Block all public access" ở ngoài, nhưng chưa thêm mã Bucket Policy dạng JSON để cấp quyền đọc đối tượng công khai cho các file bên trong.
- **Solution**: Vào phần Permissions -> Bucket Policy -> Thêm đoạn mã JSON chứa Action `s3:GetObject` với Principal là `*`. Lưu lại và reload trang web, lỗi 403 biến mất, giao diện website hiển thị thành công.

##  Reflection & Insights
- Tốc độ và độ bền vững (durability lên tới 99.999999999%) của S3 thực sự ấn tượng. Việc biến một bucket lưu trữ thành một hosting chạy website tĩnh chỉ trong vài click chuột cho thấy tính linh hoạt tuyệt vời của hạ tầng đám mây.

##  Kế hoạch tuần tiếp theo
- Chuyển sang Tuần 4 thiết lập hệ thống hạ tầng mạng Amazon VPC cơ bản, phân chia Public Subnet, Private Subnet và cấu hình định tuyến Internet.

##  Self Assessment
- Productivity: 9/10
- Learning: 8.5/10
- Collaboration: 7/10