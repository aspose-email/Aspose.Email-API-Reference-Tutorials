---
"date": "2025-05-29"
"description": "जावा के लिए Aspose.Email का उपयोग करके ईमेल और अनुलग्नकों से नामित MAPI गुणों को कुशलतापूर्वक निकालने का तरीका जानें। यह चरण-दर-चरण मार्गदर्शिका सेटअप, कोड उदाहरण और व्यावहारिक अनुप्रयोगों को कवर करती है।"
"title": "Aspose.Email&#58; के साथ Java में नामित MAPI गुण पढ़ें एक व्यापक गाइड"
"url": "/hi/java/mapi-operations/read-named-mapi-properties-aspose-email-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# जावा में Aspose.Email का उपयोग करके नामित MAPI गुण कैसे पढ़ें

## परिचय

ईमेल या अनुलग्नकों से विशिष्ट नामित गुण निकालना जटिल हो सकता है, खासकर Microsoft Outlook के MAPI प्रारूप के साथ। यदि आप एक जावा एप्लिकेशन विकसित कर रहे हैं जिसे इस कार्यक्षमता की आवश्यकता है, तो Aspose.Email for Java एक आदर्श समाधान है। यह ट्यूटोरियल आपको नामित MAPI गुणों को प्रभावी ढंग से पढ़ने में मार्गदर्शन करेगा।

**आप क्या सीखेंगे:**
- Java के लिए Aspose.Email को सेट अप और कॉन्फ़िगर करना।
- नामित गुणों को निकालना `MapiMessage` वस्तुएं.
- ईमेल अनुलग्नकों से सीधे गुण प्राप्त करना।
- MAPI गुणधर्मों को पढ़ने के वास्तविक-विश्व अनुप्रयोग।

इससे पहले कि हम आगे बढ़ें, आइए उन पूर्व-आवश्यकताओं पर नजर डालें जिनकी आपको आवश्यकता होगी।

## आवश्यक शर्तें

सुनिश्चित करें कि आपके पास:
- **जावा डेवलपमेंट किट (JDK)**: आपके सिस्टम पर JDK 16 या उच्चतर संस्करण स्थापित है।
- **मावेन**निर्भरता प्रबंधन के लिए मावेन से परिचित होना।
- **Aspose.Email for Java लाइब्रेरी**: हमारे द्वारा निष्पादित किये जाने वाले कार्यों के लिए आवश्यक।

### पर्यावरण सेटअप आवश्यकताएँ
1. अपनी मशीन पर JDK 16+ स्थापित और कॉन्फ़िगर करें।
2. अपने पसंदीदा IDE (जैसे, IntelliJ IDEA, Eclipse) में एक Maven-आधारित प्रोजेक्ट सेट अप करें।

### ज्ञान पूर्वापेक्षाएँ
आपको समझना चाहिए:
- बुनियादी जावा प्रोग्रामिंग अवधारणाएँ.
- मावेन के साथ निर्भरता का प्रबंधन करना।
- ईमेल संदेशों की संरचना.

## Java के लिए Aspose.Email सेट अप करना

Java के लिए Aspose.Email का उपयोग करने के लिए, इसे अपने में निर्भरता के रूप में जोड़ें `pom.xml` Maven का उपयोग करके फ़ाइल:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### लाइसेंस अधिग्रहण
Java के लिए Aspose.Email का उपयोग करने के लिए, आप यह कर सकते हैं:
- **मुफ्त परीक्षण**: कार्यक्षमताओं का परीक्षण करने के लिए परीक्षण संस्करण डाउनलोड करें।
- **अस्थायी लाइसेंस**: इससे प्राप्त [Aspose की वेबसाइट](https://purchase.aspose.com/temporary-license/).
- **खरीदना**: दीर्घकालिक पहुंच के लिए पूर्ण लाइसेंस खरीदें।

### मूल आरंभीकरण
अपना Maven प्रोजेक्ट सेट अप करने और निर्भरता जोड़ने के बाद, Aspose.Email को निम्न प्रकार से आरंभ करें:

```java
import com.aspose.email.License;

public class InitializeAspose {
    public static void main(String[] args) {
        // लाइसेंस लागू करें (यदि उपलब्ध हो)
        License license = new License();
        try {
            license.setLicense("path/to/your/license/file.lic");
        } catch (Exception e) {
            System.out.println("License setup failed: " + e.getMessage());
        }
    }
}
```

## कार्यान्वयन मार्गदर्शिका

### किसी से नामित MAPI गुण पढ़ना `MapiMessage` वस्तु

यह अनुभाग दर्शाता है कि किसी फ़ाइल से सीधे विशिष्ट नामित गुण कैसे निकाले जाएं `MapiMessage`.

#### अवलोकन
हम MSG प्रारूप में संग्रहीत ईमेल से "TEST" और "MYPROP" जैसे नामित गुण पढ़ेंगे।

#### चरण:
##### चरण 1: MSG फ़ाइल लोड करें

```java
import com.aspose.email.MapiMessage;
import com.aspose.email.MapiNamedProperty;

public class ReadNamedMapiPropertiesFeature {
    public static void main(String[] args) {
        String dataDir = "YOUR_DOCUMENT_DIRECTORY/outlook/";
        readNamedMAPIProperty(dataDir);
    }
    
    @SuppressWarnings("unchecked")
    public static void readNamedMAPIProperty(String dataDir) {
        // MSG फ़ाइल लोड करें
        MapiMessage message = MapiMessage.fromFile(dataDir + "message.msg");
        
        // नामित गुण पुनर्प्राप्त करें
        for (MapiNamedProperty mapiNamedProp : (Iterable<MapiNamedProperty>) message.getNamedProperties().getValues()) {
            switch (mapiNamedProp.getNameId()) {
                case "TEST":
                    System.out.println(mapiNamedProp.getNameId() + " equals " + mapiNamedProp.getString());
                    break;
                case "MYPROP":
                    System.out.println(mapiNamedProp.getNameId() + " equals " + mapiNamedProp.getString());
                    break;
            }
        }
    }
}
```

**स्पष्टीकरण:**
- **`fromFile()`**: आपकी निर्दिष्ट निर्देशिका से MSG फ़ाइल लोड करता है।
- **`getNamedProperties().getValues()`**: प्रत्येक नामित संपत्ति पर पुनरावृत्ति करता है, जिससे आपको आवश्यकतानुसार फ़िल्टर और प्रक्रिया करने की अनुमति मिलती है।

### अनुलग्नक से नामित MAPI गुण पढ़ना

यह अनुभाग दर्शाता है कि किसी अनुलग्नक से गुण कैसे निकाले जाएं `MapiMessage`.

#### अवलोकन
हम EML प्रारूप में संग्रहीत ईमेल के प्रथम अनुलग्नक से "CustomAttGuid" जैसे कस्टम गुण प्राप्त करेंगे।

#### चरण:
##### चरण 1: EML फ़ाइल लोड करें और कनवर्ट करें

```java
import com.aspose.email.MailMessage;
import com.aspose.email.MapiAttachment;

public class ReadMapiPropertyFromAttachmentFeature {
    public static void main(String[] args) {
        String dataDir = "YOUR_DOCUMENT_DIRECTORY/outlook/";
        readNamedMapiPropertyFromAttachment(dataDir);
    }
    
    @SuppressWarnings("unchecked")
    public static void readNamedMapiPropertyFromAttachment(String dataDir) {
        // EML फ़ाइल लोड करें और MapiMessage में परिवर्तित करें
        MailMessage mail = MailMessage.load(dataDir + "test.eml");
        MapiMessage mapi = MapiMessage.fromMailMessage(mail);
        
        // प्रथम अनुलग्नक से नामित गुणों तक पहुँचें
        MapiAttachment firstAttachment = mapi.getAttachments().get_Item(0);
        for (MapiNamedProperty namedProperty : (Iterable<MapiNamedProperty>) firstAttachment.getNamedProperties().getValues()) {
            if (namedProperty.getNameId().equalsIgnoreCase("CustomAttGuid")) {
                System.out.println("Equal..");
            }
        }
    }
}
```

**स्पष्टीकरण:**
- **`MailMessage.load()`**: EML फ़ाइल लोड करता है.
- **`fromMailMessage()`**: एक को रूपांतरित करता है `MailMessage` वस्तु को एक `MapiMessage`.
- **अनुलग्नकों तक पहुँचना**: अनुलग्नकों से गुण पुनर्प्राप्त करें `getAttachments().get_Item(0)`.

## व्यावहारिक अनुप्रयोगों

नामित MAPI गुणों को पढ़ने के कई वास्तविक-विश्व अनुप्रयोग हैं:
1. **ईमेल फ़िल्टरिंग और वर्गीकरण**: कस्टम मेटाडेटा के आधार पर ईमेल को स्वचालित रूप से वर्गीकृत करें।
2. **डेटा संग्रहण**: संग्रहण प्रयोजनों के लिए विशिष्ट डेटा निकालें।
3. **CRM सिस्टम के साथ एकीकरण**: ग्राहक संबंध प्रबंधन प्रणालियों के साथ ईमेल मेटाडेटा को सिंक करें।
4. **अनुपालन और लेखा परीक्षा**विनियामक आवश्यकताओं के अनुसार संपत्तियों का निष्कर्षण करके अनुपालन सुनिश्चित करना।

## प्रदर्शन संबंधी विचार

Java में Aspose.Email के साथ काम करते समय, निम्नलिखित पर विचार करें:
- फ़ाइल हैंडलिंग को अनुकूलित करें: फ़ाइलों को कुशलतापूर्वक संसाधित करके I/O संचालन को न्यूनतम करें।
- मेमोरी उपयोग प्रबंधित करें: सिस्टम संसाधनों का उपयोग किए बिना बड़े ईमेल को संभालें।
- उपयोग `try-with-resources` जहां लागू हो, स्वचालित संसाधन प्रबंधन के लिए।

## निष्कर्ष

इस ट्यूटोरियल में, आपने सीखा कि दोनों से नामित MAPI गुणों को कैसे पढ़ा जाए `MapiMessage` जावा के लिए Aspose.Email का उपयोग करके ऑब्जेक्ट और अनुलग्नक। ये तकनीकें आपके अनुप्रयोगों के भीतर कुशल ईमेल डेटा हेरफेर को सक्षम करती हैं।

**अगले कदम:**
- अतिरिक्त संपत्ति प्रकारों के साथ प्रयोग करें और Aspose.Email की पूर्ण क्षमताओं का पता लगाएं।
- इन सुविधाओं को अपने द्वारा विकसित की जा रही बड़ी परियोजनाओं या प्रणालियों में एकीकृत करने पर विचार करें।

क्यों न इसे आज़माया जाए? इस समाधान को लागू करने से आप जावा में ईमेल डेटा को प्रबंधित करने और उसका उपयोग करने के तरीके को काफ़ी हद तक बेहतर बना सकते हैं!

## अक्सर पूछे जाने वाले प्रश्न अनुभाग

1. **मैं Aspose.Email के साथ बड़े ईमेल को कुशलतापूर्वक कैसे संभाल सकता हूँ?**
   - संपूर्ण फ़ाइलों को मेमोरी में लोड किए बिना अनुलग्नकों को संसाधित करने के लिए स्ट्रीमिंग API का उपयोग करें।
2. **क्या मैं एक साथ कई अनुलग्नकों से गुण पढ़ सकता हूँ?**
   - हां, अनुलग्नक संग्रह पर पुनरावृत्ति करें और प्रत्येक आइटम के लिए समान गुण निष्कर्षण तर्क लागू करें।
3. **यदि मेरे एप्लिकेशन को MSG या EML के अलावा अन्य प्रारूपों में ईमेल को संभालने की आवश्यकता हो तो क्या होगा?**
   - Aspose.Email विभिन्न ईमेल प्रारूपों का समर्थन करता है; देखें [Aspose का दस्तावेज़ीकरण](https://docs.aspose.com/email/java/) जानकारी के लिए।

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}