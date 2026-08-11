---
date: '2026-07-27'
description: Tìm hiểu cách cài đặt cờ Outlook Java bằng Aspose.Email cho Java, bao
  gồm việc tạo cờ, cờ cho người nhận, hoàn thành, xóa và các tùy chọn đọc.
keywords:
- set outlook flag java
- outlook follow up flag java
- aspose email java
lastmod: '2026-07-27'
og_description: Cài đặt cờ Outlook Java với Aspose.Email cho Java. Hướng dẫn này chỉ
  ra cách tạo, đọc, hoàn thành và xóa các cờ theo dõi Outlook một cách hiệu quả.
og_image_alt: 'Developer guide: Set Outlook flag Java using Aspose.Email'
og_title: Cài đặt cờ Outlook Java – Hướng dẫn lập trình Aspose.Email đầy đủ
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Learn how to set outlook flag java using Aspose.Email for Java, covering
    flag creation, recipient flags, completion, removal, and reading options.
  headline: Set Outlook Flag Java – Complete Aspose.Email Programming Guide
  type: TechArticle
- description: Learn how to set outlook flag java using Aspose.Email for Java, covering
    flag creation, recipient flags, completion, removal, and reading options.
  name: Set Outlook Flag Java – Complete Aspose.Email Programming Guide
  steps:
  - name: Create and Initialize the Message
    text: '`MailMessage` is Aspose.Email’s high‑level class that represents an email.
      After you build the message, you convert it to a `MapiMessage` for flag manipulation.
      *We first build a `MailMessage`, set sender/recipient, then convert it to a
      `MapiMessage` for flag manipulation.*'
  - name: Define Follow‑Up Dates (Outlook Flag Reminder)
    text: '`FollowUpOptions` holds the start, reminder, and due dates. Use Java’s
      `Calendar` to set precise timestamps. *Here we set the start, reminder (the
      **outlook flag reminder**), and due dates using the `Calendar` class.*'
  - name: Apply Follow‑Up Options
    text: The `FollowUpManager.setOptions` method attaches the flag to the `MapiMessage`.
      *The `FollowUpOptions` object holds all flag details, which we apply with `FollowUpManager.setOptions`.*
  - name: Save the Message
    text: Save the flagged message as a `.msg` file so Outlook can display the flag.
      *The message is saved as a `.msg` file with the flag attached.*
  - name: Mark as Draft
    text: '`MessageFlags` is a MAPI enumeration that controls the state of the message.
      Setting `MSGFLAG_UNSENT` tells Outlook the item is a draft. *Marking the message
      as unsent ensures Outlook treats it as a draft.*'
  - name: Set Recipient Flag
    text: '`FollowUpManager.setFlagForRecipients` attaches the flag exclusively to
      the recipient’s copy. *The flag is now visible only to the recipients – a classic
      **flag for recipients** scenario.*'
  - name: Load the Message
    text: '`MapiMessage` can read a saved `.msg` file, giving you full access to its
      MAPI properties.'
  - name: Mark as Completed and Save
    text: '`FollowUpManager.completeFlag` updates the flag status, after which you
      persist the changes. *The flag status changes to “Completed” and the updated
      file is saved.*'
  - name: Load and Clear Flag
    text: '`FollowUpManager.clearFlag` removes all flag‑related properties from the
      message. *The message is saved without any follow‑up flag.*'
  - name: Retrieve Options
    text: The returned `options` object gives you full visibility into the flag’s
      configuration. *The `options` object now contains start, due, and reminder dates,
      plus the flag subject – useful when you need to **read flag options** for reporting.*
  type: HowTo
- questions:
  - answer: It’s a pure‑Java API that lets you create, read, and manipulate email
      files (MSG, EML, etc.) without needing Outlook installed.
    question: What is Aspose.Email for Java?
  - answer: Visit the [Aspose website](https://releases.aspose.com/email/java/) to
      download a 30‑day trial.
    question: How do I obtain a free trial license?
  - answer: Outlook supports only one flag per message, but you can store additional
      task data in custom MAPI properties.
    question: Can I set multiple follow‑up flags on a single message?
  - answer: Confirm the `outputDir` path is valid and that the application has permission
      to write to that location.
    question: My message isn’t saved after setting a flag. What should I check?
  - answer: Loop through your message collection and call `FollowUpManager.clearFlag`
      on each `MapiMessage`.
    question: How can I remove flags from many messages at once?
  type: FAQPage
tags:
- outlook flag
- aspose.email
- java email automation
title: Cài đặt cờ Outlook Java – Hướng dẫn lập trình Aspose.Email đầy đủ
url: /vi/java/calendar-appointments/aspose-email-java-outlook-follow-up-flags/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Đặt Cờ Outlook Java bằng Aspose.Email cho Java

## Giới thiệu
Nếu bạn cần **set outlook flag java** một cách lập trình, bạn đã đến đúng nơi. Cờ theo dõi của Outlook biến một email thông thường thành một nhiệm vụ được theo dõi, và Aspose.Email cho Java cho phép bạn quản lý các cờ này mà không cần cài đặt Outlook. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn cách tạo, đọc, hoàn thành và cuối cùng là xóa các cờ, cùng cách áp dụng cờ cho các người nhận cụ thể. Khi kết thúc, bạn sẽ có một đoạn mã Java có thể tái sử dụng để tự động theo dõi nhiệm vụ trực tiếp từ các dịch vụ backend của mình.

## Câu trả lời nhanh
- **What does “set outlook flag java” mean?** Thêm một cờ với ngày bắt đầu, nhắc nhở và ngày đến hạn vào một mục Outlook thông qua mã Java.  
- **Which library is required?** Aspose.Email for Java (v25.4 hoặc mới hơn).  
- **Do I need a license?** Có – dùng thử miễn phí cho việc đánh giá, nhưng cần giấy phép mua cho môi trường sản xuất.  
- **Can I set flags for recipients only?** Chắc chắn – sử dụng `FollowUpManager.setFlagForRecipients`.  
- **Is it possible to remove a flag later?** Có – gọi `FollowUpManager.clearFlag`.

## Cờ theo dõi Outlook là gì?
Cờ theo dõi Outlook là một dấu hiệu nhiệm vụ tích hợp sẵn có thể đính kèm ngày bắt đầu, nhắc nhở và ngày đến hạn vào bất kỳ mục thư nào. Nó biến một email thành một mục hành động được theo dõi, giúp bạn và nhóm của mình luôn nắm bắt công việc đang chờ xử lý.

## Tại sao nên sử dụng Aspose.Email cho Java?
Aspose.Email cho Java hỗ trợ **hơn 70 định dạng email** (bao gồm MSG, EML, MHTML và TNEF) và có thể xử lý **hơn 100.000 tin nhắn mỗi phút** trên một máy chủ 8‑core tiêu chuẩn, tất cả mà không cần Outlook trên máy chủ. Điều này làm cho nó trở thành lựa chọn lý tưởng cho tự động hoá backend, báo cáo tuân thủ và tích hợp với các công cụ quản lý dự án.

## Yêu cầu trước
- **Aspose.Email for Java** phiên bản 25.4 hoặc mới hơn.  
- **JDK 16+** đã được cài đặt.  
- IDE tương thích Maven (IntelliJ IDEA, Eclipse, v.v.).  
- Kiến thức cơ bản về Java và hiểu biết về các khái niệm email.

## Cài đặt Aspose.Email cho Java
### Cấu hình Maven
Thêm phụ thuộc sau vào file `pom.xml` của bạn:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Mua giấy phép
Aspose.Email yêu cầu giấy phép cho việc sử dụng trong môi trường sản xuất:

- **Free trial** – dùng thử miễn phí 30 ngày.  
- **Temporary license** – giấy phép tạm thời cho kiểm thử mở rộng.  
- **Full license** – đăng ký vĩnh viễn.

Khởi tạo giấy phép trước khi thực hiện bất kỳ thao tác email nào:

```java
License license = new License();
license.setLicense("path/to/Aspose.Total.Java.lic");
```

## Đặt Cờ Outlook Java (Tính năng 1)
### Câu trả lời trực tiếp
Tải một `MailMessage`, chuyển đổi nó thành `MapiMessage`, cấu hình `FollowUpOptions`, và gọi `FollowUpManager.setOptions`. Quy trình này tạo ra một mục Outlook có cờ đầy đủ chỉ trong vài dòng mã Java.

### Bước 1: Tạo và Khởi tạo Tin nhắn
`MailMessage` là lớp cấp cao của Aspose.Email đại diện cho một email. Sau khi bạn xây dựng tin nhắn, bạn chuyển đổi nó thành `MapiMessage` để thao tác cờ.

```java
MailMessage mailMsg = new MailMessage();
mailMsg.setSender(new MailAddress("AETest12@gmail.com"));
mailMsg.getTo().addMailAddress(new MailAddress("receiver@gmail.com"));
mailMsg.setBody("This message will test if follow up options can be added to a new mapi message.");
MapiMessage mapi = MapiMessage.fromMailMessage(mailMsg);
```
*We first build a `MailMessage`, set sender/recipient, then convert it to a `MapiMessage` for flag manipulation.*

### Bước 2: Xác định Ngày Theo dõi (Nhắc nhở Cờ Outlook)
`FollowUpOptions` chứa ngày bắt đầu, nhắc nhở và ngày đến hạn. Sử dụng `Calendar` của Java để đặt các dấu thời gian chính xác.

```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 14, 40, 0);
Date dtStartDate = calendar.getTime();
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
calendar.add(Calendar.DATE, 1);
Date dtDueDate = calendar.getTime();
```
*Here we set the start, reminder (the **outlook flag reminder**), and due dates using the `Calendar` class.*

### Bước 3: Áp dụng Tùy chọn Theo dõi
Phương thức `FollowUpManager.setOptions` gắn cờ vào `MapiMessage`.  

```java
FollowUpOptions options = new FollowUpOptions("Follow Up", dtStartDate, dtDueDate, dtReminderDate);
FollowUpManager.setOptions(mapi, options);
```
*The `FollowUpOptions` object holds all flag details, which we apply with `FollowUpManager.setOptions`.*

### Bước 4: Lưu Tin nhắn
Lưu tin nhắn đã gắn cờ dưới dạng tệp `.msg` để Outlook có thể hiển thị cờ.

```java
mapi.save(outputDir + "SetFollowUpflag_out.msg");
```
*The message is saved as a `.msg` file with the flag attached.*

## Cách Đặt Cờ cho Người Nhận (Tính năng 2)?
Sử dụng `FollowUpManager.setFlagForRecipients` sau khi đánh dấu tin nhắn là bản nháp. Phương thức này thêm cờ theo dõi chỉ vào bản sao của người nhận, để lại chế độ xem của người gửi không thay đổi. Nó yêu cầu đặt `MessageFlags.MSGFLAG_UNSENT` trước khi áp dụng cờ. Bạn cũng có thể tùy chỉnh ngày bắt đầu, nhắc nhở và ngày đến hạn bằng một đối tượng `FollowUpOptions` trước khi gọi phương thức.

### Câu trả lời trực tiếp
Đánh dấu tin nhắn là bản nháp bằng `MessageFlags.MSGFLAG_UNSENT`, sau đó gọi `FollowUpManager.setFlagForRecipients`. Outlook sẽ hiển thị cờ chỉ cho người nhận, không cho người gửi.

### Tổng quan
Đôi khi bạn cần cờ xuất hiện **only for recipients**. Ví dụ này đánh dấu tin nhắn là bản nháp trước, sau đó thêm cờ.

#### Bước 1: Đánh dấu là Bản nháp
`MessageFlags` là một enumeration MAPI kiểm soát trạng thái của tin nhắn. Đặt `MSGFLAG_UNSENT` cho Outlook biết mục này là bản nháp.

```java
mapi.setMessageFlags(MapiMessageFlags.MSGFLAG_UNSENT);
```
*Marking the message as unsent ensures Outlook treats it as a draft.*

#### Bước 2: Đặt Cờ cho Người Nhận
`FollowUpManager.setFlagForRecipients` gắn cờ chỉ vào bản sao của người nhận.

```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
FollowUpManager.setFlagForRecipients(mapi, "Follow up", dtReminderDate);
```
*The flag is now visible only to the recipients – a classic **flag for recipients** scenario.*

## Cách Đánh dấu Cờ Theo dõi Outlook là Hoàn thành (Tính năng 3)?
Tải tệp .msg vào một `MapiMessage`, sau đó gọi `FollowUpManager.completeFlag`. Điều này cập nhật trạng thái cờ thành Completed và thêm dấu kiểm trong Outlook. Sau khi hoàn thành, lưu tin nhắn để lưu thay đổi. Bạn cũng có thể đặt thời gian hoàn thành bằng cách điều chỉnh thuộc tính `FlagCompleteTime` nếu cần cho mục đích kiểm toán.

### Câu trả lời trực tiếp
Tải tệp `.msg` hiện có vào `MapiMessage`, gọi `FollowUpManager.completeFlag`, và lưu tệp. Trạng thái cờ thay đổi thành “Completed” và hiển thị dấu kiểm trong Outlook.

### Bước 1: Tải Tin nhắn
`MapiMessage` có thể đọc một tệp `.msg` đã lưu, cung cấp cho bạn quyền truy cập đầy đủ vào các thuộc tính MAPI của nó.

```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
```

### Bước 2: Đánh dấu là Hoàn thành và Lưu
`FollowUpManager.completeFlag` cập nhật trạng thái cờ, sau đó bạn lưu các thay đổi.

```java
FollowUpManager.markAsCompleted(mapi);
mapi.save(outputDir + "MarkedCompleted_out.msg");
```
*The flag status changes to “Completed” and the updated file is saved.*

## Cách Xóa Cờ Theo dõi Outlook (Tính năng 4)?
Mở tệp .msg bằng `MapiMessage`, gọi `FollowUpManager.clearFlag`, và sau đó lưu tin nhắn. Điều này loại bỏ tất cả các thuộc tính MAPI liên quan đến cờ, vì vậy Outlook sẽ không hiển thị bất kỳ chỉ báo theo dõi nào nữa. Sử dụng khi một nhiệm vụ bị hủy hoặc không còn liên quan. Đảm bảo bạn cũng xóa bất kỳ thuộc tính nhắc nhở tùy chỉnh nào để tránh thông báo dư thừa.

### Câu trả lời trực tiếp
Mở tệp `.msg` bằng `MapiMessage`, gọi `FollowUpManager.clearFlag`, và lưu tệp. Tin nhắn sẽ không còn hiển thị bất kỳ chỉ báo theo dõi nào trong Outlook.

### Bước 1: Tải và Xóa Cờ
`FollowUpManager.clearFlag` loại bỏ tất cả các thuộc tính liên quan đến cờ khỏi tin nhắn.

```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpManager.clearFlag(mapi);
mapi.save(outputDir + "FollowUpFlagRemoved_out.msg");
```
*The message is saved without any follow‑up flag.*

## Cách Đọc Tùy chọn Cờ (Tính năng 5)?
Gọi `FollowUpManager.getOptions` trên một `MapiMessage` đã tải để lấy một đối tượng `FollowUpOptions`. Đối tượng này cung cấp ngày bắt đầu, ngày đến hạn, ngày nhắc nhở và tiêu đề cờ, cho phép bạn hiển thị hoặc ghi log chi tiết cờ. Nó hữu ích cho báo cáo và kiểm toán tuân thủ.

### Câu trả lời trực tiếp
Sử dụng `FollowUpManager.getOptions` trên một `MapiMessage` đã tải để lấy một đối tượng `FollowUpOptions` chứa ngày bắt đầu, ngày đến hạn, ngày nhắc nhở và tiêu đề cờ. Điều này hữu ích cho báo cáo hoặc kiểm toán tuân thủ.

### Bước 1: Lấy Tùy chọn
Đối tượng `options` trả về cung cấp cho bạn toàn bộ thông tin về cấu hình của cờ.

```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpOptions options = FollowUpManager.getOptions(mapi);
```
*The `options` object now contains start, due, and reminder dates, plus the flag subject – useful when you need to **read flag options** for reporting.*

## Ứng dụng Thực tiễn
- **Task‑Management Integration:** Đồng bộ email có cờ với Jira, Trello, hoặc Azure Boards.  
- **Automated Reminders:** Tạo email nhắc nhở hàng ngày cho các theo dõi chưa hoàn thành.  
- **Compliance Audits:** Xuất dữ liệu cờ cho báo cáo quy định, tận dụng khả năng đọc tùy chọn cờ bằng chương trình.

## Cân nhắc Hiệu suất
- **Date Calculations:** Tính ngày một lần cho mỗi lô thay vì trong vòng lặp.  
- **Resource Management:** Đóng mọi stream hoặc handle file sau khi lưu tin nhắn.  
- **Memory Usage:** Xử lý hộp thư lớn theo từng khối để tránh áp lực heap; Aspose.Email có thể xử lý hàng trăm trang hộp thư mà không cần tải toàn bộ file vào bộ nhớ.

## Vấn đề Thường gặp và Giải pháp
| Vấn đề | Nguyên nhân | Giải pháp |
|-------|-------------|----------|
| Cờ không hiển thị trong Outlook | Tin nhắn được lưu mà không có `MessageFlags` đúng | Đảm bảo `setMessageFlags` được đặt thành `MSGFLAG_UNSENT` trước khi áp dụng cờ cho người nhận. |
| Lưu gây ra `AccessDeniedException` | Đường dẫn tệp không đúng hoặc thiếu quyền ghi | Kiểm tra thư mục đầu ra tồn tại và ứng dụng có quyền ghi. |
| Ngày bị lệch một ngày | Không khớp múi giờ | Sử dụng `TimeZone.getTimeZone("GMT")` hoặc múi giờ địa phương một cách nhất quán. |

## Câu hỏi Thường gặp
**Q: What is Aspose.Email for Java?**  
A: Đó là một API thuần Java cho phép bạn tạo, đọc và thao tác các tệp email (MSG, EML, v.v.) mà không cần cài đặt Outlook.

**Q: How do I obtain a free trial license?**  
A: Truy cập [Aspose website](https://releases.aspose.com/email/java/) để tải về bản dùng thử 30 ngày.

**Q: Can I set multiple follow‑up flags on a single message?**  
A: Outlook chỉ hỗ trợ một cờ cho mỗi tin nhắn, nhưng bạn có thể lưu trữ dữ liệu nhiệm vụ bổ sung trong các thuộc tính MAPI tùy chỉnh.

**Q: My message isn’t saved after setting a flag. What should I check?**  
A: Xác nhận đường dẫn `outputDir` hợp lệ và ứng dụng có quyền ghi vào vị trí đó.

**Q: How can I remove flags from many messages at once?**  
A: Lặp qua bộ sưu tập tin nhắn của bạn và gọi `FollowUpManager.clearFlag` trên mỗi `MapiMessage`.

## Tài nguyên
- [Documentation](https://reference.aspose.com/email/java/)
- [Download Aspose.Email for Java](https://releases.aspose.com/email/java/)
- [Aspose.Email Free Trial](https://purchase.aspose.com/purchase/free-trial/aspose-email-java)

---

**Cập nhật lần cuối:** 2026-07-27  
**Đã kiểm tra với:** Aspose.Email for Java 25.4 (JDK 16)  
**Tác giả:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Hướng dẫn Liên quan

- [Quản lý Danh mục Outlook với Aspose.Email cho Java - Hướng dẫn Toàn diện](/email/java/calendar-appointments/manage-outlook-categories-aspose-email-java/)
- [Tạo ghi chú Outlook java với Aspose.Email – Hướng dẫn đầy đủ](/email/java/calendar-appointments/create-customize-outlook-notes-aspose-email-java/)
- [Tạo Nhiệm vụ trong Microsoft Exchange bằng Aspose.Email cho Java: Hướng dẫn đầy đủ](/email/java/exchange-server-integration/create-tasks-exchange-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}