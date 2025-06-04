---
"date": "2025-05-29"
"description": "學習如何使用 Aspose.Email for Java 高效管理 MAPI 訊息中的多個屬性。本指南涵蓋設定浮點型、雙精確型、長整型及其他類型的內容。"
"title": "使用 Aspose.Email 在 Java 中設定多個 MAPI 屬性－綜合指南"
"url": "/zh-hant/java/mapi-operations/aspose-email-java-set-mapi-properties/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Email 在 Java 中設定多個 MAPI 屬性：綜合指南

## 介紹

有效管理 MAPI 訊息屬性對於增強 Java 應用程式至關重要。使用 Aspose.Email for Java，您可以無縫設定多種屬性，例如浮點型、雙精確型、長整型、短整型、布林型和自訂屬性。本指南將引導您了解實現此目的的各種方法。

**您將學到什麼：**
- 使用 Aspose.Email Java 在 MAPI 訊息中設定多個屬性
- 了解不同的財產類型及其用途
- 實際實施程式碼範例

讓我們先介紹一下先決條件。

## 先決條件

為了繼續操作，請確保您已：
- **Java 開發工具包 (JDK)：** 安裝了 JDK 8 或更高版本。
- **Aspose.Email庫：** 建議使用 25.4 版本。
- **Maven設定：** 您應該在 IDE 中設定 Maven 以進行依賴項管理。

### 所需庫

在您的 `pom.xml`：
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### 許可證獲取
- **免費試用：** 從免費試用開始探索功能。
- **臨時執照：** 不受限制地進行擴展測試。
- **購買：** 如果它適合您的需求，請考慮購買。

## 設定 Aspose.Email for Java

確保 Aspose.Email 在您的開發環境中正確配置：
1. **導入相依性：** 解決 Maven 依賴關係。
2. **設定許可證：**
   - 從以下位置下載許可證文件 [Aspose](https://purchase。aspose.com/buy).
   - 使用以下方式應用它：
     ```java
     com.aspose.email.License license = new com.aspose.email.License();
     license.setLicense("path/to/your/license.lic");
     ```

設定完成後，讓我們探索如何設定各種屬性。

## 實施指南

### 設定多個浮動屬性

設定浮點屬性可以有效儲存數值資料：

#### 概述
此功能示範如何使用 Aspose.Email for Java 新增多個浮點值作為 MAPI 訊息屬性。

#### 步驟
1. **建立並初始化訊息**
   ```java
   import java.util.ArrayList;
   import com.aspose.email.MapiMessage;
   import com.aspose.email.MapiProperty;
   import com.aspose.email.system.collections.IList;

   MapiMessage msg = new MapiMessage();
   ```
2. **將浮點值加入到清單中**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((float) 1);
   values.addItem((float) 2);
   ```
3. **使用唯一識別碼設定屬性**
   ```java
   msg.setProperty(new MapiProperty(0x23901004, values));
   ```
*解釋：* 屬性標籤 `0x23901004` 標識此浮點屬性集。

### 設定多個雙精度屬性

Double 屬性儲存高精度浮點數：

#### 概述
本節介紹如何將多個雙精確值儲存為 MAPI 訊息屬性。

#### 步驟
1. **初始化訊息**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **填充雙精度值**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((double) 1);
   values.addItem((double) 2);
   ```
3. **分配給屬性標籤**
   ```java
   msg.setProperty(new MapiProperty(0x23901005, values));
   ```

### 設定多個 APPTIME 屬性

APPTIME 屬性可以有效地儲存時間持續時間：

#### 概述
此功能說明使用雙精確度數字來表示時間。

#### 步驟
1. **建立訊息對象**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **新增時間值**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem(30456.34);
   values.addItem(40655.45);
   ```
3. **設定屬性**
   ```java
   msg.setProperty(new MapiProperty(0x23901007, values));
   ```

### 設定多個長屬性

長屬性非常適合大整數：

#### 概述
此功能主要針對在訊息中設定多個長整數值。

#### 步驟
1. **初始化 MAPI 訊息**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **新增長值**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((long) 30456);
   values.addItem((long) 40655);
   ```
3. **定義屬性標籤**
   ```java
   msg.setProperty(new MapiProperty(0x23901014, values));
   ```

### 設定多個簡短屬性

短屬性可以有效率地儲存小整數資料：

#### 概述
本指南示範如何將短整數設定為訊息屬性。

#### 步驟
1. **初始化訊息**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **新增短值**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((short) 1);
   values.addItem((short) 2);
   ```
3. **分配屬性標籤**
   ```java
   msg.setProperty(new MapiProperty(0x23901002, values));
   ```

### 設定多個布林屬性

布林屬性儲存真/假狀態：

#### 概述
了解如何在訊息中設定多個布林值。

#### 步驟
1. **建立訊息對象**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **添加布林值**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem(true);
   values.addItem(false);
   ```
3. **使用標識符設定屬性**
   ```java
   msg.setProperty(new MapiProperty(0x2390100b, values));
   ```

### 設定空屬性

明確地將屬性設為 null 可能會很有用：

#### 概述
本節示範如何為屬性指派空值。

#### 步驟
1. **初始化訊息**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **分配空屬性**
   ```java
   msg.setProperty(new MapiProperty(0x67400001, new byte[1]));
   ```

### 使用自訂 ID 和 UUID 設定命名長屬性

對於複雜的場景，設定命名屬性：

#### 概述
此功能示範如何使用自訂識別碼和 UUID 設定長屬性。

#### 步驟
1. **初始化訊息**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **新增長值**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((int) 4);
   UUID uuid = UUID.randomUUID();
   ```
3. **建立和映射屬性**
   ```java
   MapiProperty property = new MapiProperty(msg.getNamedPropertyMapping().getNextAvailablePropertyId(com.aspose.email.MapiPropertyType.PT_MV_LONG), values);
   msg.getNamedPropertyMapping().addNamedPropertyMapping(property, (long) 0x00008028, uuid);
   msg.setProperty(property);
   ```

### 使用名稱設定自訂屬性

可以命名自訂屬性以便於識別：

#### 概述
本指南展示如何設定自訂命名的屬性。

#### 步驟
1. **初始化訊息對象**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **定義自訂屬性**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem("Custom Value");
   UUID uuid = UUID.randomUUID();
   
   MapiProperty property = new MapiProperty(msg.getNamedPropertyMapping().getNextAvailablePropertyId(com.aspose.email.MapiPropertyType.PT_STRING), values);
   msg.getNamedPropertyMapping().addNamedPropertyMapping(property, "CustomName", uuid);
   ```

### 設定和驗證屬性

確保正確設定屬性至關重要：

#### 概述
本節介紹如何設定和驗證 MAPI 訊息中的多個屬性。

#### 步驟
1. **設定屬性**
   依照前面的範例來設定屬性。
2. **驗證屬性**
   ```java
   if (msg.getProperties().containsKey(0x23901004)) {
       System.out.println("Property is set correctly.");
   } else {
       System.err.println("Property setting failed.");
   }
   ```

## 結論

本指南提供了使用 Aspose.Email for Java 管理 MAPI 訊息中多種屬性的全面方法。按照以下步驟，您可以有效率地在應用程式中儲存和管理各種資料類型。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}