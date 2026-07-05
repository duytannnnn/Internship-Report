+++
title = "Week 2 Worklog "
date = 2026-04-20
weight = 2
chapter = false
pre = " <b> 1.2. </b> "
+++

##  Thông tin cơ bản
- **Họ và tên**: Trương Lê Duy Tân
- **MSSV**: 2280602878
- **Lớp**: 22DTHH1
- **Ngành**: Công nghệ thông tin
- **Đơn vị thực tập**: AWS Cloud Training
- **Vị trí thực tập**: Thực tập sinh AWS Cloud
- **Ngày bắt đầu tuần**: 20/04/2026
- **Tuần thực tập**: Tuần thứ 2/12

##  Mục tiêu tuần này
- Học lý thuyết và xem các video từ số 11 đến 20 trong playlist đào tạo AWS.
- Tìm hiểu dịch vụ tính toán cốt lõi Amazon EC2 (Elastic Compute Cloud).
- Thực hành khởi chạy máy ảo, cấu hình tường lửa Security Group và quản lý cặp khóa Key Pair.

##  Công việc đã thực hiện

### 1. Nghiên cứu dịch vụ tính toán Amazon EC2
- **Mô tả**: Học về các thành phần cấu thành một máy ảo trên mây bao gồm: Các thế hệ Instance Type (t2.micro, t3.micro), hệ điều hành (AMI), ổ đĩa lưu trữ ảo (EBS Volume) và cơ chế mã hóa bảo mật đường truyền.

### 2. Thực hành Khởi tạo và Kết nối Máy chủ EC2 Linux
- **Mô tả**: 
  - Tạo mới một Key Pair để phục vụ xác thực an toàn.
  - Khởi chạy một Instance EC2 sử dụng hệ điều hành Ubuntu Server thuộc gói Free Tier.
  - Sử dụng phần mềm Terminal (hoặc Git Bash) trên máy cá nhân để thực hiện lệnh SSH kết nối từ xa vào máy chủ thông qua Public IP bằng Key Pair.
- **Kết quả**: Kết nối thành công, có thể toàn quyền tương tác và quản trị máy chủ thông qua giao diện dòng lệnh.

### 3. Cấu hình Tường lửa Security Group
- **Mô tả**: Thiết lập các quy tắc kiểm soát lưu lượng mạng vào/ra (Inbound/Outbound Rules). Mở port 22 cho traffic SSH và port 80 cho traffic HTTP để chuẩn bị chạy ứng dụng web.
- **Kết quả**: Bảo vệ máy chủ EC2 an toàn, chặn các truy cập trái phép ở các cổng không được phân quyền.
- **Tools/Tech**: Amazon EC2, Ubuntu, SSH, Security Group.

##  Kiến thức học được

###  Technical Skills
- **AWS Services**: Amazon EC2, Key Pair, Security Group, AMI.
- **Linux Tools**: Các lệnh quản trị Linux cơ bản, phân quyền file `chmod 400` cho private key.

###  Concepts & Theory
- **New Concepts**: Bản chất của tường lửa trạng thái (Stateful Firewall) đối với Security Group (tự động cho phép traffic phản hồi đi ra nếu traffic đi vào hợp lệ).

##  Khó khăn và giải pháp
- **Vấn đề**: Thực hiện lệnh SSH vào EC2 Ubuntu liên tục gặp lỗi "Permission denied (publickey)" hoặc "Bad permissions".
- **Root Cause**: File private key `.pem` vừa tải xuống máy cá nhân có quyền truy cập quá rộng rãi, hệ điều hành Linux/macOS yêu cầu file key phải được cô lập quyền đọc.
- **Solution**: Chạy lệnh `chmod 400 <ten_file_key>.pem` để thu hẹp quyền truy cập chỉ dành riêng cho chủ sở hữu máy tính, sau đó thực hiện lại lệnh SSH thành công.

##  Reflection & Insights
- Việc có thể sở hữu một máy chủ cấu hình mạnh mẽ chỉ trong vòng chưa đầy 2 phút thay vì phải đi mua linh kiện phần cứng vật lý giúp tiết kiệm tối đa thời gian triển khai sản phẩm, thể hiện rõ nét sức mạnh linh hoạt của hạ tầng đám mây.

##  Kế hoạch tuần tiếp theo
- Chuyển sang Tuần 3 nghiên cứu về dịch vụ lưu trữ đối tượng toàn cầu Amazon S3, thực hành quản lý vòng đời đối tượng và cấu hình S3 Static Website Hosting.

##  Self Assessment
- Productivity: 9/10
- Learning: 8.5/10
- Collaboration: 7/10