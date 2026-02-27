---
date: '2026-02-27'
description: Tìm hiểu cách tải tệp MSG và chuyển đổi chúng sang MHTML bằng Aspose.Email
  cho Java, bao gồm cài đặt múi giờ tùy chỉnh và các mẹo xử lý email hàng loạt.
keywords:
- Aspose.Email for Java
- load emails in MHTML format
- custom timezone settings
title: Cách tải MSG và lưu dưới dạng MHTML bằng Aspose.Email cho Java
url: /vi/java/email-message-operations/load-save-emails-mhtml-aspose-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cách tải MSG và lưu dưới dạng MHTML bằng Aspose.Email cho Java

## Introduction

Nếu bạn cần **how to load msg** các tệp, điều chỉnh dấu thời gian của chúng, và sau đó **convert msg to mhtml**, bạn đang ở đúng nơi. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn cách tải một email `.msg`, áp dụng độ lệch múi giờ tùy chỉnh, và lưu kết quả dưới dạng một kho lưu trữ MHTML — tất cả đều sử dụng Aspose.Email cho Java. Dù bạn đang xử lý một tin nhắn duy nhất hay một quy trình **batch email processing**, các bước này sẽ cung cấp nền tảng vững chắc.

**What you’ll learn**
- Cách tải một `MailMessage` từ tệp `.msg`.
- Cách đặt múi giờ tùy chỉnh và ngày hiện tại.
- Cách lưu tin nhắn dưới dạng MHTML với định dạng chính xác.
- Mẹo mở rộng cách tiếp cận cho các kịch bản batch.

Ready to boost your email workflow? Let’s get the environment ready first.

## Quick Answers
- **What is the primary library?** Aspose.Email for Java.
- **Can I load MSG and export to MHTML in one step?** No, you load, adjust, then save.
- **Do I need a license for production?** Yes, a valid Aspose.Email license is required.
- **Is timezone handling supported?** Yes, via `setTimeZoneOffset`.
- **Can this be used in batch processing?** Absolutely – wrap the steps in a loop.

## Prerequisites

Trước khi bắt đầu, hãy chắc chắn bạn có những thứ sau:

### Required Libraries and Dependencies
- Thư viện **Aspose.Email for Java** phiên bản 25.4 (jdk16 classifier)
- Kiến thức cơ bản về Java.
- Một IDE như IntelliJ IDEA hoặc Eclipse.

### Environment Setup Requirements
- JDK 16 hoặc mới hơn đã được cài đặt.
- Maven để quản lý phụ thuộc.

## Setting Up Aspose.Email for Java

Để thêm thư viện vào dự án Maven, bao gồm phụ thuộc sau:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### License Acquisition Steps

Bắt đầu với một **free trial** hoặc lấy một **temporary license** để đánh giá đầy đủ khả năng của thư viện mà không có giới hạn. Đối với việc sử dụng lâu dài, hãy cân nhắc mua giấy phép:

- [Free Trial](https://releases.aspose.com/email/java/)
- [Temporary License](https://purchase.aspose.com/temporary-license/)
- [Purchase License](https://purchase.aspose.com/buy)

### Basic Initialization

Sau khi thêm phụ thuộc, khởi tạo giấy phép trong mã Java của bạn:

```java
import com.aspose.email.License;

License license = new License();
license.setLicense("path_to_your_license_file.lic");
```

## Implementation Guide

Chúng tôi sẽ chia triển khai thành ba tính năng rõ ràng.

### Feature 1: Loading a MailMessage from a File

#### Overview
Tải một tệp `.msg` cho phép bạn truy cập đầy đủ về lập trình tới nội dung email, tệp đính kèm và siêu dữ liệu.

#### Step‑by‑Step

**Import the required classes**

```java
import com.aspose.email.MailMessage;
import com.aspose.email.MsgLoadOptions;
```

**Load the email**

```java
String filename = "YOUR_DOCUMENT_DIRECTORY/MSG file with RTF Formatting.msg";
MailMessage msg = MailMessage.load(filename, new MsgLoadOptions());
```

`MsgLoadOptions` lets you control how the MSG file is interpreted; the default settings work for most scenarios.

### Feature 2: Setting the Current Date and Custom Timezone Offset

#### Overview
Accurate timestamps are essential when you’re dealing with users across different regions.

**Set the current date**

```java
import java.util.Date;

msg.setDate(new Date());
```

**Apply a custom timezone offset (e.g., UTC+5)**

```java
msg.setTimeZoneOffset(5 * 60 * 60 * 1000); // 5 hours ahead of UTC in milliseconds.
```

The offset is expressed in milliseconds, so you can also pass negative values for zones west of UTC.

### Feature 3: Saving a MailMessage as an MHTML File

#### Overview
MHTML bundles HTML content and embedded resources into a single file, perfect for archiving or sharing.

**Configure save options**

```java
import com.aspose.email.MhtSaveOptions;
import com.aspose.email.MhtFormatOptions;

MhtSaveOptions mhtOptions = new MhtSaveOptions();
mhtOptions.setMhtFormatOptions(MhtFormatOptions.WriteHeader);
```

**Save the email**

```java
msg.save("YOUR_OUTPUT_DIRECTORY/ExportToMHTWithCustomTimezone_out.mhtml", mhtOptions);
```

The resulting `.mhtml` file retains the original formatting, images, and attachments.

## Why Convert MSG to MHTML?

Converting MSG files to MHTML gives you a web‑friendly, single‑file representation that can be opened in any modern browser. This is especially useful for:

- **Legal archiving** where a faithful visual copy is required.
- **Cross‑platform sharing** without needing Outlook.
- **Embedding emails** into web pages or documentation.

## Batch Email Processing Tips

If you need to **batch email processing**, wrap the loading, timezone adjustment, and saving steps inside a loop that iterates over a directory of `.msg` files. Remember to:

1. Reuse a single `License` instance to avoid overhead.
2. Release resources after each iteration (`msg.dispose()` if applicable).
3. Log any failures to a separate file for later review.

## Practical Applications

1. **Email Archiving:** Preserve communications in a portable format for compliance.
2. **Global Scheduling:** Adjust timestamps to a unified timezone before sending notifications.
3. **CRM Integration:** Automatically import archived emails into a CRM system as MHTML attachments.

## Performance Considerations

- **Memory Management:** Process large batches in chunks to keep memory usage low.
- **I/O Optimization:** Use buffered streams if you’re reading/writing many files.
- **Parallel Execution:** Consider Java’s `ForkJoinPool` for parallel processing, but ensure thread‑safety of the Aspose objects.

## Conclusion

You now know **how to load msg** files, apply custom timezone offsets, and **convert msg to mhtml** using Aspose.Email for Java. These techniques can be scaled to handle **batch email processing** tasks, giving you a robust solution for email archiving, migration, and automation.

**Next Steps**  
Explore additional Aspose.Email features such as attachment handling, calendar item extraction, or SMTP sending by visiting the official [documentation](https://reference.aspose.com/email/java/).

## Frequently Asked Questions

**Q: Can I load emails from formats other than .msg?**  
A: Yes, Aspose.Email supports EML, MSG, MHT, and several other formats.

**Q: How can I handle very large email files efficiently?**  
A: Use streaming APIs provided by Aspose.Email to read/write data in chunks, reducing memory pressure.

**Q: Is it possible to modify attachments within a MailMessage?**  
A: Absolutely. You can add, remove, or replace attachments via the `MailMessage.getAttachments()` collection.

**Q: What if my timezone offset is negative (behind UTC)?**  
A: Pass a negative millisecond value to `setTimeZoneOffset`, e.g., `-3 * 60 * 60 * 1000` for UTC‑3.

**Q: Can I use Aspose.Email in commercial projects?**  
A: Yes, provided you have a valid commercial license.

**Q: How do I process thousands of MSG files without running out of memory?**  
A: Process files in batches, release each `MailMessage` after saving, and consider using Java’s `try‑with‑resources` pattern for automatic cleanup.

---

**Last Updated:** 2026-02-27  
**Tested With:** Aspose.Email for Java 25.4 (jdk16 classifier)  
**Author:** Aspose  

## Resources
- [Documentation](https://reference.aspose.com/email/java/)
- [Download Library](https://releases.aspose.com/email/java/)
- [Purchase License](https://purchase.aspose.com/buy)
- [Free Trial](https://releases.aspose.com/email/java/)
- [Temporary License](https://purchase.aspose.com/temporary-license/)
- [Support Forum](https://forum.aspose.com/c/email/10)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}