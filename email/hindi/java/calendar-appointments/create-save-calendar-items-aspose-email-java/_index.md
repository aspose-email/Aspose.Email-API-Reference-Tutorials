---
date: '2026-05-18'
description: Aspose.Email for Java के साथ जावा में कैलेंडर आइटम बनाने के लिए चरण‑दर‑चरण
  गाइड, जिसमें .ics के रूप में सहेजने का कोड, रिमाइंडर जोड़ना, और MAPI के साथ काम
  करना शामिल है।
keywords:
- how to create calendar item java
- Aspose.Email Java
- calendar item Java
- ICS format Java
- MAPI calendar Java
schemas:
- author: Aspose
  dateModified: '2026-05-18'
  description: Step‑by‑step guide on how to create calendar item java with Aspose.Email
    for Java, including code to save as .ics, add reminders, and work with MAPI.
  headline: How to Create Calendar Item Java Using Aspose.Email
  type: TechArticle
- description: Step‑by‑step guide on how to create calendar item java with Aspose.Email
    for Java, including code to save as .ics, add reminders, and work with MAPI.
  name: How to Create Calendar Item Java Using Aspose.Email
  steps:
  - name: '**Add Dependency:** Ensure your `pom.xml` includes the necessary dependency
      as shown above.'
    text: '**Add Dependency:** Ensure your `pom.xml` includes the necessary dependency
      as shown above.'
  - name: '**Download and Include JAR:** Alternatively, download the JAR file from
      [Aspose Downloads](https://releases.aspose.com/email/java/) and add it to your
      project’s classpath.'
    text: '**Download and Include JAR:** Alternatively, download the JAR file from
      [Aspose Downloads](https://releases.aspose.com/email/java/) and add it to your
      project’s classpath.'
  - name: '**License Setup:** If you have a license file, initialize it in your code
      to unlock full features:'
    text: '**License Setup:** If you have a license file, initialize it in your code
      to unlock full features:'
  - name: '**Initialize MapiCalendar:**'
    text: '**Initialize MapiCalendar:**'
  - name: '**Set Appointment Details:**'
    text: '**Set Appointment Details:**'
  - name: '**Define Start and End Dates:**'
    text: '**Define Start and End Dates:**'
  - name: '**Add Reminders (Optional):**'
    text: '**Add Reminders (Optional):**'
  - name: '**Save the Appointment:**'
    text: '**Save the Appointment:**'
  type: HowTo
- questions:
  - answer: Yes – set the `Recurrence` property on `MapiCalendar` and define the recurrence
      pattern (daily, weekly, etc.).
    question: Can I generate recurring appointments?
  - answer: Absolutely – use `MapiCalendar.fromFile("path.ics")` to load and manipulate
      existing calendar data.
    question: Is it possible to read existing .ics files?
  - answer: It does; the library converts UTC to the target zone based on the `TimeZoneInfo`
      object you provide.
    question: Does Aspose.Email support time‑zone conversion automatically?
  - answer: Attach a `MapiReminderAudio` object to the `Reminders` collection and
      specify the path to a .wav file.
    question: How do I add an audio reminder?
  - answer: Up to **2 GB** per file without performance degradation, thanks to streaming
      APIs.
    question: What is the maximum file size Aspose.Email can handle?
  type: FAQPage
title: Aspose.Email का उपयोग करके जावा में कैलेंडर आइटम कैसे बनाएं
url: /hi/java/calendar-appointments/create-save-calendar-items-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Email का उपयोग करके जावा में कैलेंडर आइटम कैसे बनाएं

आधुनिक एंटरप्राइज़ अनुप्रयोगों में, मीटिंग निमंत्रण और कैलेंडर प्रविष्टियों को स्वचालित करने से अनगिनत घंटे बचते हैं। यह ट्यूटोरियल Aspose.Email के साथ **how to create calendar item java** को दिखाता है, जिसमें ऑब्जेक्ट इनिशियलाइज़ेशन से लेकर एक अपॉइंटमेंट को *.ics* फ़ाइल के रूप में सहेजना, विज़ुअल और ऑडियो रिमाइंडर जोड़ना, और MAPI संदेशों से प्राप्तकर्ता की स्थिति निकालना शामिल है। अंत तक, आप अपने जावा सेवाओं में पूरी‑फ़ीचर कैलेंडर कार्यक्षमता एम्बेड कर सकेंगे।

## त्वरित उत्तर
- **क्या लाइब्रेरी आवश्यक है?** Aspose.Email for Java (v25.4 या बाद का)।
- **क्या मैं .ics के रूप में सहेज सकता हूँ?** हाँ – `MapiCalendar.save(..., SaveOptions.getIcs())` कॉल करें।
- **क्या उत्पादन के लिए लाइसेंस चाहिए?** एक वैध Aspose.Email लाइसेंस मूल्यांकन सीमाओं को हटा देता है।
- **कौन सा जावा संस्करण समर्थित है?** JDK 8 + (Java 11 और 17 सहित)।
- **क्या Maven समर्थित है?** बिल्कुल – `pom.xml` में Maven डिपेंडेंसी जोड़ें।

`SaveOptions` क्लास सहेजने के विकल्प प्रदान करती है; `getIcs()` iCalendar फ़ॉर्मेट के लिए सेटिंग्स लौटाता है।

## जावा में कैलेंडर आइटम कैसे बनाएं?
`MapiCalendar` क्लास लोड करें, आवश्यक प्रॉपर्टीज़ (subject, location, start/end times) सेट करें, और `save` को ICS फ़ॉर्मेट के साथ कॉल करें – पूरी प्रक्रिया को दस लाइनों से कम कोड में किया जा सकता है। Aspose.Email स्वचालित रूप से टाइम‑ज़ोन रूपांतरण और पुनरावृत्ति नियमों को संभालता है, जिससे उत्पन्न *.ics* फ़ाइल RFC 5545 के अनुरूप रहती है।

## कैलेंडर प्रबंधन के लिए Aspose.Email क्यों उपयोग करें?
Aspose.Email **70+** ईमेल और कैलेंडर फ़ॉर्मेट्स को सपोर्ट करता है, **2 GB** तक की फ़ाइलों को पूरी दस्तावेज़ को मेमोरी में लोड किए बिना प्रोसेस करता है, और MAPI तथा iCalendar मानकों दोनों के लिए **single‑API** दृष्टिकोण प्रदान करता है। यह मापी गई क्षमता आपको बड़े पैमाने पर कैलेंडर आइटम्स को विश्वसनीय रूप से जेनरेट, मॉडिफ़ाई और पढ़ने में सक्षम बनाती है।

## पूर्वापेक्षाएँ
- **Java Development Kit (JDK):** Version 8 या उससे ऊपर।
- **Maven:** डिपेंडेंसी मैनेजमेंट के लिए।
- **Aspose.Email for Java:** Version 25.4 या नया (नवीनतम रिलीज़ की सिफारिश की जाती है)।

## पर्यावरण सेटअप
अपने Maven प्रोजेक्ट में Aspose.Email शामिल करने के लिए, निम्न डिपेंडेंसी को अपने `pom.xml` में जोड़ें:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

## लाइसेंस प्राप्ति
Aspose.Email एक मुफ्त ट्रायल लाइसेंस प्रदान करता है जो अधिकांश मूल्यांकन प्रतिबंधों को हटा देता है। उत्पादन उपयोग के लिए, सब्सक्रिप्शन खरीदें या परीक्षण के लिए एक अस्थायी लाइसेंस का अनुरोध करें।

## जावा के लिए Aspose.Email सेटअप
1. **डिपेंडेंसी जोड़ें:** सुनिश्चित करें कि आपका `pom.xml` ऊपर दिखाए अनुसार आवश्यक डिपेंडेंसी शामिल करता है।  
2. **JAR डाउनलोड और शामिल करें:** वैकल्पिक रूप से, JAR फ़ाइल को [Aspose Downloads](https://releases.aspose.com/email/java/) से डाउनलोड करें और इसे अपने प्रोजेक्ट की क्लासपाथ में जोड़ें।  
3. **लाइसेंस सेटअप:** यदि आपके पास लाइसेंस फ़ाइल है, तो इसे अपने कोड में इनिशियलाइज़ करके सभी फीचर अनलॉक करें:

   ```java
   License license = new License();
   license.setLicense("Path_to_Aspose.Email_License_File");
   ```

`License` क्लास एक Aspose.Email लाइसेंस फ़ाइल को लोड और लागू करती है, जिससे पूर्ण‑फ़ीचर उपयोग सक्षम हो जाता है।

## कार्यान्वयन गाइड
नीचे हम **create calendar item java** ऑब्जेक्ट्स बनाने, उन्हें रिमाइंडर के साथ समृद्ध करने, और *.ics* फ़ाइलों के रूप में सहेजने के लिए आवश्यक मुख्य चरणों को देखते हैं।

### कैलेंडर आइटम बनाना और सहेजना

#### अवलोकन
यह सेक्शन प्रोग्रामेटिक रूप से कैलेंडर अपॉइंटमेंट बनाने, डिस्प्ले और ऑडियो रिमाइंडर संलग्न करने, और परिणाम को यूनिवर्सल iCalendar फ़ॉर्मेट में सहेजने को दर्शाता है।

#### चरण‑दर‑चरण कार्यान्वयन

1. **MapiCalendar इनिशियलाइज़ करें:**  
   `MapiCalendar` क्लास MAPI फ़ॉर्मेट में एक कैलेंडर ऑब्जेक्ट को दर्शाती है। यह सभी अपॉइंटमेंट प्रॉपर्टीज़ सेट करने के लिए एंट्री पॉइंट के रूप में कार्य करती है।

   ```java
   MapiCalendar appointment = new MapiCalendar();
   ```

2. **अपॉइंटमेंट विवरण सेट करें:**  
   मीटिंग के लिए स्पष्ट विषय, स्थान, और वर्णनात्मक बॉडी प्रदान करें।

   ```java
   appointment.setLocation("LAKE ARGYLE WA 6743");
   appointment.setSubject("Appointment");
   appointment.setBody("This is a very important meeting");
   ```

3. **शुरू और समाप्ति तिथियां निर्धारित करें:**  
   `GregorianCalendar` का उपयोग करके सटीक शुरू और समाप्ति टाइमस्टैम्प निर्दिष्ट करें, समय‑ज़ोन को ध्यान में रखते हुए।

   ```java
   Calendar cal = GregorianCalendar.getInstance();
   cal.set(2016, 10, 2); // Month is zero-based.
   Date startDate = cal.getTime();

   cal.setTime(startDate);
   cal.add(Calendar.DAY_OF_MONTH, 1); // End date is one day later.
   Date endDate = cal.getTime();

   appointment.setStartDate(startDate);
   appointment.setEndDate(endDate);
   ```

4. **रिमाइंडर जोड़ें (वैकल्पिक):**  
   आप विज़ुअल रिमाइंडर (पॉप‑अप) और ऑडियो रिमाइंडर (wav फ़ाइल) संलग्न कर सकते हैं ताकि प्रतिभागियों को बेहतर सूचित किया जा सके।  
   *प्रो टिप:* अग्रिम 15‑मिनट नोटिस के लिए `ReminderMinutesBeforeStart` को `15` सेट करें।  
   `MapiReminderAudio` क्लास कैलेंडर आइटम से जुड़ा ऑडियो रिमाइंडर दर्शाती है।

5. **अपॉइंटमेंट सहेजें:**  
   कैलेंडर आइटम को इच्छित आउटपुट फ़ोल्डर में *.ics* फ़ाइल के रूप में सहेजें।

   ```java
   String dataDir = "YOUR_OUTPUT_DIRECTORY/";
   appointment.save(dataDir + "CalendarItem_out.ics\
   ```

## सामान्य समस्याएँ और टिप्स
- **समय‑ज़ोन असंगतियां:** `StartDate` और `EndDate` सेट करते समय हमेशा समय‑ज़ोन निर्दिष्ट करें ताकि डेलाइट‑सेविंग त्रुटियों से बचा जा सके।  
- **बड़ी उपस्थितियों की सूची:** 200 से अधिक उपस्थितियों वाले मीटिंग्स के लिए, मेमोरी सीमा के भीतर रहने हेतु `MapiRecipientCollection` बैचिंग का उपयोग करें।  
  `MapiRecipientCollection` क्लास मीटिंग उपस्थितियों की सूची रखती है।  
- **लाइसेंस अनुपलब्ध:** यदि लाइसेंस फ़ाइल लोड नहीं हुई, तो API ट्रायल मोड में स्विच हो जाता है जो प्रति निष्पादन सहेजे गए आइटम्स की संख्या को **10** तक सीमित करता है।

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या मैं आवर्ती अपॉइंटमेंट बना सकता हूँ?**  
A: हाँ – `MapiCalendar` पर `Recurrence` प्रॉपर्टी सेट करें और आवर्ती पैटर्न (दैनिक, साप्ताहिक, आदि) परिभाषित करें।

**Q: क्या मौजूदा .ics फ़ाइलें पढ़ना संभव है?**  
A: बिल्कुल – मौजूदा कैलेंडर डेटा को लोड और संशोधित करने के लिए `MapiCalendar.fromFile("path.ics")` का उपयोग करें।

**Q: क्या Aspose.Email स्वचालित रूप से समय‑ज़ोन रूपांतरण का समर्थन करता है?**  
A: हाँ; लाइब्रेरी आपके द्वारा प्रदान किए गए `TimeZoneInfo` ऑब्जेक्ट के आधार पर UTC को लक्ष्य ज़ोन में परिवर्तित करती है।

**Q: मैं ऑडियो रिमाइंडर कैसे जोड़ूँ?**  
A: `Reminders` कलेक्शन में एक `MapiReminderAudio` ऑब्जेक्ट संलग्न करें और .wav फ़ाइल का पाथ निर्दिष्ट करें।

**Q: Aspose.Email द्वारा संभाली जा सकने वाला अधिकतम फ़ाइल आकार क्या है?**  
A: स्ट्रीमिंग API के कारण प्रति फ़ाइल **2 GB** तक बिना प्रदर्शन गिरावट के संभाला जा सकता है।

---

**अंतिम अपडेट:** 2026-05-18  
**परीक्षित संस्करण:** Aspose.Email for Java 25.4  
**लेखक:** Aspose

## संबंधित ट्यूटोरियल
- [कैलेंडर शेयरिंग प्रबंधन - Aspose.Email for Java गाइड](/email/java/calendar-appointments/create-send-calendar-invitations-aspose-email-java/)
- [Aspose.Email for Java का उपयोग करके Outlook कैलेंडर आइटम्स को ICS में निकालना कैसे करें](/email/java/calendar-appointments/extract-outlook-calendar-to-ics-aspose-email-java/)
- [Aspose.Email in Java का उपयोग करके एक ICS फ़ाइल से कई कैलेंडर इवेंट्स पढ़ना कैसे करें](/email/java/calendar-appointments/read-multiple-ics-events-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}