+++
title = "Week 1 Worklog "
date = 2026-04-13
weight = 1
chapter = false
pre = " <b> 1.1. </b> "
+++

##  Thông tin cơ bản
- **Họ và tên**: Trương Lê Duy Tân
- **MSSV**: 2280602878
- **Lớp**: 22DTHH1
- **Ngành**: Công nghệ thông tin
- **Đơn vị thực tập**: AWS Cloud Training
- **Vị trí thực tập**: Thực tập sinh AWS Cloud
- **Ngày bắt đầu tuần**: 13/04/2026
- **Tuần thực tập**: Tuần thứ 1/12

##  Mục tiêu tuần này
- Làm quen với môi trường làm việc, văn hóa doanh nghiệp và quy trình báo cáo tại đơn vị thực tập.
- Nhận tài khoản đào tạo, cài đặt các công cụ cần thiết (AWS CLI, Git, VS Code) và kích hoạt bảo mật tài khoản.
- Bắt đầu lộ trình nghiên cứu các video bài giảng cơ bản từ playlist đào tạo AWS được khoa giới thiệu (Tập trung vào Tổng quan Điện toán đám mây và dịch vụ IAM).

##  Công việc đã thực hiện

### 1. Hội nhập môi trường thực tập và Thiết lập công cụ
- **Mô tả**: Tham gia buổi định hướng thực tập sinh, nắm rõ nội quy và lộ trình học tập Lab trong 10 tuần. Khởi tạo môi trường làm việc cá nhân, cài đặt thành công công cụ dòng lệnh AWS CLI, Git để quản lý mã nguồn và VS Code phục vụ biên tập cấu hình.
- **Kết quả**: Hoàn thành cấu hình môi trường, kiểm tra kết nối AWS CLI với AWS Account thông qua Access Key kiểm thử thành công.

### 2. Nghiên cứu lý thuyết Tổng quan Cloud Computing và Dịch vụ IAM
- **Mô tả**: Xem các video bài giảng đầu tiên trong playlist đào tạo. Học về khái niệm Điện toán đám mây, các mô hình dịch vụ (IaaS, PaaS, SaaS) và mô hình triển khai (Public, Private, Hybrid). Đi sâu nghiên cứu dịch vụ quản lý danh tính và truy cập AWS Identity and Access Management (IAM).
- **Kết quả**: Hiểu rõ nguyên lý phân quyền, cơ chế hoạt động của Root Account và lý do tại sao không nên sử dụng Root Account cho các tác vụ cấu hình hàng ngày.

### 3. Lab cấu hình Bảo mật Tài khoản và Phân quyền IAM
- **Mô tả**: Truy cập AWS Console bằng tài khoản được cấp. Thiết lập kích hoạt tính năng Xác thực đa yếu tố (MFA) cho tài khoản để tăng cường bảo mật. Thực hành khởi tạo các IAM User, phân chia vào các IAM Group chuyên trách (nhũ nhóm Administrator, nhóm Developer) và gắn các IAM Managed Policy tương ứng nhằm tuân thủ nguyên tắc "Đặc quyền tối thiểu".
- **Kết quả**: Tài khoản được bảo mật an toàn qua MFA, các IAM User đăng nhập và thao tác đúng phạm vi quyền hạn được cấp.
- **Tools/Tech**: AWS IAM, Authenticator App, AWS Console.

##  Kiến thức học được

###  Technical Skills
- **AWS Services**: AWS IAM (Users, Groups, Policies, Roles), MFA Activation.
- **Tools**: Sử dụng thành thạo AWS Management Console và cấu hình AWS CLI cơ bản.

###  Concepts & Theory
- **New Concepts**: Mô hình trách nhiệm chia sẻ (Shared Responsibility Model) giữa AWS và khách hàng. Sự khác biệt cốt lõi giữa Authentication (Xác thực danh tính) và Authorization (Phân quyền thao tác) trong an toàn thông tin đám mây.

##  Khó khăn và giải pháp
- **Vấn đề**: Gặp lỗi không thể thực hiện các lệnh kiểm tra tài nguyên qua AWS CLI sau khi cài đặt.
- **Root Cause**: Nhập sai định dạng vùng tài nguyên mặc định (Default Region Name) và gõ nhầm ký tự trong chuỗi Secret Access Key khi chạy lệnh `aws configure`.
- **Solution**: 主 động tra cứu tài liệu hướng dẫn AWS, thực hiện chạy lại lệnh `aws configure` để cập nhật chính xác cặp Key bảo mật mới và chọn đúng Region (`ap-southeast-1`).

##  Reflection & Insights
- Tuần đầu tiên giúp em thay đổi hoàn toàn tư duy về hạ tầng. Việc bảo mật tài khoản ngay từ những bước đi đầu tiên trên môi trường Cloud là cực kỳ quan trọng để bảo vệ tài nguyên doanh nghiệp trước các nguy cơ tấn công mạng.

## Kế hoạch tuần tiếp theo
- Chuyển sang Tuần 2 nghiên cứu và thực hành dịch vụ tính toán cốt lõi Amazon EC2 (Elastic Compute Cloud), cách khởi chạy máy ảo, cấu hình tường lửa Security Group và quản lý cặp khóa Key Pair.

##  Self Assessment
- Productivity: 8.5/10
- Learning: 8.5/10
- Collaboration: 7/10