---
date: '2026-02-27'
description: Tìm hiểu cách tải tệp MSG và chuyển đổi chúng sang MHTML bằng Aspose.Email
  cho Java, bao gồm cài đặt múi giờ tùy chỉnh và các mẹo xử lý email hàng loạt.
keywords:
- Aspose.Email for Java
- load emails in MHTML format
- custom timezone settings
title: Cách tải MSG và lưu dưới dạng MHTML bằng Aspose.Email cho Java
url: /vi/java/email-message-operations/load-save-emails-mhtml-aspose-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cách tải MSG và lưu dưới dạng MHTML bằng Aspose.Email cho Java

## Giới thiệu

Nếu bạn cần **cách tải tin nhắn** các tệp, điều chỉnh dấu thời gian của chúng và sau đó **chuyển đổi tin nhắn thành mhtml**, bạn đang ở đúng nơi. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn cách tải một email `.msg`, áp dụng tùy chỉnh múi giờ tùy chỉnh và lưu kết quả dưới dạng kho lưu trữ MHTML — Tất cả đều sử dụng Aspose.Email cho Java. Dù bạn đang xử lý một tin nhắn duy nhất hay một quy trình **xử lý email hàng loạt**, các bước này sẽ cung cấp nền tảng vững chắc.

**Bạn sẽ học được gì**
- Cách tải một `MailMessage` từ tệp `.msg`.
- Cách cài đặt tùy chọn múi giờ và hiện tại ngày.
- Cách lưu tin nhắn dưới dạng MHTML với định dạng chính xác.
- Mẹo mở rộng cách tiếp cận cho lô bản script.

Sẵn sàng để tăng cường quy trình làm việc email của bạn? Trước tiên hãy chuẩn bị sẵn sàng môi trường.

## Trả lời nhanh
- **Thư viện chính là gì?** Aspose.Email for Java.
- **Tôi có thể tải MSG và xuất sang MHTML trong một bước không?** Không, bạn tải, điều chỉnh rồi lưu lại.
- **Tôi có cần giấy phép sản xuất không?** Có, cần có giấy phép Aspose.Email hợp lệ.
- **Có hỗ trợ xử lý múi giờ không?** Có, thông qua `setTimeZoneOffset`.
- **Điều này có thể được sử dụng trong xử lý hàng loạt không?** Hoàn toàn có thể – gói các bước trong một vòng lặp.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy chắc chắn rằng bạn có thứ sau:

### Thư viện và thư viện phụ thuộc bắt buộc
- Thư viện **Aspose.Email for Java** phiên bản 25.4 (jdk16 classifier)
- Kiến thức cơ bản về Java.
- Một IDE như IntelliJ IDEA hoặc Eclipse.

### Yêu cầu thiết lập môi trường
- JDK16hoặc mới hơn đã được cài đặt.
- Maven để quản lý phụ thuộc.

## Thiết lập Aspose.Email cho Java

Để thêm thư viện vào dự án Maven, bao gồm các phụ thuộc sau:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Các bước lấy giấy phép

Bắt đầu **dùng thử miễn phí** hoặc lấy **giấy phép tạm thời** để đánh giá đầy đủ giá trị của thư viện mà không có giới hạn. Đối với việc sử dụng lâu dài, hãy cân nhắc mua giấy phép:

- [Dùng thử miễn phí](https://releases.aspose.com/email/java/)
- [Giấy phép tạm thời](https://purchase.aspose.com/temporary-license/)
- [Mua giấy phép](https://purchase.aspose.com/buy)

### Khởi tạo cơ bản

Sau khi thêm phụ thuộc, khởi tạo giấy phép trong mã Java của bạn:

```java
import com.aspose.email.License;

License license = new License();
license.setLicense("path_to_your_license_file.lic");
```

## Hướng dẫn thực hiện

Chúng tôi sẽ chia sẻ việc khai triển thành ba tính năng rõ ràng.

### Tính năng 1: Tải Thư từ một Tệp

#### Tổng quan
Tải một tệp `.msg` cho phép bạn truy cập đầy đủ cài đặt tới email nội dung, tệp đính kèm và siêu dữ liệu.

#### Từng bước một

**Nhập các lớp được yêu cầu**

```java
import com.aspose.email.MailMessage;
import com.aspose.email.MsgLoadOptions;
```

**Tải email**

```java
String filename = "YOUR_DOCUMENT_DIRECTORY/MSG file with RTF Formatting.msg";
MailMessage msg = MailMessage.load(filename, new MsgLoadOptions());
```

`MsgLoadOptions` cho phép bạn kiểm soát cách diễn giải tệp MSG; cài đặt mặc định hoạt động trong hầu hết các trường hợp.

### Tính năng 2: Cài đặt ngày hiện tại và độ lệch múi giờ tùy chỉnh

#### Tổng quan
Dấu thời gian chính xác là điều cần thiết khi bạn giao dịch với người dùng ở các khu vực khác nhau.

**Đặt ngày hiện tại**

```java
import java.util.Date;

msg.setDate(new Date());
```

**Áp dụng độ lệch múi giờ tùy chỉnh (ví dụ: UTC+5)**

```java
msg.setTimeZoneOffset(5 * 60 * 60 * 1000); // 5 hours ahead of UTC in milliseconds.
```

Độ lệch được biểu thị bằng mili giây, vì vậy bạn cũng có thể truyền các giá trị âm cho các múi giờ phía tây UTC.

### Tính năng 3: Lưu tin nhắn email dưới dạng tệp MHTML

#### Tổng quan
MHTML đóng gói nội dung HTML và các tài nguyên nhúng vào một tệp duy nhất, rất phù hợp để lưu trữ hoặc chia sẻ.

**Cấu hình các tùy chọn lưu**

```java
import com.aspose.email.MhtSaveOptions;
import com.aspose.email.MhtFormatOptions;

MhtSaveOptions mhtOptions = new MhtSaveOptions();
mhtOptions.setMhtFormatOptions(MhtFormatOptions.WriteHeader);
```

**Lưu email**

```java
msg.save("YOUR_OUTPUT_DIRECTORY/ExportToMHTWithCustomTimezone_out.mhtml", mhtOptions);
```

Tệp `.mhtml` kết quả vẫn giữ nguyên định dạng, hình ảnh và tệp đính kèm ban đầu.

## Tại sao cần chuyển đổi MSG sang MHTML?

Việc chuyển đổi tệp MSG sang MHTML cung cấp cho bạn một định dạng tệp duy nhất thân thiện với web, có thể mở được trên bất kỳ trình duyệt hiện đại nào. Điều này đặc biệt hữu ích cho:

- **Lưu trữ pháp lý** khi cần bản sao hình ảnh chính xác.

- **Chia sẻ đa nền tảng** mà không cần Outlook.

- **Nhúng email** vào các trang web hoặc tài liệu.

## Mẹo xử lý email hàng loạt

Nếu bạn cần **xử lý email hàng loạt**, hãy gói các bước tải, điều chỉnh múi giờ và lưu vào trong một vòng lặp lặp lại trên thư mục chứa các tệp `.msg`. Hãy nhớ:

1. Sử dụng lại một phiên bản `License` duy nhất để tránh lãng phí tài nguyên.

2. Giải phóng tài nguyên sau mỗi lần lặp (`msg.dispose()` nếu có).

3. Ghi lại bất kỳ lỗi nào vào một tệp riêng để xem xét sau.

## Ứng dụng thực tiễn

1. **Lưu trữ email:** Bảo quản thông tin liên lạc ở định dạng di động để tuân thủ quy định.

2. **Lập lịch toàn cầu:** Điều chỉnh dấu thời gian về múi giờ thống nhất trước khi gửi thông báo.

3. **Tích hợp CRM:** Tự động nhập email đã lưu trữ vào hệ thống CRM dưới dạng tệp đính kèm MHTML.

## Cân nhắc về hiệu năng

- **Quản lý bộ nhớ:** Xử lý các lô lớn theo từng phần để giữ mức sử dụng bộ nhớ thấp.

- **Tối ưu hóa I/O:** Sử dụng luồng đệm nếu bạn đang đọc/ghi nhiều tệp.

- **Thực thi song song:** Cân nhắc sử dụng `ForkJoinPool` của Java để xử lý song song, nhưng đảm bảo tính an toàn luồng của các đối tượng Aspose.

## Kết luận

Bây giờ bạn đã biết **cách tải tệp msg**, áp dụng độ lệch múi giờ tùy chỉnh và **chuyển đổi msg sang mhtml** bằng Aspose.Email cho Java. Các kỹ thuật này có thể được mở rộng để xử lý các tác vụ **xử lý email hàng loạt**, cung cấp cho bạn một giải pháp mạnh mẽ để lưu trữ, di chuyển và tự động hóa email.

**Các bước tiếp theo** Khám phá thêm các tính năng của Aspose.Email như xử lý tệp đính kèm, trích xuất mục lịch hoặc gửi SMTP bằng cách truy cập tài liệu chính thức [documentation](https://reference.aspose.com/email/java/).

## Câu hỏi thường gặp

**H: Tôi có thể tải email từ các định dạng khác ngoài .msg không?**
Đáp: Có, Aspose.Email hỗ trợ EML, MSG, MHT và một số định dạng khác.

**H: Làm thế nào tôi có thể xử lý các tệp email rất lớn một cách hiệu quả?**
Đáp: Sử dụng API truyền dữ liệu do Aspose.Email cung cấp để đọc/ghi dữ liệu theo từng phần, giảm áp lực bộ nhớ.

**H: Có thể sửa đổi tệp đính kèm trong MailMessage không?**
Đáp: Chắc chắn rồi. Bạn có thể thêm, xóa hoặc thay thế tệp đính kèm thông qua bộ sưu tập `MailMessage.getAttachments()`.

** **Hỏi: Nếu độ lệch múi giờ của tôi là âm (chậm hơn UTC) thì sao?**
Trả lời: Hãy truyền giá trị mili giây âm cho `setTimeZoneOffset`, ví dụ: `-3 * 60 * 60 * 1000` cho UTC-3.

**Hỏi: Tôi có thể sử dụng Aspose.Email trong các dự án thương mại không?**
Trả lời: Có, miễn là bạn có giấy phép thương mại hợp lệ.

**Hỏi: Làm thế nào để xử lý hàng nghìn tệp MSG mà không bị hết bộ nhớ?**
Trả lời: Xử lý các tệp theo lô, giải phóng mỗi `MailMessage` sau khi lưu và xem xét sử dụng mẫu `try-with-resources` của Java để tự động dọn dẹp.

** ## Tài liệu tham khảo
- [Tài liệu hướng dẫn](https://reference.aspose.com/email/java/)
- [Tải xuống thư viện](https://releases.aspose.com/email/java/)
- [Mua giấy phép](https://purchase.aspose.com/buy)

- [Dùng thử miễn phí](https://releases.aspose.com/email/java/)
- [Giấy phép tạm thời](https://purchase.aspose.com/temporary-license/)
- [Diễn đàn hỗ trợ](https://forum.aspose.com/c/email/10)

---

**Cập nhật lần cuối:** 27/02/2026
**Đã kiểm thử với:** Aspose.Email for Java 25.4 (phân loại jdk16)
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}