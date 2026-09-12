---
date: '2026-09-12'
description: Aspose.Email का उपयोग करके Java में iCalendar फ़ाइल बनाना सीखें, attendee
  status सेट करें, और कई calendar events को कुशलतापूर्वक जनरेट करें।
keywords:
- create icalendar file java
- java generate ics calendar
- aspose email java
- ics export java
lastmod: '2026-09-12'
og_description: Aspose.Email का उपयोग करके Java में iCalendar फ़ाइल बनाएं। attendee
  status सेट करें, कई events लिखें, और Outlook, Google Calendar, तथा अधिक के साथ एकीकृत
  करें।
og_image_alt: Guide to creating iCalendar files in Java with Aspose.Email
og_title: Java में iCalendar फ़ाइल बनाएं – Aspose.Email के साथ ICS निर्यात करें
schemas:
- author: Aspose
  dateModified: '2026-09-12'
  description: Learn how to create iCalendar file Java using Aspose.Email, set attendee
    status, and generate multiple calendar events efficiently.
  headline: How to create iCalendar file Java – export ICS with Aspose.Email
  type: TechArticle
- description: Learn how to create iCalendar file Java using Aspose.Email, set attendee
    status, and generate multiple calendar events efficiently.
  name: How to create iCalendar file Java – export ICS with Aspose.Email
  steps:
  - name: '**Free trial** – Download a temporary license to test Aspose.Email without
      restrictions. Visit [Aspose Temporary License](https://purchase.aspose.com/temporary-license/)
      for details.'
    text: '**Free trial** – Download a temporary license to test Aspose.Email without
      restrictions. Visit [Aspose Temporary License](https://purchase.aspose.com/temporary-license/)
      for details.'
  - name: '**Purchase** – For long‑term use, buy a subscription at [Aspose Purchase](https://purchase.aspose.com/buy).'
    text: '**Purchase** – For long‑term use, buy a subscription at [Aspose Purchase](https://purchase.aspose.com/buy).'
  - name: '**Automated meeting scheduling** – Generate calendar invites on‑the‑fly
      for internal tools or CRM systems.'
    text: '**Automated meeting scheduling** – Generate calendar invites on‑the‑fly
      for internal tools or CRM systems.'
  - name: '**Cross‑platform calendar integration** – Export appointments from legacy
      databases to Outlook, Google Calendar, or Apple Calendar using the standard
      iCalendar format.'
    text: '**Cross‑platform calendar integration** – Export appointments from legacy
      databases to Outlook, Google Calendar, or Apple Calendar using the standard
      iCalendar format.'
  - name: '**Event management platforms** – Bulk‑create schedules for conferences,
      workshops, or webinars with a single API call, preserving all attendee responses.'
    text: '**Event management platforms** – Bulk‑create schedules for conferences,
      workshops, or webinars with a single API call, preserving all attendee responses.'
  type: HowTo
- questions:
  - answer: Yes. Set `saveOptions.setAction(AppointmentAction.Modify)` and provide
      the UID of the appointment you wish to update.
    question: Can I update an existing ICS file instead of creating a new one?
  - answer: Absolutely. Configure recurrence patterns on the `Appointment` object
      before writing to the ICS file.
    question: Does Aspose.Email support recurring events?
  - answer: Yes. Use `appointment.getCustomProperties().add("X‑MyProperty", "MyValue")`
      to embed non‑standard fields.
    question: Is it possible to add custom properties to an ICS event?
  - answer: Both IANA time‑zone IDs (e.g., “America/New_York”) and GMT offsets are
      supported.
    question: What time‑zone formats are accepted?
  - answer: A temporary license removes evaluation restrictions; a full license is
      required for production deployments.
    question: Do I need a license for development builds?
  type: FAQPage
tags:
- create icalendar file java
- aspose.email
- java calendar integration
title: Java में iCalendar फ़ाइल कैसे बनाएं – Aspose.Email के साथ ICS निर्यात करें
url: /hi/java/calendar-appointments/aspose-email-java-set-participant-status-write-ics/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java में iCalendar फ़ाइल कैसे बनाएं – Aspose.Email के साथ ICS निर्यात करें

समय क्षेत्रों में मीटिंग शेड्यूल को प्रबंधित करना सिरदर्द बन सकता है, विशेष रूप से जब आपको दर्जनों प्रतिभागियों के साथ आमंत्रण साझा करने की आवश्यकता हो। इस ट्यूटोरियल में आप Aspose.Email for Java का उपयोग करके **Java में iCalendar फ़ाइल कैसे बनाएं** सीखेंगे, उपस्थितियों की स्थिति सेट करेंगे, और कई कैलेंडर इवेंट्स को एक ही `.ics` फ़ाइल में लिखेंगे। स्टेप‑बाय‑स्टेप कोड स्निपेट्स आपके प्रोजेक्ट में कॉपी करने के लिए तैयार हैं, और व्याख्याएँ दिखाती हैं कि प्रत्येक भाग क्यों महत्वपूर्ण है।

## त्वरित उत्तर
- **क्या मैं Aspose.Email for Java के साथ उपस्थितियों की स्थिति सेट कर सकता हूँ?** हाँ – आप प्रत्येक प्रतिभागी को Accepted, Declined, या Tentative मान असाइन कर सकते हैं।  
- **मैं एक ही ICS फ़ाइल में कितने इवेंट्स लिख सकता हूँ?** लाइब्रेरी कोई कठोर सीमा नहीं लगाती; उदाहरण में दस इवेंट्स दिखाए गए हैं, और आप इसे हजारों तक स्केल कर सकते हैं।  
- **क्या विकास के लिए लाइसेंस चाहिए?** एक मुफ्त टेम्पररी लाइसेंस मूल्यांकन प्रतिबंधों को हटाता है; उत्पादन के लिए खरीदा हुआ लाइसेंस आवश्यक है।  
- **कौन सा Java संस्करण अनुशंसित है?** JDK 16 (या बाद का) प्रदान किए गए क्लासिफायर से मेल खाता है और पूर्ण API संगतता सुनिश्चित करता है।  
- **क्या टाइम‑ज़ोन हैंडलिंग स्वचालित है?** आप तिथियों को बनाते समय टाइम ज़ोन निर्दिष्ट कर सकते हैं, और Aspose.Email सही TZID एम्बेड करेगा।

## iCalendar क्या है और यह क्यों महत्वपूर्ण है?
iCalendar (ICS) फ़ॉर्मेट Outlook, Google Calendar, Apple Calendar और कई अन्य क्लाइंट्स के बीच कैलेंडर डेटा का आदान‑प्रदान करने का सार्वभौमिक मानक है। iCalendar में निर्यात करने से आप मीटिंग आमंत्रण वितरित कर सकते हैं, बड़े पैमाने पर इवेंट्स बना सकते हैं, या लेगेसी सिस्टम को एकीकृत कर सकते हैं बिना प्रतिभागी स्थिति या कस्टम प्रॉपर्टीज़ खोए।

## iCalendar फ़ाइलें निर्यात करने के लिए Aspose.Email for Java का उपयोग क्यों करें?
Aspose.Email आपको प्रत्येक iCalendar तत्व पर सूक्ष्म नियंत्रण देता है जबकि कार्यान्वयन को सरल रखता है। यह **50+ इनपुट और आउटपुट फ़ॉर्मेट** का समर्थन करता है, पूरी फ़ाइल को मेमोरी में लोड किए बिना सैकड़ों पृष्ठों वाले कैलेंडर को प्रोसेस करता है, और किसी भी प्लेटफ़ॉर्म पर काम करता है जो Java 16 या उससे नया चलाता है। इसका मतलब है कि आप मजबूत `.ics` फ़ाइलें बना सकते हैं जो हर प्रमुख कैलेंडर क्लाइंट में सही ढंग से रेंडर होती हैं।

## पूर्वापेक्षाएँ

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

### आवश्यक लाइब्रेरी और संस्करण
- **Aspose.Email for Java** संस्करण 25.4 या बाद का (लाइब्रेरी में iCalendar हैंडलिंग के लिए 30 से अधिक क्लासेस शामिल हैं)।
- Maven डिपेंडेंसी मैनेजमेंट के लिए (या JAR सीधे [Aspose](https://releases.aspose.com/email/java/) से डाउनलोड करें)।

### पर्यावरण सेटअप
- JDK 16 (या बाद का) आपके मशीन पर स्थापित हो।
- IntelliJ IDEA या Eclipse जैसे IDE।

### ज्ञान पूर्वापेक्षाएँ
- बुनियादी Java प्रोग्रामिंग कौशल।
- `java.util.Calendar` और `java.util.Date` के साथ डेट‑टाइम हैंडलिंग की परिचितता।

## Aspose.Email for Java सेटअप

अपने Maven प्रोजेक्ट में Aspose.Email लाइब्रेरी जोड़ें:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### लाइसेंस प्राप्ति चरण
1. **Free trial** – Aspose.Email को बिना प्रतिबंधों के परीक्षण करने के लिए एक टेम्पररी लाइसेंस डाउनलोड करें। विवरण के लिए [Aspose Temporary License](https://purchase.aspose.com/temporary-license/) देखें।  
2. **Purchase** – दीर्घकालिक उपयोग के लिए, [Aspose Purchase](https://purchase.aspose.com/buy) पर सब्सक्रिप्शन खरीदें।

अपने कोड में लाइसेंस इनिशियलाइज़ करें:

```java
com.aspose.email.License license = new com.aspose.email.License();
license.setLicense("path/to/your/license.lic");
```

अब आप इस गाइड की दो मुख्य सुविधाओं में डुबकी लगाने के लिए तैयार हैं।

## Java में iCalendar फ़ाइल निर्यात कैसे करें: अपॉइंटमेंट उपस्थितियों की स्थिति सेट करें

### कैलेंडर अपॉइंटमेंट में प्रतिभागी स्थिति क्या है?
प्रतिभागी स्थिति रिकॉर्ड करती है कि एक उपस्थित ने मीटिंग आमंत्रण का कैसे जवाब दिया — Accepted, Declined, या Tentative। इसे प्रोग्रामेटिक रूप से सेट करना स्वचालित शेड्यूलिंग सिस्टम और सटीक मीटिंग ट्रैकिंग के लिए आवश्यक है।

आप कैलेंडर फ़ाइल लिखने से पहले प्रत्येक `Attendee` ऑब्जेक्ट पर सीधे प्रतिभागी स्थिति सेट कर सकते हैं।

### स्टेप‑बाय‑स्टेप इम्प्लीमेंटेशन

#### 1️⃣ अपॉइंटमेंट तिथियों को बनाएं और कॉन्फ़िगर करें
`java.util.Calendar` जावा क्लास है जो तिथि और समय मानों को संभालता है। `java.util.Calendar` का उपयोग करके शुरू और समाप्ति समय निर्धारित करें। लाइब्रेरी प्रदान किए गए टाइम‑ज़ोन पहचानकर्ता का सम्मान करती है।

```java
String location = "Room 5";
Calendar calendar = Calendar.getInstance();

// Set start date and time
calendar.set(2011, Calendar.NOVEMBER, 10, 10, 12, 11);
Date startDate = calendar.getTime();

// Set end date and time
calendar.set(2012, Calendar.OCTOBER, 13, 13, 11, 12);
Date endDate = calendar.getTime();
```

#### 2️⃣ ऑर्गनाइज़र और उपस्थितियों की सूची निर्धारित करें
`AttendeeCollection` एक कलेक्शन क्लास है जो मीटिंग प्रतिभागियों का प्रतिनिधित्व करने वाले `Attendee` ऑब्जेक्ट्स को रखती है। एक `AttendeeCollection` बनाएं और प्रत्येक प्रतिभागी का ईमेल पता जोड़ें।

```java
MailAddress organizer = new MailAddress("aaa@amail.com", "Organizer");

// Initialize attendee list
MailAddressCollection attendees = new MailAddressCollection();
```

#### 3️⃣ प्रत्येक उपस्थित को भागीदारी स्थिति असाइन करें
`ResponseType` उपस्थित की प्रतिक्रिया स्थिति दर्शाता है जैसे Accepted, Declined, या Tentative। प्रत्येक `Attendee` पर `ResponseType` प्रॉपर्टी सेट करके Accepted, Declined, या Tentative को इंगित करें।

```java
MailAddress attendee1 = new MailAddress("bbb@bmail.com", "First attendee");
MailAddress attendee2 = new MailAddress("ccc@cmail.com", "Second attendee");

// Set statuses
attendee1.setParticipationStatus(ParticipationStatus.Accepted);
attendee2.setParticipationStatus(ParticipationStatus.Declined);

attendees.addMailAddress(attendee1);
attendees.addMailAddress(attendee2);
```

#### 4️⃣ `Appointment` ऑब्जेक्ट बनाएं
`Appointment` कैलेंडर इवेंट को दर्शाता है जिसमें विषय, स्थान और समय जैसी विवरण होते हैं। `Appointment` क्लास एकल कैलेंडर इवेंट का प्रतिनिधित्व करती है। तिथियों, ऑर्गनाइज़र और उपस्थितियों को कॉन्फ़िगर करने के बाद, आप इसे iCalendar में सीरियलाइज़ कर सकते हैं।

```java
Appointment target = new Appointment(location, startDate, endDate, organizer, attendees);
```

**Pro tip:** संग्रह में जोड़ने से पहले हमेशा ईमेल पते को सरल regex से वैलिडेट करें; गलत फॉर्मेट के पते `ParseException` का कारण बनते हैं।

## Java में iCalendar फ़ाइल निर्यात कैसे करें: कई इवेंट्स को एक ICS फ़ाइल में लिखें

### Java के साथ कैलेंडर को iCalendar में निर्यात क्यों करें?
iCalendar फ़ॉर्मेट सार्वभौमिक रूप से समझा जाता है, जिससे आप Outlook, Google Calendar, Apple Calendar और कई अन्य क्लाइंट्स के बीच मीटिंग जानकारी साझा कर सकते हैं। Aspose.Email के साथ **java generate ics calendar** करके, आप प्रतिभागी स्थिति, कस्टम प्रॉपर्टीज़ और पुनरावृत्ति नियमों को अतिरिक्त रूपांतरण चरणों के बिना संरक्षित रखते हैं।

### स्टेप‑बाय‑स्टेप इम्प्लीमेंटेशन

#### 1️⃣ सेव ऑप्शन्स कॉन्फ़िगर करें और राइटर बनाएं
`IcsSaveOptions` यह कॉन्फ़िगर करता है कि iCalendar फ़ाइल कैसे लिखी जाए, जिसमें एन्कोडिंग और फ़ॉर्मेटिंग विकल्प शामिल हैं। `IcsSaveOptions` फ़ाइल लिखने के तरीके को नियंत्रित करता है। कई इवेंट्स को संभालते समय एक ही इंस्टेंस को पुन: उपयोग करने से प्रदर्शन में सुधार होता है।

```java
IcsSaveOptions saveOptions = new IcsSaveOptions();
saveOptions.setAction(AppointmentAction.Create);

CalendarWriter writer = new CalendarWriter("YOUR_OUTPUT_DIRECTORY/WriteMultipleEventsToICS_out.ics", saveOptions);
```

#### 2️⃣ प्रत्येक इवेंट के लिए टाइम फ्रेम निर्धारित करें
`java.util.Date` समय में एक विशिष्ट क्षण को दर्शाता है, आमतौर पर शुरू और समाप्ति टाइमस्टैम्प के लिए उपयोग किया जाता है। अपने डेटा स्रोत के माध्यम से लूप करें, प्रत्येक अपॉइंटमेंट के लिए शुरू/समाप्ति `Date` ऑब्जेक्ट बनाते हुए।

```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2018, Calendar.JUNE, 19, 19, 0, 0); // Start time
Date startDate = calendar.getTime();
calendar.set(2018, Calendar.JUNE, 19, 20, 0, 0); // End time
Date endDate = calendar.getTime();
```

#### 3️⃣ उपस्थितियों का कलेक्शन तैयार करें
`AttendeeCollection` को एक बार बनाएं और इसे प्रत्येक उत्पन्न `Appointment` से संलग्न करें।

```java
MailAddressCollection attendees = new MailAddressCollection();
attendees.addItem(new MailAddress("recepientEmail@gmail.com"));
```

#### 4️⃣ कई अपॉइंटमेंट्स जेनरेट करें और लिखें
इटररेट करें, प्रत्येक एंट्री के लिए एक `Appointment` बनाएं, और `writer.write(appointment)` कॉल करें। अंत में, फ़ाइल हैंडल को बंद करने के लिए राइटर को डिस्पोज़ करें।

```java
try {
    for (int i = 0; i < 10; i++) {
        Appointment app = new Appointment("Room 112", startDate, endDate,
                new MailAddress("organizer@domain.com"), attendees);
        app.setDescription("Test body " + i);
        app.setSummary("Test summary:" + i);
        
        writer.write(app); // Write the appointment to ICS file
    }
} finally {
    writer.dispose(); // Clean up resources
}
```

**Common pitfall:** `writer.dispose()` को कॉल करना भूलने से फ़ाइल खुली रहती है, जिससे बाद के रन में “file in use” त्रुटियाँ आती हैं।

## व्यावहारिक अनुप्रयोग

Aspose.Email for Java कई वास्तविक‑दुनिया परिदृश्यों में चमकता है:

1. **Automated meeting scheduling** – आंतरिक टूल्स या CRM सिस्टम के लिए ऑन‑द‑फ़्लाई कैलेंडर आमंत्रण जेनरेट करें।  
2. **Cross‑platform calendar integration** – लेगेसी डेटाबेस से अपॉइंटमेंट्स को मानक iCalendar फ़ॉर्मेट का उपयोग करके Outlook, Google Calendar, या Apple Calendar में एक्सपोर्ट करें।  
3. **Event management platforms** – कॉन्फ़रेंस, वर्कशॉप या वेबिनार के लिए शेड्यूल को एक ही API कॉल से बड़े पैमाने पर बनाएं, सभी उपस्थितियों की प्रतिक्रियाओं को संरक्षित रखते हुए।

## प्रदर्शन संबंधी विचार

**Aspose.Email for Java** के साथ काम करते समय, इन टिप्स को ध्यान में रखें:

- `CalendarWriter`, `Appointment`, और किसी भी `MailMessage` ऑब्जेक्ट को तुरंत डिस्पोज़ करें ताकि नेटिव रिसोर्सेज़ मुक्त हो सकें।  
- बड़े डेटा सेट को संभालते समय अपॉइंटमेंट्स को बैच‑प्रोसेस करें; इससे गार्बेज‑कलेक्शन ओवरहेड में 30 % तक कमी आती है।  
- प्रत्येक लिखने के ऑपरेशन के लिए नया बनाने के बजाय एक ही `IcsSaveOptions` इंस्टेंस को पुन: उपयोग करें।

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या मैं एक नई फ़ाइल बनाने के बजाय मौजूदा ICS फ़ाइल को अपडेट कर सकता हूँ?**  
A: हाँ। `saveOptions.setAction(AppointmentAction.Modify)` सेट करें और उस अपॉइंटमेंट का UID प्रदान करें जिसे आप अपडेट करना चाहते हैं।

**Q: क्या Aspose.Email आवर्ती इवेंट्स को सपोर्ट करता है?**  
A: बिल्कुल। `Appointment` ऑब्जेक्ट पर पुनरावृत्ति पैटर्न कॉन्फ़िगर करें और फिर iCS फ़ाइल में लिखें।

**Q: क्या एक ICS इवेंट में कस्टम प्रॉपर्टीज़ जोड़ना संभव है?**  
A: हाँ। `appointment.getCustomProperties().add("X‑MyProperty", "MyValue")` का उपयोग करके गैर‑मानक फ़ील्ड एम्बेड करें।

**Q: कौन से टाइम‑ज़ोन फ़ॉर्मेट स्वीकार किए जाते हैं?**  
A: दोनों IANA टाइम‑ज़ोन IDs (जैसे “America/New_York”) और GMT ऑफ़सेट सपोर्टेड हैं।

**Q: क्या विकास बिल्ड्स के लिए लाइसेंस चाहिए?**  
A: टेम्पररी लाइसेंस मूल्यांकन प्रतिबंधों को हटाता है; उत्पादन डिप्लॉयमेंट्स के लिए पूर्ण लाइसेंस आवश्यक है।

## निष्कर्ष

अब आप **Java में iCalendar फ़ाइल कैसे बनाएं** जानते हैं, प्रतिभागी स्थिति सेट कर सकते हैं, और Aspose.Email for Java का उपयोग करके कई इवेंट्स लिख सकते हैं। ये क्षमताएँ आपको मजबूत शेड्यूलिंग फीचर्स बनाने, किसी भी कैलेंडर क्लाइंट के साथ इंटीग्रेट करने, और आपके संगठन में इवेंट वितरण को सहज बनाने में मदद करती हैं।

---

**अंतिम अपडेट:** 2026-09-12  
**परीक्षित संस्करण:** Aspose.Email for Java 25.4 (jdk16 classifier)  
**लेखक:** Aspose

## संबंधित ट्यूटोरियल

- [Generate .ics फ़ाइल Java – Aspose.Email for Java के साथ कैलेंडर आमंत्रण बनाएं – पूर्ण ट्यूटोरियल](/email/java/)
- [Parse ics फ़ाइल java – Aspose.Email के साथ कैलेंडर इवेंट्स पढ़ें](/email/java/calendar-appointments/read-multiple-ics-events-aspose-email-java/)
- [Aspose.Email for Java के साथ कैलेंडर शेयरिंग आमंत्रण बनाएं](/email/java/calendar-appointments/create-send-calendar-invitations-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}