---
date: '2026-06-13'
description: تعلم كيفية قراءة ملفات MSG وتحليل مرفقات MSG باستخدام Aspose.Email for
  Java، واستخراج إيصالات التسليم/القراءة ونتائج التصويت بكفاءة. يتضمن الإعداد، الكود،
  وأفضل الممارسات.
keywords:
- how to read msg
- parse msg attachments
- Aspose.Email for Java
schemas:
- author: Aspose
  dateModified: '2026-06-13'
  description: Learn how to read MSG files and parse MSG attachments using Aspose.Email
    for Java, extracting delivery/read receipts and vote results efficiently. Includes
    setup, code, and best practices.
  headline: How to Read MSG Files with Aspose.Email for Java
  type: TechArticle
- description: Learn how to read MSG files and parse MSG attachments using Aspose.Email
    for Java, extracting delivery/read receipts and vote results efficiently. Includes
    setup, code, and best practices.
  name: How to Read MSG Files with Aspose.Email for Java
  steps:
  - name: Load the MSG File
    text: MapiMessage is the Aspose.Email class that represents an Outlook MSG message.
  - name: Iterate Over Recipients
    text: MapiRecipient represents a single recipient (To, CC, or BCC) in the MSG
      file.
  - name: Retrieve and Print Delivery Time
    text: DeliveryTime is a property of MapiRecipient that holds the timestamp when
      the message was delivered to the recipient’s server.
  - name: Retrieve and Print Read Time
    text: ReadTime is a property of MapiRecipient indicating when the recipient opened
      the message, if that information is available.
  - name: Load the MSG File
    text: MapiMessage is used again to access the voting information embedded in the
      MSG file.
  - name: Iterate Over Recipients
    text: MapiRecipient provides access to each participant’s voting choice and response
      time.
  - name: Retrieve and Print Response
    text: The `VotingResponse` property contains the actual vote (e.g., “Accept”,
      “Decline”, or custom options).
  - name: Retrieve and Print Response Time
    text: '`VotingResponseTime` records when the recipient submitted their vote, allowing
      chronological analysis of poll activity.'
  type: HowTo
- questions:
  - answer: Split the file into smaller segments or use the streaming API to read
      portions without full in‑memory loading.
    question: How do I handle MSG files larger than 500 MB?
  - answer: Yes, map the receipt and vote fields to your DB schema and use JDBC or
      an ORM to persist them.
    question: Can I store the extracted data directly into a database?
  - answer: Absolutely; Aspose.Email for Java is platform‑agnostic and runs on any
      OS with a supported JDK.
    question: Does the library work on Linux environments?
  - answer: Use `MailMessage.getAttachments()` after loading the MSG; the method returns
      a collection of all embedded files.
    question: Is there a way to extract attachments while reading receipts?
  - answer: Reach out via the official Aspose Email Forum for community help or open
      a support ticket with a valid license.
    question: What support options are available if I encounter bugs?
  type: FAQPage
title: كيفية قراءة ملفات MSG باستخدام Aspose.Email for Java
url: /ar/java/email-parsing-analysis/aspose-email-java-msg-receipts-vote-results/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية قراءة ملفات MSG باستخدام Aspose.Email for Java

## مقدمة

تتيح لك قراءة ملفات MSG برمجياً استخراج بيانات تتبع قيمة—إيصالات التسليم، تأكيدات القراءة، ونتائج التصويت—من رسائل Outlook. في هذا الدليل سنوضح **كيفية قراءة msg** باستخدام Aspose.Email for Java، نستعرض الإعداد المطلوب، ونظهر كيفية استخراج معلومات الإيصال والتصويت بكفاءة.

## إجابات سريعة
- **ما المكتبة التي تتعامل مع تحليل MSG؟** Aspose.Email for Java.  
- **هل يمكنني استخراج إيصالات القراءة؟** نعم، تُعيد API طوابع زمنية للتسليم والقراءة.  
- **هل بيانات التصويت متاحة؟** بالتأكيد؛ يمكنك استرجاع استجابة التصويت لكل مستلم.  
- **هل أحتاج إلى ترخيص؟** النسخة التجريبية تعمل للاختبار؛ الترخيص المدفوع يزيل حدود التقييم.  
- **ما نسخة Java المطلوبة؟** يُنصح بـ Java 16 أو أحدث.

## ما هو Aspose.Email for Java؟

Aspose.Email for Java هي مكتبة Java مستقلة تمكّن من إنشاء ومعالجة وتحويل صيغ البريد الإلكتروني دون الحاجة إلى Microsoft Outlook. توفر نموذج كائن غني لـ MSG وEML وPST والعديد من الصيغ الأخرى، مما يسمح للمطورين بالعمل مع بيانات البريد مباشرةً من كود Java. (45 words)

## لماذا تستخدم Aspose.Email for Java لقراءة ملفات MSG؟

يدعم Aspose.Email for Java **30+ email formats** ويمكنه معالجة ملفات MSG حتى **500 MB** دون تحميل الملف بالكامل في الذاكرة. يقلل محرك التحليل عالي الأداء من استهلاك المعالج والذاكرة، مما يجعله مثالياً لمعالجة أرشفة البريد على نطاق واسع وسيناريوهات التحليل في الوقت الفعلي. (48 words)

## المتطلبات المسبقة

- **المكتبات والاعتمادات:** Aspose.Email for Java الإصدار 25.4 أو أحدث وبيئة تشغيل JDK 16+.  
- **IDE:** IntelliJ IDEA أو Eclipse أو أي IDE متوافق مع Java يدعم Maven.  
- **المهارات الأساسية:** الإلمام بصياغة Java ومفاهيم البرمجة الكائنية.

## الحصول على الترخيص

لاستخدام Aspose.Email for Java، تحتاج إلى ترخيص:

- **نسخة تجريبية مجانية:** ابدأ بالنسخة التجريبية المتاحة على [Aspose's website](https://releases.aspose.com/email/java/).  
- **ترخيص مؤقت:** اطلب ترخيصًا مؤقتًا من [purchase page](https://purchase.aspose.com/temporary-license/).  
- **شراء:** إذا كنت راضيًا عن التقييم، اشترِ ترخيصًا للوصول الكامل إلى جميع الميزات عبر صفحة [Buy Aspose Products](https://purchase.aspose.com/buy).  

## كيف تستخرج معلومات إيصال القراءة والتسليم من ملف MSG؟

حمّل ملف MSG، وتكرّر عبر المستلمين، واقرأ خصائص `DeliveryTime` و `ReadTime`. تُعيد هذه الطريقة طوابع زمنية دقيقة عندما يقوم خادم بريد كل مستلم بتسليم الرسالة ومتى فتح المستلم الرسالة، مما يزودك ببيانات تتبع دقيقة للتحليل. (53 words)

### الخطوة 1: تحميل ملف MSG
MapiMessage هي الفئة في Aspose.Email التي تمثل رسالة Outlook MSG.  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```  

### الخطوة 2: التكرار عبر المستلمين
MapiRecipient تمثل مستلمًا واحدًا (To أو CC أو BCC) في ملف MSG.  
```java
import com.aspose.email.MapiMessage;
import com.aspose.email.MapiRecipient;
import com.aspose.email.MapiPropertyTag;

public class RetrieveReceipts {
    public static void main(String[] args) {
        String dataDir = "YOUR_DOCUMENT_DIRECTORY/outlook/";
        MapiMessage msg = MapiMessage.fromFile(dataDir + "message.msg");
```  

### الخطوة 3: استرجاع وطباعة وقت التسليم
DeliveryTime هي خاصية في MapiRecipient تحتفظ بالطابع الزمني عندما تم تسليم الرسالة إلى خادم المستلم.  
```java
        for (MapiRecipient recipient : msg.getRecipients()) {
            System.out.println("Recipient: " + recipient.getDisplayName());
```  

### الخطوة 4: استرجاع وطباعة وقت القراءة
ReadTime هي خاصية في MapiRecipient تشير إلى متى فتح المستلم الرسالة، إذا كانت هذه المعلومة متاحة.  
```java
            System.out.println("Delivery time: " + 
                recipient.getProperties().get_Item(MapiPropertyTag.PR_RECIPIENT_TRACKSTATUS_TIME_DELIVERY).getDateTime());
```  

## كيف تقرأ نتائج التصويت من ملف MSG؟

بعد تحميل الرسالة، تُظهر API استجابة التصويت لكل مستلم والوقت الذي رد فيه، مما يتيح لك تجميع نتائج الاستطلاع برمجياً. يمكن استخدام هذه البيانات لإنشاء تقارير ملخصة أو تغذية مباشرةً إلى لوحات معلومات ذكاء الأعمال لاتخاذ قرارات سريعة. (53 words)

### الخطوة 1: تحميل ملف MSG
يُستخدم MapiMessage مرة أخرى للوصول إلى معلومات التصويت المدمجة في ملف MSG.  
```java
            System.out.println("Read time: " + 
                recipient.getProperties().get_Item(MapiPropertyTag.PR_RECIPIENT_TRACKSTATUS_TIME_READ).getDateTime());
        }
    }
}
```  

### الخطوة 2: التكرار عبر المستلمين
يوفر MapiRecipient الوصول إلى خيار التصويت لكل مشارك ووقت استجابته.  
```java
import com.aspose.email.MapiMessage;
import com.aspose.email.MapiRecipient;
import com.aspose.email.MapiPropertyTag;

public class ReadVoteResults {
    public static void main(String[] args) {
        String dataDir = "YOUR_DOCUMENT_DIRECTORY/outlook/";
        MapiMessage msg = MapiMessage.fromFile(dataDir + "message.msg");
```  

### الخطوة 3: استرجاع وطباعة الاستجابة
خاصية `VotingResponse` تحتوي على التصويت الفعلي (مثل “Accept”، “Decline”، أو خيارات مخصصة).  
```java
        for (MapiRecipient recipient : msg.getRecipients()) {
            System.out.println("Recipient: " + recipient.getDisplayName());
```  

### الخطوة 4: استرجاع وطباعة وقت الاستجابة
`VotingResponseTime` تسجل متى قدم المستلم تصويته، مما يسمح بتحليل زمني لنشاط الاستطلاع.  
```java
            System.out.println("Response: " + 
                recipient.getProperties().get_Item(MapiPropertyTag.PR_RECIPIENT_AUTORESPONSE_PROP_RESPONSE).getString());
```  

## التطبيقات العملية

1. **تتبع حملات البريد الإلكتروني:** قياس معدلات الفتح ونجاح التسليم من خلال تحليل طوابع إيصالات الاستلام.  
2. **تحليل الاستطلاعات:** تجميع نتائج التصويت من استطلاعات Outlook لاتخاذ قرارات سريعة.  
3. **إدارة ملاحظات العملاء:** سحب بيانات الاستجابة إلى أنظمة CRM أو منصات التحليل للحصول على رؤى أعمق.

دمج هذه الاستخراجات مع قواعد البيانات أو أدوات BI يعزز قيمة بيانات البريد الخام.

## اعتبارات الأداء

- معالجة ملفات MSG الكبيرة في **chunks** للحفاظ على انخفاض استهلاك الذاكرة.  
- استخدام **streaming APIs** عند التعامل مع آلاف الرسائل.  
- تخزين بيانات المستلمين في مجموعات خفيفة الوزن مثل `ArrayList` أو `HashMap` لعمليات بحث سريعة.

## المشكلات الشائعة والحلول

- **طوابع زمنية فارغة:** عادةً ما يعني غياب `ReadTime` أن المستلم لم يفتح الرسالة بعد.  
- **مرفقات كبيرة:** إذا كان MSG يحتوي على مرفقات ضخمة، فعّل `LoadOptions.setPreserveEmbeddedResources(false)` لتخطي تحميلها إلى الذاكرة.  
- **مشكلات الترميز:** تأكد من ضبط صفحة الترميز الصحيحة عبر `MailMessage.setCharset(Charset.forName("UTF-8"))` عند قراءة محتوى غير ASCII.

## الأسئلة المتكررة

**س: كيف أتعامل مع ملفات MSG أكبر من 500 MB؟**  
**ج:** قسّم الملف إلى أقسام أصغر أو استخدم streaming API لقراءة أجزاء دون تحميل كامل في الذاكرة.

**س: هل يمكنني تخزين البيانات المستخرجة مباشرةً في قاعدة بيانات؟**  
**ج:** نعم، قم بربط حقول الإيصال والتصويت بمخطط قاعدة البيانات الخاصة بك واستخدم JDBC أو ORM لحفظها.

**س: هل تعمل المكتبة على بيئات Linux؟**  
**ج:** بالتأكيد؛ Aspose.Email for Java مستقل عن المنصة ويعمل على أي نظام تشغيل يدعم JDK.

**س: هل هناك طريقة لاستخراج المرفقات أثناء قراءة الإيصالات؟**  
**ج:** استخدم `MailMessage.getAttachments()` بعد تحميل MSG؛ تُعيد الطريقة مجموعة من جميع الملفات المدمجة.

**س: ما خيارات الدعم المتاحة إذا واجهت أخطاء؟**  
**ج:** تواصل عبر منتدى Aspose Email الرسمي للحصول على مساعدة المجتمع أو افتح تذكرة دعم بترخيص صالح.

## الموارد
- **الوثائق:** [Aspose Email Documentation](https://reference.aspose.com/email/java/)  
- **الوثائق (مكررة):** [Aspose Email Documentation](https://reference.aspose.com/email/java/)  
- **تنزيل SDK:** [Aspose Email Downloads](https://releases.aspose.com/email/java/)  
- **قسم التنزيل:** [Download Section](https://releases.aspose.com/email/java/)  
- **شراء الترخيص:** [Buy Aspose Products](https://purchase.aspose.com/buy)  
- **نسخة تجريبية مجانية:** ابدأ بـ [Free Trial Version](https://releases.aspose.com/email/java/)  
- **ترخيص مؤقت:** [Request Temporary License](https://purchase.aspose.com/temporary-license/)  
- **منتدى الدعم:** [Aspose Email Forum](https://forum.aspose.com/c/email/10)  
- **منتدى الدعم (مكرر):** [Aspose Email Forum](https://forum.aspose.com/c/email/10)

---

**آخر تحديث:** 2026-06-13  
**تم الاختبار مع:** Aspose.Email for Java 25.4  
**المؤلف:** Aspose

```java
            System.out.println("Response time: " + 
                recipient.getProperties().get_Item(MapiPropertyTag.PR_RECIPIENT_TRACKSTATUS_TIME).getDateTime());
        }
    }
}
```

## دروس ذات صلة

- [كيفية تحميل وتحليل ملفات Outlook MSG باستخدام Aspose.Email for Java: دليل شامل](/email/java/mapi-operations/outlook-msg-aspose-email-java-guide/)
- [تحويل MSG إلى EML وإدارة المرفقات باستخدام Aspose.Email for Java](/email/java/attachments-handling/aspose-email-java-master-msg-attachments-parsing/)
- [استخراج المرفقات المضمنة Java – ملفات MSG باستخدام Aspose.Email](/email/java/attachments-handling/extract-inline-attachments-msg-files-java-aspose-email/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}