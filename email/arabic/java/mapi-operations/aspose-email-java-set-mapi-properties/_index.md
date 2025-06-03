---
"date": "2025-05-29"
"description": "Learn how to efficiently manage multiple properties in MAPI messages using Aspose.Email for Java. This guide covers setting float, double, long, and more types."
"title": "Set Multiple MAPI Properties in Java with Aspose.Email&#58; A Comprehensive Guide"
"url": "/ar/java/mapi-operations/aspose-email-java-set-mapi-properties/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Set Multiple MAPI Properties in Java with Aspose.Email: A Comprehensive Guide

## مقدمة

Managing MAPI message properties effectively is crucial for enhancing your Java applications. With Aspose.Email for Java, you can set multiple properties such as float, double, long, short, boolean, and custom properties seamlessly. This guide will walk you through various methods to achieve this.

**ما سوف تتعلمه:**
- Setting multiple properties in MAPI messages using Aspose.Email Java
- Understanding different property types and their uses
- Practical code examples for implementation

Let’s start by covering the prerequisites.

## المتطلبات الأساسية

To follow along, ensure you have:
- **Java Development Kit (JDK):** JDK 8 or later installed.
- **مكتبة Aspose.Email:** Version 25.4 is recommended.
- **Maven Setup:** Maven should be configured in your IDE for dependency management.

### المكتبات المطلوبة

Include Aspose.Email as a dependency in your `pom.xml`:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### الحصول على الترخيص
- **نسخة تجريبية مجانية:** ابدأ بإصدار تجريبي مجاني لاستكشاف الميزات.
- **رخصة مؤقتة:** Obtain for extended testing without limitations.
- **شراء:** Consider purchasing if it suits your needs.

## Setting Up Aspose.Email for Java

Ensure Aspose.Email is correctly configured in your development environment:
1. **Import Dependencies:** Resolve Maven dependencies.
2. **Set License:**
   - Download a license file from [أسبوزي](https://purchase.aspose.com/buy).
   - Apply it using:
     ```java
     com.aspose.email.License license = new com.aspose.email.License();
     license.setLicense("path/to/your/license.lic");
     ```

With the setup complete, let’s explore how to set various properties.

## دليل التنفيذ

### Setting Multiple Float Properties

Setting float properties allows efficient storage of numerical data:

#### ملخص
This feature demonstrates adding multiple float values as MAPI message properties using Aspose.Email for Java.

#### خطوات
1. **Create and Initialize the Message**
   ```java
   import java.util.ArrayList;
   import com.aspose.email.MapiMessage;
   import com.aspose.email.MapiProperty;
   import com.aspose.email.system.collections.IList;

   MapiMessage msg = new MapiMessage();
   ```
2. **Add Float Values to a List**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((float) 1);
   values.addItem((float) 2);
   ```
3. **Set the Property with a Unique Identifier**
   ```java
   msg.setProperty(new MapiProperty(0x23901004, values));
   ```
*توضيح:* The property tag `0x23901004` identifies this float property set.

### Setting Multiple Double Properties

Double properties store high-precision floating-point numbers:

#### ملخص
This section shows storing multiple double values as MAPI message properties.

#### خطوات
1. **Initialize the Message**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Populate Double Values**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((double) 1);
   values.addItem((double) 2);
   ```
3. **Assign to Property Tag**
   ```java
   msg.setProperty(new MapiProperty(0x23901005, values));
   ```

### Setting Multiple APPTIME Properties

APPTIME properties store time durations efficiently:

#### ملخص
This feature illustrates using double-precision numbers for time representations.

#### خطوات
1. **Create Message Object**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Add Time Values**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem(30456.34);
   values.addItem(40655.45);
   ```
3. **Set the Property**
   ```java
   msg.setProperty(new MapiProperty(0x23901007, values));
   ```

### Setting Multiple Long Properties

Long properties are ideal for large integers:

#### ملخص
This feature focuses on setting multiple long integer values in a message.

#### خطوات
1. **Initialize MAPI Message**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Add Long Values**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((long) 30456);
   values.addItem((long) 40655);
   ```
3. **Define Property Tag**
   ```java
   msg.setProperty(new MapiProperty(0x23901014, values));
   ```

### Setting Multiple Short Properties

Short properties store small integer data efficiently:

#### ملخص
This guide demonstrates setting short integers as message properties.

#### خطوات
1. **Initialize the Message**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Add Short Values**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((short) 1);
   values.addItem((short) 2);
   ```
3. **Assign Property Tag**
   ```java
   msg.setProperty(new MapiProperty(0x23901002, values));
   ```

### Setting Multiple Boolean Properties

Boolean properties store true/false states:

#### ملخص
Learn how to set multiple boolean values in a message.

#### خطوات
1. **Create Message Object**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Add Boolean Values**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem(true);
   values.addItem(false);
   ```
3. **Set Property with Identifier**
   ```java
   msg.setProperty(new MapiProperty(0x2390100b, values));
   ```

### Setting a Null Property

Explicitly setting a property as null can be useful:

#### ملخص
This section demonstrates assigning a null value to a property.

#### خطوات
1. **Initialize the Message**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Assign Null Property**
   ```java
   msg.setProperty(new MapiProperty(0x67400001, new byte[1]));
   ```

### Setting Named Long Property with Custom ID and UUID

For complex scenarios, set named properties:

#### ملخص
This feature demonstrates setting a long property with a custom identifier and UUID.

#### خطوات
1. **Initialize the Message**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Add Long Values**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((int) 4);
   UUID uuid = UUID.randomUUID();
   ```
3. **Create and Map Property**
   ```java
   MapiProperty property = new MapiProperty(msg.getNamedPropertyMapping().getNextAvailablePropertyId(com.aspose.email.MapiPropertyType.PT_MV_LONG), values);
   msg.getNamedPropertyMapping().addNamedPropertyMapping(property, (long) 0x00008028, uuid);
   msg.setProperty(property);
   ```

### Setting Custom Property with Name

Custom properties can be named for easier identification:

#### ملخص
This guide shows setting custom-named properties.

#### خطوات
1. **Initialize Message Object**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Define Custom Property**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem("Custom Value");
   UUID uuid = UUID.randomUUID();
   
   MapiProperty property = new MapiProperty(msg.getNamedPropertyMapping().getNextAvailablePropertyId(com.aspose.email.MapiPropertyType.PT_STRING), values);
   msg.getNamedPropertyMapping().addNamedPropertyMapping(property, "CustomName", uuid);
   ```

### Setting and Validating Properties

Ensuring properties are set correctly is crucial:

#### ملخص
This section covers setting and validating multiple properties in MAPI messages.

#### خطوات
1. **Set Property**
   Follow previous examples to set a property.
2. **Validate Property**
   ```java
   if (msg.getProperties().containsKey(0x23901004)) {
       System.out.println("Property is set correctly.");
   } else {
       System.err.println("Property setting failed.");
   }
   ```

## خاتمة

This guide provided a comprehensive approach to managing multiple properties in MAPI messages using Aspose.Email for Java. By following these steps, you can efficiently store and manage various data types within your applications.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}