---
date: '2026-07-27'
description: Aspose.Email for Java का उपयोग करके Outlook Flag Java सेट करना सीखें,
  जिसमें flag creation, recipient flags, completion, removal, और reading options शामिल
  हैं।
keywords:
- set outlook flag java
- outlook follow up flag java
- aspose email java
lastmod: '2026-07-27'
og_description: Aspose.Email for Java के साथ Outlook Flag Java सेट करें। यह गाइड दिखाता
  है कि Outlook follow‑up flags को कैसे create, read, complete, और remove किया जाए,
  प्रभावी रूप से।
og_image_alt: 'Developer guide: Set Outlook flag Java using Aspose.Email'
og_title: Outlook Flag Java सेट करें – Complete Aspose.Email Programming Guide
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Learn how to set outlook flag java using Aspose.Email for Java, covering
    flag creation, recipient flags, completion, removal, and reading options.
  headline: Set Outlook Flag Java – Complete Aspose.Email Programming Guide
  type: TechArticle
- description: Learn how to set outlook flag java using Aspose.Email for Java, covering
    flag creation, recipient flags, completion, removal, and reading options.
  name: Set Outlook Flag Java – Complete Aspose.Email Programming Guide
  steps:
  - name: Create and Initialize the Message
    text: '`MailMessage` is Aspose.Email’s high‑level class that represents an email.
      After you build the message, you convert it to a `MapiMessage` for flag manipulation.
      *We first build a `MailMessage`, set sender/recipient, then convert it to a
      `MapiMessage` for flag manipulation.*'
  - name: Define Follow‑Up Dates (Outlook Flag Reminder)
    text: '`FollowUpOptions` holds the start, reminder, and due dates. Use Java’s
      `Calendar` to set precise timestamps. *Here we set the start, reminder (the
      **outlook flag reminder**), and due dates using the `Calendar` class.*'
  - name: Apply Follow‑Up Options
    text: The `FollowUpManager.setOptions` method attaches the flag to the `MapiMessage`.
      *The `FollowUpOptions` object holds all flag details, which we apply with `FollowUpManager.setOptions`.*
  - name: Save the Message
    text: Save the flagged message as a `.msg` file so Outlook can display the flag.
      *The message is saved as a `.msg` file with the flag attached.*
  - name: Mark as Draft
    text: '`MessageFlags` is a MAPI enumeration that controls the state of the message.
      Setting `MSGFLAG_UNSENT` tells Outlook the item is a draft. *Marking the message
      as unsent ensures Outlook treats it as a draft.*'
  - name: Set Recipient Flag
    text: '`FollowUpManager.setFlagForRecipients` attaches the flag exclusively to
      the recipient’s copy. *The flag is now visible only to the recipients – a classic
      **flag for recipients** scenario.*'
  - name: Load the Message
    text: '`MapiMessage` can read a saved `.msg` file, giving you full access to its
      MAPI properties.'
  - name: Mark as Completed and Save
    text: '`FollowUpManager.completeFlag` updates the flag status, after which you
      persist the changes. *The flag status changes to “Completed” and the updated
      file is saved.*'
  - name: Load and Clear Flag
    text: '`FollowUpManager.clearFlag` removes all flag‑related properties from the
      message. *The message is saved without any follow‑up flag.*'
  - name: Retrieve Options
    text: The returned `options` object gives you full visibility into the flag’s
      configuration. *The `options` object now contains start, due, and reminder dates,
      plus the flag subject – useful when you need to **read flag options** for reporting.*
  type: HowTo
- questions:
  - answer: It’s a pure‑Java API that lets you create, read, and manipulate email
      files (MSG, EML, etc.) without needing Outlook installed.
    question: What is Aspose.Email for Java?
  - answer: Visit the [Aspose website](https://releases.aspose.com/email/java/) to
      download a 30‑day trial.
    question: How do I obtain a free trial license?
  - answer: Outlook supports only one flag per message, but you can store additional
      task data in custom MAPI properties.
    question: Can I set multiple follow‑up flags on a single message?
  - answer: Confirm the `outputDir` path is valid and that the application has permission
      to write to that location.
    question: My message isn’t saved after setting a flag. What should I check?
  - answer: Loop through your message collection and call `FollowUpManager.clearFlag`
      on each `MapiMessage`.
    question: How can I remove flags from many messages at once?
  type: FAQPage
tags:
- outlook flag
- aspose.email
- java email automation
title: Outlook Flag Java सेट करें – Complete Aspose.Email Programming Guide
url: /hi/java/calendar-appointments/aspose-email-java-outlook-follow-up-flags/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Email for Java का उपयोग करके Outlook फ़्लैग सेट करें

## परिचय
यदि आपको प्रोग्रामेटिक रूप से **set outlook flag java** सेट करना है, तो आप सही जगह पर आए हैं। Outlook का फ़ॉलो‑अप फ़्लैग एक सामान्य ई‑मेल को ट्रैक्ड टास्क में बदल देता है, और Aspose.Email for Java आपको Outlook स्थापित किए बिना इन फ़्लैग को मैनेज करने की सुविधा देता है। इस ट्यूटोरियल में हम फ़्लैग बनाना, पढ़ना, पूरा करना और अंत में हटाना, साथ ही विशिष्ट प्राप्तकर्ताओं के लिए फ़्लैग लागू करना सीखेंगे। अंत तक आपके पास एक पुन: उपयोग योग्य Java स्निपेट होगा जो बैकएंड सर्विसेज़ से सीधे टास्क ट्रैकिंग को ऑटोमेट करता है।

## त्वरित उत्तर
- **“set outlook flag java” का क्या अर्थ है?** Java कोड के माध्यम से Outlook आइटम में शुरूआत, रिमाइंडर और ड्यू डेट के साथ फ़्लैग जोड़ना।  
- **कौन सी लाइब्रेरी आवश्यक है?** Aspose.Email for Java (v25.4 या नया)।  
- **क्या लाइसेंस चाहिए?** हाँ – मूल्यांकन के लिए ट्रायल चल सकता है, लेकिन प्रोडक्शन के लिए खरीदा हुआ लाइसेंस आवश्यक है।  
- **क्या केवल प्राप्तकर्ताओं के लिए फ़्लैग सेट कर सकते हैं?** बिल्कुल – `FollowUpManager.setFlagForRecipients` का उपयोग करें।  
- **क्या बाद में फ़्लैग हटाना संभव है?** हाँ – `FollowUpManager.clearFlag` को कॉल करें।

## Outlook फ़ॉलो‑अप फ़्लैग क्या है?
Outlook फ़ॉलो‑अप फ़्लैग एक अंतर्निहित टास्क मार्कर है जो किसी भी मेल आइटम में शुरूआत तिथि, रिमाइंडर और ड्यू डेट संलग्न कर सकता है। यह ई‑मेल को एक ट्रैक्ड एक्शन आइटम में बदल देता है, जिससे आप और आपकी टीम लंबित कार्यों पर नज़र रख सके।

## Aspose.Email for Java क्यों उपयोग करें?
Aspose.Email for Java **70+ ईमेल फ़ॉर्मैट** (MSG, EML, MHTML, और TNEF सहित) को सपोर्ट करता है और सामान्य 8‑कोर सर्वर पर **100,000 से अधिक संदेश प्रति मिनट** प्रोसेस कर सकता है, बिना होस्ट मशीन पर Outlook की आवश्यकता के। यह बैकएंड ऑटोमेशन, अनुपालन रिपोर्टिंग और प्रोजेक्ट‑मैनेजमेंट टूल्स के साथ इंटीग्रेशन के लिए आदर्श है।

## पूर्वापेक्षाएँ
- **Aspose.Email for Java** संस्करण 25.4 या बाद का।  
- **JDK 16+** स्थापित हो।  
- Maven‑संगत IDE (IntelliJ IDEA, Eclipse, आदि)।  
- बेसिक Java ज्ञान और ईमेल अवधारणाओं की परिचितता।

## Aspose.Email for Java सेटअप करना
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

### लाइसेंस प्राप्त करना
प्रोडक्शन उपयोग के लिए Aspose.Email को लाइसेंस चाहिए:

- **फ़्री ट्रायल** – 30‑दिन मूल्यांकन।  
- **टेम्पररी लाइसेंस** – विस्तारित परीक्षण।  
- **पूर्ण लाइसेंस** – स्थायी सब्सक्रिप्शन।

किसी भी ईमेल ऑपरेशन से पहले लाइसेंस को इनिशियलाइज़ करें:

```java
License license = new License();
license.setLicense("path/to/Aspose.Total.Java.lic");
```

## Set Outlook Flag Java (फ़ीचर 1)
### सीधा उत्तर
`MailMessage` लोड करें, उसे `MapiMessage` में बदलें, `FollowUpOptions` कॉन्फ़िगर करें, और `FollowUpManager.setOptions` को कॉल करें। यह क्रम कुछ ही लाइनों के Java कोड में पूरी तरह फ़्लैग्ड Outlook आइटम बनाता है।

### चरण 1: संदेश बनाएं और इनिशियलाइज़ करें
`MailMessage` Aspose.Email की हाई‑लेवल क्लास है जो ई‑मेल को दर्शाती है। संदेश बनाने के बाद आप फ़्लैग मैनीपुलेशन के लिए इसे `MapiMessage` में बदलते हैं।

```java
MailMessage mailMsg = new MailMessage();
mailMsg.setSender(new MailAddress("AETest12@gmail.com"));
mailMsg.getTo().addMailAddress(new MailAddress("receiver@gmail.com"));
mailMsg.setBody("This message will test if follow up options can be added to a new mapi message.");
MapiMessage mapi = MapiMessage.fromMailMessage(mailMsg);
```
*हम पहले एक `MailMessage` बनाते हैं, प्रेषक/प्राप्तकर्ता सेट करते हैं, फिर फ़्लैग मैनीपुलेशन के लिए इसे `MapiMessage` में बदलते हैं।*

### चरण 2: फ़ॉलो‑अप तिथियां परिभाषित करें (Outlook फ़्लैग रिमाइंडर)
`FollowUpOptions` में शुरूआत, रिमाइंडर और ड्यू डेट संग्रहीत होते हैं। सटीक टाइमस्टैम्प सेट करने के लिए Java के `Calendar` का उपयोग करें।

```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 14, 40, 0);
Date dtStartDate = calendar.getTime();
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
calendar.add(Calendar.DATE, 1);
Date dtDueDate = calendar.getTime();
```
*यहाँ हम `Calendar` क्लास का उपयोग करके शुरूआत, रिमाइंडर (**outlook flag reminder**) और ड्यू डेट सेट करते हैं।*

### चरण 3: फ़ॉलो‑अप विकल्प लागू करें
`FollowUpManager.setOptions` मेथड फ़्लैग को `MapiMessage` से जोड़ता है।  

```java
FollowUpOptions options = new FollowUpOptions("Follow Up", dtStartDate, dtDueDate, dtReminderDate);
FollowUpManager.setOptions(mapi, options);
```
*`FollowUpOptions` ऑब्जेक्ट में सभी फ़्लैग विवरण होते हैं, जिन्हें हम `FollowUpManager.setOptions` से लागू करते हैं।*

### चरण 4: संदेश सहेजें
फ़्लैग्ड संदेश को `.msg` फ़ाइल के रूप में सहेजें ताकि Outlook फ़्लैग दिखा सके।

```java
mapi.save(outputDir + "SetFollowUpflag_out.msg");
```
*संदेश को `.msg` फ़ाइल के रूप में फ़्लैग के साथ सहेजा जाता है।*

## प्राप्तकर्ताओं के लिए फ़्लैग सेट करना (फ़ीचर 2)?
ड्राफ्ट के रूप में संदेश को मार्क करने के बाद `FollowUpManager.setFlagForRecipients` का उपयोग करें। यह मेथड फ़्लैग केवल प्राप्तकर्ता की कॉपी पर जोड़ता है, प्रेषक के दृश्य को अपरिवर्तित रखता है। फ़्लैग लागू करने से पहले `MessageFlags.MSGFLAG_UNSENT` सेट करना आवश्यक है। आप `FollowUpOptions` ऑब्जेक्ट का उपयोग करके शुरूआत, रिमाइंडर और ड्यू डेट को कस्टमाइज़ कर सकते हैं।

### सीधा उत्तर
`MessageFlags.MSGFLAG_UNSENT` का उपयोग करके संदेश को ड्राफ्ट बनाएं, फिर `FollowUpManager.setFlagForRecipients` को कॉल करें। Outlook फ़्लैग केवल प्राप्तकर्ताओं को दिखाएगा, प्रेषक को नहीं।

### अवलोकन
कभी‑कभी आपको फ़्लैग **केवल प्राप्तकर्ताओं के लिए** दिखाना पड़ता है। यह उदाहरण पहले संदेश को ड्राफ्ट बनाता है, फिर फ़्लैग जोड़ता है।

#### चरण 1: ड्राफ्ट के रूप में मार्क करें
`MessageFlags` एक MAPI एनेमरेशन है जो संदेश की स्थिति नियंत्रित करता है। `MSGFLAG_UNSENT` सेट करने से Outlook इसे ड्राफ्ट मानता है।

```java
mapi.setMessageFlags(MapiMessageFlags.MSGFLAG_UNSENT);
```
*संदेश को अनसेंट मार्क करने से Outlook इसे ड्राफ्ट के रूप में ट्रीट करता है।*

#### चरण 2: प्राप्तकर्ता फ़्लैग सेट करें
`FollowUpManager.setFlagForRecipients` फ़्लैग को केवल प्राप्तकर्ता की कॉपी पर संलग्न करता है।

```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
FollowUpManager.setFlagForRecipients(mapi, "Follow up", dtReminderDate);
```
*फ़्लैग अब केवल प्राप्तकर्ताओं को दिखाई देगा – एक क्लासिक **flag for recipients** परिदृश्य।*

## Outlook फ़ॉलो‑अप फ़्लैग को पूर्ण (Completed) के रूप में मार्क करना (फ़ीचर 3)?
`.msg` फ़ाइल को `MapiMessage` में लोड करें, फिर `FollowUpManager.completeFlag` को कॉल करें। यह फ़्लैग स्थिति को Completed में बदल देता है और Outlook में चेक‑मार्क जोड़ता है। पूर्ण करने के बाद फ़ाइल को सहेजें ताकि परिवर्तन स्थायी हो। यदि ऑडिट के लिए आवश्यक हो तो `FlagCompleteTime` प्रॉपर्टी को समायोजित करके पूर्णता समय सेट कर सकते हैं।

### सीधा उत्तर
मौजूदा `.msg` फ़ाइल को `MapiMessage` में लोड करें, `FollowUpManager.completeFlag` को कॉल करें, और फ़ाइल को सहेजें। फ़्लैग स्थिति “Completed” में बदल जाएगी और Outlook में चेक‑मार्क के साथ दिखेगी।

### चरण 1: संदेश लोड करें
`MapiMessage` सहेजी गई `.msg` फ़ाइल पढ़ सकता है, जिससे आपको उसके सभी MAPI प्रॉपर्टीज़ तक पूर्ण पहुंच मिलती है।

```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
```

### चरण 2: पूर्ण के रूप में मार्क करें और सहेजें
`FollowUpManager.completeFlag` फ़्लैग स्थिति अपडेट करता है, जिसके बाद आप बदलावों को स्थायी बनाते हैं।

```java
FollowUpManager.markAsCompleted(mapi);
mapi.save(outputDir + "MarkedCompleted_out.msg");
```
*फ़्लैग स्थिति “Completed” में बदल गई और अपडेटेड फ़ाइल सहेजी गई।*

## Outlook फ़ॉलो‑अप फ़्लैग हटाना (फ़ीचर 4)?
`.msg` फ़ाइल को `MapiMessage` के साथ खोलें, `FollowUpManager.clearFlag` को इनवोक करें, और फिर संदेश को सहेजें। यह सभी फ़्लैग‑संबंधित MAPI प्रॉपर्टीज़ को हटा देता है, जिससे Outlook अब कोई फ़ॉलो‑अप इंडिकेटर नहीं दिखाएगा। यह तब उपयोगी है जब टास्क रद्द हो गया हो या अब प्रासंगिक न हो। किसी भी कस्टम रिमाइंडर प्रॉपर्टी को भी साफ़ करना न भूलें ताकि बची हुई नोटिफिकेशन न रहे।

### सीधा उत्तर
`.msg` फ़ाइल को `MapiMessage` के साथ खोलें, `FollowUpManager.clearFlag` को इनवोक करें, और फ़ाइल को सहेजें। संदेश अब Outlook में कोई फ़ॉलो‑अप इंडिकेटर नहीं दिखाएगा।

### चरण 1: लोड करें और फ़्लैग साफ़ करें
`FollowUpManager.clearFlag` संदेश से सभी फ़्लैग‑संबंधित प्रॉपर्टीज़ हटाता है।

```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpManager.clearFlag(mapi);
mapi.save(outputDir + "FollowUpFlagRemoved_out.msg");
```
*संदेश को बिना किसी फ़ॉलो‑अप फ़्लैग के सहेजा गया।*

## फ़्लैग विकल्प पढ़ना (फ़ीचर 5)?
लोड किए गए `MapiMessage` पर `FollowUpManager.getOptions` कॉल करें ताकि `FollowUpOptions` ऑब्जेक्ट प्राप्त हो सके। यह ऑब्जेक्ट शुरूआत, ड्यू, रिमाइंडर तिथियां और फ़्लैग विषय प्रदान करता है, जिससे आप फ़्लैग विवरण को डिस्प्ले या लॉग कर सकते हैं। यह रिपोर्टिंग और अनुपालन ऑडिट के लिए उपयोगी है।

### सीधा उत्तर
लोड किए गए `MapiMessage` पर `FollowUpManager.getOptions` का उपयोग करके `FollowUpOptions` ऑब्जेक्ट प्राप्त करें, जिसमें शुरूआत, ड्यू, रिमाइंडर तिथियां और फ़्लैग विषय शामिल होते हैं। यह रिपोर्टिंग या अनुपालन ऑडिट में सहायक है।

### चरण 1: विकल्प प्राप्त करें
रिटर्न किया गया `options` ऑब्जेक्ट फ़्लैग की पूरी कॉन्फ़िगरेशन दिखाता है।

```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpOptions options = FollowUpManager.getOptions(mapi);
```
*`options` ऑब्जेक्ट अब शुरूआत, ड्यू, रिमाइंडर तिथियां और फ़्लैग विषय रखता है – रिपोर्टिंग के लिए **read flag options** आवश्यक होने पर उपयोगी।*

## व्यावहारिक अनुप्रयोग
- **टास्क‑मैनेजमेंट इंटीग्रेशन:** फ़्लैग्ड ईमेल को Jira, Trello, या Azure Boards के साथ सिंक करें।  
- **ऑटोमेटेड रिमाइंडर:** लंबित फ़ॉलो‑अप के लिए दैनिक रिमाइंडर ईमेल जेनरेट करें।  
- **अनुपालन ऑडिट:** नियामक रिपोर्टिंग के लिए फ़्लैग डेटा एक्सपोर्ट करें, प्रोग्रामेटिक रूप से फ़्लैग विकल्प पढ़ने की क्षमता का उपयोग करके।

## प्रदर्शन विचार
- **तिथि गणनाएँ:** लूप के भीतर नहीं, बल्कि बैच के लिए एक बार तिथियां गणना करें।  
- **संसाधन प्रबंधन:** संदेश सहेजने के बाद सभी स्ट्रीम या फ़ाइल हैंडल बंद करें।  
- **मेमोरी उपयोग:** बड़े मेलबॉक्स को चंक्स में प्रोसेस करें ताकि हीप प्रेशर से बचा जा सके; Aspose.Email पूरी फ़ाइल को मेमोरी में लोड किए बिना कई‑सौ पेज़ मेलबॉक्स संभाल सकता है।

## सामान्य समस्याएँ और समाधान
| समस्या | कारण | समाधान |
|-------|-------|-----|
| फ़्लैग Outlook में नहीं दिख रहा | `MessageFlags` सही से सेट नहीं है | फ़्लैग लागू करने से पहले `setMessageFlags` को `MSGFLAG_UNSENT` पर सेट करना सुनिश्चित करें। |
| Save पर `AccessDeniedException` फेंकता है | फ़ाइल पाथ गलत या लिखने की अनुमति नहीं | आउटपुट डायरेक्टरी मौजूद है और एप्लिकेशन को लिखने की अनुमति है, यह सत्यापित करें। |
| तिथियां एक दिन आगे हैं | टाइम‑ज़ोन मिसमैच | लगातार `TimeZone.getTimeZone("GMT")` या अपने स्थानीय ज़ोन का उपयोग करें। |

## अक्सर पूछे जाने वाले प्रश्न
**प्रश्न:** Aspose.Email for Java क्या है?  
**उत्तर:** यह एक शुद्ध‑Java API है जो आपको Outlook स्थापित किए बिना ईमेल फ़ाइलें (MSG, EML, आदि) बनाना, पढ़ना और मैनीपुलेट करना देता है।

**प्रश्न:** मुफ्त ट्रायल लाइसेंस कैसे प्राप्त करें?  
**उत्तर:** 30‑दिन ट्रायल डाउनलोड करने के लिए [Aspose वेबसाइट](https://releases.aspose.com/email/java/) पर जाएँ।

**प्रश्न:** क्या एक ही संदेश पर कई फ़ॉलो‑अप फ़्लैग सेट कर सकते हैं?  
**उत्तर:** Outlook प्रति संदेश केवल एक फ़्लैग सपोर्ट करता है, लेकिन आप अतिरिक्त टास्क डेटा को कस्टम MAPI प्रॉपर्टीज़ में स्टोर कर सकते हैं।

**प्रश्न:** फ़्लैग सेट करने के बाद मेरा संदेश सहेजा नहीं जा रहा। क्या जांचें?  
**उत्तर:** `outputDir` पाथ वैध है और एप्लिकेशन को उस लोकेशन पर लिखने की अनुमति है, यह सुनिश्चित करें।

**प्रश्न:** कई संदेशों से फ़्लैग एक साथ कैसे हटाएँ?  
**उत्तर:** अपने संदेश संग्रह पर लूप चलाएँ और प्रत्येक `MapiMessage` पर `FollowUpManager.clearFlag` को कॉल करें।

## संसाधन
- [डॉक्यूमेंटेशन](https://reference.aspose.com/email/java/)
- [Aspose.Email for Java डाउनलोड करें](https://releases.aspose.com/email/java/)
- [Aspose.Email फ्री ट्रायल](https://purchase.aspose.com/purchase/free-trial/aspose-email-java)

---

**अंतिम अपडेट:** 2026-07-27  
**परीक्षित संस्करण:** Aspose.Email for Java 25.4 (JDK 16)  
**लेखक:** Aspose  

{{< blocks/products/products-backtop-button >}}

## संबंधित ट्यूटोरियल

- [Aspose.Email for Java के साथ Outlook कैटेगरीज मैनेज करें - एक व्यापक गाइड](/email/java/calendar-appointments/manage-outlook-categories-aspose-email-java/)
- [Aspose.Email के साथ Outlook नोट्स जावा में बनाएं – पूर्ण गाइड](/email/java/calendar-appointments/create-customize-outlook-notes-aspose-email-java/)
- [Aspose.Email for Java का उपयोग करके Microsoft Exchange में टास्क बनाएं: एक पूर्ण गाइड](/email/java/exchange-server-integration/create-tasks-exchange-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}