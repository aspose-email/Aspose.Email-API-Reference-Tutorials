---
"date": "2025-05-30"
"description": "了解如何使用 Aspose.Email for .NET 建立、填入和儲存 MAPI 聯絡人。本指南涵蓋從設定到進階功能的所有內容。"
"title": "使用 Aspose.Email for .NET™ 開發人員指南建立和管理 MAPI 聯絡人"
"url": "/zh-hant/net/mapi-operations/manage-mapi-contacts-aspose-email-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Email for .NET 建立和管理 MAPI 聯絡人：開發人員指南

## 介紹

您是否希望透過高效管理相容 Microsoft Outlook (MAPI) 的聯絡人來增強您的應用程式？使用 Aspose.Email for .NET，建立和儲存聯絡人資料變得非常簡單。無論您是開發企業解決方案還是需要強大電子郵件管理功能的個人項目，本教學都將指導您使用 Aspose.Email 實現聯絡人的建立和儲存。

在當今的數位時代，以程式設計方式管理聯絡人可以簡化工作流程並節省時間，這對開發人員來說是一項非常寶貴的技能。利用 Aspose.Email for .NET 的強大功能，您將能夠輕鬆處理複雜的聯絡人資料。

**您將學到什麼：**
- 如何使用 Aspose.Email 建立 MAPI 聯絡人
- 高效率填入聯絡方式的技巧
- 以 MSG 和 VCF 等各種格式儲存聯絡人的方法
- 效能提示和整合可能性

在開始實現這些功能之前，讓我們先深入了解先決條件！

## 先決條件

在開始之前，請確保滿足以下要求：

### 所需的庫和依賴項

- **Aspose.Email for .NET**：這個函式庫很重要，因為它提供了管理電子郵件相關任務所需的類別和方法。
  
### 環境設定要求

- 確保與某個版本的 .NET 相容（最好是 .NET Core 3.1 或更高版本）。
- 使用 Visual Studio 或任何支援 C# 開發的 IDE。

### 知識前提

- 對 C# 程式設計有基本的了解。
- 熟悉物件導向程式設計概念。

## 設定 Aspose.Email for .NET

若要使用本文討論的功能，請先在您的專案中設定 Aspose.Email。操作方法如下：

**使用 .NET CLI：**

```bash
dotnet add package Aspose.Email
```

**套件管理器控制台：**

```powershell
Install-Package Aspose.Email
```

**NuGet 套件管理器 UI：**
- 搜尋“Aspose.Email”並安裝最新版本。

### 許可證取得步驟

首先下載 **免費試用** 探索該庫的功能。如需擴充使用，您可能需要購買許可證或申請 **臨時執照** 來自 Aspose。請依照以下步驟操作：

1. 訪問 [Aspose 電子郵件購買](https://purchase.aspose.com/buy) 購買選項。
2. 探索 [免費試用和臨時許可證](https://releases.aspose.com/email/net/) 供試用。

### 基本初始化

要開始使用 Aspose.Email，請透過確保包含必要的命名空間來初始化專案中的函式庫：

```csharp
using Aspose.Email.Mapi;
```

## 實施指南

在本節中，我們將介紹如何使用 Aspose.Email for .NET 建立和儲存 MAPI 聯絡人。

### 功能：建立和填充 MAPI 聯絡人

#### 概述

此功能示範如何建立 `MapiContact` 並填寫必要的聯絡方式，如姓名、職業、地址、電子郵件、電話號碼、類別等。

#### 逐步實施

##### 初始化輸出目錄

首先，定義儲存檔案的位置：

```csharp
string dataDir = "YOUR_OUTPUT_DIRECTORY";
```

##### 建立新的 MapiContact 對象

首先初始化一個新的 `MapiContact` 目的：

```csharp
MapiContact contact = new MapiContact();
```

##### 設定基本訊息

填寫姓名和職業等基本資料：

```csharp
contact.NameInfo = new MapiContactNamePropertySet("Bertha", "A.", "Buell");
contact.ProfessionalInfo = new MapiContactProfessionalPropertySet("Awthentikz", "Social work assistant");
```

##### 新增聯絡資訊

包括其他聯絡資訊，如實際地址、電子郵件和電話號碼：

```csharp
// 工作實際地址
contact.PhysicalAddresses.WorkAddress.Address = "Im Astenfeld 59 8580 EDELSCHROTT";

// 電子郵件
contact.ElectronicAddresses.Email1 = new MapiContactElectronicAddress("Experwas", "SMTP", "BerthaABuell@armyspy.com");

// 電話號碼
contact.Telephones = new MapiContactTelephonePropertySet("06605045265");
```

##### 添加其他詳細信息

您也可以新增其他資訊和使用者定義的欄位：

```csharp
// 其他資訊
contact.Mileage = "Some test mileage";
contact.Billing = "Test billing information";

// 使用者定義字段
contact.OtherFields.Journal = true;
contact.OtherFields.Private = true;
contact.OtherFields.ReminderTime = new DateTime(2014, 1, 1, 0, 0, 55);
contact.OtherFields.UserField1 = "ContactUserField1";
```

##### 載入照片

將圖像載入到聯絡人照片欄位：

```csharp
using (FileStream fs = File.OpenRead("YOUR_DOCUMENT_DIRECTORY/Desert.jpg"))
{
    byte[] buffer = new byte[fs.Length];
    fs.Read(buffer, 0, buffer.Length);
    contact.Photo = new MapiContactPhoto(buffer, MapiContactPhotoImageFormat.Jpeg);
}
```

### 功能：將 MAPI 聯絡人儲存為不同的格式

#### 概述

一旦你填滿了你的 `MapiContact` 物件包含所需資訊後，就可以將其儲存為各種格式，例如 MSG 和 VCF。

#### 逐步實施

##### 以 MSG 格式儲存

```csharp
contact.Save(dataDir + "/MapiContact_out.msg", ContactSaveFormat.Msg);
```

##### 以 VCF 格式儲存

```csharp
contact.Save(dataDir + "/MapiContact_out.vcf", ContactSaveFormat.VCard);
```

## 實際應用

以下是一些可以應用這些功能的實際場景：

1. **CRM系統**：在客戶關係管理系統中自動建立和維護聯絡人記錄。
2. **電子郵件行銷平台**：整合聯絡人資料以進行有針對性的電子郵件活動，增強客戶參與度。
3. **商務溝通工具**：使用 MAPI 聯絡人有效管理專業網路和通訊。

## 性能考慮

在 .NET 應用程式中使用 Aspose.Email 時，請考慮以下事項：

- 盡可能透過串流資料有效地處理大型資料集。
- 透過仔細的物件管理和檔案流等資源的處理來優化記憶體使用。
- 利用非同步程式設計模型來增強應用程式的反應能力。

## 結論

在本教學中，您學習如何使用 Aspose.Email for .NET 建立和管理 MAPI 聯絡人。從設定庫到實現以多種格式儲存聯絡人的功能，我們涵蓋了基本技巧和最佳實踐。 

為了進一步探索，請考慮深入了解 Aspose.Email 提供的更高級的功能，或將這些解決方案與您正在使用的其他系統整合。

## 常見問題部分

1. **什麼是 MAPI？**
   - MAPI（訊息應用程式介面）是一種允許應用程式發送和接收電子郵件以及管理聯絡人的協定。
   
2. **我可以在商業專案中使用 Aspose.Email for .NET 嗎？**
   - 是的，但您需要從 Aspose 獲得許可證。

3. **如何處理大量聯絡人資料？**
   - 使用高效的記憶體管理技術並考慮非同步操作。

4. **是否有可用於解決 Aspose.Email 問題的支援？**
   - 是的，請訪問 [Aspose 支援論壇](https://forum.aspose.com/c/email/10) 尋求幫助。

5. **我可以自訂 MAPI 聯絡人中的使用者定義欄位嗎？**
   - 當然！您可以根據需要添加任何自訂字段，使用 `OtherFields`。

## 資源

- **文件**：查看詳細指南和 API 參考 [Aspose 電子郵件文檔](https://reference。aspose.com/email/net/).
- **下載**：從取得最新版本 [Aspose 版本](https://releases。aspose.com/email/net/).
- **購買**：了解有關購買許可證的更多信息，請訪問 [Aspose 購買](https://purchase。aspose.com/buy).
- **免費試用和臨時許可證**：免費試用功能或申請臨時許可證 [Aspose 下載](https://releases。aspose.com/email/net/). 

今天就踏出第一步，

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}