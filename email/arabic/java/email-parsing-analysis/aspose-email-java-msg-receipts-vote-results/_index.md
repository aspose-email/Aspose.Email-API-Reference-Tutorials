---
"date": "2025-05-29"
"description": "Learn how to use Aspose.Email for Java to efficiently extract delivery and read receipts, as well as vote results from MSG files. This guide covers setup, code implementation, and best practices."
"title": "How to Extract MSG Receipts & Vote Results Using Aspose.Email for Java&#58; A Comprehensive Guide"
"url": "/ar/java/email-parsing-analysis/aspose-email-java-msg-receipts-vote-results/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# How to Extract MSG Receipts & Vote Results Using Aspose.Email for Java: A Comprehensive Guide

## مقدمة

Managing email tracking effectively is essential for understanding when your messages are read or gauging the results of an office poll. This guide demonstrates how to use Aspose.Email for Java to retrieve read and delivery receipts, as well as vote result information from Microsoft Outlook MSG files. By leveraging these features, you can gain valuable insights into email interactions.

**ما سوف تتعلمه:**
- Setting up Aspose.Email for Java
- Extracting recipient tracking details like delivery and read times
- Reading vote results data from email recipients
- Best practices for handling email data in Java

## المتطلبات الأساسية

To follow this tutorial, ensure you have the following:
- **المكتبات والتبعيات:** Aspose.Email for Java version 25.4 and a compatible JDK (Java Development Kit), such as JRE 16 or above.
- **إعداد البيئة:** A suitable Integrated Development Environment (IDE) like IntelliJ IDEA or Eclipse configured with Maven support.
- **المتطلبات المعرفية:** Basic understanding of Java programming, object-oriented principles, and familiarity with handling email data.

## Setting Up Aspose.Email for Java

To start using Aspose.Email in your project, integrate it via Maven:

**Maven Dependency:**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### الحصول على الترخيص

To use Aspose.Email for Java, you need to obtain a license:
- **نسخة تجريبية مجانية:** Start with the free trial version available on [موقع Aspose](https://releases.aspose.com/email/java/).
- **رخصة مؤقتة:** For extended testing, request a temporary license from the [صفحة الشراء](https://purchase.aspose.com/temporary-license/).
- **شراء:** If you’re satisfied with the evaluation, purchase a license for full access to all features.

## دليل التنفيذ

### Extracting Read and Delivery Receipt Information

This feature allows you to extract when emails are delivered and read by recipients from an MSG file.

#### التنفيذ خطوة بخطوة

**الخطوة 1:** تحميل ملف MSG
```java
import com.aspose.email.MapiMessage;
import com.aspose.email.MapiRecipient;
import com.aspose.email.MapiPropertyTag;

public class RetrieveReceipts {
    public static void main(String[] args) {
        String dataDir = "YOUR_DOCUMENT_DIRECTORY/outlook/";
        MapiMessage msg = MapiMessage.fromFile(dataDir + "message.msg");
```
**الخطوة 2:** Iterate Over Recipients
```java
        for (MapiRecipient recipient : msg.getRecipients()) {
            System.out.println("Recipient: " + recipient.getDisplayName());
```
**Step 3:** Retrieve and Print Delivery Time
```java
            System.out.println("Delivery time: " + 
                recipient.getProperties().get_Item(MapiPropertyTag.PR_RECIPIENT_TRACKSTATUS_TIME_DELIVERY).getDateTime());
```
**Step 4:** Retrieve and Print Read Time
```java
            System.out.println("Read time: " + 
                recipient.getProperties().get_Item(MapiPropertyTag.PR_RECIPIENT_TRACKSTATUS_TIME_READ).getDateTime());
        }
    }
}
```

### Reading Vote Results Information

This feature helps extract how recipients have voted and when they responded, crucial for decision-making processes.

#### التنفيذ خطوة بخطوة

**الخطوة 1:** تحميل ملف MSG
```java
import com.aspose.email.MapiMessage;
import com.aspose.email.MapiRecipient;
import com.aspose.email.MapiPropertyTag;

public class ReadVoteResults {
    public static void main(String[] args) {
        String dataDir = "YOUR_DOCUMENT_DIRECTORY/outlook/";
        MapiMessage msg = MapiMessage.fromFile(dataDir + "message.msg");
```
**الخطوة 2:** Iterate Over Recipients
```java
        for (MapiRecipient recipient : msg.getRecipients()) {
            System.out.println("Recipient: " + recipient.getDisplayName());
```
**Step 3:** Retrieve and Print Response
```java
            System.out.println("Response: " + 
                recipient.getProperties().get_Item(MapiPropertyTag.PR_RECIPIENT_AUTORESPONSE_PROP_RESPONSE).getString());
```
**Step 4:** Retrieve and Print Response Time
```java
            System.out.println("Response time: " + 
                recipient.getProperties().get_Item(MapiPropertyTag.PR_RECIPIENT_TRACKSTATUS_TIME).getDateTime());
        }
    }
}
```

## التطبيقات العملية

1. **Email Campaign Tracking:** Use receipt data to measure open rates and delivery success.
2. **Survey Analysis:** Quickly analyze vote results from email-based surveys.
3. **Customer Feedback Management:** Retrieve and process responses efficiently to improve services.

Integrating with CRM systems or analytics tools can provide deeper insights into communication efficacy.

## اعتبارات الأداء

- Optimize performance by handling large MSG files in chunks if necessary.
- Monitor memory usage, especially when processing numerous emails, to prevent leaks.
- Utilize efficient data structures for storing and accessing recipient properties.

## خاتمة

In this tutorial, you've learned how to leverage Aspose.Email for Java to extract crucial information from MSG files. These features can significantly enhance your communication workflows by tracking email delivery and read times or analyzing vote results. Continue exploring Aspose.Email’s capabilities to further optimize your email management processes.

لمزيد من الاستكشاف:
- Dive deeper into the [توثيق البريد الإلكتروني لـ Aspose](https://reference.aspose.com/email/java/).
- Try out more examples in the [Download Section](https://releases.aspose.com/email/java/).

## التعليمات

1. **How do I handle large MSG files?**
   - Process them in smaller batches to avoid memory issues.
2. **What if a recipient's response time is null?**
   - It might indicate they haven't responded yet or the property isn’t set.
3. **Can Aspose.Email be used with databases?**
   - Yes, integrate it with SQL or NoSQL databases for storing and querying email data.
4. **Is there support for other file formats?**
   - Aspose.Email supports various formats like EML, PST, etc., beyond MSG files.
5. **Where can I get help if I run into issues?**
   - قم بزيارة [منتدى البريد الإلكتروني Aspose](https://forum.aspose.com/c/email/10) for community support.

## موارد
- **التوثيق:** [توثيق البريد الإلكتروني لـ Aspose](https://reference.aspose.com/email/java/)
- **Download SDK:** [تنزيلات البريد الإلكتروني من Aspose](https://releases.aspose.com/email/java/)
- **رخصة الشراء:** [شراء منتجات Aspose](https://purchase.aspose.com/buy)
- **نسخة تجريبية مجانية:** ابدأ بـ [نسخة تجريبية مجانية](https://releases.aspose.com/email/java/)
- **رخصة مؤقتة:** [طلب ترخيص مؤقت](https://purchase.aspose.com/temporary-license/)
- **منتدى الدعم:** Engage in discussions at the [منتدى البريد الإلكتروني Aspose](https://forum.aspose.com/c/email/10)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}