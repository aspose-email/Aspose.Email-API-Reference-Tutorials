---
"date": "2025-05-30"
"description": "了解如何使用 Aspose.Email for .NET 載入和管理 MAPI 郵件。本指南內容全面，涵蓋載入 MAPI 郵件、建立筆記以及管理 PST 檔案。"
"title": "使用 Aspose.Email for .NET 載入和管理 MAPI 訊息－綜合指南"
"url": "/zh-hant/net/mapi-operations/load-manage-mapi-messages-aspose-email-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Email for .NET 載入和管理 MAPI 訊息：綜合指南

## 介紹

使用 Aspose.Email for .NET，您可以將電子郵件功能無縫地整合到您的 .NET 應用程式中。這個強大的程式庫以程式設計方式簡化了 Microsoft Outlook 郵件的管理。無論您是開發需要處理電子郵件的應用程序，還是在企業環境中自動執行任務，本指南都能為您提供高效入門的見解。

**您將學到什麼：**
- 如何從檔案載入 MAPI 訊息
- 以程式設計方式建立和自訂筆記
- 有效管理個人儲存檔案 (PST)

在開始編碼之前，讓我們確保您的環境已準備好必要的依賴項。

## 先決條件

要遵循本教程，請確保您具有以下設定：

### 所需的函式庫、版本和相依性
- **Aspose.Email for .NET**：確保與專案的目標框架相容。

### 環境設定要求
- 在您的機器上安裝相容版本的 .NET SDK。
- 使用文字編輯器或支援 C# 開發的 IDE（如 Visual Studio）。

### 知識前提
- 對 C# 程式設計有基本的了解。
- 熟悉電子郵件概念和 MAPI 訊息是有益的，但不是必需的。

## 設定 Aspose.Email for .NET

首先，將 Aspose.Email 庫新增到您的專案中。操作如下：

**使用 .NET CLI：**
```bash
dotnet add package Aspose.Email
```

**使用套件管理器：**
```powershell
Install-Package Aspose.Email
```

**透過 NuGet 套件管理器 UI：**
搜尋“Aspose.Email”並安裝最新版本。

### 許可證取得步驟
您可以先免費試用，或取得臨時許可證來探索更多功能：
- **免費試用**： [下載](https://releases.aspose.com/email/net/)
- **臨時執照**：可在 Aspose 網站上獲取，以進行擴展訪問。
- **購買**：完整許可選項可在 [Aspose 購買](https://purchase。aspose.com/buy).

**基本初始化和設定**
確保您的專案引用了必要的命名空間：
```csharp
using System;
using Aspose.Email.Mapi;
```

## 實施指南

我們將把實作分為兩個主要功能：載入 MAPI 訊息和管理 PST 檔案。

### 功能1：載入MAPI訊息

#### 概述
此功能示範如何從檔案載入 MAPI 訊息，這對於處理應用程式中已儲存的電子郵件訊息或註釋至關重要。

#### 實施步驟

**步驟 1：載入 MAPI 訊息**
指定你的 `Note.msg` 文件的位置並使用 Aspose.Email 載入它：
```csharp
string dataDir = \@"YOUR_DOCUMENT_DIRECTORY";
MapiMessage mess = MapiMessage.FromFile(dataDir + "Note.msg");
```

**第 2 步：建立和自訂註釋**
將載入的訊息轉換為具有不同屬性的多個註釋：
```csharp
// 建立黃色註釋
MapiNote note1 = (MapiNote)mess.ToMapiMessageItem();
note1.Subject = "Yellow color note";
note1.Body = "This is a yellow color note";

// 建立粉紅色筆記
MapiNote note2 = (MapiNote)mess.ToMapiMessageItem();
note2.Subject = "Pink color note";
note2.Body = "This is a pink color note";
note2.Color = NoteColor.Pink;

// 用維度創建藍色音符
MapiNote note3 = (MapiNote)mess.ToMapiMessageItem();
note3.Subject = "Blue color note";
note3.Body = "This is a blue color note";
note3.Color = NoteColor.Blue;
note3.Height = 500;
note3.Width = 500;
```

### 功能2：建立和管理個人儲存檔案（PST）

#### 概述
了解如何建立 PST 檔案、新增資料夾以及插入 MAPI 訊息。這對於需要在本地儲存電子郵件的應用程式至關重要。

#### 實施步驟

**步驟 1：設定輸出路徑**
定義輸出 PST 檔案的儲存位置：
```csharp
string outputPath = \@"YOUR_OUTPUT_DIRECTORY\AddMapiNoteToPST_out.pst";

// 如果存在檔案則刪除，以確保不存在檔案衝突。
if (File.Exists(outputPath))
{
    File.Delete(outputPath);
}
```

**步驟 2：建立並組織 PST**
初始化新的 PST 並建立資料夾：
```csharp
using (PersonalStorage personalStorage = PersonalStorage.Create(outputPath, FileFormatVersion.Unicode))
{
    // 建立一個「Notes」資料夾來儲存您的筆記。
    FolderInfo notesFolder = personalStorage.CreatePredefinedFolder("Notes\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}