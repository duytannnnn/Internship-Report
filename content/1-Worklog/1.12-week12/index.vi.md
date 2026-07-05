+++
title = "Nhật ký Tuần 12 "
date = 2026-06-29
weight = 12
chapter = false
pre = " <b> 1.12. </b> "
+++

## 📑 Thông tin cơ bản
- **Họ và tên**: Trương Lê Duy Tân
- **Mã số sinh viên**: 2280602878
- **Lớp**: 22DTHH1
- **Chuyên ngành**: Công nghệ thông tin
- **Đơn vị thực tập**: AWS Cloud Training
- **Vị trí thực tập**: AWS Cloud Intern
- **Ngày bắt đầu tuần**: 29/06/2026
- **Tuần thực tập**: Tuần 12/12 (Tuần cuối cùng)

## 🎯 Mục tiêu trong tuần
- Tham gia chuỗi chuyên đề công nghệ (Workshop) nâng cao do các chuyên gia điện toán đám mây chia sẻ.
- Tổng hợp toàn bộ các kết quả kỹ thuật, nhật ký kiến trúc và tài liệu Lab đã tích lũy trong suốt 3 tháng qua.
- Hoàn thiện báo cáo thực tập tốt nghiệp cuối kỳ để chuẩn bị nghiệm thu và chấm điểm.
- Tiến hành họp tổng kết, nhận đánh giá phản hồi và hoàn tất chương trình thực tập tại doanh nghiệp.

## 🛠️ Công việc đã thực hiện

### 1. Tham gia chuỗi Chuyên đề Công nghệ (Workshop) nâng cao
- **Mô tả**: Tham gia tích cực vào các buổi thảo luận chuyên sâu (Workshop). Nghiên cứu các chủ đề thực tế về bảo mật nâng cao (quản lý ranh giới quyền hạn IAM nâng cao, tự động xoay vòng mã khóa qua AWS Secrets Manager), chiến lược tối ưu chi phí FinOps chuyên sâu, và quản lý hạ tầng bằng mã (IaC) với AWS CloudFormation.
- **Kết quả**: Thu hoạch được nhiều kinh nghiệm thực chiến quý báu, giúp thu hẹp khoảng cách giữa kiến thức học thuật và tiêu chuẩn vận hành thực tế tại các doanh nghiệp lớn.

### 2. Tổng hợp Nhật ký công việc và Hoàn thiện Báo cáo cuối khóa
- **Mô tả**: Kiểm tra, rà soát lại toàn bộ hệ thống thư mục 12 tuần làm việc trên kho lưu trữ Markdown. Hệ thống hóa các kinh nghiệm xử lý sự cố, giải pháp kiến trúc và viết báo cáo thực tập tổng kết chi tiết mô tả đầy đủ quá trình trưởng thành và các cột mốc đã đạt được.
- **Kết quả**: Đóng gói thành công trang tài liệu kỹ thuật Worklog đa ngôn ngữ hoàn chỉnh, chuyên nghiệp, đáp ứng đầy đủ các tiêu chí kiểm tra và đánh giá học thuật của nhà trường.

### 3. Nghiệm thu bàn giao tài nguyên và Họp tổng kết thực tập
- **Mô tả**: Hoàn tất các thủ tục hành chính, dọn dẹp và giải phóng hoàn toàn các tài nguyên thử nghiệm phụ trợ trên tài khoản AWS để tránh phát sinh chi phí ngoài ý muốn. Gửi hồ sơ kết quả cho các Mentor và tham gia buổi họp tổng kết đánh giá năng lực cuối kỳ.
- **Kết quả**: Kết thúc thành công chương trình thực tập kéo dài 3 tháng với đầy đủ chữ ký xác nhận, chứng nhận từ phía doanh nghiệp và nhận được những phản hồi rất tích cực cho định hướng nghề nghiệp tương lai.
- **Công cụ/Công nghệ sử dụng**: Hugo Markdown Repo, AWS Console, Git Control Systems, Tài liệu hướng dẫn hệ thống.

## 📖 Kiến thức tiếp thu được

### 🔧 Kỹ năng kỹ thuật
- **Kỹ sư Cloud**: Kỹ năng kiểm toán cấu hình hệ thống nâng cao, cơ chế tự động hóa bảo mật thông tin, chuẩn hóa và tối ưu cấu trúc hiển thị trang tài liệu công nghệ, kỹ năng viết báo cáo kỹ thuật chuyên sâu.
- **Kỹ năng chuyên nghiệp**: Tư duy giao tiếp trong môi trường doanh nghiệp, kỹ năng bàn giao sản phẩm công nghệ và chuyển hóa các ý kiến phản hồi thành cải tiến kiến trúc cụ thể.

### 💡 Khái niệm & Lý thuyết
- **Khái niệm mới**: Tiếp cận tư duy DevSecOps (tích hợp bảo mật tự động vào mọi lớp của hạ tầng), quy trình bàn giao phần mềm chuẩn công nghiệp và các tiêu chí đánh giá hiệu năng nhân sự (KPIs).

## ⚠️ Khó khăn & Giải pháp xử lý
- **Vấn đề**: Khi rà soát lại cấu trúc tài liệu đa ngôn ngữ trên hệ thống Hugo, phát hiện một số liên kết nội bộ giữa bản tiếng Anh (`.en.md`) và bản tiếng Việt (`.vi.md`) bị lỗi hiển thị trang 404 hoặc dẫn sai thư mục.
- **Nguyên nhân**: Do sự không đồng nhất về cách đặt tên đường dẫn tương đối (relative paths) và cấu trúc phân cấp giữa hai thư mục ngôn ngữ trong quá trình cập nhật nội dung hàng tuần.
- **Giải pháp**: Sử dụng các đoạn mã lệnh kiểm tra thư mục trong terminal để quét toàn bộ cây thư mục, đồng bộ hóa lại toàn bộ các tham chiếu URL và tiến hành biên dịch (build) thử nghiệm trên môi trường local để đảm bảo hệ thống chuyển đổi ngôn ngữ mượt mà không lỗi.

## 💭 Trải nghiệm & Trực giác cá nhân
- Hành trình 12 tuần thực tập vừa qua là một trải nghiệm vô giá đối với em. Chương trình không chỉ giúp em củng cố vững chắc chuyên môn về Điện toán đám mây (từ tính toán, mạng, lưu trữ đến bảo mật), mà còn rèn luyện cho em tư duy giải quyết vấn đề độc lập và khả năng thích ứng nhanh trước các sự cố hệ thống. Em cảm thấy hoàn toàn tự tin để bước tiếp vào các vị trí kỹ sư Cloud chuyên nghiệp.

## 📅 Kế hoạch tuần tiếp theo
- Nộp toàn bộ hồ sơ báo cáo thực tập có đầy đủ xác nhận của doanh nghiệp về văn phòng Khoa tại Trường.
- Tập trung chuẩn bị cho buổi bảo vệ Đồ án tốt nghiệp sắp tới trước Hội đồng học thuật.

## 📊 Tự đánh giá
- Năng suất (Productivity): 9.5/10
- Khả năng học hỏi (Learning): 9.5/10
- Khả năng phối hợp (Collaboration): 9/10