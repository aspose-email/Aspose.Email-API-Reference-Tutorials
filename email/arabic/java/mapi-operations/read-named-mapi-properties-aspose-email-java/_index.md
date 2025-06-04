---
"date": "2025-05-29"
"description": "تعرّف على كيفية استخراج خصائص MAPI المُسمّاة بكفاءة من رسائل البريد الإلكتروني والمرفقات باستخدام Aspose.Email لـ Java. يغطي هذا الدليل خطوة بخطوة الإعداد، وأمثلة التعليمات البرمجية، والتطبيقات العملية."
"title": "اقرأ خصائص MAPI المسماة في Java باستخدام Aspose.Email - دليل شامل"
"url": "/ar/java/mapi-operations/read-named-mapi-properties-aspose-email-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية قراءة خصائص MAPI المسماة باستخدام Aspose.Email في Java

## مقدمة

قد يكون استخراج خصائص مُسمّاة مُحددة من رسائل البريد الإلكتروني أو المرفقات مُعقّدًا، خاصةً مع تنسيق MAPI في Microsoft Outlook. إذا كنت تُطوّر تطبيق Java يحتاج إلى هذه الوظيفة، فإن Aspose.Email for Java هو الحل الأمثل. سيُرشدك هذا البرنامج التعليمي إلى كيفية فهم خصائص MAPI المُسمّاة بفعالية.

**ما سوف تتعلمه:**
- إعداد وتكوين Aspose.Email لـ Java.
- استخراج الخصائص المسماة من `MapiMessage` أشياء.
- استرجاع الخصائص مباشرة من مرفقات البريد الإلكتروني.
- التطبيقات الواقعية لقراءة خصائص MAPI.

قبل أن نبدأ، دعنا نستعرض المتطلبات الأساسية التي ستحتاجها.

## المتطلبات الأساسية

تأكد من أن لديك:
- **مجموعة تطوير جافا (JDK)**:تم تثبيت JDK 16 أو أعلى على نظامك.
- **مافن**:المعرفة بـ Maven لإدارة التبعيات.
- **Aspose.Email لمكتبة Java**:ضروري للمهام التي سنقوم بأدائها.

### متطلبات إعداد البيئة
1. قم بتثبيت وتكوين JDK 16+ على جهازك.
2. قم بإعداد مشروع قائم على Maven في IDE المفضل لديك (على سبيل المثال، IntelliJ IDEA، Eclipse).

### متطلبات المعرفة
يجب عليك أن تفهم:
- مفاهيم برمجة جافا الأساسية.
- إدارة التبعيات باستخدام Maven.
- هيكل رسائل البريد الإلكتروني.

## إعداد Aspose.Email لـ Java

لاستخدام Aspose.Email لـ Java، أضفه كتبعية في `pom.xml` الملف باستخدام Maven:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### الحصول على الترخيص
لاستخدام Aspose.Email لـ Java، يمكنك:
- **نسخة تجريبية مجانية**:قم بتنزيل النسخة التجريبية لاختبار الوظائف.
- **رخصة مؤقتة**:الحصول عليها من [موقع Aspose](https://purchase.aspose.com/temporary-license/).
- **شراء**:شراء ترخيص كامل للوصول على المدى الطويل.

### التهيئة الأساسية
بعد إعداد مشروع Maven وإضافة التبعية، قم بتهيئة Aspose.Email على النحو التالي:

```java
import com.aspose.email.License;

public class InitializeAspose {
    public static void main(String[] args) {
        // تقديم طلب الترخيص (إن وجد)
        License license = new License();
        try {
            license.setLicense("path/to/your/license/file.lic");
        } catch (Exception e) {
            System.out.println("License setup failed: " + e.getMessage());
        }
    }
}
```

## دليل التنفيذ

### قراءة خصائص MAPI المسماة من `MapiMessage` هدف

يوضح هذا القسم كيفية استخراج خصائص محددة مسماة مباشرة من `MapiMessage`.

#### ملخص
سوف نقرأ خصائص مسماة مثل "TEST" و"MYPROP" من رسالة بريد إلكتروني مخزنة بتنسيق MSG.

#### خطوات:
##### الخطوة 1: تحميل ملف MSG

```java
import com.aspose.email.MapiMessage;
import com.aspose.email.MapiNamedProperty;

public class ReadNamedMapiPropertiesFeature {
    public static void main(String[] args) {
        String dataDir = "YOUR_DOCUMENT_DIRECTORY/outlook/";
        readNamedMAPIProperty(dataDir);
    }
    
    @SuppressWarnings("unchecked")
    public static void readNamedMAPIProperty(String dataDir) {
        // تحميل ملف MSG
        MapiMessage message = MapiMessage.fromFile(dataDir + "message.msg");
        
        // استرداد الخصائص المسماة
        for (MapiNamedProperty mapiNamedProp : (Iterable<MapiNamedProperty>) message.getNamedProperties().getValues()) {
            switch (mapiNamedProp.getNameId()) {
                case "TEST":
                    System.out.println(mapiNamedProp.getNameId() + " equals " + mapiNamedProp.getString());
                    break;
                case "MYPROP":
                    System.out.println(mapiNamedProp.getNameId() + " equals " + mapiNamedProp.getString());
                    break;
            }
        }
    }
}
```

**توضيح:**
- **`fromFile()`**:يقوم بتحميل ملف MSG من الدليل المحدد.
- **`getNamedProperties().getValues()`**:يتكرر كل خاصية مسماة، مما يسمح لك بالتصفية والمعالجة حسب الحاجة.

### قراءة خصائص MAPI المسماة من مرفق

يوضح هذا القسم كيفية استخراج الخصائص من المرفقات داخل `MapiMessage`.

#### ملخص
سوف نقوم باسترجاع خصائص مخصصة مثل "CustomAttGuid" من المرفق الأول للبريد الإلكتروني المخزن بتنسيق EML.

#### خطوات:
##### الخطوة 1: تحميل ملف EML وتحويله

```java
import com.aspose.email.MailMessage;
import com.aspose.email.MapiAttachment;

public class ReadMapiPropertyFromAttachmentFeature {
    public static void main(String[] args) {
        String dataDir = "YOUR_DOCUMENT_DIRECTORY/outlook/";
        readNamedMapiPropertyFromAttachment(dataDir);
    }
    
    @SuppressWarnings("unchecked")
    public static void readNamedMapiPropertyFromAttachment(String dataDir) {
        // قم بتحميل ملف EML وتحويله إلى MapiMessage
        MailMessage mail = MailMessage.load(dataDir + "test.eml");
        MapiMessage mapi = MapiMessage.fromMailMessage(mail);
        
        // الوصول إلى الخصائص المسماة من المرفق الأول
        MapiAttachment firstAttachment = mapi.getAttachments().get_Item(0);
        for (MapiNamedProperty namedProperty : (Iterable<MapiNamedProperty>) firstAttachment.getNamedProperties().getValues()) {
            if (namedProperty.getNameId().equalsIgnoreCase("CustomAttGuid")) {
                System.out.println("Equal..");
            }
        }
    }
}
```

**توضيح:**
- **`MailMessage.load()`**:يقوم بتحميل ملف EML.
- **`fromMailMessage()`**:يحول `MailMessage` كائن في `MapiMessage`.
- **الوصول إلى المرفقات**:استرداد الخصائص من المرفقات باستخدام `getAttachments().get_Item(0)`.

## التطبيقات العملية

قراءة خصائص MAPI المسماة لها العديد من التطبيقات في العالم الحقيقي:
1. **تصفية البريد الإلكتروني وتصنيفه**:تصنيف رسائل البريد الإلكتروني تلقائيًا استنادًا إلى البيانات الوصفية المخصصة.
2. **أرشفة البيانات**:استخراج بيانات محددة لأغراض الأرشفة.
3. **التكامل مع أنظمة إدارة علاقات العملاء**:مزامنة بيانات البريد الإلكتروني مع أنظمة إدارة علاقات العملاء.
4. **الامتثال والتدقيق**:ضمان الامتثال من خلال استخراج الخصائص وفقًا للمتطلبات التنظيمية.

## اعتبارات الأداء

عند العمل مع Aspose.Email في Java، ضع ما يلي في الاعتبار:
- تحسين التعامل مع الملفات: تقليل عمليات الإدخال/الإخراج من خلال معالجة الملفات بكفاءة.
- إدارة استخدام الذاكرة: تعامل مع رسائل البريد الإلكتروني الكبيرة دون استنفاد موارد النظام.
- يستخدم `try-with-resources` لإدارة الموارد تلقائيًا عند الاقتضاء.

## خاتمة

في هذا البرنامج التعليمي، تعلمت كيفية قراءة خصائص MAPI المسماة من كلا `MapiMessage` الكائنات والمرفقات باستخدام Aspose.Email لجافا. تتيح هذه التقنيات معالجة بيانات البريد الإلكتروني بكفاءة داخل تطبيقاتك.

**الخطوات التالية:**
- قم بتجربة أنواع الخصائص الإضافية واستكشف الإمكانات الكاملة لـ Aspose.Email.
- فكر في دمج هذه الميزات في المشاريع أو الأنظمة الأكبر التي تقوم بتطويرها.

لمَ لا تُجرّبه؟ تطبيق هذا الحل سيُحسّن بشكل كبير طريقة إدارة بيانات البريد الإلكتروني واستخدامها في جافا!

## قسم الأسئلة الشائعة

1. **كيف أتعامل مع رسائل البريد الإلكتروني الكبيرة بكفاءة باستخدام Aspose.Email؟**
   - استخدم واجهات برمجة التطبيقات المتدفقة لمعالجة المرفقات دون تحميل الملفات بالكامل في الذاكرة.
2. **هل يمكنني قراءة الخصائص من مرفقات متعددة في نفس الوقت؟**
   - نعم، قم بالتكرار عبر مجموعة المرفقات وقم بتطبيق منطق استخراج الخصائص المماثل لكل عنصر.
3. **ماذا لو احتاج تطبيقي إلى التعامل مع رسائل البريد الإلكتروني بتنسيقات أخرى غير MSG أو EML؟**
   - يدعم Aspose.Email تنسيقات البريد الإلكتروني المختلفة؛ راجع [توثيق Aspose](https://docs.aspose.com/email/java/) لمزيد من التفاصيل.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}