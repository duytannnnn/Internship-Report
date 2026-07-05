+++
title = "Week 7 Worklog "
date = 2026-05-25
weight = 7
chapter = false
pre = " <b> 1.7. </b> "
+++

##  Thông tin cơ bản
- **Họ và tên**: Trương Lê Duy Tân
- **MSSV**: 2280602878
- **Lớp**: 22DTHH1
- **Ngành**: Công nghệ thông tin
- **Đơn vị thực tập**: AWS Cloud Training
- **Vị trí thực tập**: Thực tập sinh AWS Cloud
- **Ngày bắt đầu tuần**: 25/05/2026
- **Tuần thực tập**: Tuần thứ 7/12

##  Mục tiêu tuần này
- Tiếp tục tăng tốc lộ trình học tập, hoàn thành đến video số 210 của playlist đào tạo AWS được giới thiệu.
- Làm chủ kiến trúc High Availability (HA) và Fault Tolerance với Application Load Balancer (ALB) và Auto Scaling Group (ASG).
- Thực hành công nghệ Container hóa ứng dụng với Docker và tìm hiểu giải pháp vận hành container (ECS, Fargate).
- Nghiên cứu nguyên lý xây dựng hệ thống tích hợp và triển khai tự động CI/CD trên AWS.

##  Công việc đã thực hiện

### 1. Triển khai Cấu trúc High Availability (HA) và Khả năng chịu lỗi
- **Mô tả**: Nghiên cứu lý thuyết nâng cao về tính sẵn sàng cao và khả năng chống chịu lỗi của hệ thống hạ tầng Cloud. Tiến hành cấu hình thực tế bộ cân bằng tải Application Load Balancer (ALB) và Network Load Balancer (NLB) để phân phối lưu lượng mạng đến các nhóm máy chủ đích (Target Group). Thiết lập một Auto Scaling Group (ASG) kết hợp Launch Template để tự động tăng/giảm số lượng máy chủ EC2 dựa trên các chỉ số tải CPU thực tế.
- **Kết quả**: Xây dựng thành công hệ thống hạ tầng web có khả năng tự động co giãn linh hoạt và tự chữa lành khi có server gặp sự cố.

### 2. Thực hành Công nghệ Container (Docker) và Dịch vụ Container AWS
- **Mô tả**: Học kiến thức cơ bản và nâng cao về Docker. Thực hành viết Dockerfile để đóng gói một ứng dụng web thành Docker Image, quản lý và chạy Docker Container trên môi trường local. Tìm hiểu các giải pháp quản lý, điều phối container quy mô lớn của AWS bao gồm Amazon ECS (Elastic Container Service) và AWS Fargate (mô hình serverless dành cho container).
- **Kết quả**: Làm chủ chu trình đóng gói ứng dụng bằng container, tối ưu hóa các layer của image giúp hệ thống vận hành gọn nhẹ hơn.

### 3. Nghiên cứu Luồng Tích hợp và Triển khai Tự động CI/CD
- **Mô tả**: Tìm hiểu nguyên lý xây dựng pipeline tự động hóa quy trình phân phối phần mềm liên tục. Tiếp cận các bộ công cụ phát triển chuyên sâu của AWS bao gồm: AWS CodeCommit (quản lý mã nguồn), AWS CodeBuild (tự động build ứng dụng và đóng gói container), AWS CodeDeploy (triển khai mã nguồn mới) và AWS CodePipeline (điều phối toàn bộ luồng tự động hóa).
- **Kết quả**: Hiểu rõ chu trình CI/CD từ lúc lập trình viên commit code cho đến khi hệ thống tự động build, cập nhật lên dịch vụ container mà không cần can thiệp thủ công.
- **Tools/Tech**: Application Load Balancer, Auto Scaling Group, Docker, Amazon ECS, AWS Fargate, AWS CodePipeline, AWS CodeBuild, Amazon CloudWatch.

##  Kiến thức học được

###  Technical Skills
- **AWS Services**: ALB, NLB, Auto Scaling Group, Launch Template, Amazon ECS, AWS Fargate, AWS CI/CD Developer Tools.
- **DevOps**: Quản lý vòng đời ứng dụng qua Container, viết Dockerfile tối ưu hóa layer, cấu hình luồng pipeline tự động hóa CI/CD và theo dõi log tập trung qua CloudWatch.

###  Concepts & Theory
- **New Concepts**: Mô hình tính toán phi máy chủ dành cho container (AWS Fargate) giúp giảm tải việc quản lý hệ điều hành, kiến trúc hạ tầng tự phục hồi (Self-healing Infrastructure).
- **Best Practices**: Thiết kế phân tách rõ ràng môi trường hạ tầng, đặt các server xử lý logic nghiệp vụ sau Load Balancer trong vùng mạng an toàn Private Subnet, áp dụng CI/CD để kiểm soát hiệu năng và tối ưu chi phí hạ tầng.

##  Khó khăn và giải pháp
- **Vấn đề**: Quá trình viết Dockerfile bị lỗi dung lượng hoặc thiếu thư viện; pipeline CI/CD bị fail ở bước deploy và hệ thống không thể định tuyến lưu lượng vào các tài nguyên mới.
- **Root Cause**: Quản lý các layer của Docker Image ban đầu chưa tối ưu. Kiến trúc kết nối giữa Load Balancer, Target Group và ASG tương đối phức tạp, cấu hình sai ở bước gắn thẻ mạng (Subnet) khiến traffic không định tuyến được vào EC2/Container bên trong Private Subnet.
- **Solution**: Chủ động đọc kỹ tài liệu AWS trắng (AWS Whitepapers), xem lại chi tiết các phần thực hành trong playlist video, kiểm tra log lỗi tập trung qua CloudWatch để bổ sung Inbound rule cho phép traffic từ ALB đi vào Container, sửa đổi thành công các bài lab.

##  Reflection & Insights
- Tự động hóa và Container hóa giải phóng rất nhiều sức lao động của kỹ sư hạ tầng. Việc phối hợp nhuần nhuyễn giữa Docker và CI/CD giúp tốc độ phân phối tính năng của sản phẩm phần mềm tăng lên vượt bậc, giảm thiểu sai sót do con người và đảm bảo tính đồng nhất giữa các môi trường phát triển.

##  Kế hoạch tuần tiếp theo
- Nỗ lực hoàn thành những nội dung cuối cùng của playlist đào tạo AWS.
- Nghiên cứu cơ sở dữ liệu trên Cloud (Amazon RDS và Amazon DynamoDB).
- Học về kiến trúc Serverless nâng cao với AWS Lambda và Amazon API Gateway.
- Tổng hợp kiến thức để phác thảo sơ đồ kiến trúc cho Mini Project ứng dụng 3 tầng (3-Tier Architecture) hoàn chỉnh.

##  Self Assessment
- Productivity: 9/10
- Learning: 9/10
- Collaboration: 7/10