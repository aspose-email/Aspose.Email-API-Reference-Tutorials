---
date: '2026-03-20'
description: जानेँ कि कैसे Outlook कैलेंडर जावा को दैनिक पुनरावृत्ति और अपवादों के
  साथ बनाएं, और Aspose.Email for Java का उपयोग करके कैलेंडर को PST में सहेजें।
keywords:
- MAPI Calendar creation
- daily recurrence events
- Java calendar exceptions
title: आउटलुक कैलेंडर जावा बनाएं दैनिक पुनरावृत्ति और अपवादों के साथ
url: /hi/java/calendar-appointments/create-mapi-calendar-daily-recurrence-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Outlook calendar java को दैनिक पुनरावृत्ति और अपवादों के साथ कैसे बनाएं

पुनरावृत्त घटनाओं का प्रभावी प्रबंधन चुनौतीपूर्ण हो सकता है, विशेष रूप से जब आपको एक **outlook calendar java** की आवश्यकता हो जो दैनिक पुनरावृत्ति पैटर्न और कभी‑कभी अपवादों का समर्थन करता हो। इस ट्यूटोरियल में आप सीखेंगे कि Outlook calendar Java ऑब्जेक्ट्स कैसे बनाएं, दैनिक पुनरावृत्ति को कॉन्फ़िगर करें, अपवाद उदाहरण जोड़ें, और अंत में Aspose.Email for Java का उपयोग करके **save calendar to PST** करें। अंत तक आपके पास एक पुन: उपयोग योग्य कोड स्निपेट होगा जिसे आप किसी भी Java‑आधारित शेड्यूलिंग सेवा में डाल सकते हैं।

## त्वरित उत्तर
- **कौन सा लाइब्रेरी?** Aspose.Email for Java  
- **मुख्य कार्य?** दैनिक पुनरावृत्ति और अपवादों के साथ Outlook calendar Java बनाएं  
- **पूर्वापेक्षित JDK?** Java 16 या उससे ऊपर  
- **क्या मैं अपवादों में फ़ाइलें संलग्न कर सकता हूँ?** Yes, using `MapiCalendarExceptionInfo`  
- **कैलेंडर कहाँ संग्रहीत है?** In a PST file via `PersonalStorage`

## Outlook calendar java क्या है?
एक Outlook calendar Java ऑब्जेक्ट (जो MAPI कैलेंडर के रूप में लागू किया गया है) Microsoft Outlook अपॉइंटमेंट्स के समान मानकों का पालन करता है। यह समृद्ध पुनरावृत्ति नियम, अपवाद प्रबंधन, उपस्थितियों और संलग्नकों को संग्रहीत करता है, जिससे यह एंटरप्राइज़‑ग्रेड शेड्यूलिंग के लिए उपयुक्त बनता है।

## Aspose.Email for Java का उपयोग क्यों करें?
Aspose.Email एक शुद्ध‑Java API प्रदान करता है जो आपको Outlook स्थापित किए बिना MAPI ऑब्जेक्ट्स के साथ काम करने देता है। यह **aspose email tutorial java** दृष्टिकोण सर्वर‑साइड PST फ़ाइलों की जनरेशन, स्वचालित मीटिंग सीरीज़, और पुनरावृत्ति लॉजिक पर पूर्ण नियंत्रण सक्षम करता है।

## पूर्वापेक्षाएँ
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित सेटअप है:

- **Aspose.Email Library**: Version 25.4 (या बाद) – Maven या सीधे डाउनलोड के माध्यम से उपलब्ध।  
- **Java Development Kit (JDK)**: JDK 16 या नया।  
- **IDE**: IntelliJ IDEA, Eclipse, NetBeans, या कोई भी Java‑compatible एडिटर।

### आवश्यक लाइब्रेरी और निर्भरताएँ
Maven का उपयोग करके Aspose.Email को अपने प्रोजेक्ट में एकीकृत करने के लिए, अपने `pom.xml` में निम्नलिखित निर्भरता जोड़ें:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### लाइसेंस प्राप्ति
Aspose.Email का उपयोग करने के लिए, आपको एक लाइसेंस चाहिए:

- **Free Trial** – बिना लागत के सभी सुविधाओं का अन्वेषण करें।  
- **Temporary License** – विस्तारित मूल्यांकन के लिए अनुरोध करें।  
- **Full License** – उत्पादन परिनियोजन के लिए खरीदें।

## Aspose.Email for Java की सेटअप
पहले, अपना पर्यावरण सेट करें:

1. जाँचें कि JDK 16 स्थापित है और `JAVA_HOME` कॉन्फ़िगर किया गया है।  
2. Maven निर्भरता (या JAR डाउनलोड) को अपने प्रोजेक्ट में जोड़ें।  

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

### दैनिक पुनरावृत्ति और अपवादों के साथ Outlook calendar java बनाना

#### अवलोकन
यह सुविधा आपको पुनरावृत्त अपॉइंटमेंट्स को स्वचालित करने देती है जबकि विशिष्ट घटनाओं को छोड़ने या संशोधित करने की क्षमता भी रखती है।

#### चरण‑दर‑चरण कार्यान्वयन

**1. इवेंट प्रारंभ तिथि सेट करें**  
निर्धारित करें कि श्रृंखला कब शुरू होनी चाहिए:

```java
Date startDate = addHours(newDate(2018, 7, 19), 12);
```

**2. MAPI कैलेंडर ऑब्जेक्ट बनाएं**  
स्थान, विषय, और विवरण प्रदान करें:

```java
MapiCalendar calendar = new MapiCalendar("location1", "summary1", "description1", startDate, addHours(startDate, 1));
```

**3. दैनिक पुनरावृत्ति पैटर्न परिभाषित करें**  
इवेंट को हर दिन दोहराने के लिए कॉन्फ़िगर करें:

```java
MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
MapiCalendarRecurrencePattern pattern = recurrence.getRecurrencePattern();

pattern.setPatternType(MapiCalendarRecurrencePatternType.Day);
pattern.setPeriod(1); // Daily
pattern.setEndType(MapiCalendarRecurrenceEndType.NeverEnd);
```

**4. पुनरावृत्ति में एक अपवाद जोड़ें**  
एक तिथि निर्दिष्ट करें जिसे बाहर रखा जाना चाहिए (या बदला जाना चाहिए):

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

**1. फ़ाइल बनाएं और संलग्न करें**

```java
MapiCalendarExceptionInfo exception = new MapiCalendarExceptionInfo();
exception.getAttachments().add("file.txt", "hello, world!".getBytes());
```

### Outlook calendar java को PST में सहेजना (save calendar to pst)

#### अवलोकन
कैलेंडर को PST फ़ाइल में सहेजें ताकि Outlook या अन्य क्लाइंट इसे पढ़ सकें।

**1. कैलेंडर बनाएं और PST में सहेजें**

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
- **Corporate Scheduling** – मीटिंग सीरीज़ को स्वचालित करें, छुट्टियों को स्वतः छोड़ें।  
- **Project Management** – कभी‑कभी तिथि परिवर्तन के साथ पुनरावृत्त माइलस्टोन ट्रैक करें।  
- **Event Planning** – मल्टी‑डे कॉन्फ्रेंस को प्रबंधित करें जहाँ कुछ सत्र रद्द या पुनर्निर्धारित होते हैं।

### एकीकरण संभावनाएँ
Aspose.Email को CRM प्लेटफ़ॉर्म, टास्क‑मैनेजमेंट API, या कस्टम वर्कफ़्लो इंजन के साथ मिलाकर एंड‑टू‑एंड ऑटोमेशन चलाएँ।

## प्रदर्शन संबंधी विचार
- **Dispose Resources** – फ़ाइल हैंडल्स को मुक्त करने के लिए हमेशा `PersonalStorage` पर `dispose()` कॉल करें।  
- **Stream Usage** – पूरी PST को मेमोरी में लोड करने से बचने के लिए `ByteArrayOutputStream` या फ़ाइल स्ट्रीम का उपयोग करें।  
- **Async Operations** – बड़े पैमाने पर कैलेंडर जनरेशन के लिए, निर्माण लॉजिक को बैकग्राउंड थ्रेड पर चलाएँ ताकि UI उत्तरदायी रहे।

## निष्कर्ष
इस गाइड का पालन करके अब आप जानते हैं कि **create outlook calendar java** ऑब्जेक्ट्स को दैनिक पुनरावृत्ति के साथ कैसे बनाएं, अपवाद जोड़ें, फ़ाइलें संलग्न करें, और **save calendar to PST**। ये क्षमताएँ आपको Outlook को सीधे छुए बिना मजबूत शेड्यूलिंग फीचर बनाने देती हैं।

### अगले कदम
- साप्ताहिक या मासिक पुनरावृत्ति पैटर्न के साथ प्रयोग करें।  
- उपस्थितियों, रिमाइंडर्स, और श्रेणियों जैसे अतिरिक्त MAPI प्रॉपर्टीज़ का अन्वेषण करें।  
- अधिक उन्नत परिदृश्यों के लिए Aspose.Email की व्यापक API दस्तावेज़ देखें।

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या लाइब्रेरी टाइम‑ज़ोन जागरूक अपॉइंटमेंट्स का समर्थन करती है?**  
A: हाँ, आप `MapiCalendar` पर `StartTimeZone` और `EndTimeZone` प्रॉपर्टीज़ सेट कर सकते हैं।

**Q: क्या मैं प्रोग्रामेटिक रूप से पुनरावृत्ति श्रृंखला से एकल घटना को हटा सकता हूँ?**  
A: पुनरावृत्ति पैटर्न पर `DeletedInstanceDates` संग्रह का उपयोग करके विशिष्ट तिथियों को हटाए गए के रूप में चिह्नित करें।

**Q: क्या Aspose.Email द्वारा निर्मित PST फ़ाइल के आकार पर कोई सीमा है?**  
A: PST फ़ाइलें Unicode फ़ॉर्मेट सीमाओं (डिफ़ॉल्ट रूप से 2 GB तक) का पालन करती हैं, लेकिन आप `PersonalStorage` सेटिंग्स के माध्यम से बड़े आकार कॉन्फ़िगर कर सकते हैं।

**Q: मीटिंग अनुरोध में उपस्थितियों को कैसे जोड़ें?**  
A: `MapiRecipient` ऑब्जेक्ट बनाएं, उनका `RecipientType` `MapiRecipientType.MAPI_TO` सेट करें, और उन्हें `MapiMessage` के `Recipients` संग्रह में जोड़ें।

**Q: क्या पुनरावृत्त कार्यों (केवल अपॉइंटमेंट्स नहीं) के लिए समर्थन है?**  
A: हाँ, Aspose.Email समान पुनरावृत्ति क्षमताओं के साथ `MapiTask` भी प्रदान करता है।

**Q: क्या मैं इस गाइड को aspose email tutorial java श्रृंखला का हिस्सा बना सकता हूँ?**  
A: बिल्कुल – यहाँ दिखाए गए चरण किसी भी Aspose.Email Java ट्यूटोरियल का मुख्य भाग हैं जो कैलेंडर निर्माण से संबंधित है।

## संसाधन
- [Aspose.Email for Java दस्तावेज़ीकरण](https://reference.aspose.com/email/java/)
- [Aspose.Email डाउनलोड करें](https://releases.aspose.com/email/java/)
- [लाइसेंस खरीदें](https://purchase.aspose.com/buy)
- [नि:शुल्क ट्रायल संस्करण](https://releases.aspose.com/email/java/)
- [अस्थायी लाइसेंस का अनुरोध करें](https://purchase.aspose.com/temporary-license/)
- [Aspose सपोर्ट फ़ोरम](https://forum.aspose.com/c/email/10)

---

**अंतिम अपडेट:** 2026-03-20  
**परीक्षण किया गया:** Aspose.Email for Java 25.4 (JDK 16)  
**लेखक:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}