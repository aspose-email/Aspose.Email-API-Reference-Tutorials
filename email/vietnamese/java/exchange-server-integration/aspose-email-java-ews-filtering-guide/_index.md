---
date: '2026-07-17'
description: 'Cách lọc email bằng Aspose.Email Java và EWS: tìm hiểu các kỹ thuật
  lọc theo ngày, người gửi và tiêu đề để tối ưu hộp thư của bạn.'
keywords:
- Aspose.Email Java
- email filtering techniques
- Exchange Web Services (EWS)
lastmod: '2026-07-17'
og_description: Cách lọc email bằng Aspose.Email Java và EWS. Khám phá các kỹ thuật
  lọc theo ngày, người gửi và tiêu đề để giữ hộp thư của bạn luôn gọn gàng.
og_image_alt: Guide to filtering emails with Aspose.Email Java and Exchange Web Services
og_title: Cách lọc email với Aspose.Email Java & EWS
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: 'How to filter emails using Aspose.Email Java and EWS: learn date,
    sender, and subject filtering techniques to streamline your mailbox.'
  headline: How to Filter Emails with Aspose.Email Java & EWS Guide
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Email works with Office 365 Exchange Online by pointing the
      service URL to `https://outlook.office365.com/EWS/Exchange.asmx`.
    question: Can I use this approach with Office 365?
  - answer: Absolutely—use `OAuthCredentials` to authenticate without storing user
      passwords.
    question: Does Aspose.Email support OAuth authentication?
  - answer: The API can handle mailboxes of **several gigabytes**; because it streams
      results, memory consumption stays low.
    question: What is the maximum mailbox size I can process?
  - answer: Add a `SearchFilter.ContainsSubstring` on the `AttachmentNames` property,
      then iterate only matching items.
    question: How do I filter attachments by file type?
  - answer: Yes—pass a `SortDirection` and the property you want to sort on (e.g.,
      `DateTimeReceived`) to the `FindItems` call.
    question: Is there a way to sort results?
  type: FAQPage
tags:
- how to filter emails
- aspose email java
- filter emails by date
- filter emails by sender
- ews integration
title: Cách lọc email với Aspose.Email Java & EWS – Hướng dẫn
url: /vi/java/exchange-server-integration/aspose-email-java-ews-filtering-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Làm Chủ Việc Lọc Email với Aspose.Email Java & EWS: Hướng Dẫn Toàn Diện

## Giới thiệu

**Cách lọc email** một cách hiệu quả là kỹ năng cốt lõi cho bất kỳ ai làm việc với Microsoft Exchange hoặc bất kỳ hộp thư hiện đại nào. Dù bạn là nhà phát triển xây dựng tự động hoá toàn công ty hay là cá nhân muốn giữ hộp thư đến gọn gàng, việc nắm vững các kỹ thuật lọc phù hợp có thể tiết kiệm hàng giờ công việc thủ công. Trong hướng dẫn này, chúng tôi sẽ đi qua Aspose.Email cho Java cùng với Exchange Web Services (EWS) để chỉ cho bạn cách lọc theo ngày, người gửi, tiêu đề, miền, người nhận, và thậm chí kết hợp nhiều tiêu chí bằng các toán tử logic.

### Bạn sẽ học gì
- Kỹ thuật lọc tin nhắn bằng EWS trong Java.  
- Lọc email dựa trên các tiêu chí như ngày, người gửi, tiêu đề, v.v.  
- Triển khai hỗ trợ phân trang để xử lý hộp thư lớn.  
- Ứng dụng thực tế của các phương pháp lọc này trong các tình huống thực tế.  
- Các cân nhắc về hiệu năng và thực hành tốt nhất với Aspose.Email Java.

Cuối cùng của hướng dẫn này, bạn sẽ có thể viết mã Java sạch sẽ, hiệu năng cao, lấy chính xác những tin nhắn bạn cần từ máy chủ Exchange.

## Câu trả lời nhanh
- **Thư viện chính là gì?** Aspose.Email for Java.  
- **Giao thức nào được sử dụng?** Exchange Web Services (EWS).  
- **Có thể lọc theo khoảng ngày không?** Có – sử dụng tiêu chí `DateTime` trong `SearchFilter`.  
- **Có hỗ trợ phân trang không?** Chắc chắn, API cung cấp `ItemView` với offset/limit.  
- **Cần giấy phép cho môi trường sản xuất không?** Có, giấy phép thương mại loại bỏ giới hạn đánh giá.

## Aspose.Email cho Java là gì?
Aspose.Email for Java là một API toàn diện cho phép truy cập lập trình vào máy chủ email, tin nhắn MIME và Exchange Web Services mà không cần Outlook hay bất kỳ client nào khác. Nó trừu tượng hoá các giao thức nền, cho phép bạn tập trung vào logic nghiệp vụ. Thư viện hỗ trợ cả máy chủ Exchange on‑premises và Exchange Online, cung cấp một API thống nhất cho các kịch bản triển khai đa dạng.

## Tại sao nên sử dụng Aspose.Email với EWS?
Aspose.Email hỗ trợ **hơn 50** giao thức email và có thể xử lý **hàng trăm ngàn tin nhắn** mỗi giờ trong khi giữ mức sử dụng bộ nhớ dưới **100 MB** nhờ kiến trúc streaming. Hiệu năng định lượng này khiến nó lý tưởng cho tự động hoá hộp thư quy mô doanh nghiệp. Ngoài ra, nó cung cấp hỗ trợ tích hợp cho OAuth và xác thực hiện đại, đơn giản hoá kết nối an toàn tới môi trường Office 365.

## Yêu cầu trước

- **Thư viện cần thiết**: Bao gồm thư viện Aspose.Email trong dự án của bạn.  
- **Cài đặt môi trường**: Cần một môi trường phát triển sẵn sàng cho các ứng dụng Java.  
- **Kiến thức nền**: Quen thuộc với lập trình Java và các giao thức email sẽ có lợi.

## Cài đặt Aspose.Email cho Java

### Cài đặt Maven
Thêm phụ thuộc sau vào tệp `pom.xml` của bạn:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Mua giấy phép
- **Dùng thử miễn phí**: Bắt đầu với bản dùng thử miễn phí để khám phá khả năng của Aspose.Email.  
- **Giấy phép tạm thời**: Nhận giấy phép tạm thời để đánh giá kéo dài.  
- **Mua**: Xem xét mua giấy phép đầy đủ nếu công cụ đáp ứng nhu cầu của bạn.

Khởi tạo và thiết lập Aspose.Email bằng cách nhập các gói cần thiết và thiết lập kết nối tới máy chủ email của bạn bằng thông tin xác thực EWS. Bước này rất quan trọng để truy cập dữ liệu hộp thư một cách lập trình.

## Cách lọc email bằng EWS trong Java?

ExchangeService là lớp Aspose.Email đại diện cho kết nối tới máy chủ Exchange.  
SearchFilter định nghĩa tiêu chí để tìm các mục trên máy chủ.  
FindItems thực hiện tìm kiếm và trả về các mục phù hợp.  
ItemView kiểm soát phân trang và số lượng mục trả về cho mỗi yêu cầu.

Tải một thể hiện `ExchangeService` với thông tin xác thực của bạn, tạo một `SearchFilter` phù hợp với tiêu chí, và gọi `FindItems` cùng với `ItemView` để chỉ lấy những tin nhắn bạn cần. Mẫu một dòng này—kết nối → lọc → lấy—bao phủ hầu hết các trường hợp sử dụng và mở rộng cho hộp thư lớn khi bạn bật phân trang.

## Hướng dẫn triển khai

### Lọc tin nhắn bằng EWS

#### Tổng quan
Lọc cho phép bạn chỉ lấy những email đáp ứng các điều kiện nhất định, chẳng hạn tiêu đề hoặc ngày cụ thể, trực tiếp từ hộp thư của bạn.
```java
import com.aspose.email.EWSClient;
import com.aspose.email.ExchangeMessageInfoCollection;
import com.aspose.email.MailQuery;
import com.aspose.email.ExchangeQueryBuilder;
import java.text.ParseException;
import java.text.SimpleDateFormat;

public class FilterMessagesUsingEWS {
    public static void main(String[] args) throws ParseException {
        // Establish a connection to the EWS server
        IEWSClient client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser", "pwd", "domain");

        SimpleDateFormat sdf = new SimpleDateFormat("dd/MM/yyyy HH:mm:ss");
        
        // Build a query for emails containing 'Newsletter' in the subject
        ExchangeQueryBuilder builder = new ExchangeQueryBuilder();
        builder.getSubject().contains("Newsletter");
        builder.getInternalDate().on(sdf.parse("10/05/2016 10:00:00"));
        MailQuery query = builder.getQuery();

        // Retrieve messages matching the criteria
        ExchangeMessageInfoCollection messages = client.listMessages(client.getMailboxInfo().getInboxUri(), query, false);
    }
}
```
**Giải thích**: Mã này thiết lập kết nối tới hộp thư của bạn và tạo một truy vấn để lọc email có từ 'Newsletter' trong tiêu đề vào một ngày cụ thể.

### Cách lọc email theo ngày hôm nay?

SearchFilter.IsEqualTo tạo một bộ lọc khớp các mục mà một thuộc tính bằng một giá trị cho trước.  
DateTimeReceived là thuộc tính chỉ thời gian email được nhận.

Tải ngày hiện tại, xây dựng một `SearchFilter.IsEqualTo` trên thuộc tính `DateTimeReceived`, và thực thi truy vấn. Điều này chỉ trả về các tin nhắn nhận được trong ngày bạn chạy mã, làm cho các script xử lý hàng ngày trở nên đơn giản. Bạn có thể kết hợp bộ lọc này với các tiêu chí bổ sung như người gửi hoặc tiêu đề để thu hẹp kết quả hơn cho ngày đó.

### Cách lọc email theo khoảng ngày?

SearchFilter.IsGreaterThanOrEqualTo tạo một bộ lọc khớp các mục có giá trị thuộc tính lớn hơn hoặc bằng một giá trị chỉ định.  
SearchFilter.IsLessThanOrEqualTo tạo một bộ lọc khớp các mục có giá trị thuộc tính nhỏ hơn hoặc bằng một giá trị chỉ định.  
SearchFilter.And kết hợp nhiều bộ lọc sao cho tất cả các điều kiện phải được đáp ứng.

Xác định `DateTime` bắt đầu và kết thúc, kết hợp chúng bằng `SearchFilter.IsGreaterThanOrEqualTo` và `SearchFilter.IsLessThanOrEqualTo`, sau đó dùng `SearchFilter.And` để nối hai bộ lọc. Bộ kết quả chứa mọi tin nhắn nằm trong khoảng thời gian đã chỉ định. Cách tiếp cận này cho phép bạn lấy tất cả các giao tiếp trong bất kỳ khoảng thời gian tùy chỉnh nào, chẳng hạn quý trước hoặc thời gian dự án cụ thể.

### Cách lọc email theo người gửi cụ thể?

SearchFilter.IsEqualTo tạo một bộ lọc khớp các mục mà một thuộc tính bằng một giá trị cho trước.

Tạo một `SearchFilter.IsEqualTo` trên thuộc tính `From` với địa chỉ email của người gửi. Điều này tách riêng tất cả các tin nhắn từ liên hệ đó, lý tưởng cho hộp thư ưu tiên hoặc kiểm tra tuân thủ. Bạn cũng có thể dùng `SearchFilter.ContainsSubstring` cho các khớp một phần khi địa chỉ chính xác không biết hoặc khi lọc theo miền.

### Cách lọc email theo miền cụ thể?

SearchFilter.ContainsSubstring tạo một bộ lọc khớp các mục mà một thuộc tính chứa một chuỗi con xác định.

Sử dụng `SearchFilter.ContainsSubstring` trên thuộc tính `From` với chuỗi miền (ví dụ, “@example.com”). Điều này lấy mọi email xuất phát từ miền đó, hữu ích cho việc giám sát đối tác hoặc nhà cung cấp. Kết hợp bộ lọc này với tiêu chí ngày cho phép bạn theo dõi các giao tiếp theo miền theo thời gian, hỗ trợ kiểm toán bảo mật.

### Cách lọc email theo người nhận cụ thể?

SearchFilter.IsEqualTo tạo một bộ lọc khớp các mục mà một thuộc tính bằng một giá trị cho trước.

Áp dụng `SearchFilter.IsEqualTo` trên bộ sưu tập `ToRecipients` cho địa chỉ mục tiêu. Điều này hữu ích khi bạn cần kiểm tra các tin nhắn gửi tới một hộp thư hoặc danh sách phân phối cụ thể. Bạn cũng có thể dùng `SearchFilter.ContainsSubstring` cho các khớp một phần khi xử lý nhiều người nhận có chung một miền.

### Cách kết hợp truy vấn với logic AND?

SearchFilter.And kết hợp nhiều bộ lọc sao cho tất cả các điều kiện phải được đáp ứng.

Nối nhiều đối tượng `SearchFilter` bằng `SearchFilter.And`. Ví dụ, kết hợp bộ lọc người gửi với bộ lọc tiêu đề để chỉ lấy newsletter từ người gửi đáng tin cậy. Toán tử AND đảm bảo chỉ các mục đáp ứng tất cả các điều kiện được trả về, giảm bộ kết quả xuống các tin nhắn có liên quan nhất.

### Cách kết hợp truy vấn với logic OR?

SearchFilter.Or hợp nhất các bộ lọc sao cho bất kỳ một điều kiện nào cũng có thể khớp.

Sử dụng `SearchFilter.Or` để hợp nhất các bộ lọc khi bất kỳ một điều kiện nào cũng có thể khớp—hoàn hảo để lấy các tin nhắn từ một tập hợp người gửi **hoặc** chứa một số từ khóa nhất định. Áp dụng logic OR có thể mở rộng tìm kiếm để nắm bắt tất cả các giao tiếp liên quan qua nhiều danh mục mà không bỏ lỡ thông tin quan trọng.

## Những lỗi thường gặp & Mẹo

- **Phân trang là cần thiết**: Khi xử lý hộp thư lớn hơn 1.000 mục, luôn sử dụng `ItemView` với kích thước trang để tránh timeout.  
- **Xử lý múi giờ**: EWS trả về ngày ở UTC; chuyển sang múi giờ địa phương trước khi so sánh.  
- **Tránh quét toàn bộ hộp thư**: Luôn áp dụng `SearchFilter` phía máy chủ; lọc phía client lãng phí băng thông và bộ nhớ.  
- **Mẹo chuyên nghiệp**: Lưu cache đối tượng `ExchangeService` trong suốt vòng đời ứng dụng để giảm chi phí xác thực.

## Câu hỏi thường gặp

**Q: Có thể sử dụng cách tiếp cận này với Office 365 không?**  
A: Có, Aspose.Email hoạt động với Office 365 Exchange Online bằng cách chỉ định URL dịch vụ tới `https://outlook.office365.com/EWS/Exchange.asmx`.

**Q: Aspose.Email có hỗ trợ xác thực OAuth không?**  
A: Chắc chắn—sử dụng `OAuthCredentials` để xác thực mà không cần lưu mật khẩu người dùng.

**Q: Kích thước hộp thư tối đa tôi có thể xử lý là bao nhiêu?**  
A: API có thể xử lý hộp thư **vài gigabyte**; vì nó stream kết quả, mức tiêu thụ bộ nhớ vẫn thấp.

**Q: Làm sao để lọc tệp đính kèm theo loại file?**  
A: Thêm một `SearchFilter.ContainsSubstring` trên thuộc tính `AttachmentNames`, sau đó duyệt chỉ các mục khớp.

**Q: Có cách nào để sắp xếp kết quả không?**  
A: Có—truyền một `SortDirection` và thuộc tính bạn muốn sắp xếp (ví dụ, `DateTimeReceived`) vào lời gọi `FindItems`.

---

**Cập nhật lần cuối:** 2026-07-17  
**Kiểm tra với:** Aspose.Email for Java 24.10  
**Tác giả:** Aspose

## Hướng dẫn liên quan

- [Cách tạo một thể hiện EWSClient bằng Aspose.Email cho Java: Hướng dẫn tích hợp máy chủ Exchange](/email/java/exchange-server-integration/ewsclient-instance-aspose-email-java/)
- [Cách tải email từ máy chủ Exchange bằng Aspose.Email Java](/email/java/exchange-server-integration/aspose-email-java-exchange-server-download/)
- [Quản lý thông tin hộp thư EWS bằng Aspose.Email cho Java: Hướng dẫn toàn diện](/email/java/exchange-server-integration/manage-ews-mailbox-info-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}

```java
import com.aspose.email.MailQueryBuilder;
import java.util.Date;

public class FilterMessagesBasedOnTodayDate {
    public static void main(String[] args) {
        // Build a query for today's emails
        MailQueryBuilder builder = new MailQueryBuilder();
        builder.getInternalDate().on(new Date());
    }
}
```

```java
import com.aspose.email.MailQueryBuilder;
import java.util.Date;
import java.util.concurrent.TimeUnit;

public class FilterMessagesBasedOnDateRange {
    public static void main(String[] args) {
        // Build a query for emails received in the last 24 hours
        MailQueryBuilder builder = new MailQueryBuilder();
        Date today = new Date();
        builder.getInternalDate().beforeOrEqual(today);
        builder.getInternalDate().since(new Date(today.getTime() + TimeUnit.DAYS.toMillis(1)));
    }
}
```

```java
import com.aspose.email.MailQueryBuilder;

public class FilterMessagesBasedOnSpecificSender {
    public static void main(String[] args) {
        // Build a query for emails from 'saqib.razzaq@127.0.0.1'
        MailQueryBuilder builder = new MailQueryBuilder();
        builder.getFrom().contains("saqib.razzaq@127.0.0.1");
    }
}
```

```java
import com.aspose.email.MailQueryBuilder;

public class FilterMessagesBasedOnSpecificDomain {
    public static void main(String[] args) {
        // Build a query for emails from 'SpecificHost.com'
        MailQueryBuilder builder = new MailQueryBuilder();
        builder.getFrom().contains("SpecificHost.com");
    }
}
```

```java
import com.aspose.email.MailQueryBuilder;

public class FilterMessagesBasedOnSpecificRecipient {
    public static void main(String[] args) {
        // Build a query for emails sent to 'recipient'
        MailQueryBuilder builder = new MailQueryBuilder();
        builder.getTo().contains("recipient");
    }
}
```

```java
import com.aspose.email.MailQueryBuilder;
import java.util.Date;
import java.util.concurrent.TimeUnit;

public class CombineQueriesWithAND {
    public static void main(String[] args) {
        // Build a combined query for specific domain, emails received before today,
        // and within the last 7 days
        MailQueryBuilder builder = new MailQueryBuilder();
        builder.getFrom().contains("SpecificHost.com");
        builder.getInternalDate().before(new Date());
        builder.getInternalDate().since(new Date(new Date().getTime() + TimeUnit.DAYS.toMillis(-7)));
    }
}
```

```java
import com.aspose.email.MailQueryBuilder;

public class CombineQueriesWithOR {
    public static void main(String[] args) {
        // Build a query for emails either from 'SpecificHost.com' or containing 'Newsletter'
        MailQueryBuilder builder = new MailQueryBuilder();
        builder.getFrom().contains("SpecificHost.com")
                .or(builder.getSubject().contains("Newsletter"));
    }
}
```