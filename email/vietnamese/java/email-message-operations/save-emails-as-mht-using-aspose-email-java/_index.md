---
date: '2026-09-22'
description: Tìm hiểu cách sử dụng giấy phép Aspose.Email cùng Maven để lưu email
  dưới dạng tệp MHT trong Java. Bao gồm cài đặt, mẫu tùy chỉnh và xử lý sự kiện lịch.
keywords:
- aspose email license
- how to save mht
- how to convert mht
- maven dependency aspose email
lastmod: '2026-09-22'
og_description: Tìm hiểu cách sử dụng giấy phép Aspose.Email cùng Maven để lưu email
  dưới dạng tệp MHT trong Java. Bao gồm cài đặt, mẫu tùy chỉnh và hỗ trợ lịch.
og_image_alt: 'Tutorial: saving emails as MHT using Aspose.Email for Java with a license'
og_title: Cách sử dụng giấy phép Aspose.Email để lưu email dưới dạng MHT
schemas:
- author: Aspose
  dateModified: '2026-09-22'
  description: Learn how to use an Aspose.Email license with Maven to save emails
    as MHT files in Java. Includes setup, custom templates, and calendar event handling.
  headline: How to use an Aspose.Email license to save emails as MHT
  type: TechArticle
- description: Learn how to use an Aspose.Email license with Maven to save emails
    as MHT files in Java. Includes setup, custom templates, and calendar event handling.
  name: How to use an Aspose.Email license to save emails as MHT
  steps:
  - name: '**Free trial** – download from [Releases](https://releases.aspose.com/email/java/)
      and explore features without limitations.'
    text: '**Free trial** – download from [Releases](https://releases.aspose.com/email/java/)
      and explore features without limitations.'
  - name: '**Temporary license** – request a fully functional version via the [Temporary
      License Page](https://purchase.aspose.com/temporary-license/).'
    text: '**Temporary license** – request a fully functional version via the [Temporary
      License Page](https://purchase.aspose.com/temporary-license/).'
  - name: '**Purchase** – obtain a permanent license for long‑term projects.'
    text: '**Purchase** – obtain a permanent license for long‑term projects.'
  type: HowTo
- questions:
  - answer: Configure `MhtSaveOptions` to embed attachments; the library automatically
      includes them in the MHT package.
    question: How do I handle attachments when saving emails as MHT?
  - answer: Yes, use `MhtFormatOptions.WriteHeader` and provide custom template strings
      for each header field.
    question: Can I customize email headers in the output MHT file?
  - answer: A JDK 16 or higher is required. The library works with any IDE that supports
      Maven projects.
    question: What are the system requirements for using Aspose.Email Java?
  - answer: While MHT typically contains the full message, you can manipulate `MailMessage`
      properties to exclude unwanted sections before saving.
    question: Is it possible to save only specific parts of an email message?
  - answer: Verify file paths, ensure the license is correctly applied, and consult
      the Aspose.Email [support forum](https://forum.aspose.com/c/email/10) for detailed
      assistance.
    question: How can I troubleshoot issues with email loading or saving?
  type: FAQPage
tags:
- aspose email
- mht conversion
- java email processing
- maven
title: Cách sử dụng giấy phép Aspose.Email để lưu email dưới dạng MHT
url: /vi/java/email-message-operations/save-emails-as-mht-using-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách sử dụng giấy phép Aspose.Email để lưu email dưới dạng MHT

## Giới thiệu

Quản lý dữ liệu email một cách hiệu quả có thể là thách thức, đặc biệt khi nói đến việc chia sẻ và lưu trữ. Trong hướng dẫn này, chúng tôi sẽ chỉ cho bạn **cách lưu tệp MHT bằng Maven Aspose.Email cho Java với giấy phép Aspose.Email**, để bạn có thể chuyển đổi email sang MHT với các mẫu tùy chỉnh và giữ nguyên các sự kiện lịch. Bạn sẽ có một giải pháp sẵn sàng chạy trong bất kỳ môi trường Java 16+ nào và tuân thủ các yêu cầu cấp phép cho việc sử dụng trong sản xuất.

## Câu trả lời nhanh
- **Thư viện nào tôi cần?** Maven Aspose.Email cho Java (v25.4+).  
- **Định dạng nào được tạo ra?** Tệp MHT (MHTML) chứa HTML, hình ảnh và dữ liệu lịch.  
- **Tôi có thể tùy chỉnh tiêu đề không?** Có – sử dụng `MhtFormatOptions` và các chuỗi mẫu.  
- **Tôi có cần giấy phép không?** Cần giấy phép Aspose.Email cho môi trường sản xuất; bản dùng thử miễn phí hoạt động cho việc đánh giá.  
- **Phiên bản Java nào được yêu cầu?** JDK 16 hoặc mới hơn.  

## Maven Aspose.Email cho Java là gì?

Maven Aspose.Email cho Java là một thư viện cung cấp API toàn diện để tạo, đọc, chuyển đổi và thao tác các tin nhắn email trực tiếp từ mã Java. Nó hỗ trợ hơn 30 định dạng email—bao gồm MSG, EML và MHT—cho phép bạn xử lý hầu hết mọi tệp email mà bạn gặp.

## Tại sao chuyển đổi email sang MHT?

Tệp MHT nhúng tất cả tài nguyên (HTML, hình ảnh, dữ liệu lịch) vào một tệp duy nhất, cho phép chúng được xem ngay lập tức trong bất kỳ trình duyệt hiện đại nào mà không cần tài nguyên bên ngoài. Định dạng này giữ nguyên giao diện gốc, hỗ trợ các sự kiện lịch định kỳ và giảm nguy cơ mất tệp đính kèm khi chia sẻ.

## Yêu cầu trước
- **Aspose.Email cho Java** (artifact Maven `com.aspose:aspose-email:25.4` với classifier `jdk16`).  
- **Maven** đã được cài đặt và cấu hình trên máy của bạn.  
- **JDK 16+** (thư viện nhắm tới Java 16).  
- Tệp giấy phép **Aspose.Email** hợp lệ cho việc sử dụng trong môi trường sản xuất.  
- Kiến thức cơ bản về Java (xử lý tệp, phụ thuộc Maven).

## Cài đặt Aspose.Email cho Java

### Phụ thuộc Maven

Thêm phụ thuộc sau vào tệp `pom.xml` của bạn:

```xml
<dependency>
  <groupId>com.aspose</groupId>
  <artifactId>aspose-email</artifactId>
  <version>25.4</version>
  <classifier>jdk16</classifier>
</dependency>
```

### Cách lấy giấy phép

Aspose cung cấp bản dùng thử miễn phí để khám phá các tính năng, cùng với các tùy chọn mua giấy phép hoặc nhận giấy phép tạm thời.

1. **Bản dùng thử miễn phí** – tải xuống từ [Releases](https://releases.aspose.com/email/java/) và khám phá các tính năng không giới hạn.  
2. **Giấy phép tạm thời** – yêu cầu phiên bản đầy đủ chức năng qua [Temporary License Page](https://purchase.aspose.com/temporary-license/).  
3. **Mua** – nhận giấy phép vĩnh viễn cho các dự án dài hạn.

### Khởi tạo cơ bản

Sau khi cài đặt, khởi tạo thư viện trong ứng dụng Java của bạn:

```java
import com.aspose.email.License;

License license = new License();
license.setLicense("path/to/your/license/file");
```

Với các bước này đã hoàn tất, bạn đã sẵn sàng sử dụng các tính năng của Aspose.Email để xử lý email một cách hiệu quả.

## Hướng dẫn triển khai

### Tính năng 1: tải MailMessage

#### Tổng quan

`MailMessage` là đối tượng cốt lõi của Aspose.Email đại diện cho một email, bao gồm tiêu đề, nội dung, tệp đính kèm và các sự kiện lịch.

#### Các bước thực hiện

**Import required classes**

```java
import com.aspose.email.MailMessage;
```

**Load email from file**

```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY" + "/email/";
MailMessage msg = MailMessage.load(dataDir + "Meeting with Recurring Occurrences.msg");
```

Đoạn mã này tải một tin nhắn email nằm trong thư mục bạn chỉ định.

### Tính năng 2: cấu hình MhtSaveOptions

#### Tổng quan

`MhtSaveOptions` cấu hình cách Aspose.Email lưu `MailMessage` dưới dạng tệp MHT, điều khiển các cờ định dạng, mẫu và việc nhúng tài nguyên. Cấu hình đúng cho phép bạn nhúng tiêu đề, hiển thị sự kiện lịch và nhúng tất cả hình ảnh.

#### Các bước thực hiện

**Import required classes**

```java
import com.aspose.email.MhtSaveOptions;
import com.aspose.email.MhtFormatOptions;
import com.aspose.email.MhtTemplateName;
```

**Set save options and templates**

```java
MhtSaveOptions options = new MhtSaveOptions();
options.setMhtFormatOptions(MhtFormatOptions.WriteHeader | MhtFormatOptions.RenderCalendarEvent);

// Customize templates for email properties
for (Map.Entry<MhtTemplateName, String> entry : options.getFormatTemplates().entrySet()) {
    switch (entry.getKey()) {
        case START:
            options.getFormatTemplates().set_Item(MhtTemplateName.START,
                    "<span class='headerLineTitle'>Start:</span><span class='headerLineText'>{0}</span><br/>");
            break;
        // Add other cases similarly...
    }
}

// Ensure entries are added if absent
options.getFormatTemplates().addIfAbsent(MhtTemplateName.START,
            "<span class='headerLineTitle'>Start:</span><span class='headerLineText'>{0}</span><br/>");
```

Cấu hình này thiết lập tiêu đề và việc hiển thị sự kiện lịch trong đầu ra MHT.

### Tính năng 3: lưu MailMessage dưới dạng MHT

#### Tổng quan

Lưu `MailMessage` đã cấu hình dưới dạng tệp MHT sẽ tạo ra một tài liệu tự chứa duy nhất có thể mở trong trình duyệt hoặc khách hàng email. Phương thức `save` sẽ tuân theo các tùy chọn bạn đã định nghĩa trước đó.

#### Các bước thực hiện

**Import required classes**

```java
import com.aspose.email.MailMessage;
import com.aspose.email.MhtSaveOptions;
```

**Save email message**

```java
msg.save("YOUR_OUTPUT_DIRECTORY" + "Meeting with Recurring Occurrences_out.mhtml", options);
```

Lệnh này ghi email vào tệp MHT, sẵn sàng cho việc chia sẻ hoặc lưu trữ.

## Ứng dụng thực tế
- **Lưu trữ email** – Chuyển đổi và lưu trữ các email quan trọng ở định dạng thân thiện với web để bảo quản lâu dài.  
- **Tài liệu pháp lý** – Sử dụng tệp MHT như một phần của bằng chứng pháp lý khi yêu cầu độ trung thực của email.  
- **Chia sẻ đa nền tảng** – Chia sẻ email giữa các nền tảng mà không gặp vấn đề tương thích, vì MHT gói mọi thứ vào một tệp.  

Việc tích hợp với các hệ thống khác—như CRM hoặc công cụ quản lý dự án—có thể nâng cao sự hợp tác bằng cách nhúng dữ liệu email quan trọng trực tiếp vào quy trình làm việc.

## Các cân nhắc về hiệu suất
Aspose.Email cho Java có thể xử lý các tệp lên tới 500 MB mà không cần tải toàn bộ tài liệu vào bộ nhớ, và thường chuyển đổi một email 100 trang có hình ảnh nhúng trong vòng dưới 2 giây trên máy chủ tiêu chuẩn. Để giữ cho ứng dụng phản hồi nhanh, hãy quản lý việc sử dụng bộ nhớ cẩn thận và thực hiện các thao tác I/O theo lô khi có thể.

## Các vấn đề thường gặp và giải pháp
`MhtFormatOptions` là một enumeration kiểm soát các yếu tố (tiêu đề, tài nguyên, sự kiện lịch) được bao gồm khi lưu tin nhắn dưới dạng MHT.

| Vấn đề | Nguyên nhân | Giải pháp |
|-------|-------------|----------|
| **NullPointerException on `msg.save`** | Đường dẫn đầu ra không đúng | Kiểm tra `YOUR_OUTPUT_DIRECTORY` tồn tại và có quyền ghi. |
| **Missing images in MHT** | `MhtFormatOptions` chưa được thiết lập để nhúng tài nguyên | Thêm `MhtFormatOptions.EmbedResources` vào cờ tùy chọn. |
| **Calendar events not rendered** | Cờ `RenderCalendarEvent` bị bỏ qua | Đảm bảo `options.setMhtFormatOptions(MhtFormatOptions.WriteHeader \| MhtFormatOptions.RenderCalendarEvent);` |

## Câu hỏi thường gặp

**Q: Làm thế nào để xử lý tệp đính kèm khi lưu email dưới dạng MHT?**  
A: Cấu hình `MhtSaveOptions` để nhúng tệp đính kèm; thư viện sẽ tự động bao gồm chúng trong gói MHT.

**Q: Tôi có thể tùy chỉnh tiêu đề email trong tệp MHT đầu ra không?**  
A: Có, sử dụng `MhtFormatOptions.WriteHeader` và cung cấp các chuỗi mẫu tùy chỉnh cho mỗi trường tiêu đề.

**Q: Các yêu cầu hệ thống cho việc sử dụng Aspose.Email Java là gì?**  
A: Yêu cầu JDK 16 hoặc cao hơn. Thư viện hoạt động với bất kỳ IDE nào hỗ trợ dự án Maven.

**Q: Có thể lưu chỉ một phần cụ thể của tin nhắn email không?**  
A: Mặc dù MHT thường chứa toàn bộ tin nhắn, bạn có thể thao tác các thuộc tính của `MailMessage` để loại bỏ các phần không mong muốn trước khi lưu.

**Q: Làm sao để khắc phục các vấn đề khi tải hoặc lưu email?**  
A: Kiểm tra đường dẫn tệp, đảm bảo giấy phép đã được áp dụng đúng, và tham khảo [diễn đàn hỗ trợ Aspose.Email](https://forum.aspose.com/c/email/10) để được trợ giúp chi tiết.

**Q: Thư viện có hỗ trợ chuyển đổi các định dạng khác (EML, MSG) sang MHT không?**  
A: Chắc chắn. `MailMessage.load` có thể đọc EML, MSG và các định dạng hỗ trợ khác, sau đó bạn có thể lưu chúng dưới dạng MHT bằng cùng các tùy chọn.

## Tài nguyên
- **Tài liệu**: Để tìm hiểu sâu hơn về tất cả các chức năng, truy cập [Aspose Email Java Documentation](https://reference.aspose.com/email/java/).  
- **Tải xuống**: Bắt đầu dùng bản dùng thử miễn phí bằng cách tải từ [Releases](https://releases.aspose.com/email/java/).  
- **Mua**: Khám phá các tùy chọn mua tại [Official Purchase Page](https://purchase.aspose.com/buy) cho việc sử dụng lâu dài.  
- **Bản dùng thử và giấy phép tạm thời**: Truy cập các tính năng toàn diện trong thời gian dùng thử hoặc nhận giấy phép tạm thời qua các liên kết sau:  
  - [Free Trial](https://releases.aspose.com/email/java/)  
  - [Temporary License](https://purchase.aspose.com/temporary-license/)

Khám phá, triển khai và biến đổi cách xử lý email của bạn với Aspose.Email cho Java ngay hôm nay!

---

**Last Updated:** 2026-09-22  
**Tested With:** Aspose.Email for Java 25.4 (jdk16 classifier)  
**Author:** Aspose  

---

## Hướng dẫn liên quan

- [Làm chủ Aspose.Email cho Java: Hướng dẫn Giấy phép & Xử lý Email](/email/java/getting-started/mastering-aspose-email-java-license-email-handling/)
- [Cách chuyển đổi MSG sang MHT bằng Aspose.Email cho Java – Hướng dẫn từng bước](/email/java/email-conversion-rendering/convert-mapi-messages-to-mht-aspose-email-java/)
- [Cách lưu email MSG với Aspose.Email cho Java](/email/java/email-message-operations/aspose-email-java-create-save-emails/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}