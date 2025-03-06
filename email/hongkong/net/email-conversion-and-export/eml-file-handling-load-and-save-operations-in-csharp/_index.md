---
title: EML 檔案處理 - C# 中的載入與儲存操作
linktitle: EML 檔案處理 - C# 中的載入與儲存操作
second_title: Aspose.Email .NET 電子郵件處理 API
description: 了解如何使用 Aspose.Email for .NET 在 C# 中處理 EML 檔案。包含用於載入、修改和保存電子郵件的程式碼範例的逐步指南。
weight: 13
url: /zh-hant/net/email-conversion-and-export/eml-file-handling-load-and-save-operations-in-csharp/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# EML 檔案處理 - C# 中的載入與儲存操作


## EML 文件簡介

電子郵件格式 (EML) 檔案儲存電子郵件並廣泛用於存檔和共用。 Aspose.Email for .NET 透過提供一套全面的功能來以程式設計方式載入、修改和儲存電子郵件訊息，從而簡化了 EML 檔案的處理。

## 設定項目

在開始之前，請確保您已安裝 Aspose.Email for .NET 程式庫。您可以從以下位置下載：[這裡](https://releases.aspose.com/email/net).

## 載入 EML 文件

載入 EML 檔案是處理電子郵件的第一步。 Aspose.Email for .NET 提供了載入單一 EML 檔案或批次載入多個檔案的有效方法。

## 載入單一 EML 文件

要載入單一 EML 文件，您可以使用以下程式碼片段：

```csharp


//載入 EML 文件
MailMessage message = MailMessage.Load("path/to/email.eml");
```

## EML檔案批次載入

如果你的目錄包含多個EML文件，你可以批次載入它們：

```csharp


//載入多個 EML 文件
string[] emlFiles = Directory.GetFiles("path/to/eml/directory", "*.eml");
foreach (string emlFile in emlFiles)
{
    MailMessage message = MailMessage.Load(emlFile);
    //根據需要處理每條訊息
}
```

## 修改EML內容

載入 EML 檔案後，您可以使用 Aspose.Email 程式庫存取和修改其內容。

## 存取電子郵件屬性

您可以存取已載入電子郵件的各種屬性，例如寄件者、收件者、主題和正文：

```csharp


//存取電子郵件屬性
Console.WriteLine($"From: {message.From}");
Console.WriteLine($"To: {message.To}");
Console.WriteLine($"Subject: {message.Subject}");
Console.WriteLine($"Body: {message.HtmlBody}");
```

## 修改收件者和主題

若要修改收件者和主題，可以使用以下程式碼：

```csharp


//修改收件者和主題
message.To.Clear();
message.To.Add("newrecipient@example.com");
message.Subject = "Updated Subject";
```

## 使用附件

附件是電子郵件的重要組成部分。您可以使用 Aspose.Email 存取和管理附件：

```csharp


//訪問附件
foreach (Attachment attachment in message.Attachments)
{
    //處理每個附件
}
```

## 保存 EML 文件

對 EML 內容進行必要的修改後，您可以將電子郵件儲存回 EML 檔案。

## 保存單一 EML 文件

若要將單封電子郵件儲存到 EML 文件，請使用以下程式碼：

```csharp


//儲存修改後的訊息
message.Save("path/to/modified_email.eml", SaveOptions.DefaultEml);
```

## 批量保存EML文件

若要批次保存修改後的電子郵件，請迭代訊息並保存每一則：

```csharp


//批次保存修改的訊息
foreach (MailMessage modifiedMessage in modifiedMessages)
{
    modifiedMessage.Save($"path/to/modified_emails/{Guid.NewGuid()}.eml", SaveOptions.DefaultEml);
}
```

## 錯誤處理和異常管理

使用 EML 檔案時，妥善處理異常非常重要。使用 try-catch 區塊有效管理錯誤並確保流暢的使用者體驗。

## 結論

Aspose.Email for .NET 簡化了 C# 應用程式中 EML 檔案的處理。憑藉其全面的功能，您可以輕鬆地以程式設計方式載入、修改和儲存電子郵件。

## 常見問題解答

### 如何安裝 Aspose.Email for .NET？

您可以從以下位置下載 Aspose.Email for .NET[這裡](https://releases.aspose.com/email/net).

### 我可以使用 Aspose.Email 修改附件嗎？

是的，您可以使用 Aspose.Email 存取和管理電子郵件中的附件。

### 使用 EML 檔案時錯誤處理重要嗎？

當然，錯誤處理對於確保流暢的使用者體驗和應用程式的正常運作至關重要。

### 我可以一次載入多個 EML 檔案嗎？

是的，Aspose.Email允許您批量加載多個EML文件，方便處理多封電子郵件。

### Aspose.Email適合商業項目嗎？

是的，Aspose.Email 是一個多功能庫，適用於個人和商業項目，為電子郵件操作提供強大的功能。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
