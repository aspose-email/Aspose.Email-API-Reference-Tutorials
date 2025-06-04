---
"date": "2025-05-29"
"description": "了解如何使用 Aspose.Email for Java 儲存和管理 PST 郵件。本指南介紹如何將電子郵件儲存為串流或文件，從而增強您的電子郵件管理工作流程。"
"title": "使用 Aspose.Email for Java 將 PST 郵件儲存到串流和檔案—綜合指南"
"url": "/zh-hant/java/outlook-pst-ost-operations/save-pst-messages-aspose-email-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Email for Java 將 PST 郵件儲存到串流和文件

## 介紹

如果沒有合適的工具，管理儲存在 PST 檔案中的電子郵件可能會很困難。有了 **Aspose.Email for Java**，您可以有效率地將 PST 檔案中的消息儲存到串流或單一檔案中，從而以程式設計方式簡化存檔、處理和分析電子郵件資料等任務。

在本指南中，我們將介紹：
- 從 PST 檔案中提取並儲存訊息
- 將電子郵件儲存為串流或獨立 .msg 檔案的技術
- 現實場景中的實際應用

準備好使用 Aspose.Email Java 提升您的電子郵件管理技能了嗎？讓我們先回顧一下先決條件！

### 先決條件

在開始之前，請確保您已：
1. **Java 開發工具包 (JDK) 16** 已安裝。
2. Maven 用於管理相依性和專案建置。
3. Java 程式設計基礎知識。

## 設定 Aspose.Email for Java

若要在 Java 專案中使用 Aspose.Email，請透過 Maven 設定庫：

### Maven配置

將此依賴項新增至您的 `pom.xml` 文件：

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### 許可證獲取

Aspose.Email for Java 現已獲得商業許可。您可以：
- **免費試用**：不受限制地存取全部功能。
- **臨時執照**：使用免費臨時許可證探索全部功能。
- **購買**：考慮購買以供長期使用。

取得許可證檔案後，請在應用程式中初始化 Aspose.Email，如下所示：

```java
License license = new License();
license.setLicense("path/to/your/license.lic");
```

## 實施指南

了解如何使用 Aspose.Email for Java 將 PST 訊息分解為邏輯部分來保存它。

### 使用 MessageInfo 將訊息從 PST 儲存到流

此功能可讓您將電子郵件訊息直接從 PST 檔案儲存到串流中，具體使用 `ByteArrayOutputStream`。

#### 概述

透過利用 `MessageInfo` 類，存取訊息詳細資訊並對其進行迭代以有效地保存每條訊息。

#### 實施步驟

1. **載入PST文件**
   
   首先載入您的 PST 檔案：
   ```java
   PersonalStorage pst = PersonalStorage.fromFile("YOUR_DOCUMENT_DIRECTORY/PersonalStorage.pst");
   ```
   
2. **存取收件匣資料夾**
   
   存取「myInbox」子資料夾中的消息：
   ```java
   FolderInfo inbox = pst.getRootFolder().getSubFolder("myInbox");
   ```
   
3. **迭代並將訊息儲存到流**
   
   使用循環枚舉訊息，將每個訊息保存到 `ByteArrayOutputStream`：
   ```java
   for (Object obj : inbox.enumerateMessages()) {
       MessageInfo messageInfo = (MessageInfo) obj;
       pst.saveMessageToStream(messageInfo.getEntryIdString(), new ByteArrayOutputStream());
   }
   ```

### 使用 MessageInfo 將郵件從 PST 儲存到文件

此功能涉及使用 `FileOutputStream`。

#### 概述

為每封郵件建立一個帶有其主題名稱的文件，以便於管理電子郵件檔案。

#### 實施步驟

1. **載入PST文件**
   
   與上一節類似：
   ```java
   PersonalStorage pst = PersonalStorage.fromFile("YOUR_DOCUMENT_DIRECTORY/PersonalStorage.pst");
   ```
   
2. **訪問和迭代訊息**
   
   存取“myInbox”中的消息並準備檔案輸出：
   ```java
   FolderInfo inbox = pst.getRootFolder().getSubFolder("myInbox");

   for (Object obj : inbox.enumerateMessages()) {
       MessageInfo messageInfo = (MessageInfo) obj;
       File file = new File(messageInfo.getSubject() + ".msg");
       
       try (FileOutputStream fop = new FileOutputStream(file)) {
           pst.saveMessageToStream(messageInfo.getEntryIdString(), fop);
       } catch (FileNotFoundException e) {
           // 處理例外
       }
   }
   ```

### 使用條目 ID 將訊息從 PST 儲存到串流

此方法使用 `enumerateMessagesEntryId()` 方法。

#### 概述

遍歷訊息條目 ID 並將每個條目儲存為流，以實現高效率的批次處理。

#### 實施步驟

1. **載入PST文件**
   
   ```java
   PersonalStorage pst = PersonalStorage.fromFile("YOUR_DOCUMENT_DIRECTORY/PersonalStorage.pst");
   ```
   
2. **訪問收件匣並透過條目 ID 進行迭代**
   
   使用條目 ID 儲存訊息：
   ```java
   FolderInfo inbox = pst.getRootFolder().getSubFolder("myInbox");

   for (Object obj : inbox.enumerateMessagesEntryId()) {
       String entryId = (String) obj;
       pst.saveMessageToStream(entryId, new ByteArrayOutputStream());
   }
   ```

## 實際應用

- **電子郵件歸檔**：將電子郵件儲存為.msg 檔案以便長期儲存。
- **數據分析**：處理電子郵件流以提取和分析內容。
- **與資料庫集成**：簡化在資料庫中儲存電子郵件元資料的過程。

## 性能考慮

- 透過有效管理流資源來優化記憶體使用情況。
- 處理大量電子郵件時使用批次技術。
- 遵循 Java 垃圾收集和資源管理的最佳實務。

## 結論

透過本教學課程，您學習如何利用 Aspose.Email for Java 有效率地管理 PST 檔案。無論是將郵件儲存為串流還是單一文件，這些方法都能為電子郵件資料處理提供強大的解決方案。

### 後續步驟

嘗試不同的配置並探索 Aspose.Email 的更多功能。考慮將您的解決方案整合到更大的系統中，例如 CRM 工具或資料庫管理應用程式。

## 常見問題部分

1. **如何有效處理大型 PST 檔案？**
   - 使用串流技術批次處理訊息，減少記憶體開銷。

2. **我可以從「我的收件匣」以外的資料夾中儲存電子郵件嗎？**
   - 是的，調整程式碼中的資料夾路徑以存取不同的子資料夾。

3. **如果郵件主題包含無效的檔案名稱符號怎麼辦？**
   - 實作清理邏輯，在將無效字元用作檔案名稱之前替換或刪除它們。

4. **保存訊息時如何處理異常？**
   - 在檔案操作周圍使用 try-catch 區塊並記錄錯誤以進行故障排除。

5. **Aspose.Email 適合企業應用程式嗎？**
   - 當然，其可擴展的架構使其成為大規模電子郵件處理任務的理想選擇。

## 資源
- [文件](https://reference.aspose.com/email/java/)
- [下載](https://releases.aspose.com/email/java/)
- [購買許可證](https://purchase.aspose.com/buy)
- [免費試用](https://releases.aspose.com/email/java/)
- [臨時執照](https://purchase.aspose.com/temporary-license/)
- [支援論壇](https://forum.aspose.com/c/email/10)

立即開始使用 Aspose.Email for Java 之旅並簡化您的電子郵件管理流程！

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}