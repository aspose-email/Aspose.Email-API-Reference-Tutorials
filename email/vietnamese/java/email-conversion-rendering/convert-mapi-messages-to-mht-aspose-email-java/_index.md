---
date: '2026-01-17'
description: Tìm hiểu cách chuyển đổi MSG sang MHT với Aspose.Email cho Java. Hướng
  dẫn từng bước này bao gồm việc tải, lưu và tùy chỉnh mẫu cho việc chuyển đổi email
  thực tế.
keywords:
- convert MAPI messages
- Aspose.Email for Java
- MHT format conversion
title: 'Cách chuyển đổi MSG sang MHT bằng Aspose.Email cho Java: Hướng dẫn toàn diện'
url: /vi/java/email-conversion-rendering/convert-mapi-messages-to-mht-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Chuyển đổi MSG sang MHT bằng Aspose.Email cho Java: Hướng dẫn toàn diện

## Giới thiệu

Việc chuyển đổi **MSG sang MHT** là một yêu cầu phổ biến khi bạn cần lưu trữ hoặc hiển thị các tin nhắn Outlook ở định dạng thân thiện với web. Trong hướng dẫn này, bạn sẽ thấy cách Aspose.Email cho Java thực hiện chuyển đổi một cách đơn giản, cho phép bạn tải tệp MAPI (MSG), điều chỉnh đầu ra bằng các mẫu HTML tùy chỉnh, và lưu nó dưới dạng tệp MHT sẵn sàng cho trình duyệt hoặc hệ thống lưu trữ.

**Bạn sẽ học:**
- Cách tải và phân tích các tệp MSG một cách hiệu quả.  
- Cách cấu hình `MhtSaveOptions` để tạo ra đầu ra MHT tối ưu.  
- Cách áp dụng các mẫu tùy chỉnh để cải thiện khả năng đọc.  
- Các kịch bản thực tế nơi việc chuyển đổi MSG sang MHT mang lại giá trị.

Hãy chuẩn bị môi trường và bắt đầu vào mã.

## Câu trả lời nhanh
- **Ý nghĩa của “chuyển đổi MSG sang MHT” là gì?** Nó chuyển đổi các tệp Outlook `.msg` sang định dạng `.mht` (MHTML) tương thích với web.  
- **Thư viện nào được sử dụng?** Aspose.Email cho Java (aspose email tutorial).  
- **Tôi có cần giấy phép không?** Bản dùng thử miễn phí 30 ngày đủ cho việc đánh giá; cần giấy phép cho môi trường sản xuất.  
- **Phiên bản Java được hỗ trợ?** Java 16 hoặc mới hơn (classifier `jdk16`).  
- **Trường hợp sử dụng điển hình?** Lưu trữ email để tuân thủ hoặc hiển thị chúng trong trình duyệt mà không cần Outlook.

## Quá trình “chuyển đổi MSG sang MHT” là gì?
Quá trình chuyển đổi đọc một tin nhắn Outlook nhị phân (`.msg`) và ghi lại nội dung, tệp đính kèm và siêu dữ liệu của nó vào một tệp MHTML dựa trên HTML duy nhất (`.mht`). Định dạng tệp đơn này bảo tồn bố cục gốc đồng thời có thể xem được trên bất kỳ trình duyệt hiện đại nào.

## Tại sao nên sử dụng Aspose.Email cho Java?
- **API đầy đủ tính năng:** Xử lý tất cả các thuộc tính MAPI, tệp đính kèm và đối tượng nhúng.  
- **Không phụ thuộc vào Outlook:** Hoạt động trên bất kỳ môi trường Java phía máy chủ nào.  
- **Mẫu tùy chỉnh:** Điều chỉnh đầu ra HTML để phù hợp với thương hiệu hoặc tiêu chuẩn báo cáo của bạn.  
- **Hiệu năng cao:** Tối ưu cho các lô lớn và xử lý bất đồng bộ.

## Yêu cầu trước
- **Thư viện Aspose.Email:** Phiên bản 25.4 hoặc mới hơn (classifier `jdk16`).  
- **Môi trường phát triển Java:** Maven đã được cài đặt để quản lý phụ thuộc.  
- **Kiến thức Java cơ bản:** Quen thuộc với I/O tệp và các dự án Maven.

## Cài đặt Aspose.Email cho Java

Để thêm Aspose.Email vào dự án Maven của bạn, bao gồm phụ thuộc sau:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Cấp phép (aspose email tutorial)

Aspose.Email là một sản phẩm thương mại, nhưng bạn có thể bắt đầu với **bản dùng thử miễn phí**:

- **Bản dùng thử miễn phí:** Tính năng đầy đủ trong 30 ngày.  
- **Giấy phép tạm thời:** Gia hạn thời gian đánh giá nếu cần.  
- **Mua:** Nhận giấy phép vĩnh viễn cho việc sử dụng trong môi trường sản xuất.

### Khởi tạo cơ bản

Sau khi thêm phụ thuộc Maven, khởi tạo thư viện trong mã Java của bạn:

```java
// Import necessary classes
import com.aspose.email.License;

public class Main {
    public static void main(String[] args) {
        // Apply license if available
        License license = new License();
        try {
            license.setLicense("path/to/your/license.lic");
        } catch (Exception e) {
            System.out.println("License not applied: " + e.getMessage());
        }
    }
}
```

## Cách chuyển đổi MSG sang MHT bằng Aspose.Email cho Java

### Tải tệp MSG

**Bước 1 – Nhập lớp cần thiết**

```java
import com.aspose.email.MapiMessage;
```

**Bước 2 – Tải tin nhắn từ đĩa**

```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY"; // Ensure this path is correct
MapiMessage msg = MapiMessage.fromFile(dataDir + "MapiTask.msg");
```

Phương thức `MapiMessage.fromFile()` đọc tệp `.msg` và tạo một đối tượng `MapiMessage` có thể thao tác.

### Cấu hình tùy chọn lưu MHT

**Bước 1 – Nhập các lớp tùy chọn lưu**

```java
import com.aspose.email.MhtFormatOptions;
import com.aspose.email.MhtSaveOptions;
import com.aspose.email.SaveOptions;
```

**Bước 2 – Thiết lập các tùy chọn**

```java
MhtSaveOptions opt = SaveOptions.getDefaultMhtml();
opt.setMhtFormatOptions(MhtFormatOptions.RenderTaskFields | MhtFormatOptions.WriteHeader);
```

`RenderTaskFields` đảm bảo các trường đặc thù của nhiệm vụ được bao gồm, trong khi `WriteHeader` thêm các tiêu đề email tiêu chuẩn vào đầu ra MHT.

### Định nghĩa mẫu HTML tùy chỉnh (Tùy chọn)

**Bước 1 – Nhập enum mẫu**

```java
import com.aspose.email.MhtTemplateName;
```

**Bước 2 – Tùy chỉnh các mẫu**

```java
opt.getFormatTemplates().clear();
opt.getFormatTemplates().add(MhtTemplateName.Task.SUBJECT, "<span class='headerLineTitle'>Subject:</span><span class='headerLineText'>{0}</span><br/>");
opt.getFormatTemplates().add(MhtTemplateName.Task.ACTUAL_WORK, "<span class='headerLineTitle'>Actual Work:</span><span class='headerLineText'>{0}</span><br/>");
opt.getFormatTemplates().add(MhtTemplateName.Task.TOTAL_WORK, "<span class='headerLineTitle'>Total Work:</span><span class='headerLineText'>{0}</span><br/>");
opt.getFormatTemplates().add(MhtTemplateName.Task.STATUS, "<span class='headerLineTitle'>Status:</span><span class='headerLineText'>{0}</span><br/>");
opt.getFormatTemplates().add(MhtTemplateName.Task.OWNER, "<span class='headerLineTitle'>Owner:</span><span class='headerLineText'>{0}</span><br/>");
opt.getFormatTemplates().add(MhtTemplateName.Task.PRIORITY, "<span class='headerLineTitle'>Priority:</span><span class='headerLineText'>{0}</span><br/>");
```

Các mẫu này cho phép bạn kiểm soát cách mỗi thuộc tính nhiệm vụ xuất hiện trong tệp MHT cuối cùng, làm cho đầu ra rõ ràng hơn cho người dùng cuối.

### Lưu tin nhắn dưới dạng tệp MHT

**Bước 1 – Xác định thư mục đầu ra**

```java
String outputDir = "YOUR_OUTPUT_DIRECTORY"; // Ensure this path is correct
```

**Bước 2 – Thực hiện thao tác lưu**

```java
msg.save(outputDir + "MapiTask_out.mht", opt);
```

Phương thức `save` ghi tệp MHT đã tùy chỉnh vào đĩa. Kiểm tra đường dẫn `outputDir` trước khi chạy mã.

## Ứng dụng thực tế (Tại sao chuyển đổi MSG sang MHT?)

- **Lưu trữ:** Lưu email trong một định dạng duy nhất, di động mà trình duyệt có thể hiển thị mà không cần Outlook.  
- **Di chuyển:** Chuyển các kho lưu trữ Outlook cũ sang các nền tảng email dựa trên web.  
- **Báo cáo & Phân tích:** Phân tích tệp MHT bằng các bộ phân tích HTML để trích xuất dữ liệu và trí tuệ kinh doanh.  
- **Tuân thủ pháp lý:** Bảo tồn nội dung và siêu dữ liệu gốc của tin nhắn trong định dạng không thể bị giả mạo.

## Cân nhắc về hiệu năng

- **Xử lý theo lô:** Khi xử lý hàng nghìn tệp MSG, xử lý chúng theo lô để tránh tăng đột biến bộ nhớ.  
- **Thực thi bất đồng bộ:** Tận dụng `CompletableFuture` của Java hoặc các dịch vụ executor để chuyển đổi tệp song song.  
- **Dọn dẹp tài nguyên:** Đóng các luồng một cách rõ ràng nếu bạn mở bất kỳ luồng tùy chỉnh nào ngoài API của Aspose.

## Các vấn đề thường gặp & Khắc phục

| Triệu chứng | Nguyên nhân có thể | Cách khắc phục |
|-------------|---------------------|----------------|
| **NullPointerException khi `msg.save`** | Thư mục đầu ra không tồn tại | Tạo thư mục hoặc sử dụng `Files.createDirectories(Paths.get(outputDir));` |
| **Thiếu tệp đính kèm trong MHT** | `MhtSaveOptions` không được thiết lập để nhúng tài nguyên | Sử dụng `opt.setMhtFormatOptions(opt.getMhtFormatOptions() \| MhtFormatOptions.WriteResources);` |
| **Định dạng ngày không đúng** | Cài đặt locale khác nhau | Điều chỉnh `opt.setDateFormat("yyyy-MM-dd HH:mm:ss");` |

## Câu hỏi thường gặp

**H: MSG và MHT có gì khác nhau?**  
T: MSG là định dạng nhị phân độc quyền của Outlook lưu trữ email, tệp đính kèm và siêu dữ liệu. MHT (MHTML) là định dạng tệp đơn dựa trên HTML, gói nội dung email, hình ảnh và CSS, cho phép xem trong bất kỳ trình duyệt nào.

**H: Tôi có thể chuyển đổi các mục MAPI khác như cuộc hẹn hoặc danh bạ không?**  
T: Có. Aspose.Email hỗ trợ chuyển đổi cuộc hẹn, danh bạ và nhiệm vụ sang MHT bằng cách sử dụng các lớp `Mapi*` tương ứng và điều chỉnh tên mẫu.

**H: Tôi có cần kết nối internet để thực hiện chuyển đổi không?**  
T: Không. Tất cả quá trình xử lý diễn ra cục bộ trong môi trường Java; chỉ có việc kiểm tra kích hoạt giấy phép có thể liên hệ với máy chủ của Aspose một lần.

**H: Quá trình chuyển đổi có an toàn với đa luồng không?**  
T: API tự nó an toàn với đa luồng cho các thao tác chỉ đọc. Khi chuyển đổi nhiều tệp đồng thời, tạo các đối tượng `MapiMessage` riêng cho mỗi luồng.

**H: Aspose.Email có thể xử lý tệp MSG lớn đến mức nào?**  
T: Thư viện có thể xử lý các tệp lên tới vài trăm megabyte, nhưng bạn nên giám sát kích thước heap JVM và cân nhắc streaming các tệp đính kèm lớn.

## Kết luận

Bây giờ bạn đã có một quy trình hoàn chỉnh, sẵn sàng cho sản xuất để **chuyển đổi MSG sang MHT** bằng Aspose.Email cho Java. Bằng cách tận dụng các mẫu tùy chỉnh, bạn có thể điều chỉnh đầu ra HTML để phù hợp với thương hiệu hoặc tiêu chuẩn báo cáo của tổ chức, trong khi thư viện thực hiện phần xử lý nặng của việc phân tích định dạng nhị phân của Outlook.

**Các bước tiếp theo:**  
- Thử nghiệm với các giá trị `MhtTemplateName` khác nhau để tạo kiểu cho các loại mục MAPI khác.  
- Tích hợp quá trình chuyển đổi vào công việc batch hoặc dịch vụ REST để xử lý theo yêu cầu.  
- Khám phá các tính năng khác của Aspose.Email như xử lý PST, gửi email và phân tích MIME.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Cập nhật lần cuối:** 2026-01-17  
**Kiểm tra với:** Aspose.Email for Java 25.4 (classifier `jdk16`)  
**Tác giả:** Aspose