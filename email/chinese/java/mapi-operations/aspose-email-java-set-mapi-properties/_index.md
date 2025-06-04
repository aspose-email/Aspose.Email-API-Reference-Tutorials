---
"date": "2025-05-29"
"description": "学习如何使用 Aspose.Email for Java 高效管理 MAPI 消息中的多个属性。本指南涵盖设置浮点型、双精度型、长整型及其他类型的内容。"
"title": "使用 Aspose.Email 在 Java 中设置多个 MAPI 属性——综合指南"
"url": "/zh/java/mapi-operations/aspose-email-java-set-mapi-properties/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Email 在 Java 中设置多个 MAPI 属性：综合指南

## 介绍

有效管理 MAPI 消息属性对于增强 Java 应用程序至关重要。使用 Aspose.Email for Java，您可以无缝设置多种属性，例如浮点型、双精度型、长整型、短整型、布尔型和自定义属性。本指南将引导您了解实现此目的的各种方法。

**您将学到什么：**
- 使用 Aspose.Email Java 在 MAPI 消息中设置多个属性
- 了解不同的财产类型及其用途
- 实际实施代码示例

让我们先介绍一下先决条件。

## 先决条件

为了继续操作，请确保您已：
- **Java 开发工具包 (JDK)：** 安装了 JDK 8 或更高版本。
- **Aspose.Email库：** 建议使用 25.4 版本。
- **Maven设置：** 您应该在 IDE 中配置 Maven 以进行依赖项管理。

### 所需库

在您的 `pom.xml`：
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### 许可证获取
- **免费试用：** 从免费试用开始探索功能。
- **临时执照：** 不受限制地进行扩展测试。
- **购买：** 如果它适合您的需求，请考虑购买。

## 设置 Aspose.Email for Java

确保 Aspose.Email 在您的开发环境中正确配置：
1. **导入依赖项：** 解决 Maven 依赖关系。
2. **设置许可证：**
   - 从以下位置下载许可证文件 [Aspose](https://purchase。aspose.com/buy).
   - 使用以下方式应用它：
     ```java
     com.aspose.email.License license = new com.aspose.email.License();
     license.setLicense("path/to/your/license.lic");
     ```

设置完成后，让我们探索如何设置各种属性。

## 实施指南

### 设置多个浮动属性

设置浮点属性可以有效地存储数值数据：

#### 概述
此功能演示了如何使用 Aspose.Email for Java 添加多个浮点值作为 MAPI 消息属性。

#### 步骤
1. **创建并初始化消息**
   ```java
   import java.util.ArrayList;
   import com.aspose.email.MapiMessage;
   import com.aspose.email.MapiProperty;
   import com.aspose.email.system.collections.IList;

   MapiMessage msg = new MapiMessage();
   ```
2. **将浮点值添加到列表中**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((float) 1);
   values.addItem((float) 2);
   ```
3. **使用唯一标识符设置属性**
   ```java
   msg.setProperty(new MapiProperty(0x23901004, values));
   ```
*解释：* 属性标签 `0x23901004` 标识此浮点属性集。

### 设置多个双精度属性

Double 属性存储高精度浮点数：

#### 概述
本节介绍如何将多个双精度值存储为 MAPI 消息属性。

#### 步骤
1. **初始化消息**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **填充双精度值**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((double) 1);
   values.addItem((double) 2);
   ```
3. **分配给属性标签**
   ```java
   msg.setProperty(new MapiProperty(0x23901005, values));
   ```

### 设置多个 APPTIME 属性

APPTIME 属性可以有效地存储时间持续时间：

#### 概述
此功能说明使用双精度数字来表示时间。

#### 步骤
1. **创建消息对象**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **添加时间值**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem(30456.34);
   values.addItem(40655.45);
   ```
3. **设置属性**
   ```java
   msg.setProperty(new MapiProperty(0x23901007, values));
   ```

### 设置多个长属性

长属性非常适合大整数：

#### 概述
此功能主要针对在消息中设置多个长整数值。

#### 步骤
1. **初始化 MAPI 消息**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **添加长值**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((long) 30456);
   values.addItem((long) 40655);
   ```
3. **定义属性标签**
   ```java
   msg.setProperty(new MapiProperty(0x23901014, values));
   ```

### 设置多个简短属性

短属性可以高效地存储小整数数据：

#### 概述
本指南演示了如何将短整数设置为消息属性。

#### 步骤
1. **初始化消息**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **添加短值**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((short) 1);
   values.addItem((short) 2);
   ```
3. **分配属性标签**
   ```java
   msg.setProperty(new MapiProperty(0x23901002, values));
   ```

### 设置多个布尔属性

布尔属性存储真/假状态：

#### 概述
了解如何在消息中设置多个布尔值。

#### 步骤
1. **创建消息对象**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **添加布尔值**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem(true);
   values.addItem(false);
   ```
3. **使用标识符设置属性**
   ```java
   msg.setProperty(new MapiProperty(0x2390100b, values));
   ```

### 设置空属性

明确地将属性设置为 null 可能会很有用：

#### 概述
本节演示如何为属性分配空值。

#### 步骤
1. **初始化消息**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **分配空属性**
   ```java
   msg.setProperty(new MapiProperty(0x67400001, new byte[1]));
   ```

### 使用自定义 ID 和 UUID 设置命名长属性

对于复杂的场景，设置命名属性：

#### 概述
此功能演示了如何使用自定义标识符和 UUID 设置长属性。

#### 步骤
1. **初始化消息**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **添加长值**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((int) 4);
   UUID uuid = UUID.randomUUID();
   ```
3. **创建和映射属性**
   ```java
   MapiProperty property = new MapiProperty(msg.getNamedPropertyMapping().getNextAvailablePropertyId(com.aspose.email.MapiPropertyType.PT_MV_LONG), values);
   msg.getNamedPropertyMapping().addNamedPropertyMapping(property, (long) 0x00008028, uuid);
   msg.setProperty(property);
   ```

### 使用名称设置自定义属性

可以命名自定义属性以便于识别：

#### 概述
本指南展示了如何设置自定义命名的属性。

#### 步骤
1. **初始化消息对象**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **定义自定义属性**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem("Custom Value");
   UUID uuid = UUID.randomUUID();
   
   MapiProperty property = new MapiProperty(msg.getNamedPropertyMapping().getNextAvailablePropertyId(com.aspose.email.MapiPropertyType.PT_STRING), values);
   msg.getNamedPropertyMapping().addNamedPropertyMapping(property, "CustomName", uuid);
   ```

### 设置和验证属性

确保正确设置属性至关重要：

#### 概述
本节介绍如何设置和验证 MAPI 消息中的多个属性。

#### 步骤
1. **设置属性**
   按照前面的示例来设置属性。
2. **验证属性**
   ```java
   if (msg.getProperties().containsKey(0x23901004)) {
       System.out.println("Property is set correctly.");
   } else {
       System.err.println("Property setting failed.");
   }
   ```

## 结论

本指南提供了使用 Aspose.Email for Java 管理 MAPI 消息中多种属性的全面方法。按照以下步骤，您可以高效地在应用程序中存储和管理各种数据类型。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}