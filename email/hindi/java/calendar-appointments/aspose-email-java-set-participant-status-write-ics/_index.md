---
date: '2026-03-18'
description: Aspose.Email for Java के साथ ics फ़ाइलें निर्यात करना, उपस्थितियों की
  स्थिति सेट करना, और कई कैलेंडर इवेंट्स को कुशलतापूर्वक लिखना सीखें।
keywords:
- Aspose.Email Java
- set participant status in Java
- write ICS files with Java
title: ICS निर्यात कैसे करें – स्थिति सेट करें – Aspose.Email जावा
url: /hi/java/calendar-appointments/aspose-email-java-set-participant-status-write-ics/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# How to Export ICS – Set Status – Aspose.Email Java

मीटिंग शेड्यूल को कुशलता से प्रबंधित करना कई पेशेवरों के लिए एक चुनौती है, विशेष रूप से जब विभिन्न टाइम ज़ोन में कई प्रतिभागियों के साथ काम करना हो। इस ट्यूटोरियल में आप **ICS फ़ाइलें कैसे निर्यात करें** Aspose.Email for Java का उपयोग करके, प्रतिभागी (attendee) की स्थिति कैसे सेट करें, और एक ही फ़ाइल में कई कैलेंडर इवेंट्स कैसे लिखें, यह सब स्पष्ट, चरण‑बद्ध कोड के साथ सीखेंगे जिसे आप अपने प्रोजेक्ट में कॉपी कर सकते हैं।

## Quick Answers
- **Can I set attendee status with Aspose.Email for Java?** Yes – you can assign Accepted, Declined, or Tentative values.  
  **क्या मैं Aspose.Email for Java के साथ उपस्थितकर्ता की स्थिति सेट कर सकता हूँ?** हाँ – आप Accepted, Declined, या Tentative मान असाइन कर सकते हैं।  
- **How many events can I write to a single ICS file?** The library supports any number; the example creates ten events.  
  **एक ही ICS फ़ाइल में मैं कितने इवेंट लिख सकता हूँ?** लाइब्रेरी किसी भी संख्या को सपोर्ट करती है; उदाहरण में दस इवेंट बनाते हैं।  
- **Do I need a license for development?** A free temporary license works for evaluation; a purchased license is required for production.  
  **क्या विकास के लिए लाइसेंस चाहिए?** मूल्यांकन के लिए एक मुफ्त टेम्पररी लाइसेंस काम करता है; प्रोडक्शन के लिए खरीदा गया लाइसेंस आवश्यक है।  
- **Which Java version is recommended?** JDK 16 (or later) matches the provided classifier.  
  **कौन सा Java संस्करण अनुशंसित है?** JDK 16 (या बाद का) प्रदान किए गए क्लासिफ़ायर से मेल खाता है।  
- **Is time‑zone handling automatic?** You can specify the time zone when creating dates; the library respects it.  
  **क्या टाइम‑ज़ोन हैंडलिंग ऑटोमैटिक है?** आप डेट बनाते समय टाइम ज़ोन निर्दिष्ट कर सकते हैं; लाइब्रेरी उसका सम्मान करती है।

## What is “how to export ics” and why does it matter?
ICS (iCalendar) फ़ॉर्मेट Outlook, Google Calendar, Apple Calendar और कई अन्य क्लाइंट्स के बीच कैलेंडर जानकारी साझा करने का डि‑फैक्ट मानक है। ICS में निर्यात करने से आप मीटिंग इनवाइट्स वितरित कर सकते हैं, बड़े पैमाने पर इवेंट्स बना सकते हैं, या लेगेसी सिस्टम्स को इंटीग्रेट कर सकते हैं बिना प्रतिभागी की स्थिति या कस्टम प्रॉपर्टीज़ खोए।

## Why use Aspose.Email for Java to export ics?
- **Full control** over attendee responses (Accepted/Declined/Tentative).  
  **पूर्ण नियंत्रण** उपस्थितकर्ता प्रतिक्रियाओं (Accepted/Declined/Tentative) पर।  
- **No external dependencies** – the library handles all iCalendar specifications internally.  
  **कोई बाहरी निर्भरताएँ नहीं** – लाइब्रेरी सभी iCalendar स्पेसिफ़िकेशन internally संभालती है।  
- **Bulk writing** – you can generate dozens or hundreds of events with a single writer, keeping file handles efficient.  
  **बुल्क राइटिंग** – आप एक ही राइटर से दर्जनों या सैकड़ों इवेंट जनरेट कर सकते हैं, जिससे फ़ाइल हैंडल्स कुशल रहते हैं।  
- **Cross‑platform compatibility** – generated ICS files work on any calendar client that follows the RFC 5545 standard.  
  **क्रॉस‑प्लेटफ़ॉर्म संगतता** – जनरेट की गई ICS फ़ाइलें किसी भी कैलेंडर क्लाइंट पर काम करती हैं जो RFC 5545 मानक का पालन करता है।

## Prerequisites

शुरू करने से पहले सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

### Required Libraries and Versions
- **Aspose.Email for Java** version 25.4 or later.  
- Maven for dependency management (or download directly from [Aspose](https://releases.aspose.com/email/java/)).

### Environment Setup Requirements
- आपके मशीन पर Java Development Kit (JDK) स्थापित होना चाहिए, अनुशंसित रूप से JDK 16 ताकि इस ट्यूटोरियल में उपयोग किए गए Aspose.Email क्लासिफ़ायर से मेल खाए।  
- IntelliJ IDEA या Eclipse जैसे Integrated Development Environment (IDE)।

### Knowledge Prerequisites
- बेसिक Java प्रोग्रामिंग स्किल्स।  
- `java.util.Calendar` और `java.util.Date` के साथ डेट‑टाइम हैंडलिंग की परिचितता।

## Setting Up Aspose.Email for Java

Maven प्रोजेक्ट में Aspose.Email लाइब्रेरी जोड़ें:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### License Acquisition Steps

1. **Free Trial** – Download a temporary license to test Aspose.Email without restrictions. Visit [Aspose Temporary License](https://purchase.aspose.com/temporary-license/) for details.  
2. **Purchase** – For long‑term use, buy a subscription at [Aspose Purchase](https://purchase.aspose.com/buy).

कोड में लाइसेंस इनिशियलाइज़ करें:

```java
com.aspose.email.License license = new com.aspose.email.License();
license.setLicense("path/to/your/license.lic");
```

अब आप इस गाइड की दो मुख्य सुविधाओं में डुबकी लगाने के लिए तैयार हैं।

## How to export ics: Set Participant Status of Appointment Attendees

### What is participant status in a calendar appointment?
Participant status दर्शाता है कि एक उपस्थितकर्ता ने मीटिंग इनवाइट पर कैसे प्रतिक्रिया दी है—Accepted, Declined, या Tentative। Aspose.Email for Java का उपयोग करके आप इन मानों को प्रोग्रामेटिकली सेट कर सकते हैं, जो ऑटोमेटेड शेड्यूलिंग सिस्टम्स और **java calendar appointment** मैनेजमेंट के लिए आवश्यक है।

### Step‑by‑step implementation

#### 1️⃣ Create and configure the appointment dates

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

#### 2️⃣ Define the organizer and the attendee list

```java
MailAddress organizer = new MailAddress("aaa@amail.com", "Organizer");

// Initialize attendee list
MailAddressCollection attendees = new MailAddressCollection();
```

#### 3️⃣ Assign participation status to each attendee

```java
MailAddress attendee1 = new MailAddress("bbb@bmail.com", "First attendee");
MailAddress attendee2 = new MailAddress("ccc@cmail.com", "Second attendee");

// Set statuses
attendee1.setParticipationStatus(ParticipationStatus.Accepted);
attendee2.setParticipationStatus(ParticipationStatus.Declined);

attendees.addMailAddress(attendee1);
attendees.addMailAddress(attendee2);
```

#### 4️⃣ Create the `Appointment` object

```java
Appointment target = new Appointment(location, startDate, endDate, organizer, attendees);
```

**Pro tip:** Always verify that email addresses are correctly formatted; otherwise, the library may throw parsing errors.  
**प्रो टिप:** हमेशा सुनिश्चित करें कि ई‑मेल एड्रेस सही फॉर्मेट में हैं; अन्यथा लाइब्रेरी पार्सिंग एरर फेंक सकती है।

## How to export ics: Write Multiple Events to an ICS File

### Why export calendar to ics with Java?
ICS फ़ॉर्मेट सार्वभौमिक रूप से समझा जाता है, जिससे आप मीटिंग जानकारी Outlook, Google Calendar, Apple Calendar और कई अन्य क्लाइंट्स के साथ साझा कर सकते हैं। Aspose.Email के साथ **write ics file java** करने से आप प्रतिभागी की स्थिति, कस्टम प्रॉपर्टीज़ और रिकरेंस रूल्स को अतिरिक्त कन्वर्ज़न स्टेप्स के बिना संरक्षित रख सकते हैं।

### Step‑by‑step implementation

#### 1️⃣ Configure save options and create a writer

```java
IcsSaveOptions saveOptions = new IcsSaveOptions();
saveOptions.setAction(AppointmentAction.Create);

CalendarWriter writer = new CalendarWriter("YOUR_OUTPUT_DIRECTORY/WriteMultipleEventsToICS_out.ics", saveOptions);
```

#### 2️⃣ Define the time frame for each event

```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2018, Calendar.JUNE, 19, 19, 0, 0); // Start time
Date startDate = calendar.getTime();
calendar.set(2018, Calendar.JUNE, 19, 20, 0, 0); // End time
Date endDate = calendar.getTime();
```

#### 3️⃣ Prepare the attendees collection

```java
MailAddressCollection attendees = new MailAddressCollection();
attendees.addItem(new MailAddress("recepientEmail@gmail.com"));
```

#### 4️⃣ Generate and write multiple appointments

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

**Common pitfall:** Forgetting to call `writer.dispose()` can leave file handles open, causing access errors on subsequent runs.  
**सामान्य गलती:** `writer.dispose()` को कॉल करना न भूलें, अन्यथा फ़ाइल हैंडल खुले रहेंगे और बाद के रन में एक्सेस एरर हो सकता है।

## Practical Applications

Aspose.Email for Java कई वास्तविक‑दुनिया परिदृश्यों में चमकता है:

1. **Automated Meeting Scheduling** – Generate calendar invites on‑the‑fly for internal tools or CRM systems.  
2. **Cross‑Platform Calendar Integration** – Export appointments from legacy systems to Outlook, Google Calendar, or Apple Calendar using the standard ICS format.  
3. **Event Management Platforms** – Bulk‑create schedules for conferences, workshops, or webinars with a single API call.

## Performance Considerations

जब आप **aspose email java** के साथ काम कर रहे हों, तो इन टिप्स को ध्यान में रखें:

- `CalendarWriter` (या कोई भी `MailMessage`/`Appointment`) ऑब्जेक्ट को उपयोग समाप्त होते ही डिस्पोज़ करें।  
- बड़े डेटा सेट को हैंडल करते समय अपॉइंटमेंट्स को बैच‑प्रोसेस करें ताकि गैर्बेज‑कलेक्शन ओवरहेड कम हो।  
- प्रत्येक राइट ऑपरेशन के लिए नया `IcsSaveOptions` बनाने के बजाय एक ही इंस्टेंस को री‑यूज़ करें।

## Frequently Asked Questions

**Q: Can I update an existing ICS file instead of creating a new one?**  
A: Yes. Set `saveOptions.setAction(AppointmentAction.Modify)` and provide the UID of the appointment you wish to update.

**Q: Does Aspose.Email support recurring events?**  
A: Absolutely. Configure recurrence patterns on the `Appointment` object before writing to the ICS file.

**Q: Is it possible to add custom properties to an ICS event?**  
A: Yes. Use `appointment.getCustomProperties().add("X‑MyProperty", "MyValue")` to embed non‑standard fields.

**Q: What time‑zone formats are accepted?**  
A: Both IANA time‑zone IDs (e.g., “America/New_York”) and GMT offsets are supported.

**Q: Do I need a license for development builds?**  
A: A temporary license removes evaluation restrictions; a full license is required for production deployments.

## Conclusion

आपने अब **ICS फ़ाइलें कैसे निर्यात करें**, प्रतिभागी की स्थिति कैसे सेट करें, और Aspose.Email for Java का उपयोग करके कई इवेंट्स कैसे लिखें, यह सीख लिया है। ये क्षमताएँ आपको मजबूत शेड्यूलिंग फीचर्स बनाने, किसी भी कैलेंडर क्लाइंट के साथ इंटीग्रेट करने, और आपके संगठन में इवेंट वितरण को सहज बनाने में मदद करती हैं।

---

**Last Updated:** 2026-03-18  
**Tested With:** Aspose.Email for Java 25.4 (jdk16 classifier)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}