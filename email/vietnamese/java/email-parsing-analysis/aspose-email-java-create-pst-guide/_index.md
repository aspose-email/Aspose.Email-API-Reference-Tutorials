---
date: '2026-06-08'
description: Tìm hiểu cách tạo tệp PST với Aspose.Email for Java, bao gồm cách thêm
  cấu trúc thư mục và cách tìm kiếm nội dung PST một cách hiệu quả. Hướng dẫn từng
  bước.
keywords:
- how to create pst
- how to add folder
- how to search pst
schemas:
- author: Aspose
  dateModified: '2026-06-08'
  description: Learn how to create PST files with Aspose.Email for Java, including
    how to add folder structures and how to search PST content efficiently. Step‑by‑step
    guide.
  headline: How to Create PST Files with Aspose.Email for Java
  type: TechArticle
- description: Learn how to create PST files with Aspose.Email for Java, including
    how to add folder structures and how to search PST content efficiently. Step‑by‑step
    guide.
  name: How to Create PST Files with Aspose.Email for Java
  steps:
  - name: Add Maven Dependency
    text: Add the Aspose.Email Maven dependency to your `pom.xml`. This pulls in all
      required binaries automatically.
  - name: Acquire and Apply a License
    text: A free trial is available, but a permanent license removes evaluation limits
      and enables full‑speed processing.
  - name: Initialize PersonalStorage
    text: The `PersonalStorage` class is Aspose.Email's top‑level object that represents
      a single PST file in memory. After instantiation, all read and write operations
      flow through this object.
  - name: Define Directory Paths
    text: Set source and destination paths for your email files and the PST output
      location.
  - name: Create the PST File
    text: Use `PersonalStorage.create()` with `FileFormatVersion.Unicode` to produce
      a modern Unicode PST that supports large folders and Unicode characters.
  - name: Build Search Query
    text: Construct a query that looks for a keyword in the subject or body, ignoring
      case.
  - name: Execute Query and Retrieve Messages
    text: Run the query on the target folder and iterate over the resulting `MapiMessage`
      collection.
  - name: Initialize PersonalStorage Object
    text: Assume `PersonalStorage` object (`pst`) is already created as shown previously.
  - name: Add to PST Folder
    text: 'Convert `MailMessage` to `MapiMessage` and add it:'
  type: HowTo
- questions:
  - answer: JDK 16 or higher is recommended for full compatibility with Aspose.Email
      for Java.
    question: What is the minimum Java version required?
  - answer: Yes, a trial mode is available but limits PST size to **10 MB** and disables
      certain optimizations.
    question: Can I use Aspose.Email without a license?
  - answer: Process messages in batches, dispose of `MapiMessage` objects promptly,
      and enable lazy loading via `PersonalStorage.setUseUnicode(true)`.
    question: How do I handle large PST files efficiently?
  - answer: Absolutely. When converting `MailMessage` to `MapiMessage`, call `mapiMsg.getAttachments().add(attachment)`
      to embed files.
    question: Is it possible to add attachments to emails in PST files?
  - answer: Aspose offers a dedicated support forum, detailed documentation, and email
      support for licensed customers.
    question: What kind of support is available for troubleshooting issues?
  type: FAQPage
title: Cách tạo tệp PST bằng Aspose.Email for Java
url: /vi/java/email-parsing-analysis/aspose-email-java-create-pst-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Làm Chủ Quản Lý Email với Aspose.Email cho Java

Nếu bạn cần **how to create pst** files programmatically, bạn đã đến đúng nơi. Trong hướng dẫn này chúng tôi sẽ hướng dẫn từng bước để tạo một tệp Unicode PST, thêm các thư mục Outlook tiêu chuẩn, nhập tin nhắn và thực hiện tìm kiếm không phân biệt chữ hoa chữ thường — tất cả bằng Aspose.Email cho Java. Khi kết thúc, bạn sẽ có một mẫu mã có thể tái sử dụng, mở rộng từ vài email đến các kho lưu trữ đa gigabyte.

## Câu trả lời nhanh
- **Làm thế nào để bắt đầu?** Thêm phụ thuộc Aspose.Email Maven, lấy giấy phép và khởi tạo `PersonalStorage`.
- **Tôi có thể thêm thư mục Inbox không?** Có – gọi `pst.getRootFolder().addSubFolder("Inbox")`.
- **Có hỗ trợ tìm kiếm không phân biệt chữ hoa chữ thường không?** Sử dụng `PersonalStorageQueryBuilder` với `StringComparison.OrdinalIgnoreCase`.
- **Kích thước tệp tối đa có thể xử lý là bao nhiêu?** Aspose.Email xử lý các tệp PST lên tới 2 GB mà không tải toàn bộ tệp vào bộ nhớ.
- **Tôi có cần giấy phép trả phí cho môi trường production không?** Giấy phép vĩnh viễn loại bỏ giới hạn dùng thử và mở khóa các tính năng hiệu năng đầy đủ.

## “how to create pst” là gì?
**how to create pst** đề cập đến quá trình tạo tệp Outlook Personal Storage Table (PST) bằng mã thay vì giao diện Outlook. Aspose.Email cho Java cung cấp một API được quản lý hoàn toàn, tạo các tệp Unicode PST, thêm thư mục và lưu các đối tượng `MapiMessage` mà không cần cài đặt Outlook.

## Tại sao nên sử dụng Aspose.Email để tạo PST?
Aspose.Email hỗ trợ **50+** định dạng liên quan đến email (MSG, EML, MBOX, PST, v.v.) và có thể xử lý các tệp PST **lên tới 2 GB** trong khi giữ mức sử dụng bộ nhớ dưới **150 MB** nhờ kiến trúc tải lười. Khả năng định lượng này khiến nó lý tưởng cho các kịch bản lưu trữ doanh nghiệp, di chuyển và tuân thủ.

## Yêu cầu trước
- **Java Development Kit (JDK)** – phiên bản 16 trở lên.
- **Maven** – để quản lý phụ thuộc.
- Kiến thức cơ bản về cú pháp Java; không cần kinh nghiệm trước về tệp PST.

## Cách tạo tệp PST?
Lớp `PersonalStorage` đại diện cho một tệp PST và cung cấp các phương thức để tạo, mở và thao tác nội dung của nó. Để tạo một PST Unicode mới, gọi `PersonalStorage.create()` với đường dẫn tệp và phiên bản định dạng mong muốn. Thao tác này tạo ra một PST hiện đại hỗ trợ thư mục lớn, ký tự Unicode và luồng dữ liệu hiệu quả, phù hợp cho cả nhiệm vụ lưu trữ quy mô nhỏ và doanh nghiệp.

### Bước 1: Thêm phụ thuộc Maven
Thêm phụ thuộc Aspose.Email Maven vào `pom.xml` của bạn. Điều này sẽ tự động tải về tất cả các binary cần thiết.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Bước 2: Nhận và áp dụng giấy phép
Có sẵn bản dùng thử miễn phí, nhưng giấy phép vĩnh viễn loại bỏ giới hạn đánh giá và cho phép xử lý tốc độ đầy đủ.

```java
import com.aspose.email.*;

public class AsposeEmailSetup {
    public static void main(String[] args) {
        // Set up license if available
        License license = new License();
        try {
            license.setLicense("path/to/your/license.lic");
        } catch (Exception e) {
            System.out.println("License not found, proceeding with trial version.");
        }

        System.out.println("Aspose.Email for Java is ready to use!");
    }
}
```

## Cách thêm thư mục vào PST?
Tạo cấu trúc thư mục mong muốn dưới gốc PST, sau đó tham chiếu khi chèn tin nhắn. Đối tượng `FolderInfo` đại diện cho mỗi thư mục và có thể lồng nhau tùy ý, cho phép bạn xây dựng các cấu trúc như Inbox, Sent Items hoặc thư mục dự án tùy chỉnh. Thêm thư mục là một thao tác nhẹ, không tải nội dung tin nhắn, giữ hiệu năng ngay cả với PST lớn.

### Bước 1: Khởi tạo PersonalStorage
Lớp `PersonalStorage` là đối tượng cấp cao nhất của Aspose.Email, đại diện cho một tệp PST duy nhất trong bộ nhớ. Sau khi khởi tạo, tất cả các thao tác đọc và ghi sẽ đi qua đối tượng này.

```java
import com.aspose.email.FileFormatVersion;
import com.aspose.email.PersonalStorage;
```

### Bước 2: Xác định đường dẫn thư mục
Đặt đường dẫn nguồn và đích cho các tệp email của bạn và vị trí xuất PST.

```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY";
String outputDir = "YOUR_OUTPUT_DIRECTORY";
```

### Bước 3: Tạo tệp PST
Sử dụng `PersonalStorage.create()` với `FileFormatVersion.Unicode` để tạo một PST Unicode hiện đại hỗ trợ thư mục lớn và ký tự Unicode.

```java
try {
    PersonalStorage pst = PersonalStorage.create(outputDir + "NewPSTFile_out.pst", FileFormatVersion.Unicode);

    // Perform operations here.
} finally {
    if (pst != null)
        pst.dispose();
}
```

## Cách tìm kiếm PST?
`PersonalStorageQueryBuilder` là một lớp builder dùng để xây dựng các truy vấn tìm kiếm nội dung PST. Bằng cách cấu hình builder với tiêu chí mong muốn và chỉ định `StringComparison.OrdinalIgnoreCase`, bạn có thể thực hiện tìm kiếm nhanh, không phân biệt chữ hoa chữ thường trên tiêu đề, nội dung và thuộc tính tùy chỉnh mà không tải toàn bộ PST vào bộ nhớ.

### Bước 1: Xây dựng truy vấn tìm kiếm
Tạo một truy vấn tìm kiếm từ khóa trong tiêu đề hoặc nội dung, bỏ qua phân biệt chữ hoa chữ thường.

```java
import com.aspose.email.MailQueryBuilder;
import com.aspose.email.MailQuery;
import com.aspose.email.MessageInfoCollection;

MailQueryBuilder builder = new MailQueryBuilder();
builder.getFrom().contains("automated", true);
```

### Bước 2: Thực thi truy vấn và lấy tin nhắn
Chạy truy vấn trên thư mục mục tiêu và lặp qua bộ sưu tập `MapiMessage` kết quả.

```java
try {
    MailQuery query = builder.getQuery();
    MessageInfoCollection coll = fi.getContents(query);

    // Process results as needed.
} finally {
    if (pst != null)
        pst.dispose();
}
```

## Tạo thư mục định trước trong PST
Thêm một thư mục định trước như **Inbox** giúp tổ chức dữ liệu email một cách hiệu quả.

### Bước 1: Khởi tạo đối tượng PersonalStorage
Giả sử đối tượng `PersonalStorage` (`pst`) đã được tạo như đã trình bày ở trên.

### Bước 2: Tạo thư mục 'Inbox'
```java
try {
    FolderInfo fi = pst.createPredefinedFolder("Inbox", StandardIpmFolder.Inbox);
} finally {
    if (pst != null)
        pst.dispose();
}
```

## Thêm tin nhắn vào thư mục PST
Điền thư mục PST của bạn bằng các tin nhắn email bằng cách tải chúng từ tệp và chuyển đổi.

### Bước 1: Tải tin nhắn email
```java
import com.aspose.email.MailMessage;
import com.aspose.email.MapiMessage;

MailMessage mailMessage = MailMessage.load(dataDir + "message.msg");
```

### Bước 2: Thêm vào thư mục PST
Chuyển đổi `MailMessage` sang `MapiMessage` và thêm vào:

```java
try {
    fi.addMessage(MapiMessage.fromMailMessage(mailMessage));
} finally {
    if (pst != null)
        pst.dispose();
}
```

## Ứng dụng thực tiễn
Aspose.Email cho Java không chỉ tạo tệp PST; nó là công cụ đa năng với nhiều ứng dụng:
- **Email Archiving**: Tự động lưu trữ email doanh nghiệp vào tệp PST, hỗ trợ chính sách lưu trữ lên tới 10 năm.
- **Migration Tools**: Dễ dàng di chuyển từ các kho lưu trữ email cũ (ví dụ, MBOX) sang Outlook PST chỉ với một lời gọi API cho mỗi tin nhắn.
- **Data Analysis**: Trích xuất siêu dữ liệu như người gửi, người nhận và thời gian để dùng trong quy trình phân tích kinh doanh.
- **Backup Solutions**: Xây dựng công cụ sao lưu mạnh mẽ lưu các thay đổi email tăng dần mà không cần xử lý lại toàn bộ hộp thư.

## Các cân nhắc về hiệu năng
Để đảm bảo hiệu năng tối ưu khi sử dụng Aspose.Email:
- **Resource Management**: Luôn gọi `pst.dispose()` hoặc sử dụng try‑with‑resources để giải phóng các handle native kịp thời.
- **Batch Processing**: Xử lý email theo lô **500** mục để giữ mức sử dụng bộ nhớ dự đoán được.
- **Concurrency Handling**: Thư viện an toàn đa luồng cho các thao tác chỉ đọc; đối với ghi, đồng bộ truy cập vào đối tượng `PersonalStorage`.

## Các vấn đề thường gặp và giải pháp
| Issue | Cause | Solution |
|-------|-------|----------|
| **OutOfMemoryError** khi xử lý PST lớn | Tải toàn bộ PST vào bộ nhớ | Bật `PersonalStorage.setUseUnicode(true)` và xử lý tin nhắn theo luồng. |
| **Folder not found** error | Tên đường dẫn thư mục không đúng chữ hoa chữ thường | Sử dụng `StringComparison.OrdinalIgnoreCase` trong truy vấn hoặc chuẩn hoá tên thư mục. |
| **License not applied** | Tệp giấy phép không được tải trước khi gọi API đầu tiên | Tải giấy phép khi khởi động ứng dụng, trước khi tạo bất kỳ đối tượng `PersonalStorage` nào. |

## Câu hỏi thường gặp
**Q: Yêu cầu tối thiểu phiên bản Java nào?**  
A: JDK 16 hoặc cao hơn được khuyến nghị để tương thích đầy đủ với Aspose.Email cho Java.

**Q: Tôi có thể sử dụng Aspose.Email mà không có giấy phép không?**  
A: Có, chế độ dùng thử có sẵn nhưng giới hạn kích thước PST ở **10 MB** và tắt một số tối ưu hóa.

**Q: Làm thế nào để xử lý các tệp PST lớn một cách hiệu quả?**  
A: Xử lý tin nhắn theo lô, giải phóng các đối tượng `MapiMessage` kịp thời, và bật tải lười bằng `PersonalStorage.setUseUnicode(true)`.

**Q: Có thể thêm tệp đính kèm vào email trong tệp PST không?**  
A: Chắc chắn. Khi chuyển đổi `MailMessage` sang `MapiMessage`, gọi `mapiMsg.getAttachments().add(attachment)` để nhúng tệp.

**Q: Loại hỗ trợ nào có sẵn để khắc phục sự cố?**  
A: Aspose cung cấp diễn đàn hỗ trợ riêng, tài liệu chi tiết và hỗ trợ qua email cho khách hàng có giấy phép.

## Tài nguyên
- [Tài liệu](https://reference.aspose.com/email/java/)
- [Tải xuống](https://releases.aspose.com/email/java/)
- [Mua](https://purchase.aspose.com/buy)
- [Dùng thử miễn phí](https://releases.aspose.com/email/java/)
- [Giấy phép tạm thời](https://purchase.aspose.com/temporary-license/)
- [Diễn đàn hỗ trợ](https://forum.aspose.com/c/email/10)

---

**Cập nhật lần cuối:** 2026-06-08  
**Kiểm tra với:** Aspose.Email for Java 24.10  
**Tác giả:** Aspose

## Hướng dẫn liên quan
- [Cách tạo và quản lý tệp Outlook PST bằng Aspose.Email cho Java](/email/java/outlook-pst-ost-operations/aspose-email-java-manage-pst-files/)
- [Thao tác với tệp PST bằng Aspose.Email cho Java: Hướng dẫn toàn diện](/email/java/outlook-pst-ost-operations/manipulate-pst-files-aspose-email-java/)
- [Trích xuất tệp đính kèm email Java - Sử dụng Aspose.Email cho tệp PST – Hướng dẫn từng bước](/email/java/attachments-handling/extract-email-attachments-pst-aspose-java/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}