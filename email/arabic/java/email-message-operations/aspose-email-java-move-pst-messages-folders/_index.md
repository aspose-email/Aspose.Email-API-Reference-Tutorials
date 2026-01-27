---
date: '2026-01-27'
description: تعلم كيفية نقل مجلدات PST والرسائل باستخدام Aspose.Email للغة Java –
  دليل خطوة بخطوة حول كيفية نقل PST بكفاءة.
keywords:
- Aspose.Email Java
- move PST folders
- email management with Aspose
- PST file manipulation in Java
title: كيفية نقل مجلدات PST والرسائل باستخدام Aspose.Email Java
url: /ar/java/email-message-operations/aspose-email-java-move-pst-messages-folders/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# إدارة البريد الإلكتروني المتقدمة باستخدام Aspose.Email Java: نقل مجلدات PST والرسائل

إدارة البريد الإلكتروني بكفاءة أمر حيوي، خاصةً عند التعامل مع كميات كبيرة من البيانات في ملفات PST الخاصة بـ Outlook. في هذا الدليل سنوضح **كيفية نقل pst** المجلدات والرسائل برمجياً باستخدام Aspose.Email for Java، لتتمكن من الحفاظ على صناديق البريد مرتبة وأتمتة مهام النقل.

## إجابات سريعة
- **ما المكتبة المستخدمة؟** Aspose.Email for Java  
- **هل يمكنني نقل كل من المجلدات والرسائل الفردية؟** نعم، باستخدام واجهات `moveItem` و `moveSubfolders`  
- **هل أحتاج إلى ترخيص للإنتاج؟** يتطلب الاستخدام التجاري ترخيص Aspose صالح  
- **ما إصدار Java الموصى به؟** Java 16 أو أحدث  
- **هل يتضمن المثال ملف PST؟** استخدم أي ملف PST تم إنشاؤه بواسطة Outlook للاختبار  

## ما معنى “كيفية نقل pst” في سياق تطوير Java؟
نقل بيانات PST يعني إعادة توطين المجلدات أو عناصر البريد داخل ملف جدول التخزين الشخصي (PST) برمجياً. هذا مفيد للتنظيف الجماعي، الأرشفة، أو ترحيل المحتوى بين مخازن البريد دون الحاجة إلى تفاعل يدوي مع Outlook.

## لماذا نستخدم Aspose.Email for Java لنقل بيانات PST؟
- **بدون اعتماد على Outlook** – يعمل على أي منصة تحتوي على بيئة تشغيل Java.  
- **واجهة PST كاملة** – تدعم إنشاء المجلدات، حذفها، ونقل العناصر.  
- **أداء عالي** – مُحسّن لصناديق البريد الكبيرة.  
- **معالجة أخطاء قوية** – استثناءات مفصلة تساعدك على استكشاف المشكلات بسرعة.

## المتطلبات المسبقة
- **Aspose.Email for Java** (أحدث نسخة)  
- **JDK 16+** (أو أحدث)  
- نظام بناء Maven أو Gradle  
- ملف `.pst` تجريبي للاختبار  

## إعداد Aspose.Email for Java
لاستخدام Aspose.Email، أضفه إلى مشروعك. إذا كنت تستخدم Maven، أضف الاعتماد التالي إلى ملف `pom.xml` الخاص بك:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
### خطوات الحصول على الترخيص
1. **تجربة مجانية** – ابدأ بتجربة مجانية لاستكشاف ميزات Aspose.Email.  
2. **ترخيص مؤقت** – احصل على ترخيص مؤقت للاستخدام الموسع من [موقع Aspose](https://purchase.aspose.com/temporary-license/).  
3. **شراء** – فكر في شراء ترخيص كامل إذا كان المكتبة تلبي احتياجات الإنتاج لديك.  

### التهيئة الأساسية والإعداد
تأكد من أن المكتبة مُشار إليها بشكل صحيح في إعداد مشروعك لبدء العمل مع ملفات PST:
```java
import com.aspose.email.PersonalStorage;
import com.aspose.email.StandardIpmFolder;

PersonalStorage pst = PersonalStorage.fromFile("YOUR_DOCUMENT_DIRECTORY/test.pst");
```

## كيفية نقل مجلدات PST والرسائل
فيما يلي العمليات الأساسية التي تحتاج إلى معرفتها عندما تريد **كيفية نقل pst** العناصر بكفاءة.

### تهيئة والوصول إلى ملف PST
**نظرة عامة**: تعلم كيفية تهيئة ملف PST والوصول إلى مجلداته المعرفة مسبقاً مثل Inbox وDeleted Items.  

#### الخطوة 1: تحميل ملف PST
```java
PersonalStorage pst = PersonalStorage.fromFile("YOUR_DOCUMENT_DIRECTORY/test.pst");
```

#### الخطوة 2: الوصول إلى المجلدات المعرفة مسبقاً
- **مجلد الوارد**:
    ```java
    FolderInfo inbox = pst.getPredefinedFolder(StandardIpmFolder.Inbox);
    ```
- **مجلد العناصر المحذوفة**:
    ```java
    FolderInfo deletedItems = pst.getPredefinedFolder(StandardIpmFolder.DeletedItems);
    ```

### نقل مجلد فرعي إلى مجلد آخر داخل PST
**نظرة عامة**: نقل مجلد فرعي كامل من مجلد إلى آخر داخل ملف PST.

#### الخطوة 1: الوصول إلى المجلدات المصدر والوجهة
```java
FolderInfo inbox = pst.getPredefinedFolder(StandardIpmFolder.Inbox);
FolderInfo deletedItems = pst.getPredefinedFolder(StandardIpmFolder.DeletedItems);
```

#### الخطوة 2: الحصول على مجلد فرعي محدد من الوارد
```java
FolderInfo subfolder = inbox.getSubFolder("Subfolder");
```

#### الخطوة 3: نقل المجلد الفرعي بالكامل
```java
pst.moveItem(subfolder, deletedItems);
```

### نقل رسائل فردية بين المجلدات في PST
**نظرة عامة**: نقل رسائل بريد إلكتروني واحدة من مجلد إلى آخر.

#### الخطوة 1: استرجاع الرسائل من مجلد فرعي محدد
```java
FolderInfo subfolder = inbox.getSubFolder("Subfolder");
MessageInfoCollection contents = subfolder.getContents();
```

#### الخطوة 2: نقل الرسالة الأولى إلى مجلد العناصر المحذوفة
```java
pst.moveItem(contents.get_Item(0), deletedItems);
```

### نقل جميع المجلدات الفرعية من مجلد إلى آخر في PST
**نظرة عامة**: نقل كل المجلدات الفرعية من مجلد المصدر (مثل Inbox) إلى مجلد الوجهة (مثل Deleted Items).

#### الخطوة 1: الوصول إلى المجلدات المصدر والوجهة
```java
FolderInfo inbox = pst.getPredefinedFolder(StandardIpmFolder.Inbox);
FolderInfo deletedItems = pst.getPredefinedFolder(StandardIpmFolder.DeletedItems);
```

#### الخطوة 2: نقل جميع المجلدات الفرعية
```java
inbox.moveSubfolders(deletedItems);
```

### نقل جميع محتويات مجلد فرعي إلى مجلد آخر في PST
**نظرة عامة**: نقل كل الرسائل داخل مجلد فرعي إلى مجلد مختلف.

#### الخطوة 1: الوصول إلى المجلدات المصدر والوجهة
```java
FolderInfo inbox = pst.getPredefinedFolder(StandardIpmFolder.Inbox);
FolderInfo deletedItems = pst.getPredefinedFolder(StandardIpmFolder.DeletedItems);
```

#### الخطوة 2: الحصول على مجلد فرعي محدد من الوارد
```java
FolderInfo subfolder = inbox.getSubFolder("Subfolder");
```

#### الخطوة 3: نقل جميع محتويات المجلد الفرعي
```java
subfolder.moveContents(deletedItems);
```

## تطبيقات عملية
يمكن أن يكون نقل مجلدات PST والرسائل مفيداً في السيناريوهات التالية:
- **ترحيل البيانات** – الانتقال من Outlook إلى نظام بريد آخر.  
- **أرشفة البريد** – تنظيم الرسائل القديمة في مجلدات أرشيفية بشكل منهجي.  
- **عمليات التنظيف** – إزالة الفوضى من صناديق الوارد بنقل العناصر غير الضرورية.

## اعتبارات الأداء
عند العمل مع ملفات PST باستخدام Aspose.Email في Java، ضع في اعتبارك النصائح التالية:

- **تحسين استخدام الموارد** – أغلق كائنات `PersonalStorage` فور الانتهاء (استخدام try‑with‑resources أو `dispose` صريح).  
- **إدارة الذاكرة** – تجنب تحميل مجلدات كبيرة بالكامل في الذاكرة؛ عالج العناصر على دفعات.  

### أفضل الممارسات
- حرّر موارد PST دائماً بعد الانتهاء من العمليات.  
- تحقق من وجود المجلد قبل محاولة النقل لتجنب الاستثناءات.  

## الأسئلة المتكررة
**س1: ما هو ملف PST؟**  
ج1: ملف PST (Personal Storage Table) يستخدمه Microsoft Outlook لتخزين رسائل البريد، جهات الاتصال، عناصر التقويم، وغيرها من البيانات محلياً.

**س2: هل يمكنني استخدام Aspose.Email for Java في مشاريع تجارية؟**  
ج2: نعم، يمكنك استخدامه تجارياً بشرط الحصول على ترخيص صالح عبر [خيارات شراء Aspose](https://purchase.aspose.com/buy).

**س3: كيف أتعامل مع الاستثناءات عند العمل مع ملفات PST باستخدام Aspose.Email؟**  
ج3: غلف الشيفرة بكتل `try‑catch` لالتقاط `IOException` أو `InvalidOperationException` أو الاستثناءات الخاصة بـ Aspose، ثم سجّلها أو أعد رميها حسب الحاجة.

**س4: ما هي متطلبات النظام لتشغيل هذا الشيفرة؟**  
ج4: تحتاج إلى JDK 16 أو أحدث وبيئة تطوير متكاملة مثل IntelliJ IDEA أو Eclipse. يجب تضمين ملف JAR الخاص بـ Aspose.Email في مسار الفئة (classpath) للمشروع.

**س5: أين يمكنني العثور على موارد إضافية حول Aspose.Email for Java؟**  
ج5: زر الوثائق الرسمية على [Aspose Email Java Reference](https://reference.aspose.com/email/java/).

**س6: هل يدعم Aspose.Email ملفات PST المحمية بكلمة مرور؟**  
ج6: نعم، يمكنك فتح ملفات PST المشفرة بتمرير كلمة المرور عند استدعاء `PersonalStorage.fromFile`.

**س7: كيف يمكنني التحقق من نجاح عملية النقل؟**  
ج7: بعد استدعاء `moveItem` أو `moveSubfolders`، استعلم عن المجلد الوجهة باستخدام `getContents()` أو `getSubFolders()` لتأكيد وجود العناصر المنقولة.

---

**آخر تحديث:** 2026-01-27  
**تم الاختبار مع:** Aspose.Email for Java 25.4 (JDK 16)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

## الموارد
- **الوثائق**: [Aspose Email Java Reference](https://reference.aspose.com/email/java/)
- **التنزيل**: [Aspose Email Java Releases](https://releases.aspose.com/email/java/)
- **الشراء**: [Buy Aspose Products](https://purchase.aspose.com/buy)
- **التجربة المجانية**: [Aspose Free Trials](https://releases.aspose.com/email/java/)
- **الترخيص المؤقت**: [Get a Temporary License](https://purchase.aspose.com/temporary-license/)