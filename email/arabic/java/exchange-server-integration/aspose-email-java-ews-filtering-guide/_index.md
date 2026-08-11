---
date: '2026-07-17'
description: 'كيفية تصفية رسائل البريد الإلكتروني باستخدام Aspose.Email Java و EWS:
  تعلّم تقنيات تصفية حسب التاريخ والمرسل والموضوع لتبسيط صندوق بريدك.'
keywords:
- Aspose.Email Java
- email filtering techniques
- Exchange Web Services (EWS)
lastmod: '2026-07-17'
og_description: كيفية تصفية رسائل البريد الإلكتروني باستخدام Aspose.Email Java و EWS.
  اكتشف تقنيات تصفية حسب التاريخ والمرسل والموضوع للحفاظ على تنظيم صندوق بريدك.
og_image_alt: Guide to filtering emails with Aspose.Email Java and Exchange Web Services
og_title: كيفية تصفية رسائل البريد الإلكتروني باستخدام Aspose.Email Java و EWS
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
title: كيفية تصفية رسائل البريد الإلكتروني باستخدام Aspose.Email Java و EWS دليل
url: /ar/java/exchange-server-integration/aspose-email-java-ews-filtering-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# إتقان تصفية البريد الإلكتروني باستخدام Aspose.Email Java & EWS: دليل شامل

## المقدمة

**كيف تصفِّي رسائل البريد الإلكتروني** بفعالية هي مهارة أساسية لأي شخص يعمل مع Microsoft Exchange أو أي صندوق بريد حديث. سواء كنت مطورًا يبني أتمتة على مستوى الشركة أو فردًا يرغب في الحفاظ على نظافة صندوق الوارد، فإن إتقان تقنيات التصفية الصحيحة يمكن أن يوفر ساعات من الجهد اليدوي. في هذا الدليل سنستعرض Aspose.Email للغة Java مع Exchange Web Services (EWS) لنظهر لك كيفية التصفية حسب التاريخ، المرسل، الموضوع، النطاق، المستلم، وحتى دمج معايير متعددة باستخدام عوامل منطقية.

### ما ستتعلمه
- تقنيات تصفية الرسائل باستخدام EWS في Java.  
- تصفية رسائل البريد بناءً على معايير مثل التاريخ، المرسل، الموضوع، إلخ.  
- تنفيذ دعم الصفحات للتعامل مع صناديق بريد كبيرة.  
- تطبيقات عملية لهذه الأساليب في سيناريوهات واقعية.  
- اعتبارات الأداء وأفضل الممارسات مع Aspose.Email Java.

بنهاية هذا البرنامج التعليمي ستكون قادرًا على كتابة كود Java نظيف وعالي الأداء يجلب الرسائل التي تحتاجها بالضبط من خادم Exchange.

## إجابات سريعة
- **ما هي المكتبة الأساسية؟** Aspose.Email للغة Java.  
- **أي بروتوكول يستخدم؟** Exchange Web Services (EWS).  
- **هل يمكن التصفية حسب نطاق تاريخ؟** نعم – استخدم معيار `DateTime` في `SearchFilter`.  
- **هل يدعم الصفحات؟** بالطبع، توفر API كائن `ItemView` مع الإزاحة/الحد.  
- **هل أحتاج إلى ترخيص للإنتاج؟** نعم، الترخيص التجاري يزيل حدود التقييم.

## ما هو Aspose.Email للغة Java؟
Aspose.Email للغة Java هو API شامل يتيح الوصول البرمجي إلى خوادم البريد، رسائل MIME، وExchange Web Services دون الحاجة إلى Outlook أو أي عميل آخر. يقوم بتجريد البروتوكولات الأساسية، مما يسمح لك بالتركيز على منطق الأعمال. تدعم المكتبة كل من خوادم Exchange المحلية وExchange Online، وتوفر API موحد لسيناريوهات النشر المتنوعة.

## لماذا نستخدم Aspose.Email مع EWS؟
يدعم Aspose.Email **أكثر من 50** بروتوكول بريد إلكتروني ويمكنه معالجة **مئات الآلاف من الرسائل** في الساعة مع الحفاظ على استهلاك الذاكرة تحت **100 ميغابايت** بفضل بنية البث. هذه الأداء الكمي يجعله مثاليًا لأتمتة صناديق البريد على نطاق المؤسسة. بالإضافة إلى ذلك، يوفر دعمًا مدمجًا لـ OAuth والمصادقة الحديثة، مما يبسط الاتصالات الآمنة ببيئات Office 365.

## المتطلبات المسبقة

- **المكتبات المطلوبة**: أدرج مكتبة Aspose.Email في مشروعك.  
- **إعداد البيئة**: يلزم وجود بيئة تطوير جاهزة لتطبيقات Java.  
- **المعرفة المسبقة**: الإلمام ببرمجة Java وبروتوكولات البريد سيكون مفيدًا.

## إعداد Aspose.Email للغة Java

### تثبيت Maven
أضف الاعتماد التالي إلى ملف `pom.xml` الخاص بك:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### الحصول على الترخيص
- **تجربة مجانية**: ابدأ بتجربة مجانية لاستكشاف قدرات Aspose.Email.  
- **ترخيص مؤقت**: احصل على ترخيص مؤقت لتقييم ممتد.  
- **شراء**: فكر في شراء ترخيص كامل إذا كان الأداة تلبي احتياجاتك.

قم بتهيئة Aspose.Email عن طريق استيراد الحزم اللازمة وإنشاء اتصال بخادم البريد باستخدام بيانات اعتماد EWS. هذه الخطوة أساسية للوصول إلى بيانات الصندوق برمجيًا.

## كيفية تصفية رسائل البريد باستخدام EWS في Java؟

`ExchangeService` هو الصف في Aspose.Email الذي يمثل اتصالًا بخادم Exchange.  
`SearchFilter` يحدد المعايير لتحديد العناصر على الخادم.  
`FindItems` ينفّذ البحث ويعيد العناصر المطابقة.  
`ItemView` يتحكم في الصفحات وعدد العناصر التي تُرجع لكل طلب.

حمّل كائن `ExchangeService` ببيانات اعتمادك، أنشئ `SearchFilter` يطابق معاييرك، واستدعِ `FindItems` مع `ItemView` لاسترجاع الرسائل المطلوبة فقط. هذا النمط من سطر واحد — اتصال → تصفية → جلب — يغطي معظم الحالات ويُوسّع إلى صناديق بريد كبيرة عندما تُفعّل الصفحات.

## دليل التنفيذ

### تصفية الرسائل باستخدام EWS

#### نظرة عامة
التصفية تتيح لك استرجاع رسائل البريد التي تفي بشروط معينة، مثل موضوع أو تاريخ محدد، مباشرة من صندوقك.
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
**شرح**: يُنشئ الكود اتصالًا بصندوق بريدك ويُكوّن استعلامًا لتصفية الرسائل التي تحتوي على كلمة “Newsletter” في سطر الموضوع في تاريخ محدد.

### كيفية تصفية الرسائل حسب تاريخ اليوم؟

`SearchFilter.IsEqualTo` يُنشئ مرشحًا يطابق العناصر التي تكون خاصية معينة مساوية لقيمة معينة.  
`DateTimeReceived` هي الخاصية التي تشير إلى وقت استلام البريد.

حمّل التاريخ الحالي، أنشئ `SearchFilter.IsEqualTo` على خاصية `DateTimeReceived`، ونفّذ الاستعلام. سيعيد هذا فقط الرسائل المستلمة في اليوم الذي تُشغّل فيه الكود، مما يجعل سكريبتات المعالجة اليومية بسيطة. يمكنك دمج هذا المرشح مع معايير إضافية مثل المرسل أو الموضوع لتضييق النتائج أكثر لهذا اليوم.

### كيفية تصفية الرسائل حسب نطاق تاريخ؟

`SearchFilter.IsGreaterThanOrEqualTo` يُنشئ مرشحًا يطابق العناصر التي تكون قيمتها أكبر من أو مساوية لقيمة محددة.  
`SearchFilter.IsLessThanOrEqualTo` يُنشئ مرشحًا يطابق العناصر التي تكون قيمتها أصغر من أو مساوية لقيمة محددة.  
`SearchFilter.And` يجمع عدة مرشحات بحيث يجب تحقيق جميع الشروط.

عرّف `DateTime` للبداية والنهاية، اجمعهما باستخدام `SearchFilter.IsGreaterThanOrEqualTo` و`SearchFilter.IsLessThanOrEqualTo`، ثم استخدم `SearchFilter.And` لربط الاثنين. مجموعة النتائج ستحتوي على كل رسالة تقع داخل النافذة المحددة. يتيح لك هذا النهج استرجاع جميع الاتصالات ضمن أي فترة مخصصة، مثل الربع الأخير أو جدول مشروع معين.

### كيفية تصفية الرسائل حسب مرسل معين؟

`SearchFilter.IsEqualTo` يُنشئ مرشحًا يطابق العناصر التي تكون خاصية معينة مساوية لقيمة معينة.

أنشئ `SearchFilter.IsEqualTo` على خاصية `From` باستخدام عنوان البريد الإلكتروني للمرسل. هذا يعزل جميع الرسائل من هذا الاتصال، وهو مثالي لصناديق الأولوية أو فحوصات الامتثال. يمكنك أيضًا استخدام `SearchFilter.ContainsSubstring` للمطابقات الجزئية عندما يكون العنوان غير معروف تمامًا أو عند التصفية حسب النطاق.

### كيفية تصفية الرسائل حسب نطاق معين؟

`SearchFilter.ContainsSubstring` يُنشئ مرشحًا يطابق العناصر التي تحتوي خاصية معينة على سلسلة فرعية محددة.

استخدم `SearchFilter.ContainsSubstring` على خاصية `From` مع سلسلة النطاق (مثال: “@example.com”). سيستخرج هذا كل بريد إلكتروني يأتي من ذلك النطاق، وهو مفيد لمراقبة الشركاء أو الموردين. دمج هذا المرشح مع معايير تاريخية يتيح لك تتبع الاتصالات الخاصة بالنطاق بمرور الوقت، مما يساعد في تدقيق الأمان.

### كيفية تصفية الرسائل حسب مستلم معين؟

`SearchFilter.IsEqualTo` يُنشئ مرشحًا يطابق العناصر التي تكون خاصية معينة مساوية لقيمة معينة.

طبّق `SearchFilter.IsEqualTo` على مجموعة `ToRecipients` للعنوان المستهدف. هذا مفيد عندما تحتاج إلى تدقيق الرسائل المرسلة إلى صندوق بريد معين أو قائمة توزيع. يمكنك أيضًا استخدام `SearchFilter.ContainsSubstring` للمطابقات الجزئية عند التعامل مع عدة مستلمين يشتركون في نطاق مشترك.

### كيفية دمج الاستعلامات باستخدام منطق AND؟

`SearchFilter.And` يجمع عدة مرشحات بحيث يجب تحقيق جميع الشروط.

سلسلة عدة كائنات `SearchFilter` باستخدام `SearchFilter.And`. على سبيل المثال، اجمع مرشح المرسل مع مرشح الموضوع لاسترجاع النشرات الإخبارية فقط من مرسل موثوق. يضمن عامل AND أن تُرجع العناصر التي تلبي جميع الشروط المحددة، مما يقلل مجموعة النتائج إلى أكثر الرسائل صلة.

### كيفية دمج الاستعلامات باستخدام منطق OR؟

`SearchFilter.Or` يدمج مرشحات بحيث يمكن لأي شرط أن يطابق.

استخدم `SearchFilter.Or` لدمج المرشحات عندما يجب أن يطابق أي شرط — مثالي لاسترجاع الرسائل التي تكون إما من مجموعة من المرسلين **أو** تحتوي على كلمات مفتاحية معينة. تطبيق منطق OR يمكن أن يوسع البحث لالتقاط جميع الاتصالات ذات الصلة عبر فئات متعددة دون فقدان معلومات حيوية.

## المشكلات الشائعة والنصائح

- **الصفحات ضرورية**: عند التعامل مع صناديق بريد تتجاوز 1,000 عنصر، استخدم دائمًا `ItemView` مع حجم صفحة لتجنب مهلات الوقت.  
- **معالجة المنطقة الزمنية**: تُعيد EWS التواريخ بتوقيت UTC؛ حوّلها إلى منطقتك المحلية قبل المقارنة.  
- **تجنب مسح الصندوق بالكامل**: دائمًا طبّق `SearchFilter` على جانب الخادم؛ التصفية على جانب العميل تهدر النطاق الترددي والذاكرة.  
- **نصيحة احترافية**: خزن كائن `ExchangeService` طوال عمر تطبيقك لتقليل عبء المصادقة.

## الأسئلة المتكررة

**س: هل يمكنني استخدام هذا النهج مع Office 365؟**  
ج: نعم، يعمل Aspose.Email مع Exchange Online في Office 365 عبر توجيه عنوان الخدمة إلى `https://outlook.office365.com/EWS/Exchange.asmx`.

**س: هل يدعم Aspose.Email مصادقة OAuth؟**  
ج: بالتأكيد — استخدم `OAuthCredentials` للمصادقة دون تخزين كلمات مرور المستخدمين.

**س: ما هو الحد الأقصى لحجم صندوق البريد الذي يمكن معالجته؟**  
ج: يمكن للـ API معالجة صناديق بريد **بعدة جيجابايت**؛ نظرًا لبث النتائج، يبقى استهلاك الذاكرة منخفضًا.

**س: كيف أصفي المرفقات حسب نوع الملف؟**  
ج: أضف `SearchFilter.ContainsSubstring` على خاصية `AttachmentNames`، ثم كرّر فقط العناصر المطابقة.

**س: هل هناك طريقة لترتيب النتائج؟**  
ج: نعم — مرّر `SortDirection` والخاصية التي تريد الترتيب بناءً عليها (مثال: `DateTimeReceived`) إلى استدعاء `FindItems`.

---

**آخر تحديث:** 2026-07-17  
**تم الاختبار مع:** Aspose.Email للغة Java 24.10  
**المؤلف:** Aspose

## دروس ذات صلة

- [How to Create an EWSClient Instance Using Aspose.Email for Java: Exchange Server Integration Guide](/email/java/exchange-server-integration/ewsclient-instance-aspose-email-java/)
- [How to Download Emails from Exchange Server Using Aspose.Email Java](/email/java/exchange-server-integration/aspose-email-java-exchange-server-download/)
- [Manage EWS Mailbox Information Using Aspose.Email for Java: A Comprehensive Guide](/email/java/exchange-server-integration/manage-ews-mailbox-info-aspose-email-java/)


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