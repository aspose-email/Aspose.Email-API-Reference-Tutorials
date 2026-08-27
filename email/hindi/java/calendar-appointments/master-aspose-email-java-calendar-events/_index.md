---
date: '2026-08-01'
description: Aspose.Email for Java के साथ कैलेंडर को PST में निर्यात करना सीखें, जिसमें
  उपस्थितियों को जोड़ना, प्रारंभ और समाप्ति तिथियों को सेट करना, और अपॉइंटमेंट्स को
  कुशलतापूर्वक प्रबंधित करना शामिल है।
keywords:
- export calendar to pst
- export recurring appointments
- Aspose.Email Java Calendar Events
lastmod: '2026-08-01'
og_description: Aspose.Email for Java का उपयोग करके कैलेंडर को PST में निर्यात करें।
  चरण‑दर‑चरण सीखें कि अपॉइंटमेंट्स कैसे बनाएं, उपस्थितियों को जोड़ें, और Outlook PST
  फ़ाइलें कैसे जनरेट करें।
og_image_alt: 'Developer guide: Export calendar to PST using Aspose.Email for Java'
og_title: कैलेंडर को PST में निर्यात – Aspose.Email for Java के साथ पूर्ण गाइड
schemas:
- author: Aspose
  dateModified: '2026-08-01'
  description: Learn how to export calendar to PST with Aspose.Email for Java, including
    how to add attendees, set start and end dates, and manage appointments efficiently.
  headline: Export calendar to PST with Aspose.Email for Java
  type: TechArticle
- description: Learn how to export calendar to PST with Aspose.Email for Java, including
    how to add attendees, set start and end dates, and manage appointments efficiently.
  name: Export calendar to PST with Aspose.Email for Java
  steps:
  - name: '**Free Trial**: Visit the [Aspose download page](https://releases.aspose.com/email/java/)
      for a temporary license.'
    text: '**Free Trial**: Visit the [Aspose download page](https://releases.aspose.com/email/java/)
      for a temporary license.'
  - name: '**Temporary License**: Apply via the [purchase page](https://purchase.aspose.com/temporary-license/).'
    text: '**Temporary License**: Apply via the [purchase page](https://purchase.aspose.com/temporary-license/).'
  - name: '**Purchase License**: Consider purchasing from [Aspose''s purchase portal](https://purchase.aspose.com/buy)
      for long‑term use.'
    text: '**Purchase License**: Consider purchasing from [Aspose''s purchase portal](https://purchase.aspose.com/buy)
      for long‑term use.'
  - name: '**Business Scheduling** – Automate internal meeting creation and distribution.'
    text: '**Business Scheduling** – Automate internal meeting creation and distribution.'
  - name: '**Event Management** – Track conferences, workshops, and participant lists.'
    text: '**Event Management** – Track conferences, workshops, and participant lists.'
  - name: '**CRM Integration** – Sync appointments with customer relationship tools.'
    text: '**CRM Integration** – Sync appointments with customer relationship tools.'
  - name: '**Project Planning** – Store project milestones as calendar items.'
    text: '**Project Planning** – Store project milestones as calendar items.'
  - name: '**Remote Team Collaboration** – Generate PST files for offline sharing.'
    text: '**Remote Team Collaboration** – Generate PST files for offline sharing.'
  type: HowTo
- questions:
  - answer: Add the Maven dependency shown above, obtain a license, and follow the
      steps in this guide to create and export calendar events.
    question: How do I get started with Aspose.Email for Java?
  - answer: Yes, change the `pstFilePath` variable in `createPSTWithCalendarEvents()`
      to any valid path on your system.
    question: Can I customize the PST file name and location?
  - answer: Absolutely – `MapiCalendar` exposes a `RecurrencePattern` property that
      you can configure before saving.
    question: Is it possible to add recurrence patterns to appointments?
  - answer: Yes, you can export to iCalendar (`.ics`) and other formats using the
      appropriate API methods.
    question: Does Aspose.Email support other calendar formats besides PST?
  - answer: With the Unicode format (`FileFormatVersion.Unicode`), PST files can grow
      up to 2 TB, limited only by available disk space.
    question: What is the maximum size of a PST file I can create?
  type: FAQPage
tags:
- export calendar to pst
- Aspose.Email
- Java calendar appointments
title: Aspose.Email for Java के साथ कैलेंडर को PST में निर्यात करें
url: /hi/java/calendar-appointments/master-aspose-email-java-calendar-events/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Email for Java के साथ कैलेंडर को PST में निर्यात करें

यदि आप एक Java एप्लिकेशन बना रहे हैं जिसे Outlook के साथ शेड्यूलिंग डेटा साझा करने की आवश्यकता है, तो आपको अक्सर **export calendar to PST** करने की जरूरत पड़ेगी। इस ट्यूटोरियल में हम आपको सभी आवश्यक चरणों से परिचित कराएंगे—एक साधारण अपॉइंटमेंट बनाने से लेकर उपस्थितियों को जोड़ने और अंत में इवेंट्स को PST फ़ाइल में लिखने तक, सभी Aspose.Email for Java के साथ। अंत तक आपके पास एक प्रोडक्शन‑रेडी समाधान होगा जो Windows, Linux, और macOS पर काम करता है।

## त्वरित उत्तर
- **मुख्य लक्ष्य क्या है?** PST फ़ाइल में कैलेंडर इवेंट्स निर्यात करना।  
- **कौन सी लाइब्रेरी आवश्यक है?** Aspose.Email for Java (v25.4+).  
- **क्या मुझे लाइसेंस चाहिए?** हाँ, एक वैध Aspose.Email लाइसेंस मूल्यांकन सीमाओं को हटा देता है।  
- **क्या मैं उपस्थितियों को जोड़ सकता हूँ?** बिल्कुल – `MapiRecipientCollection` का उपयोग करें।  
- **कौन सा Java संस्करण समर्थित है?** JDK 16 या उससे ऊपर।

## **export calendar to pst** क्या है?
`MapiCalendar` Aspose.Email की क्लास है जो Outlook कैलेंडर आइटम को मॉडल करती है, जिसमें विषय, स्थान, और समय विवरण शामिल हैं।

कैलेंडर को PST में निर्यात करना मतलब इन‑मेमोरी `MapiCalendar` ऑब्जेक्ट्स को Microsoft Outlook Personal Storage Table (PST) में बदलना है। उत्पन्न PST फ़ाइल को सीधे Outlook में खोला जा सकता है, सहयोगियों के साथ साझा किया जा सकता है, या किसी भी सिस्टम में आयात किया जा सकता है जो PST फ़ॉर्मेट को समझता है, और सभी इवेंट विवरण जैसे उपस्थितियों, आवृत्ति, और रिमाइंडर को संरक्षित रखता है।

## Aspose.Email for Java का उपयोग करके कैलेंडर को PST में निर्यात क्यों करें?
आप Outlook स्थापित किए बिना पूरी तरह संगत PST फ़ाइल बना सकते हैं। Aspose.Email **पूर्ण MAPI समर्थन** प्रदान करता है, **सभी प्रमुख OS** पर काम करता है, और Unicode PST फ़ॉर्मेट में **2 TB तक** डेटा संभाल सकता है—उद्यम‑स्तर के अभिलेखों के लिए पर्याप्त। API आपको केवल कुछ मेथड कॉल्स के साथ उपस्थितियों, आवृत्ति पैटर्न, रिमाइंडर, और कस्टम प्रॉपर्टीज़ को प्रबंधित करने की सुविधा देता है, जिससे विकास प्रयास में उल्लेखनीय कमी आती है।

## पूर्वापेक्षाएँ
- **लाइब्रेरीज़ और निर्भरताएँ**: Aspose.Email for Java version 25.4 or later.  
- **पर्यावरण**: JDK 16 या उससे ऊपर, निर्भरताओं के प्रबंधन के लिए Maven।  
- **ज्ञान**: बेसिक Java प्रोग्रामिंग और Maven की परिचितता।

## Aspose.Email for Java को सेट अप कैसे करें
`pom.xml` में Aspose.Email निर्भरता जोड़ें और अपने Maven प्रोजेक्ट को रिफ्रेश करें। यह एकल कदम पूरे MAPI API को आपके क्लासपाथ पर उपलब्ध कराता है।

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

```xml
<dependency>
  <groupId>com.aspose</groupId>
  <artifactId>aspose-email</artifactId>
  <version>25.4</version>
  <classifier>jdk16</classifier>
</dependency>
```

### लाइसेंस प्राप्ति
Aspose.Email की पूरी कार्यक्षमता को मूल्यांकन सीमाओं के बिना अनलॉक करने के लिए लाइसेंस प्राप्त करें:

1. **नि:शुल्क परीक्षण**: अस्थायी लाइसेंस के लिए [Aspose डाउनलोड पेज](https://releases.aspose.com/email/java/) पर जाएँ।  
2. **अस्थायी लाइसेंस**: [खरीद पेज](https://purchase.aspose.com/temporary-license/) के माध्यम से आवेदन करें।  
3. **लाइसेंस खरीदें**: दीर्घकालिक उपयोग के लिए [Aspose की खरीद पोर्टल](https://purchase.aspose.com/buy) से खरीदने पर विचार करें।

एक बार जब आपके पास लाइसेंस हो, तो इसे अपने एप्लिकेशन में इनिशियलाइज़ करें ताकि सभी फीचर सक्षम हो सकें।

## **अपॉइंटमेंट बनाएं** (Java में कैलेंडर इवेंट बनाएं)

`MapiCalendar` ऑब्जेक्ट लोड करें, उसकी मुख्य प्रॉपर्टीज़ सेट करें, और आगे की प्रोसेसिंग के लिए तैयार लौटाएँ। यह मेथड एक कैलेंडर एंट्री बनाता है जिसमें विषय, स्थान, विवरण, और आप द्वारा परिभाषित **java calendar start date** / **java calendar end date** शामिल होते हैं।

```java
public static MapiCalendar createAppointment(String subject, String location,
                                             String description, Calendar start, Calendar end) {
    MapiCalendar appointment = new MapiCalendar();
    appointment.setSubject(subject);
    appointment.setLocation(location);
    appointment.setBody(description);
    appointment.setStartDate(start);
    appointment.setEndDate(end);
    return appointment;
}
```

```java
import com.aspose.email.MapiCalendar;
import java.util.Calendar;
import java.util.Date;

public MapiCalendar createAppointment() {
    Calendar cal = Calendar.getInstance();
    
    // Setting the start date
    cal.set(Calendar.YEAR, 2023);
    cal.set(Calendar.MONTH, Calendar.OCTOBER);
    cal.set(Calendar.DAY_OF_MONTH, 1);
    Date startDate = cal.getTime();
    
    // Setting the end date
    cal.set(Calendar.HOUR_OF_DAY, 10);
    Date endDate = cal.getTime();
    
    return new MapiCalendar("Conference Room", "Important Meeting",
        "Discuss project milestones and updates.", startDate, endDate);
}
```

*व्याख्या*: `MapiCalendar` क्लास Aspose.Email का Outlook कैलेंडर आइटम का प्रतिनिधित्व है। बेसिक फ़ील्ड्स सेट करने के बाद आप सहेजने से पहले आवृत्ति, रिमाइंडर, और श्रेणियों को भी कॉन्फ़िगर कर सकते हैं।

## **उपस्थितियों को जोड़ें** (java मीटिंग उपस्थितियों को जोड़ें)

`MapiRecipientCollection` बनाएं, प्रत्येक प्रतिभागी से इसे भरें, और इसे मीटिंग से संलग्न करें। इससे यह सुनिश्चित होता है कि PST खोलने पर हर उपस्थित को उचित निमंत्रण मिले।

`MapiRecipientCollection` एक कलेक्शन क्लास है जो मीटिंग प्रतिभागियों को दर्शाने वाले `MapiRecipient` ऑब्जेक्ट्स को रखता है। `MapiRecipient` एक व्यक्तिगत उपस्थित को ईमेल पता और रिसीपीएंट टाइप जैसी प्रॉपर्टीज़ के साथ दर्शाता है।

```java
public static MapiRecipientCollection buildAttendees(List<String> emails) {
    MapiRecipientCollection attendees = new MapiRecipientCollection();
    for (String email : emails) {
        MapiRecipient recipient = new MapiRecipient(email, email, MapiRecipientType.MAPI_TO);
        attendees.add(recipient);
    }
    return attendees;
}
```

```java
import com.aspose.email.MapiCalendar;
import com.aspose.email.MapiRecipientCollection;
import com.aspose.email.MapiRecipientType;
import java.util.Date;

public MapiCalendar createMeetingWithAttendees(Date startDate, Date endDate) {
    MapiRecipientCollection attendees = new MapiRecipientCollection();
    
    // Adding primary recipients
    attendees.add("attendee1@example.com", "John Doe", MapiRecipientType.MAPI_TO);
    attendees.add("attendee2@example.com", "Jane Smith", MapiRecipientType.MAPI_TO);
    
    return new MapiCalendar(
        "Main Office Boardroom",
        "Team Meeting",
        "Discuss quarterly goals.",
        startDate,
        endDate,
        "organizer@example.com",
        attendees
    );
}
```

*व्याख्या*: `MapiRecipient` एकल मीटिंग प्रतिभागी को परिभाषित करता है। टाइप को `MAPI_TO` सेट करने से पता मुख्य उपस्थित के रूप में चिह्नित होता है, जबकि `MAPI_CC` या `MAPI_BCC` वैकल्पिक प्रतिभागियों के लिए उपयोग किए जा सकते हैं।

## **कैलेंडर को PST में निर्यात करें** (कैलेंडर इवेंट्स के साथ PST बनाएं)

एक Unicode PST फ़ाइल बनाएं, एक "Calendar" फ़ोल्डर जोड़ें, और पहले निर्मित `MapiCalendar` ऑब्जेक्ट्स को सम्मिलित करें। PST को फिर Outlook में खोला जा सकता है या अंतिम उपयोगकर्ताओं को वितरित किया जा सकता है।

`PersonalStorage` Aspose.Email की क्लास है जिसका उपयोग PST फ़ाइलों को बनाने, खोलने और संशोधित करने के लिए किया जाता है।

```java
public static void createPSTWithCalendarEvents(String pstFilePath,
                                                List<MapiCalendar> events) throws Exception {
    // Create a new Unicode PST (supports up to 2 TB)
    PersonalStorage pst = PersonalStorage.create(pstFilePath, FileFormatVersion.Unicode);
    // Add the default Calendar folder
    FolderInfo calendarFolder = pst.getRootFolder().addSubFolder("Calendar", 
                                   StandardIpmFolder.Calendar);
    // Insert each event
    for (MapiCalendar event : events) {
        calendarFolder.addMapiMessageItem(event);
    }
}
```

```java
import com.aspose.email.FileFormatVersion;
import com.aspose.email.FolderInfo;
import com.aspose.email.PersonalStorage;
import com.aspose.email.StandardIpmFolder;

public void createPSTWithCalendarEvents() {
    String pstFilePath = "/path/to/output/MapiCalendarToPST_out.pst";
    
    PersonalStorage pst = PersonalStorage.create(pstFilePath, FileFormatVersion.Unicode);
    FolderInfo calendarFolder = pst.createPredefinedFolder("Calendar", StandardIpmFolder.Appointments);

    MapiCalendar appointment = createAppointment();
    calendarFolder.addMapiMessageItem(appointment);
    
    Date startDate = new Date(); // Use actual dates from your event
    Date endDate = new Date();
    MapiCalendar meeting = createMeetingWithAttendees(startDate, endDate);
    calendarFolder.addMapiMessageItem(meeting);
}
```

*व्याख्या*: `PersonalStorage` PST हेरफेर के लिए प्रवेश बिंदु है। Unicode फ़ॉर्मेट का उपयोग करके आप पुराने PST संस्करणों की 2 GB सीमा से बचते हैं और बड़े अभिलेखों पर तेज़ I/O का लाभ उठाते हैं।

## व्यावहारिक अनुप्रयोग
1. **व्यवसाय शेड्यूलिंग** – आंतरिक मीटिंग निर्माण और वितरण को स्वचालित करें।  
2. **इवेंट मैनेजमेंट** – सम्मेलनों, कार्यशालाओं, और प्रतिभागी सूचियों को ट्रैक करें।  
3. **CRM इंटीग्रेशन** – अपॉइंटमेंट्स को कस्टमर रिलेशनशिप टूल्स के साथ सिंक करें।  
4. **प्रोजेक्ट प्लानिंग** – प्रोजेक्ट माइलस्टोन को कैलेंडर आइटम्स के रूप में संग्रहीत करें।  
5. **रिमोट टीम कोलैबोरेशन** – ऑफ़लाइन शेयरिंग के लिए PST फ़ाइलें जनरेट करें।

## प्रदर्शन संबंधी विचार
- **ऑब्जेक्ट्स को डिस्पोज़** करें जो अब आवश्यक नहीं हैं ताकि मेमोरी तुरंत मुक्त हो सके।  
- **कुशल कलेक्शन का उपयोग करें** (जैसे, `ArrayList` उपस्थितियों की सूची के लिए) जब हजारों प्रतिभागियों को संभाल रहे हों।  
- **बार-बार एक्सेस किए जाने वाले इवेंट्स को कैश करें** यदि आप PST को बार-बार क्वेरी करते हैं, जिससे डिस्क I/O कम हो।

## सामान्य समस्याएँ और समाधान
| समस्या | समाधान |
|-------|----------|
| **PST फ़ाइल नहीं बनी** | लक्ष्य डायरेक्टरी पर लिखने की अनुमति सत्यापित करें और सुनिश्चित करें कि फ़ोल्डर पथ मौजूद है। |
| **उपस्थितियों को निमंत्रण नहीं मिल रहा** | सुनिश्चित करें कि प्रत्येक `MapiRecipient` `MapiRecipientType.MAPI_TO` का उपयोग करता है और आयोजक ईमेल वैध है। |
| **तारीख असंगतता** | `Calendar` को शुरू/समाप्ति तिथियों के लिए लगातार उपयोग करें; बिना रूपांतरण के `java.util.Date` को अन्य डेट लाइब्रेरीज़ के साथ मिलाने से बचें। |

## अक्सर पूछे जाने वाले प्रश्न

**प्र: Aspose.Email for Java के साथ कैसे शुरू करें?**  
उ: ऊपर दिखाए गए Maven निर्भरता को जोड़ें, लाइसेंस प्राप्त करें, और इस गाइड के चरणों का पालन करके कैलेंडर इवेंट्स बनाएं और निर्यात करें।

**प्र: क्या मैं PST फ़ाइल का नाम और स्थान कस्टमाइज़ कर सकता हूँ?**  
उ: हाँ, अपने सिस्टम पर किसी भी वैध पथ के लिए `createPSTWithCalendarEvents()` में `pstFilePath` वेरिएबल बदलें।

**प्र: क्या अपॉइंटमेंट्स में आवृत्ति पैटर्न जोड़ना संभव है?**  
उ: बिल्कुल – `MapiCalendar` एक `RecurrencePattern` प्रॉपर्टी प्रदान करता है जिसे आप सहेजने से पहले कॉन्फ़िगर कर सकते हैं।

**प्र: क्या Aspose.Email PST के अलावा अन्य कैलेंडर फ़ॉर्मेट्स को सपोर्ट करता है?**  
उ: हाँ, आप उपयुक्त API मेथड्स का उपयोग करके iCalendar (`.ics`) और अन्य फ़ॉर्मेट्स में निर्यात कर सकते हैं।

**प्र: मैं अधिकतम कितनी बड़ी PST फ़ाइल बना सकता हूँ?**  
उ: Unicode फ़ॉर्मेट (`FileFormatVersion.Unicode`) के साथ, PST फ़ाइलें 2 TB तक बढ़ सकती हैं, केवल उपलब्ध डिस्क स्पेस द्वारा सीमित।

---

**अंतिम अपडेट:** 2026-08-01  
**परीक्षित संस्करण:** Aspose.Email for Java 25.4 (jdk16 classifier)  
**लेखक:** Aspose  

{{< blocks/products/products-backtop-button >}}

## संबंधित ट्यूटोरियल

- [Aspose.Email for Java में महारत: Outlook PST फ़ाइलों को कुशलतापूर्वक प्रबंधित करें](/email/java/outlook-pst-ost-operations/aspose-email-java-manage-outlook-pst-files/)
- [Aspose.Email for Java के साथ कैलेंडर आइटम बनाना और सहेजना में महारत](/email/java/calendar-appointments/create-save-calendar-items-aspose-email-java/)
- [Aspose.Email का उपयोग करके Java में एक ICS फ़ाइल से कई कैलेंडर इवेंट पढ़ना](/email/java/calendar-appointments/read-multiple-ics-events-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}