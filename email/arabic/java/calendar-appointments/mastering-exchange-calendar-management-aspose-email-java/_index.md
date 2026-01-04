---
date: '2026-01-04'
description: تعلم كيفية إنشاء تقويم Exchange باستخدام Java و Aspose.Email للـ Java.
  يتضمن تبعية Maven، الاتصال بـ Exchange عبر Java، وإدارة المواعيد.
keywords:
- Exchange Calendar Management
- Aspose.Email for Java
- Java Exchange Server Integration
title: إنشاء تقويم Exchange باستخدام Java و Aspose.Email – دليل شامل
url: /ar/java/calendar-appointments/mastering-exchange-calendar-management-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# إنشاء تقويم Exchange بلغة Java باستخدام Aspose.Email

## المقدمة

إدارة البريد الإلكتروني والتقويمات في بيئة الأعمال يمكن أن تكون معقدة، خاصةً عندما تحتاج إلى **create exchange calendar java** برامج تعمل عبر عدة مستخدمين ومناطق زمنية. لحسن الحظ، **Aspose.Email for Java** يبسط هذه المهام من خلال توفير واجهات برمجة تطبيقات قوية لإدارة تقويمات خادم Exchange. في هذا الدليل الشامل، ستتعلم كيفية الاتصال بخادم Exchange، وإنشاء مجلدات تقويم، ومعالجة المواعيد—كل ذلك باستخدام كود Java واضح خطوة بخطوة.

**ما ستتعلمه**
- كيفية **connect to exchange java** باستخدام Aspose.Email  
- كيفية إضافة **maven dependency aspose email** إلى مشروعك  
- إنشاء مجلد تقويم جديد وإدارة المواعيد  
- تحديث، سرد، وإلغاء المواعيد  

هيا نبدأ!

## أسئلة سريعة
- **ما هي المكتبة الأساسية؟** Aspose.Email for Java  
- **كيف أضيف المكتبة؟** استخدم تبعية Maven الموضحة أدناه  
- **هل يمكنني إنشاء مجلد تقويم؟** نعم، باستدعاء API واحد  
- **هل أحتاج إلى ترخيص؟** النسخة التجريبية تعمل للتطوير؛ الترخيص الكامل مطلوب للإنتاج  
- **هل هذا متوافق مع Office 365؟** بالتأكيد – نفس الكود يعمل مع Exchange Online  

## ما هو “create exchange calendar java”؟
إنشاء تقويم Exchange بلغة Java يعني التفاعل برمجيًا مع صندوق بريد Exchange لإضافة أو تعديل أو إزالة عناصر التقويم. هذا النهج مثالي للجدولة الآلية، أدوات إدارة الاجتماعات، أو مزامنة التقويم على مستوى المؤسسة.

## لماذا تستخدم Aspose.Email for Java؟
- **Full‑featured API** – يتعامل مع Exchange Web Services (EWS) دون الحاجة إلى معالجة SOAP منخفضة المستوى.  
- **Cross‑platform** – يعمل على Windows وLinux وmacOS مع أي بيئة تشغيل JDK 16+.  
- **No external dependencies** – المكتبة تضم كل ما تحتاجه للتواصل مع Exchange.  

## المتطلبات المسبقة
- **Aspose.Email for Java** library (الإصدار 25.4 أو أحدث)  
- JDK 16 أو أعلى  
- الوصول إلى خادم Exchange (Office 365 أو في الموقع)  
- IDE مثل IntelliJ IDEA أو Eclipse أو NetBeans  

## تبعية Maven لـ Aspose Email
أضف المقتطف التالي إلى ملف `pom.xml`. هذه هي **maven dependency aspose email** التي تحتاجها لجلب المكتبة من Maven Central.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### خطوات الحصول على الترخيص
1. **Free Trial:** قم بتنزيل نسخة تجريبية من [موقع Aspose](https://releases.aspose.com/email/java/) لاختبار الميزات.  
2. **Temporary License:** احصل على ترخيص مؤقت للوصول الكامل للميزات عبر [هذا الرابط](https://purchase.aspose.com/temporary-license/).  
3. **Purchase:** إذا كنت راضيًا، فكر في شراء ترخيص كامل من [صفحة الشراء الخاصة بـ Aspose](https://purchase.aspose.com/buy).

## الاتصال بـ Exchange Java
**Overview:** يوضح هذا القسم كيفية **connect to exchange java** باستخدام عميل EWS.

### الخطوة 1: إنشاء الاتصال
```java
import com.aspose.email.EWSClient;
import com.aspose.email.IEWSClient;

public class ConnectToExchangeServer {
    public static void main(String[] args) {
        IEWSClient client = null;
        try {
            // Connect to Exchange Server with provided URL and credentials
            client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "username", "password");
            System.out.println("Connected to Exchange server.");
        } finally {
            if (client != null)
                client.dispose();
        }
    }
}
```
**Explanation:** استبدل `"username"` و `"password"` ببيانات الاعتماد الفعلية الخاصة بك. ينشئ هذا الكود مثيلًا من `IEWSClient` ستعيد استخدامه لجميع عمليات التقويم اللاحقة.

## إنشاء مجلد تقويم
**Overview:** إنشاء مجلد مخصص داخل تقويم صندوق البريد للحفاظ على تنظيم المواعيد ذات الصلة.

### الخطوة 2: إنشاء مجلد تقويم جديد
```java
import com.aspose.email.MailboxInfo;

public class CreateCalendarFolder {
    public static void main(String[] args) {
        IEWSClient client = null;
        try {
            // Connect to Exchange Server (Replace with actual credentials)
            client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "username", "password");

            // Create a new calendar folder named 'new calendar'
            String calendarUri = client.getMailboxInfo().getCalendarUri();
            client.createFolder(calendarUri, "new calendar", null, "IPF.Appointment");
        } finally {
            if (client != null)
                client.dispose();
        }
    }
}
```
**Explanation:** يظهر المجلد `"new calendar"` تحت التسلسل الهرمي الرئيسي للتقويم، جاهز لتخزين المواعيد التي سيتم إنشاؤها لاحقًا.

## إنشاء موعد في مجلد التقويم
**Overview:** إضافة اجتماع أو حدث إلى مجلد التقويم الذي تم إنشاؤه حديثًا.

### الخطوة 3: إعداد تفاصيل الموعد
```java
import com.aspose.email.Appointment;
import com.aspose.email.MailAddress;
import java.util.Calendar;
import java.util.Date;
import java.util.UUID;

public class CreateAppointment {
    public static void main(String[] args) {
        IEWSClient client = null;
        try {
            // Connect to Exchange Server (Replace with actual credentials)
            client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "username", "password");

            // Setup appointment details
            Calendar calendar = Calendar.getInstance();
            Date startTime = calendar.getTime();
            calendar.add(Calendar.HOUR, 1);
            Date endTime = calendar.getTime();
            String timeZone = "America/New_York";

            Appointment appointment = new Appointment("Room 121", startTime, endTime,
                    MailAddress.to_MailAddress("email1@aspose.com"),
                    MailAddressCollection.to_MailAddressCollection("email2@aspose.com"));
            appointment.setTimeZone(timeZone);
            appointment.setSummary("EMAILNET-35198 - ".concat(UUID.randomUUID().toString()));
            appointment.setDescription("EMAILNET-35198 Ability to add Java event to Secondary Calendar of Office 365");

            // List subfolders and get the URI for the new calendar folder created earlier
            String newCalendarFolderUri = client.listSubFolders(client.getMailboxInfo().getCalendarUri()).get_Item(0).getUri();

            // Create appointment in the specified calendar folder
            client.createAppointment(appointment, newCalendarFolderUri);
        } finally {
            if (client != null)
                client.dispose();
        }
    }
}
```
**Explanation:** يبني هذا الكود كائن `Appointment`، يحدد منطقته الزمنية، يضيف الحضور، ويخزنه في مجلد التقويم المخصص.

## تحديث الموعد
**Overview:** تعديل خصائص موعد موجود، مثل الموقع أو الموضوع.

### الخطوة 4: تعريف الموعد الموجود
```java
import com.aspose.email.Appointment;

public class UpdateAppointment {
    public static void main(String[] args) {
        IEWSClient client = null;
        try {
            // Connect to Exchange Server (Replace with actual credentials)
            client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "username", "password");

            // Setup appointment details for existing appointment
            Appointment appointment = new Appointment();
            appointment.setLocation("Room 122");

            // Specify the URI of the calendar folder where the appointment exists
            String newCalendarFolderUri = "YOUR_DOCUMENT_DIRECTORY";

            // Update the location of the existing appointment
            client.updateAppointment(appointment, newCalendarFolderUri);
        } finally {
            if (client != null)
                client.dispose();
        }
    }
}
```
**Explanation:** استبدل `"YOUR_DOCUMENT_DIRECTORY"` بالمسار الفعلي لمجلد URI للموعد الذي ترغب في تحديثه. يوضح هذا المقتطف كيفية تغيير حقل الموقع.

## المشكلات الشائعة والنصائح
- **Authentication errors:** تحقق من أن الحساب لديه وصول EWS وأن المصادقة متعددة العوامل معطلة أو تم استخدام كلمة مرور تطبيق.  
- **Folder URI not found:** استخدم `client.listSubFolders()` لاكتشاف URI التقويم الصحيح قبل إنشاء أو تحديث العناصر.  
- **Time‑zone mismatches:** دائمًا قم بتعيين المنطقة الزمنية على كائن `Appointment` لتجنب مفاجآت التوقيت الصيفي.  

## الأسئلة المتكررة

**س: هل أحتاج إلى ترخيص للتطوير؟**  
ج: النسخة التجريبية تعمل للتطوير والاختبار، لكن الترخيص الكامل مطلوب للنشر في الإنتاج.

**س: هل يمكنني استخدام هذا مع Exchange في الموقع؟**  
ج: نعم. فقط قم بتغيير عنوان URL الخاص بـ EWS للإشارة إلى خادمك في الموقع.

**س: هل يدعم Java 8؟**  
ج: المكتبة تدعم JDK 16 وما بعده؛ لا يُنصح باستخدام إصدارات JDK أقدم للنسخة الأخيرة.

**س: كيف أحذف موعدًا؟**  
ج: استخدم `client.deleteAppointment(appointmentId, calendarFolderUri);` بعد الحصول على المعرف الفريد للموعد.

**س: ماذا لو احتجت إلى التعامل مع الاجتماعات المتكررة؟**  
ج: توفر Aspose.Email فئة `Recurrence` التي يمكنك إرفاقها بـ `Appointment` قبل الحفظ.

---

**آخر تحديث:** 2026-01-04  
**تم الاختبار مع:** Aspose.Email for Java 25.4 (jdk16 classifier)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}