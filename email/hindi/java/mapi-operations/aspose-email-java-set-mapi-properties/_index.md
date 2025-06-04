---
"date": "2025-05-29"
"description": "जावा के लिए Aspose.Email का उपयोग करके MAPI संदेशों में कई गुणों को कुशलतापूर्वक प्रबंधित करना सीखें। यह मार्गदर्शिका फ़्लोट, डबल, लॉन्ग और अधिक प्रकार सेट करने को कवर करती है।"
"title": "Aspose.Email&#58; के साथ Java में एकाधिक MAPI गुण सेट करें एक व्यापक गाइड"
"url": "/hi/java/mapi-operations/aspose-email-java-set-mapi-properties/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Email के साथ जावा में एकाधिक MAPI गुण सेट करें: एक व्यापक गाइड

## परिचय

MAPI संदेश गुणों को प्रभावी ढंग से प्रबंधित करना आपके Java अनुप्रयोगों को बेहतर बनाने के लिए महत्वपूर्ण है। Java के लिए Aspose.Email के साथ, आप फ़्लोट, डबल, लॉन्ग, शॉर्ट, बूलियन और कस्टम गुणों जैसे कई गुणों को सहजता से सेट कर सकते हैं। यह मार्गदर्शिका आपको इसे प्राप्त करने के लिए विभिन्न तरीकों से परिचित कराएगी।

**आप क्या सीखेंगे:**
- Aspose.Email Java का उपयोग करके MAPI संदेशों में एकाधिक गुण सेट करना
- विभिन्न प्रकार की सम्पत्तियों और उनके उपयोगों को समझना
- कार्यान्वयन के लिए व्यावहारिक कोड उदाहरण

आइये, पहले आवश्यक शर्तों पर चर्चा करें।

## आवश्यक शर्तें

अनुसरण करने के लिए, सुनिश्चित करें कि आपके पास ये हैं:
- **जावा डेवलपमेंट किट (JDK):** JDK 8 या बाद का संस्करण स्थापित.
- **Aspose.ईमेल लाइब्रेरी:** संस्करण 25.4 अनुशंसित है.
- **मावेन सेटअप:** निर्भरता प्रबंधन के लिए आपके IDE में Maven को कॉन्फ़िगर किया जाना चाहिए।

### आवश्यक पुस्तकालय

Aspose.Email को अपनी ईमेल निर्देशिका में निर्भरता के रूप में शामिल करें। `pom.xml`:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### लाइसेंस अधिग्रहण
- **मुफ्त परीक्षण:** सुविधाओं का पता लगाने के लिए निःशुल्क परीक्षण से शुरुआत करें।
- **अस्थायी लाइसेंस:** बिना किसी सीमा के विस्तारित परीक्षण के लिए प्राप्त करें।
- **खरीदना:** यदि यह आपकी आवश्यकताओं के अनुरूप हो तो इसे खरीदने पर विचार करें।

## Java के लिए Aspose.Email सेट अप करना

सुनिश्चित करें कि Aspose.Email आपके विकास परिवेश में सही ढंग से कॉन्फ़िगर किया गया है:
1. **आयात निर्भरताएँ:** मावेन निर्भरताओं का समाधान करें.
2. **लाइसेंस सेट करें:**
   - लाइसेंस फ़ाइल यहाँ से डाउनलोड करें [असपोज](https://purchase.aspose.com/buy).
   - इसका प्रयोग करें:
     ```java
     com.aspose.email.License license = new com.aspose.email.License();
     license.setLicense("path/to/your/license.lic");
     ```

सेटअप पूरा होने के बाद, आइए जानें कि विभिन्न गुण कैसे सेट करें।

## कार्यान्वयन मार्गदर्शिका

### एकाधिक फ़्लोट गुण सेट करना

फ्लोट गुण सेट करने से संख्यात्मक डेटा का कुशल भंडारण संभव होता है:

#### अवलोकन
यह सुविधा Java के लिए Aspose.Email का उपयोग करके MAPI संदेश गुणों के रूप में एकाधिक फ़्लोट मान जोड़ने का प्रदर्शन करती है।

#### कदम
1. **संदेश बनाएं और आरंभ करें**
   ```java
   import java.util.ArrayList;
   import com.aspose.email.MapiMessage;
   import com.aspose.email.MapiProperty;
   import com.aspose.email.system.collections.IList;

   MapiMessage msg = new MapiMessage();
   ```
2. **सूची में फ़्लोट मान जोड़ें**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((float) 1);
   values.addItem((float) 2);
   ```
3. **प्रॉपर्टी को एक अद्वितीय पहचानकर्ता के साथ सेट करें**
   ```java
   msg.setProperty(new MapiProperty(0x23901004, values));
   ```
*स्पष्टीकरण:* संपत्ति टैग `0x23901004` इस फ़्लोट प्रॉपर्टी सेट की पहचान करता है.

### एकाधिक डबल गुण सेट करना

डबल गुण उच्च परिशुद्धता फ़्लोटिंग-पॉइंट संख्याएँ संग्रहीत करते हैं:

#### अवलोकन
यह अनुभाग MAPI संदेश गुणों के रूप में एकाधिक डबल मानों को संग्रहीत करना दिखाता है।

#### कदम
1. **संदेश आरंभ करें**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **दोहरा मान भरें**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((double) 1);
   values.addItem((double) 2);
   ```
3. **प्रॉपर्टी टैग को असाइन करें**
   ```java
   msg.setProperty(new MapiProperty(0x23901005, values));
   ```

### एकाधिक APPTIME गुण सेट करना

APPTIME गुण समय अवधि को कुशलतापूर्वक संग्रहीत करते हैं:

#### अवलोकन
यह सुविधा समय निरूपण के लिए दोहरे परिशुद्धता वाले अंकों के उपयोग को दर्शाती है।

#### कदम
1. **संदेश ऑब्जेक्ट बनाएँ**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **समय मान जोड़ें**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem(30456.34);
   values.addItem(40655.45);
   ```
3. **संपत्ति सेट करें**
   ```java
   msg.setProperty(new MapiProperty(0x23901007, values));
   ```

### एकाधिक लंबी प्रॉपर्टी सेट करना

लंबे गुण बड़े पूर्णांकों के लिए आदर्श होते हैं:

#### अवलोकन
यह सुविधा किसी संदेश में एकाधिक लंबे पूर्णांक मान सेट करने पर केंद्रित है।

#### कदम
1. **MAPI संदेश आरंभ करें**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **लंबे मान जोड़ें**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((long) 30456);
   values.addItem((long) 40655);
   ```
3. **संपत्ति टैग परिभाषित करें**
   ```java
   msg.setProperty(new MapiProperty(0x23901014, values));
   ```

### एकाधिक लघु गुण सेट करना

लघु गुण छोटे पूर्णांक डेटा को कुशलतापूर्वक संग्रहीत करते हैं:

#### अवलोकन
यह मार्गदर्शिका संदेश गुण के रूप में लघु पूर्णांक सेट करने का प्रदर्शन करती है।

#### कदम
1. **संदेश आरंभ करें**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **लघु मान जोड़ें**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((short) 1);
   values.addItem((short) 2);
   ```
3. **प्रॉपर्टी टैग असाइन करें**
   ```java
   msg.setProperty(new MapiProperty(0x23901002, values));
   ```

### एकाधिक बूलियन गुण सेट करना

बूलियन गुण सत्य/असत्य स्थितियाँ संग्रहीत करते हैं:

#### अवलोकन
संदेश में एकाधिक बूलियन मान सेट करना सीखें।

#### कदम
1. **संदेश ऑब्जेक्ट बनाएँ**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **बूलियन मान जोड़ें**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem(true);
   values.addItem(false);
   ```
3. **पहचानकर्ता के साथ संपत्ति सेट करें**
   ```java
   msg.setProperty(new MapiProperty(0x2390100b, values));
   ```

### नल प्रॉपर्टी सेट करना

किसी गुण को स्पष्ट रूप से शून्य के रूप में सेट करना उपयोगी हो सकता है:

#### अवलोकन
यह अनुभाग किसी संपत्ति को शून्य मान निर्दिष्ट करना प्रदर्शित करता है।

#### कदम
1. **संदेश आरंभ करें**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **शून्य संपत्ति असाइन करें**
   ```java
   msg.setProperty(new MapiProperty(0x67400001, new byte[1]));
   ```

### कस्टम आईडी और UUID के साथ नामित लंबी संपत्ति सेट करना

जटिल परिदृश्यों के लिए, नामित गुण सेट करें:

#### अवलोकन
यह सुविधा एक कस्टम पहचानकर्ता और UUID के साथ एक लंबी संपत्ति सेट करना प्रदर्शित करती है।

#### कदम
1. **संदेश आरंभ करें**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **लंबे मान जोड़ें**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((int) 4);
   UUID uuid = UUID.randomUUID();
   ```
3. **संपत्ति बनाएं और मैप करें**
   ```java
   MapiProperty property = new MapiProperty(msg.getNamedPropertyMapping().getNextAvailablePropertyId(com.aspose.email.MapiPropertyType.PT_MV_LONG), values);
   msg.getNamedPropertyMapping().addNamedPropertyMapping(property, (long) 0x00008028, uuid);
   msg.setProperty(property);
   ```

### नाम के साथ कस्टम प्रॉपर्टी सेट करना

आसान पहचान के लिए कस्टम गुणों को नाम दिया जा सकता है:

#### अवलोकन
यह मार्गदर्शिका कस्टम-नामित गुण सेट करना दिखाती है.

#### कदम
1. **संदेश ऑब्जेक्ट आरंभ करें**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **कस्टम प्रॉपर्टी परिभाषित करें**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem("Custom Value");
   UUID uuid = UUID.randomUUID();
   
   MapiProperty property = new MapiProperty(msg.getNamedPropertyMapping().getNextAvailablePropertyId(com.aspose.email.MapiPropertyType.PT_STRING), values);
   msg.getNamedPropertyMapping().addNamedPropertyMapping(property, "CustomName", uuid);
   ```

### गुण सेट करना और मान्य करना

यह सुनिश्चित करना महत्वपूर्ण है कि गुण सही ढंग से सेट किए गए हैं:

#### अवलोकन
यह अनुभाग MAPI संदेशों में एकाधिक गुणों को सेट करने और मान्य करने पर आधारित है।

#### कदम
1. **संपत्ति सेट करें**
   प्रॉपर्टी सेट करने के लिए पिछले उदाहरणों का अनुसरण करें.
2. **संपत्ति मान्य करें**
   ```java
   if (msg.getProperties().containsKey(0x23901004)) {
       System.out.println("Property is set correctly.");
   } else {
       System.err.println("Property setting failed.");
   }
   ```

## निष्कर्ष

इस गाइड में जावा के लिए Aspose.Email का उपयोग करके MAPI संदेशों में कई गुणों को प्रबंधित करने के लिए एक व्यापक दृष्टिकोण प्रदान किया गया है। इन चरणों का पालन करके, आप अपने अनुप्रयोगों के भीतर विभिन्न डेटा प्रकारों को कुशलतापूर्वक संग्रहीत और प्रबंधित कर सकते हैं।

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}