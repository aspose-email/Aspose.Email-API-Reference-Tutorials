---
date: '2026-09-17'
description: Cách tạo calendar invitation với Aspose.Email for Java cho phép bạn chia
  sẻ lịch, thiết lập delegate permissions và gửi sharing emails programmatically.
keywords:
- how to create calendar invitation
- calendar sharing invitation
- Aspose.Email Java
- delegate calendar permissions
lastmod: '2026-09-17'
og_description: Cách tạo calendar invitation với Aspose.Email for Java cho phép bạn
  programmatically chia sẻ lịch, thiết lập delegate permissions và gửi sharing emails
  qua Exchange Web Services, cải thiện team collaboration.
og_image_alt: Guide showing how to create calendar invitation with Aspose.Email for
  Java
og_title: Cách tạo calendar invitation với Aspose.Email for Java
schemas:
- author: Aspose
  dateModified: '2026-09-17'
  description: How to create calendar invitation with Aspose.Email for Java lets you
    share calendars, set delegate permissions, and send sharing emails programmatically.
  headline: How to create calendar invitation with Aspose.Email for Java
  type: TechArticle
- description: How to create calendar invitation with Aspose.Email for Java lets you
    share calendars, set delegate permissions, and send sharing emails programmatically.
  name: How to create calendar invitation with Aspose.Email for Java
  steps:
  - name: Install JDK if you haven't already. You can download it from [Oracle's official
      site](https://www.oracle.com/java/technologies/javase-downloads.html).
    text: Install JDK if you haven't already. You can download it from [Oracle's official
      site](https://www.oracle.com/java/technologies/javase-downloads.html).
  - name: Ensure Maven is installed and configured on your machine.
    text: Ensure Maven is installed and configured on your machine.
  - name: Choose an IDE such as IntelliJ IDEA or Eclipse for easier development.
    text: Choose an IDE such as IntelliJ IDEA or Eclipse for easier development.
  - name: '**Corporate meetings** – Let team members view meeting schedules without
      giving full mailbox rights.'
    text: '**Corporate meetings** – Let team members view meeting schedules without
      giving full mailbox rights.'
  - name: '**Project management** – Project leads can monitor timelines while developers
      retain control of their own calendars.'
    text: '**Project management** – Project leads can monitor timelines while developers
      retain control of their own calendars.'
  - name: '**Event planning** – Vendors receive a **calendar sharing email** to coordinate
      logistics without exposing internal details.'
    text: '**Event planning** – Vendors receive a **calendar sharing email** to coordinate
      logistics without exposing internal details.'
  type: HowTo
- questions:
  - answer: It’s a comprehensive library for handling emails, calendars, and contacts
      in Java applications, supporting Outlook, Exchange, and other protocols.
    question: What is Aspose.Email for Java used for?
  - answer: Install JDK 16+, Maven, add the Aspose.Email dependency to `pom.xml`,
      and obtain a license (trial or full).
    question: How do I set up my environment for using Aspose.Email?
  - answer: Yes, but verify the service URL and permission levels match your server’s
      configuration.
    question: Can I use this code with other versions of Exchange Online?
  - answer: Check network connectivity, credentials, and that the delegate user has
      valid permissions. Review exception details for clues.
    question: What should I do if the calendar sharing invitation fails to send?
  - answer: Absolutely – replace `ExchangeDelegateFolderPermissionLevel.Reviewer`
      with `Editor`, `Author`, or `Owner` as needed.
    question: Is it possible to add additional permissions like editing or full access?
  type: FAQPage
tags:
- calendar sharing
- Aspose.Email
- Java email API
- delegate permissions
- EWS client
title: Cách tạo calendar invitation với Aspose.Email for Java
url: /vi/java/calendar-appointments/create-send-calendar-invitations-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Quản lý chia sẻ lịch: Hướng dẫn Aspose.Email cho Java

## Giới thiệu về quản lý chia sẻ lịch
Quản lý lời mời chia sẻ lịch có thể là một nhiệm vụ phức tạp, đặc biệt khi làm việc với nhiều người dùng trên các nền tảng khác nhau. Trong hướng dẫn này, bạn sẽ **create calendar sharing invitation** với Aspose.Email cho Java, bao gồm mọi thứ từ việc tạo quyền ủy quyền đến việc gửi email chia sẻ lịch. Khi kết thúc, bạn sẽ có thể thiết lập quyền ủy quyền, **configure calendar permissions**, và tối ưu hoá sự hợp tác trong tổ chức của mình.

**Bạn sẽ học được**
- Cách khởi tạo client EWS với Aspose.Email cho Java  
- Tạo người dùng ủy quyền và **set delegate permissions**  
- **Create delegate access** và cấu hình quyền lịch  
- Gửi một **calendar sharing email** (lời mời) một cách lập trình  
- Các kịch bản thực tế nơi các tính năng này mang lại giá trị  

Trước khi chúng ta bắt đầu, hãy chắc chắn rằng bạn đã có mọi thứ cần thiết.

## Câu trả lời nhanh
- **What is the primary purpose of this guide?** Để chỉ cách **create calendar sharing invitation** bằng Aspose.Email cho Java.  
- **Which library version is required?** Aspose.Email for Java 25.4 (JDK 16 classifier).  
- **Do I need a license?** Có – cần giấy phép dùng thử hoặc đầy đủ cho môi trường sản xuất.  
- **What environment is needed?** JDK 16+, Maven, và một tài khoản Exchange Online.  
- **Can I use this with other Exchange servers?** Có, nhưng bạn có thể cần điều chỉnh URL dịch vụ và mức quyền.

## Lời mời chia sẻ lịch là gì?
Lời mời chia sẻ lịch là một tin nhắn email cấp cho người dùng khác quyền xem (hoặc chỉnh sửa) lịch của bạn mà không cung cấp toàn bộ quyền hộp thư. Nó cho phép các thành viên trong nhóm xem lịch trình của bạn, đề xuất cuộc họp, hoặc quản lý sự kiện trong khi vẫn bảo mật hộp thư của bạn.

## Tại sao cần cấu hình quyền lịch?
Cấu hình quyền lịch cho phép bạn kiểm soát chính xác những gì một ủy quyền có thể làm — họ chỉ có thể đọc sự kiện, đề xuất sự kiện mới, hoặc chỉnh sửa các mục hiện có. Cài đặt quyền phù hợp bảo vệ thông tin nhạy cảm đồng thời cho phép hợp tác hiệu quả. Ví dụ, cấp quyền chỉ đọc ngăn ngừa các thay đổi vô tình, trong khi quyền chỉnh sửa cho phép ủy quyền lên lịch hoặc sửa đổi các cuộc họp thay bạn.

## Yêu cầu trước
- **Java Development Kit (JDK):** Phiên bản 16 hoặc mới hơn.  
- **Maven:** Để quản lý phụ thuộc và xây dựng dự án.  
- **Aspose.Email for Java Library:** Phiên bản 25.4 hỗ trợ JDK 16.  

### Yêu cầu thiết lập môi trường
1. Cài đặt JDK nếu bạn chưa có. Bạn có thể tải xuống từ [Oracle's official site](https://www.oracle.com/java/technologies/javase-downloads.html).  
2. Đảm bảo Maven đã được cài đặt và cấu hình trên máy của bạn.  
3. Chọn một IDE như IntelliJ IDEA hoặc Eclipse để phát triển dễ dàng hơn.

### Kiến thức yêu cầu
- Kiến thức cơ bản về lập trình Java  
- Quen thuộc với các phụ thuộc Maven  
- Tùy chọn: Kinh nghiệm với Exchange Web Services (EWS)

## Cài đặt Aspose.Email cho Java
### Cấu hình Maven
Thêm phụ thuộc sau vào tệp `pom.xml` của bạn:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Lấy giấy phép
Aspose.Email for Java yêu cầu giấy phép để hoạt động đầy đủ. Bạn có thể:
- **Free trial:** Tải xuống từ [Aspose's release page](https://releases.aspose.com/email/java/).  
- **Temporary license:** Yêu cầu một khóa tạm thời trên trang web Aspose.  
- **Purchase:** Nhận giấy phép vĩnh viễn cho triển khai sản xuất.

### Khởi tạo và thiết lập cơ bản
Khi Maven đã giải quyết phụ thuộc, khởi tạo client EWS:

`ExchangeService` là lớp chính được sử dụng để giao tiếp với Exchange Web Services.  

```java
IEWSClient client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser", "pwd", "domain");
```

## Cách tạo lời mời chia sẻ lịch
Để tạo lời mời chia sẻ lịch, bạn đầu tiên kết nối tới Exchange bằng client `ExchangeService`, sau đó định nghĩa một ủy quyền với mức quyền mong muốn, và cuối cùng soạn một `MailMessage` bao gồm yêu cầu chia sẻ. Các bước sau minh họa quy trình này trong Java.

Dưới đây chúng tôi sẽ đề cập đến hai tính năng chính: tạo và gửi lời mời chia sẻ lịch, và **set delegate permissions** cho quyền truy cập lịch.

### Tính năng 1: tạo và gửi lời mời chia sẻ lịch
#### Tổng quan
Tính năng này hướng dẫn bạn qua việc khởi tạo client, **create delegate access**, và gửi email lời mời.

#### Triển khai từng bước
##### 1️⃣ Khởi tạo client EWS
`ExchangeService` đại diện cho kết nối tới máy chủ Exchange và được sử dụng để gửi và nhận tin nhắn.

```java
IEWSClient client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser", "pwd", "domain");
```  
Điều này kết nối ứng dụng Java của bạn với Exchange Online.

##### 2️⃣ Tạo người dùng ủy quyền
`DelegateUser` xác định địa chỉ email của ủy quyền và mức quyền sẽ được cấp.

```java
ExchangeDelegateUser delegateUser = new ExchangeDelegateUser("sharingfrom@domain.com", ExchangeDelegateFolderPermissionLevel.NotSpecified);
delegateUser.getFolderPermissions().setCalendarFolderPermissionLevel(ExchangeDelegateFolderPermissionLevel.Reviewer);
client.delegateAccess(delegateUser, "sharingfrom@domain.com");
```  
Ở đây chúng tôi **create delegate access** và gán mức `Reviewer`, cho phép ủy quyền xem các mục lịch.

##### 3️⃣ Gửi lời mời chia sẻ lịch
`MailMessage` tạo email chứa lời mời chia sẻ lịch.

```java
MapiMessage mapiMessage = client.createCalendarSharingInvitationMessage("sharingfrom@domain.com");

MailConversionOptions options = new MailConversionOptions();
options.setConvertAsTnef(true);

MailMessage mail = mapiMessage.toMailMessage(options);
client.send(mail);
```  
Mã này xây dựng một **calendar sharing email** (lời mời) và gửi nó qua client EWS.

### Tính năng 2: quyền truy cập lịch của ủy quyền
#### Tổng quan
Phần này cho thấy cách **configure calendar permissions** và đảm bảo ủy quyền có quyền phù hợp.

#### Các bước thực hiện
##### 1️⃣ Khởi tạo client EWS (tái sử dụng)
`ExchangeService` có thể được tái sử dụng cho nhiều thao tác sau khi cấu hình ban đầu.

```java
IEWSClient client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser", "pwd", "domain");
```  

##### 2️⃣ Tạo và đặt quyền ủy quyền
`ExchangeDelegateFolderPermissionLevel` liệt kê các mức truy cập mà ủy quyền có thể có đối với thư mục lịch.

```java
ExchangeDelegateUser delegateUser = new ExchangeDelegateUser("sharingfrom@domain.com", ExchangeDelegateFolderPermissionLevel.NotSpecified);
delegateUser.getFolderPermissions().setCalendarFolderPermissionLevel(ExchangeDelegateFolderPermissionLevel.Reviewer);

client.delegateAccess(delegateUser, "sharingfrom@domain.com");
```  
Đoạn mã này **sets delegate permissions** để người dùng có thể xem các mục lịch mà không cần quyền truy cập toàn bộ hộp thư.

## Cách cấu hình quyền lịch cho ủy quyền
Khi một ủy quyền cần quyền vượt quá chỉ đọc, bạn có thể điều chỉnh `ExchangeDelegateFolderPermissionLevel` để cấp quyền chỉnh sửa, tác giả, hoặc chủ sở hữu. Chọn mức tối thiểu đáp ứng nhu cầu kinh doanh để duy trì bảo mật đồng thời cung cấp chức năng cần thiết. Ví dụ, gán mức Editor cho phép ủy quyền tạo, sửa đổi và xóa sự kiện, trong khi mức Reviewer chỉ cho phép xem.

- `Reviewer` – quyền chỉ đọc.  
- `Editor` – quyền đọc/ghi.  
- `Author` – tạo và đọc, nhưng không thể xóa.  
- `Owner` – kiểm soát đầy đủ, bao gồm thay đổi quyền.  

**Mẹo:** Sử dụng mức quyền tối thiểu đáp ứng yêu cầu kinh doanh để giữ dữ liệu lịch của bạn an toàn.

## Ứng dụng thực tiễn
Kịch bản thực tế nơi **manage calendar sharing** tỏa sáng:
1. **Corporate meetings** – Cho phép các thành viên trong nhóm xem lịch họp mà không cấp toàn quyền hộp thư.  
2. **Project management** – Các trưởng dự án có thể giám sát tiến độ trong khi các nhà phát triển vẫn kiểm soát lịch cá nhân của họ.  
3. **Event planning** – Các nhà cung cấp nhận được **calendar sharing email** để phối hợp logistics mà không tiết lộ chi tiết nội bộ.

## Lưu ý về hiệu năng
- **Memory management:** Giải phóng các đối tượng `MailMessage` lớn kịp thời trong các ứng dụng có khối lượng cao.  
- **Exception handling:** Bao bọc các cuộc gọi mạng trong khối try‑catch để xử lý lỗi kết nối một cách nhẹ nhàng.  
- **Library updates:** Aspose.Email for Java hỗ trợ hơn 50 giao thức và có thể xử lý lịch với tới 10.000 mục mà không cần tải toàn bộ tệp vào bộ nhớ, vì vậy hãy cập nhật thư viện thường xuyên để hưởng lợi từ cải thiện hiệu năng và sửa lỗi.

## Các vấn đề thường gặp và giải pháp
| Vấn đề | Nguyên nhân có thể | Giải pháp |
|-------|---------------------|----------|
| Lời mời không nhận được | Bộ lọc spam hoặc địa chỉ email không đúng | Xác minh địa chỉ người nhận và thêm miền gửi vào danh sách an toàn |
| Quyền không được áp dụng | Sử dụng `ExchangeDelegateFolderPermissionLevel` sai | Kiểm tra lại mức quyền phù hợp với quyền truy cập yêu cầu |
| Ngoại lệ runtime trên `createCalendarSharingInvitationMessage` | Thiếu giấy phép hoặc thư viện lỗi thời | Đảm bảo tải giấy phép hợp lệ và sử dụng phiên bản Aspose.Email mới nhất |

## Câu hỏi thường gặp
**Q: Aspose.Email cho Java được dùng để làm gì?**  
A: Đây là thư viện toàn diện để xử lý email, lịch và danh bạ trong các ứng dụng Java, hỗ trợ Outlook, Exchange và các giao thức khác.

**Q: Làm thế nào để thiết lập môi trường sử dụng Aspose.Email?**  
A: Cài đặt JDK 16+, Maven, thêm phụ thuộc Aspose.Email vào `pom.xml`, và lấy giấy phép (dùng thử hoặc đầy đủ).

**Q: Tôi có thể sử dụng mã này với các phiên bản khác của Exchange Online không?**  
A: Có, nhưng hãy xác minh URL dịch vụ và mức quyền phù hợp với cấu hình máy chủ của bạn.

**Q: Tôi nên làm gì nếu lời mời chia sẻ lịch không gửi được?**  
A: Kiểm tra kết nối mạng, thông tin đăng nhập, và đảm bảo người dùng ủy quyền có quyền hợp lệ. Xem chi tiết ngoại lệ để tìm manh mối.

**Q: Có thể thêm các quyền bổ sung như chỉnh sửa hoặc truy cập đầy đủ không?**  
A: Chắc chắn – thay thế `ExchangeDelegateFolderPermissionLevel.Reviewer` bằng `Editor`, `Author`, hoặc `Owner` tùy nhu cầu.

## Kết luận
Bây giờ bạn đã có một giải pháp hoàn chỉnh, đầu‑tới‑cuối cho **create calendar sharing invitation** với Aspose.Email cho Java. Bằng cách khởi tạo client EWS, **create delegate access**, **set delegate permissions**, và gửi một **calendar sharing email**, bạn có thể tự động hoá sự hợp tác trong toàn tổ chức.

**Các bước tiếp theo**
- Thử nghiệm các mức quyền khác (Editor, Owner).  
- Tích hợp logic này vào hệ thống lập lịch hoặc HR hiện có của bạn.  
- Khám phá các tính năng bổ sung của Aspose.Email như sự kiện lặp lại hoặc yêu cầu họp.

---

**Cập nhật lần cuối:** 2026-09-17  
**Được kiểm tra với:** Aspose.Email for Java 25.4 (JDK 16 classifier)  
**Tác giả:** Aspose

## Các hướng dẫn liên quan

- [Cách tạo mục lịch Java bằng Aspose.Email](/email/java/calendar-appointments/create-save-calendar-items-aspose-email-java/)
- [Aspose Email Java lọc cuộc hẹn Exchange theo ngày](/email/java/calendar-appointments/aspose-email-java-filter-exchange-appointments-by-date/)
- [Tạo lịch Exchange Java với Aspose.Email – Hướng dẫn đầy đủ](/email/java/calendar-appointments/mastering-exchange-calendar-management-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}