---
date: 2025-12-01
description: Tìm hiểu cách gửi email có hình ảnh nhúng bằng Aspose.Email cho Java.
  Hướng dẫn này chỉ cách nhúng hình ảnh vào email và tạo email HTML trong Java với
  các tệp đính kèm nội tuyến.
language: vi
linktitle: Working with Inline Attachments in Aspose.Email
second_title: Aspose.Email Java Email Management API
title: Cách gửi email với hình ảnh nhúng bằng Aspose.Email cho Java
url: /java/advanced-email-attachments/working-with-inline-attachments/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Cách Gửi Email với Hình Ảnh Nhúng Sử Dụng Aspose.Email cho Java

Nhúng hình ảnh trực tiếp vào email giúp tin nhắn của bạn trông chuyên nghiệp và đảm bảo người nhận thấy được đồ họa mà không cần tải xuống các tệp riêng biệt. Trong hướng dẫn này, bạn sẽ học **cách gửi email với hình ảnh nhúng** bằng Aspose.Email cho Java, bao gồm mọi thứ từ việc thiết lập thư viện, tạo email HTML, thêm tài nguyên nội tuyến, và cuối cùng gửi tin nhắn.

## Quick Answers
- **Lớp chính cho hình ảnh nội tuyến là gì?** `LinkedResource`
- **Phương thức nào tham chiếu hình ảnh trong HTML?** Sử dụng `cid:yourContentId` trong thẻ `<img>`
- **Tôi có cần giấy phép cho việc phát triển không?** Bản dùng thử miễn phí hoạt động cho việc thử nghiệm; cần giấy phép cho môi trường sản xuất
- **Tôi có thể gửi email qua bất kỳ máy chủ SMTP nào không?** Có, chỉ cần cấu hình `SmtpClient` với chi tiết máy chủ của bạn
- **Cách tiếp cận này có tương thích với tất cả các client email chính không?** Hầu hết các client hiện đại (Outlook, Gmail, Thunderbird) hỗ trợ hình ảnh nhúng CID

## Các Tệp Đính Kèm Nội Tuyến (Hình Ảnh Nhúng)?

Các tệp đính kèm nội tuyến—đôi khi được gọi là hình ảnh nhúng hoặc CID—là các tệp nằm bên trong phần MIME của email. Chúng được tham chiếu từ phần HTML của tin nhắn bằng **Content‑ID** (CID). Kỹ thuật này cho phép bạn **nhúng hình ảnh vào email** để chúng hiển thị ngay tại vị trí bạn đặt thẻ `<img>`, mà không xuất hiện như các tệp đính kèm có thể tải xuống riêng.

## Tại Sao Nên Sử Dụng Hình Ảnh Nhúng Trong Email Java Của Bạn?

- **Giao diện chuyên nghiệp:** Logo, banner và hình ảnh sản phẩm hiển thị ngay lập tức.
- **Tăng tương tác:** Người nhận có xu hướng đọc email trông đầy đủ hơn.
- **Không cần click thêm:** Người dùng không cần tải xuống tệp đính kèm để xem hình ảnh.
- **Nhận diện thương hiệu nhất quán:** Tài sản thương hiệu của bạn được giữ trong nội dung tin nhắn.

## Yêu Cầu Trước

- Thư viện Aspose.Email cho Java (tải xuống từ [tài liệu chính thức Aspose.Email cho Java](https://reference.aspose.com/email/java/))
- Môi trường phát triển Java 8+
- Truy cập vào máy chủ SMTP để gửi thư
- Tệp hình ảnh bạn muốn nhúng (ví dụ, `logo.png`)

## Hướng Dẫn Từng Bước

### Bước 1: Tạo Thông Điệp Email HTML Cơ Bản

Đầu tiên, thiết lập một `MailMessage` đơn giản với phần thân HTML. Đây sẽ là nền tảng mà chúng ta sẽ nhúng hình ảnh sau này.

```java
// Import necessary classes
import com.aspose.email.MailAddress;
import com.aspose.email.MailMessage;

// Create a new email message
MailMessage message = new MailMessage();
message.setSubject("Hello, World!");
message.setFrom(new MailAddress("sender@example.com"));
message.setTo(new MailAddress("recipient@example.com"));
message.setHtmlBody("<html><body>This is a sample email with inline attachments.</body></html>");
```

### Bước 2: Thêm Hình Ảnh Nội Tuyến Sử Dụng `LinkedResource`

Bây giờ chúng ta nhúng một hình ảnh. Lớp `LinkedResource` đại diện cho tệp đính kèm nội tuyến. Gán một **Content‑ID** duy nhất và tham chiếu nó trong phần thân HTML bằng `cid:`.

```java
import com.aspose.email.LinkedResource;

// Create a LinkedResource for the image
LinkedResource linkedResource = new LinkedResource("path/to/your/image.png");
linkedResource.setContentId("image001"); // Unique ID for the inline image

// Add the LinkedResource to the HTML body
message.getLinkedResources().add(linkedResource);

// Reference the inline image in the HTML body
message.setHtmlBody("<html><body>This is an inline image: <img src='cid:image001'></body></html>");
```

> **Mẹo chuyên nghiệp:** Giữ `ContentId` đơn giản và duy nhất trong thông điệp để tránh xung đột.

### Bước 3: Gửi Email qua `SmtpClient`

Cấu hình các thiết lập SMTP của bạn và gửi thông điệp. Hình ảnh nhúng sẽ đi cùng email, vì vậy người nhận sẽ thấy nó ngay lập tức.

```java
import com.aspose.email.SmtpClient;

// Create an instance of SmtpClient
SmtpClient client = new SmtpClient("smtp.example.com", 587, "username", "password");

// Send the email
client.send(message);
```

### Bước 4: Nhận và Trích Xuất Hình Ảnh Nội Tuyến (Tùy Chọn)

Nếu bạn cần xử lý các tin nhắn đến có chứa hình ảnh nhúng, bạn có thể tải tệp `.eml` và truy cập `LinkedResources` của nó.

```java
import com.aspose.email.MailMessage;
import com.aspose.email.LinkedResourceCollection;

// Load the received email message
MailMessage receivedMessage = MailMessage.load("path/to/received_email.eml");

// Access the inline attachments
LinkedResourceCollection inlineAttachments = receivedMessage.getLinkedResources();
```

## Các Vấn Đề Thường Gặp & Cách Khắc Phục

| Vấn đề | Nguyên nhân | Cách khắc phục |
|-------|-------------|----------------|
| **Không khớp Content‑ID** | Tham chiếu `cid:` trong HTML không khớp với `ContentId` được đặt trên `LinkedResource`. | Đảm bảo các chuỗi giống hệt nhau (`image001` vs `cid:image001`). |
| **Không tìm thấy tệp** | Đường dẫn tới hình ảnh không đúng hoặc tệp bị thiếu. | Kiểm tra đường dẫn tuyệt đối/relative và chắc chắn tệp tồn tại trên máy chủ. |
| **Xác thực SMTP thất bại** | Thông tin đăng nhập hoặc cài đặt máy chủ sai. | Kiểm tra lại host, port, tên người dùng và mật khẩu. Bật TLS/SSL nếu cần. |
| **Hình ảnh không hiển thị trong một số client** | Một số client chặn tài nguyên bên ngoài. | Sử dụng hình ảnh nhúng CID (như ví dụ) thay vì URL bên ngoài. |

## Câu Hỏi Thường Gặp

**Q: Làm sao để tải Aspose.Email cho Java?**  
**A:** Bạn có thể tải Aspose.Email cho Java từ [tài liệu](https://reference.aspose.com/email/java/). Thực hiện theo hướng dẫn cài đặt để thiết lập trong dự án của bạn.

**Q: Tôi có thể sử dụng Aspose.Email cho Java cùng với các thư viện Java khác không?**  
**A:** Có, Aspose.Email tích hợp mượt mà với các thư viện Java khác, cho phép bạn kết hợp xử lý email với tạo PDF, OCR, hoặc truy cập cơ sở dữ liệu.

**Q: Các định dạng tệp nào được hỗ trợ cho tệp đính kèm nội tuyến?**  
**A:** Các định dạng hình ảnh phổ biến như PNG, JPEG, GIF, cùng với các loại tài liệu khác (ví dụ, SVG) đều được hỗ trợ làm tài nguyên nội tuyến.

**Q: Làm sao để xử lý tệp đính kèm nội tuyến trong email HTML?**  
**A:** Sử dụng lớp `LinkedResource` để gán một `ContentId`, thêm nó vào `message.getLinkedResources()`, và tham chiếu trong phần thân HTML bằng `<img src='cid:yourContentId'>`.

**Q: Aspose.Email cho Java có tương thích với các máy chủ email khác nhau không?**  
**A:** Có, nó hoạt động với bất kỳ máy chủ SMTP/IMAP/POP3 nào. Chỉ cần cung cấp địa chỉ máy chủ, cổng và chi tiết xác thực đúng.

---

**Cập nhật lần cuối:** 2025-12-01  
**Kiểm tra với:** Aspose.Email cho Java 24.12 (phiên bản mới nhất tại thời điểm viết)  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}