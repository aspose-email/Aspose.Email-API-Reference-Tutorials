---
"date": "2025-05-30"
"description": "學習如何使用 Aspose.Email .NET 有效率地操作 MAPI 屬性。探索設定多值屬性、使用命名屬性進行自訂以及最佳化電子郵件工作流程的技巧。"
"title": "Aspose.Email .NET&#58; 掌握 MAPI 屬性操作以增強電子郵件管理"
"url": "/zh-hant/net/mapi-operations/mastering-mapi-property-manipulation-aspose-email-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Email .NET：掌握 MAPI 屬性操作以增強電子郵件管理

在動態的電子郵件通訊世界中，有效地管理和自訂訊息屬性對於簡化工作流程和增強資料互通性至關重要。 **Aspose.Email for .NET**開發人員可以在 MAPI 訊息上設定多個值屬性，以滿足不同的業務需求。本教學將深入探討如何使用 Aspose.Email 實現這些功能，確保您充分發揮其潛力。

## 您將學到什麼
- 在 MAPI 訊息上設定多個值屬性。
- 利用命名屬性來增強自訂。
- 實現單值屬性設定。
- Aspose.Email .NET 的實際應用和效能考量。

準備深入研究高階電子郵件管理 **Aspose.Email**？讓我們開始吧！

## 先決條件
在開始之前，請確保您具備以下條件：

### 所需庫
- **Aspose.Email for .NET**：確保您的專案包含這個庫。
- **.NET Framework 或 .NET Core/5+**：您的開發環境應該支援這些框架。

### 環境設定要求
- 一個可運行的 C# IDE，例如 Visual Studio。
- 對電子郵件系統中的 MAPI 訊息和屬性處理有基本的了解。

## 設定 Aspose.Email for .NET
若要將 Aspose.Email 整合到您的專案中，請按照以下安裝步驟操作：

**.NET CLI**
```bash
dotnet add package Aspose.Email
```

**套件管理器**
```powershell
Install-Package Aspose.Email
```

**NuGet 套件管理器 UI**
- 搜尋“Aspose.Email”並安裝最新版本。

### 許可證獲取
您可以先免費試用，探索 Aspose.Email 的功能。如需長期使用，請考慮申請臨時許可證或購買訂閱：
- [免費試用](https://releases.aspose.com/email/net/)
- [臨時執照](https://purchase.aspose.com/temporary-license/)
- [購買選項](https://purchase.aspose.com/buy)

#### 基本初始化
安裝後，在您的專案中初始化 Aspose.Email：
```csharp
using Aspose.Email.Mapi;
```

## 實施指南

### 設定多值屬性
此功能可讓您將多個值附加到 MAPI 屬性。對於需要多個值的屬性，此功能尤其有用。

#### PT_MV_FLOAT 和 PT_MV_R4
這些屬性代表浮點數：
```csharp
string dataDir = "YOUR_DOCUMENT_DIRECTORY";
MapiMessage msg = MapiMessage.FromFile(dataDir + "message.msg");

IList<object> values = new List<object>();
values.Add((float)1);
values.Add((float)2);

msg.SetProperty(new MapiProperty(0x23901004, values));
```

#### PT_MV_DOUBLE 和 PT_MV_R8
對於雙精度浮點數：
```csharp
values = new List<object>();
values.Add((double)1);
values.Add((double)2);

msg.SetProperty(new MapiProperty(0x23901005, values));
```

#### PT_MV_CURRENCY (mv.fixed.14.4)
設定貨幣相關屬性：
```csharp
values = new List<object>();
values.Add((decimal)123.34);
values.Add((decimal)289.45);

msg.SetProperty(new MapiProperty(0x23901006, values));
```

#### PT_MV_APPTIME
對於特定於應用程式的時間值：
```csharp
values = new List<object>();
values.Add(30456.34);
values.Add(40655.45);

msg.SetProperty(new MapiProperty(0x23901007, values));
```

#### PT_MV_I8 和 PT_MV_LONGLONG
處理大整數：
```csharp
values = new List<object>();
values.Add((long)30456);
values.Add((long)40655);

msg.SetProperty(new MapiProperty(0x23901014, values));
```

#### PT_MV_CLSID (mv.uuid)
對於唯一識別碼：
```csharp
values = new List<object>();
values.Add(Guid.NewGuid());
values.Add(Guid.NewGuid());

msg.SetProperty(new MapiProperty(0x23901048, values));
```

#### PT_MV_SHORT 和 PT_MV_I2
設定短整數屬性：
```csharp
values = new List<object>();
values.Add((short)1);
values.Add((short)2);

msg.SetProperty(new MapiProperty(0x23901002, values));
```

#### PT_MV_系統時間
對於系統時間值：
```csharp
values = new List<object>();
values.Add(DateTime.Now);
values.Add(DateTime.Now);

msg.SetProperty(new MapiProperty(0x23901040, values));
```

#### PT_MV_BOOLEAN
布爾屬性可以設定如下：
```csharp
values = new List<object>();
values.Add(true);
values.Add(false);

msg.SetProperty(new MapiProperty(0x2390100b, values));
```

#### PT_MV_二進位
對於二進位資料：
```csharp
values = new List<object>();
values.Add(Guid.NewGuid().ToByteArray());
values.Add(new byte[]{1,2,4,5,6,7,5,4,3,5,6,7,8,6,4,3,4,5,6,7,8,6,5,4,3,7,8,9,0,2,3,4});

msg.SetProperty(new MapiProperty(0x23901102, values));
```

#### PT_NULL
要設定空屬性：
```csharp
msg.SetProperty(new MapiProperty(0x67400001, new byte[1]));
```

### 在新訊息上設定命名屬性
命名屬性允許進行更具描述性的自訂：
```csharp
MapiMessage message = new MapiMessage("sender@test.com", "recipient@test.com", "subj", "Body of test msg");

IList<object> values = new List<object>();
values.Add((int)4);

MapiProperty property = new MapiProperty(message.NamedPropertyMapping.GetNextAvailablePropertyId(MapiPropertyType.PT_MV_LONG), values);
message.NamedPropertyMapping.AddNamedPropertyMapping(property, 0x00008028, new Guid("00062004-0000-0000-C000-000000000046"));
message.SetProperty(property);

// 設定具有特定名稱的自訂屬性
values = new List<object>();
values.Add((int)4);
property = new MapiProperty(message.NamedPropertyMapping.GetNextAvailablePropertyId(MapiPropertyType.PT_MV_LONG), values);
message.AddCustomProperty(property, "customProperty");
```

### 設定單值屬性
對於單值屬性：
```csharp
MapiMessage newMsg = new MapiMessage();
float floatValue = (float)123.456;
long floatTag = newMsg.NamedPropertyMapping.GetNextAvailablePropertyId(MapiPropertyType.PT_FLOAT);
Guid guid = Guid.NewGuid();

MapiProperty newMapiProperty = new MapiProperty(floatTag, BitConverter.GetBytes(floatValue));
newMsg.NamedPropertyMapping.AddNamedPropertyMapping(newMapiProperty, 12, guid);
newMsg.SetProperty(newMapiProperty);
```

## 實際應用
Aspose.Email的屬性操作功能有多種應用：
1. **自動電子郵件標記**：有效地對電子郵件進行分類，以便更好地組織。
2. **自訂元資料集成**：將附加資料附加到訊息中以增強追蹤和分析。
3. **多幣種支持**：無縫處理涉及不同貨幣的金融交易。
4. **增強安全性**：使用唯一識別碼（GUID）來安全處理訊息。
5. **系統時間同步**：確保分散式系統之間的時間戳記一致。

## 性能考慮
操作 MAPI 屬性時，請考慮以下事項以優化效能：
- 盡量減少屬性修改以減少處理開銷。
- 盡可能進行大量更新以提高效率。
- 處理大型資料集或大量電子郵件時監控記憶體使用量。

## 結論
透過掌握 Aspose.Email .NET 的 MAPI 屬性操作，您可以大幅增強電子郵件管理工作流程。本指南提供了實用的範例和應用程序，幫助您快速入門。如需進一步探索，您可以嘗試不同的屬性類型和場景。

請記住，有效電子郵件管理的關鍵是了解您可用的工具並策略性地應用它們。

## 關鍵字推薦
- “Aspose.Email .NET”
- “MAPI 屬性操作”
- “郵件管理優化”

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}