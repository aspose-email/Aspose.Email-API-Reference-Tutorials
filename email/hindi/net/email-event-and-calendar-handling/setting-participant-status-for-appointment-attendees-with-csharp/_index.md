---
"description": ".NET के लिए C# और Aspose.Email का उपयोग करके अपॉइंटमेंट अटेंडीज़ की स्थिति प्रबंधित करना सीखें। स्रोत कोड के साथ चरण-दर-चरण मार्गदर्शिका।"
"linktitle": "C# के साथ अपॉइंटमेंट अटेंडीज़ के लिए प्रतिभागी स्थिति सेट करना"
"second_title": "Aspose.Email .NET ईमेल प्रोसेसिंग API"
"title": "C# के साथ अपॉइंटमेंट अटेंडीज़ के लिए प्रतिभागी स्थिति सेट करना"
"url": "/hi/net/email-event-and-calendar-handling/setting-participant-status-for-appointment-attendees-with-csharp/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# C# के साथ अपॉइंटमेंट अटेंडीज़ के लिए प्रतिभागी स्थिति सेट करना


## .NET के लिए Aspose.Email का परिचय

Aspose.Email for .NET एक बहुमुखी लाइब्रेरी है जो डेवलपर्स को उनके .NET अनुप्रयोगों के भीतर ईमेल संदेशों, अपॉइंटमेंट्स, संपर्कों और बहुत कुछ के साथ काम करने में सक्षम बनाती है। इसके सहज API के साथ, डेवलपर्स ईमेल संचार के विभिन्न पहलुओं को आसानी से नियंत्रित कर सकते हैं, जिससे यह अपॉइंटमेंट-संबंधी कार्यों को संभालने के लिए एक उत्कृष्ट विकल्प बन जाता है।

## आवश्यक शर्तें

इससे पहले कि हम कार्यान्वयन में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:

- विजुअल स्टूडियो (या कोई भी C# IDE)
- .NET लाइब्रेरी के लिए Aspose.Email
- C# प्रोग्रामिंग की बुनियादी समझ

## अपॉइंटमेंट बनाना

आरंभ करने के लिए, आपको .NET के लिए Aspose.Email का उपयोग करके अपॉइंटमेंट इंस्टेंस बनाना होगा। अपॉइंटमेंट एक शेड्यूल किए गए ईवेंट का प्रतिनिधित्व करता है, और आप प्रारंभ समय, समाप्ति समय, स्थान और बहुत कुछ जैसे विभिन्न गुण सेट कर सकते हैं।

```csharp
// आवश्यक उपयोग कथन जोड़ें
using Aspose.Email;
using Aspose.Email.Appointment;

// अपॉइंटमेंट क्लास का एक उदाहरण बनाएँ
var appointment = new Appointment();

// अपॉइंटमेंट गुण सेट करें
appointment.StartTime = DateTime.Now;
appointment.EndTime = appointment.StartTime.AddHours(1);
appointment.Location = "Conference Room 101";
```

## उपस्थित लोगों को जोड़ना

इसके बाद, आप अपॉइंटमेंट में उपस्थित लोगों को जोड़ सकते हैं `Attendees` संग्रह। सहभागी वे व्यक्ति हैं जो नियुक्ति में भाग लेंगे। आप उनके ईमेल पते और नाम निर्दिष्ट कर सकते हैं।

```csharp
// अपॉइंटमेंट में उपस्थित लोगों को जोड़ें
appointment.Attendees.Add("john@example.com", "John Doe");
appointment.Attendees.Add("jane@example.com", "Jane Smith");
```

## प्रतिभागी स्थिति निर्धारित करना

अब महत्वपूर्ण हिस्सा आता है: उपस्थित लोगों के लिए प्रतिभागी स्थिति निर्धारित करना। प्रतिभागी स्थिति यह बताती है कि किसी सहभागी ने नियुक्ति आमंत्रण स्वीकार किया है, अस्वीकार किया है या अस्थायी रूप से स्वीकार किया है। Aspose.Email for .NET चुनने के लिए विभिन्न स्थिति विकल्प प्रदान करता है।

```csharp
// उपस्थित लोगों के लिए प्रतिभागी स्थिति निर्धारित करें
appointment.Attendees[0].ParticipantStatus = AppointmentParticipantStatus.Accepted;
appointment.Attendees[1].ParticipantStatus = AppointmentParticipantStatus.Declined;
```

## संपूर्ण स्रोत कोड

यहां संपूर्ण स्रोत कोड दिया गया है जो अपॉइंटमेंट बनाने, उपस्थित लोगों को जोड़ने और प्रतिभागी की स्थिति निर्धारित करने की प्रक्रिया को प्रदर्शित करता है:

```csharp
// आवश्यक उपयोग कथन जोड़ें
using Aspose.Email;
using Aspose.Email.Appointment;

// अपॉइंटमेंट क्लास का एक उदाहरण बनाएँ
var appointment = new Appointment();

// अपॉइंटमेंट गुण सेट करें
appointment.StartTime = DateTime.Now;
appointment.EndTime = appointment.StartTime.AddHours(1);
appointment.Location = "Conference Room 101";

// अपॉइंटमेंट में उपस्थित लोगों को जोड़ें
appointment.Attendees.Add("john@example.com", "John Doe");
appointment.Attendees.Add("jane@example.com", "Jane Smith");

// उपस्थित लोगों के लिए प्रतिभागी स्थिति निर्धारित करें
appointment.Attendees[0].ParticipantStatus = AppointmentParticipantStatus.Accepted;
appointment.Attendees[1].ParticipantStatus = AppointmentParticipantStatus.Declined;
```

## निष्कर्ष

इस गाइड में, हमने C# और Aspose.Email for .NET का उपयोग करके अपॉइंटमेंट अटेंडीज़ को प्रबंधित करने और प्रतिभागी की स्थिति सेट करने की प्रक्रिया का पता लगाया है। लाइब्रेरी की व्यापक विशेषताएं इसे उन डेवलपर्स के लिए एक मूल्यवान उपकरण बनाती हैं जिन्हें ईमेल-संबंधित कार्यों के साथ कुशलतापूर्वक काम करने की आवश्यकता होती है।

## अक्सर पूछे जाने वाले प्रश्न

### मैं .NET लाइब्रेरी के लिए Aspose.Email कैसे प्राप्त कर सकता हूं?

आप वेबसाइट से .NET लाइब्रेरी के लिए Aspose.Email डाउनलोड कर सकते हैं: [.NET के लिए Aspose.Email डाउनलोड करें](https://releases.aspose.com).

### क्या मैं प्रतिभागी स्थिति विकल्पों को अनुकूलित कर सकता हूँ?

हां, आप अपने आवेदन की जरूरतों के अनुसार प्रतिभागी स्थिति विकल्पों को अनुकूलित कर सकते हैं `AppointmentParticipantStatus` .NET के लिए Aspose.Email द्वारा प्रदान की गई गणना।

### क्या Aspose.Email for .NET अन्य ईमेल-संबंधी कार्यों को संभालने के लिए उपयुक्त है?

बिल्कुल! Aspose.Email for .NET ईमेल, अटैचमेंट, अपॉइंटमेंट और बहुत कुछ के साथ काम करने के लिए कई प्रकार की सुविधाएँ प्रदान करता है, जो इसे विभिन्न ईमेल-संबंधित कार्यों के लिए एक बहुमुखी विकल्प बनाता है।

### क्या मैं इस कार्यक्षमता को अपने मौजूदा .NET अनुप्रयोग में एकीकृत कर सकता हूँ?

हां, आप इस गाइड में चर्चा की गई कार्यक्षमता को आसानी से अपने मौजूदा .NET अनुप्रयोगों में Aspose.Email for .NET लाइब्रेरी का संदर्भ देकर और दिए गए कोड उदाहरणों का पालन करके एकीकृत कर सकते हैं।

### मैं अधिक दस्तावेज और संसाधन कहां पा सकता हूं?

अधिक विस्तृत दस्तावेज़ीकरण और संसाधनों के लिए, .NET दस्तावेज़ीकरण के लिए Aspose.Email देखें: [.NET दस्तावेज़ीकरण के लिए Aspose.Email](https://reference.aspose.com/email/net).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}