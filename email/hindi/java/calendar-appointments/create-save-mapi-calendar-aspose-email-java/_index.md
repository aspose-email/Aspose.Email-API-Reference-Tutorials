---
date: '2026-09-17'
description: Aspose.Email for Java का उपयोग करके Outlook calendar PST निर्यात करना
  सीखें – MAPI calendar items बनाएं, recurrence सेट करें, attendees जोड़ें, और PST
  में सहेजें।
keywords:
- export outlook calendar pst
- how to export pst
- how to add recurrence
- how to add attendees
- save calendar to pst
lastmod: '2026-09-17'
og_description: Aspose.Email for Java का उपयोग करके Outlook calendar PST निर्यात करें।
  MAPI calendar items बनाना, recurrence, attendees जोड़ना, और मिनटों में PST में सहेजना
  सीखें।
og_image_alt: Guide to exporting Outlook calendar PST files with Aspose.Email for
  Java
og_title: Aspose.Email – Java के साथ Outlook calendar PST निर्यात करें
schemas:
- author: Aspose
  dateModified: '2026-09-17'
  description: Learn how to export Outlook calendar PST using Aspose.Email for Java
    – create MAPI calendar items, set recurrence, add attendees, and save to PST.
  headline: Export Outlook calendar PST with Aspose.Email – Java
  type: TechArticle
- description: Learn how to export Outlook calendar PST using Aspose.Email for Java
    – create MAPI calendar items, set recurrence, add attendees, and save to PST.
  name: Export Outlook calendar PST with Aspose.Email – Java
  steps:
  - name: '**Initialize date and recurrence pattern**'
    text: '**Initialize date and recurrence pattern**'
  - name: '**Set up recipients**'
    text: '**Set up recipients**'
  - name: '**Create the MAPI calendar item**'
    text: '**Create the MAPI calendar item**'
  - name: '**Save to PST file**'
    text: '**Save to PST file**'
  - name: '**Automated meeting scheduling** – Generate recurring meeting invites for
      project teams without manual effort.'
    text: '**Automated meeting scheduling** – Generate recurring meeting invites for
      project teams without manual effort.'
  - name: '**Event management platforms** – Export conference sessions as Outlook‑compatible
      calendar items.'
    text: '**Event management platforms** – Export conference sessions as Outlook‑compatible
      calendar items.'
  - name: '**CRM integration** – Sync customer appointments from a CRM system directly
      into Outlook via PST files.'
    text: '**CRM integration** – Sync customer appointments from a CRM system directly
      into Outlook via PST files.'
  type: HowTo
- questions:
  - answer: Aspose.Email for Java
    question: Which library?
  - answer: Export Outlook calendar PST and **save calendar to PST**
    question: Primary goal?
  - answer: Java 8+, Maven, Aspose.Email license
    question: Prerequisites?
  - answer: 10‑15 minutes for a basic event
    question: Typical implementation time?
  - answer: Yes – daily, weekly, monthly, etc.
    question: Can I add recurrence?
  type: FAQPage
tags:
- export outlook calendar pst
- Aspose.Email
- Java calendar automation
title: Aspose.Email – Java के साथ Outlook calendar PST निर्यात करें
url: /hi/java/calendar-appointments/create-save-mapi-calendar-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Email – Java के साथ Outlook कैलेंडर PST निर्यात करें

## परिचय

क्या आप अपने Java अनुप्रयोगों में कैलेंडर ऑटोमेशन को सरल बनाना चाहते हैं और **Outlook कैलेंडर PST** फ़ाइलें निर्यात करने की आवश्यकता है? **Aspose.Email for Java** के साथ, आप **MAPI कैलेंडर Java** आइटम बना सकते हैं, पुनरावृत्ति पैटर्न निर्धारित कर सकते हैं, प्रतिभागियों को जोड़ सकते हैं, और केवल कुछ कोड लाइनों से **कैलेंडर को PST में सहेज** सकते हैं। यह ट्यूटोरियल आपको पूरी प्रक्रिया के माध्यम से ले जाता है—लाइब्रेरी सेटअप से लेकर वितरण के लिए तैयार एक पूर्ण कार्यात्मक कैलेंडर एंट्री जेनरेट करने तक।

### आप क्या सीखेंगे
- Aspose.Email का उपयोग करके **MAPI कैलेंडर Java** इवेंट कैसे बनाएं।  
- दैनिक, साप्ताहिक, या कस्टम पुनरावृत्ति पैटर्न को कॉन्फ़िगर करना।  
- अपने कैलेंडर आमंत्रण में प्राप्तकर्ताओं (आयोजक, प्रतिभागी) को जोड़ना।  
- Outlook संगतता के लिए **कैलेंडर को PST में सहेज** कर कैलेंडर आइटम को स्थायी बनाना।  
- पुन: उपयोग योग्य कोड के साथ **मीटिंग शेड्यूलिंग को ऑटोमेट** करने का तरीका।

## त्वरित उत्तर
- **कौन सी लाइब्रेरी?** Aspose.Email for Java  
- **मुख्य लक्ष्य?** Outlook कैलेंडर PST निर्यात करना और **कैलेंडर को PST में सहेज**  
- **पूर्वापेक्षाएँ?** Java 8+, Maven, Aspose.Email लाइसेंस  
- **आम कार्यान्वयन समय?** बुनियादी इवेंट के लिए 10‑15 मिनट  
- **क्या मैं पुनरावृत्ति जोड़ सकता हूँ?** हाँ – दैनिक, साप्ताहिक, मासिक, आदि।

## Outlook कैलेंडर PST निर्यात करें

इस अनुभाग में हम अंत‑से‑अंत प्रवाह पर ध्यान देंगे जो आपको **Outlook कैलेंडर PST** फ़ाइलें निर्यात करने की अनुमति देता है। MAPI कैलेंडर ऑब्जेक्ट बनाने के बाद, अंतिम चरण इसे एक PST फ़ाइल में संग्रहीत करना है जिसे Outlook सीधे पढ़ सकता है।

## कैलेंडर ऑटोमेशन के लिए Aspose.Email क्यों उपयोग करें?
Outlook कैलेंडर PST निर्यात करने के लिए Aspose.Email चुनें क्योंकि यह COM इंटरऑप के बिना Outlook‑संगत आइटम उत्पन्न करने का विश्वसनीय, सर्वर‑साइड तरीका प्रदान करता है। लाइब्रेरी **50+ इनपुट और आउटपुट फ़ॉर्मेट** का समर्थन करती है, 2 GB से बड़ी PST फ़ाइलों को संभाल सकती है, और सामान्य सर्वर हार्डवेयर पर प्रति मिनट हजारों कैलेंडर एंट्री प्रोसेस करती है। इसका बिल्ट‑इन पुनरावृत्ति इंजन दैनिक, साप्ताहिक, मासिक, और कस्टम पैटर्न को कवर करता है, जिससे मैन्युअल तिथि गणना की आवश्यकता समाप्त हो जाती है।

## पूर्वापेक्षाएँ

शुरू करने से पहले सुनिश्चित करें कि आपके पास हैं:

### आवश्यक लाइब्रेरी
- **Aspose.Email for Java**: संस्करण 25.4 या बाद का (Java 8‑21 का समर्थन करता है)।

### पर्यावरण सेटअप आवश्यकताएँ
- IntelliJ IDEA या Eclipse जैसे Java IDE।  
- निर्भरताओं को प्रबंधित करने के लिए Maven स्थापित हो।

### ज्ञान पूर्वापेक्षाएँ
- बुनियादी Java प्रोग्रामिंग कौशल।  
- ऑब्जेक्ट‑ओरिएंटेड अवधारणाओं की परिचितता।

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

Aspose.Email फ़्री ट्रायल प्रदान करता है, लेकिन लाइसेंस सभी फीचर अनलॉक करता है:

- **फ़्री ट्रायल**: 30 दिनों के लिए बिना सीमाओं के परीक्षण करें।  
- **अस्थायी लाइसेंस**: यदि आपको अतिरिक्त समय चाहिए तो [Aspose की वेबसाइट](https://purchase.aspose.com/temporary-license/) पर अनुरोध करें।  
- **खरीदें**: स्थायी लाइसेंस [खरीद पृष्ठ](https://purchase.aspose.com/buy) से खरीदें।

### बुनियादी प्रारंभिककरण

डिपेंडेंसी जोड़ने के बाद, अपने लाइसेंस फ़ाइल के साथ लाइब्रेरी को इनिशियलाइज़ करें:

```java
com.aspose.email.License license = new com.aspose.email.License();
license.setLicense("path_to_your_license.lic");
```

## कार्यान्वयन गाइड

अब जब आप सेट हो गए हैं, चलिए **MAPI कैलेंडर Java** बनाते हैं और **कैलेंडर को PST में सहेज**ते हैं।

### पुनरावृत्ति के साथ MAPI कैलेंडर बनाएं

#### अवलोकन

हम एक कैलेंडर इवेंट बनाएंगे, दैनिक पुनरावृत्ति लागू करेंगे, प्रतिभागियों को जोड़ेंगे, और अंत में इसे PST फ़ाइल में सहेजेंगे।

#### चरण‑दर‑चरण कार्यान्वयन

1. **तारीख और पुनरावृत्ति पैटर्न इनिशियलाइज़ करें**  

   `MapiCalendarEventRecurrence` वह क्लास है जो कैलेंडर आइटम के लिए पुनरावृत्ति विवरण संग्रहीत करता है।  
   `MapiCalendarDailyRecurrencePattern` एक सरल दैनिक दोहराव शेड्यूल को परिभाषित करता है।  

   पहले, प्रारंभ समय निर्धारित करें और दैनिक पुनरावृत्ति सेट करें:

   ```java
   import java.util.Date;

   // Add hours to current date to get the start time
   Date startDate = addHours(new Date(), 12);

   MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
   recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
   ```

2. **प्राप्तकर्ताओं को सेट अप करें**  

   `MapiRecipientCollection` मीटिंग में आमंत्रित लोगों की सूची को दर्शाता है।  
   `MAPI_TO` वह फ़्लैग है जो प्राप्तकर्ता को प्राथमिक प्रतिभागी के रूप में चिह्नित करता है।  

   उन लोगों को जोड़ें जिन्हें मीटिंग आमंत्रण प्राप्त होना चाहिए:

   ```java
   import com.aspose.email.MapiRecipientCollection;
   import com.aspose.email.MapiRecipientType;

   MapiRecipientCollection recColl = new MapiRecipientCollection();
   recColl.add("recipient@gmail.com", "Attendee Name", MapiRecipientType.MAPI_TO);
   ```

3. **MAPI कैलेंडर आइटम बनाएं**  

   `MapiMessage` क्लास (यहाँ कैलेंडर ऑब्जेक्ट के रूप में उपयोग किया गया) सभी इवेंट प्रॉपर्टीज़ को समाहित करता है जैसे आयोजक, विषय, स्थान, प्रारंभ/समाप्ति समय, विवरण, प्राप्तकर्ता सूची, और पुनरावृत्ति।  

   सभी आवश्यक विवरणों के साथ कैलेंडर ऑब्जेक्ट बनाएं:

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

4. **PST फ़ाइल में सहेजें**  

   `PersonalStorage` Aspose.Email का टॉप‑लेवल API है जो PST फ़ाइलों को बनाने और मैनीपुलेट करने के लिए उपयोग होता है।  
   `addMapiMessageItem` निर्दिष्ट फ़ोल्डर में MAPI संदेश (कैलेंडर आइटम सहित) डालता है।  

   अंत में, **कैलेंडर को PST में सहेज** कर कैलेंडर को स्थायी बनाएं:

   ```java
   import com.aspose.email.PersonalStorage;
   import com.aspose.email.FolderInfo;
   import com.aspose.email.StandardIpmFolder;

   PersonalStorage pst = PersonalStorage.create("calendar.pst", 0);
   FolderInfo calendarFolder = pst.createPredefinedFolder("Calendar", StandardIpmFolder.CALendars);

   // Save the MAPI Calendar item
   calendarFolder.addMapiMessageItem(calendar);
   ```

### समस्या निवारण टिप्स
- लाइसेंस पथ सत्यापित करें; अमान्य लाइसेंस कार्यक्षमता को सीमित करेगा।  
- आमंत्रण विफलता से बचने के लिए प्राप्तकर्ता ईमेल पते सही ढंग से स्वरूपित हों।  
- ऑपरेशनों के बाद PST (`pst.dispose()`) बंद करें ताकि फ़ाइल हैंडल मुक्त हो सकें।

## व्यावहारिक अनुप्रयोग

यहाँ सामान्य परिदृश्य हैं जहाँ **MAPI कैलेंडर Java** बनाना और **कैलेंडर को PST में सहेज**ना प्रभावी साबित होता है:

1. **ऑटोमेटेड मीटिंग शेड्यूलिंग** – प्रोजेक्ट टीमों के लिए पुनरावृत्त मीटिंग आमंत्रण बिना मैन्युअल प्रयास के जेनरेट करें।  
2. **इवेंट मैनेजमेंट प्लेटफ़ॉर्म** – कॉन्फ़्रेंस सत्रों को Outlook‑संगत कैलेंडर आइटम के रूप में निर्यात करें।  
3. **CRM इंटीग्रेशन** – CRM सिस्टम से ग्राहक अपॉइंटमेंट्स को सीधे PST फ़ाइलों के माध्यम से Outlook में सिंक करें।

## प्रदर्शन विचार

- **संसाधन प्रबंधन**: फ़ाइल लॉक से बचने के लिए उपयोग के बाद `PersonalStorage` ऑब्जेक्ट्स को डिस्पोज़ करें।  
- **बैच प्रोसेसिंग**: बड़े वॉल्यूम के लिए, मेमोरी उपयोग कम रखने हेतु कैलेंडर आइटम को असिंक्रोनस या चंक्स में प्रोसेस करें।  
- **स्केलेबिलिटी**: Aspose.Email 2 GB से बड़े PST फ़ाइलों को लिख सकता है जबकि मेमोरी उपयोग 200 MB से कम रहता है।

## निष्कर्ष

आपने अब **Outlook कैलेंडर PST** को निर्यात करना सीख लिया है, MAPI कैलेंडर Java ऑब्जेक्ट बनाकर, पुनरावृत्ति कॉन्फ़िगर करके, प्रतिभागियों को जोड़कर, और Aspose.Email का उपयोग करके **कैलेंडर को PST में सहेज**कर। यह दृष्टिकोण आपके Java अनुप्रयोगों को Outlook संगतता के साथ परिष्कृत शेड्यूलिंग वर्कफ़्लो ऑटोमेट करने में सक्षम बनाता है।

गहरी जानकारी के लिए आधिकारिक [documentation](https://reference.aspose.com/email/java/) देखें।

## अक्सर पूछे जाने वाले प्रश्न

### प्रश्न: क्या मैं साप्ताहिक पुनरावृत्ति पैटर्न बना सकता हूँ?
- **उत्तर**: हाँ! साप्ताहिक पुनरावृत्ति के लिए `MapiCalendarWeeklyRecurrencePattern` का उपयोग करें।

### प्रश्न: इवेंट पुनरावृत्ति में अपवादों को कैसे संभालें?
- **उत्तर**: पैटर्न से अलग होने वाली तिथियों को निर्दिष्ट करने के लिए पुनरावृत्ति ऑब्जेक्ट पर `setExceptions()` कॉल करें।

### प्रश्न: क्या मौजूदा कैलेंडर आइटम को अपडेट करना संभव है?
- **उत्तर**: बिल्कुल। PST से आइटम लोड करें, उसकी प्रॉपर्टीज़ बदलें, और फिर से सहेजें।

### प्रश्न: क्या मैं PST फ़ाइल को एन्क्रिप्ट कर सकता हूँ?
- **उत्तर**: हाँ, PST बनाते समय `PersonalStorage` पर पासवर्ड सेट करने की अनुमति Aspose.Email देता है।

### प्रश्न: यदि मुझे कैलेंडर इवेंट में अटैचमेंट जोड़ने की जरूरत हो तो?
- **उत्तर**: सहेजने से पहले `calendar.getAttachments().addFileAttachment("path/to/file")` का उपयोग करें।

## संसाधन

- [Aspose.Email Documentation](https://reference.aspose.com/email/java/)
- [Download Aspose.Email for Java](https://releases.aspose.com/email/java/)
- [Purchase a License](https://purchase.aspose.com/buy)
- [Free trial version](https://releases.aspose.com/email/java/)
- [Request a Temporary License](https://purchase.aspose.com/temporary-license/)
- [Aspose support forum](https://forum.aspose.com/c/email/10)

---

**अंतिम अपडेट:** 2026-09-17  
**के साथ परीक्षण किया गया:** Aspose.Email for Java 25.4 (JDK 16)  
**लेखक:** Aspose

## संबंधित ट्यूटोरियल

- [How to Create and Manage Outlook PST Files Using Aspose.Email for Java](/email/java/outlook-pst-ost-operations/aspose-email-java-manage-pst-files/)
- [How to Create PST Files with Aspose.Email for Java](/email/java/email-parsing-analysis/aspose-email-java-create-pst-guide/)
- [How to Create Calendar Item Java Using Aspose.Email](/email/java/calendar-appointments/create-save-calendar-items-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}