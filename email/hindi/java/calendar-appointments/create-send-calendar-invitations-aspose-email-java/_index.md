---
date: '2026-09-17'
description: Aspose.Email for Java के साथ कैलेंडर निमंत्रण बनाना आपको कैलेंडर साझा
  करने, प्रतिनिधि अनुमतियों को सेट करने, और प्रोग्रामेटिक रूप से शेयरिंग ईमेल भेजने
  की सुविधा देता है।
keywords:
- how to create calendar invitation
- calendar sharing invitation
- Aspose.Email Java
- delegate calendar permissions
lastmod: '2026-09-17'
og_description: Aspose.Email for Java के साथ कैलेंडर निमंत्रण बनाना आपको प्रोग्रामेटिक
  रूप से कैलेंडर साझा करने, प्रतिनिधि अनुमतियों को सेट करने, और Exchange Web Services
  के माध्यम से शेयरिंग ईमेल भेजने की अनुमति देता है, जिससे टीम सहयोग में सुधार होता
  है।
og_image_alt: Guide showing how to create calendar invitation with Aspose.Email for
  Java
og_title: Aspose.Email for Java के साथ कैलेंडर निमंत्रण कैसे बनाएं
schemas:
- author: Aspose
  dateModified: '2026-09-17'
  description: How to create calendar invitation with Aspose.Email for Java lets you
    share calendars, set delegate permissions, and send sharing emails programmatically.
  headline: How to create calendar invitation with Aspose.Email for Java
  type: TechArticle
- description: How to create calendar invitation with Aspose.Email for Java lets you
    share calendars, set delegate permissions, and send sharing emails programmatically.
  name: How to create calendar invitation with Aspose.Email for Java
  steps:
  - name: Install JDK if you haven't already. You can download it from [Oracle's official
      site](https://www.oracle.com/java/technologies/javase-downloads.html).
    text: Install JDK if you haven't already. You can download it from [Oracle's official
      site](https://www.oracle.com/java/technologies/javase-downloads.html).
  - name: Ensure Maven is installed and configured on your machine.
    text: Ensure Maven is installed and configured on your machine.
  - name: Choose an IDE such as IntelliJ IDEA or Eclipse for easier development.
    text: Choose an IDE such as IntelliJ IDEA or Eclipse for easier development.
  - name: '**Corporate meetings** – Let team members view meeting schedules without
      giving full mailbox rights.'
    text: '**Corporate meetings** – Let team members view meeting schedules without
      giving full mailbox rights.'
  - name: '**Project management** – Project leads can monitor timelines while developers
      retain control of their own calendars.'
    text: '**Project management** – Project leads can monitor timelines while developers
      retain control of their own calendars.'
  - name: '**Event planning** – Vendors receive a **calendar sharing email** to coordinate
      logistics without exposing internal details.'
    text: '**Event planning** – Vendors receive a **calendar sharing email** to coordinate
      logistics without exposing internal details.'
  type: HowTo
- questions:
  - answer: It’s a comprehensive library for handling emails, calendars, and contacts
      in Java applications, supporting Outlook, Exchange, and other protocols.
    question: What is Aspose.Email for Java used for?
  - answer: Install JDK 16+, Maven, add the Aspose.Email dependency to `pom.xml`,
      and obtain a license (trial or full).
    question: How do I set up my environment for using Aspose.Email?
  - answer: Yes, but verify the service URL and permission levels match your server’s
      configuration.
    question: Can I use this code with other versions of Exchange Online?
  - answer: Check network connectivity, credentials, and that the delegate user has
      valid permissions. Review exception details for clues.
    question: What should I do if the calendar sharing invitation fails to send?
  - answer: Absolutely – replace `ExchangeDelegateFolderPermissionLevel.Reviewer`
      with `Editor`, `Author`, or `Owner` as needed.
    question: Is it possible to add additional permissions like editing or full access?
  type: FAQPage
tags:
- calendar sharing
- Aspose.Email
- Java email API
- delegate permissions
- EWS client
title: Aspose.Email for Java के साथ कैलेंडर निमंत्रण कैसे बनाएं
url: /hi/java/calendar-appointments/create-send-calendar-invitations-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# कैलेंडर शेयरिंग प्रबंधन: Aspose.Email for Java गाइड

## कैलेंडर शेयरिंग प्रबंधन का परिचय
कैलेंडर शेयरिंग निमंत्रणों का प्रबंधन एक जटिल कार्य हो सकता है, विशेष रूप से जब विभिन्न प्लेटफ़ॉर्म पर कई उपयोगकर्ताओं से निपटना हो। इस ट्यूटोरियल में आप Aspose.Email for Java के साथ **कैलेंडर शेयरिंग निमंत्रण बनाएँगे**, जिसमें डेलीगेट एक्सेस बनाने से लेकर कैलेंडर शेयरिंग ईमेल भेजने तक सब कुछ शामिल है। अंत तक, आप डेलीगेट अनुमतियाँ सेट कर सकेंगे, **कैलेंडर अनुमतियों को कॉन्फ़िगर** कर सकेंगे, और अपने संगठन में सहयोग को सरल बना सकेंगे।

**आप क्या सीखेंगे**
- Aspose.Email for Java के साथ EWS क्लाइंट को इनिशियलाइज़ कैसे करें  
- एक डेलीगेट उपयोगकर्ता बनाना और **डेलीगेट अनुमतियाँ सेट करना**  
- **डेलीगेट एक्सेस बनाना** और कैलेंडर अनुमतियों को कॉन्फ़िगर करना  
- प्रोग्रामेटिक रूप से **कैलेंडर शेयरिंग ईमेल** (निमंत्रण) भेजें  
- वास्तविक दुनिया के परिदृश्य जहाँ ये सुविधाएँ मूल्य जोड़ती हैं  

शुरू करने से पहले, सुनिश्चित करें कि आपके पास सब कुछ है।

## त्वरित उत्तर
- **इस गाइड का मुख्य उद्देश्य क्या है?** Aspose.Email for Java का उपयोग करके **कैलेंडर शेयरिंग निमंत्रण बनाने** का तरीका दिखाना।  
- **कौन सा लाइब्रेरी संस्करण आवश्यक है?** Aspose.Email for Java 25.4 (JDK 16 classifier)।  
- **क्या मुझे लाइसेंस चाहिए?** हाँ – उत्पादन उपयोग के लिए ट्रायल या पूर्ण लाइसेंस आवश्यक है।  
- **कौन सा वातावरण आवश्यक है?** JDK 16+, Maven, और एक Exchange Online खाता।  
- **क्या मैं इसे अन्य Exchange सर्वरों के साथ उपयोग कर सकता हूँ?** हाँ, लेकिन आपको सर्विस URL और अनुमतियों के स्तर को समायोजित करना पड़ सकता है।

## कैलेंडर शेयरिंग निमंत्रण क्या है?
कैलेंडर शेयरिंग निमंत्रण एक ईमेल संदेश है जो दूसरे उपयोगकर्ता को आपके कैलेंडर को देखने (या संपादित करने) की अनुमति देता है, बिना पूर्ण मेलबॉक्स अधिकार दिए। यह टीम के सदस्यों को आपका शेड्यूल देखने, मीटिंग प्रस्तावित करने, या इवेंट्स प्रबंधित करने की सुविधा देता है, जबकि आपका मेलबॉक्स सुरक्षित रहता है।

## कैलेंडर अनुमतियों को कॉन्फ़िगर क्यों करें?
कैलेंडर अनुमतियों को कॉन्फ़िगर करने से आप यह नियंत्रित कर सकते हैं कि डेलीगेट क्या कर सकता है—क्या वह केवल इवेंट्स पढ़ सकता है, नए प्रस्तावित कर सकता है, या मौजूदा प्रविष्टियों को संपादित कर सकता है। उचित अनुमति सेटिंग्स संवेदनशील जानकारी की सुरक्षा करती हैं जबकि प्रभावी सहयोग को सक्षम बनाती हैं। उदाहरण के लिए, केवल-रीड एक्सेस देने से आकस्मिक बदलाव रोकते हैं, जबकि संपादन अधिकार डेलीगेट को आपके behalf पर मीटिंग्स शेड्यूल या संशोधित करने की अनुमति देते हैं।

## पूर्वापेक्षाएँ
- **Java Development Kit (JDK):** संस्करण 16 या बाद का।  
- **Maven:** निर्भरता प्रबंधन और प्रोजेक्ट निर्माण के लिए।  
- **Aspose.Email for Java Library:** संस्करण 25.4, JDK 16 समर्थन के साथ।  

### पर्यावरण सेटअप आवश्यकताएँ
1. यदि आपने अभी तक JDK स्थापित नहीं किया है, तो इसे इंस्टॉल करें। आप इसे [Oracle की आधिकारिक साइट](https://www.oracle.com/java/technologies/javase-downloads.html) से डाउनलोड कर सकते हैं।  
2. सुनिश्चित करें कि Maven आपके मशीन पर स्थापित और कॉन्फ़िगर है।  
3. आसान विकास के लिए IntelliJ IDEA या Eclipse जैसे IDE चुनें।

### ज्ञान पूर्वापेक्षाएँ
- बुनियादी Java प्रोग्रामिंग कौशल  
- Maven निर्भरताओं की परिचितता  
- वैकल्पिक: Exchange Web Services (EWS) का अनुभव  

## Aspose.Email for Java सेटअप करना
### Maven कॉन्फ़िगरेशन
अपने `pom.xml` फ़ाइल में निम्नलिखित निर्भरता जोड़ें:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### लाइसेंस प्राप्त करना
Aspose.Email for Java को पूर्ण कार्यक्षमता के लिए लाइसेंस की आवश्यकता होती है। आप कर सकते हैं:
- **नि:शुल्क ट्रायल:** [Aspose के रिलीज़ पेज](https://releases.aspose.com/email/java/) से डाउनलोड करें।  
- **अस्थायी लाइसेंस:** Aspose वेबसाइट पर एक अस्थायी कुंजी का अनुरोध करें।  
- **खरीदें:** उत्पादन डिप्लॉयमेंट के लिए स्थायी लाइसेंस प्राप्त करें।

### बुनियादी इनिशियलाइज़ेशन और सेटअप
एक बार Maven निर्भरता को हल कर लेता है, EWS क्लाइंट को इनिशियलाइज़ करें:

`ExchangeService` Exchange Web Services के साथ संचार करने के लिए उपयोग की जाने वाली मुख्य क्लास है।

```java
IEWSClient client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser", "pwd", "domain");
```

## कैलेंडर शेयरिंग निमंत्रण कैसे बनाएं
कैलेंडर शेयरिंग निमंत्रण बनाने के लिए आप पहले `ExchangeService` क्लाइंट का उपयोग करके Exchange से कनेक्ट होते हैं, फिर इच्छित अनुमति स्तर के साथ एक डेलीगेट परिभाषित करते हैं, और अंत में एक `MailMessage` बनाते हैं जिसमें शेयरिंग अनुरोध शामिल होता है। निम्नलिखित चरण Java में इस वर्कफ़्लो को दर्शाते हैं।

नीचे हम दो मुख्य सुविधाओं को कवर करते हैं: कैलेंडर शेयरिंग निमंत्रण बनाना और भेजना, और कैलेंडर एक्सेस के लिए **डेलीगेट अनुमतियाँ सेट करना**।

### सुविधा 1: कैलेंडर शेयरिंग निमंत्रण बनाना और भेजना
#### अवलोकन
यह सुविधा आपको क्लाइंट को इनिशियलाइज़ करने, **डेलीगेट एक्सेस बनाना**, और निमंत्रण ईमेल भेजने के चरणों से ले जाती है।

#### चरण‑दर‑चरण कार्यान्वयन
##### 1️⃣ EWS क्लाइंट को इनिशियलाइज़ करें
`ExchangeService` Exchange सर्वर से कनेक्शन का प्रतिनिधित्व करता है और संदेश भेजने व प्राप्त करने के लिए उपयोग किया जाता है।

```java
IEWSClient client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser", "pwd", "domain");
```  
यह आपके Java एप्लिकेशन को Exchange Online से जोड़ता है।

##### 2️⃣ डेलीगेट उपयोगकर्ता बनाएं
`DelegateUser` डेलीगेट के ईमेल पते और प्रदान की जाने वाली अनुमति स्तर को परिभाषित करता है।

```java
ExchangeDelegateUser delegateUser = new ExchangeDelegateUser("sharingfrom@domain.com", ExchangeDelegateFolderPermissionLevel.NotSpecified);
delegateUser.getFolderPermissions().setCalendarFolderPermissionLevel(ExchangeDelegateFolderPermissionLevel.Reviewer);
client.delegateAccess(delegateUser, "sharingfrom@domain.com");
```  
यहाँ हम **डेलीगेट एक्सेस बनाते** हैं और `Reviewer` स्तर असाइन करते हैं, जो डेलीगेट को कैलेंडर आइटम देखने की अनुमति देता है।

##### 3️⃣ कैलेंडर शेयरिंग निमंत्रण भेजें
`MailMessage` वह ईमेल बनाता है जिसमें कैलेंडर शेयरिंग निमंत्रण होता है।

```java
MapiMessage mapiMessage = client.createCalendarSharingInvitationMessage("sharingfrom@domain.com");

MailConversionOptions options = new MailConversionOptions();
options.setConvertAsTnef(true);

MailMessage mail = mapiMessage.toMailMessage(options);
client.send(mail);
```  
कोड एक **कैलेंडर शेयरिंग ईमेल** (निमंत्रण) बनाता है और इसे EWS क्लाइंट के माध्यम से भेजता है।

### सुविधा 2: डेलीगेट कैलेंडर एक्सेस अनुमति
#### अवलोकन
यह अनुभाग दिखाता है कि **कैलेंडर अनुमतियों को कॉन्फ़िगर** कैसे करें और सुनिश्चित करें कि डेलीगेट के पास सही अधिकार हों।

#### कार्यान्वयन चरण
##### 1️⃣ EWS क्लाइंट को इनिशियलाइज़ करें (पुन: उपयोग)
`ExchangeService` प्रारंभिक कॉन्फ़िगरेशन के बाद कई ऑपरेशनों के लिए पुनः उपयोग किया जा सकता है।

```java
IEWSClient client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser", "pwd", "domain");
```  

##### 2️⃣ डेलीगेट अनुमतियाँ बनाएं और सेट करें
`ExchangeDelegateFolderPermissionLevel` एक कैलेंडर फ़ोल्डर पर डेलीगेट के पास हो सकने वाले एक्सेस स्तरों को सूचीबद्ध करता है।

```java
ExchangeDelegateUser delegateUser = new ExchangeDelegateUser("sharingfrom@domain.com", ExchangeDelegateFolderPermissionLevel.NotSpecified);
delegateUser.getFolderPermissions().setCalendarFolderPermissionLevel(ExchangeDelegateFolderPermissionLevel.Reviewer);

client.delegateAccess(delegateUser, "sharingfrom@domain.com");
```  
यह स्निपेट **डेलीगेट अनुमतियाँ सेट करता** है ताकि उपयोगकर्ता पूर्ण मेलबॉक्स एक्सेस के बिना कैलेंडर प्रविष्टियों को देख सके।

## डेलीगेट्स के लिए कैलेंडर अनुमतियों को कैसे कॉन्फ़िगर करें
जब डेलीगेट को केवल-रीड एक्सेस से अधिक की आवश्यकता हो, तो आप `ExchangeDelegateFolderPermissionLevel` को समायोजित करके संपादन, लेखक, या मालिक अधिकार दे सकते हैं। सुरक्षा बनाए रखने और आवश्यक कार्यक्षमता प्रदान करने के लिए न्यूनतम स्तर चुनें जो व्यावसायिक आवश्यकता को पूरा करता हो। उदाहरण के लिए, Editor स्तर असाइन करने से डेलीगेट को इवेंट्स बनाने, संशोधित करने और हटाने की अनुमति मिलती है, जबकि Reviewer स्तर केवल देखने की अनुमति देता है।

- `Reviewer` – केवल-रीड एक्सेस।  
- `Editor` – पढ़ने/लिखने की एक्सेस।  
- `Author` – बनाना और पढ़ना, लेकिन हटाना नहीं।  
- `Owner` – पूर्ण नियंत्रण, जिसमें अनुमतियों में परिवर्तन भी शामिल है।  

**प्रो टिप:** अपने कैलेंडर डेटा को सुरक्षित रखने के लिए व्यावसायिक आवश्यकता को पूरा करने वाला न्यूनतम‑विशेषाधिकार स्तर उपयोग करें।

## व्यावहारिक अनुप्रयोग
वास्तविक दुनिया के परिदृश्य जहाँ **कैलेंडर शेयरिंग प्रबंधन** उत्कृष्ट है:
1. **कॉरपोरेट मीटिंग्स** – टीम के सदस्यों को मीटिंग शेड्यूल देखने दें बिना पूर्ण मेलबॉक्स अधिकार दिए।  
2. **प्रोजेक्ट मैनेजमेंट** – प्रोजेक्ट लीड्स टाइमलाइन मॉनिटर कर सकते हैं जबकि डेवलपर्स अपने कैलेंडर पर नियंत्रण रखते हैं।  
3. **इवेंट प्लानिंग** – विक्रेता एक **कैलेंडर शेयरिंग ईमेल** प्राप्त करते हैं ताकि वे लॉजिस्टिक्स समन्वय कर सकें बिना आंतरिक विवरण उजागर किए।

## प्रदर्शन संबंधी विचार
- **मेमोरी प्रबंधन:** उच्च‑वॉल्यूम एप्लिकेशन में बड़े `MailMessage` ऑब्जेक्ट्स को तुरंत डिस्पोज़ करें।  
- **अपवाद संभालना:** नेटवर्क कॉल्स को try‑catch ब्लॉक्स में रैप करें ताकि कनेक्टिविटी गड़बड़ियों को सहजता से संभाला जा सके।  
- **लाइब्रेरी अपडेट्स:** Aspose.Email for Java 50+ प्रोटोकॉल का समर्थन करता है और 10,000 आइटम तक के कैलेंडर को बिना पूरी फ़ाइल मेमोरी में लोड किए प्रोसेस कर सकता है, इसलिए प्रदर्शन सुधार और बग फिक्सेज़ के लाभ के लिए लाइब्रेरी को अद्यतित रखें।

## सामान्य समस्याएँ और समाधान
| समस्या | संभावित कारण | समाधान |
|-------|--------------|----------|
| निमंत्रण प्राप्त नहीं हुआ | स्पैम फ़िल्टर या गलत ईमेल पता | प्राप्तकर्ता पते की जाँच करें और भेजने वाले डोमेन को सुरक्षित‑प्रेषक सूची में जोड़ें |
| अनुमति लागू नहीं हुई | `ExchangeDelegateFolderPermissionLevel` का गलत उपयोग | अनुमति स्तर को दोबारा जांचें कि वह आवश्यक एक्सेस से मेल खाता है |
| `createCalendarSharingInvitationMessage` पर रनटाइम अपवाद | लाइसेंस गायब या लाइब्रेरी पुरानी | सुनिश्चित करें कि वैध लाइसेंस लोड किया गया है और आप नवीनतम Aspose.Email संस्करण का उपयोग कर रहे हैं |

## अक्सर पूछे जाने वाले प्रश्न
**Q: Aspose.Email for Java किस लिए उपयोग किया जाता है?**  
A: यह Java एप्लिकेशनों में ईमेल, कैलेंडर और संपर्कों को संभालने के लिए एक व्यापक लाइब्रेरी है, जो Outlook, Exchange और अन्य प्रोटोकॉल को सपोर्ट करती है।

**Q: Aspose.Email के उपयोग के लिए अपना पर्यावरण कैसे सेट अप करें?**  
A: JDK 16+, Maven स्थापित करें, `pom.xml` में Aspose.Email निर्भरता जोड़ें, और लाइसेंस प्राप्त करें (ट्रायल या पूर्ण)।

**Q: क्या मैं इस कोड को Exchange Online के अन्य संस्करणों के साथ उपयोग कर सकता हूँ?**  
A: हाँ, लेकिन सुनिश्चित करें कि सर्विस URL और अनुमति स्तर आपके सर्वर की कॉन्फ़िगरेशन से मेल खाते हैं।

**Q: यदि कैलेंडर शेयरिंग निमंत्रण भेजने में विफल हो तो क्या करें?**  
A: नेटवर्क कनेक्टिविटी, क्रेडेंशियल्स, और यह जांचें कि डेलीगेट उपयोगकर्ता के पास वैध अनुमतियाँ हैं। संकेतों के लिए अपवाद विवरण की समीक्षा करें।

**Q: क्या संपादन या पूर्ण एक्सेस जैसी अतिरिक्त अनुमतियाँ जोड़ना संभव है?**  
A: बिल्कुल – आवश्यकतानुसार `ExchangeDelegateFolderPermissionLevel.Reviewer` को `Editor`, `Author`, या `Owner` से बदलें।

## निष्कर्ष
अब आपके पास Aspose.Email for Java के साथ **कैलेंडर शेयरिंग निमंत्रण बनाने** के लिए एक पूर्ण, अंत‑से‑अंत समाधान है। EWS क्लाइंट को इनिशियलाइज़ करके, **डेलीगेट एक्सेस बनाकर**, **डेलीगेट अनुमतियाँ सेट करके**, और **कैलेंडर शेयरिंग ईमेल** भेजकर, आप अपने संगठन में सहयोग को स्वचालित कर सकते हैं।

**अगले कदम**
- अन्य अनुमति स्तरों (Editor, Owner) के साथ प्रयोग करें।  
- इस लॉजिक को अपने मौजूदा शेड्यूलिंग या HR सिस्टम में एकीकृत करें।  
- आवर्ती इवेंट्स या मीटिंग अनुरोधों जैसी अतिरिक्त Aspose.Email सुविधाओं का अन्वेषण करें।

---

**अंतिम अपडेट:** 2026-09-17  
**परीक्षण किया गया:** Aspose.Email for Java 25.4 (JDK 16 classifier)  
**लेखक:** Aspose

## संबंधित ट्यूटोरियल

- [Aspose.Email का उपयोग करके Java में कैलेंडर आइटम कैसे बनाएं](/email/java/calendar-appointments/create-save-calendar-items-aspose-email-java/)
- [Aspose Email Java द्वारा तिथि के अनुसार Exchange अपॉइंटमेंट फ़िल्टर करना](/email/java/calendar-appointments/aspose-email-java-filter-exchange-appointments-by-date/)
- [Aspose.Email के साथ Java में Exchange कैलेंडर बनाना – एक पूर्ण गाइड](/email/java/calendar-appointments/mastering-exchange-calendar-management-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}