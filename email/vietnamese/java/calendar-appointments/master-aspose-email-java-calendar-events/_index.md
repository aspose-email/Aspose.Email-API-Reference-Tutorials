---
date: '2026-02-24'
description: Tìm hiểu cách xuất lịch sang PST với Aspose.Email cho Java, bao gồm cách
  thêm người tham dự, đặt ngày bắt đầu và kết thúc, và quản lý các cuộc hẹn một cách
  hiệu quả.
keywords:
- Aspose.Email Java Calendar Events
- Create Calendar Events in Java
- Manage Calendar Appointments with Java
- export calendar to pst
title: Xuất lịch sang PST bằng Aspose.Email cho Java
url: /vi/java/calendar-appointments/master-aspose-email-java-calendar-events/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Xuất lịch vào PST với Aspose.Email cho Java

Nếu bạn đang xây dựng một ứng dụng Java cần chia sẻ dữ liệu lịch với Outlook, bạn thường sẽ cần **export calendar to PST**. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn mọi thứ bạn cần—từ việc tạo một cuộc hẹn đơn giản, thêm người tham dự và cuối cùng ghi các sự kiện vào tệp PST, tất cả đều sử dụng Aspose.Email cho Java.

## Câu trả lời nhanh
- **Mục tiêu chính là gì?** Export calendar events to a PST file.  
- **Thư viện nào được yêu cầu?** Aspose.Email for Java (v25.4+).  
- **Tôi có cần giấy phép không?** Yes, a valid Aspose.Email license removes evaluation limits.  
- **Tôi có thể thêm người tham dự không?** Absolutely – use `MapiRecipientCollection`.  
- **Phiên bản Java nào được hỗ trợ?** JDK 16 or higher.

## **export calendar to pst** là gì?
Xuất lịch sang PST có nghĩa là chuyển đổi các đối tượng `MapiCalendar` trong bộ nhớ thành Microsoft Outlook Personal Storage Table (PST). Tệp kết quả có thể được mở trực tiếp trong Outlook, chia sẻ với đồng nghiệp, hoặc nhập vào bất kỳ hệ thống nào hiểu định dạng PST.

## Tại sao nên sử dụng Aspose.Email cho Java để export calendar to PST?
- **Full MAPI support** – tạo, sửa đổi và lưu các cuộc hẹn mà không cần cài đặt Outlook.  
- **Cross‑platform** – hoạt động trên Windows, Linux và macOS.  
- **Rich API** – quản lý người tham dự, lặp lại, nhắc nhở và hơn thế nữa.  
- **Performance‑optimized** – xử lý lượng lớn sự kiện với mức sử dụng bộ nhớ thấp.

## Yêu cầu trước
- **Libraries & Dependencies**: Aspose.Email for Java version 25.4 or later.  
- **Environment**: JDK 16 or higher, Maven for dependency management.  
- **Knowledge**: Kiến thức cơ bản về lập trình Java và quen thuộc với Maven.

## Cách thiết lập Aspose.Email cho Java
Add the Aspose.Email dependency to your `pom.xml`:

```xml
<dependency>
  <groupId>com.aspose</groupId>
  <artifactId>aspose-email</artifactId>
  <version>25.4</version>
  <classifier>jdk16</classifier>
</dependency>
```

### Nhận giấy phép
Unlock full functionality of Aspose.Email without evaluation limitations by acquiring a license:

1. **Free Trial**: Truy cập [Aspose download page](https://releases.aspose.com/email/java/) để nhận giấy phép tạm thời.  
2. **Temporary License**: Đăng ký qua [purchase page](https://purchase.aspose.com/temporary-license/).  
3. **Purchase License**: Xem xét mua từ [Aspose's purchase portal](https://purchase.aspose.com/buy) để sử dụng lâu dài.

Sau khi bạn có giấy phép, hãy khởi tạo nó trong ứng dụng của bạn để kích hoạt tất cả các tính năng.

## Cách **create appointment** (Create Calendar Event Java)

### Bước 1: Xác định ngày bắt đầu và kết thúc (java calendar start date / java calendar end date)
Phương thức dưới đây cho thấy cách đặt ngày bắt đầu và kết thúc cho một cuộc hẹn và trả về một đối tượng `MapiCalendar`:

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

*Explanation*: Đoạn mã này tạo một `MapiCalendar` với vị trí, tiêu đề, mô tả cụ thể, và **java calendar start date** / **java calendar end date** mà bạn đã định nghĩa.

## Cách **add attendees** (java add meeting attendees)

### Bước 2: Xây dựng danh sách người tham dự
Sử dụng `MapiRecipientCollection` để chỉ định ai sẽ nhận lời mời họp:

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

*Explanation*: Đoạn mã này tạo một cuộc họp, đặt người tổ chức, và đính kèm danh sách **java add meeting attendees** để mọi người nhận được lời mời đúng.

## Cách **export calendar to pst** (Create PST with calendar events)

### Bước 3: Tạo tệp PST và thêm các sự kiện
Phương thức dưới đây minh họa cách tạo tệp PST Unicode và lưu cả cuộc hẹn đơn giản và cuộc họp có người tham dự:

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

*Explanation*: Đoạn mã này **exports calendar to PST** bằng cách tạo một container PST, thêm thư mục "Calendar" đã định nghĩa trước, và chèn các đối tượng `MapiCalendar` đã xây dựng trước đó.

## Ứng dụng thực tiễn
1. **Business Scheduling** – Tự động tạo và phân phối các cuộc họp nội bộ.  
2. **Event Management** – Theo dõi hội nghị, hội thảo và danh sách người tham dự.  
3. **CRM Integration** – Đồng bộ các cuộc hẹn với công cụ quản lý quan hệ khách hàng.  
4. **Project Planning** – Lưu các mốc dự án dưới dạng mục lịch.  
5. **Remote Team Collaboration** – Tạo tệp PST để chia sẻ ngoại tuyến.

## Các cân nhắc về hiệu năng
- **Dispose objects** các đối tượng không còn cần để giải phóng bộ nhớ.  
- **Choose efficient collections** chọn các collection hiệu quả cho danh sách người tham dự lớn.  
- **Cache frequently accessed events** nếu bạn truy vấn PST thường xuyên.

## Các vấn đề thường gặp và giải pháp
| Issue | Solution |
|-------|----------|
| **PST file not created** | Xác minh quyền ghi trên thư mục đích và đảm bảo đường dẫn thư mục tồn tại. |
| **Attendees not receiving invitations** | Xác nhận mỗi `MapiRecipient` sử dụng `MapiRecipientType.MAPI_TO` và email người tổ chức là hợp lệ. |
| **Date mismatch** | Sử dụng `Calendar` một cách nhất quán cho ngày bắt đầu/kết thúc; tránh trộn `java.util.Date` với các thư viện ngày khác mà không chuyển đổi. |

## Câu hỏi thường gặp

**Q: Làm thế nào để bắt đầu với Aspose.Email cho Java?**  
A: Thêm dependency Maven như trên, nhận giấy phép, và làm theo các bước trong hướng dẫn này để tạo và xuất các sự kiện lịch.

**Q: Tôi có thể tùy chỉnh tên và vị trí tệp PST không?**  
A: Có, thay đổi biến `pstFilePath` trong `createPSTWithCalendarEvents()` thành bất kỳ đường dẫn hợp lệ nào trên hệ thống của bạn.

**Q: Có thể thêm mẫu lặp lại vào các cuộc hẹn không?**  
A: Chắc chắn – `MapiCalendar` cung cấp các thuộc tính lặp lại như `RecurrencePattern` mà bạn có thể cấu hình trước khi lưu.

**Q: Aspose.Email có hỗ trợ các định dạng lịch khác ngoài PST không?**  
A: Có, bạn có thể xuất sang iCalendar (`.ics`) và các định dạng khác bằng các phương thức API tương ứng.

**Q: Kích thước tối đa của tệp PST tôi có thể tạo là bao nhiêu?**  
A: Với định dạng Unicode (`FileFormatVersion.Unicode`), tệp PST có thể lên tới 2 TB, chỉ bị giới hạn bởi không gian đĩa khả dụng.

---

**Cập nhật lần cuối:** 2026-02-24  
**Kiểm tra với:** Aspose.Email for Java 25.4 (jdk16 classifier)  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}