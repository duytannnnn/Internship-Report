---
title: "Kiểm thử lấy invoice theo ID"
weight: 3
chapter: false
pre: " <b> 5.5.3 </b> "
---

#### Bước 1: Tạo request

1. Trong Collection **InvoiceGetAPI-Tests**, nhấn dấu **"+"** để tạo request.

![Test get all invoices by ID](/images/5/5.3/001.png)

2. Đặt tên: `Get Invoices By ID`.

![Test get all invoices by ID](/images/5/5.3/002.png)

3. Chọn method **GET**.

![Test get all invoices by ID](/images/5/5.3/003.png)

5. Truy cập API Gateway, chọn API: `GetInvoiceAPI`.

6. Chọn mục **Stages**.

7. Bấm dấu **“+”** để mở ra đường dẫn đến `/invoice/{id}` như dưới đây:

![Test get all invoices by ID](/images/5/5.3/004.png)

8. Chọn phương thức **GET** và sao chép **Invoke URL**.

![Test get all invoices by ID](/images/5/5.3/005.png)

9. Dán **Invoke URL** vừa sao chép vào trong Postman như sau:

![Test get all invoices by ID](/images/5/5.3/006.png)

10. Xóa `{id}` trong API endpoint của Postman và thay bằng ID Invoice trong DynamoDB:

```bash
https://pwxyscvv7i.execute-api.ap-southeast-1.amazonaws.com/dev/invoice/<InvoiceId_trong_DynamoDB>
```

![Test get all invoices by ID](/images/5/5.3/007.png)

![Test get all invoices by ID](/images/5/5.3/008.png)

11. Nhấn nút **Send** để xem kết quả.

![Test get all invoices by ID](/images/5/5.3/009-send.png)

14. Kết quả trả về thành công như sau:

![Test get all invoices by ID](/images/5/5.3/010-result.png)

> Bạn có thể kiểm tra 2 tệp hóa đơn còn lại!
