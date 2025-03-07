---
title: छवियों के लिए वैकल्पिक पाठ सेट करना - सी# गाइड
linktitle: छवियों के लिए वैकल्पिक पाठ सेट करना - सी# गाइड
second_title: Aspose.Email .NET ईमेल प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Email का उपयोग करके ईमेल में छवियों के लिए वैकल्पिक टेक्स्ट सेट करना सीखें। स्पष्ट वैकल्पिक पाठ के साथ पहुंच सुनिश्चित करें। दस्तावेज़ीकरण और कोड शामिल हैं।
weight: 15
url: /hi/net/email-composition-and-creation/setting-alternative-text-for-images-csharp-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# छवियों के लिए वैकल्पिक पाठ सेट करना - सी# गाइड


यह मार्गदर्शिका आपको .NET के लिए Aspose.Email का उपयोग करके ईमेल में छवियों के लिए वैकल्पिक पाठ सेट करने की प्रक्रिया के बारे में बताएगी। वैकल्पिक पाठ, जिसे "ऑल्ट टेक्स्ट" के रूप में भी जाना जाता है, का उपयोग किसी छवि का पाठ्य विवरण प्रदान करने के लिए किया जाता है, यदि छवि प्रदर्शित नहीं की जा सकती है। .NET के लिए Aspose.Email एक शक्तिशाली लाइब्रेरी है जो आपको विभिन्न प्रारूपों में ईमेल और अटैचमेंट के साथ काम करने की अनुमति देती है। इस गाइड में, हम C# का उपयोग करके ईमेल संदेशों में छवियों के लिए वैकल्पिक टेक्स्ट सेट करने पर ध्यान केंद्रित करेंगे।

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:

1. विज़ुअल स्टूडियो या कोई संगत C# विकास वातावरण स्थापित।
2. .NET लाइब्रेरी के लिए Aspose.Email. आप विजुअल स्टूडियो में NuGet पैकेज मैनेजर का उपयोग कर सकते हैं।

## चरण 1: एक नया प्रोजेक्ट बनाएं

1. विज़ुअल स्टूडियो लॉन्च करें और एक नया C# कंसोल एप्लिकेशन प्रोजेक्ट बनाएं।

## चरण 2: NuGet के माध्यम से Aspose.Email इंस्टॉल करें

1. सॉल्यूशन एक्सप्लोरर में अपने प्रोजेक्ट पर राइट-क्लिक करें और "न्यूगेट पैकेज प्रबंधित करें" चुनें।
2. "Aspose.Email" खोजें और पैकेज का नवीनतम संस्करण स्थापित करें।

## चरण 3: कथनों का उपयोग करके जोड़ें

```csharp

using Aspose.Email.Mime;
```

## चरण 4: ईमेल संदेश को लोड करें और संशोधित करें

1.  का उपयोग करके ईमेल संदेश लोड करें`MailMessage` कक्षा:

```csharp
MailMessage message = new MailMessage();
message.Subject = "Sample Email with Alternative Text";
message.From = new MailAddress("sender@example.com");
message.To.Add("recipient@example.com");
```

3. ईमेल संदेश की HTML सामग्री लोड करें:

```csharp
var htmlView = AlternateView.CreateAlternateViewFromString("<html><body><img src='cid:logo.jpg' alt='Company Logo'></body></html>", null, "text/html");
```

## चरण 5: छवियों में वैकल्पिक पाठ के लिए वैकल्पिक दृश्य जोड़ें

संदेश में वैकल्पिक दृश्य के रूप में छवि में वैकल्पिक पाठ के लिए htmlview जोड़ें। 
```csharp
message.AlternateViews.Add(htmlView);
```

## चरण 6: ईमेल सहेजें और भेजें

1. संशोधित संदेश को किसी फ़ाइल में सहेजें या अपनी इच्छित विधि का उपयोग करके भेजें:

```csharp
message.Save("output.eml", SaveOptions.DefaultEml);
```

## निष्कर्ष

इस गाइड में, आपने सीखा कि .NET के लिए Aspose.Email का उपयोग करके ईमेल संदेशों में छवियों के लिए वैकल्पिक टेक्स्ट कैसे सेट किया जाए। ऊपर बताए गए चरणों का पालन करके, आप यह सुनिश्चित कर सकते हैं कि आपकी ईमेल सामग्री तब भी पहुंच योग्य और जानकारीपूर्ण बनी रहे, जब छवियां प्रदर्शित न की जा सकें।

## सामान्य प्रश्न

## मैं Aspose.Email लाइब्रेरी कैसे डाउनलोड कर सकता हूँ?

आप Aspose.Email लाइब्रेरी को Aspose रिलीज से डाउनलोड कर सकते हैं या इसे विजुअल स्टूडियो में NuGet पैकेज मैनेजर के माध्यम से इंस्टॉल कर सकते हैं।

### मैं किसी ईमेल में लिंक किए गए संसाधनों के रूप में छवियां कैसे जोड़ूं?

किसी ईमेल में छवियों को लिंक किए गए संसाधनों के रूप में जोड़ने के लिए, आप इसका उपयोग कर सकते हैं`LinkedResource` कक्षा। लिंक किए गए संसाधन के लिए एक सामग्री आईडी निर्दिष्ट करें, और फिर HTML बॉडी में इस सामग्री आईडी का संदर्भ लें`cid:` योजना। विस्तृत जानकारी के लिए देखें[लिंक्ड रिसोर्स दस्तावेज़ीकरण](https://reference.aspose.com/email/net/aspose.email/linkedresource/).
### मुझे .NET के लिए Aspose.Email पर अधिक दस्तावेज़ कहां मिल सकते हैं?

 आप .NET के लिए Aspose.Email के साथ काम करने पर अधिक विस्तृत दस्तावेज़, ट्यूटोरियल और उदाहरण पा सकते हैं[एपीआई संदर्भ](https://reference.aspose.com/email/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
