---
date: '2026-08-27'
description: Tìm hiểu cách tải các tệp MSG và chuyển chúng sang MHTML với Aspose.Email
  for Java, bao gồm các cài đặt múi giờ tùy chỉnh và mẹo xử lý email hàng loạt.
keywords:
- how to load msg
- Aspose.Email Java
- convert MSG to MHTML
- email timezone offset
lastmod: '2026-08-27'
og_description: Tìm hiểu cách tải các tệp msg và xuất chúng dưới dạng MHTML bằng Aspose.Email
  for Java. Bao gồm cách xử lý múi giờ và mẹo xử lý hàng loạt.
og_image_alt: Guide to loading MSG files and saving as MHTML with Aspose.Email for
  Java
og_title: Cách tải msg và lưu dưới dạng MHTML với Aspose.Email for Java
schemas:
- author: Aspose
  dateModified: '2026-08-27'
  description: Learn how to load MSG files and convert them to MHTML with Aspose.Email
    for Java, including custom timezone settings and batch email processing tips.
  headline: How to load msg and save as MHTML using Aspose.Email for Java
  type: TechArticle
- description: Learn how to load MSG files and convert them to MHTML with Aspose.Email
    for Java, including custom timezone settings and batch email processing tips.
  name: How to load msg and save as MHTML using Aspose.Email for Java
  steps:
  - name: '**Reuse the license** – call `new License().setLicense(...)` once at application
      startup.'
    text: '**Reuse the license** – call `new License().setLicense(...)` once at application
      startup.'
  - name: '**Use try‑with‑resources** for automatic cleanup of streams.'
    text: '**Use try‑with‑resources** for automatic cleanup of streams.'
  - name: '**Log failures** to a separate file so you can retry problematic messages
      later.'
    text: '**Log failures** to a separate file so you can retry problematic messages
      later.'
  - name: '**Consider parallelism** with `ForkJoinPool` for large batches, but ensure
      each thread uses its own `MailMessage` instance.'
    text: '**Consider parallelism** with `ForkJoinPool` for large batches, but ensure
      each thread uses its own `MailMessage` instance.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Email supports EML, MHT, EMLX, and several other formats,
      totaling over 30 input types.
    question: Can I load emails from formats other than .msg?
  - answer: Use the streaming APIs (`MailMessage.load(InputStream, ...)`) to read
      and write data in chunks, which keeps memory consumption under 50 MB even for
      500‑page messages.
    question: How can I handle very large email files efficiently?
  - answer: Absolutely. You can add, remove, or replace attachments via the `msg.getAttachments()`
      collection, then call `save` to persist changes.
    question: Is it possible to modify attachments within a MailMessage?
  - answer: Pass a negative millisecond value to `setTimeZoneOffset`, e.g., `-3 *
      60 * 60 * 1000` for UTC‑3.
    question: What if my timezone offset is negative (behind UTC)?
  - answer: Yes, provided you have a valid commercial license. The free trial is limited
      to 20 MB per document.
    question: Can I use Aspose.Email in commercial projects?
  type: FAQPage
tags:
- email processing
- Aspose.Email
- Java email conversion
title: Cách tải tệp msg và lưu dưới dạng MHTML bằng Aspose.Email for Java
url: /vi/java/email-message-operations/load-save-emails-mhtml-aspose-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tải msg và lưu dưới dạng MHTML bằng Aspose.Email cho Java

## Giới thiệu

Nếu bạn cần **cách tải msg** các tệp, điều chỉnh dấu thời gian của chúng, và sau đó **chuyển đổi msg sang mhtml**, bạn đang ở đúng nơi. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn cách tải một email `.msg`, áp dụng một độ lệch múi giờ tùy chỉnh, và lưu kết quả dưới dạng một kho lưu trữ MHTML — tất cả đều sử dụng Aspose.Email cho Java. Dù bạn đang xử lý một tin nhắn duy nhất hay một **pipeline xử lý email hàng loạt**, các bước này sẽ cung cấp nền tảng vững chắc cho việc lưu trữ và di chuyển đáng tin cậy.

**Bạn sẽ học**
- Cách tải một `MailMessage` từ tệp `.msg`.
- Cách đặt múi giờ tùy chỉnh và ngày hiện tại.
- Cách lưu tin nhắn dưới dạng MHTML với định dạng chính xác.
- Mẹo để mở rộng phương pháp cho các kịch bản hàng loạt.

Sẵn sàng nâng cao quy trình làm việc với email? Hãy chuẩn bị môi trường trước tiên.

## Câu trả lời nhanh
- **Thư viện chính là gì?** Aspose.Email for Java.
- **Có thể tải MSG và xuất ra MHTML trong một bước không?** Không, bạn phải tải, điều chỉnh, rồi lưu.
- **Có cần giấy phép cho môi trường sản xuất không?** Có, cần giấy phép Aspose.Email hợp lệ.
- **Xử lý múi giờ có được hỗ trợ không?** Có, thông qua `setTimeZoneOffset`.
- **Có thể sử dụng trong xử lý hàng loạt không?** Chắc chắn – bao bọc các bước trong một vòng lặp.

## Aspose.Email cho Java là gì?

Aspose.Email cho Java là một API toàn diện cho phép bạn tạo, đọc, chuyển đổi và thao tác các tin nhắn email mà không cần Microsoft Outlook. Nó hỗ trợ hơn 30 định dạng email và có thể xử lý các tin nhắn có hàng trăm trang trong khi giữ mức sử dụng bộ nhớ thấp.

## Tại sao chuyển đổi MSG sang MHTML?

Chuyển đổi các tệp MSG sang MHTML cung cấp cho bạn một dạng đại diện thân thiện với web, dạng tệp đơn có thể mở trong bất kỳ trình duyệt hiện đại nào. Định dạng này bảo tồn kiểu dáng gốc, hình ảnh nhúng và tệp đính kèm, làm cho nó trở nên lý tưởng cho **lưu trữ pháp lý**, **chia sẻ đa nền tảng**, và **nhúng email vào các trang web hoặc tài liệu**.

## Yêu cầu trước

Trước khi bắt đầu, hãy chắc chắn bạn có những thứ sau:

### Thư viện và phụ thuộc cần thiết
- **Thư viện Aspose.Email cho Java** phiên bản 25.4 (jdk16 classifier) – thư viện hỗ trợ **hơn 50** định dạng email đầu vào và đầu ra.
- Kiến thức cơ bản về Java.
- Một IDE như IntelliJ IDEA hoặc Eclipse.

### Yêu cầu thiết lập môi trường
- JDK 16 hoặc mới hơn đã được cài đặt.
- Maven để quản lý phụ thuộc.

## Cài đặt Aspose.Email cho Java

Để thêm thư viện vào dự án Maven, bao gồm phụ thuộc sau:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Các bước lấy giấy phép

Bắt đầu với **bản dùng thử miễn phí** hoặc nhận **giấy phép tạm thời** để đánh giá đầy đủ khả năng của thư viện mà không bị giới hạn. Đối với việc sử dụng lâu dài, hãy cân nhắc mua giấy phép:

- [Free Trial](https://releases.aspose.com/email/java/)
- [Temporary License](https://purchase.aspose.com/temporary-license/)
- [Purchase License](https://purchase.aspose.com/buy)

### Khởi tạo cơ bản

Lớp `License` đăng ký giấy phép Aspose.Email của bạn để mở khóa đầy đủ tính năng.  
Sau khi thêm phụ thuộc, khởi tạo giấy phép trong mã Java của bạn:

```java
import com.aspose.email.License;

License license = new License();
license.setLicense("Aspose.Email.lic");
```
```java
import com.aspose.email.License;

License license = new License();
license.setLicense("path_to_your_license_file.lic");
```

## Cách tải msg và lưu dưới dạng MHTML?

Tải tệp MSG, điều chỉnh dấu thời gian, và lưu nó dưới dạng MHTML trong ba bước đơn giản. Đầu tiên, tạo một `MailMessage` từ tệp MSG bằng `MsgLoadOptions`. Tiếp theo, đặt độ lệch múi giờ mong muốn bằng `setTimeZoneOffset`. Cuối cùng, cấu hình `MhtSaveOptions` và gọi `save` để tạo ra kho lưu trữ MHTML.

### Tính năng 1: tải MailMessage từ tệp

Lớp `MailMessage` đại diện cho một tin nhắn email với các header, phần thân và tệp đính kèm.

```java
import com.aspose.email.MailMessage;
import com.aspose.email.MsgLoadOptions;
```
```java
import com.aspose.email.MailMessage;
import com.aspose.email.MsgLoadOptions;
```

```java
MsgLoadOptions loadOptions = new MsgLoadOptions();
MailMessage msg = MailMessage.load("sample.msg", loadOptions);
```
```java
String filename = "YOUR_DOCUMENT_DIRECTORY/MSG file with RTF Formatting.msg";
MailMessage msg = MailMessage.load(filename, new MsgLoadOptions());
```

`MsgLoadOptions` cho phép bạn kiểm soát cách tệp MSG được phân tích; các cài đặt mặc định hoạt động cho hầu hết các kịch bản.

### Tính năng 2: đặt ngày hiện tại và độ lệch múi giờ tùy chỉnh

Đối tượng `Date` chứa dấu thời gian sẽ được ghi vào header **Date** của email.

```java
java.util.Date now = new java.util.Date();
msg.setDate(now);
```
```java
import java.util.Date;

msg.setDate(new Date());
```

Độ lệch được biểu diễn bằng mili giây; đối với UTC+5 bạn truyền `5 * 60 * 60 * 1000`.

```java
int utcPlusFive = 5 * 60 * 60 * 1000;
msg.setTimeZoneOffset(utcPlusFive);
```
```java
msg.setTimeZoneOffset(5 * 60 * 60 * 1000); // 5 hours ahead of UTC in milliseconds.
```

### Tính năng 3: lưu MailMessage dưới dạng tệp MHTML

`MhtSaveOptions` xác định cách email được đóng gói thành kho lưu trữ MHTML, bảo tồn hình ảnh nội tuyến và tệp đính kèm.

```java
import com.aspose.email.MhtSaveOptions;
MhtSaveOptions saveOptions = new MhtSaveOptions();
saveOptions.setWriteHeader(true);
```
```java
import com.aspose.email.MhtSaveOptions;
import com.aspose.email.MhtFormatOptions;

MhtSaveOptions mhtOptions = new MhtSaveOptions();
mhtOptions.setMhtFormatOptions(MhtFormatOptions.WriteHeader);
```

```java
msg.save("output.mhtml", saveOptions);
```
```java
msg.save("YOUR_OUTPUT_DIRECTORY/ExportToMHTWithCustomTimezone_out.mhtml", mhtOptions);
```

Tệp `.mhtml` tạo ra giữ nguyên định dạng, hình ảnh và tệp đính kèm gốc, tạo ra một bản sao trực quan trung thực của MSG gốc.

## Cách đặt độ lệch múi giờ tùy chỉnh?

Bạn có thể sửa đổi múi giờ bằng cách gọi `setTimeZoneOffset` trên đối tượng `MailMessage`. Phương thức này yêu cầu một độ lệch tính bằng mili giây, cho phép cả giá trị dương (đông UTC) và âm (tây UTC). Ví dụ, UTC‑3 là `-3 * 60 * 60 * 1000`.

## Cách xử lý tệp MSG hàng loạt?

Bao bọc quy trình ba bước trong một vòng lặp duyệt qua thư mục chứa các tệp `.msg`. Tái sử dụng một thể hiện `License` duy nhất để tránh I/O lặp lại, và giải phóng mỗi `MailMessage` sau khi lưu để giữ mức sử dụng bộ nhớ thấp.

```java
File folder = new File("msg_folder");
for (File file : folder.listFiles((dir, name) -> name.toLowerCase().endsWith(".msg"))) {
    MailMessage msg = MailMessage.load(file.getAbsolutePath(), new MsgLoadOptions());
    // set date & timezone as shown earlier
    msg.save(file.getName().replace(".msg", ".mhtml"), new MhtSaveOptions());
    msg.dispose(); // releases native resources
}
```

### Mẹo xử lý hàng loạt
1. **Tái sử dụng giấy phép** – gọi `new License().setLicense(...)` một lần khi khởi động ứng dụng.
2. **Sử dụng try‑with‑resources** để tự động dọn dẹp các stream.
3. **Ghi lại lỗi** vào một tệp riêng để bạn có thể thử lại các tin nhắn gặp vấn đề sau này.
4. **Xem xét song song** với `ForkJoinPool` cho các batch lớn, nhưng đảm bảo mỗi luồng sử dụng một thể hiện `MailMessage` riêng.

## Các vấn đề thường gặp và giải pháp

- **Tăng đột biến bộ nhớ với các tệp MSG lớn** – bật streaming bằng cách sử dụng `MailMessage.load(InputStream, MsgLoadOptions)` và xử lý stream theo từng khối.
- **Dấu thời gian không chính xác** – kiểm tra đồng hồ hệ thống đã được đặt ở UTC trước khi áp dụng độ lệch, hoặc truyền rõ ràng một thể hiện `java.util.Calendar`.
- **Thiếu tệp đính kèm trong MHTML** – đảm bảo `MhtSaveOptions.setWriteHeader(true)`; điều này sẽ nhúng tệp đính kèm dưới dạng tài nguyên `cid:`.

## Câu hỏi thường gặp

**Q: Tôi có thể tải email từ các định dạng khác ngoài .msg không?**  
A: Có, Aspose.Email hỗ trợ EML, MHT, EMLX và một số định dạng khác, tổng cộng hơn 30 loại đầu vào.

**Q: Làm thế nào để xử lý các tệp email rất lớn một cách hiệu quả?**  
A: Sử dụng các API streaming (`MailMessage.load(InputStream, ...)`) để đọc và ghi dữ liệu theo từng khối, giúp tiêu thụ bộ nhớ dưới 50 MB ngay cả với các tin nhắn 500 trang.

**Q: Có thể sửa đổi các tệp đính kèm trong MailMessage không?**  
A: Chắc chắn. Bạn có thể thêm, xóa hoặc thay thế các tệp đính kèm thông qua bộ sưu tập `msg.getAttachments()`, sau đó gọi `save` để lưu các thay đổi.

**Q: Nếu độ lệch múi giờ của tôi là âm (trước UTC) thì sao?**  
A: Truyền một giá trị mili giây âm vào `setTimeZoneOffset`, ví dụ `-3 * 60 * 60 * 1000` cho UTC‑3.

**Q: Tôi có thể sử dụng Aspose.Email trong các dự án thương mại không?**  
A: Có, với điều kiện bạn có giấy phép thương mại hợp lệ. Bản dùng thử miễn phí giới hạn 20 MB cho mỗi tài liệu.

**Q: Làm thế nào để xử lý hàng ngàn tệp MSG mà không hết bộ nhớ?**  
A: Xử lý tệp theo từng batch, giải phóng mỗi `MailMessage` sau khi lưu, và sử dụng mẫu `try‑with‑resources` của Java để tự động dọn dẹp.

## Tài nguyên
- [tài liệu](https://reference.aspose.com/email/java/)
- [Tài liệu](https://reference.aspose.com/email/java/)
- [Tải thư viện](https://releases.aspose.com/email/java/)
- [Mua giấy phép](https://purchase.aspose.com/buy)
- [Bản dùng thử miễn phí](https://releases.aspose.com/email/java/)
- [Giấy phép tạm thời](https://purchase.aspose.com/temporary-license/)
- [Diễn đàn hỗ trợ](https://forum.aspose.com/c/email/10)

---

**Cập nhật lần cuối:** 2026-08-27  
**Kiểm tra với:** Aspose.Email cho Java 25.4 (jdk16 classifier)  
**Tác giả:** Aspose

## Hướng dẫn liên quan

- [Cách tải và phân tích tệp Outlook MSG bằng Aspose.Email cho Java: Hướng dẫn toàn diện](/email/java/mapi-operations/outlook-msg-aspose-email-java-guide/)
- [Maven Aspose.Email cho Java: Lưu email dưới dạng tệp MHT](/email/java/email-message-operations/save-emails-as-mht-using-aspose-email-java/)
- [Cách trích xuất tệp đính kèm từ tệp msg bằng Aspose.Email cho Java](/email/java/advanced-email-attachments/extracting-attachments-from-email-messages/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}