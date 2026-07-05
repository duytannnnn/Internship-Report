+++
title = "Week 10 Worklog "
date = 2026-06-15
weight = 10
chapter = false
pre = " <b> 1.10. </b> "
+++

##  Thông tin cơ bản
- **Họ và tên**: Trương Lê Duy Tân
- **MSSV**: 2280602878
- **Lớp**: 22DTHH1
- **Ngành**: Công nghệ thông tin
- **Đơn vị thực tập**: AWS Cloud Training
- **Vị trí thực tập**: Thực tập sinh AWS Cloud
- **Ngày bắt đầu tuần**: 15/06/2026
- **Tuần thực tập**: Tuần thứ 10/12 

##  Mục tiêu tuần này
- Hoàn thành toàn bộ các video bài giảng còn lại của chuỗi playlist đào tạo AWS.
- Thực hiện rà soát, kiểm tra toàn diện hệ thống hóa đơn chi phí (AWS Billing & Cost Management) của tài khoản Free Tier.
- Tiến hành dọn dẹp (Clean up) toàn bộ các tài nguyên Lab tạm thời để đưa mức chi phí dự kiến về an toàn, tránh phát sinh chi phí ngoài ý muốn.
- Tổng kết kiến thức của toàn bộ giai đoạn 1 (10 tuần Lab) và chuẩn bị bàn giao tài liệu phục vụ giai đoạn làm đồ án thực tập tốt nghiệp.

##  Công việc đã thực hiện

### 1. Hoàn thành Lộ trình Bài giảng và Nghiên cứu AWS Well-Architected Framework
- **Mô tả**: Xem các tập video cuối cùng trong playlist đào tạo, tổng kết các kiến thức cốt lõi. Đi sâu nghiên cứu về Khung kiến trúc chuẩn mực (AWS Well-Architected Framework) để hiểu cách đánh giá một hệ thống đám mây đạt tiêu chuẩn vận hành của doanh nghiệp lớn.
- **Kết quả**: Hoàn thành 100% lộ trình bài giảng lý thuyết. Nắm chắc 5 trụ cột cốt lõi của Well-Architected bao gồm: Bảo mật (Security), Hiệu năng (Performance Efficiency), Độ tin cậy (Reliability), Tối ưu chi phí (Cost Optimization) và Vận hành xuất sắc (Operational Excellence).

### 2. Kiểm tra Hệ thống Hóa đơn và Quản trị Tài chính Đám mây
- **Mô tả**: Truy cập vào AWS Billing & Cost Management Dashboard để xem báo cáo chi tiết về lượng tài nguyên tiêu thụ trong suốt quá trình làm Lab. Kiểm tra các dịch vụ sắp chạm hoặc đã vượt ngưỡng giới hạn của tài khoản Free Tier để có phương án xử lý kịp thời.
- **Kết quả**: Làm chủ các công cụ quản lý chi phí như AWS Cost Explorer và AWS Budgets. Thiết lập cảnh báo tự động về email cá nhân ngay khi chi phí tài khoản vượt quá mức quy định.

### 3. Tổng lực Dọn dẹp Tài nguyên Đám mây (Clean-up Resources)
- **Mô tả**: Tiến hành rà soát qua tất cả các khu vực (Regions) đã từng thao tác thực hành Lab trên AWS Console nhằm loại bỏ triệt để nguy cơ bùng nổ hóa đơn ẩn. Các tác vụ cụ thể bao gồm:
  - Tắt và xóa bỏ hoàn toàn (Terminate) các máy chủ EC2 không còn sử dụng.
  - Xóa bỏ các ổ đĩa rời EBS Volume và các bản sao lưu EBS Snapshot cũ.
  - Gỡ bỏ cấu hình Auto Scaling Group, Launch Template và Application Load Balancer (ALB).
  - Dọn sạch dữ liệu (Empty) và xóa bỏ các Amazon S3 Bucket tạm thời.
  - Xóa NAT Gateway và thực hiện giải phóng (Release) toàn bộ các địa chỉ IP tĩnh Elastic IP về lại pool chung của AWS.
- **Kết quả**: Tài khoản AWS được làm sạch hoàn toàn một cách an toàn, đưa mức chi phí dự kiến (Forecasted Cost) về lại mức 0 USD, loại bỏ hoàn toàn các rủi ro phát sinh chi phí ngoài ý muốn.

##  Kiến thức học được

###  Technical Skills
- **AWS Services**: Quản trị tài chính đám mây nâng cao (AWS Billing, Cost Explorer, AWS Budgets).
- **Resource Management**: Kỹ năng quản lý vòng đời tài nguyên, rà soát hệ thống đa vùng (Multi-region) và quy trình giải phóng hạ tầng quy mô lớn trên hệ sinh thái Cloud.

###  Concepts & Theory
- **New Concepts**: Hiểu rõ mô hình 5 trụ cột của AWS Well-Architected Framework để ứng dụng vào việc thiết kế và tối ưu hóa hệ thống thực tế.
- **Best Practices**: Luôn dọn dẹp tài nguyên ngay sau khi hoàn thành bài Lab; sử dụng AWS Budgets làm chốt chặn an toàn cho tài khoản cá nhân và doanh nghiệp.

##  Khó khăn và giải pháp
- **Vấn đề**: Không thể xóa được một số Amazon S3 Bucket mặc dù hệ thống báo đã xóa hết các file hiển thị, hoặc gặp lỗi không thể giải phóng Elastic IP.
- **Root Cause**: Các S3 Bucket này trước đó đã bật tính năng quản lý phiên bản (Bucket Versioning), khiến các phiên bản cũ (Versions) và dấu vết xóa (Delete Markers) vẫn nằm ngầm bên trong. Đối với Elastic IP, do chưa tháo gỡ hoàn toàn NAT Gateway liên kết nên hệ thống khóa quyền giải phóng.
- **Solution**: Truy cập vào S3 bucket, bật nút hiển thị "Show versions" để chọn xóa vĩnh viễn toàn bộ các version ẩn, sau đó thực hiện lệnh xóa Bucket thành công. Chờ NAT Gateway chuyển hẳn sang trạng thái `Deleted` rồi mới tiến hành giải phóng Elastic IP thành công.

##  Reflection & Insights
- Kết thúc 10 tuần học tập và làm Lab liên tục đã mang lại cho em một nền tảng kiến thức thực tế vô cùng vững chắc về hệ sinh thái AWS Cloud. Việc tự tay triển khai và giải quyết lỗi (troubleshoot) giúp em tự tin hơn khi đối mặt với các kiến thức nâng cao. Giai đoạn Lab này là bước đệm tuyệt vời để chuẩn bị bước vào giai đoạn làm đồ án thực tế tiếp theo.

##  Kế hoạch tuần tiếp theo
- Chính thức bước vào Giai đoạn 2: Phối hợp cùng đội ngũ thực tập để lựa chọn đề tài tốt nghiệp, xây dựng bản đề xuất dự án (Project Proposal) và tập trung triển khai đồ án thực tế trên môi trường Cloud AWS.

##  Self Assessment
- Productivity: 9/10
- Learning: 9/10
- Collaboration: 7.5/10