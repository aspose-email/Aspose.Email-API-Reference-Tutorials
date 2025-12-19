---
date: '2025-12-19'
description: Aspose.Email for Java का उपयोग करके Outlook में फॉलो‑अप फ़्लैग कैसे सेट
  करें, जिसमें Outlook फॉलो‑अप फ़्लैग सेट करना और उसे कुशलतापूर्वक हटाना शामिल है,
  सीखें।
keywords:
- Manage Outlook follow-up flags
- Set follow-up flags in Outlook with Aspose.Email for Java
- Integrate email task management with Aspose.Email
title: Aspose.Email for Java का उपयोग करके Outlook में फ़ॉलो‑अप फ़्लैग कैसे सेट करें
url: /hi/java/calendar-appointments/aspose-email-java-outlook-follow-up-flags/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Outlook में Aspose.Email for Java का उपयोग करके फ़ॉलो‑अप फ़्लैग कैसे सेट करें

## परिचय
यदि आप कभी महत्वपूर्ण ई‑मेल को ट्रैक करने में संघर्ष करते रहे हैं, तो आप जानते हैं कि Outlook के फ़ॉलो‑अप फ़्लैग कितने मूल्यवान हो सकते हैं। इस गाइड में हम **how to set follow-up** फ़्लैग को Aspose.Email for Java के साथ प्रोग्रामेटिकली सेट करना दिखाएंगे, साथ ही **set outlook follow-up flag** को प्राप्तकर्ताओं के लिए कैसे सेट करें, और जब कार्य समाप्त हो जाए तो **remove outlook follow-up flag** कैसे हटाएँ, यह भी कवर करेंगे। अंत तक, आप अपने Java कोड से सीधे टास्क ट्रैकिंग, रिमाइंडर और ऑडिट ट्रेल्स को ऑटोमेट कर पाएँगे।

**आप क्या सीखेंगे**
- Outlook संदेश पर फ़ॉलो‑अप फ़्लैग बनाना और लागू करना।  
- विशिष्ट प्राप्तकर्ताओं के लिए फ़ॉलो‑अप फ़्लैग सेट करना।  
- फ़्लैग को पूर्ण के रूप में चिह्नित करना और बाद में उसे हटाना।  
- रिपोर्टिंग या अनुपालन के लिए फ़्लैग विकल्प पढ़ना।  

कोड में डुबकी लगाने से पहले पर्यावरण तैयार करें।

## त्वरित उत्तर
- **What does “how to set follow-up” mean?** Outlook आइटम में प्रारंभ, रिमाइंडर और ड्यू डेट के साथ फ़्लैग जोड़ना।  
- **Which library is required?** Aspose.Email for Java (v25.4 या नया)।  
- **Do I need a license?** हाँ, पूर्ण कार्यक्षमता के लिए ट्रायल या खरीदा हुआ लाइसेंस आवश्यक है।  
- **Can I set flags for recipients only?** बिल्कुल – `FollowUpManager.setFlagForRecipients` का उपयोग करें।  
- **Is it possible to remove a flag later?** हाँ, `FollowUpManager.clearFlag` को कॉल करें।

## फ़ॉलो‑अप फ़्लैग क्या है?
फ़ॉलो‑अप फ़्लैग Outlook की एक सुविधा है जो ई‑मेल को टास्क के रूप में चिह्नित करती है, वैकल्पिक रूप से प्रारंभ, रिमाइंडर और ड्यू डेट जोड़ती है। यह आपको और आपकी टीम को लंबित कार्यों पर नज़र रखने में मदद करता है।

## Aspose.Email for Java का उपयोग क्यों करें?
Aspose.Email एक शुद्ध‑Java API प्रदान करता है जो Outlook स्थापित किए बिना काम करता है, जिससे आप .msg फ़ाइलों को हेरफेर कर सकते हैं, फ़्लैग सेट कर सकते हैं, और किसी भी प्लेटफ़ॉर्म पर टास्क प्रबंधित कर सकते हैं—बैकएंड सेवाओं, स्वचालित वर्कफ़्लो या प्रोजेक्ट‑मैनेजमेंट टूल्स के साथ एकीकरण के लिए आदर्श।

## पूर्वापेक्षाएँ
- **Aspose.Email for Java** संस्करण 25.4 या बाद का।  
- **JDK 16+** स्थापित।  
- Maven‑संगत IDE (IntelliJ IDEA, Eclipse, आदि)।  
- बुनियादी Java ज्ञान और ई‑मेल अवधारणाओं की परिचितता।

## Aspose.Email for Java सेटअप

### Maven कॉन्फ़िगरेशन
अपने `pom.xml` में निम्नलिखित डिपेंडेंसी जोड़ें:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### लाइसेंस प्राप्ति
Aspose.Email को उत्पादन उपयोग के लिए लाइसेंस की आवश्यकता होती है:

- **Free trial** – 30‑दिन का मूल्यांकन।  
- **Temporary license** – विस्तारित परीक्षण।  
- **Full license** – स्थायी सदस्यता।

किसी भी ई‑मेल ऑपरेशन से पहले लाइसेंस को इनिशियलाइज़ करें:

```java
License license = new License();
license.setLicense("path/to/Aspose.Total.Java.lic");
```

## कार्यान्वयन गाइड

### फ़ॉलो‑अप फ़्लैग कैसे सेट करें (फ़ीचर 1)

#### समीक्षा
यह अनुभाग आपको Outlook संदेश बनाने, प्रारंभ/रिमाइंडर/ड्यू तिथियां निर्धारित करने, और फ़ॉलो‑अप फ़्लैग लागू करने के चरणों से परिचित कराता है।

#### चरण 1: संदेश बनाएं और प्रारंभ करें
```java
MailMessage mailMsg = new MailMessage();
mailMsg.setSender(new MailAddress("AETest12@gmail.com"));
mailMsg.getTo().addMailAddress(new MailAddress("receiver@gmail.com"));
mailMsg.setBody("This message will test if follow up options can be added to a new mapi message.");
MapiMessage mapi = MapiMessage.fromMailMessage(mailMsg);
```
*हम पहले एक `MailMessage` बनाते हैं, प्रेषक/प्राप्तकर्ता सेट करते हैं, फिर फ़्लैग हेरफेर के लिए इसे `MapiMessage` में परिवर्तित करते हैं।*

#### चरण 2: फ़ॉलो‑अप तिथियां निर्धारित करें
```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 14, 40, 0);
Date dtStartDate = calendar.getTime();
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
calendar.add(Calendar.DATE, 1);
Date dtDueDate = calendar.getTime();
```
*यहाँ हम `Calendar` क्लास का उपयोग करके प्रारंभ, रिमाइंडर और ड्यू तिथियां सेट करते हैं।*

#### चरण 3: फ़ॉलो‑अप विकल्प लागू करें
```java
FollowUpOptions options = new FollowUpOptions("Follow Up", dtStartDate, dtDueDate, dtReminderDate);
FollowUpManager.setOptions(mapi, options);
```
*`FollowUpOptions` ऑब्जेक्ट सभी फ़्लैग विवरण रखता है, जिसे हम `FollowUpManager.setOptions` के साथ लागू करते हैं।*

#### चरण 4: संदेश सहेजें
```java
mapi.save(outputDir + "SetFollowUpflag_out.msg");
```
*फ़्लैग संलग्न के साथ संदेश को `.msg` फ़ाइल के रूप में सहेजा जाता है।*

### प्राप्तकर्ताओं के लिए Outlook फ़ॉलो‑अप फ़्लैग कैसे सेट करें (फ़ीचर 2)

#### समीक्षा
कभी‑कभी आपको संदेश को केवल प्राप्तकर्ताओं के लिए फ़्लैग करना पड़ता है। यह उदाहरण पहले संदेश को ड्राफ्ट के रूप में चिह्नित करता है, फिर फ़्लैग जोड़ता है।

#### चरण 1: ड्राफ्ट के रूप में चिह्नित करें
```java
mapi.setMessageFlags(MapiMessageFlags.MSGFLAG_UNSENT);
```
*संदेश को अनसेंट के रूप में चिह्नित करने से Outlook इसे ड्राफ्ट मानता है।*

#### चरण 2: प्राप्तकर्ता फ़्लैग सेट करें
```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
FollowUpManager.setFlagForRecipients(mapi, "Follow up", dtReminderDate);
```
*फ़्लैग अब केवल प्राप्तकर्ताओं को दिखाई देगा।*

### Outlook फ़ॉलो‑अप फ़्लैग को पूर्ण के रूप में कैसे चिह्नित करें (फ़ीचर 3)

#### समीक्षा
जब कोई टास्क पूरा हो जाता है, तो आप प्रोग्रामेटिकली फ़्लैग को पूर्ण के रूप में चिह्नित कर सकते हैं।

#### चरण 1: संदेश लोड करें
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
```

#### चरण 2: पूर्ण के रूप में चिह्नित करें और सहेजें
```java
FollowUpManager.markAsCompleted(mapi);
mapi.save(outputDir + "MarkedCompleted_out.msg");
```
*फ़्लैग स्थिति “Completed” में बदल जाती है और अपडेटेड फ़ाइल सहेजी जाती है।*

### Outlook फ़ॉलो‑अप फ़्लैग को कैसे हटाएं (फ़ीचर 4)

#### समीक्षा
यदि फ़्लैग अब आवश्यक नहीं है, तो आप इसे पूरी तरह से साफ़ कर सकते हैं।

#### चरण 1: लोड करें और फ़्लैग साफ़ करें
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpManager.clearFlag(mapi);
mapi.save(outputDir + "FollowUpFlagRemoved_out.msg");
```
*संदेश को बिना किसी फ़ॉलो‑अप फ़्लैग के सहेजा जाता है।*

### फ़ॉलो‑अप फ़्लैग विकल्प कैसे पढ़ें (फ़ीचर 5)

#### समीक्षा
ऑडिट या रिपोर्टिंग के लिए आपको मौजूदा फ़्लैग सेटिंग्स पढ़नी पड़ सकती हैं।

#### चरण 1: विकल्प प्राप्त करें
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpOptions options = FollowUpManager.getOptions(mapi);
```
*`options` ऑब्जेक्ट अब प्रारंभ, ड्यू, रिमाइंडर तिथियों और फ़्लैग विषय को समाहित करता है।*

## व्यावहारिक अनुप्रयोग
- **Task‑Management Integration:** फ़्लैग किए गए ई‑मेल को Jira, Trello, या Azure Boards के साथ सिंक करें।  
- **Automated Reminders:** लंबित फ़ॉलो‑अप के लिए दैनिक रिमाइंडर ई‑मेल जेनरेट करें।  
- **Compliance Audits:** नियामक रिपोर्टिंग के लिए फ़्लैग डेटा एक्सपोर्ट करें।

## प्रदर्शन विचार
- **Date Calculations:** लूप के अंदर नहीं, बल्कि बैच के लिए एक बार तिथियां गणना करें।  
- **Resource Management:** संदेश सहेजने के बाद किसी भी स्ट्रीम या फ़ाइल हैंडल को बंद करें।  
- **Memory Usage:** बड़े मेलबॉक्स को चंक्स में प्रोसेस करें ताकि हीप दबाव कम रहे।

## सामान्य समस्याएँ और समाधान
| समस्या | कारण | समाधान |
|-------|-------|-----|
| Outlook में फ़्लैग नहीं दिख रहा है | `MessageFlags` सही तरीके से सेट नहीं किए गए, इसलिए संदेश बिना उचित फ़्लैग के सहेजा गया | `setMessageFlags` को `MSGFLAG_UNSENT` पर सेट करना सुनिश्चित करें, इससे पहले कि आप प्राप्तकर्ता फ़्लैग लागू करें। |
| Save throws `AccessDeniedException` | फ़ाइल पाथ गलत है या लिखने की अनुमति नहीं है | आउटपुट डायरेक्टरी मौजूद है और एप्लिकेशन को उस स्थान पर लिखने की अनुमति है, यह सत्यापित करें। |
| Dates are off by one day | टाइम‑ज़ोन मिसमैच | लगातार `TimeZone.getTimeZone("GMT")` या अपने स्थानीय ज़ोन का उपयोग करें। |

## अक्सर पूछे जाने वाले प्रश्न
**Q: Aspose.Email for Java क्या है?**  
A: यह एक शुद्ध‑Java API है जो आपको Outlook स्थापित किए बिना ई‑मेल फ़ाइलें (MSG, EML, आदि) बनाना, पढ़ना और हेरफेर करना सक्षम करता है।

**Q: मैं मुफ्त ट्रायल लाइसेंस कैसे प्राप्त करूँ?**  
A: 30‑दिन के ट्रायल के लिए [Aspose वेबसाइट](https://releases.aspose.com/email/java/) पर जाएँ।

**Q: क्या मैं एक ही संदेश पर कई फ़ॉलो‑अप फ़्लैग सेट कर सकता हूँ?**  
A: Outlook प्रति संदेश केवल एक फ़्लैग समर्थन करता है, लेकिन आप अतिरिक्त टास्क डेटा को कस्टम MAPI प्रॉपर्टीज़ में स्टोर कर सकते हैं।

**Q: फ़्लैग सेट करने के बाद मेरा संदेश सहेजा नहीं जा रहा है। मुझे क्या जांचना चाहिए?**  
A: सुनिश्चित करें कि `outputDir` पाथ वैध है और एप्लिकेशन को उस स्थान पर लिखने की अनुमति है।

**Q: कई संदेशों से फ़्लैग एक साथ कैसे हटाएँ?**  
A: अपने संदेश संग्रह पर लूप चलाएँ और प्रत्येक `MapiMessage` पर `FollowUpManager.clearFlag` को कॉल करें।

## संसाधन
- [Documentation](https://reference.aspose.com/email/java/)  
- [Download Aspose.Email for Java](https://releases.aspose.com/email/java/)  
- [Aspose.Email Free Trial](https://purchase.aspose.com/purchase/free-trial/aspose-email-java)

---

**अंतिम अपडेट:** 2025-12-19  
**परीक्षित संस्करण:** Aspose.Email for Java 25.4 (jdk16)  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}