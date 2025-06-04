---
"date": "2025-05-30"
"description": ".NET और EWS के लिए Aspose.Email का उपयोग करके उन्नत ईमेल फ़िल्टरिंग तकनीक सीखें। दिनांक, प्रेषक, प्राप्तकर्ता, सूचनाएँ, आकार और बहुत कुछ के आधार पर ईमेल को कुशलतापूर्वक प्रबंधित करें।"
"title": "एक्सचेंज सर्वर एकीकरण के लिए Aspose.Email .NET के साथ उन्नत EWS ईमेल फ़िल्टरिंग में महारत हासिल करें"
"url": "/hi/net/exchange-server-integration/advanced-ews-email-filtering-aspose-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Email .NET के साथ उन्नत EWS ईमेल फ़िल्टरिंग में महारत हासिल करें

## परिचय
तेज़ गति वाली डिजिटल दुनिया में, कुशल ईमेल प्रबंधन महत्वपूर्ण है। प्रतिदिन आने वाले अनगिनत संदेशों के साथ, उन्हें जल्दी से प्रासंगिक जानकारी खोजने के लिए छांटना उत्पादकता को काफी बढ़ा सकता है। यह ट्यूटोरियल आपको .NET और Exchange Web Services (EWS) के लिए Aspose.Email का उपयोग करके उन्नत फ़िल्टरिंग तकनीकों के बारे में मार्गदर्शन करेगा। आप सीखेंगे कि EWS से कैसे कनेक्ट करें और तिथि, प्रेषक, प्राप्तकर्ता, डिलीवरी सूचनाएँ, आकार और अधिक जैसे मानदंडों के आधार पर ईमेल फ़िल्टर करें।

**आप क्या सीखेंगे:**
- .NET के लिए Aspose.Email का उपयोग करके EWS से कनेक्ट करें।
- ईमेल को दिनांक, प्रेषक, प्राप्तकर्ता और अन्य विशेषताओं के आधार पर फ़िल्टर करें.
- कुशल संदेश फ़िल्टरिंग के लिए पेजिंग समर्थन लागू करें।
- बड़ी मात्रा में ईमेल डेटा को संभालते समय प्रदर्शन को अनुकूलित करें.

आइए कार्यान्वयन विवरण में जाने से पहले पूर्वावश्यकताओं की समीक्षा करें।

## आवश्यक शर्तें
इस ट्यूटोरियल का अनुसरण करने के लिए, सुनिश्चित करें कि आपके पास ये हैं:
- **.NET के लिए Aspose.Email** आपके प्रोजेक्ट में स्थापित लाइब्रेरी। यह ट्यूटोरियल संस्करण 22.x और उससे ऊपर के संस्करणों को लक्षित करता है।
- C# प्रोग्रामिंग की बुनियादी समझ.
- EWS सक्षम Exchange सर्वर तक पहुंच (उदाहरणार्थ, Microsoft Outlook).
- विजुअल स्टूडियो या कोई भी संगत IDE.

कार्यान्वयन अनुभाग पर आगे बढ़ने से पहले सुनिश्चित करें कि ये उपकरण स्थापित हैं।

## .NET के लिए Aspose.Email सेट अप करना
सबसे पहले, निम्न विधियों में से किसी एक का उपयोग करके अपने प्रोजेक्ट में Aspose.Email स्थापित करें:

**.नेट सीएलआई:**
```bash
dotnet add package Aspose.Email
```

**पैकेज प्रबंधक कंसोल:**
```powershell
Install-Package Aspose.Email
```

**NuGet पैकेज मैनेजर UI:**
"Aspose.Email" खोजें और नवीनतम संस्करण स्थापित करें।

### लाइसेंस अधिग्रहण
आप तीन तरीकों से लाइसेंस प्राप्त कर सकते हैं:
- **मुफ्त परीक्षण:** संपूर्ण सुविधाओं का मूल्यांकन करने के लिए अस्थायी लाइसेंस डाउनलोड करें.
- **अस्थायी लाइसेंस:** Aspose से निःशुल्क 30-दिन का अस्थायी लाइसेंस का अनुरोध करें।
- **खरीदना:** यदि आपको यह उपकरण दीर्घकालिक परियोजनाओं के लिए उपयोगी लगे तो सदस्यता खरीदें।

स्थापना और लाइसेंसिंग के बाद, EWS से अपना कनेक्शन आरंभ करने के लिए आगे बढ़ें।

## कार्यान्वयन मार्गदर्शिका

### विशेषता: EWS से कनेक्ट करें
**अवलोकन:** .NET के लिए Aspose.Email का उपयोग करके Exchange Web Services (EWS) से कनेक्शन स्थापित करें।

#### चरण 1: कनेक्शन आरंभ करें
```csharp
using Aspose.Email.Clients.Exchange.WebService;
using System;

const string mailboxUri = "https://आउटलुक.ऑफिस365.com/ews/एक्सचेंज.asmx";
const string username = "username";
const string password = "password";
const string domain = "domain";                        

try
{
    IEWSClient client = EWSClient.GetEWSClient(mailboxUri, username, password, domain);
}
catch (Exception ex)
{
    Console.WriteLine(ex.Message);
}
```
**स्पष्टीकरण:** यह कोड प्रदान किए गए क्रेडेंशियल का उपयोग करके Exchange सर्वर से कनेक्ट होता है। प्लेसहोल्डर्स को अपने वास्तविक मेलबॉक्स URI और प्रमाणीकरण विवरण से बदलें।

### सुविधा: तिथि के अनुसार ईमेल फ़िल्टर करें
**अवलोकन:** आज और पिछले 7 दिनों में प्राप्त ईमेल को फ़िल्टर करने का तरीका जानें.

#### चरण 1: आज के ईमेल पुनः प्राप्त करें
```csharp
using Aspose.Email.Tools.Search;
using System;

try
{
    IEWSClient client = EWSClient.GetEWSClient(mailboxUri, username, password, domain);
    
    MailQueryBuilder builder = new MailQueryBuilder();
    builder.InternalDate.On(DateTime.Now);
    
    MailQuery query = builder.GetQuery();
    var messagesToday = client.ListMessages(client.MailboxInfo.InboxUri, query);
}
catch (Exception ex)
{
    Console.WriteLine(ex.Message);
}
```

#### चरण 2: पिछले 7 दिनों के ईमेल पुनर्प्राप्त करें
```csharp
try
{
    IEWSClient client = EWSClient.GetEWSClient(mailboxUri, username, password, domain);
    
    MailQueryBuilder builder = new MailQueryBuilder();
    builder.InternalDate.Before(DateTime.Now);
    builder.InternalDate.Since(DateTime.Now.AddDays(-7));
    
    MailQuery query = builder.GetQuery();
    var messagesLastWeek = client.ListMessages(client.MailboxInfo.InboxUri, query);
}
catch (Exception ex)
{
    Console.WriteLine(ex.Message);
}
```
**स्पष्टीकरण:** उपयोग `MailQueryBuilder` ईमेल तिथियों के आधार पर क्वेरीज़ बनाने के लिए। यह आज या किसी विशिष्ट समय सीमा के भीतर प्राप्त ईमेल को फ़िल्टर करने में सक्षम बनाता है।

### सुविधा: प्रेषक या डोमेन के आधार पर ईमेल फ़िल्टर करें
**अवलोकन:** यह सुविधा दर्शाती है कि किसी विशिष्ट प्रेषक और डोमेन से ईमेल को कैसे फ़िल्टर किया जाए।

#### चरण 1: विशिष्ट प्रेषक से ईमेल प्राप्त करें
```csharp
try
{
    IEWSClient client = EWSClient.GetEWSClient(mailboxUri, username, password, domain);
    
    MailQueryBuilder builderSender = new MailQueryBuilder();
    builderSender.From.Contains("saqib.razzaq@127.0.0.1");
    
    MailQuery querySender = builderSender.GetQuery();
    var senderMessages = client.ListMessages(client.MailboxInfo.InboxUri, querySender);
}
catch (Exception ex)
{
    Console.WriteLine(ex.Message);
}
```

#### चरण 2: विशिष्ट डोमेन से ईमेल पुनर्प्राप्त करें
```csharp
try
{
    IEWSClient client = EWSClient.GetEWSClient(mailboxUri, username, password, domain);
    
    MailQueryBuilder builderDomain = new MailQueryBuilder();
    builderDomain.From.Contains("SpecificHost.com");
    
    MailQuery queryDomain = builderDomain.GetQuery();
    var domainMessages = client.ListMessages(client.MailboxInfo.InboxUri, queryDomain);
}
catch (Exception ex)
{
    Console.WriteLine(ex.Message);
}
```
**स्पष्टीकरण:** उपयोग `MailQueryBuilder` प्रेषक के ईमेल पते या डोमेन के आधार पर ईमेल फ़िल्टर करने के लिए। यह विशिष्ट स्रोतों से महत्वपूर्ण संचार की पहचान करने में मदद करता है।

### सुविधा: प्राप्तकर्ता या संदेश आईडी के आधार पर ईमेल फ़िल्टर करें
**अवलोकन:** किसी विशिष्ट प्राप्तकर्ता को और किसी विशिष्ट MessageId के साथ भेजे गए ईमेल को फ़िल्टर करने का तरीका जानें।

#### चरण 1: विशिष्ट प्राप्तकर्ता को भेजे गए ईमेल पुनः प्राप्त करें
```csharp
try
{
    IEWSClient client = EWSClient.GetEWSClient(mailboxUri, username, password, domain);
    
    MailQueryBuilder builderRecipient = new MailQueryBuilder();
    builderRecipient.To.Contains("recipient@example.com");
    
    MailQuery queryRecipient = builderRecipient.GetQuery();
    var recipientMessages = client.ListMessages(client.MailboxInfo.InboxUri, queryRecipient);
}
catch (Exception ex)
{
    Console.WriteLine(ex.Message);
}
```

#### चरण 2: विशिष्ट संदेशआईडी द्वारा ईमेल पुनर्प्राप्त करें
```csharp
try
{
    IEWSClient client = EWSClient.GetEWSClient(mailboxUri, username, password, domain);
    
    ExchangeQueryBuilder builderMessageId = new ExchangeQueryBuilder();
    builderMessageId.MessageId.Equals("Specific-Message-ID");
    
    MailQuery queryMessageId = builderMessageId.GetQuery();
    var messageIdMessages = client.ListMessages(client.MailboxInfo.InboxUri, queryMessageId);
}
catch (Exception ex)
{
    Console.WriteLine(ex.Message);
}
```
**स्पष्टीकरण:** प्राप्तकर्ता या संदेश आईडी के आधार पर फ़िल्टर करने से इच्छित प्राप्तकर्ता या विशिष्ट पहचानकर्ता के आधार पर रुचिकर ईमेल पर ध्यान केंद्रित करने में मदद मिलती है।

### सुविधा: डिलीवरी नोटिफिकेशन और आकार के अनुसार ईमेल फ़िल्टर करें
**अवलोकन:** यह सुविधा डिलीवरी नोटिफिकेशन और संदेश के आकार के आधार पर ईमेल फ़िल्टर करने का प्रदर्शन करती है।

#### चरण 1: मेल डिलीवरी सूचनाएँ प्राप्त करें
```csharp
try
{
    IEWSClient client = EWSClient.GetEWSClient(mailboxUri, username, password, domain);
    
    ExchangeQueryBuilder builderMDN = new ExchangeQueryBuilder();
    builderMDN.ContentClass.Equals(ContentClassType.MDN.ToString());
    
    MailQuery queryMDN = builderMDN.GetQuery();
    var mdnMessages = client.ListMessages(client.MailboxInfo.InboxUri, queryMDN);
}
catch (Exception ex)
{
    Console.WriteLine(ex.Message);
}
```

#### चरण 2: आकार के अनुसार संदेश फ़िल्टर करें
```csharp
try
{
    IEWSClient client = EWSClient.GetEWSClient(mailboxUri, username, password, domain);
    
    ExchangeQueryBuilder builderSize = new ExchangeQueryBuilder();
    builderSize.ItemSize.Greater(80000); // बाइट्स में उदाहरण आकार
    
    MailQuery querySize = builderSize.GetQuery();
    var sizeMessages = client.ListMessages(client.MailboxInfo.InboxUri, querySize);
}
catch (Exception ex)
{
    Console.WriteLine(ex.Message);
}
```
**स्पष्टीकरण:** डिलीवरी स्थिति और आकार के आधार पर ईमेल को प्रभावी ढंग से प्रबंधित करने के लिए इन फ़िल्टर का उपयोग करें।

## निष्कर्ष
इस ट्यूटोरियल में EWS के साथ .NET के लिए Aspose.Email का उपयोग करके उन्नत ईमेल फ़िल्टरिंग तकनीकों को शामिल किया गया है। इन कौशलों में महारत हासिल करके, आप अपने इनबॉक्स को कुशलतापूर्वक प्रबंधित कर सकते हैं, जिससे बड़ी मात्रा में ईमेल को संभालने में उत्पादकता में सुधार होगा।

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}