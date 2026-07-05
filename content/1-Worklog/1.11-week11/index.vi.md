+++
title = "Nhật ký Tuần 11 "
date = 2026-06-22
weight = 11
chapter = false
pre = " <b> 1.11. </b> "
+++

##  Thông tin cơ bản
- **Họ và tên**: Trương Lê Duy Tân
- **Mã số sinh viên**: 2280602878
- **Lớp**: 22DTHH1
- **Chuyên ngành**: Công nghệ thông tin
- **Đơn vị thực tập**: AWS Cloud Training
- **Vị trí thực tập**: AWS Cloud Intern
- **Ngày bắt đầu tuần**: 22/06/2026
- **Tuần thực tập**: Tuần 11/12

##  Mục tiêu trong tuần
- Chuyển giao chính thức từ giai đoạn thực hành Lab độc lập sang giai đoạn xây dựng đồ án tốt nghiệp cuối khóa.
- Thu thập yêu cầu nghiệp vụ và yêu cầu chức năng để phác thảo bản Đề xuất Đồ án (Project Proposal).
- Thiết kế mô hình kiến trúc đám mây đa tầng, bảo mật và có tính sẵn sàng cao trên AWS.
- Trình bày và bảo vệ thành công bản đề xuất kỹ thuật trước hội đồng đánh giá của doanh nghiệp.

##  Công việc đã thực hiện

### 1. Phân tích yêu cầu bài toán và lựa chọn giải pháp công nghệ
- **Mô tả**: Tiến hành phân tích đề tài đồ án tốt nghiệp được giao. Đánh giá lưu lượng truy cập dự kiến, đặc thù tải công việc (workload) và các quy chuẩn bảo mật bắt buộc của hệ thống để lựa chọn các dịch vụ AWS tối ưu nhất.
- **Kết quả**: Xác định được ngăn xếp công nghệ (tech stack) nâng cao, phân tách rõ ràng hệ thống thành tầng hiển thị (S3 + CloudFront CDN), tầng xử lý ứng dụng (Amazon ECS Fargate) và tầng lưu trữ dữ liệu an toàn (Amazon RDS).

### 2. Thiết kế kiến trúc hệ thống tổng thể (System Architecture Blueprint)
- **Mô tả**: Thiết kế mô hình hạ tầng có tính sẵn sàng cao (High Availability) trên nhiều vùng khả dụng (Multi-AZ). Thiết lập sơ đồ mạng ảo bao gồm ranh giới VPC tùy chỉnh, phân chia các Public/Private Subnet, phân bổ các bộ cân bằng tải (ALB), cấu hình Auto Scaling và thiết lập quy tắc ràng buộc chéo cho các Security Group.
- **Kết quả**: Hoàn thành Sơ đồ Kiến trúc Hệ thống 3 lớp (3-Tier Architecture) hoàn chỉnh sử dụng bộ icon chuẩn của AWS, thể hiện rõ ràng luồng dữ liệu luân chuyển và các giao thức kết nối.

### 3. Hoàn thiện và bảo vệ Đề xuất Đồ án (Project Proposal) trước Hội đồng
- **Mô tả**: Tài liệu hóa phương án kỹ thuật, tính toán chi phí vận hành ước tính thông qua công cụ AWS Pricing Calculator, xây dựng lộ trình triển khai chi tiết và các phương án quản trị rủi ro. Thực hiện thuyết trình slide kiến trúc trước các Mentor hướng dẫn và hội đồng doanh nghiệp.
- **Kết quả**: Bảo vệ thành công bản Đề xuất Đồ án (Project Proposal), ghi nhận các đóng góp chuyên môn từ hội đồng và được phê duyệt chính thức để tiến hành giai đoạn triển khai thực tế.
- **Công cụ/Công nghệ sử dụng**: AWS Architecture Icons, AWS Pricing Calculator, Draw.io, Phần mềm thuyết trình.

##  Kiến thức tiếp thu được

###  Kỹ năng kỹ thuật
- **Kiến trúc Cloud**: Thành thạo kỹ năng thiết kế hạ tầng Multi-AZ, dự toán và tối ưu hóa ngân sách vận hành hệ thống đám mây, bóc tách yêu cầu nghiệp vụ sang giải pháp kỹ thuật.
- **Quản trị hệ thống**: Biết cách gắn kết các tính năng kỹ thuật trực tiếp với các chỉ số cam kết chất lượng dịch vụ (SLA) và tính liên tục của doanh nghiệp.

###  Khái niệm & Lý thuyết
- **Khái niệm mới**: Hiểu sâu về cấu trúc thiết kế của các hệ thống phần mềm lớn trong doanh nghiệp (Enterprise Architecture Patterns) và quy trình chuyển dịch từ môi trường thử nghiệm sang vận hành thực tế (SDLC).

##  Khó khăn & Giải pháp xử lý
- **Vấn đề**: Bản dự toán chi phí ban đầu cho kiến trúc hạ tầng vượt quá mức ngân sách giả định mà doanh nghiệp cấp cho dự án.
- **Nguyên nhân**: Cấu hình dư thừa tài nguyên (Over-provisioning) khi lựa chọn các dòng database quá lớn (Amazon RDS Multi-AZ ghi đồng thời) và phân bổ CPU/RAM quá cao cho các container AWS Fargate ngay từ giai đoạn khởi tạo.
- **Giải pháp**: Tối ưu lại sơ đồ kiến trúc bằng cách áp dụng các mô hình tiết kiệm chi phí; thay thế các tài nguyên chạy idle cố định bằng cơ chế co giãn tự động của AWS Fargate, và chuyển Amazon RDS sang Single-AZ kết hợp chiến lược sao lưu snapshot tự động cho môi trường phát triển.

##  Trải nghiệm & Trực giác cá nhân
- Việc chuyển từ các bài Lab tuần lẻ tẻ sang tự tay lên kế hoạch cho một dự án tổng thể đòi hỏi một góc nhìn rộng hơn rất nhiều. Một kiến trúc tốt không chỉ cần chạy được, mà phải là sự cân bằng hoàn hảo giữa tính bảo mật, hiệu năng hệ thống và bài toán kinh tế của doanh nghiệp.

##  Kế hoạch tuần tiếp theo
- Tham gia đầy đủ chuỗi chuyên đề công nghệ nâng cao và các buổi Workshop tổng kết.
- Hoàn thiện báo cáo thực tập tổng hợp, chuẩn bị hồ sơ nghiệm thu kỹ thuật cuối khóa.

##  Tự đánh giá
- Năng suất (Productivity): 9.5/10
- Khả năng học hỏi (Learning): 9/10
- Khả năng phối hợp (Collaboration): 8.5/10