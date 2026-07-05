+++
title = "Week 5 Worklog "
date = 2026-05-11
weight = 5
chapter = false
pre = " <b> 1.5. </b> "
+++

##  Thông tin cơ bản
- **Họ và tên**: Trương Lê Duy Tân
- **MSSV**: 2280602878
- **Lớp**: 22DTHH1
- **Ngành**: Công nghệ thông tin
- **Đơn vị thực tập**: AWS Cloud Training
- **Vị trí thực tập**: Thực tập sinh AWS Cloud
- **Ngày bắt đầu tuần**: 11/05/2026
- **Tuần thực tập**: Tuần thứ 5/12

##  Mục tiêu tuần này
- Tiếp tục tăng tốc để hoàn thành đến video số 107 của playlist đào tạo AWS được khoa giới thiệu.
- Nghiên cứu giải pháp lưu trữ kết hợp với AWS Storage Gateway, liên kết File Gateway với Amazon S3.
- Cấu hình và thực hành mount thành công SMB File Share lên môi trường Windows Server.
- Tham gia sự kiện công nghệ cộng đồng AWS Vietnam Community Day nhằm đúc kết kiến thức thực tế về GenAIOps, Agentic AI và kiến trúc Multi-Agent phục vụ vận hành doanh nghiệp.

##  Công việc đã thực hiện

### 1. Nghiên cứu lý thuyết hạ tầng lưu trữ nâng cao và AWS Storage Gateway
- **Mô tả**: Ôn tập, củng cố lại kiến thức nền tảng về EC2, VPC và S3. Xem các video bài giảng về giải pháp lưu trữ kết hợp (Hybrid Cloud Storage) và tìm hiểu cơ chế hoạt động của File Storage trên Cloud. Nghiên cứu cách thức AWS Storage Gateway kết nối hạ tầng On-Premises truyền thống với các dịch vụ lưu trữ đám mây của AWS, tập trung chuyên sâu vào mô hình File Gateway kết hợp với Amazon S3.
- **Kết quả**: Hiểu rõ nguyên lý lưu trữ, bộ nhớ đệm (Caching) dữ liệu, quản lý lưu trữ đồng bộ dữ liệu trên Cloud và giao thức chia sẻ file qua mạng LAN (SMB và NFS).

### 2. Triển khai Hệ thống SMB File Share và Mount trên Windows Server
- **Mô tả**: Trực tiếp thực hành trên AWS Console để khởi tạo File Gateway và liên kết nó với một Amazon S3 bucket. Thực hiện cấu hình tạo, quản lý một file share sử dụng giao thức Server Message Block (SMB) và thiết lập quyền truy cập cho người dùng (Guest Access). Tiến hành khởi chạy một máy ảo Windows Server trên EC2 để giả lập môi trường local. Cấu hình quy tắc Security Group cho Storage Gateway và sử dụng giao diện điều khiển của Windows để map ổ đĩa mạng (Mount SMB File Share) bằng địa chỉ mạng của Storage Gateway.
- **Kết quả**: Kết nối ổ đĩa mạng thành công. Việc tạo, sửa hoặc xóa dữ liệu trên thư mục mạng này của Windows Server tự động đồng bộ hóa thời gian thực lên Amazon S3 Bucket một cách an toàn.
- **Tools/Tech**: AWS Storage Gateway, Amazon S3, Windows Server (EC2), SMB Protocol, Guest Access, Security Group, AWS CloudWatch.

### 3. Tham gia Sự kiện AWS Vietnam Community Day và Đúc kết Thực tế
- **Mô tả**: 
  - **Chuyên đề GenAIOps (Xây dựng bộ não AI thứ hai từ góc độ DevOps)**: Lắng nghe chia sẻ về chu trình xây dựng "Second AI Brain" (Lưu trữ → Truy xuất → Tạo phản hồi → Học hỏi) dựa trên hạ tầng AWS (S3, Vector DB, Bedrock). Phân tích các sai lầm phổ biến như nhồi nhét tài liệu không liên quan làm loãng ngữ cảnh của mô hình ngôn ngữ lớn (LLM).
  - **Chuyên đề Trợ lý AI và Kiến trúc Multi-Agent**: Ứng dụng bộ giải pháp Amazon Quick Suite tích hợp Agentic AI giúp tự động hóa tác vụ lặp lại của doanh nghiệp. Nghiên cứu tư duy thiết kế kiến trúc đa đại lý (Multi-Agent) mô phỏng các phòng ban chuyên trách tương tác và phản biện chéo lẫn nhau trong các bài toán phức tạp (như chấm điểm tín dụng ngân hàng).
- **Kết quả**: Nâng cao tư duy quản trị ngữ cảnh (Context Engineering), tiếp thu kỹ thuật thiết kế bộ phòng thủ kỹ thuật (JSON định dạng, cơ chế bỏ phiếu số đông) và làm chủ bài toán quản lý tài chính đám mây (FinOps) để kiểm soát chi phí hạ tầng Cloud trước khi hệ thống tăng trưởng đột biến (viral).
- **Tools/Tech**: Amazon Bedrock, Vector Databases, Amazon Quick Suite, Multi-Agent Architecture, Cost Optimization Strategies.

##  Kiến thức học được

###  Technical Skills
- **AWS Services**: AWS Storage Gateway (File Gateway), Amazon S3, Amazon EBS Volume, EBS Snapshot, Amazon Bedrock, Amazon CloudWatch.
- **System Administration & AI**: Kỹ năng quản trị Windows Server, mount ổ đĩa mạng qua dòng lệnh, xử lý lỗi giao thức SMB, mở port mạng (cổng 445 cho SMB). Nắm vững quy trình lưu trữ và trích xuất dữ liệu thông minh qua Vector DB trên hạ tầng đám mây.

###  Concepts & Theory
- **New Concepts**: Mô hình lưu trữ đám mây kết hợp giúp mở rộng không gian lưu trữ local vô hạn lên Cloud mà không làm gián đoạn ứng dụng hiện tại; Khái niệm bộ não AI doanh nghiệp và kiến trúc hệ thống đa nền tảng (Multi-Agent Architecture).
- **Best Practices**: Kiểm soát chặt chẽ thời gian khởi động của Gateway và cấu hình quy tắc Security Group tối giản (chỉ mở cổng cần thiết). Tập trung sửa đổi các chi tiết nhỏ mang lại giá trị thực tiễn cao (tiết kiệm token) thay vì xáo trộn toàn bộ thiết kế hệ thống quá sớm.

##  Khó khăn và giải pháp
- **Vấn đề**: Gặp lỗi xác thực hệ thống "Access Denied" khi thực hiện lệnh mount ổ đĩa SMB trên Windows Server; đồng thời các kiến thức nâng cao về AI, LLM và Vector DB tại sự kiện nằm ngoài phạm vi bài học cơ bản gây khó khăn khi tiếp thu.
- **Root Cause**: Khai báo nhầm lẫn giữa địa chỉ Public IP và Private IP của Storage Gateway trong điều kiện Security Group chưa mở port 445 nhận traffic từ máy Windows. Dịch vụ Storage Gateway cần thời gian khởi động khá lâu nên ban đầu dễ nhầm lẫn là bị lỗi.
- **Solution**: Đọc tài liệu hướng dẫn, cập nhật Inbound rule của Security Group gán cho Storage Gateway để mở cổng 445 từ CIDR block của Windows Server EC2, đồng thời cấu hình chính xác tài khoản Guest Access. Đối với sự kiện công nghệ, chủ động ghi chú lại các từ khóa cốt lõi, chụp ảnh slide bài giảng và hỏi đáp trực tiếp với các diễn giả tại hội trường để làm rõ sơ đồ vận hành.

##  Reflection & Insights
- Việc tích hợp hạ tầng truyền thống lên đám mây đòi hỏi sự am hiểu sâu sắc về cả hai môi trường. Bên cạnh đó, công nghệ thay đổi vô cùng nhanh chóng; kỳ thực tập không chỉ là việc hoàn thành các bài Lab có sẵn mà phải liên tục cập nhật xu hướng thị trường. Dưới áp lực cực hạn của tiến độ doanh nghiệp, công nghệ có thể bù đắp nhanh bằng AI nhưng sự gắn kết và phối hợp đội ngũ (Team Chemistry) mới là chìa khóa cốt lõi để thành công.

##  Kế hoạch tuần tiếp theo
- Quay trở lại lộ trình đào tạo, tập trung vào mảng kiến thức hạ tầng nâng cao: Học về Docker, container, tìm hiểu CI/CD cơ bản trên AWS, cấu hình hệ thống tự động co giãn (Auto Scaling Group) và Elastic Load Balancer (Tuần 7).

##  Self Assessment
- Productivity: 9/10
- Learning: 9.5/10
- Collaboration: 8/10