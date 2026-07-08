---
date: '2026-07-08'
description: Aspose.Email का उपयोग करके EWS क्लाइंट Java बनाने के बारे में जानें,
  जो कुशल email प्रबंधन के लिए है, जिसमें message deletion, appending, और Exchange
  Server पर user impersonation शामिल है।
keywords:
- create ews client java
- Aspose.Email Java
- Exchange Server EWS
- email impersonation Java
lastmod: '2026-07-08'
og_description: Aspose.Email का उपयोग करके EWS क्लाइंट Java बनाने के बारे में जानें,
  जो कुशल email प्रबंधन के लिए है, जिसमें message deletion, appending, और Exchange
  Server पर user impersonation शामिल है।
og_image_alt: 'Developer guide: Create EWS client Java with Aspose.Email for user
  management'
og_title: Aspose.Email के साथ EWS क्लाइंट Java बनाएं – उपयोगकर्ताओं को प्रबंधित करें
schemas:
- author: Aspose
  dateModified: '2026-07-08'
  description: Learn how to create EWS client Java using Aspose.Email for efficient
    email management, including message deletion, appending, and user impersonation
    on Exchange Server.
  headline: Create EWS Client Java with Aspose.Email – Manage Users
  type: TechArticle
- description: Learn how to create EWS client Java using Aspose.Email for efficient
    email management, including message deletion, appending, and user impersonation
    on Exchange Server.
  name: Create EWS Client Java with Aspose.Email – Manage Users
  steps:
  - name: '**Automated Email Cleanup:** Schedule a nightly job that clears out stale
      Draft folders across dozens of mailboxes.'
    text: '**Automated Email Cleanup:** Schedule a nightly job that clears out stale
      Draft folders across dozens of mailboxes.'
  - name: '**Batch Email Distribution:** Append a templated announcement to the Inbox
      of every employee with a single loop.'
    text: '**Batch Email Distribution:** Append a templated announcement to the Inbox
      of every employee with a single loop.'
  - name: '**Shared Mailbox Management:** Impersonate a department mailbox to archive
      old messages without granting each user full access.'
    text: '**Shared Mailbox Management:** Impersonate a department mailbox to archive
      old messages without granting each user full access.'
  type: HowTo
- questions:
  - answer: Check the endpoint URL, credentials, and network firewalls; enable detailed
      logging in Aspose.Email to capture HTTP request/response data.
    question: How do I troubleshoot connectivity issues with EWS?
  - answer: Yes—its batch APIs let you process **10,000+** messages per minute while
      keeping memory usage under 200 MB.
    question: Can Aspose.Email handle large volumes of emails efficiently?
  - answer: Managing shared mailboxes, performing bulk archiving, and running scheduled
      reports on behalf of multiple users without storing their passwords.
    question: What are typical use cases for user impersonation in EWS?
  - answer: Aspose.Email itself imposes no call limits; however, Exchange may enforce
      throttling policies that you need to respect.
    question: Are there limits on API calls imposed by Aspose.Email?
  - answer: Store them in encrypted configuration files or use Azure Key Vault / AWS
      Secrets Manager, and always use HTTPS for EWS endpoints.
    question: How can I keep credentials secure in my Java code?
  type: FAQPage
tags:
- create ews client java
- Aspose.Email
- Java Exchange
- email impersonation
- EWS client
title: Aspose.Email के साथ EWS क्लाइंट Java बनाएं – उपयोगकर्ताओं को प्रबंधित करें
url: /hi/java/exchange-server-integration/aspose-email-java-ews-client-user-management/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# ईमेल प्रबंधन में महारत: Aspose.Email Java के लिए EWS क्लाइंट उपयोगकर्ता और इम्पर्सोनेशन

## परिचय

इस ट्यूटोरियल में आप Aspose.Email के साथ **EWS client Java** एप्लिकेशन बनाएँगे, जिससे आप एक ही Java कोडबेस से कई Exchange Server मेलबॉक्स को प्रबंधित कर सकेंगे। हम `EWSClient` इंस्टेंस बनाने, संदेशों को हटाने, नए ईमेल जोड़ने, और अन्य उपयोगकर्ताओं का इम्पर्सोनेशन करने की प्रक्रिया को देखेंगे—ऐसे कार्य जो एंटरप्राइज़ वातावरण में मैन्युअल काम के घंटों को बचाते हैं।

### आप क्या सीखेंगे
- कैसे अलग-अलग क्रेडेंशियल्स का उपयोग करके **EWS client Java** ऑब्जेक्ट बनाएँ।  
- चयनित फ़ोल्डर से सभी संदेशों को हटाने की कुशल तकनीकें।  
- एक तैयार ईमेल को उपयोगकर्ता के मेलबॉक्स में जोड़ने के चरण।  
- शेयर किए गए मेलबॉक्स परिदृश्यों के लिए दूसरे मेलबॉक्स का इम्पर्सोनेशन कैसे करें।

अब जब आप जानते हैं कि हम क्या कवर करेंगे, चलिए विकास वातावरण को तैयार करते हैं।

## त्वरित उत्तर
- **पहला कदम क्या है?** अपने `pom.xml` में Aspose.Email Maven डिपेंडेंसी जोड़ें।  
- **कौन सा क्लास Exchange कनेक्शन को दर्शाता है?** `EWSClient` (या इसका इंटरफ़ेस `IEWSClient`)।  
- **क्या मैं सभी संदेश एक ही कॉल में हटा सकता हूँ?** हाँ—`listMessages` के साथ इटरेट करें और प्रत्येक URI पर `deleteMessage` कॉल करें।  
- **SMTP के बिना ईमेल कैसे भेजें?** `appendMessage` का उपयोग करके `MailMessage` को सीधे फ़ोल्डर में रखें।  
- **क्या इम्पर्सोनेशन सुरक्षित है?** यह मूल क्रेडेंशियल्स के तहत चलता है और Exchange की डेलीगेशन नीतियों का सम्मान करता है।

## create EWS client Java क्या है?
`create ews client java` का अर्थ है Java एप्लिकेशन में `EWSClient` ऑब्जेक्ट को इंस्टैंसिएट करना ताकि आप Exchange Web Services (EWS) ऑपरेशन्स को प्रोग्रामेटिक रूप से कॉल कर सकें। यह तरीका मैन्युअल Outlook इंटरैक्शन की आवश्यकता को हटाता है और स्वचालित मेलबॉक्स प्रोसेसिंग को सक्षम करता है। प्रत्येक उपयोगकर्ता के लिए एक समर्पित क्लाइंट बनाकर, आप क्रेडेंशियल्स को अलग कर सकते हैं, प्रति‑मेलबॉक्स नीतियों को लागू कर सकते हैं, और कोड डुप्लिकेशन के बिना दर्जनों खातों में समाधान को स्केल कर सकते हैं।

## EWS इंटीग्रेशन के लिए Aspose.Email क्यों उपयोग करें?
Aspose.Email **50+** EWS ऑपरेशन्स का समर्थन करता है, **सैकड़ों‑पृष्ठ** वाले मेलबॉक्स को पूरी स्टोर को मेमोरी में लोड किए बिना संभालता है, और सामान्य सर्वर हार्डवेयर पर प्रति मिनट **10,000** तक संदेश प्रोसेस करता है। ये मापनीय क्षमताएँ इसे बड़े‑पैमाने पर ईमेल ऑटोमेशन के लिए शीर्ष विकल्प बनाती हैं। लाइब्रेरी लो‑लेवल SOAP विवरणों को भी एब्स्ट्रैक्ट करती है, एक साफ़, टाइप‑सेफ़ API प्रदान करती है जो विकास समय को कम करती है और बग्स को न्यूनतम करती है।

## आवश्यकताएँ
- **Java Development Kit (JDK)** ≥ 16।  
- **Maven** डिपेंडेंसी मैनेजमेंट के लिए।  
- **Aspose.Email for Java** लाइब्रेरी (Maven के माध्यम से जोड़ें)।  
- Exchange Web Services (EWS) अवधारणाओं का बुनियादी ज्ञान।

## Aspose.Email for Java सेटअप करना
अपने Maven `pom.xml` में लाइब्रेरी जोड़ें:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### लाइसेंस प्राप्ति
Aspose.Email एक मुफ्त ट्रायल प्रदान करता है, जिसमें पूर्ण क्षमताओं के लिए अस्थायी लाइसेंस का अनुरोध करने का विकल्प है। दीर्घकालिक उपयोग के लिए, [Aspose's purchase page](https://purchase.aspose.com/buy) से लाइसेंस खरीदने पर विचार करें।

## EWS client Java कैसे बनाएं?
उपयुक्त क्रेडेंशियल्स के साथ Exchange सेवा लोड करें और एक `IEWSClient` इंस्टेंस प्राप्त करें—यह दो‑चरणीय पैटर्न प्रत्येक बाद के ऑपरेशन का मूल है। आप एक ही क्लाइंट को कई कार्यों के लिए पुन: उपयोग कर सकते हैं या अलगाव के लिए प्रत्येक उपयोगकर्ता के लिए अलग इंस्टेंस बना सकते हैं। **`IEWSClient` वह इंटरफ़ेस है जो सभी EWS ऑपरेशन्स को उजागर करता है, जबकि `EWSClient` एक स्थैतिक फ़ैक्टरी मेथड प्रदान करता है जिससे इम्प्लीमेंटेशन प्राप्त किया जा सकता है।**

### EWSClient इंस्टेंस बनाएं
**परिभाषा:** `EWSClient` (जो `IEWSClient` इंटरफ़ेस के माध्यम से एक्सपोज़ किया गया है) Aspose.Email का मुख्य ऑब्जेक्ट है जो EWS के माध्यम से Exchange सर्वर के साथ संचार करता है।

#### आवश्यक क्लासेस इम्पोर्ट करें
आवश्यक Aspose.Email क्लासेस को इम्पोर्ट करके शुरू करें:

```java
import com.aspose.email.EWSClient;
import com.aspose.email.IEWSClient;
```

#### EWSClient इंस्टेंस इनिशियलाइज़ करें
प्रत्येक मेलबॉक्स जिसके आप प्रबंधन करना चाहते हैं, उसके लिए `IEWSClient` ऑब्जेक्ट बनाएं:

```java
IEWSClient client1 = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser1", "pwd", "domain");
IEWSClient client2 = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser2", "pwd", "domain");
```

*व्याख्या:* `getEWSClient` हेल्पर प्रदान किए गए क्रेडेंशियल्स का उपयोग करके Exchange से कनेक्ट होता है, और एक तैयार‑से‑उपयोग क्लाइंट लौटाता है जो वर्तमान उपयोगकर्ता की अनुमतियों का सम्मान करता है।

## फ़ोल्डर से संदेश कैसे हटाएँ?
लक्षित फ़ोल्डर में सभी आइटम प्राप्त करें और प्रत्येक को एक ही पास में स्थायी रूप से हटाएँ। यह विधि प्रत्येक संदेश को अलग‑अलग खोलने के ओवरहेड से बचती है। **`listMessages` `MessageInfo` ऑब्जेक्ट्स का संग्रह लौटाता है जिसमें प्रत्येक संदेश का यूनिक URI होता है, जिसे आप फिर `deleteMessage` को पास करके सर्वर से आइटम हटा सकते हैं।**

बैच में प्रोसेस करने से नेटवर्क राउंड‑ट्रिप्स कम होते हैं और बड़े फ़ोल्डर से निपटते समय टाइम‑आउट से बचा जा सकता है। हमेशा सुनिश्चित करें कि आप जिस फ़ोल्डर को लक्षित कर रहे हैं वह सही है, क्योंकि हटाए गए संदेश बैकअप के बिना अपरिवर्तनीय होते हैं।

### संदेशों की सूची और हटाएँ
प्रत्येक संदेश URI पर इटरेट करें और डिलीट ऑपरेशन कॉल करें:

```java
String folder = "Drafts"; // Specify the folder.
ExchangeMessageInfoCollection messages1 = client1.listMessages(folder);
for (ExchangeMessageInfo messageInfo : messages1) {
    client1.deleteItem(messageInfo.getUniqueUri(), DeletionOptions.getDeletePermanently());
}

ExchangeMessageInfoCollection messages2 = client2.listMessages(folder);
for (ExchangeMessageInfo messageInfo : messages2) {
    client2.deleteItem(messageInfo.getUniqueUri(), DeletionOptions.getDeletePermanently());
}
```

*व्याख्या:* `listMessages` `MessageInfo` ऑब्जेक्ट्स का संग्रह लौटाता है; उनके `getUniqueUri()` मानों को `deleteMessage` को पास किया जाता है, जो आइटम को सर्वर से स्थायी रूप से हटाता है।

## फ़ोल्डर में संदेश कैसे जोड़ें?
स्थानीय रूप से एक `MailMessage` ऑब्जेक्ट बनाएं और उसे सीधे मेलबॉक्स फ़ोल्डर में सहेजें—SMTP सर्वर की आवश्यकता नहीं। **`MailMessage` एक ईमेल को हेडर, बॉडी और अटैचमेंट्स के साथ दर्शाता है; इसे पूरी तरह मेमोरी में बनाया जा सकता है इससे पहले कि इसे Exchange में सहेजा जाए।**

ऐपेंड करने से सेंड पाइपलाइन बायपास हो जाती है, जिससे यह ड्राफ्ट, टेम्प्लेट या प्रोग्रामेटिक संदेश निर्माण के लिए आदर्श बन जाता है जहाँ आप चाहते हैं कि संदेश तुरंत उपयोगकर्ता के मेलबॉक्स में दिखाई दे।

### संदेश बनाएं और भेजें
ईमेल बनाएं और इसे Drafts फ़ोल्डर में जोड़ें:

```java
String subj1 = String.format("NETWORKNET_33354 {0} {1}", "User", "User1");
client1.appendMessage(folder, new MailMessage("User1@exchange.conholdate.local", "To@aspsoe.com", subj1, ""));

String subj2 = String.format("NETWORKNET_33354 {0} {1}", "User", "User2");
client2.appendMessage(folder, new MailMessage("User2@exchange.conholdate.local", "To@aspose.com", subj2, ""));
```

*व्याख्या:* `appendMessage` `MailMessage` और एक `FolderInfo` (जैसे Drafts) लेता है और आइटम को मेलबॉक्स में लिखता है, जिससे यह उपयोगकर्ता के लिए तुरंत उपलब्ध हो जाता है।

## EWS में उपयोगकर्ता इम्पर्सोनेशन कैसे करें?
क्लाइंट के सुरक्षा संदर्भ को दूसरे मेलबॉक्स में बदलें, कार्य करें, फिर मूल खाते पर वापस आएँ। यह शेयर्ड मेलबॉक्स प्रशासन के लिए आवश्यक है। **`impersonateUser` अंतर्निहित EWS अनुरोध पर `ImpersonatedUserId` सेट करता है, जिससे सर्वर कॉल को ऐसे मानता है जैसे वह लक्ष्य मेलबॉक्स से आया हो।**

आवश्यक ऑपरेशन्स पूरा करने के बाद, `resetImpersonation` कॉल करके मूल क्रेडेंशियल्स को पुनर्स्थापित करें, जिससे बाद के कॉल सही सुरक्षा संदर्भ में निष्पादित हों।

### उपयोगकर्ता इम्पर्सोनेशन करें
अस्थायी रूप से क्लाइंट का संदर्भ बदलकर दूसरे उपयोगकर्ता के रूप में कार्य करें:

```java
ExchangeMessageInfoCollection messInfoColl1 = client1.listMessages(folder);
client1.impersonateUser(0, "User2@exchange.conholdate.local");

ExchangeMessageInfoCollection messInfoColl2 = client1.listMessages(folder);
// Revert to the original user context.
client1.resetImpersonation();
ExchangeMessageInfoCollection messInfoColl3 = client1.listMessages(folder);
```

*व्याख्या:* `impersonateUser` अंतर्निहित EWS अनुरोध पर `ImpersonatedUserId` सेट करता है, जिससे आप लक्ष्य उपयोगकर्ता की तरह पढ़ या लिख सकते हैं। `resetImpersonation` कॉल करने से मूल क्रेडेंशियल्स पुनर्स्थापित होते हैं।

## व्यावहारिक अनुप्रयोग
Aspose.Email Java का उपयोग करके मजबूत ईमेल ऑटोमेशन समाधान सक्षम होते हैं:
1. **स्वचालित ईमेल सफाई:** एक रात्री कार्य निर्धारित करें जो दर्जनों मेलबॉक्स में पुराने Draft फ़ोल्डर को साफ़ करता है।  
2. **बैच ईमेल वितरण:** एक लूप के साथ प्रत्येक कर्मचारी के इनबॉक्स में टेम्प्लेटेड घोषणा जोड़ें।  
3. **शेयर्ड मेलबॉक्स प्रबंधन:** प्रत्येक उपयोगकर्ता को पूर्ण एक्सेस दिए बिना पुराने संदेशों को आर्काइव करने के लिए विभाग के मेलबॉक्स का इम्पर्सोनेशन करें।

## प्रदर्शन विचार
बड़े मेलबॉक्स को संभालते समय अपने एप्लिकेशन को प्रतिक्रियाशील रखने के लिए:
- **बैच API कॉल्स** जहाँ संभव हो (जैसे, प्रति अनुरोध 500 संदेश हटाएँ)।  
- **संदेशों को स्ट्रीम** करें बजाय पूरी बॉडी को मेमोरी में लोड करने के।  
- **क्लाइंट ऑब्जेक्ट्स को तुरंत डिस्पोज** करें ताकि नेटवर्क सॉकेट्स और HTTP कनेक्शन मुक्त हो सकें।

## सामान्य समस्याएँ और समाधान
- **कनेक्टिविटी त्रुटियाँ:** EWS एंडपॉइंट URL सत्यापित करें, सुनिश्चित करें TLS 1.2 सक्षम है, और फ़ायरवॉल नियम आउटबाउंड HTTPS की अनुमति देते हैं।  
- **इम्पर्सोनेशन पर अनुमति अस्वीकृत:** सर्विस अकाउंट को Exchange में “ApplicationImpersonation” भूमिका असाइन की जानी चाहिए।  
- **बड़े फ़ोल्डर टाइमआउट:** `HttpWebRequest` टाइमआउट बढ़ाएँ या फ़ोल्डर को छोटे हिस्सों में प्रोसेस करें।

## अक्सर पूछे जाने वाले प्रश्न

**Q: EWS के साथ कनेक्टिविटी समस्याओं का समाधान कैसे करें?**  
**A:** एंडपॉइंट URL, क्रेडेंशियल्स और नेटवर्क फ़ायरवॉल की जाँच करें; Aspose.Email में विस्तृत लॉगिंग सक्षम करें ताकि HTTP अनुरोध/प्रतिक्रिया डेटा कैप्चर हो सके।

**Q: क्या Aspose.Email बड़ी मात्रा में ईमेल को कुशलतापूर्वक संभाल सकता है?**  
**A:** हाँ—इसके बैच API आपको प्रति मिनट **10,000+** संदेश प्रोसेस करने देते हैं जबकि मेमोरी उपयोग 200 MB से कम रहता है।

**Q: EWS में उपयोगकर्ता इम्पर्सोनेशन के सामान्य उपयोग केस क्या हैं?**  
**A:** शेयर्ड मेलबॉक्स का प्रबंधन, बैच आर्काइविंग, और कई उपयोगकर्ताओं की ओर से शेड्यूल्ड रिपोर्ट चलाना बिना उनके पासवर्ड संग्रहीत किए।

**Q: क्या Aspose.Email द्वारा API कॉल्स पर कोई सीमा लगाई गई है?**  
**A:** Aspose.Email स्वयं कोई कॉल सीमा नहीं लगाता; हालांकि, Exchange थ्रॉटलिंग नीतियों को लागू कर सकता है जिन्हें आपको मानना होगा।

**Q: मैं अपने Java कोड में क्रेडेंशियल्स को सुरक्षित कैसे रखूँ?**  
**A:** उन्हें एन्क्रिप्टेड कॉन्फ़िगरेशन फ़ाइलों में रखें या Azure Key Vault / AWS Secrets Manager का उपयोग करें, और हमेशा EWS एंडपॉइंट्स के लिए HTTPS उपयोग करें।

---

**अंतिम अपडेट:** 2026-07-08  
**परीक्षित संस्करण:** Aspose.Email for Java 23.10  
**लेखक:** Aspose

## संबंधित ट्यूटोरियल

- [Aspose.Email for Java का उपयोग करके EWSClient इंस्टेंस कैसे बनाएं: Exchange Server इंटीग्रेशन गाइड](/email/java/exchange-server-integration/ewsclient-instance-aspose-email-java/)
- [Aspose.Email for Java और EWS का उपयोग करके Microsoft Exchange Server से कैसे कनेक्ट करें](/email/java/exchange-server-integration/connect-exchange-server-aspose-email-ews-java/)
- [Aspose.Email और Java EWS क्लाइंट के साथ ईमेल प्रबंधन को स्वचालित करें: एक व्यापक गाइड](/email/java/exchange-server-integration/aspose-email-java-ews-client-tutorial/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}