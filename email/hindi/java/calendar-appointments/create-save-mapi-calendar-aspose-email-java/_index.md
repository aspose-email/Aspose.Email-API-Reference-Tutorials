---
date: '2026-01-01'
description: Aspose.Email for Java का उपयोग करके MAPI कैलेंडर जावा कैसे बनाएं और कैलेंडर
  को PST में सहेजें, यह सीखें। कोड, आवर्ती घटनाएँ और प्राप्तकर्ताओं के साथ चरण‑दर‑चरण
  गाइड।
keywords:
- Create MAPI Calendar Java
- Aspose.Email Java Calendar
- Java PST File Save
title: Aspose.Email के साथ Java में MAPI कैलेंडर कैसे बनाएं – कैलेंडर को PST में सहेजें
url: /hi/java/calendar-appointments/create-save-mapi-calendar-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Email के साथ MAPI calendar java कैसे बनाएं – कैलेंडर को PST में सहेजें

## परिचय

क्या आप अपने जावा अनुप्रयोगों में कैलेंडर ऑटोमेशन को सरल बनाना चाहते हैं? **Aspose.Email for Java** के साथ, आप **create MAPI calendar java** आइटम बना सकते हैं, पुनरावृत्ति पैटर्न निर्धारित कर सकते हैं, उपस्थितियों को जोड़ सकते हैं, और **save calendar to PST** फ़ाइलों को कुछ ही कोड लाइनों से सहेज सकते हैं। यह ट्यूटोरियल आपको पूरी प्रक्रिया के माध्यम से ले जाता है—लाइब्रेरी सेटअप से लेकर एक पूर्ण कार्यात्मक कैलेंडर एंट्री बनाने तक, जो वितरण के लिए तैयार हो।  
### आप क्या सीखेंगे
- Aspose.Email का उपयोग करके **create MAPI calendar java** इवेंट्स कैसे बनाएं।  
- दैनिक, साप्ताहिक, या कस्टम पुनरावृत्ति पैटर्न को कॉन्फ़िगर करना।  
- अपने कैलेंडर निमंत्रण में प्राप्तकर्ताओं (आयोजक, उपस्थितियों) को जोड़ना।  
- Outlook संगतता के लिए कैलेंडर आइटम को **save calendar to PST** करके स्थायी बनाना।  

आइए शुरू करें और अपना विकास वातावरण तैयार करें।

## त्वरित उत्तर
- **कौनसी लाइब्रेरी?** Aspose.Email for Java  
- **मुख्य लक्ष्य?** MAPI calendar java बनाना और **save calendar to PST**  
- **पूर्वापेक्षाएँ?** Java 8+, Maven, Aspose.Email लाइसेंस  
- **सामान्य कार्यान्वयन समय?** बुनियादी इवेंट के लिए 10‑15 मिनट  
- **क्या मैं पुनरावृत्ति जोड़ सकता हूँ?** हाँ – दैनिक, साप्ताहिक, मासिक, आदि।

## जावा में MAPI कैलेंडर क्या है?
एक MAPI (Messaging Application Programming Interface) कैलेंडर ऑब्जेक्ट Outlook‑संगत मीटिंग या अपॉइंटमेंट को दर्शाता है। Aspose.Email का उपयोग करके, आप इन ऑब्जेक्ट्स को प्रोग्रामेटिकली बना सकते हैं, जिससे Exchange, Outlook, या किसी भी क्लाइंट के साथ सहज एकीकरण संभव हो जाता है जो PST फ़ाइलों का उपयोग करता है।

## कैलेंडर ऑटोमेशन के लिए Aspose.Email क्यों उपयोग करें?
- **पूर्ण Outlook संगतता** – उत्पन्न आइटम Outlook, OWA, और मोबाइल क्लाइंट्स में काम करते हैं।  
- **समृद्ध पुनरावृत्ति समर्थन** – दैनिक, साप्ताहिक, मासिक, और कस्टम पैटर्न बॉक्स से बाहर नहीं।  
- **कोई बाहरी निर्भरताएँ नहीं** – शुद्ध जावा लाइब्रेरी, कोई COM इंटरऑप आवश्यक नहीं।  
- **उच्च प्रदर्शन** – बड़े PST फ़ाइलों और बल्क ऑपरेशन्स को कुशलता से संभालता है।

## पूर्वापेक्षाएँ
शुरू करने से पहले, सुनिश्चित करें कि आपके पास है:

### आवश्यक लाइब्रेरीज़
- **Aspose.Email for Java**: संस्करण 25.4 या बाद का।

### पर्यावरण सेटअप आवश्यकताएँ
- IntelliJ IDEA या Eclipse जैसे जावा IDE।  
- निर्भरताओं को प्रबंधित करने के लिए Maven स्थापित हो।

### ज्ञान पूर्वापेक्षाएँ
- बुनियादी जावा प्रोग्रामिंग कौशल।  
- ऑब्जेक्ट‑ओरिएंटेड अवधारणाओं से परिचितता।

## Aspose.Email for Java सेटअप करना
`pom.xml` में Aspose.Email Maven निर्भरता जोड़ें:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### लाइसेंस प्राप्ति
Aspose.Email एक मुफ्त ट्रायल प्रदान करता है, लेकिन लाइसेंस सभी सुविधाओं को अनलॉक करता है:
- **Free Trial**: 30 दिनों के लिए बिना सीमाओं के परीक्षण।  
- **Temporary License**: यदि आपको अतिरिक्त समय चाहिए तो [Aspose की वेबसाइट](https://purchase.aspose.com/temporary-license/) से अनुरोध करें।  
- **Purchase**: [purchase page](https://purchase.aspose.com/buy) से स्थायी लाइसेंस खरीदें।

### बुनियादी आरंभिककरण
निर्भरता जोड़ने के बाद, अपनी लाइसेंस फ़ाइल के साथ लाइब्रेरी को आरंभ करें:

```java
com.aspose.email.License license = new com.aspose.email.License();
license.setLicense("path_to_your_license.lic");
```

## कार्यान्वयन गाइड
अब जब आप सेटअप हो गए हैं, चलिए **create MAPI calendar java** और **save calendar to PST** करते हैं।

### पुनरावृत्ति के साथ MAPI कैलेंडर बनाएं

#### सारांश
हम एक कैलेंडर इवेंट बनाएंगे, दैनिक पुनरावृत्ति लागू करेंगे, उपस्थितियों को जोड़ेंगे, और अंत में इसे PST फ़ाइल में सहेजेंगे।

#### चरण‑दर‑चरण कार्यान्वयन
1. **Initialize Date and Recurrence Pattern**  

   First, define the start time and set a daily recurrence:

   ```java
   import java.util.Date;

   // Add hours to current date to get the start time
   Date startDate = addHours(new Date(), 12);

   MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
   recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
   ```

   *Explanation*: `MapiCalendarEventRecurrence` पुनरावृत्ति विवरण रखता है; हम `MapiCalendarDailyRecurrencePattern` के माध्यम से दैनिक पैटर्न चुनते हैं।

2. **Set Up Recipients**  

   Add the people who should receive the meeting invitation:

   ```java
   import com.aspose.email.MapiRecipientCollection;
   import com.aspose.email.MapiRecipientType;

   MapiRecipientCollection recColl = new MapiRecipientCollection();
   recColl.add("recipient@gmail.com", "Attendee Name", MapiRecipientType.MAPI_TO);
   ```

   *Explanation*: `MapiRecipientCollection` प्रत्येक उपस्थित को संग्रहीत करता है; `MAPI_TO` उन्हें मुख्य प्राप्तकर्ता के रूप में चिह्नित करता है।

3. **Create the MAPI Calendar Item**  

   Build the calendar object with all required details:

   ```java
   import com.aspose.email.MapiCalendar;

   MapiCalendar calendar = new MapiCalendar(
       "Organizer Name", 
       "Meeting Subject", 
       "Meeting Location", 
       startDate, 
       addHours(startDate, 1), // End time is one hour after start
       "Event Description",
       recColl,
       recurrence
   );
   ```

   *Explanation*: कंस्ट्रक्टर में आयोजक, विषय, स्थान, प्रारंभ/समाप्ति समय, विवरण, प्राप्तकर्ता सूची, और पुनरावृत्ति की अपेक्षा होती है।

4. **Save to PST File**  

   Finally, persist the calendar by **save calendar to PST**:

   ```java
   import com.aspose.email.PersonalStorage;
   import com.aspose.email.FolderInfo;
   import com.aspose.email.StandardIpmFolder;

   PersonalStorage pst = PersonalStorage.create("calendar.pst", 0);
   FolderInfo calendarFolder = pst.createPredefinedFolder("Calendar", StandardIpmFolder.CALendars);

   // Save the MAPI Calendar item
   calendarFolder.addMapiMessageItem(calendar);
   ```

   *Explanation*: `PersonalStorage.create` एक नई PST फ़ाइल बनाता है, और `addMapiMessageItem` कैलेंडर एंट्री को "Calendar" फ़ोल्डर में डालता है।

### समस्या निवारण टिप्स
- लाइसेंस पथ सत्यापित करें; एक अमान्य लाइसेंस कार्यक्षमता को सीमित करेगा।  
- आमंत्रण विफलताओं से बचने के लिए प्राप्तकर्ता ईमेल पते सही रूप में हों, यह सुनिश्चित करें।  
- ऑपरेशन्स के बाद PST (`pst.dispose()`) बंद करें ताकि फ़ाइल हैंडल मुक्त हो सकें।

## व्यावहारिक अनुप्रयोग
यहाँ सामान्य परिदृश्य हैं जहाँ **create MAPI calendar java** और **save calendar to PST** उपयोगी होते हैं:
1. **स्वचालित मीटिंग शेड्यूलिंग** – प्रोजेक्ट टीमों के लिए पुनरावृत्त मीटिंग आमंत्रण बिना मैन्युअल प्रयास के जनरेट करें।  
2. **इवेंट मैनेजमेंट प्लेटफ़ॉर्म** – कॉन्फ़्रेंस सत्रों को Outlook‑संगत कैलेंडर आइटम के रूप में निर्यात करें।  
3. **CRM इंटीग्रेशन** – CRM सिस्टम से ग्राहक अपॉइंटमेंट को सीधे PST फ़ाइलों के माध्यम से Outlook में सिंक करें।

## प्रदर्शन विचार
- **संसाधन प्रबंधन**: फ़ाइल लॉक से बचने के लिए उपयोग के बाद `PersonalStorage` ऑब्जेक्ट्स को डिस्पोज़ करें।  
- **बैच प्रोसेसिंग**: बड़े वॉल्यूम के लिए, मेमोरी उपयोग कम रखने हेतु कैलेंडर आइटम को असिंक्रोनस या चंक्स में प्रोसेस करें।

## निष्कर्ष
अब आपने **create MAPI calendar java** ऑब्जेक्ट्स, पुनरावृत्ति कॉन्फ़िगर करना, उपस्थितियों को जोड़ना, और Aspose.Email का उपयोग करके **save calendar to PST** करना सीख लिया है। यह दृष्टिकोण आपके जावा अनुप्रयोगों को Outlook संगतता के साथ उन्नत शेड्यूलिंग वर्कफ़्लो को स्वचालित करने में सक्षम बनाता है।  
और अधिक खोज के लिए, आधिकारिक [documentation](https://reference.aspose.com/email/java/) देखें।

## FAQ अनुभाग

### Q: क्या मैं साप्ताहिक पुनरावृत्ति पैटर्न बना सकता हूँ?
- **A**: हाँ! साप्ताहिक दोहराव को परिभाषित करने के लिए `MapiCalendarWeeklyRecurrencePattern` का उपयोग करें।

### Q: इवेंट पुनरावृत्ति में अपवादों को कैसे संभालूँ?
- **A**: पैटर्न से विचलित तिथियों को निर्दिष्ट करने के लिए पुनरावृत्ति ऑब्जेक्ट पर `setExceptions()` कॉल करें।

### Q: क्या मौजूदा कैलेंडर आइटम को अपडेट करना संभव है?
- **A**: बिल्कुल। PST से आइटम लोड करें, उसकी प्रॉपर्टीज़ बदलें, और फिर से सहेजें।

### Q: क्या मैं PST फ़ाइल को एन्क्रिप्ट कर सकता हूँ?
- **A**: हाँ, Aspose.Email PST बनाते समय `PersonalStorage` पर पासवर्ड सेट करने की अनुमति देता है।

### Q: यदि मुझे कैलेंडर इवेंट में अटैचमेंट जोड़ने की आवश्यकता हो तो?
- **A**: सहेजने से पहले `calendar.getAttachments().addFileAttachment("path/to/file")` का उपयोग करें।

## संसाधन
- [Aspose.Email Documentation](https://reference.aspose.com/email/java/)  
- [Aspose.Email for Java डाउनलोड करें](https://releases.aspose.com/email/java/)  
- [लाइसेंस खरीदें](https://purchase.aspose.com/buy)  
- [फ्री ट्रायल संस्करण](https://releases.aspose.com/email/java/)  
- [टेम्पररी लाइसेंस का अनुरोध करें](https://purchase.aspose.com/temporary-license/)  
- [Aspose सपोर्ट फ़ोरम](https://forum.aspose.com/c/email/10)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**अंतिम अपडेट:** 2026-01-01  
**परीक्षण किया गया:** Aspose.Email for Java 25.4 (JDK 16)  
**लेखक:** Aspose