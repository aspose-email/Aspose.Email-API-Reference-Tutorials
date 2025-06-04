---
"description": ".NET के लिए Aspose.Email का उपयोग करके ईमेल में छवियों के लिए वैकल्पिक टेक्स्ट सेट करना सीखें। स्पष्ट alt टेक्स्ट के साथ पहुँच सुनिश्चित करें। दस्तावेज़ीकरण और कोड शामिल हैं।"
"linktitle": "छवियों के लिए वैकल्पिक पाठ सेट करना - C# गाइड"
"second_title": "Aspose.Email .NET ईमेल प्रोसेसिंग API"
"title": "छवियों के लिए वैकल्पिक पाठ सेट करना - C# गाइड"
"url": "/hi/net/email-composition-and-creation/setting-alternative-text-for-images-csharp-guide/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# छवियों के लिए वैकल्पिक पाठ सेट करना - C# गाइड


यह गाइड आपको .NET के लिए Aspose.Email का उपयोग करके ईमेल में छवियों के लिए वैकल्पिक पाठ सेट करने की प्रक्रिया से परिचित कराएगा। वैकल्पिक पाठ, जिसे "alt text" के रूप में भी जाना जाता है, का उपयोग छवि का पाठ्य विवरण प्रदान करने के लिए किया जाता है, यदि छवि प्रदर्शित नहीं हो पाती है। .NET के लिए Aspose.Email एक शक्तिशाली लाइब्रेरी है जो आपको विभिन्न प्रारूपों में ईमेल और अनुलग्नकों के साथ काम करने की अनुमति देती है। इस गाइड में, हम C# का उपयोग करके ईमेल संदेशों में छवियों के लिए वैकल्पिक पाठ सेट करने पर ध्यान केंद्रित करेंगे।

## आवश्यक शर्तें

आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ हैं:

1. विजुअल स्टूडियो या कोई भी संगत C# विकास वातावरण स्थापित होना चाहिए।
2. .NET लाइब्रेरी के लिए Aspose.Email. आप Visual Studio में NuGet पैकेज मैनेजर का उपयोग कर सकते हैं।

## चरण 1: एक नया प्रोजेक्ट बनाएं

1. विज़ुअल स्टूडियो लॉन्च करें और एक नया C# कंसोल अनुप्रयोग प्रोजेक्ट बनाएं।

## चरण 2: NuGet के माध्यम से Aspose.Email स्थापित करें

1. सॉल्यूशन एक्सप्लोरर में अपने प्रोजेक्ट पर राइट-क्लिक करें और "मैनेज नुगेट पैकेजेस" चुनें।
2. "Aspose.Email" खोजें और पैकेज का नवीनतम संस्करण स्थापित करें।

## चरण 3: कथनों का उपयोग करके जोड़ें

```csharp

using Aspose.Email.Mime;
```

## चरण 4: ईमेल संदेश लोड करें और संशोधित करें

1. ईमेल संदेश को लोड करने के लिए निम्न का उपयोग करें: `MailMessage` कक्षा:

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

## चरण 5: छवियों में वैकल्पिक पाठ के लिए AlternativeView जोड़ें

संदेश में AlternateView के रूप में छवि के लिए वैकल्पिक पाठ हेतु htmlview जोड़ें। 
```csharp
message.AlternateViews.Add(htmlView);
```

## चरण 6: ईमेल सहेजें और भेजें

1. संशोधित संदेश को फ़ाइल में सहेजें या अपनी इच्छित विधि का उपयोग करके भेजें:

```csharp
message.Save("output.eml", SaveOptions.DefaultEml);
```

## निष्कर्ष

इस गाइड में, आपने सीखा कि Aspose.Email for .NET का उपयोग करके ईमेल संदेशों में छवियों के लिए वैकल्पिक पाठ कैसे सेट करें। ऊपर बताए गए चरणों का पालन करके, आप यह सुनिश्चित कर सकते हैं कि आपकी ईमेल सामग्री तब भी सुलभ और जानकारीपूर्ण बनी रहे, जब छवियाँ प्रदर्शित न की जा सकें।

## सामान्य प्रश्न

## मैं Aspose.Email लाइब्रेरी कैसे डाउनलोड कर सकता हूं?

आप Aspose.Email लाइब्रेरी को Aspose Releases से डाउनलोड कर सकते हैं या इसे Visual Studio में NuGet Package Manager के माध्यम से इंस्टॉल कर सकते हैं।

### मैं ईमेल में लिंक किए गए संसाधनों के रूप में छवियाँ कैसे जोड़ूँ?

ईमेल में लिंक किए गए संसाधनों के रूप में चित्र जोड़ने के लिए, आप इसका उपयोग कर सकते हैं `LinkedResource` क्लास। लिंक किए गए संसाधन को एक सामग्री आईडी असाइन करें, और फिर HTML बॉडी में इस सामग्री आईडी को संदर्भित करें `cid:` योजना। विस्तृत जानकारी के लिए, देखें [लिंक्डरिसोर्स दस्तावेज़ीकरण](https://reference.aspose.com/email/net/aspose.email/linkedresource/).
### मैं .NET के लिए Aspose.Email पर अधिक दस्तावेज़ कहां पा सकता हूं?

आप .NET के लिए Aspose.Email के साथ काम करने पर अधिक विस्तृत दस्तावेज़, ट्यूटोरियल और उदाहरण पा सकते हैं। [एपीआई संदर्भ](https://reference.aspose.com/email/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}