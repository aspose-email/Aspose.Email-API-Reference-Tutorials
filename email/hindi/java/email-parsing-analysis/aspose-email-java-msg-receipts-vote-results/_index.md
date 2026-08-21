---
date: '2026-06-13'
description: Aspose.Email for Java का उपयोग करके MSG फ़ाइलें पढ़ना और MSG अटैचमेंट्स
  को पार्स करना सीखें, डिलीवरी/रीड रसीदें और वोट परिणामों को कुशलतापूर्वक निकालें।
  सेटअप, कोड, और सर्वोत्तम प्रथाएँ शामिल हैं।
keywords:
- how to read msg
- parse msg attachments
- Aspose.Email for Java
schemas:
- author: Aspose
  dateModified: '2026-06-13'
  description: Learn how to read MSG files and parse MSG attachments using Aspose.Email
    for Java, extracting delivery/read receipts and vote results efficiently. Includes
    setup, code, and best practices.
  headline: How to Read MSG Files with Aspose.Email for Java
  type: TechArticle
- description: Learn how to read MSG files and parse MSG attachments using Aspose.Email
    for Java, extracting delivery/read receipts and vote results efficiently. Includes
    setup, code, and best practices.
  name: How to Read MSG Files with Aspose.Email for Java
  steps:
  - name: Load the MSG File
    text: MapiMessage is the Aspose.Email class that represents an Outlook MSG message.
  - name: Iterate Over Recipients
    text: MapiRecipient represents a single recipient (To, CC, or BCC) in the MSG
      file.
  - name: Retrieve and Print Delivery Time
    text: DeliveryTime is a property of MapiRecipient that holds the timestamp when
      the message was delivered to the recipient’s server.
  - name: Retrieve and Print Read Time
    text: ReadTime is a property of MapiRecipient indicating when the recipient opened
      the message, if that information is available.
  - name: Load the MSG File
    text: MapiMessage is used again to access the voting information embedded in the
      MSG file.
  - name: Iterate Over Recipients
    text: MapiRecipient provides access to each participant’s voting choice and response
      time.
  - name: Retrieve and Print Response
    text: The `VotingResponse` property contains the actual vote (e.g., “Accept”,
      “Decline”, or custom options).
  - name: Retrieve and Print Response Time
    text: '`VotingResponseTime` records when the recipient submitted their vote, allowing
      chronological analysis of poll activity.'
  type: HowTo
- questions:
  - answer: Split the file into smaller segments or use the streaming API to read
      portions without full in‑memory loading.
    question: How do I handle MSG files larger than 500 MB?
  - answer: Yes, map the receipt and vote fields to your DB schema and use JDBC or
      an ORM to persist them.
    question: Can I store the extracted data directly into a database?
  - answer: Absolutely; Aspose.Email for Java is platform‑agnostic and runs on any
      OS with a supported JDK.
    question: Does the library work on Linux environments?
  - answer: Use `MailMessage.getAttachments()` after loading the MSG; the method returns
      a collection of all embedded files.
    question: Is there a way to extract attachments while reading receipts?
  - answer: Reach out via the official Aspose Email Forum for community help or open
      a support ticket with a valid license.
    question: What support options are available if I encounter bugs?
  type: FAQPage
title: Aspose.Email for Java के साथ MSG फ़ाइलें कैसे पढ़ें
url: /hi/java/email-parsing-analysis/aspose-email-java-msg-receipts-vote-results/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Email for Java के साथ MSG फ़ाइलें कैसे पढ़ें

## परिचय

प्रोग्रामेटिक रूप से MSG फ़ाइलें पढ़ने से आप Outlook संदेशों से मूल्यवान ट्रैकिंग डेटा—डिलीवरी रसीदें, पढ़ने की पुष्टि, और मतदान परिणाम—प्राप्त कर सकते हैं। इस गाइड में हम Aspose.Email for Java का उपयोग करके **msg कैसे पढ़ें** फ़ाइलें दिखाएंगे, आवश्यक सेटअप को समझाएंगे, और रसीद और वोट जानकारी को कुशलतापूर्वक निकालने का प्रदर्शन करेंगे।

## त्वरित उत्तर
- **MSG पार्सिंग को संभालने वाली लाइब्रेरी कौन सी है?** Aspose.Email for Java.  
- **क्या मैं पढ़ने की रसीदें निकाल सकता हूँ?** हाँ, API डिलीवरी और पढ़ने के टाइमस्टैम्प लौटाता है।  
- **क्या वोट डेटा उपलब्ध है?** बिल्कुल; आप प्रत्येक प्राप्तकर्ता की वोटिंग प्रतिक्रिया प्राप्त कर सकते हैं।  
- **क्या मुझे लाइसेंस चाहिए?** परीक्षण के लिए ट्रायल काम करता है; एक पेड लाइसेंस मूल्यांकन सीमाओं को हटा देता है।  
- **कौन सा Java संस्करण आवश्यक है?** Java 16 या बाद का संस्करण अनुशंसित है।

## Aspose.Email for Java क्या है?
Aspose.Email for Java एक स्वतंत्र Java लाइब्रेरी है जो Microsoft Outlook की आवश्यकता के बिना ईमेल फ़ॉर्मेट्स का निर्माण, हेरफेर और रूपांतरण सक्षम करती है। यह MSG, EML, PST और कई अन्य फ़ॉर्मेट्स के लिए एक समृद्ध ऑब्जेक्ट मॉडल प्रदान करती है, जिससे डेवलपर्स सीधे Java कोड से ईमेल डेटा के साथ काम कर सकते हैं। (45 words)

## MSG फ़ाइलें पढ़ने के लिए Aspose.Email for Java का उपयोग क्यों करें?
Aspose.Email for Java **30+ ईमेल फ़ॉर्मेट्स** का समर्थन करता है और पूरी फ़ाइल को मेमोरी में लोड किए बिना **500 MB** तक की MSG फ़ाइलों को प्रोसेस कर सकता है। इसका हाई‑परफ़ॉर्मेंस पार्सिंग इंजन CPU और मेमोरी की खपत को कम करता है, जिससे यह बड़े‑पैमाने पर मेल‑आर्काइव प्रोसेसिंग और रियल‑टाइम एनालिटिक्स परिदृश्यों के लिए आदर्श बन जाता है। (48 words)

## पूर्वापेक्षाएँ
- **Libraries & Dependencies:** Aspose.Email for Java संस्करण 25.4 या बाद का और JDK 16+ रनटाइम।  
- **IDE:** IntelliJ IDEA, Eclipse, या Maven समर्थन वाला कोई भी Java‑compatible IDE।  
- **Basic Skills:** Java सिंटैक्स और ऑब्जेक्ट‑ओरिएंटेड अवधारणाओं की परिचितता।

## लाइसेंस प्राप्ति
Aspose.Email for Java का उपयोग करने के लिए, आपको एक लाइसेंस चाहिए:
- **Free Trial:** उपलब्ध मुफ्त ट्रायल संस्करण से शुरू करें जो [Aspose's website](https://releases.aspose.com/email/java/) पर उपलब्ध है।  
- **Temporary License:** [purchase page](https://purchase.aspose.com/temporary-license/) से एक टेम्पररी लाइसेंस का अनुरोध करें।  
- **Purchase:** यदि आप मूल्यांकन से संतुष्ट हैं, तो सभी फीचर्स की पूर्ण पहुँच के लिए लाइसेंस खरीदें via [Buy Aspose Products](https://purchase.aspose.com/buy) पेज।  

## आप MSG फ़ाइल से पढ़ने और डिलीवरी रसीद जानकारी कैसे निकालते हैं?
MSG फ़ाइल को लोड करें, उसके प्राप्तकर्ताओं पर इटररेट करें, और `DeliveryTime` और `ReadTime` प्रॉपर्टीज़ पढ़ें। यह तरीका प्रत्येक प्राप्तकर्ता के मेल सर्वर द्वारा संदेश डिलीवर किए जाने और प्राप्तकर्ता द्वारा इसे खोलने के सटीक टाइमस्टैम्प लौटाता है, जिससे आपको विश्लेषण के लिए सटीक ट्रैकिंग डेटा मिलता है। (53 words)

### चरण 1: MSG फ़ाइल लोड करें
MapiMessage Aspose.Email क्लास है जो Outlook MSG संदेश का प्रतिनिधित्व करता है।  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```  

### चरण 2: प्राप्तकर्ताओं पर इटररेट करें
MapiRecipient MSG फ़ाइल में एकल प्राप्तकर्ता (To, CC, या BCC) का प्रतिनिधित्व करता है।  
```java
import com.aspose.email.MapiMessage;
import com.aspose.email.MapiRecipient;
import com.aspose.email.MapiPropertyTag;

public class RetrieveReceipts {
    public static void main(String[] args) {
        String dataDir = "YOUR_DOCUMENT_DIRECTORY/outlook/";
        MapiMessage msg = MapiMessage.fromFile(dataDir + "message.msg");
```  

### चरण 3: डिलीवरी टाइम प्राप्त करें और प्रिंट करें
DeliveryTime MapiRecipient की एक प्रॉपर्टी है जो उस टाइमस्टैम्प को रखती है जब संदेश प्राप्तकर्ता के सर्वर पर डिलीवर किया गया था।  
```java
        for (MapiRecipient recipient : msg.getRecipients()) {
            System.out.println("Recipient: " + recipient.getDisplayName());
```  

### चरण 4: रीड टाइम प्राप्त करें और प्रिंट करें
ReadTime MapiRecipient की एक प्रॉपर्टी है जो दर्शाती है कि प्राप्तकर्ता ने संदेश कब खोला, यदि वह जानकारी उपलब्ध है।  
```java
            System.out.println("Delivery time: " + 
                recipient.getProperties().get_Item(MapiPropertyTag.PR_RECIPIENT_TRACKSTATUS_TIME_DELIVERY).getDateTime());
```  

## आप MSG फ़ाइल से वोट परिणाम कैसे पढ़ते हैं?
संदेश को लोड करने के बाद, API प्रत्येक प्राप्तकर्ता की वोटिंग प्रतिक्रिया और उनके उत्तर देने का समय उजागर करता है, जिससे आप प्रोग्रामेटिक रूप से पोल परिणामों को एकत्रित कर सकते हैं। यह डेटा सारांश रिपोर्ट बनाने या तेज़ निर्णय‑लेने के लिए सीधे बिजनेस इंटेलिजेंस डैशबोर्ड में फीड करने के लिए उपयोग किया जा सकता है। (53 words)

### चरण 1: MSG फ़ाइल लोड करें
MapiMessage फिर से उपयोग किया जाता है MSG फ़ाइल में एम्बेडेड वोटिंग जानकारी तक पहुँचने के लिए।  
```java
            System.out.println("Read time: " + 
                recipient.getProperties().get_Item(MapiPropertyTag.PR_RECIPIENT_TRACKSTATUS_TIME_READ).getDateTime());
        }
    }
}
```  

### चरण 2: प्राप्तकर्ताओं पर इटररेट करें
MapiRecipient प्रत्येक प्रतिभागी की वोटिंग विकल्प और प्रतिक्रिया समय तक पहुँच प्रदान करता है।  
```java
import com.aspose.email.MapiMessage;
import com.aspose.email.MapiRecipient;
import com.aspose.email.MapiPropertyTag;

public class ReadVoteResults {
    public static void main(String[] args) {
        String dataDir = "YOUR_DOCUMENT_DIRECTORY/outlook/";
        MapiMessage msg = MapiMessage.fromFile(dataDir + "message.msg");
```  

### चरण 3: प्रतिक्रिया प्राप्त करें और प्रिंट करें
`VotingResponse` प्रॉपर्टी वास्तविक वोट (जैसे, “Accept”, “Decline”, या कस्टम विकल्प) रखती है।  
```java
        for (MapiRecipient recipient : msg.getRecipients()) {
            System.out.println("Recipient: " + recipient.getDisplayName());
```  

### चरण 4: प्रतिक्रिया समय प्राप्त करें और प्रिंट करें
`VotingResponseTime` रिकॉर्ड करता है कि प्राप्तकर्ता ने अपना वोट कब सबमिट किया, जिससे पोल गतिविधि का कालक्रमिक विश्लेषण संभव होता है।  
```java
            System.out.println("Response: " + 
                recipient.getProperties().get_Item(MapiPropertyTag.PR_RECIPIENT_AUTORESPONSE_PROP_RESPONSE).getString());
```  

## व्यावहारिक अनुप्रयोग
1. **Email Campaign Tracking:** रसीद टाइमस्टैम्प का विश्लेषण करके ओपन रेट और डिलीवरी सफलता मापें।  
2. **Survey Analysis:** Outlook पोल्स से वोट परिणामों को एकत्रित करके तेज़ निर्णय‑लेने के लिए उपयोग करें।  
3. **Customer Feedback Management:** प्रतिक्रिया डेटा को CRM या एनालिटिक्स प्लेटफ़ॉर्म में खींचें गहरी अंतर्दृष्टियों के लिए।

इन निकाले गए डेटा को डेटाबेस या BI टूल्स के साथ एकीकृत करने से कच्चे ईमेल डेटा का मूल्य बढ़ जाता है।

## प्रदर्शन विचार
- बड़े MSG फ़ाइलों को **chunks** में प्रोसेस करें ताकि मेमोरी उपयोग कम रहे।  
- हजारों संदेशों से निपटते समय **streaming APIs** का उपयोग करें।  
- तेज़ लुक‑अप के लिए प्राप्तकर्ता डेटा को `ArrayList` या `HashMap` जैसे हल्के कलेक्शन्स में स्टोर करें।

## सामान्य समस्याएँ और समाधान
- **Null timestamps:** एक गायब `ReadTime` आमतौर पर मतलब है कि प्राप्तकर्ता ने अभी तक संदेश नहीं खोला है।  
- **Large attachments:** यदि MSG में बड़े अटैचमेंट हैं, तो `LoadOptions.setPreserveEmbeddedResources(false)` सक्षम करें ताकि उन्हें मेमोरी में लोड न किया जाए।  
- **Encoding problems:** गैर‑ASCII कंटेंट पढ़ते समय `MailMessage.setCharset(Charset.forName("UTF-8"))` के माध्यम से सही कोड पेज सेट करना सुनिश्चित करें।

## अक्सर पूछे जाने वाले प्रश्न
**Q: 500 MB से बड़ी MSG फ़ाइलों को मैं कैसे संभालूँ?**  
A: फ़ाइल को छोटे हिस्सों में विभाजित करें या स्ट्रीमिंग API का उपयोग करके भागों को पढ़ें बिना पूरी मेमोरी में लोड किए।

**Q: क्या मैं निकाले गए डेटा को सीधे डेटाबेस में स्टोर कर सकता हूँ?**  
A: हाँ, रसीद और वोट फ़ील्ड को अपने DB स्कीमा में मैप करें और JDBC या ORM का उपयोग करके उन्हें स्थायी बनाएं।

**Q: क्या लाइब्रेरी Linux वातावरण में काम करती है?**  
A: बिल्कुल; Aspose.Email for Java प्लेटफ़ॉर्म‑अज्ञेय है और समर्थित JDK वाले किसी भी OS पर चलती है।

**Q: क्या रसीद पढ़ते समय अटैचमेंट निकालने का कोई तरीका है?**  
A: MSG लोड करने के बाद `MailMessage.getAttachments()` का उपयोग करें; यह मेथड सभी एम्बेडेड फ़ाइलों का कलेक्शन लौटाता है।

**Q: यदि मुझे बग्स मिलें तो कौन से सपोर्ट विकल्प उपलब्ध हैं?**  
A: आधिकारिक Aspose Email Forum के माध्यम से समुदाय सहायता प्राप्त करें या वैध लाइसेंस के साथ सपोर्ट टिकट खोलें।

## संसाधन
- **डॉक्यूमेंटेशन:** [Aspose Email डॉक्यूमेंटेशन](https://reference.aspose.com/email/java/)  
- **डॉक्यूमेंटेशन (डुप्लिकेट):** [Aspose Email डॉक्यूमेंटेशन](https://reference.aspose.com/email/java/)  
- **SDK डाउनलोड:** [Aspose Email Downloads](https://releases.aspose.com/email/java/)  
- **डाउनलोड सेक्शन:** [Download Section](https://releases.aspose.com/email/java/)  
- **लाइसेंस खरीदें:** [Buy Aspose Products](https://purchase.aspose.com/buy)  
- **फ्री ट्रायल:** उपलब्ध मुफ्त ट्रायल संस्करण से शुरू करें एक [Free Trial Version](https://releases.aspose.com/email/java/)  
- **टेम्पररी लाइसेंस:** [Request Temporary License](https://purchase.aspose.com/temporary-license/)  
- **सपोर्ट फ़ोरम:** [Aspose Email Forum](https://forum.aspose.com/c/email/10)  
- **सपोर्ट फ़ोरम (डुप्लिकेट):** [Aspose Email Forum](https://forum.aspose.com/c/email/10)

---

**अंतिम अपडेट:** 2026-06-13  
**परीक्षण किया गया संस्करण:** Aspose.Email for Java 25.4  
**लेखक:** Aspose

```java
            System.out.println("Response time: " + 
                recipient.getProperties().get_Item(MapiPropertyTag.PR_RECIPIENT_TRACKSTATUS_TIME).getDateTime());
        }
    }
}
```

## संबंधित ट्यूटोरियल
- [Aspose.Email for Java का उपयोग करके Outlook MSG फ़ाइलें लोड और पार्स कैसे करें: एक व्यापक गाइड](/email/java/mapi-operations/outlook-msg-aspose-email-java-guide/)
- [Aspose.Email for Java के साथ MSG को EML में कनवर्ट करें और अटैचमेंट्स प्रबंधित करें](/email/java/attachments-handling/aspose-email-java-master-msg-attachments-parsing/)
- [Java – MSG फ़ाइलों से इनलाइन अटैचमेंट्स निकालें Aspose.Email के साथ](/email/java/attachments-handling/extract-inline-attachments-msg-files-java-aspose-email/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}