---
"date": "2025-05-29"
"description": "تعرّف على كيفية إنشاء جهات اتصال MAPI وإدارتها بكفاءة باستخدام Aspose.Email لـ Java. يغطي هذا الدليل كل شيء، بدءًا من إنشاء جهات الاتصال الأساسية ووصولًا إلى إدارتها التفصيلية، بما في ذلك إضافة معلومات احترافية."
"title": "إنشاء جهات اتصال MAPI في Java باستخدام Aspose.Email - دليل خطوة بخطوة"
"url": "/ar/java/mapi-operations/create-mapi-contacts-aspose-email-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية إنشاء جهات اتصال MAPI في Java باستخدام Aspose.Email: دليل خطوة بخطوة

## مقدمة

إدارة جهات الاتصال ضرورية للتطبيقات التي تتطلب تكاملاً قوياً بين البريد الإلكتروني ودفتر العناوين. يوضح هذا الدليل الشامل كيفية إنشاء جهات اتصال MAPI (واجهة برمجة تطبيقات المراسلة) باستخدام مكتبة Aspose.Email القوية في جافا. باتباع هذا البرنامج التعليمي، ستتمكن من أتمتة إنشاء جهات الاتصال، وتحسين تنظيم البيانات، ودمج إدارة جهات الاتصال بسلاسة في تطبيقات جافا.

**ما سوف تتعلمه:**
- إنشاء جهات اتصال MAPI أساسية ومفصلة
- إدارة المعلومات المهنية والعناوين ورسائل البريد الإلكتروني باستخدام Aspose.Email لـ Java
- إعداد ملف جدول التخزين الشخصي (PST) لتخزين جهات الاتصال بكفاءة

## المتطلبات الأساسية

قبل الغوص في إنشاء جهة اتصال، تأكد من أن لديك ما يلي:

### المكتبات المطلوبة:
- Aspose.Email لمكتبة Java (الإصدار 25.4 أو أحدث)

### متطلبات إعداد البيئة:
- JDK الإصدار 16 أو أعلى
- بيئة التطوير المتكاملة (IDE) حسب اختيارك (IntelliJ IDEA، Eclipse، وما إلى ذلك)

### المتطلبات المعرفية:
فهم أساسي لبرمجة جافا والمعرفة بكيفية التعامل مع مكتبات الطرف الثالث.

## إعداد Aspose.Email لـ Java

للبدء، أدرج مكتبة Aspose.Email في مشروعك. إذا كنت تستخدم Maven، فأضف التبعية التالية إلى مشروعك: `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### خطوات الحصول على الترخيص:
- **نسخة تجريبية مجانية:** قم بتنزيل النسخة التجريبية من [موقع Aspose](https://releases.aspose.com/email/java/) لاستكشاف ميزاته.
- **رخصة مؤقتة:** التقدم بطلب للحصول على رخصة مؤقتة عبر [صفحة الشراء](https://purchase.aspose.com/temporary-license/).
- **شراء:** فكر في شراء ترخيص كامل منهم [صفحة الشراء](https://purchase.aspose.com/buy) إذا كان Aspose.Email يلبي احتياجاتك.

### التهيئة الأساسية:
بمجرد التثبيت، قم بتشغيل Aspose.Email في تطبيق Java الخاص بك لبدء إنشاء جهات اتصال MAPI وإدارتها.

## دليل التنفيذ

سنغطي ثلاث ميزات رئيسية: إنشاء جهات اتصال أساسية، وإدراج المعلومات الاحترافية، وإدارة التفاصيل الشاملة.

### إنشاء جهة اتصال MAPI أساسية

#### ملخص
تتيح لك هذه الميزة إنشاء جهات اتصال بسيطة باستخدام الاسم الأول واسم العائلة وعنوان البريد الإلكتروني فقط، وهي مناسبة للتطبيقات التي تتطلب الحد الأدنى من البيانات.

#### خطوات التنفيذ

##### الخطوة 1: استيراد الفئات المطلوبة
```java
import com.aspose.email.MapiContact;
```

##### الخطوة 2: إنشاء جهة اتصال MAPI
فيما يلي كيفية إنشاء جهة اتصال MAPI أساسية:
```java
public static MapiContact createBasicMapiContact(String firstName, String lastName, String emailAddress) {
    return new MapiContact(firstName + " " + lastName, emailAddress);
}
```
**توضيح:** هذه الطريقة تعمل على تهيئة `MapiContact` باستخدام الاسم وعنوان البريد الإلكتروني المُقدَّمين. تُخزَّن جهة الاتصال بأقل قدر من المعلومات.

### إنشاء جهة اتصال MAPI بالمعلومات المهنية

#### ملخص
قم بتعزيز جهات الاتصال الخاصة بك عن طريق إضافة تفاصيل مهنية مثل اسم الشركة والمسمى الوظيفي وأرقام الهواتف.

#### خطوات التنفيذ

##### الخطوة 1: استيراد فئات إضافية
```java
import com.aspose.email.MapiContactNamePropertySet;
import com.aspose.email.MapiContactProfessionalPropertySet;
import com.aspose.email.MapiContactTelephonePropertySet;
```

##### الخطوة 2: إنشاء جهة اتصال MAPI مع التفاصيل المهنية
إليك كيفية تضمين المعلومات المهنية:
```java
public static MapiContact createProfessionalMapiContact(String firstName, String middleName, String lastName,
        String company, String jobTitle, String businessPhone, String mobilePhone) {
    MapiContact contact = new MapiContact();
    contact.setNameInfo(new MapiContactNamePropertySet(firstName, middleName, lastName));
    contact.setProfessionalInfo(new MapiContactProfessionalPropertySet(company, jobTitle));
    contact.getTelephones().setBusinessTelephoneNumber(businessPhone);
    contact.getTelephones().setMobileTelephoneNumber(mobilePhone);
    return contact;
}
```
**توضيح:** هذه الطريقة تعمل على تهيئة `MapiContact` كائن بتفاصيل مُفصّلة، بما في ذلك اسم الشركة والمسمى الوظيفي. كما يُحدّد أرقام هواتف مُتعلّقة بالعمل.

### إنشاء جهة اتصال MAPI بمعلومات مفصلة

#### ملخص
قم بإنشاء جهات اتصال شاملة عن طريق إضافة عناوين فعلية ومعلومات البريد الإلكتروني وسمات الجنس لإدارة مفصلة.

#### خطوات التنفيذ

##### الخطوة 1: استيراد فئات إضافية
```java
import com.aspose.email.MapiContactNamePropertySet;
import com.aspose.email.MapiContactProfessionalPropertySet;
import com.aspose.email.MapiContactTelephonePropertySet;
import com.aspose.email.MapiContactElectronicAddress;
import com.aspose.email.MapiContactGender;
```

##### الخطوة 2: إنشاء جهة اتصال MAPI مفصلة
إليك كيفية إنشاء جهة اتصال مفصلة:
```java
public static MapiContact createDetailedMapiContact(String firstName, String middleName, String lastName,
        MapiContactGender gender, String company, String jobTitle, String email, String workAddress) {
    MapiContact contact = new MapiContact();
    contact.setNameInfo(new MapiContactNamePropertySet(firstName, middleName, lastName));
    contact.getPersonalInfo().setGender(gender);
    contact.setProfessionalInfo(new MapiContactProfessionalPropertySet(company, jobTitle));
    contact.getPhysicalAddresses().getWorkAddress().setAddress(workAddress);
    contact.getElectronicAddresses().setEmail1(new MapiContactElectronicAddress(email));
    return contact;
}
```
**توضيح:** هذه الطريقة تعمل على تهيئة `MapiContact` مع معلومات مفصلة، بما في ذلك الجنس والعنوان الفعلي. ويضمن ذلك جمع جميع البيانات ذات الصلة.

### إنشاء ملف PST وإضافة جهات اتصال

#### ملخص
قم بتخزين جهات اتصال متعددة في ملف جدول التخزين الشخصي (PST) للإدارة المركزية.

#### خطوات التنفيذ

##### الخطوة 1: استيراد الفئات المطلوبة
```java
import com.aspose.email.FileFormatVersion;
import com.aspose.email.FolderInfo;
import com.aspose.email.MapiContact;
import com.aspose.email.PersonalStorage;
import com.aspose.email.StandardIpmFolder;
```

##### الخطوة 2: إنشاء PST وإضافة جهات اتصال
إليك كيفية إنشاء ملف PST وإضافة جهات اتصال:
```java
public static void createPstAndAddContacts(MapiContact[] contacts) {
    String pstPath = "YOUR_OUTPUT_DIRECTORY/MapiContactToPST_out.pst";
    PersonalStorage pst = PersonalStorage.create(pstPath, FileFormatVersion.Unicode);
    FolderInfo contactFolder = pst.createPredefinedFolder("Contacts", StandardIpmFolder.Contacts);
    for (MapiContact contact : contacts) {
        contactFolder.addMapiMessageItem(contact);
    }
}
```
**توضيح:** تعمل هذه الطريقة على إنشاء ملف PST وإضافة ملفات متعددة `MapiContact` قم بجمع الكائنات فيه، وتنظيمها ضمن مجلد "جهات الاتصال".

## التطبيقات العملية

1. **أنظمة إدارة علاقات العملاء:** أتمتة إنشاء جهات الاتصال في برنامج إدارة علاقات العملاء.
2. **عملاء البريد الإلكتروني:** قم بتعزيز عملاء البريد الإلكتروني من خلال دمج ميزات إدارة جهات الاتصال القوية.
3. **مزامنة دفتر العناوين:** استخدم هذه الوظيفة لمزامنة جهات الاتصال عبر منصات وأجهزة مختلفة.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}