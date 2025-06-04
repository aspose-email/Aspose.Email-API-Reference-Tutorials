---
"date": "2025-05-30"
"description": "學習使用 Aspose.Email for .NET 和 EWS 進行進階電子郵件過濾的技術。有效率地按日期、寄件者、收件者、通知、大小等管理電子郵件。"
"title": "掌握使用 Aspose.Email .NET for Exchange Server 整合的高階 EWS 電子郵件過濾"
"url": "/zh-hant/net/exchange-server-integration/advanced-ews-email-filtering-aspose-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Email .NET 掌握進階 EWS 電子郵件過濾

## 介紹
在快節奏的數位世界中，高效的電子郵件管理至關重要。每天都有無數的郵件湧入，對其進行分類以快速找到相關資訊可以顯著提高工作效率。本教學將引導您使用 Aspose.Email for .NET 和 Exchange Web Services (EWS) 實作進階過濾技術。您將學習如何連接到 EWS 並根據日期、寄件者、收件人、送達通知、大小等條件過濾電子郵件。

**您將學到什麼：**
- 使用 Aspose.Email for .NET 連接到 EWS。
- 按日期、寄件者、收件者和其他屬性過濾電子郵件。
- 實現分頁支援以實現高效率的訊息過濾。
- 優化處理大量電子郵件資料時的效能。

在深入探討實施細節之前，讓我們先回顧一下先決條件。

## 先決條件
要繼續本教程，請確保您已具備：
- **Aspose.Email for .NET** 庫已安裝在您的專案中。本教學針對的是 22.x 以上版本。
- 對 C# 程式設計有基本的了解。
- 存取啟用了 EWS 的 Exchange 伺服器（例如 Microsoft Outlook）。
- Visual Studio 或任何相容的 IDE。

在繼續實施部分之前，請確保這些工具已設定好。

## 設定 Aspose.Email for .NET
首先，使用以下方法之一在您的專案中安裝 Aspose.Email：

**.NET CLI：**
```bash
dotnet add package Aspose.Email
```

**套件管理器控制台：**
```powershell
Install-Package Aspose.Email
```

**NuGet 套件管理器 UI：**
搜尋“Aspose.Email”並安裝最新版本。

### 許可證獲取
您可以透過三種方式取得許可證：
- **免費試用：** 下載臨時許可證來評估全部功能。
- **臨時執照：** 向 Aspose 申請免費的 30 天臨時許可證。
- **購買：** 如果您發現該工具對長期專案有用，請購買訂閱。

安裝和授權後，繼續初始化與 EWS 的連線。

## 實施指南

### 功能：連接到 EWS
**概述：** 使用 Aspose.Email for .NET 建立與 Exchange Web 服務 (EWS) 的連線。

#### 步驟 1：初始化連接
```csharp
using Aspose.Email.Clients.Exchange.WebService;
using System;

const string mailboxUri = "https://outlook.office365.com/ews/exchange.asmx」；
const string username = "username";
const string password = "password";
const string domain = "domain";                        

try
{
    IEWSClient client = EWSClient.GetEWSClient(mailboxUri, username, password, domain);
}
catch (Exception ex)
{
    Console.WriteLine(ex.Message);
}
```
**解釋：** 此程式碼使用提供的憑證連接到 Exchange 伺服器。請將佔位符替換為您的實際郵箱 URI 和身份驗證詳細資訊。

### 功能：按日期過濾電子郵件
**概述：** 了解如何過濾今天和過去 7 天內收到的電子郵件。

#### 步驟 1：檢索今天的電子郵件
```csharp
using Aspose.Email.Tools.Search;
using System;

try
{
    IEWSClient client = EWSClient.GetEWSClient(mailboxUri, username, password, domain);
    
    MailQueryBuilder builder = new MailQueryBuilder();
    builder.InternalDate.On(DateTime.Now);
    
    MailQuery query = builder.GetQuery();
    var messagesToday = client.ListMessages(client.MailboxInfo.InboxUri, query);
}
catch (Exception ex)
{
    Console.WriteLine(ex.Message);
}
```

#### 步驟 2： 檢索過去 7 天的電子郵件
```csharp
try
{
    IEWSClient client = EWSClient.GetEWSClient(mailboxUri, username, password, domain);
    
    MailQueryBuilder builder = new MailQueryBuilder();
    builder.InternalDate.Before(DateTime.Now);
    builder.InternalDate.Since(DateTime.Now.AddDays(-7));
    
    MailQuery query = builder.GetQuery();
    var messagesLastWeek = client.ListMessages(client.MailboxInfo.InboxUri, query);
}
catch (Exception ex)
{
    Console.WriteLine(ex.Message);
}
```
**解釋：** 使用 `MailQueryBuilder` 根據電子郵件日期建立查詢。這可以過濾今天或特定時間內收到的電子郵件。

### 功能：按寄件者或網域過濾電子郵件
**概述：** 此功能示範如何過濾來自特定寄件者和網域的電子郵件。

#### 步驟 1：檢索特定寄件者的電子郵件
```csharp
try
{
    IEWSClient client = EWSClient.GetEWSClient(mailboxUri, username, password, domain);
    
    MailQueryBuilder builderSender = new MailQueryBuilder();
    builderSender.From.Contains("saqib.razzaq@127.0.0.1");
    
    MailQuery querySender = builderSender.GetQuery();
    var senderMessages = client.ListMessages(client.MailboxInfo.InboxUri, querySender);
}
catch (Exception ex)
{
    Console.WriteLine(ex.Message);
}
```

#### 步驟 2：從特定網域檢索電子郵件
```csharp
try
{
    IEWSClient client = EWSClient.GetEWSClient(mailboxUri, username, password, domain);
    
    MailQueryBuilder builderDomain = new MailQueryBuilder();
    builderDomain.From.Contains("SpecificHost.com");
    
    MailQuery queryDomain = builderDomain.GetQuery();
    var domainMessages = client.ListMessages(client.MailboxInfo.InboxUri, queryDomain);
}
catch (Exception ex)
{
    Console.WriteLine(ex.Message);
}
```
**解釋：** 使用 `MailQueryBuilder` 按寄件者電子郵件地址或網域名稱過濾電子郵件。這有助於識別來自特定來源的重要通訊。

### 功能：按收件者或 MessageId 過濾電子郵件
**概述：** 了解如何過濾傳送給特定收件者並具有特定 MessageId 的電子郵件。

#### 步驟 1：檢索發送給特定收件者的電子郵件
```csharp
try
{
    IEWSClient client = EWSClient.GetEWSClient(mailboxUri, username, password, domain);
    
    MailQueryBuilder builderRecipient = new MailQueryBuilder();
    builderRecipient.To.Contains("recipient@example.com");
    
    MailQuery queryRecipient = builderRecipient.GetQuery();
    var recipientMessages = client.ListMessages(client.MailboxInfo.InboxUri, queryRecipient);
}
catch (Exception ex)
{
    Console.WriteLine(ex.Message);
}
```

#### 步驟 2：透過特定 MessageId 檢索電子郵件
```csharp
try
{
    IEWSClient client = EWSClient.GetEWSClient(mailboxUri, username, password, domain);
    
    ExchangeQueryBuilder builderMessageId = new ExchangeQueryBuilder();
    builderMessageId.MessageId.Equals("Specific-Message-ID");
    
    MailQuery queryMessageId = builderMessageId.GetQuery();
    var messageIdMessages = client.ListMessages(client.MailboxInfo.InboxUri, queryMessageId);
}
catch (Exception ex)
{
    Console.WriteLine(ex.Message);
}
```
**解釋：** 透過收件者或 MessageId 進行篩選有助於根據預期收件者或唯一識別碼鎖定感興趣的電子郵件。

### 功能：按送達通知和大小過濾電子郵件
**概述：** 此功能示範如何根據傳遞通知和郵件大小來過濾電子郵件。

#### 步驟 1：檢索郵件送達通知
```csharp
try
{
    IEWSClient client = EWSClient.GetEWSClient(mailboxUri, username, password, domain);
    
    ExchangeQueryBuilder builderMDN = new ExchangeQueryBuilder();
    builderMDN.ContentClass.Equals(ContentClassType.MDN.ToString());
    
    MailQuery queryMDN = builderMDN.GetQuery();
    var mdnMessages = client.ListMessages(client.MailboxInfo.InboxUri, queryMDN);
}
catch (Exception ex)
{
    Console.WriteLine(ex.Message);
}
```

#### 第 2 步：按大小過濾郵件
```csharp
try
{
    IEWSClient client = EWSClient.GetEWSClient(mailboxUri, username, password, domain);
    
    ExchangeQueryBuilder builderSize = new ExchangeQueryBuilder();
    builderSize.ItemSize.Greater(80000); // 以位元組為單位的範例大小
    
    MailQuery querySize = builderSize.GetQuery();
    var sizeMessages = client.ListMessages(client.MailboxInfo.InboxUri, querySize);
}
catch (Exception ex)
{
    Console.WriteLine(ex.Message);
}
```
**解釋：** 使用這些過濾器根據傳遞狀態和大小有效地管理電子郵件。

## 結論
本教學涵蓋了使用 Aspose.Email for .NET 和 EWS 進行進階電子郵件過濾的技術。掌握這些技能後，您可以有效率地管理收件箱，提高處理大量電子郵件的效率。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}