---
"date": "2025-05-29"
"description": "Tìm hiểu cách quản lý hiệu quả nhiều thuộc tính trong tin nhắn MAPI bằng Aspose.Email cho Java. Hướng dẫn này bao gồm thiết lập float, double, long và nhiều loại khác."
"title": "Thiết lập nhiều thuộc tính MAPI trong Java với Aspose.Email&#58; Hướng dẫn toàn diện"
"url": "/vi/java/mapi-operations/aspose-email-java-set-mapi-properties/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Thiết lập nhiều thuộc tính MAPI trong Java với Aspose.Email: Hướng dẫn toàn diện

## Giới thiệu

Quản lý các thuộc tính tin nhắn MAPI hiệu quả là rất quan trọng để nâng cao các ứng dụng Java của bạn. Với Aspose.Email for Java, bạn có thể thiết lập nhiều thuộc tính như float, double, long, short, boolean và các thuộc tính tùy chỉnh một cách liền mạch. Hướng dẫn này sẽ hướng dẫn bạn qua nhiều phương pháp khác nhau để đạt được điều này.

**Những gì bạn sẽ học được:**
- Thiết lập nhiều thuộc tính trong tin nhắn MAPI bằng Aspose.Email Java
- Hiểu các loại tài sản khác nhau và cách sử dụng của chúng
- Ví dụ mã thực tế để triển khai

Chúng ta hãy bắt đầu bằng cách tìm hiểu các điều kiện tiên quyết.

## Điều kiện tiên quyết

Để thực hiện theo, hãy đảm bảo bạn có:
- **Bộ phát triển Java (JDK):** Đã cài đặt JDK 8 trở lên.
- **Thư viện Aspose.Email:** Phiên bản 25.4 được khuyến nghị.
- **Thiết lập Maven:** Maven phải được cấu hình trong IDE của bạn để quản lý sự phụ thuộc.

### Thư viện bắt buộc

Bao gồm Aspose.Email như một phần phụ thuộc trong `pom.xml`:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Mua lại giấy phép
- **Dùng thử miễn phí:** Bắt đầu bằng bản dùng thử miễn phí để khám phá các tính năng.
- **Giấy phép tạm thời:** Có thể dùng thử nghiệm mở rộng mà không bị giới hạn.
- **Mua:** Hãy cân nhắc mua nếu nó phù hợp với nhu cầu của bạn.

## Thiết lập Aspose.Email cho Java

Đảm bảo Aspose.Email được cấu hình đúng trong môi trường phát triển của bạn:
1. **Nhập phụ thuộc:** Giải quyết các vấn đề phụ thuộc của Maven.
2. **Thiết lập giấy phép:**
   - Tải xuống tệp giấy phép từ [Đặt ra](https://purchase.aspose.com/buy).
   - Áp dụng bằng cách:
     ```java
     com.aspose.email.License license = new com.aspose.email.License();
     license.setLicense("path/to/your/license.lic");
     ```

Sau khi thiết lập xong, chúng ta hãy khám phá cách thiết lập nhiều thuộc tính khác nhau.

## Hướng dẫn thực hiện

### Thiết lập nhiều thuộc tính Float

Thiết lập thuộc tính float cho phép lưu trữ dữ liệu số hiệu quả:

#### Tổng quan
Tính năng này minh họa cách thêm nhiều giá trị float làm thuộc tính tin nhắn MAPI bằng Aspose.Email cho Java.

#### Các bước
1. **Tạo và khởi tạo tin nhắn**
   ```java
   import java.util.ArrayList;
   import com.aspose.email.MapiMessage;
   import com.aspose.email.MapiProperty;
   import com.aspose.email.system.collections.IList;

   MapiMessage msg = new MapiMessage();
   ```
2. **Thêm giá trị Float vào danh sách**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((float) 1);
   values.addItem((float) 2);
   ```
3. **Đặt Thuộc tính với Mã định danh duy nhất**
   ```java
   msg.setProperty(new MapiProperty(0x23901004, values));
   ```
*Giải thích:* Thẻ thuộc tính `0x23901004` xác định tập thuộc tính float này.

### Thiết lập nhiều thuộc tính Double

Thuộc tính kép lưu trữ số dấu phẩy động có độ chính xác cao:

#### Tổng quan
Phần này hiển thị cách lưu trữ nhiều giá trị double dưới dạng thuộc tính tin nhắn MAPI.

#### Các bước
1. **Khởi tạo tin nhắn**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Điền giá trị kép**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((double) 1);
   values.addItem((double) 2);
   ```
3. **Gán cho thẻ thuộc tính**
   ```java
   msg.setProperty(new MapiProperty(0x23901005, values));
   ```

### Thiết lập nhiều thuộc tính APPTIME

Thuộc tính APPTIME lưu trữ khoảng thời gian một cách hiệu quả:

#### Tổng quan
Tính năng này minh họa việc sử dụng số có độ chính xác kép để biểu diễn thời gian.

#### Các bước
1. **Tạo đối tượng tin nhắn**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Thêm giá trị thời gian**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem(30456.34);
   values.addItem(40655.45);
   ```
3. **Thiết lập Thuộc tính**
   ```java
   msg.setProperty(new MapiProperty(0x23901007, values));
   ```

### Thiết lập nhiều thuộc tính dài

Các thuộc tính dài lý tưởng cho các số nguyên lớn:

#### Tổng quan
Tính năng này tập trung vào việc thiết lập nhiều giá trị số nguyên dài trong một tin nhắn.

#### Các bước
1. **Khởi tạo tin nhắn MAPI**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Thêm giá trị dài**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((long) 30456);
   values.addItem((long) 40655);
   ```
3. **Định nghĩa thẻ thuộc tính**
   ```java
   msg.setProperty(new MapiProperty(0x23901014, values));
   ```

### Thiết lập nhiều thuộc tính ngắn

Thuộc tính ngắn lưu trữ dữ liệu số nguyên nhỏ một cách hiệu quả:

#### Tổng quan
Hướng dẫn này trình bày cách thiết lập số nguyên ngắn làm thuộc tính tin nhắn.

#### Các bước
1. **Khởi tạo tin nhắn**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Thêm giá trị ngắn**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((short) 1);
   values.addItem((short) 2);
   ```
3. **Gán thẻ thuộc tính**
   ```java
   msg.setProperty(new MapiProperty(0x23901002, values));
   ```

### Thiết lập nhiều thuộc tính Boolean

Thuộc tính Boolean lưu trữ trạng thái đúng/sai:

#### Tổng quan
Tìm hiểu cách thiết lập nhiều giá trị boolean trong một tin nhắn.

#### Các bước
1. **Tạo đối tượng tin nhắn**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Thêm giá trị Boolean**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem(true);
   values.addItem(false);
   ```
3. **Đặt Thuộc tính với Mã định danh**
   ```java
   msg.setProperty(new MapiProperty(0x2390100b, values));
   ```

### Thiết lập Thuộc tính Null

Việc thiết lập rõ ràng một thuộc tính là null có thể hữu ích:

#### Tổng quan
Phần này trình bày cách gán giá trị null cho một thuộc tính.

#### Các bước
1. **Khởi tạo tin nhắn**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Gán Thuộc tính Null**
   ```java
   msg.setProperty(new MapiProperty(0x67400001, new byte[1]));
   ```

### Thiết lập Thuộc tính Long có Tên với ID Tùy chỉnh và UUID

Đối với các tình huống phức tạp, hãy đặt các thuộc tính được đặt tên:

#### Tổng quan
Tính năng này minh họa cách thiết lập thuộc tính dài với mã định danh và UUID tùy chỉnh.

#### Các bước
1. **Khởi tạo tin nhắn**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Thêm giá trị dài**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((int) 4);
   UUID uuid = UUID.randomUUID();
   ```
3. **Tạo và lập bản đồ thuộc tính**
   ```java
   MapiProperty property = new MapiProperty(msg.getNamedPropertyMapping().getNextAvailablePropertyId(com.aspose.email.MapiPropertyType.PT_MV_LONG), values);
   msg.getNamedPropertyMapping().addNamedPropertyMapping(property, (long) 0x00008028, uuid);
   msg.setProperty(property);
   ```

### Thiết lập Thuộc tính Tùy chỉnh với Tên

Có thể đặt tên cho các thuộc tính tùy chỉnh để dễ nhận dạng hơn:

#### Tổng quan
Hướng dẫn này hướng dẫn cách thiết lập các thuộc tính có tên tùy chỉnh.

#### Các bước
1. **Khởi tạo đối tượng tin nhắn**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Xác định Thuộc tính Tùy chỉnh**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem("Custom Value");
   UUID uuid = UUID.randomUUID();
   
   MapiProperty property = new MapiProperty(msg.getNamedPropertyMapping().getNextAvailablePropertyId(com.aspose.email.MapiPropertyType.PT_STRING), values);
   msg.getNamedPropertyMapping().addNamedPropertyMapping(property, "CustomName", uuid);
   ```

### Thiết lập và xác thực thuộc tính

Đảm bảo các thuộc tính được thiết lập chính xác là rất quan trọng:

#### Tổng quan
Phần này đề cập đến việc thiết lập và xác thực nhiều thuộc tính trong thông báo MAPI.

#### Các bước
1. **Thiết lập Thuộc tính**
   Thực hiện theo các ví dụ trước để thiết lập thuộc tính.
2. **Xác thực Thuộc tính**
   ```java
   if (msg.getProperties().containsKey(0x23901004)) {
       System.out.println("Property is set correctly.");
   } else {
       System.err.println("Property setting failed.");
   }
   ```

## Phần kết luận

Hướng dẫn này cung cấp một cách tiếp cận toàn diện để quản lý nhiều thuộc tính trong tin nhắn MAPI bằng Aspose.Email cho Java. Bằng cách làm theo các bước này, bạn có thể lưu trữ và quản lý hiệu quả nhiều loại dữ liệu khác nhau trong ứng dụng của mình.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}