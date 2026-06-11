---
date: '2026-03-02'
description: Tìm hiểu cách sử dụng Maven Aspose.Email cho Java để lưu email dưới dạng
  tệp MHT. Hướng dẫn từng bước này bao gồm cài đặt, mẫu tùy chỉnh và chuyển đổi email
  sang MHT.
keywords:
- save emails as MHT files
- Aspose.Email for Java
- convert emails to MHTML
title: 'Maven Aspose.Email cho Java: Lưu email dưới dạng tệp MHT'
url: /vi/java/email-message-operations/save-emails-as-mht-using-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Maven Aspose.Email for Java: Cách Lưu Email dưới Dạng Tệp MHT

## Giới thiệu

Quản lý dữ liệu email một cách hiệu quả có thể gặp khó khăn, đặc biệt khi liên quan đến việc chia sẻ và lưu trữ. Trong hướng dẫn này, chúng tôi sẽ chỉ cho bạn **cách lưu tệp MHT** bằng **Maven Aspose.Email for Java**, để bạn có thể chuyển đổi email sang MHT với các mẫu tùy chỉnh và giữ nguyên các sự kiện lịch. Bạn sẽ có một giải pháp sẵn sàng chạy trong bất kỳ môi trường Java 16+ nào.

## Câu trả lời nhanh
- **Thư viện tôi cần là gì?** Maven Aspose.Email for Java (v25.4+).  
- **Định dạng được tạo ra là gì?** Một tệp MHT (MHTML) chứa HTML, hình ảnh và dữ liệu lịch.  
- **Tôi có thể tùy chỉnh tiêu đề không?** Có – sử dụng `MhtFormatOptions` và các chuỗi mẫu.  
- **Tôi có cần giấy phép không?** Bản dùng thử miễn phí đủ cho việc đánh giá; giấy phép vĩnh viễn cần cho môi trường sản xuất.  
- **Phiên bản Java yêu cầu là gì?** JDK 16 hoặc mới hơn.

## Aspose.Email for Java là gì?
Maven Aspose.Email for Java là một API mạnh mẽ cho phép bạn tạo, đọc, chuyển đổi và thao tác các tin nhắn email trực tiếp từ mã Java. Nó hỗ trợ nhiều định dạng — bao gồm MSG, EML và MHT — làm cho nó trở thành lựa chọn lý tưởng cho các nhiệm vụ **java email conversion**.

## Tại sao chuyển đổi Email sang MHT?
- **Thân thiện với web**: Tệp MHT hiển thị trong trình duyệt mà không cần tài nguyên bên ngoài.  
- **Ổn định lưu trữ**: Tất cả tài nguyên được nhúng, giữ nguyên giao diện gốc.  
- **Hỗ trợ lịch**: Bạn có thể hiển thị các sự kiện lặp lại với các mẫu tùy chỉnh.  

## Yêu cầu trước
- **Aspose.Email for Java** (artifact Maven `com.aspose:aspose-email:25.4` với classifier `jdk16`).  
- **Maven** đã được cài đặt và cấu hình trên máy của bạn.  
- **JDK 16+** (thư viện hướng tới Java 16).  
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

### Nhận giấy phép

Aspose cung cấp bản dùng thử miễn phí để khám phá các tính năng, cùng với các tùy chọn mua giấy phép hoặc nhận giấy phép tạm thời.

1. **Bản dùng thử**: Tải xuống từ [Releases](https://releases.aspose.com/email/java/) và khám phá các tính năng không giới hạn.  
2. **Giấy phép tạm thời**: Truy cập phiên bản đầy đủ chức năng bằng cách yêu cầu qua [Temporary License Page](https://purchase.aspose.com/temporary-license/).  
3. **Mua**: Xem xét mua nếu Aspose.Email đáp ứng nhu cầu dự án dài hạn của bạn.

### Khởi tạo cơ bản

Sau khi cài đặt, khởi tạo thư viện trong ứng dụng Java của bạn:

```java
import com.aspose.email.License;

License license = new License();
license.setLicense("path/to/your/license/file");
```

Với các bước này, bạn đã sẵn sàng sử dụng các tính năng của Aspose.Email để xử lý email một cách hiệu quả.

## Hướng dẫn triển khai

### Tính năng 1: Tải MailMessage

#### Tổng quan
Tải một tin nhắn email là bước đầu tiên trong quá trình xử lý và lưu nó dưới dạng tệp MHT. Ở đây, chúng tôi sẽ minh họa cách tải tệp `.msg` bằng `MailMessage`.

#### Các bước thực hiện

**Nhập các lớp cần thiết**

```java
import com.aspose.email.MailMessage;
```

**Tải Email từ tệp**

```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY" + "/email/";
MailMessage msg = MailMessage.load(dataDir + "Meeting with Recurring Occurrences.msg");
```

Đoạn mã này tải một tin nhắn email nằm trong thư mục bạn chỉ định.

### Tính năng 2: Cấu hình MhtSaveOptions

#### Tổng quan
Cấu hình `MhtSaveOptions` rất quan trọng để xác định cách email của bạn sẽ được lưu dưới dạng tệp MHT, bao gồm định dạng tùy chỉnh cho các sự kiện lịch.

#### Các bước thực hiện

**Nhập các lớp cần thiết**

```java
import com.aspose.email.MhtSaveOptions;
import com.aspose.email.MhtFormatOptions;
import com.aspose.email.MhtTemplateName;
```

**Đặt tùy chọn lưu và mẫu**

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

Cấu hình này thiết lập tiêu đề và cách hiển thị sự kiện lịch trong đầu ra MHT.

### Tính năng 3: Lưu MailMessage dưới dạng MHT

#### Tổng quan
Bước cuối cùng là lưu `MailMessage` đã cấu hình dưới dạng tệp MHT bằng các tùy chọn đã chỉ định.

#### Các bước thực hiện

**Nhập các lớp cần thiết**

```java
import com.aspose.email.MailMessage;
import com.aspose.email.MhtSaveOptions;
```

**Lưu tin nhắn Email**

```java
msg.save("YOUR_OUTPUT_DIRECTORY" + "Meeting with Recurring Occurrences_out.mhtml", options);
```

Lệnh này ghi email vào tệp MHT, sẵn sàng để chia sẻ hoặc lưu trữ.

## Ứng dụng thực tiễn
- **Lưu trữ Email**: Chuyển đổi và lưu trữ các email quan trọng ở định dạng thân thiện với web.  
- **Tài liệu pháp lý**: Sử dụng tệp MHT như một phần của bằng chứng pháp lý khi cần bảo toàn chi tiết email.  
- **Chia sẻ đa nền tảng**: Chia sẻ email giữa các nền tảng mà không gặp vấn đề tương thích.  

Việc tích hợp với các hệ thống khác, chẳng hạn CRM hoặc công cụ quản lý dự án, có thể nâng cao hợp tác bằng cách nhúng dữ liệu email quan trọng trực tiếp vào quy trình làm việc.

## Lưu ý về hiệu năng
Để đảm bảo hiệu năng tối ưu:
- Quản lý bộ nhớ một cách hiệu quả khi xử lý lượng lớn email.  
- Tối ưu hoá các thao tác I/O để tránh nghẽn cổ chai trong quá trình lưu.  

Áp dụng các thực hành tốt về quản lý bộ nhớ trong Java sẽ giúp ứng dụng của bạn luôn phản hồi nhanh.

## Các vấn đề thường gặp và giải pháp
| Vấn đề | Nguyên nhân | Giải pháp |
|-------|-------------|----------|
| **NullPointerException khi `msg.save`** | Đường dẫn đầu ra không đúng | Kiểm tra `YOUR_OUTPUT_DIRECTORY` tồn tại và có quyền ghi. |
| **Hình ảnh bị thiếu trong MHT** | `MhtFormatOptions` chưa được thiết lập để nhúng tài nguyên | Thêm `MhtFormatOptions.EmbedResources` vào cờ tùy chọn. |
| **Sự kiện lịch không hiển thị** | Bỏ qua cờ `RenderCalendarEvent` | Đảm bảo `options.setMhtFormatOptions(MhtFormatOptions.WriteHeader \| MhtFormatOptions.RenderCalendarEvent);` |

## Câu hỏi thường gặp

**H: Làm sao xử lý tệp đính kèm khi lưu email dưới dạng MHT?**  
Đ: Đảm bảo `MhtSaveOptions` được cấu hình để bao gồm logic xử lý tệp đính kèm. Thư viện hỗ trợ nhúng các tệp đính kèm vào tệp MHT.

**H: Tôi có thể tùy chỉnh tiêu đề email trong tệp MHT đầu ra không?**  
Đ: Có, sử dụng `MhtFormatOptions.WriteHeader` và định nghĩa các mẫu tùy chỉnh cho các trường tiêu đề như trong hướng dẫn.

**H: Yêu cầu hệ thống cho Aspose.Email Java là gì?**  
Đ: Cần JDK 16 hoặc cao hơn. Thư viện hoạt động mượt mà với hầu hết IDE hiện đại hỗ trợ dự án Maven.

**H: Có thể lưu chỉ một phần cụ thể của tin nhắn email không?**  
Đ: Mặc dù định dạng MHT thường bao gồm toàn bộ tin nhắn, bạn có thể sử dụng các thuộc tính của `MailMessage` để chọn lọc và chỉ bao gồm nội dung mong muốn.

**H: Làm sao khắc phục các vấn đề khi tải hoặc lưu email?**  
Đ: Kiểm tra lại đường dẫn tệp, đảm bảo thư viện đã được thiết lập đúng trong dự án, và tham khảo diễn đàn hỗ trợ của Aspose.Email tại [support forum](https://forum.aspose.com/c/email/10).

**H: Thư viện có hỗ trợ chuyển đổi các định dạng khác (EML, MSG) sang MHT không?**  
Đ: Hoàn toàn có. `MailMessage.load` có thể đọc EML, MSG và các định dạng khác, sau đó bạn có thể lưu chúng dưới dạng MHT bằng cùng một bộ tùy chọn.

## Tài nguyên
- **Documentation**: Để tìm hiểu sâu hơn về mọi chức năng, truy cập [Aspose Email Java Documentation](https://reference.aspose.com/email/java/).  
- **Download**: Bắt đầu với bản dùng thử miễn phí bằng cách tải từ [Releases](https://releases.aspose.com/email/java/).  
- **Purchase**: Khám phá các tùy chọn mua tại [Official Purchase Page](https://purchase.aspose.com/buy) cho việc sử dụng lâu dài.  
- **Free Trial và Temporary License**: Truy cập đầy đủ tính năng trong thời gian dùng thử hoặc nhận giấy phép tạm thời qua các liên kết sau:  
  - [Free Trial](https://releases.aspose.com/email/java/)  
  - [Temporary License](https://purchase.aspose.com/temporary-license/)

Khám phá, triển khai và biến đổi cách xử lý email của bạn với Aspose.Email cho Java ngay hôm nay!

---

**Cập nhật lần cuối:** 2026-03-02  
**Đã kiểm tra với:** Aspose.Email for Java 25.4 (jdk16 classifier)  
**Tác giả:** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
