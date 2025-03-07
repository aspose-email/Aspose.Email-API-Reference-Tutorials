---
title: सी# के साथ नियुक्ति सहभागियों के लिए प्रतिभागी स्थिति निर्धारित करना
linktitle: सी# के साथ नियुक्ति सहभागियों के लिए प्रतिभागी स्थिति निर्धारित करना
second_title: Aspose.Email .NET ईमेल प्रोसेसिंग एपीआई
description: जानें कि .NET के लिए C# और Aspose.Email का उपयोग करके अपॉइंटमेंट में उपस्थित लोगों की स्थिति कैसे प्रबंधित करें। स्रोत कोड के साथ चरण-दर-चरण मार्गदर्शिका।
weight: 16
url: /hi/net/email-event-and-calendar-handling/setting-participant-status-for-appointment-attendees-with-csharp/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# सी# के साथ नियुक्ति सहभागियों के लिए प्रतिभागी स्थिति निर्धारित करना


## .NET के लिए Aspose.Email का परिचय

.NET के लिए Aspose.Email एक बहुमुखी लाइब्रेरी है जो डेवलपर्स को उनके .NET अनुप्रयोगों के भीतर ईमेल संदेशों, नियुक्तियों, संपर्कों और बहुत कुछ के साथ काम करने में सक्षम बनाती है। अपने सहज ज्ञान युक्त एपीआई के साथ, डेवलपर्स ईमेल संचार के विभिन्न पहलुओं में आसानी से हेरफेर कर सकते हैं, जिससे यह नियुक्ति-संबंधित कार्यों को संभालने के लिए एक उत्कृष्ट विकल्प बन जाता है।

## आवश्यक शर्तें

इससे पहले कि हम कार्यान्वयन में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:

- विजुअल स्टूडियो (या कोई C# IDE)
- .NET लाइब्रेरी के लिए Aspose.Email
- C# प्रोग्रामिंग की बुनियादी समझ

## अपॉइंटमेंट बनाना

आरंभ करने के लिए, आपको .NET के लिए Aspose.Email का उपयोग करके एक अपॉइंटमेंट इंस्टेंस बनाना होगा। एक अपॉइंटमेंट एक निर्धारित कार्यक्रम का प्रतिनिधित्व करता है, और आप विभिन्न गुण जैसे प्रारंभ समय, समाप्ति समय, स्थान और बहुत कुछ सेट कर सकते हैं।

```csharp
// कथनों का उपयोग करके आवश्यक जोड़ें
using Aspose.Email;
using Aspose.Email.Appointment;

// अपॉइंटमेंट वर्ग का एक उदाहरण बनाएँ
var appointment = new Appointment();

// नियुक्ति गुण सेट करें
appointment.StartTime = DateTime.Now;
appointment.EndTime = appointment.StartTime.AddHours(1);
appointment.Location = "Conference Room 101";
```

## उपस्थित लोगों को जोड़ना

 इसके बाद, आप इसका उपयोग करके उपस्थित लोगों को अपॉइंटमेंट में जोड़ सकते हैं`Attendees` संग्रह। उपस्थित व्यक्ति वे व्यक्ति हैं जो नियुक्ति में भाग लेंगे। आप उनके ईमेल पते और नाम निर्दिष्ट कर सकते हैं.

```csharp
// उपस्थित लोगों को अपॉइंटमेंट में जोड़ें
appointment.Attendees.Add("john@example.com", "John Doe");
appointment.Attendees.Add("jane@example.com", "Jane Smith");
```

## प्रतिभागी स्थिति निर्धारित करना

अब महत्वपूर्ण हिस्सा आता है: उपस्थित लोगों के लिए प्रतिभागी स्थिति निर्धारित करना। प्रतिभागी की स्थिति इंगित करती है कि क्या किसी सहभागी ने नियुक्ति निमंत्रण स्वीकार कर लिया है, अस्वीकार कर दिया है या अस्थायी रूप से स्वीकार कर लिया है। .NET के लिए Aspose.Email चुनने के लिए विभिन्न स्थिति विकल्प प्रदान करता है।

```csharp
// उपस्थित लोगों के लिए प्रतिभागी स्थिति निर्धारित करें
appointment.Attendees[0].ParticipantStatus = AppointmentParticipantStatus.Accepted;
appointment.Attendees[1].ParticipantStatus = AppointmentParticipantStatus.Declined;
```

## संपूर्ण स्रोत कोड

यहां संपूर्ण स्रोत कोड है जो अपॉइंटमेंट बनाने, उपस्थित लोगों को जोड़ने और प्रतिभागी की स्थिति निर्धारित करने की प्रक्रिया को प्रदर्शित करता है:

```csharp
// कथनों का उपयोग करके आवश्यक जोड़ें
using Aspose.Email;
using Aspose.Email.Appointment;

// अपॉइंटमेंट वर्ग का एक उदाहरण बनाएँ
var appointment = new Appointment();

// नियुक्ति गुण सेट करें
appointment.StartTime = DateTime.Now;
appointment.EndTime = appointment.StartTime.AddHours(1);
appointment.Location = "Conference Room 101";

// उपस्थित लोगों को अपॉइंटमेंट में जोड़ें
appointment.Attendees.Add("john@example.com", "John Doe");
appointment.Attendees.Add("jane@example.com", "Jane Smith");

// उपस्थित लोगों के लिए प्रतिभागी स्थिति निर्धारित करें
appointment.Attendees[0].ParticipantStatus = AppointmentParticipantStatus.Accepted;
appointment.Attendees[1].ParticipantStatus = AppointmentParticipantStatus.Declined;
```

## निष्कर्ष

इस गाइड में, हमने .NET के लिए C# और Aspose.Email का उपयोग करके नियुक्ति में उपस्थित लोगों को प्रबंधित करने और प्रतिभागी स्थिति निर्धारित करने की प्रक्रिया का पता लगाया है। लाइब्रेरी की व्यापक विशेषताएं इसे उन डेवलपर्स के लिए एक मूल्यवान उपकरण बनाती हैं जिन्हें ईमेल-संबंधित कार्यों को कुशलतापूर्वक करने की आवश्यकता होती है।

## अक्सर पूछे जाने वाले प्रश्न

### मैं .NET लाइब्रेरी के लिए Aspose.Email कैसे प्राप्त कर सकता हूँ?

 आप वेबसाइट से .NET लाइब्रेरी के लिए Aspose.Email डाउनलोड कर सकते हैं:[.NET के लिए Aspose.Email डाउनलोड करें](https://releases.aspose.com).

### क्या मैं प्रतिभागी स्थिति विकल्पों को अनुकूलित कर सकता हूँ?

 हाँ, आप इसका उपयोग करके अपने आवेदन की आवश्यकताओं के अनुसार प्रतिभागी स्थिति विकल्पों को अनुकूलित कर सकते हैं`AppointmentParticipantStatus` .NET के लिए Aspose.Email द्वारा प्रदान की गई गणना।

### क्या .NET के लिए Aspose.Email अन्य ईमेल-संबंधित कार्यों को संभालने के लिए उपयुक्त है?

बिल्कुल! .NET के लिए Aspose.Email ईमेल, अटैचमेंट, अपॉइंटमेंट और बहुत कुछ के साथ काम करने के लिए सुविधाओं की एक विस्तृत श्रृंखला प्रदान करता है, जो इसे विभिन्न ईमेल-संबंधित कार्यों के लिए एक बहुमुखी विकल्प बनाता है।

### क्या मैं इस कार्यक्षमता को अपने मौजूदा .NET एप्लिकेशन में एकीकृत कर सकता हूँ?

हां, आप .NET लाइब्रेरी के लिए Aspose.Email का संदर्भ लेकर और दिए गए कोड उदाहरणों का पालन करके इस गाइड में चर्चा की गई कार्यक्षमता को अपने मौजूदा .NET अनुप्रयोगों में आसानी से एकीकृत कर सकते हैं।

### मुझे और अधिक दस्तावेज़ और संसाधन कहां मिल सकते हैं?

 अधिक विस्तृत दस्तावेज़ और संसाधनों के लिए, .NET दस्तावेज़ के लिए Aspose.Email देखें:[.NET दस्तावेज़ीकरण के लिए Aspose.Email](https://reference.aspose.com/email/net).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
