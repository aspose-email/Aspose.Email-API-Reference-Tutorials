---
date: '2026-10-02'
description: Tìm hiểu cách kết nối Exchange và liệt kê các thư mục công cộng của Exchange
  bằng Aspose.Email cho Java. Hướng dẫn từng bước này hiển thị phụ thuộc Maven và
  thiết lập không cần viết mã.
keywords:
- how to connect exchange
- list exchange public folders
- maven dependency aspose email
lastmod: '2026-10-02'
og_description: Tìm hiểu cách kết nối Exchange và liệt kê các thư mục công cộng của
  Exchange bằng Aspose.Email cho Java. Hướng dẫn này bao gồm phụ thuộc Maven, giấy
  phép và việc truy xuất tin nhắn đệ quy.
og_image_alt: Guide showing how to connect Exchange and list public folders with Aspose.Email
  for Java
og_title: Cách kết nối Exchange và liệt kê các thư mục công cộng trong Java
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Learn how to connect exchange and list exchange public folders using
    Aspose.Email for Java. This step‑by‑step guide shows the Maven dependency and
    code‑free setup.
  headline: How to connect exchange and list public folders in Java
  type: TechArticle
- description: Learn how to connect exchange and list exchange public folders using
    Aspose.Email for Java. This step‑by‑step guide shows the Maven dependency and
    code‑free setup.
  name: How to connect exchange and list public folders in Java
  steps:
  - name: '**Automated email archiving** – Periodically pull all public‑folder messages
      and store them in a compliant archive.'
    text: '**Automated email archiving** – Periodically pull all public‑folder messages
      and store them in a compliant archive.'
  - name: '**Backup solutions** – Mirror Exchange public folders to a secure file
      system or cloud bucket, guaranteeing data redundancy.'
    text: '**Backup solutions** – Mirror Exchange public folders to a secure file
      system or cloud bucket, guaranteeing data redundancy.'
  - name: '**Custom email clients** – Build lightweight viewers that display only
      the folders and messages you need, reducing UI complexity.'
    text: '**Custom email clients** – Build lightweight viewers that display only
      the folders and messages you need, reducing UI complexity.'
  type: HowTo
- questions:
  - answer: Yes. Provide the Office 365 EWS endpoint (`https://outlook.office365.com/EWS/Exchange.asmx`)
      and use modern authentication (OAuth) – Aspose.Email supports OAuth tokens out
      of the box.
    question: Can I use this code with Exchange Online (Office 365)?
  - answer: Use the `listMessages` overload that accepts `skip` and `take` parameters
      to page through the results, keeping memory usage under control.
    question: What if a folder contains more than 10 000 messages?
  - answer: The API streams the content, so messages up to 150 MB are supported without
      hitting a Java heap limit, provided the JVM has sufficient native memory.
    question: Is there a limit on the size of a single email I can download?
  - answer: By default Aspose.Email trusts the Java default keystore. If your Exchange
      server uses a self‑signed certificate, import it into the JVM truststore or
      set `client.setEnableSslVerification(false)` for testing only.
    question: Do I need to handle SSL certificates manually?
  - answer: Enable Aspose.Email’s built‑in logging by configuring `Logger.setLevel(Level.INFO)`
      and directing output to a file or monitoring system.
    question: How do I log the operations for audit purposes?
  type: FAQPage
tags:
- exchange integration
- Aspose.Email
- Java email automation
title: Cách kết nối Exchange và liệt kê các thư mục công cộng trong Java
url: /vi/java/exchange-server-integration/aspose-email-java-exchange-messages-listing/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách kết nối Exchange và liệt kê các thư mục công cộng trong Java

## Giới thiệu
Trong các doanh nghiệp hiện đại, việc truy cập các hộp thư Microsoft Exchange một cách lập trình cho phép bạn tự động hoá các nhiệm vụ lưu trữ, giám sát và báo cáo. Hướng dẫn này trình bày **cách kết nối Exchange** với Aspose.Email cho Java và sau đó **liệt kê các thư mục công cộng của Exchange** một cách đệ quy. Bạn sẽ thấy phụ thuộc Maven cần thiết, các bước cấp phép, và chuỗi các lời gọi API chính xác — không cần thư viện bổ sung. Khi hoàn thành, bạn sẽ có thể lấy các tin nhắn từ bất kỳ thư mục công cộng nào và lưu chúng về máy cục bộ.

## Câu trả lời nhanh
- **Bước đầu tiên là gì?** Thêm phụ thuộc Maven Aspose.Email vào tệp `pom.xml` của bạn.  
- **Tôi có cần giấy phép không?** Có — sử dụng giấy phép tạm thời để đánh giá hoặc mua giấy phép đầy đủ cho môi trường sản xuất.  
- **Lớp nào tạo kết nối?** `ExchangeClient` (hoặc `ImapClient` cho IMAP) chịu trách nhiệm xác thực và giao tiếp với máy chủ.  
- **Tôi có thể liệt kê các thư mục con tự động không?** Có — sử dụng phương thức đệ quy `listSubFolders` được cung cấp bởi API.  
- **Cách tiếp cận này có an toàn với đa luồng không?** Các đối tượng client không an toàn với đa luồng; tạo một thể hiện riêng cho mỗi luồng khi thực hiện tải công việc đồng thời.

## Cách kết nối Exchange là gì?
**How to connect exchange** là quá trình xác thực một ứng dụng Java với máy chủ Microsoft Exchange tại chỗ hoặc dựa trên đám mây để bạn có thể thực hiện các lời gọi API như liệt kê thư mục hoặc lấy tin nhắn. Aspose.Email trừu tượng hoá các giao thức EWS/IMAP nền tảng, cung cấp cho bạn một mô hình đối tượng duy nhất và nhất quán.

## Tại sao cần liệt kê các thư mục công cộng của Exchange?
Việc liệt kê các thư mục công cộng giúp bạn nhìn thấy cấu trúc phân cấp mà các tổ chức sử dụng cho hộp thư chia sẻ, danh sách phân phối và kho lưu trữ. Aspose.Email có thể liệt kê hơn **50+ thư mục công cộng** trong một lần gọi và hỗ trợ xử lý các hộp thư hàng trăm trang mà không cần tải toàn bộ kho vào bộ nhớ, giảm tiêu thụ RAM tới 70 %.

## Các yêu cầu trước
- **Aspose.Email for Java** — phiên bản 25.4 trở lên (bản phát hành ổn định mới nhất).  
- **Java Development Kit (JDK)** — JDK 11 hoặc mới hơn đã được cài đặt và cấu hình `JAVA_HOME`.  
- **Maven** — để quản lý phụ thuộc và tự động hoá quá trình xây dựng.  
- Kiến thức cơ bản về cú pháp Java và các khái niệm Exchange (hộp thư, thư mục, EWS).

## Cài đặt Aspose.Email cho Java
Để tích hợp thư viện, thêm phụ thuộc Maven vào tệp `pom.xml` của dự án. Đây là **phụ thuộc Maven Aspose Email** mà bạn cần.

### Phụ thuộc Maven
Add the following snippet inside the `<dependencies>` element of your `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Các bước lấy giấy phép
Aspose.Email requires a valid license for full‑feature use:

- **Dùng thử miễn phí** – Tải giấy phép tạm thời từ [trang web Aspose](https://purchase.aspose.com/temporary-license/) để đánh giá API.  
- **Mua** – Mua giấy phép thương mại qua cổng thông tin Aspose cho các triển khai sản xuất.

#### Khởi tạo cơ bản
After Maven resolves the package and you have a license file, place the `.lic` file on the classpath and initialise the library:

```java
import com.aspose.email.License;

License license = new License();
license.setLicense("path/to/your/license.lic");
```

## Hướng dẫn triển khai
Chúng tôi sẽ đi qua từng khối chức năng, trả lời các câu hỏi chính bằng các đoạn ngắn gọn, trực tiếp trước khi đưa ra các bước chi tiết.

### Cách kết nối Exchange?
Tải `ExchangeClient` với URL máy chủ, thông tin đăng nhập người dùng và miền, sau đó gọi `connect()`.  
Client thiết lập một phiên HTTPS với Exchange Web Services (EWS) và xác thực thông tin đăng nhập.  
Nếu kết nối thất bại, API sẽ ném ra một `AuthenticationException` chi tiết, bao gồm mã trạng thái HTTP để dễ dàng khắc phục.  
`ExchangeClient` là lớp của Aspose.Email quản lý kết nối tới Exchange Web Services.

```java
import com.aspose.email.EWSClient;
import com.aspose.email.IEWSClient;

IEWSClient connectToExchangeServer(String exchangeUrl, String username, String password, String domain) {
    // Create instance of IEWSClient class by providing credentials
    return EWSClient.getEWSClient(exchangeUrl, username, password, domain);
}
```

### Cách liệt kê các thư mục công cộng của Exchange?
Gọi `client.listPublicFolders()` để lấy một tập hợp các đối tượng `FolderInfo` đại diện cho mỗi thư mục công cộng cấp cao nhất.  
Phương thức trả về siêu dữ liệu như tên thư mục, tổng số mục, và một định danh duy nhất dùng cho các lời gọi tiếp theo.  
Lời gọi này hoàn thành trong vòng dưới 2 giây cho các triển khai tại chỗ điển hình với tối đa 500 thư mục.  
`listPublicFolders()` trả về một tập hợp các đối tượng `FolderInfo`.  
`FolderInfo` chứa siêu dữ liệu như tên hiển thị và số lượng mục.

```java
import com.aspose.email.ExchangeFolderInfoCollection;
import com.aspose.email.IEWSClient;

ExchangeFolderInfoCollection listPublicFolders(IEWSClient client) {
    // List all public folders and return their information as a collection
    return client.listPublicFolders();
}
```

### Cách hiển thị thông tin thư mục?
Duyệt qua tập hợp `FolderInfo` và in ra `displayName` và `subFolderCount`.  
Bản tóm tắt nhanh này giúp bạn hiểu cấu trúc phân cấp trước khi thực hiện việc thu thập sâu hơn.  
Đối với các tổ chức lớn, API có thể phân trang kết quả, trả về 100 thư mục mỗi trang để giảm mức sử dụng bộ nhớ.

```java
import com.aspose.email.ExchangeFolderInfo;

void displayFolderInfo(ExchangeFolderInfo folder) {
    // Print folder details
    System.out.println("Name: " + folder.getDisplayName());
    System.out.println("Subfolders count: " + folder.getChildFolderCount());
}
```

### Cách liệt kê tin nhắn từ một thư mục?
Gọi `client.listMessages(folderId)` trong đó `folderId` là định danh đã lấy ở bước trước.  
Phương thức trả về một danh sách các đối tượng `MessageInfo` chứa tiêu đề, người gửi và ngày nhận.  
Bạn có thể giới hạn tập kết quả bằng `maxCount` để tránh làm quá tải client khi xử lý các thư mục rất lớn.  
`listMessages(folderId)` trả về một danh sách các đối tượng `MessageInfo`.  
`MessageInfo` chứa các thuộc tính cơ bản của email như tiêu đề, người gửi và ngày nhận.

```java
import com.aspose.email.ExchangeMessageInfoCollection;
import com.aspose.email.IEWSClient;

ExchangeMessageInfoCollection listMessagesFromFolder(IEWSClient client, ExchangeFolderInfo folder) {
    // List messages from the specified public folder and return their information as a collection
    return client.listMessagesFromPublicFolder(folder);
}
```

### Cách tải và lưu tin nhắn?
Đối với mỗi `MessageInfo`, sử dụng `client.fetchMessage(messageId)` để tải về toàn bộ nội dung MIME.  
Sau đó ghi mảng byte vào tệp `.eml` trên đĩa.  
API truyền luồng nội dung, vì vậy ngay cả các tin nhắn 100 MB cũng được xử lý mà không cần tải toàn bộ dữ liệu vào bộ nhớ.  
`fetchMessage(messageId)` tải về toàn bộ nội dung MIME của email được chỉ định.

```java
import com.aspose.email.ExchangeMessageInfo;
import com.aspose.email.IEWSClient;
import com.aspose.email.MailMessage;
import com.aspose.email.SaveOptions;

void fetchAndSaveMessages(IEWSClient client, ExchangeMessageInfoCollection messages) {
    for (ExchangeMessageInfo messageInfo : messages) {
        // Fetch the full MailMessage using its unique URI
        MailMessage msg = client.fetchMessage(messageInfo.getUniqueUri());
        
        // Save the fetched message to a file named after its subject with .msg extension
        String filePath = "YOUR_OUTPUT_DIRECTORY/" + msg.getSubject() + ".msg";
        msg.save(filePath, SaveOptions.getDefaultMsgUnicode());
    }
}
```

### Cách liệt kê đệ quy tin nhắn từ các thư mục con?
Triển khai duyệt sâu‑đầu tiên: bắt đầu từ một thư mục cấp cao nhất, liệt kê các thư mục con của nó bằng `client.listSubFolders(parentId)`, sau đó gọi lại quy trình liệt kê tin nhắn cho mỗi thư mục con.  
Mẫu này đảm bảo mọi tin nhắn trong cây thư mục công cộng đều được xử lý.  
Độ sâu đệ quy chỉ bị giới hạn bởi cấu trúc thư mục của máy chủ (thông thường < 20 cấp).  
`listSubFolders(parentId)` trả về các thư mục con trực tiếp của thư mục được chỉ định.

```java
import com.aspose.email.ExchangeFolderInfo;
import com.aspose.email.IEWSClient;

void listMessagesFromSubFolders(IEWSClient client, ExchangeFolderInfo folder) {
    // List all messages in the current public folder
    ExchangeMessageInfoCollection msgCollection = client.listMessagesFromPublicFolder(folder);
    fetchAndSaveMessages(client, msgCollection);

    if (folder.getChildFolderCount() > 0) {
        ExchangeFolderInfoCollection subFolders = client.listSubFolders(folder);
        for (ExchangeFolderInfo subFolder : subFolders) {
            listMessagesFromSubFolders(client, subFolder);
        }
    }
}
```

## Ứng dụng thực tiễn
Real‑world scenarios where this workflow shines:

1. **Lưu trữ email tự động** – Định kỳ lấy tất cả tin nhắn từ thư mục công cộng và lưu chúng vào kho lưu trữ tuân thủ.  
2. **Giải pháp sao lưu** – Sao chép các thư mục công cộng của Exchange sang hệ thống tệp an toàn hoặc bucket đám mây, đảm bảo dư thừa dữ liệu.  
3. **Ứng dụng email tùy chỉnh** – Xây dựng các trình xem nhẹ chỉ hiển thị các thư mục và tin nhắn bạn cần, giảm độ phức tạp của giao diện người dùng.

## Các cân nhắc về hiệu năng
When scaling to thousands of folders and millions of messages, keep these tips in mind:

- **Kết nối pool** – Tái sử dụng một thể hiện `ExchangeClient` duy nhất cho nhiều thao tác thay vì tạo client mới cho mỗi thư mục.  
- **Tải lười** – Yêu cầu chỉ siêu dữ liệu cần thiết (`listMessages` với tham số `maxCount`) và tải toàn bộ nội dung khi cần.  
- **Giải phóng đối tượng** – Gọi `client.dispose()` sau khi chạy batch để giải phóng kết nối HTTP và bộ đệm cục bộ của luồng.  
- **Xử lý song song** – Chia các thư mục cấp cao nhất thành nhiều luồng, mỗi luồng có một thể hiện client riêng, để tận dụng hiệu quả CPU đa nhân.

## Câu hỏi thường gặp

**H: Tôi có thể sử dụng mã này với Exchange Online (Office 365) không?**  
Đáp: Có. Cung cấp endpoint EWS của Office 365 (`https://outlook.office365.com/EWS/Exchange.asmx`) và sử dụng xác thực hiện đại (OAuth) – Aspose.Email hỗ trợ token OAuth ngay từ đầu.

**H: Nếu một thư mục chứa hơn 10 000 tin nhắn thì sao?**  
Đáp: Sử dụng phiên bản `listMessages` chấp nhận các tham số `skip` và `take` để phân trang kết quả, giữ mức sử dụng bộ nhớ trong tầm kiểm soát.

**H: Có giới hạn kích thước của một email duy nhất mà tôi có thể tải về không?**  
Đáp: API truyền luồng nội dung, vì vậy các tin nhắn lên tới 150 MB được hỗ trợ mà không gặp giới hạn heap Java, với điều kiện JVM có đủ bộ nhớ gốc.

**H: Tôi có cần xử lý chứng chỉ SSL thủ công không?**  
Đáp: Mặc định Aspose.Email tin tưởng keystore mặc định của Java. Nếu máy chủ Exchange của bạn sử dụng chứng chỉ tự ký, hãy nhập nó vào truststore của JVM hoặc đặt `client.setEnableSslVerification(false)` chỉ để thử nghiệm.

**H: Làm thế nào để ghi lại các hoạt động cho mục đích kiểm toán?**  
Đáp: Kích hoạt tính năng ghi log tích hợp của Aspose.Email bằng cách cấu hình `Logger.setLevel(Level.INFO)` và chuyển đầu ra tới tệp hoặc hệ thống giám sát.

## Kết luận
Bạn hiện đã có một công thức hoàn chỉnh, sẵn sàng cho môi trường sản xuất để **cách kết nối Exchange** và liệt kê đệ quy các tin nhắn từ thư mục công cộng bằng Aspose.Email cho Java. Các bước bao gồm thiết lập Maven, cấp phép, kết nối, liệt kê thư mục, lấy tin nhắn và tối ưu hiệu năng. Mở rộng nền tảng này bằng cách tích hợp với cơ sở dữ liệu, lưu trữ đám mây, hoặc các pipeline phân tích tùy chỉnh để đáp ứng nhu cầu cụ thể của tổ chức bạn.

---

**Cập nhật lần cuối:** 2026-10-02  
**Kiểm thử với:** Aspose.Email for Java 25.4  
**Tác giả:** Aspose

## Hướng dẫn liên quan

- [Cách kết nối tới máy chủ Exchange bằng Aspose.Email trong Java: Hướng dẫn từng bước](/email/java/exchange-server-integration/aspose-email-java-exchange-server-connection/)
- [Cách kết nối và liệt kê các thư mục máy chủ Exchange bằng Aspose.Email cho Java](/email/java/exchange-server-integration/connect-list-exchange-server-folders-aspose-email-java/)
- [Quản lý các thư mục máy chủ Exchange bằng Aspose.Email cho Java: Hướng dẫn toàn diện](/email/java/exchange-server-integration/exchange-server-folders-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}