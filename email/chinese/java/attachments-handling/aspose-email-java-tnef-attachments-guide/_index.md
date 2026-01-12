---
date: '2025-12-13'
description: 学习如何使用 Aspose.Email for Java 将 msg 转换为 eml，添加新附件，保存电子邮件附件并处理 TNEF 数据。
keywords:
- Aspose.Email Java
- TNEF Handling
- Email Attachments
title: 使用 Aspose.Email Java 将 msg 转换为 eml – TNEF 附件指南
url: /zh/java/attachments-handling/aspose-email-java-tnef-attachments-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 精通 Aspose.Email Java：处理 TNEF 与电子邮件附件  

在现代以电子邮件为中心的应用中，您经常需要 **convert msg eml** 文件，向现有邮件添加新附件，并保留 TNEF 等特殊格式。无论您是在构建归档服务、迁移工具，还是客户端邮件查看器，Aspose.Email for Java 都为您提供了一种简洁的编程方式来实现这些功能。在本教程中，您将看到如何 **convert msg to eml**、添加新附件、保存电子邮件附件，以及使用 Aspose.Email Java 库处理 TNEF 数据的完整步骤。

## 快速答案
- **How do I convert MSG to EML?** Use `MapiMessage` with `MailConversionOptions` and set `convertAsTnef` to `true`.  
- **Can I add an attachment to a TNEF‑enabled EML?** Yes – load the EML, call `getAttachments().addItem(...)`, then save.  
- **What version of Aspose.Email is required?** The example uses version 25.4 (JDK 16).  
- **Do I need a license for production?** Yes – a trial works for evaluation, but a full license removes limitations.  
- **Is there a way to detect TNEF in an existing message?** Call `mail.getOriginalIsTnef()` after loading the EML.

## 什么是 “convert msg eml”？
将 Microsoft Outlook MSG 文件转换为标准 EML 格式，使该邮件能够被任何符合 RFC‑822 标准的邮件客户端读取。转换过程还为您提供了在处理过程中保留或操作 TNEF 编码数据的机会。

## 为什么使用 Aspose.Email Java 完成此任务？
- **Full format support** – MSG, EML, MHTML, and more.  
- **Built‑in TNEF handling** – no need for third‑party parsers.  
- **Simple API** – one‑line calls for loading, converting, and saving.  
- **Robust licensing** – trial for testing, full license for production.

## 前置条件
- **Aspose.Email for Java** (v25.4, JDK 16) – see Maven dependency below.  
- **Maven** 或其他能够解析 Aspose 包的构建工具。  
- 基本的 Java I/O 与异常处理知识。  

## 设置 Aspose.Email for Java
将库添加到您的 Maven `pom.xml` 中：

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### 许可证获取
Aspose.Email 提供免费试用，但要想无限制使用需要许可证。

- **Free Trial:** Download a temporary license [here](https://releases.aspose.com/email/java/).  
- **Purchase:** To buy a license, visit the [purchase page](https://purchase.aspose.com/buy).

在 Java 代码中初始化许可证：

```java
License license = new License();
license.setLicense("path/to/your/license/file.lic");
```

## 实现指南

### 向包含 TNEF 的主邮件添加新附件
**How to add attachment:** Load the EML, add the file, then save.

#### 步骤 1：加载现有电子邮件
```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY/";
MailMessage eml = MailMessage.load(dataDir + "MainMessage.eml");
```

#### 步骤 2：添加新附件
```java
try (FileInputStream fi = new FileInputStream(dataDir + "barcode.png")) {
    eml.getAttachments().addItem(new Attachment(fi, "barcode.png", "image/png"));
}
```

#### 步骤 3：保存修改后的电子邮件
```java
eml.save(dataDir + "test_out.eml");
```
*Pro tip:* Use try‑with‑resources to ensure streams are closed and avoid `FileNotFoundException`.

### 从 MSG 创建支持 TNEF 的 EML
**How to convert msg to eml:** Set `convertAsTnef` to `true`.

#### 步骤 1：加载 MSG 文件
```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY/";
MapiMessage msg = MapiMessage.fromFile(dataDir + "Message.msg");
```

#### 步骤 2：设置转换选项
```java
MailConversionOptions options = new MailConversionOptions();
options.setConvertAsTnef(true);
```

#### 步骤 3：转换并保存
```java
MailMessage mail = msg.toMailMessage(options);
mail.save(dataDir + "converted_message.eml");
```

### 加载 EML 文件时保留 TNEF 附件
**How to save email attachment while preserving TNEF:** Use `MsgLoadOptions`.

#### 步骤 1：设置加载选项
```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY/";
MsgLoadOptions msgLoadOptions = new MsgLoadOptions();
msgLoadOptions.setPreserveTnefAttachments(true);
```

#### 步骤 2：使用选项加载 EML 文件
```java
MailMessage eml = MailMessage.load(dataDir + "test.eml", msgLoadOptions);
```

### 检测邮件是否为 TNEF
**How to check TNEF presence:** Call `getOriginalIsTnef()`.

#### 步骤 1：加载 EML 文件
```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY/";
MailMessage mail = MailMessage.load(dataDir + "test.eml");
```

#### 步骤 2：检测 TNEF 存在性
```java
boolean isTnef = mail.getOriginalIsTnef();
system.out.println("Is TNEF: " + isTnef);
```

## 实际应用
1. **Email Archiving:** Preserve every attachment—including TNEF‑encoded ones—for compliance audits.  
2. **Corporate Migration:** Convert legacy MSG files to EML so they can be imported into modern mail servers.  
3. **Customer Support:** Automatically detect TNEF data when users forward messages between Outlook and web‑mail clients.

## 性能考虑
- **Resource Management:** Wrap file streams in try‑with‑resources to free handles promptly.  
- **Large Attachments:** Process big files in chunks or stream them directly to avoid high memory usage.  
- **Monitoring:** Use Java profiling tools to watch heap consumption when handling many attachments.

## 结论
通过上述步骤，您可以 **convert msg eml**、添加新附件、保存电子邮件附件，并使用 Aspose.Email for Java 可靠地处理 TNEF 数据。该库抽象了底层 MIME 处理，让您专注于业务逻辑。想进一步探索，请查阅官方 [Aspose documentation](https://reference.aspose.com/email/java/) 或尝试其他转换选项。

## FAQ Section
**Q1: What is a TNEF file?**  
A1: TNEF stands for Transport Neutral Encapsulation Format and is used by Microsoft Outlook to preserve rich‑text formatting when sending emails as attachments.

**Q2: Can I use Aspose.Email without purchasing a license?**  
A1: Yes, you can start with a free trial. However, the trial version imposes certain limitations that may affect full‑scale usage.

**Q3: Is it possible to convert between all email formats using Aspose.Email?**  
A1: Aspose.Email supports conversion among most popular formats—including EML, MSG, and MHTML‑ but verify specific format support in the [documentation](https://reference.aspose.com/email/java/).

**Q4: How do I troubleshoot file‑not‑found errors with Aspose.Email?**  
A1: Double‑check that the file paths you pass to the API are correct, that the files exist, and that the executing process has read/write permissions for those directories.

**Q5: What is the best way to handle large attachments with Aspose.Email?**  
A1: Process attachments in smaller streams or chunks, and always close streams promptly. This reduces memory pressure and prevents `OutOfMemoryError`.

## Frequently Asked Questions (Additional)

**Q: Does Aspose.Email automatically strip TNEF when converting to EML?**  
A: No. By default, TNEF data is preserved. You can control this behavior with `MailConversionOptions.setConvertAsTnef`.

**Q: Can I programmatically list all attachments in a loaded message?**  
A: Yes—use `mail.getAttachments()` which returns a collection you can iterate over.

**Q: Is there a way to convert a batch of MSG files to EML in one run?**  
A: Absolutely. Loop through the files, apply the conversion steps shown above, and save each result.

**Related Resources:** [Aspose Email Java Documentation](https://reference.aspose.com/email/java/) | [Aspose Email Java Releases](https://releases.aspose.com/email/java/) | [Buy Aspose.Email for Java](https://purchase.aspose.com/buy) | Download a temporary license [here](https://releases.aspose.com/email/java/).

---

**Last Updated:** 2025-12-13  
**Tested With:** Aspose.Email for Java 25.4 (JDK 16)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}