---
date: '2026-03-20'
description: Tìm hiểu cách xuất PST lịch Outlook bằng Aspose.Email cho Java – tạo
  mục lịch MAPI, thiết lập lịch lặp, thêm người tham dự và lưu vào PST.
keywords:
- Create MAPI Calendar Java
- Aspose.Email Java Calendar
- Java PST File Save
title: Xuất lịch Outlook PST bằng Aspose.Email – Java
url: /vi/java/calendar-appointments/create-save-mapi-calendar-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Xuất lịch Outlook PST với Aspose.Email – Java

## Giới thiệu

Bạn đang muốn tối ưu hoá tự động hoá lịch trong các ứng dụng Java và cần **export Outlook calendar PST**? Với **Aspose.Email for Java**, bạn có thể **create MAPI calendar Java** items, định nghĩa mẫu lặp lại, thêm người tham dự, và **save calendar to PST** chỉ với vài dòng code. Hướng dẫn này sẽ đưa bạn qua toàn bộ quy trình—từ cài đặt thư viện đến tạo một mục lịch hoạt động đầy đủ sẵn sàng phân phối.

### Những gì bạn sẽ học
- Cách **create MAPI calendar Java** events bằng Aspose.Email.  
- Cấu hình mẫu lặp lại hàng ngày, hàng tuần hoặc tùy chỉnh.  
- Thêm recipients (organizers, attendees) vào lời mời lịch của bạn.  
- Lưu trữ mục lịch bằng **saving calendar to PST** để tương thích với Outlook.  
- Cách **automate meeting scheduling** với mã có thể tái sử dụng.

## Câu trả lời nhanh
- **Thư viện nào?** Aspose.Email for Java  
- **Mục tiêu chính?** Export Outlook calendar PST và **save calendar to PST**  
- **Yêu cầu trước?** Java 8+, Maven, giấy phép Aspose.Email  
- **Thời gian triển khai điển hình?** 10‑15 phút cho một sự kiện cơ bản  
- **Có thể thêm recurrence không?** Có – hàng ngày, hàng tuần, hàng tháng, v.v.

## Export Outlook calendar PST

Trong phần này chúng ta tập trung vào quy trình end‑to‑end cho phép bạn **export Outlook calendar PST**. Sau khi tạo đối tượng MAPI calendar, bước cuối cùng là lưu nó vào một file PST mà Outlook có thể đọc trực tiếp.

## Tại sao nên dùng Aspose.Email cho tự động hoá lịch?

- **Full Outlook compatibility** – các mục được tạo hoạt động trong Outlook, OWA và các client di động.  
- **Rich recurrence support** – hỗ trợ mẫu hàng ngày, hàng tuần, hàng tháng và tùy chỉnh ngay từ đầu.  
- **No external dependencies** – thư viện Java thuần, không cần COM interop.  
- **High performance** – xử lý hiệu quả các file PST lớn và các thao tác bulk.  
- **Automate meeting scheduling** – nhúng logic này vào batch jobs hoặc web services để tự động tạo hàng trăm lời mời.

## Yêu cầu trước

### Thư viện cần thiết
- **Aspose.Email for Java**: Phiên bản 25.4 trở lên.

### Yêu cầu thiết lập môi trường
- Một IDE Java như IntelliJ IDEA hoặc Eclipse.  
- Maven đã được cài đặt để quản lý dependencies.

### Kiến thức nền tảng
- Kỹ năng lập trình Java cơ bản.  
- Hiểu biết về các khái niệm hướng đối tượng.

## Cài đặt Aspose.Email cho Java

Thêm dependency Aspose.Email Maven vào `pom.xml` của bạn:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Mua giấy phép

Aspose.Email cung cấp bản dùng thử miễn phí, nhưng giấy phép sẽ mở khóa tất cả các tính năng:

- **Free Trial**: Kiểm tra không giới hạn trong 30 ngày.  
- **Temporary License**: Yêu cầu qua [Aspose's website](https://purchase.aspose.com/temporary-license/) nếu bạn cần thời gian thêm.  
- **Purchase**: Mua giấy phép vĩnh viễn từ [purchase page](https://purchase.aspose.com/buy).

### Khởi tạo cơ bản

Sau khi thêm dependency, khởi tạo thư viện với file giấy phép của bạn:

```java
com.aspose.email.License license = new com.aspose.email.License();
license.setLicense("path_to_your_license.lic");
```

## Hướng dẫn triển khai

Bây giờ bạn đã sẵn sàng, hãy **create MAPI calendar Java** và **save calendar to PST**.

### Tạo MAPI Calendar với Recurrence

#### Tổng quan

Chúng ta sẽ xây dựng một sự kiện lịch, áp dụng recurrence hàng ngày, thêm attendees, và cuối cùng lưu vào file PST.

#### Thực hiện từng bước

1. **Initialize Date and Recurrence Pattern**  

   Đầu tiên, xác định thời gian bắt đầu và thiết lập recurrence hàng ngày:

   ```java
   import java.util.Date;

   // Add hours to current date to get the start time
   Date startDate = addHours(new Date(), 12);

   MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
   recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
   ```

   *Explanation*: `MapiCalendarEventRecurrence` chứa chi tiết recurrence; chúng ta chọn mẫu hàng ngày qua `MapiCalendarDailyRecurrencePattern`.

2. **Set Up Recipients**  

   Thêm những người sẽ nhận lời mời họp:

   ```java
   import com.aspose.email.MapiRecipientCollection;
   import com.aspose.email.MapiRecipientType;

   MapiRecipientCollection recColl = new MapiRecipientCollection();
   recColl.add("recipient@gmail.com", "Attendee Name", MapiRecipientType.MAPI_TO);
   ```

   *Explanation*: `MapiRecipientCollection` lưu trữ mỗi attendee; `MAPI_TO` đánh dấu họ là người nhận chính.

3. **Create the MAPI Calendar Item**  

   Xây dựng đối tượng lịch với tất cả các chi tiết cần thiết:

   ```java
   import com.aspose.email.MapiCalendar;

   MapiCalendar calendar = new MapiCalendar(
       "Organizer Name", 
       "Meeting Subject", 
       "Meeting Location", 
       startDate, 
       addHours(startDate, 1), // End time is one hour after start
       "Event Description",
       recColl,
       recurrence
   );
   ```

   *Explanation*: Constructor yêu cầu organizer, subject, location, thời gian bắt đầu/kết thúc, description, danh sách recipients và recurrence.

4. **Save to PST File**  

   Cuối cùng, lưu lịch bằng **saving calendar to PST**:

   ```java
   import com.aspose.email.PersonalStorage;
   import com.aspose.email.FolderInfo;
   import com.aspose.email.StandardIpmFolder;

   PersonalStorage pst = PersonalStorage.create("calendar.pst", 0);
   FolderInfo calendarFolder = pst.createPredefinedFolder("Calendar", StandardIpmFolder.CALendars);

   // Save the MAPI Calendar item
   calendarFolder.addMapiMessageItem(calendar);
   ```

   *Explanation*: `PersonalStorage.create` tạo một file PST mới, và `addMapiMessageItem` chèn mục lịch vào thư mục "Calendar".

### Mẹo khắc phục sự cố
- Kiểm tra đường dẫn giấy phép; giấy phép không hợp lệ sẽ giới hạn chức năng.  
- Đảm bảo địa chỉ email của recipients được định dạng đúng để tránh lỗi lời mời.  
- Đóng PST (`pst.dispose()`) sau khi thực hiện để giải phóng handle file.

## Ứng dụng thực tiễn

Dưới đây là các kịch bản thường gặp mà **creating MAPI calendar Java** và **saving calendar to PST** tỏa sáng:

1. **Automated Meeting Scheduling** – Tạo lời mời họp định kỳ cho các đội dự án mà không cần thao tác thủ công.  
2. **Event Management Platforms** – Xuất các phiên hội nghị dưới dạng mục lịch tương thích Outlook.  
3. **CRM Integration** – Đồng bộ các cuộc hẹn khách hàng từ hệ thống CRM trực tiếp vào Outlook qua file PST.

## Các lưu ý về hiệu năng

- **Resource Management**: Dispose các đối tượng `PersonalStorage` sau khi dùng để tránh khóa file.  
- **Batch Processing**: Đối với khối lượng lớn, xử lý các mục lịch bất đồng bộ hoặc theo lô để giảm tiêu thụ bộ nhớ.  

## Kết luận

Bạn đã học cách **export Outlook calendar PST** bằng cách tạo các đối tượng MAPI calendar Java, cấu hình recurrence, thêm attendees, và **save calendar to PST** sử dụng Aspose.Email. Cách tiếp cận này cho phép các ứng dụng Java của bạn tự động hoá quy trình lập lịch phức tạp với khả năng tương thích Outlook.

Để khám phá sâu hơn, xem tài liệu chính thức tại [documentation](https://reference.aspose.com/email/java/).

## Phần FAQ

### Q: Tôi có thể tạo mẫu recurrence hàng tuần không?
- **A**: Có! Sử dụng `MapiCalendarWeeklyRecurrencePattern` để định nghĩa lặp lại hàng tuần.

### Q: Làm sao xử lý các ngoại lệ trong recurrence của sự kiện?
- **A**: Gọi `setExceptions()` trên đối tượng recurrence để chỉ định các ngày không tuân theo mẫu.

### Q: Có thể cập nhật một mục lịch đã tồn tại không?
- **A**: Chắc chắn. Tải mục từ PST, sửa các thuộc tính, và lưu lại.

### Q: Tôi có thể mã hoá file PST không?
- **A**: Có, Aspose.Email cho phép bạn đặt mật khẩu cho `PersonalStorage` khi tạo PST.

### Q: Nếu muốn thêm tệp đính kèm vào sự kiện lịch thì sao?
- **A**: Dùng `calendar.getAttachments().addFileAttachment("path/to/file")` trước khi lưu.

## Tài nguyên

- [Aspose.Email Documentation](https://reference.aspose.com/email/java/)
- [Download Aspose.Email for Java](https://releases.aspose.com/email/java/)
- [Purchase a License](https://purchase.aspose.com/buy)
- [Free Trial Version](https://releases.aspose.com/email/java/)
- [Request a Temporary License](https://purchase.aspose.com/temporary-license/)
- [Aspose Support Forum](https://forum.aspose.com/c/email/10)

---

**Last Updated:** 2026-03-20  
**Tested With:** Aspose.Email for Java 25.4 (JDK 16)  
**Author:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}