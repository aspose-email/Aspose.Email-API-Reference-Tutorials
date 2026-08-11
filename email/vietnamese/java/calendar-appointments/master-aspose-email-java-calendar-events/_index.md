---
date: '2026-08-01'
description: Tìm hiểu cách xuất lịch sang PST với Aspose.Email for Java, bao gồm cách
  thêm người tham dự, đặt ngày bắt đầu và kết thúc, và quản lý các cuộc hẹn một cách
  hiệu quả.
keywords:
- export calendar to pst
- export recurring appointments
- Aspose.Email Java Calendar Events
lastmod: '2026-08-01'
og_description: Xuất lịch sang PST bằng Aspose.Email for Java. Tìm hiểu từng bước
  cách tạo cuộc hẹn, thêm người tham dự và tạo file Outlook PST.
og_image_alt: 'Developer guide: Export calendar to PST using Aspose.Email for Java'
og_title: Xuất lịch sang PST – Hướng dẫn đầy đủ với Aspose.Email for Java
schemas:
- author: Aspose
  dateModified: '2026-08-01'
  description: Learn how to export calendar to PST with Aspose.Email for Java, including
    how to add attendees, set start and end dates, and manage appointments efficiently.
  headline: Export calendar to PST with Aspose.Email for Java
  type: TechArticle
- description: Learn how to export calendar to PST with Aspose.Email for Java, including
    how to add attendees, set start and end dates, and manage appointments efficiently.
  name: Export calendar to PST with Aspose.Email for Java
  steps:
  - name: '**Free Trial**: Visit the [Aspose download page](https://releases.aspose.com/email/java/)
      for a temporary license.'
    text: '**Free Trial**: Visit the [Aspose download page](https://releases.aspose.com/email/java/)
      for a temporary license.'
  - name: '**Temporary License**: Apply via the [purchase page](https://purchase.aspose.com/temporary-license/).'
    text: '**Temporary License**: Apply via the [purchase page](https://purchase.aspose.com/temporary-license/).'
  - name: '**Purchase License**: Consider purchasing from [Aspose''s purchase portal](https://purchase.aspose.com/buy)
      for long‑term use.'
    text: '**Purchase License**: Consider purchasing from [Aspose''s purchase portal](https://purchase.aspose.com/buy)
      for long‑term use.'
  - name: '**Business Scheduling** – Automate internal meeting creation and distribution.'
    text: '**Business Scheduling** – Automate internal meeting creation and distribution.'
  - name: '**Event Management** – Track conferences, workshops, and participant lists.'
    text: '**Event Management** – Track conferences, workshops, and participant lists.'
  - name: '**CRM Integration** – Sync appointments with customer relationship tools.'
    text: '**CRM Integration** – Sync appointments with customer relationship tools.'
  - name: '**Project Planning** – Store project milestones as calendar items.'
    text: '**Project Planning** – Store project milestones as calendar items.'
  - name: '**Remote Team Collaboration** – Generate PST files for offline sharing.'
    text: '**Remote Team Collaboration** – Generate PST files for offline sharing.'
  type: HowTo
- questions:
  - answer: Add the Maven dependency shown above, obtain a license, and follow the
      steps in this guide to create and export calendar events.
    question: How do I get started with Aspose.Email for Java?
  - answer: Yes, change the `pstFilePath` variable in `createPSTWithCalendarEvents()`
      to any valid path on your system.
    question: Can I customize the PST file name and location?
  - answer: Absolutely – `MapiCalendar` exposes a `RecurrencePattern` property that
      you can configure before saving.
    question: Is it possible to add recurrence patterns to appointments?
  - answer: Yes, you can export to iCalendar (`.ics`) and other formats using the
      appropriate API methods.
    question: Does Aspose.Email support other calendar formats besides PST?
  - answer: With the Unicode format (`FileFormatVersion.Unicode`), PST files can grow
      up to 2 TB, limited only by available disk space.
    question: What is the maximum size of a PST file I can create?
  type: FAQPage
tags:
- export calendar to pst
- Aspose.Email
- Java calendar appointments
title: Xuất lịch sang PST với Aspose.Email for Java
url: /vi/java/calendar-appointments/master-aspose-email-java-calendar-events/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Xuất lịch vào PST với Aspose.Email cho Java

Nếu bạn đang xây dựng một ứng dụng Java cần chia sẻ dữ liệu lịch trình với Outlook, bạn thường cần **export calendar to PST**. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn mọi thứ bạn cần — từ việc tạo một cuộc hẹn đơn giản, thêm người tham dự và cuối cùng ghi các sự kiện vào tệp PST, tất cả bằng Aspose.Email cho Java. Khi kết thúc, bạn sẽ có một giải pháp sẵn sàng cho sản xuất hoạt động trên Windows, Linux và macOS.

## Câu trả lời nhanh
- **Mục tiêu chính là gì?** Xuất các sự kiện lịch vào tệp PST.  
- **Thư viện nào được yêu cầu?** Aspose.Email cho Java (v25.4+).  
- **Tôi có cần giấy phép không?** Có, giấy phép Aspose.Email hợp lệ sẽ loại bỏ các giới hạn đánh giá.  
- **Tôi có thể thêm người tham dự không?** Chắc chắn – sử dụng `MapiRecipientCollection`.  
- **Phiên bản Java nào được hỗ trợ?** JDK 16 hoặc cao hơn.

## **export calendar to pst** là gì?
`MapiCalendar` là lớp của Aspose.Email mô phỏng một mục lịch Outlook, bao gồm tiêu đề, địa điểm và chi tiết thời gian.

Xuất một lịch ra PST có nghĩa là chuyển đổi các đối tượng `MapiCalendar` trong bộ nhớ thành Microsoft Outlook Personal Storage Table (PST). Tệp PST được tạo có thể mở trực tiếp trong Outlook, chia sẻ với đồng nghiệp, hoặc nhập vào bất kỳ hệ thống nào hiểu định dạng PST, bảo toàn mọi chi tiết sự kiện như người tham dự, lặp lại và lời nhắc.

## Tại sao nên sử dụng Aspose.Email cho Java để xuất lịch ra PST?
Bạn có thể tạo tệp PST hoàn toàn tương thích mà không cần cài đặt Outlook. Aspose.Email cung cấp **full MAPI support**, hoạt động trên **tất cả các hệ điều hành chính**, và có thể xử lý **lên tới 2 TB** dữ liệu trong định dạng PST Unicode — đủ cho các kho lưu trữ quy mô doanh nghiệp. API cũng cho phép bạn quản lý người tham dự, mẫu lặp lại, lời nhắc và các thuộc tính tùy chỉnh chỉ với vài lời gọi phương thức, giảm đáng kể công sức phát triển.

## Yêu cầu trước
- **Thư viện & Phụ thuộc**: Aspose.Email cho Java phiên bản 25.4 trở lên.  
- **Môi trường**: JDK 16 hoặc cao hơn, Maven để quản lý phụ thuộc.  
- **Kiến thức**: Lập trình Java cơ bản và quen thuộc với Maven.

## Cách thiết lập Aspose.Email cho Java
Thêm phụ thuộc Aspose.Email vào `pom.xml` của bạn và làm mới dự án Maven. Bước duy nhất này sẽ làm cho toàn bộ API MAPI có sẵn trên classpath của bạn.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

```xml
<dependency>
  <groupId>com.aspose</groupId>
  <artifactId>aspose-email</artifactId>
  <version>25.4</version>
  <classifier>jdk16</classifier>
</dependency>
```

### Nhận giấy phép
Mở khóa toàn bộ chức năng của Aspose.Email mà không có giới hạn đánh giá bằng cách mua giấy phép:

1. **Dùng thử miễn phí**: Truy cập [trang tải Aspose](https://releases.aspose.com/email/java/) để lấy giấy phép tạm thời.  
2. **Giấy phép tạm thời**: Đăng ký qua [trang mua](https://purchase.aspose.com/temporary-license/).  
3. **Mua giấy phép**: Xem xét mua từ [cổng mua của Aspose](https://purchase.aspose.com/buy) để sử dụng lâu dài.

Khi bạn đã có giấy phép, khởi tạo nó trong ứng dụng của bạn để kích hoạt tất cả các tính năng.

## Cách **create appointment** (Tạo sự kiện lịch Java)

Tải một đối tượng `MapiCalendar`, đặt các thuộc tính chính của nó, và trả về để sẵn sàng cho xử lý tiếp theo. Phương thức này tạo một mục lịch với tiêu đề, địa điểm, mô tả, và **java calendar start date** / **java calendar end date** mà bạn đã định nghĩa.

```java
public static MapiCalendar createAppointment(String subject, String location,
                                             String description, Calendar start, Calendar end) {
    MapiCalendar appointment = new MapiCalendar();
    appointment.setSubject(subject);
    appointment.setLocation(location);
    appointment.setBody(description);
    appointment.setStartDate(start);
    appointment.setEndDate(end);
    return appointment;
}
```

```java
import com.aspose.email.MapiCalendar;
import java.util.Calendar;
import java.util.Date;

public MapiCalendar createAppointment() {
    Calendar cal = Calendar.getInstance();
    
    // Setting the start date
    cal.set(Calendar.YEAR, 2023);
    cal.set(Calendar.MONTH, Calendar.OCTOBER);
    cal.set(Calendar.DAY_OF_MONTH, 1);
    Date startDate = cal.getTime();
    
    // Setting the end date
    cal.set(Calendar.HOUR_OF_DAY, 10);
    Date endDate = cal.getTime();
    
    return new MapiCalendar("Conference Room", "Important Meeting",
        "Discuss project milestones and updates.", startDate, endDate);
}
```

*Giải thích*: Lớp `MapiCalendar` là đại diện của Aspose.Email cho một mục lịch Outlook. Sau khi đặt các trường cơ bản, bạn cũng có thể cấu hình lặp lại, lời nhắc và danh mục trước khi lưu.

## Cách **add attendees** (java add meeting attendees)

Tạo một `MapiRecipientCollection`, điền nó với từng người tham gia, và gắn vào cuộc họp. Điều này đảm bảo mỗi người tham dự nhận được lời mời thích hợp khi PST được mở.

`MapiRecipientCollection` là một lớp collection chứa các đối tượng `MapiRecipient` đại diện cho các người tham dự cuộc họp. `MapiRecipient` đại diện cho một người tham dự cá nhân với các thuộc tính như địa chỉ email và loại người nhận.

```java
public static MapiRecipientCollection buildAttendees(List<String> emails) {
    MapiRecipientCollection attendees = new MapiRecipientCollection();
    for (String email : emails) {
        MapiRecipient recipient = new MapiRecipient(email, email, MapiRecipientType.MAPI_TO);
        attendees.add(recipient);
    }
    return attendees;
}
```

```java
import com.aspose.email.MapiCalendar;
import com.aspose.email.MapiRecipientCollection;
import com.aspose.email.MapiRecipientType;
import java.util.Date;

public MapiCalendar createMeetingWithAttendees(Date startDate, Date endDate) {
    MapiRecipientCollection attendees = new MapiRecipientCollection();
    
    // Adding primary recipients
    attendees.add("attendee1@example.com", "John Doe", MapiRecipientType.MAPI_TO);
    attendees.add("attendee2@example.com", "Jane Smith", MapiRecipientType.MAPI_TO);
    
    return new MapiCalendar(
        "Main Office Boardroom",
        "Team Meeting",
        "Discuss quarterly goals.",
        startDate,
        endDate,
        "organizer@example.com",
        attendees
    );
}
```

*Giải thích*: `MapiRecipient` định nghĩa một người tham dự duy nhất. Đặt loại thành `MAPI_TO` đánh dấu địa chỉ là người tham dự chính, trong khi `MAPI_CC` hoặc `MAPI_BCC` có thể được dùng cho các người tham dự tùy chọn.

## Cách **export calendar to pst** (Tạo PST với các sự kiện lịch)

Tạo một tệp PST Unicode, thêm thư mục "Calendar", và chèn các đối tượng `MapiCalendar` đã xây dựng trước đó. PST sau đó có thể mở trong Outlook hoặc phân phối cho người dùng cuối.

`PersonalStorage` là lớp của Aspose.Email dùng để tạo, mở và thao tác với các tệp PST.

```java
public static void createPSTWithCalendarEvents(String pstFilePath,
                                                List<MapiCalendar> events) throws Exception {
    // Create a new Unicode PST (supports up to 2 TB)
    PersonalStorage pst = PersonalStorage.create(pstFilePath, FileFormatVersion.Unicode);
    // Add the default Calendar folder
    FolderInfo calendarFolder = pst.getRootFolder().addSubFolder("Calendar", 
                                   StandardIpmFolder.Calendar);
    // Insert each event
    for (MapiCalendar event : events) {
        calendarFolder.addMapiMessageItem(event);
    }
}
```

```java
import com.aspose.email.FileFormatVersion;
import com.aspose.email.FolderInfo;
import com.aspose.email.PersonalStorage;
import com.aspose.email.StandardIpmFolder;

public void createPSTWithCalendarEvents() {
    String pstFilePath = "/path/to/output/MapiCalendarToPST_out.pst";
    
    PersonalStorage pst = PersonalStorage.create(pstFilePath, FileFormatVersion.Unicode);
    FolderInfo calendarFolder = pst.createPredefinedFolder("Calendar", StandardIpmFolder.Appointments);

    MapiCalendar appointment = createAppointment();
    calendarFolder.addMapiMessageItem(appointment);
    
    Date startDate = new Date(); // Use actual dates from your event
    Date endDate = new Date();
    MapiCalendar meeting = createMeetingWithAttendees(startDate, endDate);
    calendarFolder.addMapiMessageItem(meeting);
}
```

*Giải thích*: `PersonalStorage` là điểm vào để thao tác PST. Bằng cách sử dụng định dạng Unicode, bạn tránh giới hạn 2 GB của các phiên bản PST cũ và hưởng lợi từ I/O nhanh hơn trên các kho lưu trữ lớn.

## Ứng dụng thực tế
1. **Lịch trình doanh nghiệp** – Tự động tạo và phân phối các cuộc họp nội bộ.  
2. **Quản lý sự kiện** – Theo dõi hội nghị, hội thảo và danh sách người tham dự.  
3. **Tích hợp CRM** – Đồng bộ các cuộc hẹn với công cụ quản lý quan hệ khách hàng.  
4. **Lập kế hoạch dự án** – Lưu các mốc dự án dưới dạng mục lịch.  
5. **Hợp tác nhóm từ xa** – Tạo tệp PST để chia sẻ ngoại tuyến.

## Các cân nhắc về hiệu năng
- **Giải phóng đối tượng** không còn cần thiết để giải phóng bộ nhớ kịp thời.  
- **Sử dụng collection hiệu quả** (ví dụ, `ArrayList` cho danh sách người tham dự) khi xử lý hàng nghìn người tham gia.  
- **Bộ nhớ đệm các sự kiện truy cập thường xuyên** nếu bạn truy vấn PST nhiều lần, giảm I/O đĩa.

## Các vấn đề thường gặp và giải pháp
| Vấn đề | Giải pháp |
|-------|----------|
| **PST file not created** | Xác minh quyền ghi trên thư mục đích và đảm bảo đường dẫn thư mục tồn tại. |
| **Attendees not receiving invitations** | Xác nhận mỗi `MapiRecipient` sử dụng `MapiRecipientType.MAPI_TO` và email của người tổ chức là hợp lệ. |
| **Date mismatch** | Sử dụng `Calendar` một cách nhất quán cho ngày bắt đầu/kết thúc; tránh trộn `java.util.Date` với các thư viện ngày khác mà không chuyển đổi. |

## Câu hỏi thường gặp

**Q: Làm thế nào để bắt đầu với Aspose.Email cho Java?**  
A: Thêm phụ thuộc Maven như trên, lấy giấy phép, và làm theo các bước trong hướng dẫn này để tạo và xuất các sự kiện lịch.

**Q: Tôi có thể tùy chỉnh tên và vị trí tệp PST không?**  
A: Có, thay đổi biến `pstFilePath` trong `createPSTWithCalendarEvents()` thành bất kỳ đường dẫn hợp lệ nào trên hệ thống của bạn.

**Q: Có thể thêm mẫu lặp lại vào các cuộc hẹn không?**  
A: Chắc chắn – `MapiCalendar` cung cấp thuộc tính `RecurrencePattern` mà bạn có thể cấu hình trước khi lưu.

**Q: Aspose.Email có hỗ trợ các định dạng lịch khác ngoài PST không?**  
A: Có, bạn có thể xuất sang iCalendar (`.ics`) và các định dạng khác bằng các phương thức API thích hợp.

**Q: Kích thước tối đa của tệp PST tôi có thể tạo là bao nhiêu?**  
A: Với định dạng Unicode (`FileFormatVersion.Unicode`), tệp PST có thể lên tới 2 TB, chỉ bị giới hạn bởi không gian đĩa khả dụng.

---

**Cập nhật lần cuối:** 2026-08-01  
**Kiểm tra với:** Aspose.Email cho Java 25.4 (jdk16 classifier)  
**Tác giả:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Hướng dẫn liên quan

- [Làm chủ Aspose.Email cho Java: Quản lý tệp PST Outlook một cách hiệu quả](/email/java/outlook-pst-ost-operations/aspose-email-java-manage-outlook-pst-files/)
- [Làm chủ việc tạo và lưu các mục lịch với Aspose.Email cho Java](/email/java/calendar-appointments/create-save-calendar-items-aspose-email-java/)
- [Cách đọc nhiều sự kiện lịch từ tệp ICS bằng Aspose.Email trong Java](/email/java/calendar-appointments/read-multiple-ics-events-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}