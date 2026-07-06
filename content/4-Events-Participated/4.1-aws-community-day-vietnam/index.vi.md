+++
title = "Sự kiện: AWS Vietnam Community Day"
date = 2026-05-23
weight = 1
chapter = false
pre = " <b> 4.1. </b> "
+++

### Tổng quan

* **Tên sự kiện:** AWS Vietnam Community Day (Technology Proceedings & Enterprise Operations)
* **Thời gian tham gia:** Ngày 23 tháng 05 năm 2026
* **Chủ đề chính:** GenAIOps, AI Doanh nghiệp, Hạ tầng Điện toán Đám mây, Tối ưu hóa Amazon CloudFront

---

### I. Tóm tắt các phiên trình bày

#### 1. GenAIOps: Xây dựng "Bộ não AI thứ hai" từ góc nhìn DevOps

* **Diễn giả:** Anh Tịnh (Platform Engineer tại GoTymeX)
* **Vấn đề:** Chất lượng của các hệ thống AI thường bị ảnh hưởng bởi việc thiếu ngữ cảnh của hệ thống mục tiêu, thiếu bộ nhớ dài hạn, đồng thời sử dụng các prompt quá chung chung hoặc cung cấp tài liệu không liên quan.
* **Giải pháp:** Xây dựng mô hình "Second AI Brain" dựa trên quy trình **Store → Retrieve → Respond → Learn**, kết hợp các dịch vụ AWS như Amazon S3, Vector Database và Amazon Bedrock. Context Engineering được xem là một kỹ năng quan trọng trong việc phát triển AI hiện đại.

#### 2. Xây dựng trợ lý AI thân thiện với người dùng bằng Amazon Quick Suite

* **Diễn giả:** Hải Anh (G-AsiaPacific Vietnam, AWS Community Builder)
* **Giải pháp:** Sử dụng Amazon Quick Suite kết hợp với Agentic AI để kết nối dữ liệu nội bộ doanh nghiệp với các nguồn tri thức bên ngoài thông qua hơn 40 bộ kết nối dữ liệu, từ đó tự động hóa nhiều quy trình làm việc.
* **Ứng dụng:** Xây dựng trợ lý quản lý dự án có khả năng tự động tạo biên bản cuộc họp (Minutes of Meeting), gửi email và lên lịch họp.

#### 3. Từ Edge đến Origin: Amazon CloudFront như nền tảng cho ứng dụng

* **Diễn giả:** Nguyễn Tuấn Thịnh (DevOps Engineer tại First Cloud AI Journey)
* **Mô hình chi phí:** CloudFront áp dụng mô hình giá cố định (Flat-rate Pricing), giúp doanh nghiệp tránh được rủi ro chi phí băng thông tăng đột biến khi lưu lượng truy cập lớn hoặc bị tấn công DDoS.
* **Tối ưu và bảo mật:** Hệ thống hơn 700 điểm hiện diện (PoPs) trên toàn cầu giúp tăng tốc phân phối nội dung, đạt tỷ lệ nén dữ liệu lên đến 82%, đồng thời hỗ trợ mTLS và cơ chế bảo vệ Origin thông qua VPC Origin và Origin Access Control (OAC).

#### 4. 36 giờ tại LotusHacks – Dự án UTMorpho

* **Đại diện:** Nhóm VIB
* **Sản phẩm:** UTMorpho khắc phục các hạn chế của AI trong việc tái tạo giao diện bằng cách sử dụng Smart Diffing kết hợp Amazon Bedrock. Giải pháp cho phép chỉnh sửa giao diện trực tiếp theo mô hình WYSIWYG mà vẫn giữ nguyên cấu trúc hiện có và giảm số lượng token tiêu thụ.

#### 5. Tính không xác định của mô hình LLM ngay cả khi cấu hình cố định

* **Diễn giả:** Đào Đức (Solution Architect - Cloud Kinetics)
* **Thực tế:** Ngay cả khi đặt `Temperature = 0`, kết quả sinh ra từ mô hình ngôn ngữ lớn (LLM) vẫn có thể khác nhau do cách GPU xử lý song song và cơ chế batching trong quá trình suy luận.
* **Giải pháp:** Thiết lập `Temperature = 0.1`, tăng Repeat Penalty, sử dụng Majority Voting và giới hạn đầu ra bằng JSON Mode hoặc Regex Grammar để đảm bảo tính ổn định.

#### 6. Kiến trúc Multi-Agent cho hệ thống chấm điểm tín dụng Startup

* **Diễn giả:** Vy Lâm (Senior Business Systems Analyst tại VPBank)
* **Giải pháp:** Xây dựng mô hình "Hội đồng tín dụng ảo" gồm nhiều AI Agent chuyên biệt (Tài chính, Thị trường, Rủi ro và Tuân thủ), được điều phối bởi một Manager Agent.
* **Kết quả:** Thời gian xử lý hồ sơ giảm từ 2–3 tuần xuống còn khoảng 2–4 giờ (nhanh hơn khoảng 95%), đồng thời giảm đáng kể chi phí xử lý nhưng vẫn đảm bảo tính bảo mật nhờ Amazon Bedrock AgentCore trong môi trường VPC riêng.

---

### II. Cảm nhận và bài học rút ra

Thông qua sự kiện này, mình nhận thấy AI đang chuyển từ giai đoạn thử nghiệm sang triển khai thực tế trong doanh nghiệp. Các chủ đề về GenAIOps, Agentic AI và tự động hóa quy trình cho thấy AI không còn chỉ là công cụ hỗ trợ mà đang dần trở thành một thành phần quan trọng trong hệ thống vận hành.

Bên cạnh đó, mình hiểu rõ hơn vai trò của hạ tầng đám mây trong việc triển khai các ứng dụng AI quy mô lớn. Những dịch vụ như Amazon CloudFront hay Amazon Bedrock không chỉ giúp tối ưu hiệu năng mà còn đảm bảo khả năng mở rộng, bảo mật và quản lý chi phí.

Một bài học đáng giá khác là yếu tố con người. Qua phần chia sẻ về cuộc thi LotusHacks, mình nhận thấy tinh thần làm việc nhóm, khả năng phối hợp và giao tiếp hiệu quả có ý nghĩa không kém so với kiến thức kỹ thuật, đặc biệt trong các dự án có thời gian triển khai ngắn và áp lực cao.

### Hình ảnh minh chứng


![Policy](/images/8/23-05-2026.jpg)