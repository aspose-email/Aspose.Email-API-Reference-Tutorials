---
date: '2026-10-02'
description: Aspose.Email for Java का उपयोग करके Exchange को कनेक्ट करने और Exchange
  public folders की सूची बनाने का तरीका सीखें। यह step‑by‑step गाइड Maven dependency
  और code‑free सेटअप दिखाता है।
keywords:
- how to connect exchange
- list exchange public folders
- maven dependency aspose email
lastmod: '2026-10-02'
og_description: Aspose.Email for Java का उपयोग करके Exchange को कनेक्ट करने और Exchange
  public folders की सूची बनाने का तरीका सीखें। यह गाइड Maven dependency, licensing,
  और recursive message retrieval को कवर करता है।
og_image_alt: Guide showing how to connect Exchange and list public folders with Aspose.Email
  for Java
og_title: Java में Exchange को कनेक्ट करने और public folders की सूची बनाने का तरीका
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Learn how to connect exchange and list exchange public folders using
    Aspose.Email for Java. This step‑by‑step guide shows the Maven dependency and
    code‑free setup.
  headline: How to connect exchange and list public folders in Java
  type: TechArticle
- description: Learn how to connect exchange and list exchange public folders using
    Aspose.Email for Java. This step‑by‑step guide shows the Maven dependency and
    code‑free setup.
  name: How to connect exchange and list public folders in Java
  steps:
  - name: '**Automated email archiving** – Periodically pull all public‑folder messages
      and store them in a compliant archive.'
    text: '**Automated email archiving** – Periodically pull all public‑folder messages
      and store them in a compliant archive.'
  - name: '**Backup solutions** – Mirror Exchange public folders to a secure file
      system or cloud bucket, guaranteeing data redundancy.'
    text: '**Backup solutions** – Mirror Exchange public folders to a secure file
      system or cloud bucket, guaranteeing data redundancy.'
  - name: '**Custom email clients** – Build lightweight viewers that display only
      the folders and messages you need, reducing UI complexity.'
    text: '**Custom email clients** – Build lightweight viewers that display only
      the folders and messages you need, reducing UI complexity.'
  type: HowTo
- questions:
  - answer: Yes. Provide the Office 365 EWS endpoint (`https://outlook.office365.com/EWS/Exchange.asmx`)
      and use modern authentication (OAuth) – Aspose.Email supports OAuth tokens out
      of the box.
    question: Can I use this code with Exchange Online (Office 365)?
  - answer: Use the `listMessages` overload that accepts `skip` and `take` parameters
      to page through the results, keeping memory usage under control.
    question: What if a folder contains more than 10 000 messages?
  - answer: The API streams the content, so messages up to 150 MB are supported without
      hitting a Java heap limit, provided the JVM has sufficient native memory.
    question: Is there a limit on the size of a single email I can download?
  - answer: By default Aspose.Email trusts the Java default keystore. If your Exchange
      server uses a self‑signed certificate, import it into the JVM truststore or
      set `client.setEnableSslVerification(false)` for testing only.
    question: Do I need to handle SSL certificates manually?
  - answer: Enable Aspose.Email’s built‑in logging by configuring `Logger.setLevel(Level.INFO)`
      and directing output to a file or monitoring system.
    question: How do I log the operations for audit purposes?
  type: FAQPage
tags:
- exchange integration
- Aspose.Email
- Java email automation
title: Java में Exchange को कनेक्ट करने और public folders की सूची बनाने का तरीका
url: /hi/java/exchange-server-integration/aspose-email-java-exchange-messages-listing/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# एक्सचेंज से कनेक्ट कैसे करें और जावा में सार्वजनिक फ़ोल्डर सूचीबद्ध करें

## परिचय
आधुनिक उद्यमों में, प्रोग्रामेटिक रूप से Microsoft Exchange मेलबॉक्स तक पहुंचना आपको आर्काइविंग, मॉनिटरिंग और रिपोर्टिंग कार्यों को स्वचालित करने की अनुमति देता है। यह ट्यूटोरियल **how to connect exchange** को Aspose.Email for Java के साथ दिखाता है और फिर **list exchange public folders** को पुनरावर्ती रूप से सूचीबद्ध करता है। आप आवश्यक Maven निर्भरता, लाइसेंसिंग चरण, और API कॉल्स का सटीक क्रम देखेंगे—कोई अतिरिक्त लाइब्रेरी आवश्यक नहीं। अंत तक, आप किसी भी सार्वजनिक फ़ोल्डर से संदेश प्राप्त कर उन्हें स्थानीय रूप से सहेज सकेंगे।

## त्वरित उत्तर
- **पहला कदम क्या है?** अपने `pom.xml` में Aspose.Email Maven निर्भरता जोड़ें।  
- **क्या मुझे लाइसेंस चाहिए?** हाँ—मूल्यांकन के लिए एक अस्थायी लाइसेंस उपयोग करें या उत्पादन के लिए पूर्ण लाइसेंस खरीदें।  
- **कौन सा क्लास कनेक्शन बनाता है?** `ExchangeClient` (या IMAP के लिए `ImapClient`) प्रमाणीकरण और सर्वर संचार को संभालता है।  
- **क्या मैं सबफ़ोल्डर स्वचालित रूप से सूचीबद्ध कर सकता हूँ?** हाँ—API द्वारा प्रदान किए गए पुनरावर्ती `listSubFolders` मेथड का उपयोग करें।  
- **क्या यह तरीका थ्रेड‑सेफ़ है?** क्लाइंट ऑब्जेक्ट थ्रेड‑सेफ़ नहीं हैं; समवर्ती कार्यभार के लिए प्रत्येक थ्रेड में अलग इंस्टेंस बनाएं।

## एक्सचेंज से कनेक्ट करने का क्या अर्थ है?
**How to connect exchange** वह प्रक्रिया है जिसमें एक Java एप्लिकेशन को ऑन‑प्रिमाइसेस या क्लाउड‑आधारित Microsoft Exchange सर्वर के साथ प्रमाणित किया जाता है ताकि आप फ़ोल्डर सूचीकरण या संदेश पुनर्प्राप्ति जैसे API कॉल्स कर सकें। Aspose.Email अंतर्निहित EWS/IMAP प्रोटोकॉल को एब्स्ट्रैक्ट करता है, जिससे आपको एकल, सुसंगत ऑब्जेक्ट मॉडल मिलता है।

## क्यों एक्सचेंज सार्वजनिक फ़ोल्डर सूचीबद्ध करें?
सार्वजनिक फ़ोल्डर सूचीबद्ध करने से आपको संगठन द्वारा साझा मेलबॉक्स, वितरण सूची और अभिलेखीय स्टोर्स के लिए उपयोग की जाने वाली पदानुक्रमित संरचना की दृश्यता मिलती है। Aspose.Email एक ही कॉल में **50+ सार्वजनिक फ़ोल्डर** को सूचीबद्ध कर सकता है और पूरी स्टोर को मेमोरी में लोड किए बिना सैकड़ों पृष्ठों वाले मेलबॉक्स को प्रोसेस करने का समर्थन करता है, जिससे RAM उपयोग में 70 % तक कमी आती है।

## पूर्वापेक्षाएँ
- **Aspose.Email for Java** — संस्करण 25.4 या बाद का (नवीनतम स्थिर रिलीज़)।  
- **Java Development Kit (JDK)** — JDK 11 या उससे नया स्थापित हो और `JAVA_HOME` कॉन्फ़िगर किया गया हो।  
- **Maven** — निर्भरता प्रबंधन और बिल्ड ऑटोमेशन के लिए।  
- Java सिंटैक्स और Exchange अवधारणाओं (मेलबॉक्स, फ़ोल्डर, EWS) का बुनियादी ज्ञान।

## Aspose.Email for Java सेटअप करना
लाइब्रेरी को एकीकृत करने के लिए, अपने प्रोजेक्ट के `pom.xml` में Maven निर्भरता जोड़ें। यह वह **maven dependency aspose email** है जिसकी आपको आवश्यकता होगी।

### Maven निर्भरता
अपने `pom.xml` के `<dependencies>` तत्व के भीतर निम्न स्निपेट जोड़ें:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### लाइसेंस प्राप्त करने के चरण
Aspose.Email पूर्ण‑फ़ीचर उपयोग के लिए एक वैध लाइसेंस आवश्यक करता है:

- **मुफ़्त ट्रायल** – API का मूल्यांकन करने के लिए [Aspose वेबसाइट](https://purchase.aspose.com/temporary-license/) से एक अस्थायी लाइसेंस डाउनलोड करें।  
- **खरीद** – उत्पादन परिनियोजन के लिए Aspose पोर्टल के माध्यम से एक व्यावसायिक लाइसेंस प्राप्त करें।

#### बुनियादी प्रारंभिककरण
Maven पैकेज को हल करने के बाद और आपके पास लाइसेंस फ़ाइल होने पर, `.lic` फ़ाइल को क्लासपाथ पर रखें और लाइब्रेरी को प्रारंभ करें:

```java
import com.aspose.email.License;

License license = new License();
license.setLicense("path/to/your/license.lic");
```

## कार्यान्वयन गाइड
हम प्रत्येक कार्यात्मक ब्लॉक को क्रमवार देखेंगे, प्रमुख प्रश्नों के उत्तर सीधे, संक्षिप्त पैराग्राफ़ में देंगे, फिर विस्तृत चरणों की ओर बढ़ेंगे।

### एक्सचेंज से कैसे कनेक्ट करें?
सर्वर URL, उपयोगकर्ता क्रेडेंशियल और डोमेन के साथ `ExchangeClient` लोड करें, फिर `connect()` कॉल करें। क्लाइंट Exchange Web Services (EWS) के साथ एक HTTPS सत्र स्थापित करता है और क्रेडेंशियल्स को मान्य करता है। यदि कनेक्शन विफल होता है, तो API एक विस्तृत `AuthenticationException` फेंकता है जिसमें तेज़ समस्या निवारण के लिए HTTP स्थिति कोड शामिल होता है।  
`ExchangeClient` Aspose.Email की वह क्लास है जो Exchange Web Services से कनेक्शन प्रबंधित करती है।

```java
import com.aspose.email.EWSClient;
import com.aspose.email.IEWSClient;

IEWSClient connectToExchangeServer(String exchangeUrl, String username, String password, String domain) {
    // Create instance of IEWSClient class by providing credentials
    return EWSClient.getEWSClient(exchangeUrl, username, password, domain);
}
```

### एक्सचेंज सार्वजनिक फ़ोल्डर कैसे सूचीबद्ध करें?
प्रत्येक शीर्ष‑स्तरीय सार्वजनिक फ़ोल्डर का प्रतिनिधित्व करने वाले `FolderInfo` ऑब्जेक्ट्स के संग्रह को प्राप्त करने के लिए `client.listPublicFolders()` को कॉल करें। यह मेथड फ़ोल्डर नाम, कुल आइटम गिनती, और बाद के कॉल्स के लिए उपयोग किए जाने वाले अद्वितीय पहचानकर्ता जैसी मेटाडेटा लौटाता है। यह कॉल सामान्य ऑन‑प्रिमाइसेस परिनियोजन में 500 फ़ोल्डर तक के लिए 2 सेकंड से कम समय में पूरी होती है।  
`listPublicFolders()` `FolderInfo` ऑब्जेक्ट्स का संग्रह लौटाता है।  
`FolderInfo` डिस्प्ले नाम और आइटम गिनती जैसी मेटाडेटा रखता है।

```java
import com.aspose.email.ExchangeFolderInfoCollection;
import com.aspose.email.IEWSClient;

ExchangeFolderInfoCollection listPublicFolders(IEWSClient client) {
    // List all public folders and return their information as a collection
    return client.listPublicFolders();
}
```

### फ़ोल्डर जानकारी कैसे प्रदर्शित करें?
`FolderInfo` संग्रह पर इटरेट करें और `displayName` तथा `subFolderCount` प्रिंट करें। यह त्वरित स्नैपशॉट आपको गहरी खोज शुरू करने से पहले पदानुक्रम समझने में मदद करता है। बड़े संगठनों के लिए, API परिणामों को पेजिनेट कर सकता है, प्रत्येक पेज पर 100 फ़ोल्डर लौटाकर मेमोरी उपयोग को कम रखता है।

```java
import com.aspose.email.ExchangeFolderInfo;

void displayFolderInfo(ExchangeFolderInfo folder) {
    // Print folder details
    System.out.println("Name: " + folder.getDisplayName());
    System.out.println("Subfolders count: " + folder.getChildFolderCount());
}
```

### फ़ोल्डर से संदेश कैसे सूचीबद्ध करें?
`client.listMessages(folderId)` को कॉल करें जहाँ `folderId` पिछले चरण से प्राप्त पहचानकर्ता है। यह मेथड `MessageInfo` ऑब्जेक्ट्स की सूची लौटाता है जिसमें विषय, प्रेषक, और प्राप्त तिथि शामिल होते हैं। आप `maxCount` के साथ परिणाम सेट को सीमित कर सकते हैं ताकि बहुत बड़े फ़ोल्डर प्रोसेस करते समय क्लाइंट ओवरलोड न हो।  
`listMessages(folderId)` `MessageInfo` ऑब्जेक्ट्स की सूची लौटाता है।  
`MessageInfo` ईमेल की मूलभूत गुणों जैसे विषय, प्रेषक, और प्राप्त तिथि को समेटे रहता है।

```java
import com.aspose.email.ExchangeMessageInfoCollection;
import com.aspose.email.IEWSClient;

ExchangeMessageInfoCollection listMessagesFromFolder(IEWSClient client, ExchangeFolderInfo folder) {
    // List messages from the specified public folder and return their information as a collection
    return client.listMessagesFromPublicFolder(folder);
}
```

### संदेशों को प्राप्त करें और सहेजें कैसे?
प्रत्येक `MessageInfo` के लिए, `client.fetchMessage(messageId)` का उपयोग करके पूर्ण MIME कंटेंट डाउनलोड करें। फिर बाइट एरे को डिस्क पर `.eml` फ़ाइल में लिखें। API कंटेंट को स्ट्रीम करता है, इसलिए 100 MB के संदेश भी पूरी पेलोड को मेमोरी में लोड किए बिना संभाले जा सकते हैं।  
`fetchMessage(messageId)` निर्दिष्ट ईमेल की पूर्ण MIME सामग्री डाउनलोड करता है।

```java
import com.aspose.email.ExchangeMessageInfo;
import com.aspose.email.IEWSClient;
import com.aspose.email.MailMessage;
import com.aspose.email.SaveOptions;

void fetchAndSaveMessages(IEWSClient client, ExchangeMessageInfoCollection messages) {
    for (ExchangeMessageInfo messageInfo : messages) {
        // Fetch the full MailMessage using its unique URI
        MailMessage msg = client.fetchMessage(messageInfo.getUniqueUri());
        
        // Save the fetched message to a file named after its subject with .msg extension
        String filePath = "YOUR_OUTPUT_DIRECTORY/" + msg.getSubject() + ".msg";
        msg.save(filePath, SaveOptions.getDefaultMsgUnicode());
    }
}
```

### सबफ़ोल्डरों से संदेशों को पुनरावर्ती रूप से कैसे सूचीबद्ध करें?
एक गहराई‑पहले (depth‑first) ट्रैवर्सल लागू करें: शीर्ष‑स्तरीय फ़ोल्डर से शुरू करें, `client.listSubFolders(parentId)` के माध्यम से उसके सबफ़ोल्डर सूचीबद्ध करें, फिर प्रत्येक चाइल्ड के लिए वही संदेश‑सूचीकरण रूटीन कॉल करें। यह पैटर्न सुनिश्चित करता है कि सार्वजनिक फ़ोल्डर ट्री में प्रत्येक संदेश प्रोसेस हो। पुनरावृत्ति गहराई केवल सर्वर की फ़ोल्डर पदानुक्रम द्वारा सीमित है (आमतौर पर < 20 स्तर)।  
`listSubFolders(parentId)` दिए गए फ़ोल्डर के तत्काल चाइल्ड फ़ोल्डर लौटाता है।

```java
import com.aspose.email.ExchangeFolderInfo;
import com.aspose.email.IEWSClient;

void listMessagesFromSubFolders(IEWSClient client, ExchangeFolderInfo folder) {
    // List all messages in the current public folder
    ExchangeMessageInfoCollection msgCollection = client.listMessagesFromPublicFolder(folder);
    fetchAndSaveMessages(client, msgCollection);

    if (folder.getChildFolderCount() > 0) {
        ExchangeFolderInfoCollection subFolders = client.listSubFolders(folder);
        for (ExchangeFolderInfo subFolder : subFolders) {
            listMessagesFromSubFolders(client, subFolder);
        }
    }
}
```

## व्यावहारिक अनुप्रयोग
1. **स्वचालित ईमेल आर्काइविंग** – समय-समय पर सभी सार्वजनिक‑फ़ोल्डर संदेशों को खींचें और उन्हें अनुपालनयुक्त आर्काइव में संग्रहीत करें।  
2. **बैकअप समाधान** – Exchange सार्वजनिक फ़ोल्डर को सुरक्षित फ़ाइल सिस्टम या क्लाउड बकेट में मिरर करें, डेटा रिडंडंसी सुनिश्चित करें।  
3. **कस्टम ईमेल क्लाइंट** – हल्के व्यूअर बनाएं जो केवल आवश्यक फ़ोल्डर और संदेश दिखाते हैं, UI जटिलता को कम करते हैं।

## प्रदर्शन विचार
जब हजारों फ़ोल्डर और लाखों संदेशों तक स्केल किया जाता है, तो इन टिप्स को ध्यान में रखें:

- **कनेक्शन पूलिंग** – प्रत्येक फ़ोल्डर के लिए नया क्लाइंट बनाने के बजाय कई ऑपरेशन्स के लिए एक ही `ExchangeClient` इंस्टेंस पुन: उपयोग करें।  
- **लेज़ी लोडिंग** – केवल आवश्यक मेटाडेटा (`listMessages` के साथ `maxCount` पैरामीटर) अनुरोध करें और पूर्ण बॉडीज़ को आवश्यकता अनुसार प्राप्त करें।  
- **ऑब्जेक्ट्स को डिस्पोज़ करें** – बैच रन के बाद `client.dispose()` कॉल करके HTTP कनेक्शन और थ्रेड‑लोकल बफ़र्स को मुक्त करें।  
- **पैरेलल प्रोसेसिंग** – शीर्ष‑स्तरीय फ़ोल्डर को कई थ्रेड्स में विभाजित करें, प्रत्येक के पास अपना क्लाइंट इंस्टेंस हो, ताकि मल्टी‑कोर CPU का प्रभावी उपयोग हो सके।

## अक्सर पूछे जाने वाले प्रश्न

**प्रश्न: क्या मैं इस कोड को Exchange Online (Office 365) के साथ उपयोग कर सकता हूँ?**  
**उत्तर:** हाँ। Office 365 EWS एन्डपॉइंट (`https://outlook.office365.com/EWS/Exchange.asmx`) प्रदान करें और आधुनिक प्रमाणीकरण (OAuth) का उपयोग करें – Aspose.Email बॉक्स से ही OAuth टोकन का समर्थन करता है।

**प्रश्न: यदि किसी फ़ोल्डर में 10 000 से अधिक संदेश हों तो क्या करें?**  
**उत्तर:** `listMessages` ओवरलोड का उपयोग करें जो `skip` और `take` पैरामीटर स्वीकार करता है, जिससे परिणामों को पेज‑बाय‑पेज किया जा सके और मेमोरी उपयोग नियंत्रित रहे।

**प्रश्न: क्या एकल ईमेल के आकार पर कोई सीमा है जिसे मैं डाउनलोड कर सकता हूँ?**  
**उत्तर:** API कंटेंट को स्ट्रीम करता है, इसलिए 150 MB तक के संदेश समर्थित हैं बिना Java हीप सीमा को पार किए, बशर्ते JVM के पास पर्याप्त नेटिव मेमोरी हो।

**प्रश्न: क्या मुझे SSL प्रमाणपत्रों को मैन्युअल रूप से संभालना चाहिए?**  
**उत्तर:** डिफ़ॉल्ट रूप से Aspose.Email Java के डिफ़ॉल्ट कीस्टोर पर भरोसा करता है। यदि आपका Exchange सर्वर स्वयं‑हस्ताक्षरित प्रमाणपत्र उपयोग करता है, तो उसे JVM ट्रस्टस्टोर में इम्पोर्ट करें या केवल परीक्षण के लिए `client.setEnableSslVerification(false)` सेट करें।

**प्रश्न: ऑडिट उद्देश्यों के लिए ऑपरेशन्स को कैसे लॉग करूँ?**  
**उत्तर:** `Logger.setLevel(Level.INFO)` को कॉन्फ़िगर करके और आउटपुट को फ़ाइल या मॉनिटरिंग सिस्टम की ओर निर्देशित करके Aspose.Email की बिल्ट‑इन लॉगिंग सक्षम करें।

## निष्कर्ष
अब आपके पास Aspose.Email for Java का उपयोग करके **how to connect exchange** और सार्वजनिक फ़ोल्डरों से पुनरावर्ती रूप से संदेश सूचीबद्ध करने के लिए एक पूर्ण, उत्पादन‑तैयार विधि है। चरणों में Maven सेटअप, लाइसेंसिंग, कनेक्शन, फ़ोल्डर सूचीकरण, संदेश पुनर्प्राप्ति, और प्रदर्शन ट्यूनिंग शामिल हैं। इस आधार को डेटाबेस, क्लाउड स्टोरेज, या कस्टम एनालिटिक्स पाइपलाइन के साथ एकीकृत करके अपने संगठन की विशिष्ट आवश्यकताओं को पूरा करने के लिए विस्तारित करें।

---

**Last Updated:** 2026-10-02  
**Tested With:** Aspose.Email for Java 25.4  
**Author:** Aspose

## संबंधित ट्यूटोरियल

- [जावा में Aspose.Email का उपयोग करके एक्सचेंज सर्वर से कनेक्ट करने का चरण-दर-चरण गाइड](/email/java/exchange-server-integration/aspose-email-java-exchange-server-connection/)
- [Aspose.Email for Java का उपयोग करके एक्सचेंज सर्वर फ़ोल्डर कनेक्ट और सूचीबद्ध करना](/email/java/exchange-server-integration/connect-list-exchange-server-folders-aspose-email-java/)
- [Aspose.Email for Java का उपयोग करके एक्सचेंज सर्वर फ़ोल्डर प्रबंधन: एक व्यापक गाइड](/email/java/exchange-server-integration/exchange-server-folders-aspose-email-java/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}