---
"date": "2025-05-29"
"description": "تعرّف على كيفية إدارة خصائص متعددة بكفاءة في رسائل MAPI باستخدام Aspose.Email لـ Java. يتناول هذا الدليل إعداد أنواع float وdouble وlong وغيرها."
"title": "تعيين خصائص MAPI متعددة في Java باستخدام Aspose.Email - دليل شامل"
"url": "/ar/java/mapi-operations/aspose-email-java-set-mapi-properties/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# تعيين خصائص MAPI متعددة في Java باستخدام Aspose.Email: دليل شامل

## مقدمة

إدارة خصائص رسائل MAPI بفعالية أمرٌ بالغ الأهمية لتحسين تطبيقات Java. باستخدام Aspose.Email لـ Java، يمكنك ضبط خصائص متعددة، مثل float وdouble وlong وshort وboolean وcustom، بسلاسة. سيشرح لك هذا الدليل طرقًا مختلفة لتحقيق ذلك.

**ما سوف تتعلمه:**
- تعيين خصائص متعددة في رسائل MAPI باستخدام Aspose.Email Java
- فهم أنواع الممتلكات المختلفة واستخداماتها
- أمثلة عملية على التعليمات البرمجية للتنفيذ

دعونا نبدأ بتغطية المتطلبات الأساسية.

## المتطلبات الأساسية

للمتابعة، تأكد من أن لديك:
- **مجموعة تطوير Java (JDK):** تم تثبيت JDK 8 أو إصدار أحدث.
- **مكتبة Aspose.Email:** يوصى بالإصدار 25.4.
- **إعداد Maven:** يجب تكوين Maven في IDE الخاص بك لإدارة التبعيات.

### المكتبات المطلوبة

قم بتضمين Aspose.Email كتبعية في `pom.xml`:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### الحصول على الترخيص
- **نسخة تجريبية مجانية:** ابدأ بإصدار تجريبي مجاني لاستكشاف الميزات.
- **رخصة مؤقتة:** احصل على الاختبار الموسع دون قيود.
- **شراء:** فكر في الشراء إذا كان يناسب احتياجاتك.

## إعداد Aspose.Email لـ Java

تأكد من تكوين Aspose.Email بشكل صحيح في بيئة التطوير الخاصة بك:
1. **استيراد التبعيات:** حل تبعيات Maven.
2. **مجموعة الترخيص:**
   - تنزيل ملف الترخيص من [أسبوزي](https://purchase.aspose.com/buy).
   - قم بتطبيقه باستخدام:
     ```java
     com.aspose.email.License license = new com.aspose.email.License();
     license.setLicense("path/to/your/license.lic");
     ```

بعد اكتمال عملية الإعداد، دعنا نستكشف كيفية تعيين خصائص مختلفة.

## دليل التنفيذ

### تعيين خصائص تعويم متعددة

يتيح ضبط خصائص التعويم تخزين البيانات الرقمية بكفاءة:

#### ملخص
تُظهر هذه الميزة كيفية إضافة قيم متعددة عائمة كخصائص رسالة MAPI باستخدام Aspose.Email لـ Java.

#### خطوات
1. **إنشاء الرسالة وتهيئتها**
   ```java
   import java.util.ArrayList;
   import com.aspose.email.MapiMessage;
   import com.aspose.email.MapiProperty;
   import com.aspose.email.system.collections.IList;

   MapiMessage msg = new MapiMessage();
   ```
2. **إضافة قيم عائمة إلى قائمة**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((float) 1);
   values.addItem((float) 2);
   ```
3. **تعيين الخاصية باستخدام معرف فريد**
   ```java
   msg.setProperty(new MapiProperty(0x23901004, values));
   ```
*توضيح:* علامة الملكية `0x23901004` يحدد مجموعة خصائص التعويم هذه.

### تعيين خصائص مزدوجة متعددة

تخزن الخصائص المزدوجة أرقامًا عائمة عالية الدقة:

#### ملخص
يوضح هذا القسم تخزين قيم مزدوجة متعددة كخصائص رسالة MAPI.

#### خطوات
1. **تهيئة الرسالة**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **ملء القيم المزدوجة**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((double) 1);
   values.addItem((double) 2);
   ```
3. **تعيين إلى علامة الخاصية**
   ```java
   msg.setProperty(new MapiProperty(0x23901005, values));
   ```

### تعيين خصائص APPTIME المتعددة

تخزن خصائص APPTIME فترات الوقت بكفاءة:

#### ملخص
توضح هذه الميزة استخدام أرقام ذات دقة مزدوجة لتمثيل الوقت.

#### خطوات
1. **إنشاء كائن الرسالة**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **إضافة قيم الوقت**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem(30456.34);
   values.addItem(40655.45);
   ```
3. **تعيين الخاصية**
   ```java
   msg.setProperty(new MapiProperty(0x23901007, values));
   ```

### تعيين خصائص طويلة متعددة

الخصائص الطويلة مثالية للأعداد الصحيحة الكبيرة:

#### ملخص
ترتكز هذه الميزة على تعيين قيم عددية صحيحة طويلة متعددة في رسالة.

#### خطوات
1. **تهيئة رسالة MAPI**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **إضافة قيم طويلة**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((long) 30456);
   values.addItem((long) 40655);
   ```
3. **تعريف علامة الخاصية**
   ```java
   msg.setProperty(new MapiProperty(0x23901014, values));
   ```

### تعيين خصائص قصيرة متعددة

تخزن الخصائص القصيرة بيانات الأعداد الصحيحة الصغيرة بكفاءة:

#### ملخص
يوضح هذا الدليل كيفية تعيين الأعداد الصحيحة القصيرة كخصائص للرسالة.

#### خطوات
1. **تهيئة الرسالة**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **إضافة قيم قصيرة**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((short) 1);
   values.addItem((short) 2);
   ```
3. **تعيين علامة الخاصية**
   ```java
   msg.setProperty(new MapiProperty(0x23901002, values));
   ```

### تعيين خصائص منطقية متعددة

تخزن الخصائص المنطقية الحالات الصحيحة/الخاطئة:

#### ملخص
تعرف على كيفية تعيين قيم منطقية متعددة في رسالة.

#### خطوات
1. **إنشاء كائن الرسالة**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **إضافة قيم منطقية**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem(true);
   values.addItem(false);
   ```
3. **تعيين الخاصية باستخدام المعرف**
   ```java
   msg.setProperty(new MapiProperty(0x2390100b, values));
   ```

### تعيين خاصية Null

قد يكون من المفيد تعيين خاصية بشكل صريح على أنها null:

#### ملخص
يوضح هذا القسم كيفية تعيين قيمة فارغة لخاصية.

#### خطوات
1. **تهيئة الرسالة**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **تعيين خاصية فارغة**
   ```java
   msg.setProperty(new MapiProperty(0x67400001, new byte[1]));
   ```

### إعداد خاصية طويلة مسماة بمعرف مخصص وUUID

بالنسبة للسيناريوهات المعقدة، قم بتعيين الخصائص المسماة:

#### ملخص
تُظهر هذه الميزة إعداد خاصية طويلة باستخدام معرف مخصص وUUID.

#### خطوات
1. **تهيئة الرسالة**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **إضافة قيم طويلة**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((int) 4);
   UUID uuid = UUID.randomUUID();
   ```
3. **إنشاء وتعيين الممتلكات على الخريطة**
   ```java
   MapiProperty property = new MapiProperty(msg.getNamedPropertyMapping().getNextAvailablePropertyId(com.aspose.email.MapiPropertyType.PT_MV_LONG), values);
   msg.getNamedPropertyMapping().addNamedPropertyMapping(property, (long) 0x00008028, uuid);
   msg.setProperty(property);
   ```

### تعيين خاصية مخصصة بالاسم

يمكن تسمية الخصائص المخصصة لتسهيل التعرف عليها:

#### ملخص
يوضح هذا الدليل كيفية إعداد الخصائص ذات الأسماء المخصصة.

#### خطوات
1. **تهيئة كائن الرسالة**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **تعريف خاصية مخصصة**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem("Custom Value");
   UUID uuid = UUID.randomUUID();
   
   MapiProperty property = new MapiProperty(msg.getNamedPropertyMapping().getNextAvailablePropertyId(com.aspose.email.MapiPropertyType.PT_STRING), values);
   msg.getNamedPropertyMapping().addNamedPropertyMapping(property, "CustomName", uuid);
   ```

### تعيين الخصائص والتحقق من صحتها

إن التأكد من تعيين الخصائص بشكل صحيح أمر بالغ الأهمية:

#### ملخص
يغطي هذا القسم إعداد وتأكيد خصائص متعددة في رسائل MAPI.

#### خطوات
1. **تعيين الخاصية**
   اتبع الأمثلة السابقة لتعيين خاصية.
2. **التحقق من صحة الملكية**
   ```java
   if (msg.getProperties().containsKey(0x23901004)) {
       System.out.println("Property is set correctly.");
   } else {
       System.err.println("Property setting failed.");
   }
   ```

## خاتمة

يقدم هذا الدليل نهجًا شاملاً لإدارة خصائص متعددة في رسائل MAPI باستخدام Aspose.Email لـ Java. باتباع هذه الخطوات، يمكنك تخزين وإدارة أنواع بيانات مختلفة بكفاءة ضمن تطبيقاتك.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}