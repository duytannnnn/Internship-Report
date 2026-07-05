+++
title = "Week 4 Worklog "
date = 2026-05-04
weight = 4
chapter = false
pre = " <b> 1.4. </b> "
+++

##  Thông tin cơ bản
- **Họ và tên**: Trương Lê Duy Tân
- **MSSV**: 2280602878
- **Lớp**: 22DTHH1
- **Ngành**: Công nghệ thông tin
- **Đơn vị thực tập**: AWS Cloud Training
- **Vị trí thực tập**: Thực tập sinh AWS Cloud
- **Ngày bắt đầu tuần**: 04/05/2026
- **Tuần thực tập**: Tuần thứ 4/12

##  Mục tiêu tuần này
- Hoàn thành đến video số 65 của playlist đào tạo AWS.
- Thiết lập hệ thống hạ tầng mạng Amazon VPC cơ bản.
- Phân chia Public Subnet, Private Subnet và cấu hình định tuyến Internet.

##  Công việc đã thực hiện

### 1. Thiết lập Amazon VPC và cấu trúc Subnet
- **Mô tả**: Khởi tạo một mạng ảo cô lập Custom VPC với dải địa chỉ mạng CIDR block `10.0.0.0/16`. Tiến hành phân chia mạng thành Public Subnet (`10.0.1.0/24`) và Private Subnet (`10.0.2.0/24`) nhằm mục đích phân tách các vùng tài nguyên public và bảo mật nội bộ.
- **Kết quả**: Tạo lập thành công hệ thống subnet ảo trên hạ tầng Cloud. Kích hoạt tính năng tự động cấp phát IP công khai cho các tài nguyên khi khởi chạy trong vùng Public Subnet.
- **Tools/Tech**: AWS VPC Console.

### 2. Cấu hình Cổng Internet Gateway và NAT Gateway
- **Mô tả**: Khởi tạo Internet Gateway (IGW) và liên kết với VPC để cấp đường ra Internet cho Public Subnet. Xin cấp phát một địa chỉ IP tĩnh Elastic IP, sau đó thiết lập một dịch vụ NAT Gateway đặt tại Public Subnet. Chỉnh sửa bảng định tuyến Route Table của Private Subnet hướng traffic `0.0.0.0/0` đi qua NAT Gateway.
- **Kết quả**: Máy ảo EC2 trong Private Subnet có thể kết nối ra Internet để cập nhật package nhưng bên ngoài không thể truy cập trực tiếp vào, đảm bảo an toàn thông tin hệ thống.
- **Tools/Tech**: Internet Gateway, NAT Gateway, Elastic IP, Route Table.

##  Kiến thức học được

###  Technical Skills
- **AWS Services**: Amazon VPC, Route Table, Internet Gateway, NAT Gateway, Elastic IP.
- **Networking**: Kỹ năng chia mạng con (Subnetting) và điều hướng luồng traffic mạng (Routing).

###  Concepts & Theory
- **New Concepts**: Nguyên lý hoạt động và vai trò của mô hình mạng hai tầng (Public và Private) trong kiến trúc đám mây an toàn.
- **Best Practices**: NAT Gateway luôn luôn phải được đặt ở Public Subnet để giao tiếp ra bên ngoài và phải giải phóng Elastic IP khi xóa NAT Gateway để tránh phát sinh chi phí ngoài Free Tier.

##  Khó khăn và giải pháp
- **Vấn đề**: Instance EC2 đặt trong Private Subnet hoàn toàn mất kết nối ra Internet và không thể tải phần mềm bổ sung.
- **Root Cause**: Gán sai vị trí của NAT Gateway vào bên trong vùng Private Subnet khiến NAT Gateway cũng bị cô lập mạng.
- **Solution**: Xóa NAT Gateway cấu hình sai, thực hiện tạo lại và chọn chính xác vị trí đặt chân tại Public Subnet, cập nhật lại Route Table tương ứng.

##  Reflection & Insights
- Kiến thức mạng đóng vai trò nền tảng. Khi làm việc trên Cloud, cấu hình sai một tham số trong Route Table có thể làm tê liệt toàn bộ hệ thống hoặc gây mất an toàn an ninh mạng.

##  Kế hoạch tuần tiếp theo
- Chuyển sang Tuần 5 nghiên cứu về các giải pháp lưu trữ nâng cao của AWS và phương thức kết nối lưu trữ Hybrid (AWS Storage Gateway).

##  Self Assessment
- Productivity: 9/10
- Learning: 9/10
- Collaboration: 6/10