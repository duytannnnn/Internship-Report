+++
title = "Week 9 Worklog "
date = 2026-06-08
weight = 9
chapter = false
pre = " <b> 1.9. </b> "
+++

##  Thông tin cơ bản
- **Họ và tên**: Trương Lê Duy Tân
- **MSSV**: 2280602878
- **Lớp**: 22DTHH1
- **Ngành**: Công nghệ thông tin
- **Đơn vị thực tập**: AWS Cloud Training
- **Vị trí thực tập**: Thực tập sinh AWS Cloud
- **Ngày bắt đầu tuần**: 08/06/2026
- **Tuần thực tập**: Tuần thứ 9/12

##  Mục tiêu tuần này
- Tiếp tục hoàn thành lộ trình đào tạo, theo dõi đến video số 257 của playlist đào tạo AWS.
- Tập trung chuyên sâu vào các dịch vụ bảo mật, quản lý danh tính, triển khai ứng dụng serverless nâng cao.
- Tham dự cuộc thi tìm hiểu kiến thức dịch vụ AWS dành cho học viên và thực tập sinh để củng cố năng lực phân tích kiến trúc thực tế.

##  Công việc đã thực hiện

### 1. Thực hành cấu hình Bảo mật nâng cao và Quản lý danh tính
- **Mô tả**: Học lý thuyết và thực hành cơ chế xác thực, phân quyền chuyên sâu với IAM Policy, IAM Role và Trust Policy (Chính sách ủy thác). Thực hiện áp dụng các ràng buộc điều kiện (Condition) trong IAM Policy như giới hạn dải địa chỉ IP truy cập (IP Address), truy cập theo thời gian (Time-based Access) và bắt buộc xác thực đa yếu tố (MFA).
- **Kết quả**: Thành thạo việc tạo, quản lý cấu trúc IAM User, Group, Role và tối ưu hóa việc phân quyền theo nguyên tắc đặc quyền tối thiểu.

### 2. Triển khai kiến trúc Serverless và tích hợp Amazon Cognito
- **Mô tả**: Nghiên cứu và khởi tạo dịch vụ Amazon Cognito (User Pool) để quản lý, xác thực người dùng cho ứng dụng. Tiến hành thiết lập Amazon API Gateway, xây dựng luồng API Serverless kết hợp với AWS Lambda và cấu hình tích hợp Amazon Cognito làm bộ xác thực (Authorizer) bảo mật cho API Gateway.
- **Kết quả**: Triển khai thành công hệ thống API Serverless an toàn. Hệ thống tự động chặn và trả về lỗi xác thực nếu yêu cầu gọi API không đính kèm ID Token hợp lệ từ Cognito.

### 3. Giám sát hệ thống với AWS CloudTrail và CloudWatch
- **Mô tả**: Sử dụng AWS CloudTrail để ghi lại toàn bộ lịch sử thao tác, API call của các tài nguyên và cấu hình Amazon CloudWatch để giám sát trạng thái, đọc log, phát hiện các hành vi bất thường hoặc lỗi phân quyền trong hệ thống.
- **Kết quả**: Kiểm soát toàn diện hoạt động hệ thống, nâng cao năng lực audit và điều tra an ninh bảo mật.

### 4. Tham gia Sự kiện Cuộc thi Kiến thức AWS nội bộ
- **Mô tả**: Tham dự và theo dõi cuộc thi tìm hiểu kiến thức dịch vụ AWS được tổ chức cho các học viên và thực tập sinh (gồm 08 đội thi đấu loại trực tiếp). Lắng nghe và phân tích các câu hỏi tình huống mô phỏng thực tế liên quan đến IAM, EC2, S3, VPC, Lambda, API Gateway, CloudWatch, CloudFormation.
- **Kết quả**: Tiếp thu tư duy giải quyết bài toán thực tế từ ban tổ chức, hiểu rõ hơn mối liên kết phối hợp giữa các dịch vụ độc lập khi xây dựng một hệ thống Cloud hoàn chỉnh và tạo động lực lớn để củng cố các lỗ hổng kiến thức.

##  Kiến thức học được

###  Technical Skills
- **AWS Services**: Amazon Cognito, Amazon API Gateway, AWS Lambda, IAM (Policy, Role, Trust Policy), AWS CloudTrail, Amazon CloudWatch.
- **Security & Operations**: Kỹ năng phân tích log bảo mật, cấu hình cơ chế AssumeRole, thiết lập bộ lọc API Authorizer và xử lý lỗi phân quyền hệ thống.

###  Concepts & Theory
- **New Concepts**: Cơ chế Identity Federation (Liên minh định danh), quy trình mạo nhận quyền an toàn giữa các dịch vụ, và vai trò của quản trị ngữ cảnh bảo mật trong môi trường Serverless.
- **Best Practices**: Luôn ghi log tập trung các thao tác quản trị qua CloudTrail để phục vụ ứng phó sự cố an ninh; áp dụng các điều kiện ngặt nghèo (Condition Policy) để thu hẹp phạm vi tấn công.

##  Khó khăn và giải pháp
- **Vấn đề**: Quá trình cấu hình Trust Policy cho IAM Role liên tục báo lỗi nghiêm trọng `Invalid Principal`; việc tích hợp Cognito với API Gateway dễ xảy ra lỗi xác thực.
- **Root Cause**: Khai báo chưa chính xác định dạng chuỗi mã tài nguyên Amazon Resource Name (ARN) của đối tượng được phép mạo nhận quyền. Thiếu thông tin cấu hình App Client hoặc thiếu quyền hạn gán chéo giữa API Gateway và Cognito.
- **Solution**: Đọc log chi tiết trên CloudWatch, tra cứu tài liệu hướng dẫn chính thức của AWS (AWS Documentation), chỉnh sửa lại chính xác định dạng ARN và bổ sung đầy đủ các bước xác thực App Client để hoàn thành bài lab.

##  Reflection & Insights
- Bảo mật và giám sát hệ thống là kim chỉ nam cho mọi kiến trúc Cloud thành công. Thông qua việc làm lab và theo dõi cuộc thi kiến thức, em nhận thấy một hệ thống tối ưu không chỉ là chạy được tính năng, mà phải được bảo vệ đa lớp từ hạ tầng mạng cho đến tầng định danh người dùng.

##  Kế hoạch tuần tiếp theo
- Hoàn thành toàn bộ các video còn lại của playlist đào tạo AWS.
- Thực hiện rà soát, kiểm tra toàn bộ hệ thống hóa đơn chi phí (AWS Billing) và tiến hành dọn dẹp (Clean up) toàn bộ các tài nguyên Lab tạm thời để tránh phát sinh chi phí ẩn ngoài ý muốn.
- Tổng kết kiến thức của giai đoạn 1 và chuẩn bị chuyển giao sang giai đoạn xây dựng đồ án tốt nghiệp cuối khóa.

##  Self Assessment
- Productivity: 9/10
- Learning: 9.5/10
- Collaboration: 8/10