---
date: '2026-09-17'
description: Tìm hiểu cách tạo lịch outlook java với daily recurrence và exceptions,
  và lưu lịch vào PST bằng Aspose.Email cho Java.
keywords:
- create outlook calendar
- outlook calendar daily recurrence
- java calendar exceptions
- Aspose.Email Java
- MAPI PST generation
lastmod: '2026-09-17'
og_description: Tạo lịch outlook trong Java bằng Aspose.Email. Tìm hiểu daily recurrence,
  exception handling, và lưu vào PST trong một step‑by‑step guide.
og_image_alt: Code example creating Outlook calendar with recurrence and PST export
  using Aspose.Email for Java
og_title: Tạo lịch outlook trong Java với daily recurrence và exceptions
schemas:
- author: Aspose
  dateModified: '2026-09-17'
  description: Learn how to create outlook calendar java with daily recurrence and
    exceptions, and save calendar to PST using Aspose.Email for Java.
  headline: Create outlook calendar java with daily recurrence and exceptions
  type: TechArticle
- questions:
  - answer: Yes, you can set the `StartTimeZone` and `EndTimeZone` properties on `MapiCalendar`.
    question: Does the library support time‑zone aware appointments?
  - answer: Use the `DeletedInstanceDates` collection on the recurrence pattern to
      mark specific dates as removed.
    question: Can I programmatically delete a single occurrence from a recurring series?
  - answer: PST files follow the Unicode format limits (up to 2 GB by default), but
      you can configure larger sizes via `PersonalStorage` settings.
    question: Are there limits on the size of a PST file created with Aspose.Email?
  - answer: Create `MapiRecipient` objects, set their `RecipientType` to `MapiRecipientType.MAPI_TO`,
      and add them to the `Recipients` collection of the `MapiMessage`.
    question: How do I add attendees to a meeting request?
  - answer: Yes, Aspose.Email also provides `MapiTask` with similar recurrence capabilities.
    question: Is there support for recurring tasks (not just appointments)?
  type: FAQPage
tags:
- outlook calendar
- Aspose.Email
- Java scheduling
- PST file
title: Tạo lịch outlook java với daily recurrence và exceptions
url: /vi/java/calendar-appointments/create-mapi-calendar-daily-recurrence-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo outlook calendar java với chu kỳ hàng ngày và các ngoại lệ

Quản lý các sự kiện lặp lại một cách hiệu quả có thể là thách thức, đặc biệt khi bạn cần một **outlook calendar java** hỗ trợ các mẫu chu kỳ hàng ngày và các ngoại lệ thỉnh thoảng. Trong hướng dẫn này, bạn sẽ học cách tạo các đối tượng Outlook calendar Java, cấu hình chu kỳ hàng ngày, thêm các trường hợp ngoại lệ, và cuối cùng **save calendar to PST** bằng Aspose.Email for Java. Khi kết thúc, bạn sẽ có một đoạn mã có thể tái sử dụng mà bạn có thể đưa vào bất kỳ dịch vụ lập lịch dựa trên Java nào.

## Câu trả lời nhanh
- **Thư viện nào?** Aspose.Email for Java  
- **Nhiệm vụ chính?** Tạo Outlook calendar Java với chu kỳ hàng ngày và các ngoại lệ  
- **Yêu cầu JDK?** Java 16 hoặc cao hơn  
- **Tôi có thể đính kèm tệp vào các ngoại lệ không?** Có, sử dụng `MapiCalendarExceptionInfo`  
- **Lịch được lưu ở đâu?** Trong tệp PST qua `PersonalStorage`  

## Outlook calendar java là gì?
Một đối tượng Outlook calendar Java là một biểu diễn lập trình của một cuộc hẹn Outlook, được xây dựng dựa trên đặc tả MAPI (Messaging Application Programming Interface), bao gồm các thuộc tính như tiêu đề, địa điểm, thời gian bắt đầu/kết thúc, quy tắc lặp lại, người tham dự và tệp đính kèm. Đối tượng này có thể được thao tác, tuần tự hoá và lưu trữ trong các tệp PST mà không cần Outlook.

## Tại sao sử dụng Aspose.Email cho Java?
Aspose.Email cho Java cho phép bạn làm việc với các đối tượng MAPI mà không cần cài đặt Outlook. Thư viện hỗ trợ **hơn 50 thuộc tính MAPI**, có thể tạo các tệp PST Unicode lên tới **2 GB** trong vòng **2 giây** cho dữ liệu cuộc hẹn tiêu chuẩn, và chạy trên bất kỳ nền tảng nào hỗ trợ Java 16+. Cách tiếp cận thuần Java này cho phép tạo lịch trên máy chủ, tự động hoá chuỗi cuộc họp, và kiểm soát toàn bộ logic lặp lại.

## Các yêu cầu
Trước khi bắt đầu, hãy đảm bảo bạn đã thiết lập các thành phần sau:
- **Thư viện Aspose.Email**: Phiên bản 25.4 (hoặc mới hơn) – có sẵn qua Maven hoặc tải trực tiếp.  
- **Bộ công cụ phát triển Java (JDK)**: JDK 16 hoặc mới hơn.  
- **IDE**: IntelliJ IDEA, Eclipse, NetBeans, hoặc bất kỳ trình soạn thảo nào hỗ trợ Java.

### Thư viện và phụ thuộc cần thiết
Để tích hợp Aspose.Email vào dự án của bạn bằng Maven, thêm phụ thuộc sau vào tệp `pom.xml` của bạn:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Cách lấy giấy phép
Để sử dụng Aspose.Email, bạn sẽ cần một giấy phép:
- **Dùng thử miễn phí** – khám phá tất cả tính năng mà không tốn phí.  
- **Giấy phép tạm thời** – yêu cầu để đánh giá mở rộng.  
- **Giấy phép đầy đủ** – mua để triển khai trong môi trường sản xuất.

## Cài đặt Aspose.Email cho Java

Đầu tiên, thiết lập môi trường của bạn:

1. Xác minh JDK 16 đã được cài đặt và `JAVA_HOME` đã được cấu hình.  
2. Thêm phụ thuộc Maven (hoặc tải JAR) vào dự án của bạn.  

Dưới đây là một đoạn mã ngắn cho thấy cách tải tệp giấy phép:

```java
import com.aspose.email.*;

public class InitializeAspose {
    public static void main(String[] args) {
        // Set up a license if available
        License license = new License();
        try {
            license.setLicense("path/to/your/license.lic");
        } catch (Exception e) {
            System.out.println("License not found, using trial version.");
        }
    }
}
```

## Hướng dẫn triển khai

### Tạo outlook calendar java với chu kỳ hàng ngày và các ngoại lệ

#### Tổng quan
Tính năng này cho phép bạn tự động hoá các cuộc hẹn lặp lại đồng thời vẫn có thể bỏ qua hoặc chỉnh sửa các trường hợp cụ thể.

#### Triển khai từng bước

**1. Thiết lập ngày bắt đầu sự kiện**  
Xác định thời điểm chuỗi bắt đầu:

```java
Date startDate = addHours(newDate(2018, 7, 19), 12);
```

**2. Tạo đối tượng lịch MAPI**  
Lớp `MapiCalendar` là đối tượng cấp cao nhất đại diện cho một mục lịch duy nhất trong bộ nhớ. Cung cấp địa điểm, tiêu đề và mô tả:

```java
MapiCalendar calendar = new MapiCalendar("location1", "summary1", "description1", startDate, addHours(startDate, 1));
```

**3. Định nghĩa mẫu chu kỳ hàng ngày**  
Lớp `MapiCalendarRecurrencePattern` lưu quy tắc lặp lại cuộc hẹn mỗi ngày. Cấu hình sự kiện để lặp lại hàng ngày:

```java
MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
MapiCalendarRecurrencePattern pattern = recurrence.getRecurrencePattern();

pattern.setPatternType(MapiCalendarRecurrencePatternType.Day);
pattern.setPeriod(1); // Daily
pattern.setEndType(MapiCalendarRecurrenceEndType.NeverEnd);
```

**4. Thêm một ngoại lệ vào chu kỳ**  
`MapiCalendarExceptionInfo` mô tả một lần xuất hiện duy nhất lệch khỏi mẫu—có thể bị loại trừ hoặc thay đổi. Chỉ định ngày cần loại trừ (hoặc thay đổi):

```java
Date exceptionDate = addDays(startDate, 3);

MapiCalendarExceptionInfo exception = new MapiCalendarExceptionInfo();
exception.setLocation("exceptionLocation");
exception.setSubject("exceptionSubject");
exception.setBody("exceptionBody");

exception.setOriginalStartDate(exceptionDate);
exception.setStartDateTime(exceptionDate);
exception.setEndDateTime(addHours(exceptionDate, 5));

pattern.getExceptions().addItem(exception);
pattern.getModifiedInstanceDates().addItem(exceptionDate);
pattern.getDeletedInstanceDates().addItem(exceptionDate);

calendar.setRecurrence(recurrence);
```

### Đính kèm tệp vào các ngoại lệ lịch

#### Tổng quan
Bạn có thể đính kèm tài liệu hỗ trợ (ví dụ: chương trình họp) vào bất kỳ trường hợp ngoại lệ nào.

**1. Tạo và đính kèm tệp**

```java
MapiCalendarExceptionInfo exception = new MapiCalendarExceptionInfo();
exception.getAttachments().add("file.txt", "hello, world!".getBytes());
```

## Lưu outlook calendar java vào PST (save calendar to pst)

#### Tổng quan
Lưu lịch vào tệp PST để Outlook hoặc các client khác có thể đọc được.

**1. Tạo và lưu lịch vào PST**  
Lớp `PersonalStorage` cung cấp các phương thức để tạo tệp PST mới và thêm các mục MAPI vào đó.

```java
final PersonalStorage pst = PersonalStorage.create(new ByteArrayOutputStream(), FileFormatVersion.Unicode);
try {
    FolderInfo calendarFolder = pst.createPredefinedFolder("Calendar", StandardIpmFolder.Appointments);
    calendarFolder.addMapiMessageItem(calendar);
} finally {
    pst.dispose();
}
```

## Ứng dụng thực tế
- **Lập lịch doanh nghiệp** – tự động hoá chuỗi cuộc họp, tự động bỏ qua ngày lễ.  
- **Quản lý dự án** – theo dõi các mốc quan trọng lặp lại với những thay đổi ngày thỉnh thoảng.  
- **Lập kế hoạch sự kiện** – quản lý hội nghị đa ngày, trong đó một số phiên có thể bị hủy hoặc dời lịch.

### Các khả năng tích hợp
Kết hợp Aspose.Email với các nền tảng CRM, API quản lý công việc, hoặc các engine workflow tùy chỉnh để tạo ra tự động hoá toàn diện từ đầu đến cuối.

## Các cân nhắc về hiệu năng
- **Giải phóng tài nguyên** – luôn gọi `dispose()` trên `PersonalStorage` để giải phóng các handle tệp.  
- **Sử dụng luồng** – ưu tiên `ByteArrayOutputStream` hoặc luồng tệp để tránh tải toàn bộ PST vào bộ nhớ.  
- **Thao tác bất đồng bộ** – đối với việc tạo lịch hàng loạt, chạy logic tạo trên một luồng nền để UI luôn phản hồi.

## Kết luận
Bằng cách làm theo hướng dẫn này, bạn đã biết cách **tạo outlook calendar java** với chu kỳ hàng ngày, thêm ngoại lệ, đính kèm tệp, và **save calendar to PST**. Những khả năng này cho phép bạn xây dựng các tính năng lập lịch mạnh mẽ mà không cần can thiệp Outlook.

### Các bước tiếp theo
- Thử nghiệm các mẫu chu kỳ hàng tuần hoặc hàng tháng.  
- Khám phá các thuộc tính MAPI bổ sung như người tham dự, nhắc nhở và danh mục.  
- Xem lại tài liệu API chi tiết của Aspose.Email để áp dụng các kịch bản nâng cao hơn.

## Câu hỏi thường gặp

**Q: Thư viện có hỗ trợ các cuộc hẹn nhận thức múi giờ không?**  
A: Có, bạn có thể đặt các thuộc tính `StartTimeZone` và `EndTimeZone` trên `MapiCalendar`.

**Q: Tôi có thể lập trình xóa một lần xuất hiện duy nhất khỏi chuỗi lặp lại không?**  
A: Sử dụng bộ sưu tập `DeletedInstanceDates` trên mẫu chu kỳ để đánh dấu các ngày cụ thể là đã bị xóa.

**Q: Có giới hạn nào về kích thước tệp PST được tạo bằng Aspose.Email không?**  
A: Các tệp PST tuân theo giới hạn định dạng Unicode (tối đa 2 GB theo mặc định), nhưng bạn có thể cấu hình kích thước lớn hơn qua cài đặt `PersonalStorage`.

**Q: Làm thế nào để thêm người tham dự vào yêu cầu họp?**  
A: Tạo các đối tượng `MapiRecipient`, đặt `RecipientType` của chúng thành `MapiRecipientType.MAPI_TO`, và thêm chúng vào bộ sưu tập `Recipients` của `MapiMessage`.

**Q: Có hỗ trợ cho các nhiệm vụ lặp lại (không chỉ cuộc hẹn) không?**  
A: Có, Aspose.Email cũng cung cấp `MapiTask` với các khả năng lặp lại tương tự.

**Q: Tôi có thể sử dụng hướng dẫn này như một phần của loạt tutorial Aspose.Email Java không?**  
A: Chắc chắn – các bước được trình bày ở đây là phần cốt lõi của bất kỳ tutorial Aspose.Email Java nào liên quan đến việc tạo lịch.

## Tài nguyên
- [Tài liệu Aspose.Email cho Java](https://reference.aspose.com/email/java/)
- [Tải xuống Aspose.Email](https://releases.aspose.com/email/java/)
- [Mua giấy phép](https://purchase.aspose.com/buy)
- [Phiên bản dùng thử miễn phí](https://releases.aspose.com/email/java/)
- [Yêu cầu giấy phép tạm thời](https://purchase.aspose.com/temporary-license/)
- [Diễn đàn hỗ trợ Aspose](https://forum.aspose.com/c/email/10)

---

**Cập nhật lần cuối:** 2026-09-17  
**Kiểm tra với:** Aspose.Email for Java 25.4 (JDK 16)  
**Tác giả:** Aspose

## Hướng dẫn liên quan

- [Xuất Outlook calendar PST với Aspose.Email – Java](/email/java/calendar-appointments/create-save-mapi-calendar-aspose-email-java/)
- [Cách tạo Calendar Item Java bằng Aspose.Email](/email/java/calendar-appointments/create-save-calendar-items-aspose-email-java/)
- [Tạo lời mời chia sẻ lịch với Aspose.Email cho Java](/email/java/calendar-appointments/create-send-calendar-invitations-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}