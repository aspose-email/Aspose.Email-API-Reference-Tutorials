---
date: '2025-12-14'
description: Tìm hiểu cách gửi email có đính kèm tệp tin bằng Aspose.Email cho Java.
  Hướng dẫn từng bước này bao gồm cài đặt, tạo tin nhắn, thêm tệp và lưu dưới dạng
  MSG.
keywords:
- send emails with attachments using Aspose.Email for Java
- Aspose.Email setup for Java
- handling email attachments in Java
title: Cách gửi email có tệp đính kèm bằng Aspose.Email cho Java
url: /vi/java/attachments-handling/build-send-emails-attachments-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cách Gửi Email kèm Tệp Đính Kèm Sử Dụng Aspose.Email cho Java

## Giới thiệu

Trong bối cảnh kỹ thuật số ngày nay, **cách gửi email** một cách lập trình là kỹ năng cốt lõi cho bất kỳ nhà phát triển Java nào xây dựng công cụ báo cáo, dịch vụ thông báo hoặc quy trình tự động. Hướng dẫn này sẽ chỉ cho bạn cách sử dụng Aspose.Email cho Java — một thư viện mạnh mẽ giúp tạo email, đính kèm tệp và thậm chí lưu tin nhắn dưới dạng tệp MSG một cách đơn giản. Khi hoàn thành, bạn sẽ có thể gửi email kèm đính kèm, đính kèm tệp vào email và lưu email dưới dạng msg chỉ với vài dòng mã.

**Bạn sẽ học được**
- Cài đặt Aspose.Email cho Java trong môi trường phát triển của bạn  
- Tạo một tin nhắn email với địa chỉ người gửi và người nhận  
- Đính kèm nhiều loại tệp (văn bản, hình ảnh, tài liệu, lưu trữ, PDF)  
- Lưu email đã tạo dưới dạng tệp MSG để sử dụng sau  

Bạn đã sẵn sàng nâng cao khả năng tự động hóa email? Hãy bắt đầu với các yêu cầu trước.

## Câu trả lời nhanh
- **Thư viện tôi cần là gì?** Aspose.Email for Java  
- **Tôi có thể đính kèm bất kỳ loại tệp nào không?** Có – văn bản, hình ảnh, PDF, lưu trữ, tài liệu Word, v.v.  
- **Tôi có cần giấy phép không?** Giấy phép tạm thời đủ cho việc thử nghiệm; giấy phép đầy đủ cần thiết cho môi trường sản xuất.  
- **Làm sao để lưu email?** Sử dụng `message.save(..., SaveOptions.getDefaultMsg())`.  
- **Email HTML có được hỗ trợ không?** Chắc chắn – đặt `message.isBodyHtml(true)` và cung cấp nội dung HTML.

## Aspose.Email cho Java là gì?
Aspose.Email cho Java là một API hiệu suất cao cho phép bạn tạo, chỉnh sửa và gửi tin nhắn email mà không cần dựa vào máy chủ mail bên ngoài. Nó xử lý cấu trúc MIME, đính kèm và các định dạng email khác nhau (EML, MSG, MHTML) ngay từ đầu.

## Tại sao nên sử dụng Aspose.Email để gửi email kèm đính kèm?
- **Không cần SMTP bên ngoài** để tạo và lưu tin nhắn.  
- **Hỗ trợ đính kèm phong phú** – bạn có thể thêm bất kỳ loại tệp nào, kể cả các tệp nhị phân lớn.  
- **Tương thích đa nền tảng** – hoạt động trên JVM của Windows, Linux và macOS.  
- **Lưu tích hợp** – dễ dàng xuất ra MSG, EML hoặc MHTML để lưu trữ.

## Yêu cầu trước

- **Bộ công cụ phát triển Java (JDK):** Phiên bản 16 trở lên.  
- **IDE:** IntelliJ IDEA, Eclipse hoặc bất kỳ trình chỉnh sửa nào hỗ trợ Java.  
- **Maven:** Chúng ta sẽ quản lý các phụ thuộc bằng Maven.  

Bạn cần có kiến thức cơ bản về Java và dự án Maven.

## Cài đặt Aspose.Email cho Java

### Cài đặt qua Maven

Thêm phụ thuộc sau vào tệp `pom.xml` của bạn:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### License Acquisition

Aspose.Email for Java có thể được sử dụng với bản dùng thử miễn phí hoặc giấy phép mua. Để thử toàn bộ tính năng, hãy lấy giấy phép tạm thời:

1. Truy cập trang [Temporary License page](https://purchase.aspose.com/temporary-license/).  
2. Làm theo hướng dẫn để yêu cầu giấy phép dùng thử miễn phí.  
3. Áp dụng giấy phép trong ứng dụng của bạn theo mô tả trong tài liệu của Aspose.

### Basic Initialization

Bắt đầu bằng cách tạo một đối tượng `MailMessage` và thiết lập các địa chỉ cơ bản:

```java
import com.aspose.email.MailAddress;
import com.aspose.email.MailMessage;

// Initialize the MailMessage object
MailMessage message = new MailMessage();
message.setFrom(new MailAddress("sender@sender.com"));
message.getTo().addMailAddress(new MailAddress("receiver@gmail.com"));
```

## Hướng dẫn triển khai

### Cách gửi email kèm đính kèm bằng Aspose.Email cho Java

#### Khởi tạo đối tượng `MailMessage`

```java
// Set 'From' address
message.setFrom(new MailAddress("sender@sender.com"));

// Add 'To' address
message.getTo().addMailAddress(new MailAddress("receiver@gmail.com"));
```

#### Định nghĩa đường dẫn thư mục cho các tệp đính kèm

Thay thế `"YOUR_DOCUMENT_DIRECTORY/"` bằng đường dẫn chứa các tệp bạn muốn đính kèm:

```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY/";
```

#### Thêm đính kèm (attach files to email)

Bạn có thể đính kèm nhiều loại tệp. Dưới đây chúng tôi thêm một tệp văn bản, một hình ảnh, một tài liệu Word, một tệp RAR và một PDF:

```java
// Adding a text file
Attachment textAttachment = new Attachment(dataDir + "1.txt");
message.getAttachments().addItem(textAttachment);

// Adding an image file (JPEG format)
message.getAttachments().addItem(new Attachment(dataDir + "1.jpg"));

// Adding a Word document
message.getAttachments().addItem(new Attachment(dataDir + "1.doc"));

// Adding a RAR archive
message.getAttachments().addItem(new Attachment(dataDir + "1.rar"));

// Adding a PDF document
message.getAttachments().addItem(new Attachment(dataDir + "1.pdf"));
```

#### Định nghĩa đường dẫn thư mục đầu ra

Đặt thư mục nơi tệp MSG cuối cùng sẽ được lưu:

```java
String outputDir = "YOUR_OUTPUT_DIRECTORY/";
```

#### Lưu tin nhắn Email (save email as msg)

```java
message.save(outputDir + "AddAttachmentToANewEmailMessage_out.msg", SaveOptions.getDefaultMsg());
```

## Ứng dụng thực tiễn

Aspose.Email cho Java tỏa sáng trong nhiều kịch bản thực tế:

1. **Báo cáo tự động:** Tạo báo cáo hàng ngày/hàng tuần và gửi email kèm tệp PDF hoặc Excel.  
2. **Hệ thống thông báo:** Gửi cảnh báo kèm tệp log, ảnh chụp màn hình hoặc sao lưu cấu hình.  
3. **Giải pháp sao lưu:** Định kỳ gửi email chứa dump cơ sở dữ liệu hoặc tệp lưu trữ để lưu trữ ngoài site.  

## Các lưu ý về hiệu năng

- **Giải phóng đối tượng:** Gọi `message.dispose()` khi tin nhắn không còn cần thiết để giải phóng tài nguyên gốc.  
- **Luồng đính kèm:** Đối với tệp lớn, sử dụng stream để tránh tải toàn bộ tệp vào bộ nhớ.  
- **Pool luồng:** Khi gửi nhiều email đồng thời, tái sử dụng pool luồng để giảm tải JVM.  

## Các vấn đề thường gặp & Giải pháp

| Vấn đề | Giải pháp |
|-------|----------|
| **Đính kèm lớn (>25 MB) thất bại** | Kiểm tra máy chủ SMTP của bạn (nếu sử dụng) cho phép tải trọng lớn; tăng heap JVM nếu cần. |
| **Đính kèm không hiển thị** | Đảm bảo đường dẫn tệp đúng và tệp có thể truy cập; kiểm tra quyền tệp. |
| **MSG đã lưu không mở được** | Sử dụng `SaveOptions.getDefaultMsg()` và chắc chắn bạn đang dùng phiên bản Aspose.Email mới nhất. |

## Câu hỏi thường gặp

**Hỏi: Làm sao để thêm nhiều người nhận vào một email?**  
**Đáp:** Sử dụng `message.getTo().addMailAddress(new MailAddress("email@example.com"));` cho mỗi người nhận.

**Hỏi: Aspose.Email có thể xử lý các tệp đính kèm lớn hơn 25 MB không?**  
**Đáp:** Có, nhưng bạn phải đảm bảo máy chủ và JVM có đủ bộ nhớ và bất kỳ máy chuyển tiếp SMTP nào cũng cho phép tin nhắn lớn.

**Hỏi: Có thể gửi email HTML bằng Aspose.Email không?**  
**Đáp:** Chắc chắn! Đặt `message.isBodyHtml(true);` và gán nội dung HTML cho `message.setHtmlBody("<h1>Hello</h1>");`.

**Hỏi: Làm sao để gỡ lỗi khi gửi email?**  
**Đáp:** Bao quanh mã của bạn bằng khối try‑catch, ghi lại stack trace của ngoại lệ, và bật logging của Aspose.Email qua `License.setLogFolder("path")`.

**Hỏi: Những thực hành bảo mật nào nên tuân theo?**  
**Đáp:** Xác thực tất cả địa chỉ email, làm sạch đường dẫn tệp, và không bao giờ nhúng dữ liệu do người dùng cung cấp trực tiếp vào nội dung email mà không thực hiện escaping.

## Kết luận

Bây giờ bạn đã có quy trình hoàn chỉnh, sẵn sàng cho môi trường sản xuất để **cách gửi email** kèm đính kèm, đính kèm tệp vào email, và **lưu email dưới dạng msg** bằng Aspose.Email cho Java. Khám phá toàn bộ [documentation](https://reference.aspose.com/email/java/) để tìm hiểu sâu hơn về các tính năng nâng cao như gửi SMTP, tạo nội dung HTML, và mã hoá.

## Tài nguyên
- [Tài liệu Aspose.Email](https://reference.aspose.com/email/java/)
- [Tải xuống Aspose.Email](https://releases.aspose.com/email/java/)
- [Mua giấy phép](https://purchase.aspose.com/buy)
- [Truy cập dùng thử miễn phí](https://releases.aspose.com/email/java/)
- [Đăng ký giấy phép tạm thời](https://purchase.aspose.com/temporary-license/)
- [Diễn đàn hỗ trợ Aspose](https://forum.aspose.com/c/email/10)

---

**Last Updated:** 2025-12-14  
**Tested With:** Aspose.Email 25.4 (JDK 16)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}