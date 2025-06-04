---
"date": "2025-05-29"
"description": "學習如何使用 Aspose.Email for Java 有效率地建立和管理 MAPI 聯絡人。本指南涵蓋從基本的聯絡人創建到詳細管理（包括添加專業資訊）的所有內容。"
"title": "使用 Aspose.Email 在 Java 中建立 MAPI 聯絡人 — 逐步指南"
"url": "/zh-hant/java/mapi-operations/create-mapi-contacts-aspose-email-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何使用 Aspose.Email 在 Java 中建立 MAPI 聯絡人：逐步指南

## 介紹

對於需要強大的電子郵件和通訊錄整合功能的應用程式來說，管理聯絡人至關重要。本指南全面示範如何使用 Java 中強大的 Aspose.Email 程式庫建立 MAPI（訊息應用程式介面）聯絡人。透過學習本教程，您將能夠自動建立聯絡人，增強資料組織，並將聯絡人管理無縫整合到您的 Java 應用程式中。

**您將學到什麼：**
- 建立基本且詳細的 MAPI 聯絡人
- 使用 Aspose.Email for Java 管理專業資訊、地址和電子郵件
- 設定個人儲存表 (PST) 檔案以有效率地儲存聯絡人

## 先決條件

在開始建立聯絡人之前，請確保您已具備以下條件：

### 所需庫：
- Aspose.Email for Java 函式庫（版本 25.4 或更高版本）

### 環境設定要求：
- JDK 版本 16 或更高版本
- 您選擇的 IDE（IntelliJ IDEA、Eclipse 等）

### 知識前提：
對 Java 程式設計有基本的了解，並熟悉處理第三方函式庫。

## 設定 Aspose.Email for Java

首先，將 Aspose.Email 庫新增到您的專案中。如果您使用 Maven，請將以下依賴項新增至您的 `pom.xml`：

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### 許可證取得步驟：
- **免費試用：** 從下載試用版 [Aspose 網站](https://releases.aspose.com/email/java/) 探索其特點。
- **臨時執照：** 透過以下方式申請臨時許可證 [購買頁面](https://purchase。aspose.com/temporary-license/).
- **購買：** 考慮從他們那裡購買完整許可證 [購買頁面](https://purchase.aspose.com/buy) 如果 Aspose.Email 滿足您的需求。

### 基本初始化：
安裝後，在 Java 應用程式中初始化 Aspose.Email 以開始建立和管理 MAPI 聯絡人。

## 實施指南

我們將介紹三個主要功能：基本聯絡人創建、專業資訊包含和全面的細節管理。

### 建立基本 MAPI 聯絡人

#### 概述
此功能可讓您僅使用名字、姓氏和電子郵件地址建立簡單的聯絡人，適用於需要最少資料的應用程式。

#### 實施步驟

##### 步驟 1：導入所需的類
```java
import com.aspose.email.MapiContact;
```

##### 步驟 2：建立 MAPI 聯絡人
建立基本 MAPI 聯絡人的方法如下：
```java
public static MapiContact createBasicMapiContact(String firstName, String lastName, String emailAddress) {
    return new MapiContact(firstName + " " + lastName, emailAddress);
}
```
**解釋：** 此方法初始化一個 `MapiContact` 使用提供的姓名和電子郵件地址的物件。聯絡人僅儲存最少的資訊。

### 建立包含專業資訊的 MAPI 聯絡人

#### 概述
透過新增公司名稱、職位和電話號碼等專業詳細資訊來增強您的聯絡人。

#### 實施步驟

##### 步驟 1：導入其他類別
```java
import com.aspose.email.MapiContactNamePropertySet;
import com.aspose.email.MapiContactProfessionalPropertySet;
import com.aspose.email.MapiContactTelephonePropertySet;
```

##### 步驟 2：建立包含專業詳細資訊的 MAPI 聯絡人
新增專業資訊的方法如下：
```java
public static MapiContact createProfessionalMapiContact(String firstName, String middleName, String lastName,
        String company, String jobTitle, String businessPhone, String mobilePhone) {
    MapiContact contact = new MapiContact();
    contact.setNameInfo(new MapiContactNamePropertySet(firstName, middleName, lastName));
    contact.setProfessionalInfo(new MapiContactProfessionalPropertySet(company, jobTitle));
    contact.getTelephones().setBusinessTelephoneNumber(businessPhone);
    contact.getTelephones().setMobileTelephoneNumber(mobilePhone);
    return contact;
}
```
**解釋：** 此方法初始化一個 `MapiContact` 對象包含擴展的詳細信息，包括公司名稱和職位。它還設定了與業務相關的電話號碼。

### 建立包含詳細資訊的 MAPI 聯絡人

#### 概述
透過新增實體地址、電子郵件資訊和性別屬性來建立全面的聯絡人，以便進行詳細管理。

#### 實施步驟

##### 步驟 1：導入其他類別
```java
import com.aspose.email.MapiContactNamePropertySet;
import com.aspose.email.MapiContactProfessionalPropertySet;
import com.aspose.email.MapiContactTelephonePropertySet;
import com.aspose.email.MapiContactElectronicAddress;
import com.aspose.email.MapiContactGender;
```

##### 步驟 2：建立詳細的 MAPI 聯絡人
建立詳細聯絡人的方法如下：
```java
public static MapiContact createDetailedMapiContact(String firstName, String middleName, String lastName,
        MapiContactGender gender, String company, String jobTitle, String email, String workAddress) {
    MapiContact contact = new MapiContact();
    contact.setNameInfo(new MapiContactNamePropertySet(firstName, middleName, lastName));
    contact.getPersonalInfo().setGender(gender);
    contact.setProfessionalInfo(new MapiContactProfessionalPropertySet(company, jobTitle));
    contact.getPhysicalAddresses().getWorkAddress().setAddress(workAddress);
    contact.getElectronicAddresses().setEmail1(new MapiContactElectronicAddress(email));
    return contact;
}
```
**解釋：** 此方法初始化一個 `MapiContact` 提供詳細信息，包括性別和實際地址。它確保捕獲所有相關數據。

### 建立 PST 檔案並新增聯絡人

#### 概述
將多個聯絡人儲存在個人儲存表 (PST) 檔案中，以便集中管理。

#### 實施步驟

##### 步驟 1：導入所需的類
```java
import com.aspose.email.FileFormatVersion;
import com.aspose.email.FolderInfo;
import com.aspose.email.MapiContact;
import com.aspose.email.PersonalStorage;
import com.aspose.email.StandardIpmFolder;
```

##### 步驟 2：建立 PST 並新增聯絡人
以下是建立 PST 檔案和新增聯絡人的方法：
```java
public static void createPstAndAddContacts(MapiContact[] contacts) {
    String pstPath = "YOUR_OUTPUT_DIRECTORY/MapiContactToPST_out.pst";
    PersonalStorage pst = PersonalStorage.create(pstPath, FileFormatVersion.Unicode);
    FolderInfo contactFolder = pst.createPredefinedFolder("Contacts", StandardIpmFolder.Contacts);
    for (MapiContact contact : contacts) {
        contactFolder.addMapiMessageItem(contact);
    }
}
```
**解釋：** 此方法會建立一個 PST 檔案並新增多個 `MapiContact` 對象，並將它們組織在「聯絡人」資料夾下。

## 實際應用

1. **CRM系統：** 在客戶關係管理軟體中自動建立聯絡人。
2. **電子郵件用戶端：** 透過整合強大的聯絡人管理功能來增強電子郵件用戶端。
3. **地址簿同步：** 使用此功能可跨不同平台和裝置同步聯絡人。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}