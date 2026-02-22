---
date: '2026-02-22'
description: Tìm hiểu cách đặt cờ theo dõi trong Outlook bằng Aspose.Email cho Java,
  bao gồm việc thiết lập, đọc và xóa cờ cho người nhận.
keywords:
- Manage Outlook follow-up flags
- Set follow-up flags in Outlook with Aspose.Email for Java
- Integrate email task management with Aspose.Email
title: Cách thiết lập cờ Theo dõi trong Outlook bằng Aspose.Email cho Java
url: /vi/java/calendar-appointments/aspose-email-java-outlook-follow-up-flags/
weight: 1
---

 code block placeholders unchanged.

Let's craft translation.

Be careful with bold formatting: keep **text** but translate inside? For example **outlook follow up flag** is English term; keep as is. So keep bold unchanged.

For bullet points, translate but keep any code names unchanged.

Proceed.

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cách Đặt Outlook Follow Up Flag bằng Aspose.Email cho Java

## Introduction
Nếu bạn từng gặp khó khăn trong việc theo dõi các email quan trọng, bạn sẽ hiểu được giá trị của **outlook follow up flag** trong Outlook. Trong hướng dẫn này, chúng tôi sẽ chỉ cho bạn **how to set an outlook follow up flag** một cách lập trình bằng Aspose.Email cho Java, đồng thời trình bày cách **set outlook follow up flag for recipients**, và cách **remove an outlook follow up flag** khi công việc đã hoàn thành. Khi kết thúc, bạn sẽ có thể tự động hoá việc theo dõi nhiệm vụ, nhắc nhở và ghi lại lịch sử trực tiếp từ mã Java của mình.

**What you’ll learn**
- Tạo và áp dụng một follow‑up flag cho một tin nhắn Outlook.  
- Đặt follow‑up flags cho các người nhận cụ thể.  
- Đánh dấu một flag là đã hoàn thành và sau đó xóa nó.  
- Đọc các tùy chọn flag để báo cáo hoặc tuân thủ.

Hãy chuẩn bị môi trường trước khi bắt đầu viết mã.

## Quick Answers
- **What does “how to set follow‑up” mean?** Thêm một flag với ngày bắt đầu, nhắc nhở và ngày đến hạn cho một mục Outlook.  
- **Which library is required?** Aspose.Email cho Java (v25.4 hoặc mới hơn).  
- **Do I need a license?** Có, cần có giấy phép dùng thử hoặc mua để sử dụng đầy đủ tính năng.  
- **Can I set flags for recipients only?** Chắc chắn – sử dụng `FollowUpManager.setFlagForRecipients`.  
- **Is it possible to remove a flag later?** Có, gọi `FollowUpManager.clearFlag`.

## What is an Outlook Follow Up Flag?
Outlook follow up flag là một dấu hiệu nhiệm vụ tích hợp sẵn, có thể gắn ngày bắt đầu, nhắc nhở và ngày đến hạn vào bất kỳ mục mail nào. Nó biến một email thông thường thành một mục hành động được theo dõi, giúp bạn và nhóm luôn nắm bắt công việc đang chờ xử lý.

## Why Use Aspose.Email for Java?
Aspose.Email cung cấp một API thuần Java hoạt động mà không cần cài đặt Outlook, cho phép bạn thao tác với các tệp .msg, đặt flag và quản lý nhiệm vụ trên bất kỳ nền tảng nào—lý tưởng cho **automate outlook tasks**, dịch vụ backend, hoặc tích hợp với các công cụ quản lý dự án.

## Prerequisites
- **Aspose.Email cho Java** phiên bản 25.4 hoặc mới hơn (còn được gọi là **aspose email java**).  
- **JDK 16+** đã được cài đặt.  
- IDE tương thích Maven (IntelliJ IDEA, Eclipse, v.v.).  
- Kiến thức cơ bản về Java và hiểu biết về các khái niệm email.

## Setting Up Aspose.Email for Java
### Maven Configuration
Thêm phụ thuộc sau vào file `pom.xml` của bạn:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### License Acquisition
Aspose.Email yêu cầu giấy phép để sử dụng trong môi trường sản xuất:

- **Free trial** – Đánh giá trong 30 ngày.  
- **Temporary license** – Kiểm thử mở rộng.  
- **Full license** – Đăng ký vĩnh viễn.

Khởi tạo giấy phép trước khi thực hiện bất kỳ thao tác email nào:

```java
License license = new License();
license.setLicense("path/to/Aspose.Total.Java.lic");
```

## Set Outlook Follow Up Flag (Feature 1)
### Step 1: Create and Initialize the Message
```java
MailMessage mailMsg = new MailMessage();
mailMsg.setSender(new MailAddress("AETest12@gmail.com"));
mailMsg.getTo().addMailAddress(new MailAddress("receiver@gmail.com"));
mailMsg.setBody("This message will test if follow up options can be added to a new mapi message.");
MapiMessage mapi = MapiMessage.fromMailMessage(mailMsg);
```
*Chúng tôi đầu tiên tạo một `MailMessage`, thiết lập người gửi/nhận, sau đó chuyển đổi nó thành `MapiMessage` để thao tác flag.*

### Step 2: Define Follow‑Up Dates (Outlook Flag Reminder)
```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 14, 40, 0);
Date dtStartDate = calendar.getTime();
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
calendar.add(Calendar.DATE, 1);
Date dtDueDate = calendar.getTime();
```
*Ở đây chúng tôi đặt ngày bắt đầu, nhắc nhở (the **outlook flag reminder**) và ngày đến hạn bằng lớp `Calendar`.*

### Step 3: Apply Follow‑Up Options
```java
FollowUpOptions options = new FollowUpOptions("Follow Up", dtStartDate, dtDueDate, dtReminderDate);
FollowUpManager.setOptions(mapi, options);
```
*Đối tượng `FollowUpOptions` chứa tất cả chi tiết flag, và chúng tôi áp dụng chúng bằng `FollowUpManager.setOptions`.*

### Step 4: Save the Message
```java
mapi.save(outputDir + "SetFollowUpflag_out.msg");
```
*Tin nhắn được lưu dưới dạng tệp `.msg` kèm theo flag đã đính.*

## How to Set Flag for Recipients (Feature 2)
### Overview
Đôi khi bạn muốn flag chỉ hiển thị **only for recipients**. Ví dụ này đánh dấu tin nhắn là bản nháp trước, sau đó thêm flag.

#### Step 1: Mark as Draft
```java
mapi.setMessageFlags(MapiMessageFlags.MSGFLAG_UNSENT);
```
*Đánh dấu tin nhắn là chưa gửi giúp Outlook xử lý nó như một bản nháp.*

#### Step 2: Set Recipient Flag
```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
FollowUpManager.setFlagForRecipients(mapi, "Follow up", dtReminderDate);
```
*Flag hiện chỉ hiển thị với người nhận – một trường hợp điển hình của **flag for recipients**.*

## How to Mark an Outlook Follow Up Flag as Completed (Feature 3)
### Step 1: Load the Message
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
```

### Step 2: Mark as Completed and Save
```java
FollowUpManager.markAsCompleted(mapi);
mapi.save(outputDir + "MarkedCompleted_out.msg");
```
*Trạng thái flag được thay đổi thành “Completed” và tệp đã cập nhật được lưu lại.*

## How to Remove an Outlook Follow Up Flag (Feature 4)
### Step 1: Load and Clear Flag
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpManager.clearFlag(mapi);
mapi.save(outputDir + "FollowUpFlagRemoved_out.msg");
```
*Tin nhắn được lưu mà không có bất kỳ follow‑up flag nào.*

## How to Read Flag Options (Feature 5)
### Step 1: Retrieve Options
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpOptions options = FollowUpManager.getOptions(mapi);
```
*Đối tượng `options` hiện chứa ngày bắt đầu, ngày đến hạn và ngày nhắc nhở, cùng với tiêu đề flag – hữu ích khi bạn cần **read flag options** để báo cáo.*

## Practical Applications
- **Task‑Management Integration:** Đồng bộ email có flag với Jira, Trello hoặc Azure Boards.  
- **Automated Reminders:** Tạo email nhắc nhở hàng ngày cho các follow‑up đang chờ.  
- **Compliance Audits:** Xuất dữ liệu flag cho báo cáo tuân thủ quy định.

## Performance Considerations
- **Date Calculations:** Tính toán ngày một lần cho mỗi lô thay vì trong vòng lặp.  
- **Resource Management:** Đóng mọi luồng hoặc handle file sau khi lưu tin nhắn.  
- **Memory Usage:** Xử lý hộp thư lớn theo từng khối để tránh áp lực lên heap.

## Common Issues and Solutions
| Issue | Cause | Fix |
|-------|-------|-----|
| Flag not appearing in Outlook | Message saved without proper `MessageFlags` | Ensure `setMessageFlags` is set to `MSGFLAG_UNSENT` before applying recipient flags. |
| Save throws `AccessDeniedException` | Incorrect file path or missing write permissions | Verify the output directory exists and the application has write rights. |
| Dates are off by one day | Time‑zone mismatch | Use `TimeZone.getTimeZone("GMT")` or your local zone consistently. |

## Frequently Asked Questions
**Q: What is Aspose.Email for Java?**  
A: It’s a pure‑Java API that lets you create, read, and manipulate email files (MSG, EML, etc.) without needing Outlook installed.

**Q: How do I obtain a free trial license?**  
A: Visit the [Aspose website](https://releases.aspose.com/email/java/) to download a 30‑day trial.

**Q: Can I set multiple follow‑up flags on a single message?**  
A: Outlook supports only one flag per message, but you can store additional task data in custom MAPI properties.

**Q: My message isn’t saved after setting a flag. What should I check?**  
A: Confirm the `outputDir` path is valid and that the application has permission to write to that location.

**Q: How can I remove flags from many messages at once?**  
A: Loop through your message collection and call `FollowUpManager.clearFlag` on each `MapiMessage`.

## Resources
- [Documentation](https://reference.aspose.com/email/java/)
- [Download Aspose.Email for Java](https://releases.aspose.com/email/java/)
- [Aspose.Email Free Trial](https://purchase.aspose.com/purchase/free-trial/aspose-email-java)

---

**Last Updated:** 2026-02-22  
**Tested With:** Aspose.Email cho Java 25.4 (jdk16)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}