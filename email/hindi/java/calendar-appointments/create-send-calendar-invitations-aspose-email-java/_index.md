---
date: '2026-03-20'
description: Aspose.Email for Java का उपयोग करके कैलेंडर शेयरिंग इनवाइट बनाना, कैलेंडर
  अनुमतियों को कॉन्फ़िगर करना और डेलीगेट एक्सेस सेट करना सीखें।
keywords:
- Aspose.Email for Java
- create calendar invitations
- send calendar invitations
title: Aspose.Email for Java के साथ कैलेंडर शेयरिंग निमंत्रण बनाएं
url: /hi/java/calendar-appointments/create-send-calendar-invitations-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# कैलेंडर शेयरिंग प्रबंधन: Aspose.Email for Java गाइड

## कैलेंडर शेयरिंग प्रबंधन का परिचय
कैलेंडर शेयरिंग निमंत्रणों का प्रबंधन एक जटिल कार्य हो सकता है, विशेषकर जब विभिन्न प्लेटफ़ॉर्म पर कई उपयोगकर्ताओं के साथ काम किया जाता है। इस ट्यूटोरियल में आप Aspose.Email for Java के साथ **create calendar sharing invitation** बनाएँगे, जिसमें डेलीगेट एक्सेस बनाना से लेकर कैलेंडर शेयरिंग ईमेल भेजना तक सब कुछ शामिल है। अंत तक, आप डेलीगेट अनुमतियों को सेट कर सकेंगे, **configure calendar permissions**, और अपने संगठन में सहयोग को सुगम बना सकेंगे।

**आप क्या सीखेंगे**
- Aspose.Email for Java के साथ EWS क्लाइंट को प्रारंभ करने का तरीका  
- डेलीगेट उपयोगकर्ता बनाना और **set delegate permissions**  
- **Create delegate access** और कैलेंडर अनुमतियों को कॉन्फ़िगर करना  
- **calendar sharing email** (निमंत्रण) को प्रोग्रामेटिक रूप से भेजना  
- वास्तविक दुनिया के परिदृश्य जहाँ ये सुविधाएँ मूल्य जोड़ती हैं  

शुरू करने से पहले, सुनिश्चित करें कि आपके पास सभी आवश्यक चीज़ें हैं।

## त्वरित उत्तर
- **इस गाइड का मुख्य उद्देश्य क्या है?** Aspose.Email for Java का उपयोग करके **create calendar sharing invitation** कैसे बनाएं, यह दिखाने के लिए।  
- **कौन सा लाइब्रेरी संस्करण आवश्यक है?** Aspose.Email for Java 25.4 (JDK 16 classifier).  
- **क्या मुझे लाइसेंस चाहिए?** हाँ – उत्पादन उपयोग के लिए एक ट्रायल या पूर्ण लाइसेंस आवश्यक है।  
- **कौन सा वातावरण आवश्यक है?** JDK 16+, Maven, और एक Exchange Online खाता।  
- **क्या मैं इसे अन्य Exchange सर्वरों के साथ उपयोग कर सकता हूँ?** हाँ, लेकिन आपको सेवा URL और अनुमति स्तरों को समायोजित करने की आवश्यकता हो सकती है।

## कैलेंडर शेयरिंग निमंत्रण क्या है?
कैलेंडर शेयरिंग निमंत्रण एक ईमेल संदेश है जो दूसरे उपयोगकर्ता को आपके कैलेंडर को देखने (या संपादित करने) की अनुमति देता है, बिना पूर्ण मेलबॉक्स अधिकार दिए। यह आमतौर पर टीम समन्वय, प्रोजेक्ट योजना और इवेंट प्रबंधन के लिए उपयोग किया जाता है।

## कैलेंडर अनुमतियों को कॉन्फ़िगर क्यों करें?
कैलेंडर अनुमतियों को कॉन्फ़िगर करने से आप यह नियंत्रित कर सकते हैं कि डेलीगेट क्या कर सकता है—क्या वह केवल इवेंट पढ़ सकता है, नए प्रस्तावित कर सकता है, या मौजूदा प्रविष्टियों को संपादित कर सकता है। उचित अनुमति सेटिंग्स संवेदनशील जानकारी की सुरक्षा करती हैं जबकि प्रभावी सहयोग को सक्षम करती हैं।

## पूर्वापेक्षाएँ
- **Java Development Kit (JDK):** संस्करण 16 या बाद का।  
- **Maven:** निर्भरता प्रबंधन और प्रोजेक्ट निर्माण के लिए।  
- **Aspose.Email for Java Library:** संस्करण 25.4, JDK 16 समर्थन के साथ।  

### पर्यावरण सेटअप आवश्यकताएँ
1. यदि आपने अभी तक JDK स्थापित नहीं किया है, तो इसे स्थापित करें। आप इसे [Oracle's official site](https://www.oracle.com/java/technologies/javase-downloads.html) से डाउनलोड कर सकते हैं।  
2. सुनिश्चित करें कि Maven आपके मशीन पर स्थापित और कॉन्फ़िगर किया गया है।  
3. विकास को आसान बनाने के लिए IntelliJ IDEA या Eclipse जैसे IDE चुनें।

### ज्ञान पूर्वापेक्षाएँ
- बुनियादी Java प्रोग्रामिंग कौशल  
- Maven निर्भरताओं की परिचितता  
- वैकल्पिक: Exchange Web Services (EWS) का अनुभव  

## Aspose.Email for Java सेटअप
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

### लाइसेंस प्राप्ति
Aspose.Email for Java पूर्ण कार्यक्षमता के लिए एक लाइसेंस की आवश्यकता होती है। आप:
- **Free Trial:** [Aspose's release page](https://releases.aspose.com/email/java/) से डाउनलोड करें।  
- **Temporary License:** Aspose वेबसाइट पर एक अस्थायी कुंजी का अनुरोध करें।  
- **Purchase:** उत्पादन परिनियोजन के लिए एक स्थायी लाइसेंस प्राप्त करें।

### बुनियादी प्रारंभिककरण और सेटअप
एक बार Maven निर्भरता हल हो जाने पर, EWS क्लाइंट को प्रारंभ करें:

```java
IEWSClient client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser", "pwd", "domain");
```

## कैसे बनाएं कैलेंडर शेयरिंग निमंत्रण
नीचे हम दो मुख्य सुविधाओं को कवर करते हैं: कैलेंडर शेयरिंग निमंत्रण बनाना और भेजना, तथा कैलेंडर एक्सेस के लिए **set delegate permissions**।

### Feature 1: Create and Send Calendar Sharing Invitation
#### सारांश
यह सुविधा आपको क्लाइंट को प्रारंभ करने, **create delegate access**, और निमंत्रण ईमेल भेजने के माध्यम से मार्गदर्शन करती है।

#### Step‑by‑Step Implementation
##### 1️⃣ Initialize EWS Client
```java
IEWSClient client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser", "pwd", "domain");
```
यह आपके Java एप्लिकेशन को Exchange Online से जोड़ता है।

##### 2️⃣ Create Delegate User
```java
ExchangeDelegateUser delegateUser = new ExchangeDelegateUser("sharingfrom@domain.com", ExchangeDelegateFolderPermissionLevel.NotSpecified);
delegateUser.getFolderPermissions().setCalendarFolderPermissionLevel(ExchangeDelegateFolderPermissionLevel.Reviewer);
client.delegateAccess(delegateUser, "sharingfrom@domain.com");
```
यहाँ हम **create delegate access** करते हैं और `Reviewer` स्तर असाइन करते हैं, जिससे डेलीगेट कैलेंडर आइटम देख सकता है।

##### 3️⃣ Send Calendar Sharing Invitation
```java
MapiMessage mapiMessage = client.createCalendarSharingInvitationMessage("sharingfrom@domain.com");

MailConversionOptions options = new MailConversionOptions();
options.setConvertAsTnef(true);

MailMessage mail = mapiMessage.toMailMessage(options);
client.send(mail);
```
कोड एक **calendar sharing email** (निमंत्रण) बनाता है और इसे EWS क्लाइंट के माध्यम से भेजता है।

### Feature 2: Delegate Calendar Access Permission
#### सारांश
यह अनुभाग दिखाता है कि **configure calendar permissions** कैसे करें और सुनिश्चित करें कि डेलीगेट के पास सही अधिकार हों।

#### Implementation Steps
##### 1️⃣ Initialize EWS Client (reuse)
```java
IEWSClient client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser", "pwd", "domain");
```

##### 2️⃣ Create and Set Delegate Permissions
```java
ExchangeDelegateUser delegateUser = new ExchangeDelegateUser("sharingfrom@domain.com", ExchangeDelegateFolderPermissionLevel.NotSpecified);
delegateUser.getFolderPermissions().setCalendarFolderPermissionLevel(ExchangeDelegateFolderPermissionLevel.Reviewer);

client.delegateAccess(delegateUser, "sharingfrom@domain.com");
```
यह स्निपेट **sets delegate permissions** करता है ताकि उपयोगकर्ता पूर्ण मेलबॉक्स एक्सेस के बिना कैलेंडर प्रविष्टियों को देख सके।

## डेलीगेट्स के लिए कैलेंडर अनुमतियों को कैसे कॉन्फ़िगर करें
जब आपको डेलीगेट को केवल इवेंट देखने से अधिक करने की आवश्यकता हो—जैसे संपादित या हटाना—तो आप `ExchangeDelegateFolderPermissionLevel` को बदल सकते हैं:

- `Reviewer` – केवल‑पढ़ने की पहुँच।  
- `Editor` – पढ़ने/लिखने की पहुँच।  
- `Author` – बनाना और पढ़ना, लेकिन हटाना नहीं।  
- `Owner` – पूर्ण नियंत्रण, जिसमें अनुमति परिवर्तन भी शामिल हैं।

**Pro tip:** व्यवसायिक आवश्यकता को पूरा करने के लिए न्यूनतम‑विशेषाधिकार स्तर का उपयोग करें ताकि आपका कैलेंडर डेटा सुरक्षित रहे।

## व्यावहारिक अनुप्रयोग
**manage calendar sharing** के वास्तविक दुनिया के परिदृश्य जहाँ यह चमकता है:
1. **Corporate Meetings** – टीम के सदस्य मीटिंग शेड्यूल देख सकते हैं बिना पूर्ण मेलबॉक्स अधिकार दिए।  
2. **Project Management** – प्रोजेक्ट लीड टाइमलाइन मॉनिटर कर सकते हैं जबकि डेवलपर्स अपने कैलेंडर पर नियंत्रण बनाए रखते हैं।  
3. **Event Planning** – विक्रेता एक **calendar sharing email** प्राप्त करते हैं ताकि वे लॉजिस्टिक्स समन्वय कर सकें बिना आंतरिक विवरण उजागर किए।

## प्रदर्शन विचार
- **Memory Management:** उच्च‑वॉल्यूम एप्स में बड़े `MailMessage` ऑब्जेक्ट्स को शीघ्रता से डिस्पोज़ करें।  
- **Exception Handling:** नेटवर्क कॉल्स को try‑catch ब्लॉक्स में रैप करें ताकि कनेक्टिविटी गड़बड़ियों को सुगमता से संभाला जा सके।  
- **Library Updates:** प्रदर्शन सुधार और बग फिक्स के लाभ के लिए Aspose.Email को अद्यतित रखें।

## सामान्य समस्याएँ और समाधान
| Issue | Likely Cause | Solution |
|-------|--------------|----------|
| Invitation not received | Spam filters or incorrect email address | प्राप्तकर्ता पते की जाँच करें और भेजने वाले डोमेन को सुरक्षित‑प्रेषक सूची में जोड़ें |
| Permission not applied | Using wrong `ExchangeDelegateFolderPermissionLevel` | सुनिश्चित करें कि अनुमति स्तर आवश्यक एक्सेस से मेल खाता है |
| Runtime exception on `createCalendarSharingInvitationMessage` | Missing license or outdated library | एक वैध लाइसेंस लोड किया गया है और आप नवीनतम Aspose.Email संस्करण का उपयोग कर रहे हैं, यह सुनिश्चित करें |

## अक्सर पूछे जाने वाले प्रश्न
**Q: Aspose.Email for Java किस लिए उपयोग किया जाता है?**  
A: यह एक व्यापक लाइब्रेरी है जो Java अनुप्रयोगों में ईमेल, कैलेंडर और संपर्कों को संभालती है, Outlook, Exchange और अन्य प्रोटोकॉल का समर्थन करती है।

**Q: Aspose.Email के लिए अपना वातावरण कैसे सेटअप करूँ?**  
A: JDK 16+, Maven स्थापित करें, `pom.xml` में Aspose.Email निर्भरता जोड़ें, और एक लाइसेंस (ट्रायल या पूर्ण) प्राप्त करें।

**Q: क्या मैं इस कोड को अन्य Exchange Online संस्करणों के साथ उपयोग कर सकता हूँ?**  
A: हाँ, लेकिन सुनिश्चित करें कि सेवा URL और अनुमति स्तर आपके सर्वर की कॉन्फ़िगरेशन से मेल खाते हों।

**Q: यदि कैलेंडर शेयरिंग निमंत्रण भेजने में विफल हो तो क्या करें?**  
A: नेटवर्क कनेक्टिविटी, क्रेडेंशियल्स, और डेलीगेट उपयोगकर्ता के पास वैध अनुमतियों की जाँच करें। संकेतों के लिए अपवाद विवरण देखें।

**Q: क्या संपादन या पूर्ण एक्सेस जैसी अतिरिक्त अनुमतियाँ जोड़ना संभव है?**  
A: बिल्कुल—`ExchangeDelegateFolderPermissionLevel.Reviewer` को आवश्यकतानुसार `Editor`, `Author`, या `Owner` से बदलें।

## निष्कर्ष
अब आपके पास Aspose.Email for Java के साथ **create calendar sharing invitation** के लिए एक पूर्ण, अंत‑से‑अंत समाधान है। EWS क्लाइंट को प्रारंभ करके, **create delegate access**, **set delegate permissions**, और एक **calendar sharing email** भेजकर, आप अपने संगठन में सहयोग को स्वचालित कर सकते हैं।

**अगले कदम**
- अन्य अनुमति स्तरों (Editor, Owner) के साथ प्रयोग करें।  
- इस लॉजिक को अपने मौजूदा शेड्यूलिंग या HR सिस्टम में एकीकृत करें।  
- आवर्ती इवेंट या मीटिंग अनुरोध जैसी अतिरिक्त Aspose.Email सुविधाओं का अन्वेषण करें।

---

**Last Updated:** 2026-03-20  
**Tested With:** Aspose.Email for Java 25.4 (JDK 16 classifier)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}