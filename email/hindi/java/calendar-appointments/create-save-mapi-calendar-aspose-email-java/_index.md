---
date: '2026-03-20'
description: Aspose.Email for Java का उपयोग करके Outlook कैलेंडर PST को निर्यात करना
  सीखें – MAPI कैलेंडर आइटम बनाएं, पुनरावृत्ति सेट करें, प्रतिभागियों को जोड़ें, और
  PST में सहेजें।
keywords:
- Create MAPI Calendar Java
- Aspose.Email Java Calendar
- Java PST File Save
title: Aspose.Email – Java के साथ Outlook कैलेंडर PST निर्यात करें
url: /hi/java/calendar-appointments/create-save-mapi-calendar-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Email – Java के साथ Outlook कैलेंडर PST निर्यात करें

## परिचय

क्या आप अपने Java अनुप्रयोगों में कैलेंडर ऑटोमेशन को सरल बनाना चाहते हैं और **Outlook कैलेंडर PST** फ़ाइलें निर्यात करने की आवश्यकता है? **Aspose.Email for Java** के साथ, आप **MAPI कैलेंडर Java** आइटम बना सकते हैं, आवर्ती पैटर्न निर्धारित कर सकते हैं, प्रतिभागियों को जोड़ सकते हैं, और **कैलेंडर को PST में सहेजें** कुछ ही कोड लाइनों के साथ। यह ट्यूटोरियल आपको पूरी प्रक्रिया के माध्यम से ले जाता है—लाइब्रेरी सेटअप से लेकर एक पूर्ण कार्यात्मक कैलेंडर एंट्री उत्पन्न करने तक, जो वितरण के लिए तैयार है।

### आप क्या सीखेंगे
- Aspose.Email का उपयोग करके **MAPI कैलेंडर Java** इवेंट्स कैसे बनाएं।  
- दैनिक, साप्ताहिक, या कस्टम आवर्ती पैटर्न को कॉन्फ़िगर करना।  
- अपने कैलेंडर निमंत्रणों में प्राप्तकर्ताओं (आयोजक, प्रतिभागी) को जोड़ना।  
- Outlook संगतता के लिए कैलेंडर आइटम को **कैलेंडर को PST में सहेजें** द्वारा स्थायी बनाना।  
- पुन: उपयोग योग्य कोड के साथ **मीटिंग शेड्यूलिंग को स्वचालित** कैसे करें।

## त्वरित उत्तर
- **कौनसी लाइब्रेरी?** Aspose.Email for Java  
- **मुख्य लक्ष्य?** Outlook कैलेंडर PST निर्यात करना और **कैलेंडर को PST में सहेजें**  
- **पूर्वापेक्षाएँ?** Java 8+, Maven, Aspose.Email लाइसेंस  
- **सामान्य कार्यान्वयन समय?** बेसिक इवेंट के लिए 10‑15 मिनट  
- **क्या मैं आवृत्ति जोड़ सकता हूँ?** हाँ – दैनिक, साप्ताहिक, मासिक, आदि।

## Outlook कैलेंडर PST निर्यात करें

इस सेक्शन में हम अंत‑से‑अंत प्रवाह पर ध्यान देंगे जो आपको **Outlook कैलेंडर PST** फ़ाइलें निर्यात करने देता है। MAPI कैलेंडर ऑब्जेक्ट बनाने के बाद, अंतिम चरण इसे एक PST फ़ाइल में संग्रहीत करना है जिसे Outlook सीधे पढ़ सकता है।

## कैलेंडर ऑटोमेशन के लिए Aspose.Email का उपयोग क्यों करें?

- **पूर्ण Outlook संगतता** – उत्पन्न आइटम Outlook, OWA, और मोबाइल क्लाइंट्स में काम करते हैं।  
- **समृद्ध आवर्ती समर्थन** – बॉक्स से बाहर दैनिक, साप्ताहिक, मासिक, और कस्टम पैटर्न।  
- **कोई बाहरी निर्भरताएँ नहीं** – शुद्ध Java लाइब्रेरी, कोई COM इंटरऑप आवश्यक नहीं।  
- **उच्च प्रदर्शन** – बड़े PST फ़ाइलों और बल्क ऑपरेशन्स को कुशलता से संभालता है।  
- **मीटिंग शेड्यूलिंग को स्वचालित करें** – इस लॉजिक को बैच जॉब्स या वेब सेवाओं में एम्बेड करें ताकि सैकड़ों निमंत्रण स्वचालित रूप से बन सकें।

## पूर्वापेक्षाएँ

शुरू करने से पहले, सुनिश्चित करें कि आपके पास है:

### आवश्यक लाइब्रेरीज़
- **Aspose.Email for Java**: Version 25.4 or later.

### पर्यावरण सेटअप आवश्यकताएँ
- IntelliJ IDEA या Eclipse जैसे Java IDE।  
- निर्भरताओं को प्रबंधित करने के लिए Maven स्थापित हो।

### ज्ञान पूर्वापेक्षाएँ
- बुनियादी Java प्रोग्रामिंग कौशल।  
- ऑब्जेक्ट‑ओरिएंटेड अवधारणाओं से परिचितता।

## Aspose.Email for Java सेटअप करना

Add the Aspose.Email Maven dependency to your `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### लाइसेंस प्राप्ति

Aspose.Email एक फ्री ट्रायल प्रदान करता है, लेकिन लाइसेंस सभी फीचर्स अनलॉक करता है:

- **फ़्री ट्रायल**: 30 दिनों के लिए बिना सीमाओं के परीक्षण करें।  
- **अस्थायी लाइसेंस**: यदि आपको अतिरिक्त समय चाहिए तो [Aspose की वेबसाइट](https://purchase.aspose.com/temporary-license/) के माध्यम से अनुरोध करें।  
- **खरीदें**: [खरीद पृष्ठ](https://purchase.aspose.com/buy) से स्थायी लाइसेंस खरीदें।

### बेसिक इनिशियलाइज़ेशन

After adding the dependency, initialize the library with your license file:

```java
com.aspose.email.License license = new com.aspose.email.License();
license.setLicense("path_to_your_license.lic");
```

## इम्प्लीमेंटेशन गाइड

Now that you’re set up, let’s **create MAPI calendar Java** and **save calendar to PST**.

### आवृत्ति के साथ MAPI कैलेंडर बनाएं

#### सारांश

हम एक कैलेंडर इवेंट बनाएँगे, दैनिक आवृत्ति लागू करेंगे, प्रतिभागियों को जोड़ेंगे, और अंत में इसे PST फ़ाइल में संग्रहीत करेंगे।

#### स्टेप‑बाय‑स्टेप इम्प्लीमेंटेशन

1. **Initialize Date and Recurrence Pattern**  

   First, define the start time and set a daily recurrence:

   ```java
   import java.util.Date;

   // Add hours to current date to get the start time
   Date startDate = addHours(new Date(), 12);

   MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
   recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
   ```

   *Explanation*: `MapiCalendarEventRecurrence` आवृत्ति विवरण रखता है; हम `MapiCalendarDailyRecurrencePattern` के माध्यम से दैनिक पैटर्न चुनते हैं।

2. **Set Up Recipients**  

   Add the people who should receive the meeting invitation:

   ```java
   import com.aspose.email.MapiRecipientCollection;
   import com.aspose.email.MapiRecipientType;

   MapiRecipientCollection recColl = new MapiRecipientCollection();
   recColl.add("recipient@gmail.com", "Attendee Name", MapiRecipientType.MAPI_TO);
   ```

   *Explanation*: `MapiRecipientCollection` प्रत्येक प्रतिभागी को संग्रहीत करता है; `MAPI_TO` उन्हें प्राथमिक प्राप्तकर्ता के रूप में चिह्नित करता है।

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

   *Explanation*: कंस्ट्रक्टर को आयोजक, विषय, स्थान, प्रारंभ/समाप्ति समय, विवरण, प्राप्तकर्ता सूची, और आवृत्ति की आवश्यकता होती है।

4. **Save to PST File**  

   Finally, persist the calendar by **saving calendar to PST**:

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
- लाइसेंस पथ सत्यापित करें; अमान्य लाइसेंस कार्यक्षमता को सीमित करेगा।  
- आमंत्रण विफलताओं से बचने के लिए प्राप्तकर्ता ईमेल पते सही ढंग से स्वरूपित हों।  
- ऑपरेशन्स के बाद PST (`pst.dispose()`) बंद करें ताकि फ़ाइल हैंडल मुक्त हो सकें।

## व्यावहारिक अनुप्रयोग

यहाँ कुछ सामान्य परिदृश्य हैं जहाँ **MAPI कैलेंडर Java** बनाना और **कैलेंडर को PST में सहेजें** चमकता है:

1. **स्वचालित मीटिंग शेड्यूलिंग** – प्रोजेक्ट टीमों के लिए मैन्युअल प्रयास के बिना आवर्ती मीटिंग निमंत्रण उत्पन्न करें।  
2. **इवेंट मैनेजमेंट प्लेटफ़ॉर्म** – कॉन्फ़्रेंस सत्रों को Outlook‑संगत कैलेंडर आइटम के रूप में निर्यात करें।  
3. **CRM इंटीग्रेशन** – CRM सिस्टम से ग्राहक अपॉइंटमेंट्स को सीधे PST फ़ाइलों के माध्यम से Outlook में सिंक करें।

## प्रदर्शन विचार

- **संसाधन प्रबंधन**: फ़ाइल लॉक से बचने के लिए उपयोग के बाद `PersonalStorage` ऑब्जेक्ट्स को डिस्पोज़ करें।  
- **बैच प्रोसेसिंग**: बड़े वॉल्यूम के लिए, मेमोरी उपयोग कम रखने हेतु कैलेंडर आइटम्स को असिंक्रोनस या चंक्स में प्रोसेस करें।  

## निष्कर्ष

आपने अब **Outlook कैलेंडर PST** को निर्यात करने का तरीका सीख लिया है, जिसमें MAPI कैलेंडर Java ऑब्जेक्ट्स बनाना, आवृत्ति कॉन्फ़िगर करना, प्रतिभागियों को जोड़ना, और Aspose.Email का उपयोग करके **कैलेंडर को PST में सहेजें** शामिल है। यह दृष्टिकोण आपके Java अनुप्रयोगों को Outlook संगतता के साथ उन्नत शेड्यूलिंग वर्कफ़्लो को स्वचालित करने में सक्षम बनाता है।

गहरी खोज के लिए, आधिकारिक [Aspose.Email दस्तावेज़ीकरण](https://reference.aspose.com/email/java/) देखें।

## अक्सर पूछे जाने वाले प्रश्न

### Q: क्या मैं साप्ताहिक आवर्ती पैटर्न बना सकता हूँ?
- **A**: हाँ! साप्ताहिक दोहराव को परिभाषित करने के लिए `MapiCalendarWeeklyRecurrencePattern` का उपयोग करें।

### Q: इवेंट आवृत्ति में अपवादों को कैसे संभालूँ?
- **A**: पैटर्न से विचलित तिथियों को निर्दिष्ट करने के लिए आवृत्ति ऑब्जेक्ट पर `setExceptions()` कॉल करें।

### Q: क्या मौजूदा कैलेंडर आइटम को अपडेट करना संभव है?
- **A**: बिल्कुल। PST से आइटम लोड करें, उसकी प्रॉपर्टीज़ बदलें, और फिर से सहेजें।

### Q: क्या मैं PST फ़ाइल को एन्क्रिप्ट कर सकता हूँ?
- **A**: हाँ, Aspose.Email आपको PST बनाते समय `PersonalStorage` पर पासवर्ड सेट करने की अनुमति देता है।

### Q: यदि मुझे कैलेंडर इवेंट में अटैचमेंट जोड़ने की आवश्यकता हो तो क्या करूँ?
- **A**: सहेजने से पहले `calendar.getAttachments().addFileAttachment("path/to/file")` का उपयोग करें।

## संसाधन

- [Aspose.Email दस्तावेज़ीकरण](https://reference.aspose.com/email/java/)
- [Aspose.Email for Java डाउनलोड करें](https://releases.aspose.com/email/java/)
- [लाइसेंस खरीदें](https://purchase.aspose.com/buy)
- [फ़्री ट्रायल संस्करण](https://releases.aspose.com/email/java/)
- [अस्थायी लाइसेंस का अनुरोध करें](https://purchase.aspose.com/temporary-license/)
- [Aspose सपोर्ट फ़ोरम](https://forum.aspose.com/c/email/10)

---

**अंतिम अपडेट:** 2026-03-20  
**परीक्षण किया गया:** Aspose.Email for Java 25.4 (JDK 16)  
**लेखक:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}