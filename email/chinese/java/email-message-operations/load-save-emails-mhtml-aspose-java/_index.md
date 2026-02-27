---
date: '2026-02-27'
description: 学习如何使用 Aspose.Email for Java 加载 MSG 文件并将其转换为 MHTML，包括自定义时区设置和批量邮件处理技巧。
keywords:
- Aspose.Email for Java
- load emails in MHTML format
- custom timezone settings
title: 如何使用 Aspose.Email for Java 加载 MSG 并保存为 MHTML
url: /zh/java/email-message-operations/load-save-emails-mhtml-aspose-java/
weight: 1
---

使用 Aspose.Email for Java 加载 MSG 并保存为 MHTML"

Similarly other headings.

Proceed.

Make sure to keep markdown syntax.

Let's craft final answer.{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何使用 Aspose.Email for Java 加载 MSG 并保存为 MHTML

## 介绍

如果你需要 **加载 msg** 文件、调整它们的时间戳，然后 **将 msg 转换为 mhtml**，这里就是你的目的地。在本教程中，我们将演示如何加载 `.msg` 邮件、应用自定义时区偏移，并将结果保存为 MHTML 存档——全部使用 Aspose.Email for Java。无论是处理单条消息还是 **批量邮件处理** 流程，这些步骤都能为你提供坚实的基础。

**你将学到的内容**
- 如何从 `.msg` 文件加载 `MailMessage`。
- 如何设置自定义时区和当前日期。
- 如何以精确的格式将邮件保存为 MHTML。
- 将该方法扩展到批量场景的技巧。

准备好提升你的邮件工作流了吗？先让环境准备就绪。

## 快速回答
- **主要使用的库是什么？** Aspose.Email for Java。
- **可以一步完成 MSG 加载并导出为 MHTML 吗？** 不能，需要先加载、调整，再保存。
- **生产环境需要许可证吗？** 需要，有效的 Aspose.Email 许可证是必需的。
- **时区处理是否受支持？** 支持，使用 `setTimeZoneOffset`。
- **可以用于批量处理吗？** 完全可以——将步骤放入循环即可。

## 前置条件

在开始之前，请确保具备以下条件：

### 必需的库和依赖
- **Aspose.Email for Java** 库 25.4 版（jdk16 classifier）
- 基础的 Java 知识。
- IntelliJ IDEA 或 Eclipse 等 IDE。

### 环境搭建要求
- 已安装 JDK 16 或更高版本。
- 使用 Maven 进行依赖管理。

## 设置 Aspose.Email for Java

在 Maven 项目中添加库依赖，请加入以下内容：

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### 许可证获取步骤

先使用 **免费试用** 或获取 **临时许可证** 来评估库的全部功能且无功能限制。长期使用请考虑购买正式许可证：

- [免费试用](https://releases.aspose.com/email/java/)
- [临时许可证](https://purchase.aspose.com/temporary-license/)
- [购买许可证](https://purchase.aspose.com/buy)

### 基本初始化

添加依赖后，在 Java 代码中初始化许可证：

```java
import com.aspose.email.License;

License license = new License();
license.setLicense("path_to_your_license_file.lic");
```

## 实现指南

我们将实现分为三个清晰的功能。

### 功能 1：从文件加载 MailMessage

#### 概述
加载 `.msg` 文件后，你可以以编程方式完全访问邮件的内容、附件和元数据。

#### 步骤说明

**导入所需类**

```java
import com.aspose.email.MailMessage;
import com.aspose.email.MsgLoadOptions;
```

**加载邮件**

```java
String filename = "YOUR_DOCUMENT_DIRECTORY/MSG file with RTF Formatting.msg";
MailMessage msg = MailMessage.load(filename, new MsgLoadOptions());
```

`MsgLoadOptions` 允许你控制 MSG 文件的解析方式；默认设置适用于大多数场景。

### 功能 2：设置当前日期和自定义时区偏移

#### 概述
在跨地区用户之间处理邮件时，准确的时间戳至关重要。

**设置当前日期**

```java
import java.util.Date;

msg.setDate(new Date());
```

**应用自定义时区偏移（例如 UTC+5）**

```java
msg.setTimeZoneOffset(5 * 60 * 60 * 1000); // 5 hours ahead of UTC in milliseconds.
```

偏移量以毫秒为单位，因此也可以传入负值来表示 UTC 西部的时区。

### 功能 3：将 MailMessage 保存为 MHTML 文件

#### 概述
MHTML 将 HTML 内容及嵌入资源打包成单个文件，非常适合归档或共享。

**配置保存选项**

```java
import com.aspose.email.MhtSaveOptions;
import com.aspose.email.MhtFormatOptions;

MhtSaveOptions mhtOptions = new MhtSaveOptions();
mhtOptions.setMhtFormatOptions(MhtFormatOptions.WriteHeader);
```

**保存邮件**

```java
msg.save("YOUR_OUTPUT_DIRECTORY/ExportToMHTWithCustomTimezone_out.mhtml", mhtOptions);
```

生成的 `.mhtml` 文件保留原始的格式、图片和附件。

## 为什么要将 MSG 转换为 MHTML？

将 MSG 文件转换为 MHTML 可以得到一种网页友好的单文件表示，任何现代浏览器都能打开。这在以下场景尤为有用：

- **法律归档**：需要忠实的可视化副本。
- **跨平台共享**：无需 Outlook 即可查看。
- **在网页或文档中嵌入邮件**。

## 批量邮件处理技巧

如果需要 **批量邮件处理**，请将加载、时区调整和保存步骤放入遍历 `.msg` 文件目录的循环中。记住：

1. 重复使用同一个 `License` 实例以避免额外开销。
2. 每次迭代后释放资源（如适用，调用 `msg.dispose()`）。
3. 将失败日志记录到单独文件，以便后续检查。

## 实际应用场景

1. **邮件归档**：将通信以可移植格式保存以满足合规要求。
2. **全球调度**：在发送通知前统一时区时间戳。
3. **CRM 集成**：自动将归档邮件作为 MHTML 附件导入 CRM 系统。

## 性能考虑

- **内存管理**：将大批量分块处理，以保持内存占用低。
- **I/O 优化**：读取/写入大量文件时使用缓冲流。
- **并行执行**：可考虑 Java 的 `ForkJoinPool` 实现并行处理，但需确保 Aspose 对象的线程安全。

## 结论

现在你已经掌握了 **加载 msg** 文件、应用自定义时区偏移，并使用 Aspose.Email for Java **将 msg 转换为 mhtml** 的方法。这些技术可以扩展到 **批量邮件处理** 任务，为邮件归档、迁移和自动化提供了强大的解决方案。

**后续步骤**  
通过访问官方 [文档](https://reference.aspose.com/email/java/) 进一步探索 Aspose.Email 的附件处理、日历项提取或 SMTP 发送等功能。

## 常见问题

**问：可以加载除 .msg 之外的其他格式吗？**  
答：可以，Aspose.Email 支持 EML、MSG、MHT 等多种格式。

**问：如何高效处理非常大的邮件文件？**  
答：使用 Aspose.Email 提供的流式 API，以块方式读写数据，降低内存压力。

**问：能否在 MailMessage 中修改附件？**  
答：完全可以。通过 `MailMessage.getAttachments()` 集合可以添加、删除或替换附件。

**问：如果我的时区偏移是负数（UTC 之前）怎么办？**  
答：向 `setTimeZoneOffset` 传入负的毫秒值，例如 `-3 * 60 * 60 * 1000` 表示 UTC‑3。

**问：Aspose.Email 能用于商业项目吗？**  
答：可以，只要拥有有效的商业许可证。

**问：如何在处理成千上万的 MSG 文件时避免内存耗尽？**  
答：分批处理文件，保存后释放每个 `MailMessage`，并考虑使用 Java 的 `try‑with‑resources` 语法实现自动清理。

---

**最后更新：** 2026-02-27  
**测试环境：** Aspose.Email for Java 25.4（jdk16 classifier）  
**作者：** Aspose  

## 资源
- [文档](https://reference.aspose.com/email/java/)
- [下载库](https://releases.aspose.com/email/java/)
- [购买许可证](https://purchase.aspose.com/buy)
- [免费试用](https://releases.aspose.com/email/java/)
- [临时许可证](https://purchase.aspose.com/temporary-license/)
- [支持论坛](https://forum.aspose.com/c/email/10)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}