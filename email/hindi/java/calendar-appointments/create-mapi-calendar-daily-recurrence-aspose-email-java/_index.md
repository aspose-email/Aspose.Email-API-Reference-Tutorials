---
date: '2026-09-17'
description: Outlook calendar java को daily recurrence और exceptions के साथ कैसे बनाएँ,
  और Aspose.Email for Java का उपयोग करके calendar को PST में सहेजें, यह सीखें।
keywords:
- create outlook calendar
- outlook calendar daily recurrence
- java calendar exceptions
- Aspose.Email Java
- MAPI PST generation
lastmod: '2026-09-17'
og_description: Aspose.Email का उपयोग करके Java में Outlook calendar बनाएँ। दैनिक
  पुनरावृत्ति, exception handling, और PST में सहेजने के बारे में चरण‑दर‑चरण गाइड में
  सीखें।
og_image_alt: Code example creating Outlook calendar with recurrence and PST export
  using Aspose.Email for Java
og_title: Java में Outlook calendar को daily recurrence और exceptions के साथ बनाएँ
schemas:
- author: Aspose
  dateModified: '2026-09-17'
  description: Learn how to create outlook calendar java with daily recurrence and
    exceptions, and save calendar to PST using Aspose.Email for Java.
  headline: Create outlook calendar java with daily recurrence and exceptions
  type: TechArticle
- questions:
  - answer: Yes, you can set the `StartTimeZone` and `EndTimeZone` properties on `MapiCalendar`.
    question: Does the library support time‑zone aware appointments?
  - answer: Use the `DeletedInstanceDates` collection on the recurrence pattern to
      mark specific dates as removed.
    question: Can I programmatically delete a single occurrence from a recurring series?
  - answer: PST files follow the Unicode format limits (up to 2 GB by default), but
      you can configure larger sizes via `PersonalStorage` settings.
    question: Are there limits on the size of a PST file created with Aspose.Email?
  - answer: Create `MapiRecipient` objects, set their `RecipientType` to `MapiRecipientType.MAPI_TO`,
      and add them to the `Recipients` collection of the `MapiMessage`.
    question: How do I add attendees to a meeting request?
  - answer: Yes, Aspose.Email also provides `MapiTask` with similar recurrence capabilities.
    question: Is there support for recurring tasks (not just appointments)?
  type: FAQPage
tags:
- outlook calendar
- Aspose.Email
- Java scheduling
- PST file
title: Outlook calendar java को daily recurrence और exceptions के साथ बनाएँ
url: /hi/java/calendar-appointments/create-mapi-calendar-daily-recurrence-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Outlook कैलेंडर जावा को दैनिक पुनरावृत्ति और अपवादों के साथ बनाएं

पुनरावर्ती घटनाओं का प्रभावी प्रबंधन चुनौतीपूर्ण हो सकता है, विशेष रूप से जब आपको एक **outlook calendar java** की आवश्यकता हो जो दैनिक पुनरावृत्ति पैटर्न और कभी‑कभी अपवादों का समर्थन करता हो। इस ट्यूटोरियल में आप सीखेंगे कि Outlook calendar Java ऑब्जेक्ट्स कैसे बनाएं, दैनिक पुनरावृत्ति को कॉन्फ़िगर करें, अपवाद उदाहरण जोड़ें, और अंत में Aspose.Email for Java का उपयोग करके **save calendar to PST** करें। अंत तक आपके पास एक पुन: उपयोग योग्य कोड स्निपेट होगा जिसे आप किसी भी Java‑आधारित शेड्यूलिंग सेवा में डाल सकते हैं।

## त्वरित उत्तर
- **कौन सी लाइब्रेरी?** Aspose.Email for Java  
- **मुख्य कार्य?** Create an Outlook calendar Java with daily recurrence and exceptions  
- **पूर्वापेक्षित JDK?** Java 16 or higher  
- **क्या मैं अपवादों में फ़ाइलें संलग्न कर सकता हूँ?** Yes, using `MapiCalendarExceptionInfo`  
- **कैलेंडर कहाँ संग्रहीत है?** In a PST file via `PersonalStorage`  

## Outlook कैलेंडर जावा क्या है?
Outlook calendar Java ऑब्जेक्ट एक प्रोग्रामेटिक प्रतिनिधित्व है Outlook अपॉइंटमेंट का, जो MAPI (Messaging Application Programming Interface) विनिर्देश पर आधारित है, जिसमें विषय, स्थान, प्रारंभ/समाप्ति समय, पुनरावृत्ति नियम, उपस्थित लोग, और संलग्नक जैसी विशेषताएँ शामिल हैं। इस ऑब्जेक्ट को हेरफेर, सीरियलाइज़ और PST फ़ाइलों में संग्रहीत किया जा सकता है बिना Outlook की आवश्यकता के।

## Aspose.Email for Java का उपयोग क्यों करें?
Aspose.Email for Java आपको Outlook स्थापित किए बिना MAPI ऑब्जेक्ट्स के साथ काम करने देता है। लाइब्रेरी **50+ MAPI properties** का समर्थन करती है, सामान्य अपॉइंटमेंट डेटा के लिए **2 seconds** से कम समय में **2 GB** तक के Unicode PST फ़ाइलें उत्पन्न कर सकती है, और Java 16+ का समर्थन करने वाले किसी भी प्लेटफ़ॉर्म पर चलती है। यह शुद्ध‑Java दृष्टिकोण सर्वर‑साइड कैलेंडर निर्माण, स्वचालित मीटिंग श्रृंखला, और पुनरावृत्ति लॉजिक पर पूर्ण नियंत्रण सक्षम करता है।

## पूर्वापेक्षाएँ

शुरू करने से पहले सुनिश्चित करें कि आपके पास निम्न सेटअप है:
- **Aspose.Email Library**: Version 25.4 (or later) – available via Maven or direct download.  
- **Java Development Kit (JDK)**: JDK 16 or newer.  
- **IDE**: IntelliJ IDEA, Eclipse, NetBeans, or any Java‑compatible editor.

### आवश्यक लाइब्रेरी और निर्भरताएँ

Maven का उपयोग करके अपने प्रोजेक्ट में Aspose.Email को एकीकृत करने के लिए, अपने `pom.xml` में निम्न निर्भरता जोड़ें:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### लाइसेंस प्राप्ति

Aspose.Email का उपयोग करने के लिए आपको एक लाइसेंस चाहिए:
- **Free trial** – explore all features without cost.  
- **Temporary license** – request for extended evaluation.  
- **Full license** – purchase for production deployments.

## Aspose.Email for Java सेटअप करना

पहले, अपना वातावरण सेट करें:

1. Verify JDK 16 is installed and `JAVA_HOME` is configured.  
2. Add the Maven dependency (or download the JAR) to your project.  

यहाँ एक छोटा स्निपेट है जो दिखाता है कि लाइसेंस फ़ाइल कैसे लोड करें:

```java
import com.aspose.email.*;

public class InitializeAspose {
    public static void main(String[] args) {
        // Set up a license if available
        License license = new License();
        try {
            license.setLicense("path/to/your/license.lic");
        } catch (Exception e) {
            System.out.println("License not found, using trial version.");
        }
    }
}
```

## कार्यान्वयन गाइड

### दैनिक पुनरावृत्ति और अपवादों के साथ outlook calendar java बनाना

#### अवलोकन
यह फीचर आपको पुनरावर्ती अपॉइंटमेंट्स को स्वचालित करने देता है जबकि विशिष्ट घटनाओं को छोड़ने या संशोधित करने की क्षमता भी रखता है।

#### चरण‑दर‑चरण कार्यान्वयन

**1. Set up event start date**  
सीरीज़ कब शुरू होनी चाहिए, यह निर्धारित करें:

```java
Date startDate = addHours(newDate(2018, 7, 19), 12);
```

**2. Create the MAPI calendar object**  
`MapiCalendar` क्लास मेमोरी में एकल कैलेंडर आइटम का प्रतिनिधित्व करने वाला शीर्ष‑स्तरीय ऑब्जेक्ट है। स्थान, विषय, और विवरण प्रदान करें:

```java
MapiCalendar calendar = new MapiCalendar("location1", "summary1", "description1", startDate, addHours(startDate, 1));
```

**3. Define a daily recurrence pattern**  
`MapiCalendarRecurrencePattern` क्लास वह नियम संग्रहीत करती है जो अपॉइंटमेंट को हर दिन दोहराता है। इवेंट को हर दिन दोहराने के लिए कॉन्फ़िगर करें:

```java
MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
MapiCalendarRecurrencePattern pattern = recurrence.getRecurrencePattern();

pattern.setPatternType(MapiCalendarRecurrencePatternType.Day);
pattern.setPeriod(1); // Daily
pattern.setEndType(MapiCalendarRecurrenceEndType.NeverEnd);
```

**4. Add an exception to the recurrence**  
`MapiCalendarExceptionInfo` एकल घटना का वर्णन करता है जो पैटर्न से भिन्न होती है—या तो बाहर रखी गई या बदली हुई। वह तिथि निर्दिष्ट करें जिसे बाहर रखा जाना चाहिए (या बदला जाना चाहिए):

```java
Date exceptionDate = addDays(startDate, 3);

MapiCalendarExceptionInfo exception = new MapiCalendarExceptionInfo();
exception.setLocation("exceptionLocation");
exception.setSubject("exceptionSubject");
exception.setBody("exceptionBody");

exception.setOriginalStartDate(exceptionDate);
exception.setStartDateTime(exceptionDate);
exception.setEndDateTime(addHours(exceptionDate, 5));

pattern.getExceptions().addItem(exception);
pattern.getModifiedInstanceDates().addItem(exceptionDate);
pattern.getDeletedInstanceDates().addItem(exceptionDate);

calendar.setRecurrence(recurrence);
```

### कैलेंडर अपवादों में फ़ाइलें संलग्न करना

#### अवलोकन
आप किसी भी अपवाद उदाहरण में सहायक दस्तावेज़ (जैसे, एजेंडा) संलग्न कर सकते हैं।

**1. Create and attach a file**

```java
MapiCalendarExceptionInfo exception = new MapiCalendarExceptionInfo();
exception.getAttachments().add("file.txt", "hello, world!".getBytes());
```

## outlook calendar java को PST में सहेजना (save calendar to pst)

#### अवलोकन
कैलेंडर को PST फ़ाइल में स्थायी बनाएं ताकि Outlook या अन्य क्लाइंट इसे पढ़ सकें।

**1. Create and save calendar to PST**  
`PersonalStorage` क्लास नई PST फ़ाइल बनाने और MAPI आइटम्स को उसमें जोड़ने के लिए मेथड्स प्रदान करती है।

```java
final PersonalStorage pst = PersonalStorage.create(new ByteArrayOutputStream(), FileFormatVersion.Unicode);
try {
    FolderInfo calendarFolder = pst.createPredefinedFolder("Calendar", StandardIpmFolder.Appointments);
    calendarFolder.addMapiMessageItem(calendar);
} finally {
    pst.dispose();
}
```

## व्यावहारिक अनुप्रयोग
- **Corporate scheduling** – automate meeting series, automatically skipping holidays.  
- **Project management** – track recurring milestones with occasional date shifts.  
- **Event planning** – manage multi‑day conferences where some sessions are cancelled or rescheduled.

### एकीकरण संभावनाएँ
Aspose.Email को CRM प्लेटफ़ॉर्म, टास्क‑मैनेजमेंट APIs, या कस्टम वर्कफ़्लो इंजिन के साथ मिलाकर एंड‑टू‑एंड ऑटोमेशन चलाएँ।

## प्रदर्शन संबंधी विचार
- **Dispose resources** – always call `dispose()` on `PersonalStorage` to free file handles.  
- **Stream usage** – prefer `ByteArrayOutputStream` or file streams to avoid loading entire PSTs into memory.  
- **Async operations** – for bulk calendar generation, run the creation logic on a background thread to keep UI responsive.

## निष्कर्ष
इस गाइड का पालन करके आप अब जानते हैं कि **create outlook calendar java** ऑब्जेक्ट्स को दैनिक पुनरावृत्ति के साथ कैसे बनाएं, अपवाद जोड़ें, फ़ाइलें संलग्न करें, और **save calendar to PST** करें। ये क्षमताएँ आपको Outlook को सीधे छुए बिना मजबूत शेड्यूलिंग फीचर्स बनाने देती हैं।

### अगले कदम
- साप्ताहिक या मासिक पुनरावृत्ति पैटर्न के साथ प्रयोग करें।  
- उपस्थित लोग, रिमाइंडर, और श्रेणियों जैसे अतिरिक्त MAPI properties का अन्वेषण करें।  
- अधिक उन्नत परिदृश्यों के लिए Aspose.Email की व्यापक API दस्तावेज़ीकरण देखें।

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या लाइब्रेरी टाइम‑ज़ोन aware अपॉइंटमेंट्स का समर्थन करती है?**  
A: हाँ, आप `MapiCalendar` पर `StartTimeZone` और `EndTimeZone` प्रॉपर्टीज़ सेट कर सकते हैं।

**Q: क्या मैं प्रोग्रामेटिक रूप से पुनरावर्ती श्रृंखला से एकल घटना को हटा सकता हूँ?**  
A: पुनरावृत्ति पैटर्न पर `DeletedInstanceDates` कलेक्शन का उपयोग करके विशिष्ट तिथियों को हटाए गए के रूप में चिह्नित करें।

**Q: क्या Aspose.Email द्वारा बनाई गई PST फ़ाइल के आकार पर कोई सीमा है?**  
A: PST फ़ाइलें Unicode फ़ॉर्मेट सीमाओं (डिफ़ॉल्ट रूप से 2 GB तक) का पालन करती हैं, लेकिन आप `PersonalStorage` सेटिंग्स के माध्यम से बड़े आकार कॉन्फ़िगर कर सकते हैं।

**Q: मीटिंग अनुरोध में उपस्थित लोगों को कैसे जोड़ूँ?**  
A: `MapiRecipient` ऑब्जेक्ट्स बनाएं, उनका `RecipientType` `MapiRecipientType.MAPI_TO` पर सेट करें, और उन्हें `MapiMessage` के `Recipients` कलेक्शन में जोड़ें।

**Q: क्या केवल अपॉइंटमेंट्स नहीं, बल्कि पुनरावर्ती टास्क्स का भी समर्थन है?**  
A: हाँ, Aspose.Email `MapiTask` भी प्रदान करता है जिसमें समान पुनरावृत्ति क्षमताएँ हैं।

**Q: क्या मैं इस गाइड को Aspose.Email Java ट्यूटोरियल श्रृंखला का हिस्सा बना सकता हूँ?**  
A: बिल्कुल – यहाँ दिखाए गए कदम किसी भी Aspose.Email Java ट्यूटोरियल का मुख्य भाग हैं जो कैलेंडर निर्माण से संबंधित है।

## संसाधन
- [Aspose.Email for Java दस्तावेज़ीकरण](https://reference.aspose.com/email/java/)
- [Aspose.Email डाउनलोड करें](https://releases.aspose.com/email/java/)
- [लाइसेंस खरीदें](https://purchase.aspose.com/buy)
- [नि:शुल्क ट्रायल संस्करण](https://releases.aspose.com/email/java/)
- [अस्थायी लाइसेंस का अनुरोध करें](https://purchase.aspose.com/temporary-license/)
- [Aspose समर्थन फ़ोरम](https://forum.aspose.com/c/email/10)

---

**Last updated:** 2026-09-17  
**Tested with:** Aspose.Email for Java 25.4 (JDK 16)  
**Author:** Aspose

## संबंधित ट्यूटोरियल

- [Aspose.Email – Java के साथ Outlook कैलेंडर PST निर्यात करें](/email/java/calendar-appointments/create-save-mapi-calendar-aspose-email-java/)
- [Aspose.Email का उपयोग करके Java में कैलेंडर आइटम बनाना](/email/java/calendar-appointments/create-save-calendar-items-aspose-email-java/)
- [Aspose.Email for Java के साथ कैलेंडर शेयरिंग निमंत्रण बनाना](/email/java/calendar-appointments/create-send-calendar-invitations-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}