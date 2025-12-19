---
date: '2025-12-19'
description: Tìm hiểu cách đặt cờ theo dõi trong Outlook bằng Aspose.Email cho Java,
  bao gồm cách đặt cờ theo dõi Outlook và cách xóa cờ theo dõi Outlook một cách hiệu
  quả.
keywords:
- Manage Outlook follow-up flags
- Set follow-up flags in Outlook with Aspose.Email for Java
- Integrate email task management with Aspose.Email
title: Cách đặt cờ theo dõi trong Outlook bằng Aspose.Email cho Java
url: /vi/java/calendar-appointments/aspose-email-java-outlook-follow-up-flags/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cách Đặt Cờ Theo Dõi trong Outlook bằng Aspose.Email cho Java

## Giới thiệu
Nếu bạn từng gặp khó khăn trong việc theo dõi các email quan trọng, bạn sẽ hiểu giá trị của các cờ theo dõi trong Outlook. Trong hướng dẫn này, chúng tôi sẽ chỉ **cách đặt cờ theo dõi** một cách lập trình bằng Aspose.Email cho Java, đồng thời đề cập đến cách **đặt cờ theo dõi Outlook** cho người nhận, cũng như cách **xóa cờ theo dõi Outlook** khi một nhiệm vụ đã hoàn thành. Khi kết thúc, bạn sẽ có thể tự động hóa việc theo dõi nhiệm vụ, nhắc nhở và ghi chép kiểm toán trực tiếp từ mã Java của mình.

**Bạn sẽ học được**
- Tạo và áp dụng cờ theo dõi trên một tin nhắn Outlook.  
- Đặt cờ theo dõi cho các người nhận cụ thể.  
- Đánh dấu cờ là đã hoàn thành và sau đó xóa nó.  
- Đọc các tùy chọn cờ để báo cáo hoặc tuân thủ.  

Hãy chuẩn bị môi trường trước khi bắt đầu vào mã.

## Câu trả lời nhanh
- **“cách đặt theo dõi” có nghĩa là gì?** Thêm một cờ với ngày bắt đầu, nhắc nhở và hạn chót vào một mục Outlook.  
- **Thư viện nào được yêu cầu?** Aspose.Email cho Java (phiên bản 25.4 trở lên).  
- **Tôi có cần giấy phép không?** Có, cần giấy phép dùng thử hoặc mua để có đầy đủ chức năng.  
- **Tôi có thể chỉ đặt cờ cho người nhận không?** Chắc chắn – sử dụng `FollowUpManager.setFlagForRecipients`.  
- **Có thể xóa cờ sau này không?** Có, gọi `FollowUpManager.clearFlag`.

## Cờ Theo Dõi là gì?
Cờ theo dõi là một tính năng của Outlook đánh dấu một email như một nhiệm vụ, tùy chọn kèm theo ngày bắt đầu, nhắc nhở và hạn chót. Nó giúp bạn và nhóm của mình luôn nắm bắt các hành động đang chờ xử lý.

## Tại sao nên dùng Aspose.Email cho Java?
Aspose.Email cung cấp một API thuần Java hoạt động mà không cần cài đặt Outlook, cho phép bạn thao tác với các tệp .msg, đặt cờ và quản lý nhiệm vụ trên bất kỳ nền tảng nào—lý tưởng cho các dịch vụ backend, quy trình tự động, hoặc tích hợp với công cụ quản lý dự án.

## Yêu cầu trước
- **Aspose.Email cho Java** phiên bản 25.4 hoặc mới hơn.  
- **JDK 16+** đã được cài đặt.  
- IDE tương thích Maven (IntelliJ IDEA, Eclipse, v.v.).  
- Kiến thức cơ bản về Java và hiểu biết về các khái niệm email.

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

### Cách nhận giấy phép
Aspose.Email yêu cầu giấy phép cho việc sử dụng trong môi trường sản xuất:

- **Bản dùng thử miễn phí** – đánh giá 30 ngày.  
- **Giấy phép tạm thời** – kiểm tra mở rộng.  
- **Giấy phép đầy đủ** – thuê bao vĩnh viễn.

Khởi tạo giấy phép trước khi thực hiện bất kỳ thao tác email nào:

```java
License license = new License();
license.setLicense("path/to/Aspose.Total.Java.lic");
```

## Hướng dẫn triển khai

### Cách Đặt Cờ Theo Dõi (Tính năng 1)
#### Tổng quan
Phần này hướng dẫn bạn tạo một tin nhắn Outlook, xác định ngày bắt đầu/nhắc nhở/hạn chót, và áp dụng cờ theo dõi.

#### Bước 1: Tạo và Khởi tạo Tin Nhắn
```java
MailMessage mailMsg = new MailMessage();
mailMsg.setSender(new MailAddress("AETest12@gmail.com"));
mailMsg.getTo().addMailAddress(new MailAddress("receiver@gmail.com"));
mailMsg.setBody("This message will test if follow up options can be added to a new mapi message.");
MapiMessage mapi = MapiMessage.fromMailMessage(mailMsg);
```
*Đầu tiên chúng tôi tạo một `MailMessage`, thiết lập người gửi/người nhận, sau đó chuyển đổi nó thành `MapiMessage` để thao tác cờ.*

#### Bước 2: Xác định Ngày Theo Dõi
```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 14, 40, 0);
Date dtStartDate = calendar.getTime();
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
calendar.add(Calendar.DATE, 1);
Date dtDueDate = calendar.getTime();
```
*Ở đây chúng tôi thiết lập ngày bắt đầu, nhắc nhở và hạn chót bằng lớp `Calendar`.*

#### Bước 3: Áp dụng Tùy chọn Theo Dõi
```java
FollowUpOptions options = new FollowUpOptions("Follow Up", dtStartDate, dtDueDate, dtReminderDate);
FollowUpManager.setOptions(mapi, options);
```
*Đối tượng `FollowUpOptions` chứa tất cả chi tiết cờ, chúng tôi áp dụng chúng bằng `FollowUpManager.setOptions`.*

#### Bước 4: Lưu Tin Nhắn
```java
mapi.save(outputDir + "SetFollowUpflag_out.msg");
```
*Tin nhắn được lưu dưới dạng tệp `.msg` kèm cờ.*

### Cách Đặt Cờ Theo Dõi Outlook cho Người Nhận (Tính năng 2)
#### Tổng quan
Đôi khi bạn cần chỉ gắn cờ cho người nhận. Ví dụ này đánh dấu tin nhắn là bản nháp trước, sau đó thêm cờ.

#### Bước 1: Đánh dấu là Bản Nháp
```java
mapi.setMessageFlags(MapiMessageFlags.MSGFLAG_UNSENT);
```
*Đánh dấu tin nhắn chưa gửi đảm bảo Outlook xử lý nó như một bản nháp.*

#### Bước 2: Đặt Cờ cho Người Nhận
```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
FollowUpManager.setFlagForRecipients(mapi, "Follow up", dtReminderDate);
```
*Cờ hiện chỉ hiển thị cho người nhận.*

### Cách Đánh Dấu Cờ Theo Dõi Outlook là Đã Hoàn Thành (Tính năng 3)
#### Tổng quan
Khi một nhiệm vụ đã xong, bạn có thể lập trình đánh dấu cờ là đã hoàn thành.

#### Bước 1: Tải Tin Nhắn
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
```

#### Bước 2: Đánh Dấu là Đã Hoàn Thành và Lưu
```java
FollowUpManager.markAsCompleted(mapi);
mapi.save(outputDir + "MarkedCompleted_out.msg");
```
*Trạng thái cờ thay đổi thành “Completed” và tệp đã cập nhật được lưu.*

### Cách Xóa Cờ Theo Dõi Outlook (Tính năng 4)
#### Tổng quan
Nếu cờ không còn cần thiết, bạn có thể xóa hoàn toàn.

#### Bước 1: Tải và Xóa Cờ
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpManager.clearFlag(mapi);
mapi.save(outputDir + "FollowUpFlagRemoved_out.msg");
```
*Tin nhắn được lưu mà không có cờ theo dõi nào.*

### Cách Đọc Các Tùy chọn Cờ Theo Dõi (Tính năng 5)
#### Tổng quan
Đối với việc kiểm toán hoặc báo cáo, bạn có thể cần đọc các cài đặt cờ hiện có.

#### Bước 1: Lấy Các Tùy chọn
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpOptions options = FollowUpManager.getOptions(mapi);
```
*Đối tượng `options` hiện chứa ngày bắt đầu, hạn chót và nhắc nhở, cùng tiêu đề cờ.*

## Ứng dụng Thực tiễn
- **Tích hợp Quản lý Nhiệm vụ:** Đồng bộ email có cờ với Jira, Trello hoặc Azure Boards.  
- **Nhắc nhở Tự động:** Tạo email nhắc nhở hàng ngày cho các theo dõi còn tồn đọng.  
- **Kiểm toán Tuân thủ:** Xuất dữ liệu cờ cho báo cáo quy định.

## Các Yếu tố Hiệu năng
- **Tính toán Ngày:** Tính ngày một lần cho mỗi lô thay vì trong vòng lặp.  
- **Quản lý Tài nguyên:** Đóng mọi luồng hoặc handle file sau khi lưu tin nhắn.  
- **Sử dụng Bộ nhớ:** Xử lý hộp thư lớn theo từng khối để tránh áp lực bộ nhớ heap.

## Các Vấn đề Thường gặp và Giải pháp
| Vấn đề | Nguyên nhân | Giải pháp |
|-------|-------|-----|
| Cờ không hiển thị trong Outlook | Tin nhắn được lưu mà không có `MessageFlags` đúng | Đảm bảo `setMessageFlags` được đặt thành `MSGFLAG_UNSENT` trước khi áp dụng cờ cho người nhận. |
| Lưu gây ra `AccessDeniedException` | Đường dẫn tệp không đúng hoặc thiếu quyền ghi | Kiểm tra thư mục đầu ra tồn tại và ứng dụng có quyền ghi. |
| Ngày bị lệch một ngày | Không khớp múi giờ | Sử dụng `TimeZone.getTimeZone("GMT")` hoặc múi giờ địa phương một cách nhất quán. |

## Câu hỏi Thường gặp
**Q: Aspose.Email cho Java là gì?**  
A: Đó là một API thuần Java cho phép bạn tạo, đọc và thao tác các tệp email (MSG, EML, v.v.) mà không cần cài đặt Outlook.

**Q: Làm sao để có được giấy phép dùng thử miễn phí?**  
A: Truy cập trang [Aspose website](https://releases.aspose.com/email/java/) để tải bản dùng thử 30 ngày.

**Q: Tôi có thể đặt nhiều cờ theo dõi trên một tin nhắn không?**  
A: Outlook chỉ hỗ trợ một cờ cho mỗi tin nhắn, nhưng bạn có thể lưu dữ liệu nhiệm vụ bổ sung trong các thuộc tính MAPI tùy chỉnh.

**Q: Tin nhắn của tôi không được lưu sau khi đặt cờ. Tôi nên kiểm tra gì?**  
A: Xác nhận đường dẫn `outputDir` hợp lệ và ứng dụng có quyền ghi vào vị trí đó.

**Q: Làm sao để xóa cờ khỏi nhiều tin nhắn cùng lúc?**  
A: Duyệt qua bộ sưu tập tin nhắn và gọi `FollowUpManager.clearFlag` cho mỗi `MapiMessage`.

## Tài nguyên
- [Documentation](https://reference.aspose.com/email/java/)
- [Download Aspose.Email for Java](https://releases.aspose.com/email/java/)
- [Aspose.Email Free Trial](https://purchase.aspose.com/purchase/free-trial/aspose-email-java)

**Last Updated:** 2025-12-19  
**Tested With:** Aspose.Email for Java 25.4 (jdk16)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}