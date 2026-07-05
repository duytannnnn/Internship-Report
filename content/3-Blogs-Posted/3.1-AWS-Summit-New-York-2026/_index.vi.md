+++
title = "AWS Summit New York 2026 – Những công bố nổi bật về AI Agent"
date = 2026-07-05
weight = 8
pre = " <b> 3.1 </b> "
+++

## Tổng quan

Tại AWS Summit New York 2026, AWS đã công bố nhiều dịch vụ và tính năng mới nhằm hỗ trợ doanh nghiệp xây dựng, quản lý và vận hành các AI Agent trong môi trường thực tế (production). Các nội dung được giới thiệu tập trung vào AI Agent, bảo mật, hiện đại hóa phần mềm, DevOps và quản lý dữ liệu phục vụ các quy trình làm việc tự động.

Mục tiêu của AWS là xây dựng một nền tảng hoàn chỉnh giúp doanh nghiệp phát triển các ứng dụng AI nhanh hơn, an toàn hơn và dễ dàng mở rộng trong tương lai.

## Những công bố nổi bật

AWS đã giới thiệu nhiều dịch vụ và tính năng đáng chú ý.

### Amazon Bedrock AgentCore

Amazon Bedrock AgentCore được bổ sung nhiều tính năng mới giúp AI Agent có thể truy cập dữ liệu nội bộ của doanh nghiệp, tìm kiếm thông tin trên Internet và kết nối với nhiều nguồn dữ liệu khác nhau. Điều này giúp quá trình xây dựng và triển khai AI Agent trong môi trường thực tế trở nên đơn giản và hiệu quả hơn.

### Amazon Bedrock Managed Knowledge Base

Managed Knowledge Base giúp đơn giản hóa việc xây dựng hệ thống Retrieval-Augmented Generation (RAG). Dịch vụ này cung cấp sẵn các bộ kết nối dữ liệu, khả năng xử lý nhiều định dạng tài liệu và cơ chế truy xuất thông minh, giúp AI Agent khai thác tri thức doanh nghiệp một cách chính xác.

### Web Search cho Amazon Bedrock AgentCore

AI Agent có thể tìm kiếm thông tin mới từ Internet thông qua cơ chế được AWS quản lý sẵn. Kết quả tìm kiếm được trích dẫn nguồn đầy đủ, đồng thời vẫn đảm bảo dữ liệu của khách hàng luôn nằm trong môi trường bảo mật của AWS.

### AWS WAF AI Traffic Monetization

AWS bổ sung khả năng giúp các nhà xuất bản nội dung theo dõi, quản lý và thu phí lưu lượng truy cập từ AI Bot hoặc AI Agent khi chúng sử dụng dữ liệu hoặc API của doanh nghiệp.

### Bedrock AgentCore Harness

Bedrock AgentCore Harness đã được phát hành chính thức, cho phép nhà phát triển cấu hình mô hình AI, công cụ, kỹ năng và hướng dẫn hoạt động của AI Agent mà không cần tự xây dựng toàn bộ cơ chế điều phối.

### AWS Continuum và Security Agent

AWS giới thiệu các công cụ bảo mật sử dụng AI có khả năng tự động phát hiện lỗ hổng, đánh giá mức độ ảnh hưởng, thực hiện threat modeling theo phương pháp STRIDE, kiểm tra Pull Request và đề xuất cách khắc phục ngay trong quá trình phát triển phần mềm.

### Kiro cho iOS

Ứng dụng Kiro hiện đã có phiên bản dành cho iOS, cho phép lập trình viên theo dõi các phiên làm việc với AI, xem lịch sử thay đổi mã nguồn và quản lý quá trình phát triển trực tiếp trên điện thoại.

### AWS DevOps Agent

AWS DevOps Agent hỗ trợ đánh giá mức độ sẵn sàng trước khi phát hành phần mềm, tự động thực hiện kiểm thử trong môi trường tương tự production nhằm giảm thiểu rủi ro khi triển khai.

### AWS Transform Continuous Modernization

AWS Transform có khả năng phân tích mã nguồn liên tục, phát hiện Technical Debt, xác định mức độ ưu tiên và tự động tạo Pull Request để cải thiện chất lượng mã nguồn.

### Amazon S3 Annotations

Amazon S3 hỗ trợ gắn thêm metadata và thông tin ngữ cảnh trực tiếp vào các đối tượng lưu trữ. Điều này giúp AI Agent hiểu dữ liệu tốt hơn và nâng cao hiệu quả xử lý trong các hệ thống quy mô lớn.

## Những vấn đề được giải quyết

Việc triển khai AI Agent trong doanh nghiệp hiện nay vẫn gặp nhiều khó khăn như:

- Dữ liệu phân tán trên nhiều hệ thống khác nhau.
- AI cần truy cập thông tin mới nhưng vẫn phải đảm bảo tính bảo mật.
- Việc quản lý quyền truy cập và kiểm soát AI ngày càng phức tạp.
- Quá trình kiểm tra bảo mật chưa theo kịp tốc độ phát triển phần mềm.
- Technical Debt tích lũy trong các dự án lớn.
- Chủ sở hữu nội dung khó kiểm soát AI Bot truy cập dữ liệu.
- Metadata phục vụ AI thường phải quản lý bằng nhiều hệ thống riêng biệt.

## Giải pháp của AWS

Để giải quyết các vấn đề trên, AWS cung cấp một hệ sinh thái hoàn chỉnh bao gồm:

- Amazon Bedrock AgentCore để xây dựng AI Agent cho môi trường production.
- Managed Knowledge Base và Web Search để truy xuất tri thức doanh nghiệp và Internet một cách an toàn.
- AWS WAF AI Traffic Monetization giúp kiểm soát và thu phí lưu lượng AI.
- AWS Continuum và Security Agent hỗ trợ tự động hóa quy trình bảo mật.
- AWS DevOps Agent giúp đánh giá và kiểm thử trước khi phát hành phần mềm.
- AWS Transform hỗ trợ hiện đại hóa ứng dụng và giảm Technical Debt.
- Amazon S3 Annotations giúp bổ sung ngữ cảnh cho dữ liệu phục vụ AI.

Những dịch vụ này kết hợp với nhau tạo thành một nền tảng toàn diện giúp doanh nghiệp phát triển các ứng dụng AI an toàn, có khả năng mở rộng và dễ quản lý trong môi trường thực tế.

## Cảm nhận cá nhân

Qua các công bố tại AWS Summit New York 2026, mình nhận thấy AWS đang từng bước xây dựng một hệ sinh thái hoàn chỉnh dành cho AI Agent thay vì chỉ cung cấp các mô hình AI. AWS tập trung vào toàn bộ vòng đời của một ứng dụng AI, từ quản lý dữ liệu, truy xuất tri thức, bảo mật, triển khai, giám sát đến hiện đại hóa phần mềm.

Việc tìm hiểu các công nghệ mới này giúp mình có cái nhìn rõ hơn về xu hướng phát triển của điện toán đám mây và AI trong tương lai. Đồng thời, nhiều dịch vụ được giới thiệu hoàn toàn có thể áp dụng vào dự án **Serverless AI Invoice Scanner** mà mình đã thực hiện, chẳng hạn như cải thiện khả năng truy xuất dữ liệu, tăng cường bảo mật, bổ sung ngữ cảnh cho dữ liệu và xây dựng các AI Agent có khả năng hỗ trợ xử lý hóa đơn thông minh hơn.

## Tài liệu tham khảo

AWS Blog: https://aws.amazon.com/blogs/aws/top-announcements-of-the-aws-summit-in-new-york-2026/


### Hình ảnh minh họa
![Policy](/images/AWS-Summit-New-York-2026.png)