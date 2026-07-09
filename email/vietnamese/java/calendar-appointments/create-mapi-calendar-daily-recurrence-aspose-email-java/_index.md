---
date: '2026-03-20'
description: Tìm hiểu cách tạo lịch Outlook bằng Java với sự lặp lại hàng ngày và
  các ngoại lệ, và lưu lịch vào tệp PST bằng Aspose.Email cho Java.
keywords:
- MAPI Calendar creation
- daily recurrence events
- Java calendar exceptions
title: Tạo lịch Outlook bằng Java với lặp lại hàng ngày và các ngoại lệ
url: /vi/java/calendar-appointments/create-mapi-calendar-daily-recurrence-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cách tạo outlook calendar java với lịch lặp hàng ngày và ngoại lệ

Quản lý các sự kiện lặp lại một cách hiệu quả có thể là thách thức, đặc biệt khi bạn cần một **outlook calendar java** hỗ trợ các mẫu lặp hàng ngày và các ngoại lệ thỉnh thoảng. Trong hướng dẫn này, bạn sẽ học cách tạo các đối tượng Outlook calendar Java, cấu hình lịch lặp hàng ngày, thêm các trường hợp ngoại lệ, và cuối cùng **save calendar to PST** bằng Aspose.Email for Java. Khi hoàn thành, bạn sẽ có một đoạn mã có thể tái sử dụng mà bạn có thể chèn vào bất kỳ dịch vụ lập lịch dựa trên Java nào.

## Câu trả lời nhanh
- **Thư viện nào?** Aspose.Email for Java  
- **Nhiệm vụ chính?** Create an Outlook calendar Java with daily recurrence and exceptions  
- **JDK yêu cầu?** Java 16 or higher  
- **Tôi có thể đính kèm tệp vào các ngoại lệ không?** Yes, using `MapiCalendarExceptionInfo`  
- **Lịch được lưu ở đâu?** In a PST file via `PersonalStorage`

## Outlook calendar java là gì?
Một đối tượng Outlook calendar Java (được triển khai dưới dạng lịch MAPI) tuân theo cùng các tiêu chuẩn như các cuộc hẹn của Microsoft Outlook. Nó lưu trữ các quy tắc lặp phong phú, xử lý ngoại lệ, người tham dự và tệp đính kèm, khiến nó hoàn hảo cho việc lập lịch cấp doanh nghiệp.

## Tại sao nên sử dụng Aspose.Email cho Java?
Aspose.Email cung cấp một API thuần Java cho phép bạn làm việc với các đối tượng MAPI mà không cần cài đặt Outlook. Cách tiếp cận **aspose email tutorial java** này cho phép tạo tệp PST phía máy chủ, chuỗi cuộc họp tự động, và kiểm soát đầy đủ logic lặp lại.

## Yêu cầu trước

Trước khi bắt đầu, hãy đảm bảo bạn đã có các thiết lập sau:
- **Aspose.Email Library**: Phiên bản 25.4 (hoặc mới hơn) – có sẵn qua Maven hoặc tải trực tiếp.  
- **Java Development Kit (JDK)**: JDK 16 hoặc mới hơn.  
- **IDE**: IntelliJ IDEA, Eclipse, NetBeans, hoặc bất kỳ trình soạn thảo nào tương thích với Java.

### Thư viện và phụ thuộc cần thiết

Để tích hợp Aspose.Email vào dự án của bạn bằng Maven, thêm phụ thuộc sau vào file `pom.xml` của bạn:

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
- **Free Trial** – khám phá tất cả tính năng mà không tốn phí.  
- **Temporary License** – yêu cầu để đánh giá kéo dài hơn.  
- **Full License** – mua để triển khai trong môi trường sản xuất.

## Cài đặt Aspose.Email cho Java

Đầu tiên, thiết lập môi trường của bạn:

1. Xác minh JDK 16 đã được cài đặt và `JAVA_HOME` đã được cấu hình.  
2. Thêm phụ thuộc Maven (hoặc tải JAR) vào dự án của bạn.  

Dưới đây là một đoạn mã ngắn cho thấy cách tải file giấy phép:

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

### Tạo outlook calendar java với Lịch lặp hàng ngày và Ngoại lệ

#### Tổng quan
Tính năng này cho phép bạn tự động hoá các cuộc hẹn lặp lại đồng thời vẫn có thể bỏ qua hoặc chỉnh sửa các trường hợp cụ thể.

#### Triển khai từng bước

**1. Thiết lập ngày bắt đầu sự kiện**  
Xác định thời điểm chuỗi nên bắt đầu:

```java
Date startDate = addHours(newDate(2018, 7, 19), 12);
```

**2. Tạo đối tượng MAPI Calendar**  
Cung cấp địa điểm, tiêu đề và mô tả:

```java
MapiCalendar calendar = new MapiCalendar("location1", "summary1", "description1", startDate, addHours(startDate, 1));
```

**3. Định nghĩa mẫu lặp hàng ngày**  
Cấu hình sự kiện để lặp lại mỗi ngày:

```java
MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
MapiCalendarRecurrencePattern pattern = recurrence.getRecurrencePattern();

pattern.setPatternType(MapiCalendarRecurrencePatternType.Day);
pattern.setPeriod(1); // Daily
pattern.setEndType(MapiCalendarRecurrenceEndType.NeverEnd);
```

**4. Thêm một ngoại lệ vào lịch lặp**  
Xác định ngày cần loại trừ (hoặc thay đổi):

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

### Đính kèm tệp vào ngoại lệ lịch

#### Tổng quan
Bạn có thể đính kèm tài liệu hỗ trợ (ví dụ: chương trình) vào bất kỳ trường hợp ngoại lệ nào.

**1. Tạo và đính kèm tệp**

```java
MapiCalendarExceptionInfo exception = new MapiCalendarExceptionInfo();
exception.getAttachments().add("file.txt", "hello, world!".getBytes());
```

### Lưu outlook calendar java vào PST (save calendar to pst)

#### Tổng quan
Lưu trữ lịch vào tệp PST để Outlook hoặc các client khác có thể đọc được.

**1. Tạo và lưu lịch vào PST**

```java
final PersonalStorage pst = PersonalStorage.create(new ByteArrayOutputStream(), FileFormatVersion.Unicode);
try {
    FolderInfo calendarFolder = pst.createPredefinedFolder("Calendar", StandardIpmFolder.Appointments);
    calendarFolder.addMapiMessageItem(calendar);
} finally {
    pst.dispose();
}
```

## Ứng dụng thực tiễn
- **Corporate Scheduling** – tự động hoá chuỗi cuộc họp, tự động bỏ qua ngày lễ.  
- **Project Management** – theo dõi các mốc lặp lại với những thay đổi ngày thỉnh thoảng.  
- **Event Planning** – quản lý hội nghị đa ngày, trong đó một số phiên bị hủy hoặc dời lịch.

### Khả năng tích hợp
Kết hợp Aspose.Email với các nền tảng CRM, API quản lý công việc, hoặc các engine quy trình làm việc tùy chỉnh để thực hiện tự động hoá toàn diện.

## Lưu ý về hiệu năng
- **Dispose Resources** – luôn gọi `dispose()` trên `PersonalStorage` để giải phóng các handle tệp.  
- **Stream Usage** – ưu tiên sử dụng `ByteArrayOutputStream` hoặc luồng tệp để tránh tải toàn bộ PST vào bộ nhớ.  
- **Async Operations** – đối với việc tạo lịch hàng loạt, chạy logic tạo trên một luồng nền để UI luôn phản hồi.

## Kết luận
Bằng cách làm theo hướng dẫn này, bạn đã biết cách **create outlook calendar java** các đối tượng với lịch lặp hàng ngày, thêm ngoại lệ, đính kèm tệp, và **save calendar to PST**. Những khả năng này cho phép bạn xây dựng các tính năng lập lịch mạnh mẽ mà không cần tiếp xúc trực tiếp với Outlook.

### Bước tiếp theo
- Thử nghiệm các mẫu lặp hàng tuần hoặc hàng tháng.  
- Khám phá các thuộc tính MAPI bổ sung như người tham dự, nhắc nhở và danh mục.  
- Xem lại tài liệu API toàn diện của Aspose.Email để hiểu các kịch bản nâng cao hơn.

## Câu hỏi thường gặp

**Q: Thư viện có hỗ trợ các cuộc hẹn nhận thức múi giờ không?**  
A: Có, bạn có thể đặt các thuộc tính `StartTimeZone` và `EndTimeZone` trên `MapiCalendar`.

**Q: Tôi có thể lập trình xóa một lần xuất hiện duy nhất khỏi chuỗi lặp lại không?**  
A: Sử dụng bộ sưu tập `DeletedInstanceDates` trên mẫu lặp để đánh dấu các ngày cụ thể là đã bị xóa.

**Q: Có giới hạn nào về kích thước của tệp PST được tạo bằng Aspose.Email không?**  
A: Các tệp PST tuân theo giới hạn định dạng Unicode (mặc định lên tới 2 GB), nhưng bạn có thể cấu hình kích thước lớn hơn thông qua cài đặt `PersonalStorage`.

**Q: Làm thế nào để thêm người tham dự vào yêu cầu họp?**  
A: Tạo các đối tượng `MapiRecipient`, đặt `RecipientType` của chúng thành `MapiRecipientType.MAPI_TO`, và thêm chúng vào bộ sưu tập `Recipients` của `MapiMessage`.

**Q: Có hỗ trợ cho các nhiệm vụ lặp lại (không chỉ cuộc hẹn) không?**  
A: Có, Aspose.Email cũng cung cấp `MapiTask` với các khả năng lặp lại tương tự.

**Q: Tôi có thể sử dụng hướng dẫn này như một phần của series aspose email tutorial java không?**  
A: Chắc chắn – các bước được trình bày ở đây là phần cốt lõi của bất kỳ hướng dẫn Aspose.Email Java nào liên quan đến việc tạo lịch.

## Tài nguyên
- [Tài liệu Aspose.Email cho Java](https://reference.aspose.com/email/java/)
- [Tải xuống Aspose.Email](https://releases.aspose.com/email/java/)
- [Mua giấy phép](https://purchase.aspose.com/buy)
- [Phiên bản dùng thử miễn phí](https://releases.aspose.com/email/java/)
- [Yêu cầu giấy phép tạm thời](https://purchase.aspose.com/temporary-license/)
- [Diễn đàn hỗ trợ Aspose](https://forum.aspose.com/c/email/10)

---

**Cập nhật lần cuối:** 2026-03-20  
**Kiểm tra với:** Aspose.Email for Java 25.4 (JDK 16)  
**Tác giả:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}