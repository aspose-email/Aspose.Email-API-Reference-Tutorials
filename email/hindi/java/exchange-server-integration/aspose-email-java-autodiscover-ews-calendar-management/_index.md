---
date: '2026-06-28'
description: Aspose.Email for Java के साथ Exchange URL को ऑटोडिस्कवर करना और Exchange
  Web Services कैलेंडर सुविधाओं का उपयोग करना सीखें। सहज एकीकरण के लिए step‑by‑step
  गाइड।
keywords:
- how to autodiscover exchange
- exchange web services calendar
- aspose email java example
schemas:
- author: Aspose
  dateModified: '2026-06-28'
  description: Learn how to autodiscover exchange URLs and use exchange web services
    calendar features with Aspose.Email for Java. Step‑by‑step guide for seamless
    integration.
  headline: How to Autodiscover Exchange with Aspose.Email Java & EWS
  type: TechArticle
- description: Learn how to autodiscover exchange URLs and use exchange web services
    calendar features with Aspose.Email for Java. Step‑by‑step guide for seamless
    integration.
  name: How to Autodiscover Exchange with Aspose.Email Java & EWS
  steps:
  - name: '**Download the Library** from the official releases page – see [Releases](https://releases.aspose.com/email/java/)
      or [Aspose Releases](https://releases.aspose.com/email/java/).'
    text: '**Download the Library** from the official releases page – see [Releases](https://releases.aspose.com/email/java/)
      or [Aspose Releases](https://releases.aspose.com/email/java/).'
  - name: '**Get a Temporary License** from the temporary‑license portal – see [Aspose''s
      Purchase Page](https://purchase.aspose.com/temporary-license/) or [Aspose Temporary
      License Page](https://purchase.aspose.com/temporary-license/).'
    text: '**Get a Temporary License** from the temporary‑license portal – see [Aspose''s
      Purchase Page](https://purchase.aspose.com/temporary-license/) or [Aspose Temporary
      License Page](https://purchase.aspose.com/temporary-license/).'
  - name: '**Purchase a Full License** for production use – see [Aspose Purchase](https://purchase.aspose.com/buy)
      or [Purchase Page](https://purchase.aspose.com/buy).'
    text: '**Purchase a Full License** for production use – see [Aspose Purchase](https://purchase.aspose.com/buy)
      or [Purchase Page](https://purchase.aspose.com/buy).'
  - name: '**Establish Credentials and Create Client** – instantiate `ExchangeClient`
      with the autodiscovered URL and user credentials.'
    text: '**Establish Credentials and Create Client** – instantiate `ExchangeClient`
      with the autodiscovered URL and user credentials.'
  - name: '**Create a CalendarMessage** – set subject, start/end times, location,
      and attendees.'
    text: '**Create a CalendarMessage** – set subject, start/end times, location,
      and attendees.'
  - name: '**Write with CalendarWriter** – call `write` to persist the event on the
      server.'
    text: '**Write with CalendarWriter** – call `write` to persist the event on the
      server.'
  type: HowTo
- questions:
  - answer: JDK 16+, Maven, and a valid Aspose.Email license (temporary for trial).
    question: What are the prerequisites for using Aspose.Email Java?
  - answer: Use `AutodiscoverService` to request user settings; the `ExternalEwsUrl`
      field contains the endpoint.
    question: How do I obtain an EWS URL for a specific email address?
  - answer: Yes – with batching and proper JVM tuning it can process thousands of
      events per minute.
    question: Can Aspose.Email handle large volumes of calendar events?
  - answer: Incorrect credentials, DNS misconfiguration, or blocked outbound ports
      are typical culprits.
    question: What are some common issues when using AutodiscoverService?
  - answer: Visit the official purchase page – see [Aspose Purchase](https://purchase.aspose.com/buy).
    question: How can I purchase a full license for Aspose.Email?
  type: FAQPage
title: Aspose.Email Java & EWS के साथ Exchange को ऑटोडिस्कवर कैसे करें
url: /hi/java/exchange-server-integration/aspose-email-java-autodiscover-ews-calendar-management/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# मुख्य ईमेल ऑटोमेशन: Aspose.Email Java & EWS for Exchange Server Integration

आज के तेज़‑गति वाले डिजिटल माहौल में, **how to autodiscover exchange** वह मूलभूत कौशल है जो किसी भी Java एप्लिकेशन के लिए आवश्यक है जो Microsoft Exchange से संवाद करता है। Aspose.Email for Java को Exchange Web Services (EWS) के साथ उपयोग करके आप सही EWS एंडपॉइंट को स्वचालित रूप से खोज सकते हैं और URLs को हार्ड‑कोड किए बिना कैलेंडर डेटा लिख सकते हैं। यह ट्यूटोरियल आपको Maven सेटअप से लेकर कैलेंडर इवेंट्स बनाने तक हर कदम में मार्गदर्शन करता है, ताकि आप ईमेल वर्कफ़्लो को सुव्यवस्थित कर सकें और उत्पादकता बढ़ा सकें।

## त्वरित उत्तर
- **What is the first step to autodiscover an Exchange URL?** Initialize `AutodiscoverService` with proper credentials and call `GetUserSettings`.  
  **पहला कदम क्या है Exchange URL को autodiscover करने का?** सही क्रेडेंशियल्स के साथ `AutodiscoverService` को इनिशियलाइज़ करें और `GetUserSettings` को कॉल करें।  
- **Which class writes calendar items to Exchange?** `CalendarWriter` handles creation and submission of iCalendar‑compatible messages.  
  **कौन सा क्लास कैलेंडर आइटम्स को Exchange में लिखता है?** `CalendarWriter` iCalendar‑compatible संदेशों के निर्माण और सबमिशन को संभालता है।  
- **Do I need a license for development?** A temporary license works for evaluation; a full license is required for production.  
  **क्या विकास के लिए लाइसेंस चाहिए?** मूल्यांकन के लिए एक अस्थायी लाइसेंस काम करता है; प्रोडक्शन के लिए पूर्ण लाइसेंस आवश्यक है।  
- **What Java version is required?** JDK 16 or higher is recommended for optimal compatibility.  
  **कौन सा Java संस्करण आवश्यक है?** इष्टतम संगतता के लिए JDK 16 या उससे ऊपर की सलाह दी जाती है।  
- **Can I batch multiple calendar events?** Yes – create several `CalendarMessage` objects and send them in a single `ExchangeClient` session.  
  **क्या मैं कई कैलेंडर इवेंट्स को बैच कर सकता हूँ?** हाँ – कई `CalendarMessage` ऑब्जेक्ट्स बनाएँ और उन्हें एक ही `ExchangeClient` सत्र में भेजें।

## AutodiscoverService क्या है?
`AutodiscoverService` Aspose.Email का हेल्पर है जो Microsoft के Autodiscover एंडपॉइंट से संपर्क करता है, उपयोगकर्ता को प्रमाणित करता है, और बाहरी EWS URL जैसी कॉन्फ़िगरेशन सेटिंग्स लौटाता है। यह सर्विस एड्रेस को हार्ड‑कोड करने की अटकलों को समाप्त करता है।

## Aspose.Email के साथ Exchange Web Services Calendar का उपयोग क्यों करें?
Aspose.Email **50+** इनपुट और आउटपुट फ़ॉर्मेट्स को सपोर्ट करता है और बैचिंग के समय **सैकड़ों कैलेंडर आइटम्स प्रति मिनट** प्रोसेस कर सकता है, इसके कम‑ओवरहेड HTTP हैंडलिंग के कारण। EWS का उपयोग करके आप सर्वर‑साइड विश्वसनीयता, पूर्ण अनुमति नियंत्रण, और सभी Exchange क्लाइंट्स में मीटिंग अपडेट्स का त्वरित प्रसारण प्राप्त करते हैं।

## पूर्वापेक्षाएँ

- **Java Development Kit (JDK)** 16+ स्थापित हो।  
- **Maven** निर्भरता प्रबंधन के लिए।  
- **Aspose.Email for Java** लाइब्रेरी (आधिकारिक साइट से डाउनलोड करें)।  
- Java सिंटैक्स और Maven प्रोजेक्ट संरचना की बुनियादी परिचितता।

## Aspose.Email for Java सेटअप

### Maven इंस्टॉलेशन

अपने `pom.xml` में Aspose.Email डिपेंडेंसी जोड़ें। यह एकल लाइन Maven Central से नवीनतम स्थिर रिलीज़ को पुल करती है:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### लाइसेंस प्राप्ति

Aspose.Email मूल्यांकन के लिए एक फ्री ट्रायल और अस्थायी लाइसेंस प्रदान करता है। नीचे दिए गए चरणों का पालन करें:

1. **लाइब्रेरी डाउनलोड करें** आधिकारिक रिलीज़ पेज से – देखें [Releases](https://releases.aspose.com/email/java/) या [Aspose Releases](https://releases.aspose.com/email/java/)।  
2. **अस्थायी लाइसेंस प्राप्त करें** अस्थायी‑लाइसेंस पोर्टल से – देखें [Aspose's Purchase Page](https://purchase.aspose.com/temporary-license/) या [Aspose Temporary License Page](https://purchase.aspose.com/temporary-license/)।  
3. **पूर्ण लाइसेंस खरीदें** प्रोडक्शन उपयोग के लिए – देखें [Aspose Purchase](https://purchase.aspose.com/buy) या [Purchase Page](https://purchase.aspose.com/buy)।

`.lic` फ़ाइल मिलने के बाद, इसे एप्लिकेशन स्टार्ट पर लोड करें:

```java
// Load the license file
License license = new License();
license.setLicense("path_to_license.lic");
```

## कार्यान्वयन गाइड

### EWS का उपयोग करके Exchange URL को Autodiscover कैसे करें?
सही EWS एंडपॉइंट खोजने के लिए, उपयोगकर्ता के क्रेडेंशियल्स के साथ `AutodiscoverService` का इंस्टैंस बनाएं, फिर `ExternalEwsUrl` सेटिंग का अनुरोध करते हुए `GetUserSettings` कॉल करें। सर्विस Microsoft के Autodiscover एंडपॉइंट से संपर्क करती है, रीडायरेक्ट्स का पालन करती है, और वह URL लौटाती है जिसका उपयोग आगे के ऑपरेशन्स के लिए `ExchangeClient` बनाने में किया जा सकता है।

```java
import com.aspose.email.AutodiscoverService;
import com.aspose.email.UserSettingName;
import com.aspose.email.system.NetworkCredential;

// Create an instance of AutodiscoverService
AutodiscoverService svc = new AutodiscoverService();

// Set credentials for the service using a NetworkCredential object
svc.setCredentials(new NetworkCredential("username@domain.com", "password"));
```

### EWS का उपयोग करके Exchange में कैलेंडर इवेंट्स कैसे लिखें?
EWS URL प्राप्त करने के बाद, खोजे गए एंडपॉइंट और उपयोगकर्ता क्रेडेंशियल्स के साथ `ExchangeClient` बनाएं। इच्छित विषय, समय, स्थान, और उपस्थितियों के साथ `CalendarMessage` बनाएं, फिर इसे `CalendarWriter.write` को पास करें जो डेटा को iCalendar फ़ॉर्मेट में बदलता है और इवेंट को Exchange सर्वर पर स्टोर करता है।

`CalendarWriter` वह क्लास है जो EWS के माध्यम से Exchange सर्वर पर कैलेंडर आइटम्स लिखता है।  
`ExchangeClient` Exchange सर्वर के साथ कनेक्शन का प्रतिनिधित्व करता है और आइटम्स भेजने व प्राप्त करने के मेथड्स प्रदान करता है।  
`CalendarMessage` कैलेंडर इवेंट के विवरण जैसे विषय, समय, स्थान, और उपस्थितियों को एन्कैप्सुलेट करता है।

```java
import com.aspose.email.system.collections.generic.IGenericDictionary;

// Obtain user settings, specifically for ExternalEwsUrl
IGenericDictionary<Integer, Object> userSettings = svc.getUserSettings("email@example.com", UserSettingName.ExternalEwsUrl).getSettings();

// Retrieve and cast the EWS URL from the dictionary
String ewsUrl = (String)userSettings.get_Item(UserSettingName.ExternalEwsUrl);

System.out.println("External EWS URL: " + ewsUrl);
```

### कैलेंडर लेखन के विस्तृत चरण

1. **क्रेडेंशियल्स स्थापित करें और क्लाइंट बनाएं** – autodiscovered URL और उपयोगकर्ता क्रेडेंशियल्स के साथ `ExchangeClient` को इंस्टैंसिएट करें।  
2. **CalendarMessage बनाएं** – विषय, शुरू/समाप्ति समय, स्थान, और उपस्थितियों को सेट करें।  
3. **CalendarWriter के साथ लिखें** – इवेंट को सर्वर पर स्थायी करने के लिए `write` को कॉल करें।

```java
import com.aspose.email.ExchangeCredentials;
import com.aspose.email.ExchangeClient;

// Establish credentials and create an Exchange client
ExchangeCredentials credentials = new ExchangeCredentials("username@domain.com", "password");
ExchangeClient client = new ExchangeClient(ewsUrl, credentials);
```

```java
import com.aspose.email.CalendarWriter;
import com.aspose.email.MailMessage;
import java.util.Date;

// Create a calendar message
MailMessage calendarMessage = MailMessage.createAppointment(
    "from@example.com",
    "to@example.com",
    "Meeting Subject",
    "Location",
    new Date(),
    new Date(System.currentTimeMillis() + 3600000)); // Set for one hour from now

// Initialize CalendarWriter and specify the folder to write to
CalendarWriter writer = new CalendarWriter(client, "YOUR_DOCUMENT_DIRECTORY", "CalendarFolderName");

// Write the calendar message to Exchange Server
writer.write(calendarMessage);
```

## व्यावहारिक अनुप्रयोग

- **स्वचालित मीटिंग शेड्यूलिंग** – बैक‑ऑफ़िस सिस्टम से तुरंत आमंत्रण उत्पन्न करें।  
- **इवेंट मैनेजमेंट प्लेटफ़ॉर्म** – मैन्युअल एंट्री के बिना कॉर्पोरेट कैलेंडर को सिंक्रनाइज़ रखें।  
- **CRM इंटीग्रेशन** – बिक्री कॉल और फॉलो‑अप मीटिंग्स को सीधे उपयोगकर्ताओं के Exchange कैलेंडर में लॉग करें।

## प्रदर्शन विचार

- **बैच अनुरोध**: कई `CalendarMessage` ऑब्जेक्ट्स को एक ही `ExchangeClient` सत्र में समूहित करें ताकि राउंड‑ट्रिप्स कम हों।  
- **मेमोरी प्रबंधन**: बड़े बैच इवेंट्स को संभालते समय JVM हीप (`-Xmx2g` या अधिक) को समायोजित करें।  
- **लाइब्रेरी अपडेट**: Aspose.Email को अद्यतित रखें; प्रत्येक रिलीज़ प्रदर्शन सुधार और नई EWS सुविधाएँ जोड़ती है।

## सामान्य समस्याएँ और समाधान

- **अवैध क्रेडेंशियल्स** – उपयोगकर्ता नाम फ़ॉर्मेट (`domain\user` या `user@domain.com`) को दोबारा जांचें।  
- **नेटवर्क फ़ायरवॉल** – Autodiscover एंडपॉइंट के लिए आउटबाउंड HTTPS ट्रैफ़िक के लिए पोर्ट 443 और 80 खुले हों यह सुनिश्चित करें।  
- **TLS संस्करण** – Exchange को TLS 1.2 या उससे ऊपर चाहिए; JVM को उसी अनुसार कॉन्फ़िगर करें (`-Dhttps.protocols=TLSv1.2`)।

## अक्सर पूछे जाने वाले प्रश्न

**Q: Aspose.Email Java उपयोग करने के लिए पूर्वापेक्षाएँ क्या हैं?**  
A: JDK 16+, Maven, और एक वैध Aspose.Email लाइसेंस (ट्रायल के लिए अस्थायी)।

**Q: किसी विशिष्ट ईमेल एड्रेस के लिए EWS URL कैसे प्राप्त करूँ?**  
A: `AutodiscoverService` का उपयोग करके यूज़र सेटिंग्स का अनुरोध करें; `ExternalEwsUrl` फ़ील्ड में एंडपॉइंट होता है।

**Q: क्या Aspose.Email बड़े पैमाने पर कैलेंडर इवेंट्स को संभाल सकता है?**  
A: हाँ – बैचिंग और उचित JVM ट्यूनिंग के साथ यह प्रति मिनट हजारों इवेंट्स प्रोसेस कर सकता है।

**Q: AutodiscoverService उपयोग करते समय कुछ सामान्य समस्याएँ क्या हैं?**  
A: गलत क्रेडेंशियल्स, DNS मिसकॉन्फ़िगरेशन, या आउटबाउंड पोर्ट ब्लॉक होना आम कारण हैं।

**Q: Aspose.Email के लिए पूर्ण लाइसेंस कैसे खरीदूँ?**  
A: आधिकारिक खरीद पेज पर जाएँ – देखें [Aspose Purchase](https://purchase.aspose.com/buy)।

## संसाधन

- **Documentation**: व्यापक गाइड और API रेफ़रेंसेज़ [Aspose Email Java Documentation](https://reference.aspose.com/email/java/) पर उपलब्ध हैं।  
- **Download**: लाइब्रेरी डाउनलोड्स के लिए [Aspose Releases](https://releases.aspose.com/email/java/) देखें।  
- **Free Trial**: फ्री ट्रायल के लिए [Aspose Email Java Free Trial](https://releases.aspose.com/email/java/) पर शुरू करें।  
- **Purchase**: लाइसेंस विकल्पों के लिए [Aspose Purchase](https://purchase.aspose.com/buy) देखें।  
- **Temporary License**: अस्थायी लाइसेंस के माध्यम से पूरी सुविधाएँ आज़माएँ [Aspose Temporary License Page](https://purchase.aspose.com/temporary-license/)।  
- **Forum**: समुदाय सहायता के लिए [Aspose Forum](https://forum.aspose.com/c/email/10) पर जाएँ।  

---

**Last Updated:** 2026-06-28  
**Tested With:** Aspose.Email for Java 23.12 (latest at time of writing)  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## संबंधित ट्यूटोरियल

- [How to Connect to Exchange Server using Aspose.Email in Java: Step-by-Step Guide](/email/java/exchange-server-integration/aspose-email-java-exchange-server-connection/)
- [How to Create an EWSClient Instance Using Aspose.Email for Java: Exchange Server Integration Guide](/email/java/exchange-server-integration/ewsclient-instance-aspose-email-java/)
- [Guide to Connecting Exchange Calendar with Aspose.Email for Java | Exchange Server Integration](/email/java/exchange-server-integration/exchange-calendar-connection-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}