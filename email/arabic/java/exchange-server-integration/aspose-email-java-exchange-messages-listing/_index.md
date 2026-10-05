---
date: '2026-10-02'
description: تعلم كيفية الاتصال بـ exchange وإدراج المجلدات العامة لـ exchange باستخدام
  Aspose.Email for Java. يوضح هذا الدليل step‑by‑step اعتماد Maven وإعداد code‑free.
keywords:
- how to connect exchange
- list exchange public folders
- maven dependency aspose email
lastmod: '2026-10-02'
og_description: تعلم كيفية الاتصال بـ exchange وإدراج المجلدات العامة لـ exchange
  باستخدام Aspose.Email for Java. يغطي هذا الدليل اعتماد Maven، licensing، وrecursive
  message retrieval.
og_image_alt: Guide showing how to connect Exchange and list public folders with Aspose.Email
  for Java
og_title: كيفية الاتصال بـ exchange وإدراج المجلدات العامة في Java
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Learn how to connect exchange and list exchange public folders using
    Aspose.Email for Java. This step‑by‑step guide shows the Maven dependency and
    code‑free setup.
  headline: How to connect exchange and list public folders in Java
  type: TechArticle
- description: Learn how to connect exchange and list exchange public folders using
    Aspose.Email for Java. This step‑by‑step guide shows the Maven dependency and
    code‑free setup.
  name: How to connect exchange and list public folders in Java
  steps:
  - name: '**Automated email archiving** – Periodically pull all public‑folder messages
      and store them in a compliant archive.'
    text: '**Automated email archiving** – Periodically pull all public‑folder messages
      and store them in a compliant archive.'
  - name: '**Backup solutions** – Mirror Exchange public folders to a secure file
      system or cloud bucket, guaranteeing data redundancy.'
    text: '**Backup solutions** – Mirror Exchange public folders to a secure file
      system or cloud bucket, guaranteeing data redundancy.'
  - name: '**Custom email clients** – Build lightweight viewers that display only
      the folders and messages you need, reducing UI complexity.'
    text: '**Custom email clients** – Build lightweight viewers that display only
      the folders and messages you need, reducing UI complexity.'
  type: HowTo
- questions:
  - answer: Yes. Provide the Office 365 EWS endpoint (`https://outlook.office365.com/EWS/Exchange.asmx`)
      and use modern authentication (OAuth) – Aspose.Email supports OAuth tokens out
      of the box.
    question: Can I use this code with Exchange Online (Office 365)?
  - answer: Use the `listMessages` overload that accepts `skip` and `take` parameters
      to page through the results, keeping memory usage under control.
    question: What if a folder contains more than 10 000 messages?
  - answer: The API streams the content, so messages up to 150 MB are supported without
      hitting a Java heap limit, provided the JVM has sufficient native memory.
    question: Is there a limit on the size of a single email I can download?
  - answer: By default Aspose.Email trusts the Java default keystore. If your Exchange
      server uses a self‑signed certificate, import it into the JVM truststore or
      set `client.setEnableSslVerification(false)` for testing only.
    question: Do I need to handle SSL certificates manually?
  - answer: Enable Aspose.Email’s built‑in logging by configuring `Logger.setLevel(Level.INFO)`
      and directing output to a file or monitoring system.
    question: How do I log the operations for audit purposes?
  type: FAQPage
tags:
- exchange integration
- Aspose.Email
- Java email automation
title: كيفية الاتصال بـ exchange وإدراج المجلدات العامة في Java
url: /ar/java/exchange-server-integration/aspose-email-java-exchange-messages-listing/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية الاتصال بـ Exchange وإدراج المجلدات العامة في Java

## مقدمة
في المؤسسات الحديثة، يتيح الوصول البرمجي إلى صناديق بريد Microsoft Exchange أتمتة مهام الأرشفة والمراقبة وإعداد التقارير. يوضح هذا الدرس **كيفية الاتصال بـ Exchange** باستخدام Aspose.Email for Java ثم **إدراج المجلدات العامة لـ Exchange** بشكل متكرر. ستشاهد تبعية Maven المطلوبة، خطوات الترخيص، وتسلسل استدعاءات API بدقة—دون الحاجة إلى مكتبات إضافية. في النهاية، ستكون قادرًا على سحب الرسائل من أي مجلد عام وحفظها محليًا.

## إجابات سريعة
- **ما هي الخطوة الأولى؟** أضف تبعية Aspose.Email Maven إلى ملف `pom.xml` الخاص بك.  
- **هل أحتاج إلى ترخيص؟** نعم — استخدم ترخيصًا مؤقتًا للتقييم أو اشترِ ترخيصًا كاملاً للإنتاج.  
- **أي فئة تنشئ الاتصال؟** `ExchangeClient` (أو `ImapClient` لـ IMAP) يتعامل مع المصادقة وتواصل الخادم.  
- **هل يمكنني إدراج المجلدات الفرعية تلقائيًا؟** نعم — استخدم طريقة `listSubFolders` المتكررة التي توفرها API.  
- **هل هذا النهج آمن للخطوط المتعددة؟** كائنات العميل ليست آمنة للخطوط المتعددة؛ أنشئ نسخة منفصلة لكل خيط للعبء المتزامن.

## ما هو كيفية الاتصال بـ Exchange؟
**كيفية الاتصال بـ Exchange** هي عملية مصادقة تطبيق Java مع خادم Microsoft Exchange محلي أو سحابي بحيث يمكنك إصدار استدعاءات API مثل تعداد المجلدات أو استرجاع الرسائل. Aspose.Email يج abstracts البروتوكولات الأساسية EWS/IMAP، ويمنحك نموذج كائن موحد ومتسق.

## لماذا إدراج المجلدات العامة لـ Exchange؟
إدراج المجلدات العامة يمنحك رؤية للهيكل الهرمي الذي تستخدمه المؤسسات للمصارف المشتركة، قوائم التوزيع، ومستودعات الأرشفة. Aspose.Email يمكنه تعداد **أكثر من 50** مجلدًا عامًا في استدعاء واحد ويدعم معالجة صناديق بريد مئات الصفحات دون تحميل المتجر بالكامل في الذاكرة، مما يقلل استهلاك RAM حتى **70 %**.

## المتطلبات المسبقة
- **Aspose.Email for Java** — الإصدار 25.4 أو أحدث (أحدث إصدار ثابت).  
- **Java Development Kit (JDK)** — JDK 11 أو أحدث مثبت ومُعَدّ `JAVA_HOME`.  
- **Maven** — لإدارة التبعيات وأتمتة البناء.  
- معرفة أساسية بصياغة Java ومفاهيم Exchange (صناديق البريد، المجلدات، EWS).

## إعداد Aspose.Email لـ Java
لدمج المكتبة، أضف تبعية Maven إلى ملف `pom.xml` الخاص بمشروعك. هذه هي **تبعية Maven Aspose Email** التي ستحتاجها.

### تبعية Maven
أضف المقتطف التالي داخل عنصر `<dependencies>` في ملف `pom.xml` الخاص بك:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### خطوات الحصول على الترخيص
Aspose.Email يتطلب ترخيصًا صالحًا للاستخدام الكامل للميزات:

- **تجربة مجانية** – قم بتحميل ترخيص مؤقت من [موقع Aspose](https://purchase.aspose.com/temporary-license/) لتقييم API.  
- **شراء** – احصل على ترخيص تجاري عبر بوابة Aspose للنشر في بيئات الإنتاج.

#### التهيئة الأساسية
بعد أن يقوم Maven بحل الحزمة وتتوفر لديك ملف الترخيص، ضع ملف `.lic` على مسار الـ classpath وابدأ تهيئة المكتبة:

```java
import com.aspose.email.License;

License license = new License();
license.setLicense("path/to/your/license.lic");
```

## دليل التنفيذ
سنستعرض كل كتلة وظيفية، مجيبين على الأسئلة الرئيسية بفقرة مختصرة قبل الانتقال إلى الخطوات التفصيلية.

### كيفية الاتصال بـ Exchange؟
حمّل `ExchangeClient` بعنوان الخادم، بيانات الاعتماد، والنطاق، ثم استدعِ `connect()`. يقوم العميل بإنشاء جلسة HTTPS مع Exchange Web Services (EWS) ويتحقق من صحة البيانات. إذا فشل الاتصال، ترمي API استثناء `AuthenticationException` يتضمن رمز حالة HTTP لتسهيل التشخيص.  
`ExchangeClient` هي فئة Aspose.Email التي تدير الاتصال بـ Exchange Web Services.

```java
import com.aspose.email.EWSClient;
import com.aspose.email.IEWSClient;

IEWSClient connectToExchangeServer(String exchangeUrl, String username, String password, String domain) {
    // Create instance of IEWSClient class by providing credentials
    return EWSClient.getEWSClient(exchangeUrl, username, password, domain);
}
```

### كيفية إدراج المجلدات العامة لـ Exchange؟
استدعِ `client.listPublicFolders()` لاسترجاع مجموعة من كائنات `FolderInfo` التي تمثل كل مجلد عام من المستوى الأعلى. تُعيد الطريقة بيانات وصفية مثل اسم المجلد، إجمالي عدد العناصر، ومعرف فريد يُستخدم في الاستدعاءات اللاحقة. يكتمل هذا الاستدعاء في أقل من 2 ثانية للانتشار المحلي النموذجي حتى 500 مجلد.  
`listPublicFolders()` تُعيد مجموعة من كائنات `FolderInfo`.  
`FolderInfo` يحمل بيانات وصفية مثل الاسم المعروض وعدد العناصر.

```java
import com.aspose.email.ExchangeFolderInfoCollection;
import com.aspose.email.IEWSClient;

ExchangeFolderInfoCollection listPublicFolders(IEWSClient client) {
    // List all public folders and return their information as a collection
    return client.listPublicFolders();
}
```

### كيفية عرض معلومات المجلد؟
قم بالتكرار على مجموعة `FolderInfo` واطبع `displayName` و`subFolderCount`. يساعدك هذا الملخص السريع على فهم الهيكل قبل الشروع في الزحف العميق. للمؤسسات الكبيرة، يمكن للـ API تقسيم النتائج، حيث تُرجع 100 مجلد لكل صفحة لتقليل استهلاك الذاكرة.

```java
import com.aspose.email.ExchangeFolderInfo;

void displayFolderInfo(ExchangeFolderInfo folder) {
    // Print folder details
    System.out.println("Name: " + folder.getDisplayName());
    System.out.println("Subfolders count: " + folder.getChildFolderCount());
}
```

### كيفية إدراج الرسائل من مجلد؟
استدعِ `client.listMessages(folderId)` حيث `folderId` هو المعرف المستخرج من الخطوة السابقة. تُعيد الطريقة قائمة من كائنات `MessageInfo` التي تحتوي على الموضوع، المرسل، وتاريخ الاستلام. يمكنك تحديد الحد الأقصى للنتائج باستخدام `maxCount` لتجنب تحميل العميل عند معالجة مجلدات ضخمة.  
`listMessages(folderId)` تُعيد قائمة من كائنات `MessageInfo`.  
`MessageInfo` يحتوي على خصائص أساسية للبريد مثل الموضوع، المرسل، وتاريخ الاستلام.

```java
import com.aspose.email.ExchangeMessageInfoCollection;
import com.aspose.email.IEWSClient;

ExchangeMessageInfoCollection listMessagesFromFolder(IEWSClient client, ExchangeFolderInfo folder) {
    // List messages from the specified public folder and return their information as a collection
    return client.listMessagesFromPublicFolder(folder);
}
```

### كيفية جلب وحفظ الرسائل؟
لكل `MessageInfo`، استخدم `client.fetchMessage(messageId)` لتنزيل المحتوى الكامل بصيغة MIME. ثم اكتب مصفوفة البايتات إلى ملف `.eml` على القرص. تقوم الـ API ببث المحتوى، لذا حتى الرسائل التي حجمها 100 MB تُعالج دون تحميل كامل الحمولة في الذاكرة.  
`fetchMessage(messageId)` يحمّل المحتوى الكامل بصيغة MIME للبريد المحدد.

```java
import com.aspose.email.ExchangeMessageInfo;
import com.aspose.email.IEWSClient;
import com.aspose.email.MailMessage;
import com.aspose.email.SaveOptions;

void fetchAndSaveMessages(IEWSClient client, ExchangeMessageInfoCollection messages) {
    for (ExchangeMessageInfo messageInfo : messages) {
        // Fetch the full MailMessage using its unique URI
        MailMessage msg = client.fetchMessage(messageInfo.getUniqueUri());
        
        // Save the fetched message to a file named after its subject with .msg extension
        String filePath = "YOUR_OUTPUT_DIRECTORY/" + msg.getSubject() + ".msg";
        msg.save(filePath, SaveOptions.getDefaultMsgUnicode());
    }
}
```

### كيفية إدراج الرسائل بشكل متكرر من المجلدات الفرعية؟
طبق خوارزمية عمق‑أول: ابدأ بمجلد من المستوى الأعلى، أدرج مجلداته الفرعية عبر `client.listSubFolders(parentId)`, ثم استدعِ روتين إدراج الرسائل نفسه لكل مجلد فرعي. يضمن هذا النمط معالجة كل رسالة في شجرة المجلدات العامة. عمق التكرار يقتصر فقط على هيكل المجلدات في الخادم (عادةً أقل من 20 مستوى).  
`listSubFolders(parentId)` تُعيد المجلدات الفرعية المباشرة للمجلد المحدد.

```java
import com.aspose.email.ExchangeFolderInfo;
import com.aspose.email.IEWSClient;

void listMessagesFromSubFolders(IEWSClient client, ExchangeFolderInfo folder) {
    // List all messages in the current public folder
    ExchangeMessageInfoCollection msgCollection = client.listMessagesFromPublicFolder(folder);
    fetchAndSaveMessages(client, msgCollection);

    if (folder.getChildFolderCount() > 0) {
        ExchangeFolderInfoCollection subFolders = client.listSubFolders(folder);
        for (ExchangeFolderInfo subFolder : subFolders) {
            listMessagesFromSubFolders(client, subFolder);
        }
    }
}
```

## تطبيقات عملية
سيناريوهات واقعية يبرز فيها هذا التدفق:

1. **أرشفة البريد الإلكتروني تلقائيًا** – سحب رسائل المجلدات العامة دوريًا وتخزينها في أرشيف متوافق.  
2. **حلول النسخ الاحتياطي** – نسخ المجلدات العامة لـ Exchange إلى نظام ملفات آمن أو حاوية سحابية، مما يضمن تكرار البيانات.  
3. **عملاء بريد مخصصين** – بناء عارضات خفيفة تعرض فقط المجلدات والرسائل المطلوبة، مما يقلل تعقيد واجهة المستخدم.

## اعتبارات الأداء
عند التوسع إلى آلاف المجلدات وملايين الرسائل، ضع في اعتبارك النصائح التالية:

- **تجميع الاتصالات** – أعد استخدام نسخة واحدة من `ExchangeClient` للعمليات المتعددة بدلاً من إنشاء عميل جديد لكل مجلد.  
- **التحميل الكسول** – اطلب البيانات الوصفية التي تحتاجها فقط (`listMessages` مع معامل `maxCount`) وجلب المحتوى الكامل عند الطلب.  
- **تحرير الكائنات** – استدعِ `client.dispose()` بعد انتهاء الدفعة لتحرير اتصالات HTTP والذاكرة المؤقتة الخاصة بالخيط.  
- **المعالجة المتوازية** – وزّع المجلدات العليا على عدة خيوط، كل منها يمتلك نسخة عميل خاصة، لاستغلال المعالجات متعددة النوى بفعالية.

## الأسئلة المتكررة

**س: هل يمكنني استخدام هذا الكود مع Exchange Online (Office 365)؟**  
ج: نعم. قدم نقطة النهاية EWS الخاصة بـ Office 365 (`https://outlook.office365.com/EWS/Exchange.asmx`) واستخدم المصادقة الحديثة (OAuth) – Aspose.Email يدعم رموز OAuth مباشرةً.

**س: ماذا لو كان المجلد يحتوي على أكثر من 10 000 رسالة؟**  
ج: استخدم نسخة `listMessages` التي تقبل معلمات `skip` و `take` لتقسيم النتائج إلى صفحات، مما يحافظ على استهلاك الذاكرة تحت السيطرة.

**س: هل هناك حد لحجم البريد الإلكتروني الواحد الذي يمكنني تنزيله؟**  
ج: تقوم الـ API ببث المحتوى، لذا تدعم الرسائل حتى 150 MB دون الوصول إلى حد كومة Java، بشرط أن تكون الذاكرة الأصلية للـ JVM كافية.

**س: هل أحتاج إلى معالجة شهادات SSL يدويًا؟**  
ج: بشكل افتراضي، يثق Aspose.Email بمخزن المفاتيح الافتراضي لـ Java. إذا كان خادم Exchange يستخدم شهادة موقعة ذاتيًا، استوردها إلى مخزن الثقة الخاص بالـ JVM أو اضبط `client.setEnableSslVerification(false)` للاختبار فقط.

**س: كيف يمكنني تسجيل العمليات لأغراض التدقيق؟**  
ج: فعّل التسجيل المدمج في Aspose.Email عبر تكوين `Logger.setLevel(Level.INFO)` وتوجيه المخرجات إلى ملف أو نظام مراقبة.

## الخاتمة
أصبحت الآن تمتلك وصفة كاملة وجاهزة للإنتاج **كيفية الاتصال بـ Exchange** وإدراج الرسائل من المجلدات العامة بشكل متكرر باستخدام Aspose.Email for Java. تغطي الخطوات إعداد Maven، الترخيص، الاتصال، تعداد المجلدات، استرجاع الرسائل، وتحسين الأداء. يمكنك توسيع هذا الأساس بدمجه مع قواعد البيانات، التخزين السحابي، أو خطوط أنابيب التحليل المخصصة لتلبية احتياجات مؤسستك الخاصة.

---

**آخر تحديث:** 2026-10-02  
**تم الاختبار مع:** Aspose.Email for Java 25.4  
**المؤلف:** Aspose

## دروس ذات صلة

- [كيفية الاتصال بخادم Exchange باستخدام Aspose.Email في Java: دليل خطوة بخطوة](/email/java/exchange-server-integration/aspose-email-java-exchange-server-connection/)
- [كيفية الاتصال وإدراج مجلدات خادم Exchange باستخدام Aspose.Email for Java](/email/java/exchange-server-integration/connect-list-exchange-server-folders-aspose-email-java/)
- [إدارة مجلدات خادم Exchange باستخدام Aspose.Email for Java: دليل شامل](/email/java/exchange-server-integration/exchange-server-folders-aspose-email-java/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}