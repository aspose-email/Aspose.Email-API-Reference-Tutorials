---
"date": "2025-05-29"
"description": "تعرف على كيفية إنشاء قوائم توزيع MAPI وإدارتها داخل ملفات PST باستخدام مكتبة Aspose.Email في Java، مما يؤدي إلى تبسيط سير عمل البريد الإلكتروني بكفاءة."
"title": "إدارة قوائم توزيع MAPI في ملفات PST باستخدام Aspose.Email Java"
"url": "/ar/java/mapi-operations/aspose-email-java-mapi-distribution-lists-pst/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# إدارة قوائم توزيع MAPI في ملفات PST باستخدام Aspose.Email Java
تُعد إدارة قوائم توزيع البريد الإلكتروني أمرًا بالغ الأهمية للشركات التي تسعى إلى تبسيط عمليات التواصل، خاصةً عند التعامل مع أعداد كبيرة من جهات الاتصال أو فرق عمل ديناميكية. سيرشدك هذا البرنامج التعليمي إلى كيفية إنشاء قوائم توزيع MAPI (واجهة برمجة تطبيقات المراسلة) وإضافتها إلى ملف PST (جدول التخزين الشخصي) باستخدام مكتبة Aspose.Email القوية في جافا.

## ما سوف تتعلمه
- كيفية إنشاء قوائم توزيع MAPI وإدارتها
- خطوات دمج هذه القوائم في ملف PST
- التطبيقات العملية لهذه الميزة
- نصائح لتحسين الأداء للتعامل مع مجموعات البيانات الكبيرة

دعنا نستكشف كيفية الاستفادة من Aspose.Email Java لتحسين سير عمل إدارة البريد الإلكتروني الخاص بك.

## المتطلبات الأساسية
قبل البدء، تأكد من توفر ما يلي:
1. **المكتبات والتبعيات**:ستحتاج إلى مكتبة Aspose.Email الإصدار 25.4 مع دعم JDK16.
2. **إعداد البيئة**:يفترض هذا البرنامج التعليمي الإلمام الأساسي ببيئات تطوير Java مثل Maven أو Gradle لإدارة التبعيات.
3. **متطلبات المعرفة**:المعرفة بمفاهيم برمجة جافا، بما في ذلك مبادئ البرمجة الكائنية والعمل مع المكتبات الخارجية.

## إعداد Aspose.Email لـ Java
### استخدام Maven
لتضمين مكتبة Aspose.Email في مشروعك باستخدام Maven، أضف التبعية التالية إلى مشروعك `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
### الحصول على الترخيص
يقدم Aspose.Email تجربة مجانية لاستكشاف كامل إمكانياته. يمكنك الحصول على ترخيص مؤقت لمزيد من الاختبارات الموسعة أو شراء اشتراك لمواصلة الاستخدام.
1. **نسخة تجريبية مجانية**:قم بتنزيل أحدث إصدار من [إصدارات Aspose](https://releases.aspose.com/email/java/).
2. **رخصة مؤقتة**:اطلب واحدة في [ترخيص Aspose المؤقت](https://purchase.aspose.com/temporary-license/) لفتح كافة الميزات.
3. **شراء**:للحصول على الوصول الكامل، قم بزيارة [شراء Aspose](https://purchase.aspose.com/buy).

لتهيئة Aspose.Email في مشروعك:

```java
// قم بتشغيل الترخيص إذا كان متاحًا
License license = new License();
license.setLicense("path/to/your/license/file");
```
## دليل التنفيذ
### الميزة 1: إنشاء قائمة توزيع MAPI وإضافتها إلى PST
تتضمن هذه الميزة إنشاء جهات اتصال، وتشكيل قائمة توزيع من هذه جهات الاتصال، وإضافة هذه القائمة إلى ملف PST.
#### ملخص
ستُنشئ جهتي اتصال برمجيًا، وتُنشئ قائمة توزيع، وتحفظها في ملف PST. تُؤتمت هذه العملية ما كان ليكون مهمة يدوية لإدارة قوائم البريد الإلكتروني داخل Outlook.
#### خطوات
##### الخطوة 1: إعداد البيئة
قم بتحديد دليل المستند الذي سيتم حفظ ملف PST فيه:

```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY/";
```
##### الخطوة 2: إنشاء ملف PST جديد
تهيئة ملف PST جديد بتنسيق Unicode:

```java
PersonalStorage pst = PersonalStorage.create(dataDir + "pstFileName_out.pst", FileFormatVersion.Unicode);
```
##### الخطوة 3: إضافة جهات اتصال إلى PST
إنشاء جهات اتصال وإضافتها إلى ملف PST الذي تم إنشاؤه حديثًا:

```java
FolderInfo contactFolder = pst.createPredefinedFolder("Contacts", StandardIpmFolder.Contacts);

MapiContact contact1 = new MapiContact("Sebastian Wright", "SebastianWright@dayrep.com");
String entryId1 = contactFolder.addMapiMessageItem(contact1).getEntryIdString();

MapiContact contact2 = new MapiContact("Wichert Kroos", "WichertKroos@teleworm.us");
String entryId2 = contactFolder.addMapiMessageItem(contact2).getEntryIdString();
```
##### الخطوة 4: إنشاء أعضاء قائمة التوزيع
تحويل جهات الاتصال إلى أعضاء قائمة التوزيع:

```java
byte[] decodedBytes1 = Base64.decodeBase64(entryId1.getBytes());
MapiDistributionListMember member1 = new MapiDistributionListMember("Sebastian Wright", "SebastianWright@dayrep.com");
member1.setEntryId(decodedBytes1);
member1.setEntryIdType(MapiDistributionListEntryIdType.Contact);

byte[] decodedBytes2 = Base64.decodeBase64(entryId2.getBytes());
MapiDistributionListMember member2 = new MapiDistributionListMember("Wichert Kroos", "WichertKroos@teleworm.us");
member2.setEntryId(decodedBytes2);
member2.setEntryIdType(MapiDistributionListEntryIdType.Contact);
```
##### الخطوة 5: إضافة الأعضاء إلى قائمة التوزيع
إنشاء قائمة التوزيع وإضافة الأعضاء:

```java
MapiDistributionListMemberCollection members = new MapiDistributionListMemberCollection();
members.addItem(member1);
members.addItem(member2);

MapiDistributionList distributionList = new MapiDistributionList("Contact List", members);
distributionList.setBody("This is a test distribution list.");
distributionList.setSubject("Team Contacts");

contactFolder.addMapiMessageItem(distributionList);
```
### الميزة 2: إنشاء قائمة توزيع MAPI لمرة واحدة وإضافتها إلى PST
هنا، يمكنك إنشاء قائمة توزيع مخصصة دون أي جهات اتصال موجودة مسبقًا.
#### ملخص
تعتبر هذه الميزة مفيدة لقوائم البريد الإلكتروني المؤقتة أو لمرة واحدة والتي تحتاج إلى إعدادها وإرسالها بسرعة.
#### خطوات
##### الخطوة 1: تهيئة البيئة
كما في السابق، ابدأ بتعيين دليل المستندات الخاص بك:

```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY/";
```
##### الخطوة 2: إنشاء ملف PST جديد
قم بتهيئة PST كما هو موضح مسبقًا.
##### الخطوة 3: إضافة الأعضاء إلى القائمة الفردية
إنشاء مجموعة من الأعضاء لهذه القائمة:

```java
MapiDistributionListMemberCollection oneOffMembers = new MapiDistributionListMemberCollection();
oneOffMembers.addItem(new MapiDistributionListMember("John R. Patrick", "JohnRPatrick@armyspy.com"));
oneOffMembers.addItem(new MapiDistributionListMember("Tilly Bates", "TillyBates@armyspy.com"));
```
##### الخطوة 4: إنشاء قائمة التوزيع وإضافتها
قم بتجميع قائمة التوزيع الفريدة وإضافتها إلى ملف PST الخاص بك:

```java
MapiDistributionList oneOffList = new MapiDistributionList("Simple List", oneOffMembers);
contactFolder.addMapiMessageItem(oneOffList);
```
## التطبيقات العملية
1. **التواصل الجماعي**:أتمتة إعداد اتصالات الفريق للمجموعات الخاصة بالمشروع.
2. **إشعارات الأحداث**:قم بإنشاء قوائم سريعة لدعوات الأحداث والإشعارات.
3. **الحملات التسويقية**:إدارة حملات البريد الإلكتروني المستهدفة من خلال تجميع العملاء أو العملاء المحتملين.
4. **التكامل مع أنظمة إدارة علاقات العملاء**:تعزيز أدوات إدارة علاقات العملاء من خلال دمج قوائم جهات الاتصال الديناميكية.

## اعتبارات الأداء
- **تحسين استخدام الموارد**:تأكد من أن تطبيقك يتمتع بتخصيص ذاكرة كافٍ، خاصة عند التعامل مع ملفات PST كبيرة الحجم.
- **التعامل الفعال مع البيانات**:استخدم البث المباشر عندما يكون ذلك ممكنًا للتعامل مع البيانات بكفاءة دون استهلاك مفرط للذاكرة.
- **أفضل ممارسات Aspose.Email**:اتبع إرشادات Aspose بشأن معالجة البريد الإلكتروني للحصول على الأداء الأمثل.

## خاتمة
بإتقان إنشاء وإدارة قوائم توزيع MAPI ضمن ملف PST، يمكنك تحسين كفاءة اتصالات مؤسستك بشكل ملحوظ. يقدم هذا البرنامج التعليمي دليلاً خطوة بخطوة لاستخدام Aspose.Email Java بفعالية، مقدماً المعرفة الأساسية والرؤى العملية.

لاستكشاف هذه الإمكانيات بشكل أعمق، فكّر في تجربة توزيعات أكثر تعقيدًا أو دمج هذه الوظيفة في تطبيقات أكبر. لمزيد من الدعم أو الاستفسارات، تفضل بزيارة [منتدى البريد الإلكتروني Aspose](https://forum.aspose.com/c/email/10).

## قسم الأسئلة الشائعة
**س: هل يمكنني إنشاء قوائم توزيع لملفات PST المتعددة؟**
ج: نعم، يمكنك إنشاء قوائم توزيع منفصلة وإدارتها عبر أجهزة PST المختلفة.

**س: كيف يمكنني التعامل مع قواعد بيانات جهات الاتصال الكبيرة باستخدام Aspose.Email؟**
أ: استخدم تقنيات معالجة البيانات الفعالة مثل المعالجة الدفعية لإدارة مجموعات البيانات الكبيرة بسلاسة.

**س: هل من الممكن استيراد جهات الاتصال الموجودة إلى ملف PST جديد؟**
ج: بالتأكيد. يمكنك قراءة جهات الاتصال من مصادر مختلفة وإضافتها برمجيًا.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}