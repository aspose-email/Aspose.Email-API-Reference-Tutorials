---
"date": "2025-05-29"
"description": "学习如何使用 Aspose.Email for Java 配置 SMTP 客户端并高效地转发邮件。非常适合企业应用程序开发人员。"
"title": "使用 Aspose.Email for Java 进行 SMTP 电子邮件转发——综合指南"
"url": "/zh/java/smtp-client-operations/smtp-email-forwarding-aspose-email-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Email for Java 进行 SMTP 电子邮件转发：综合指南

在数字时代，以编程方式管理电子邮件对于开发企业或客户通信系统的开发人员至关重要。本指南详细介绍了如何使用 Aspose.Email for Java 设置 SMTP 客户端，从而高效地转发电子邮件，而无需使用 `MailMessage`。让我们来探索一下这个强大的工具如何满足您的电子邮件自动化需求。

## 您将学到什么：
- 使用 Aspose.Email for Java 配置 SMTP 客户端
- 使用集合管理电子邮件收件人
- 直接从文件流转发电子邮件

**先决条件：** 在深入研究之前，请确保您已准备好以下设置以有效地遵循本教程。

### 先决条件
要成功完成本指南，请确保您已：

- **库和依赖项：**
  - Aspose.Email for Java 版本 25.4 或更高版本。
  
- **环境设置：**
  - 兼容的 JDK（Java 开发工具包），最好是我们的 Maven 依赖项中的分类器指定的 JDK 16。
- **知识前提：**
  - 对 SMTP 协议有基本的了解
  - 熟悉 Java 编程

## 设置 Aspose.Email for Java

使用 Maven 集成 Aspose.Email 到你的项目中非常简单。添加以下依赖到你的 `pom.xml` 文件：

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### 获取许可证
Aspose.Email 提供免费试用许可证，供您无限制测试其全部功能。获取方式如下：

1. **免费试用：** 访问 [Aspose 的免费试用页面](https://releases.aspose.com/email/java/) 下载并开始使用评估版本。
2. **临时执照：** 如需延长测试时间，请通过以下方式申请临时许可证 [许可证请求页面](https://purchase。aspose.com/temporary-license/).
3. **购买：** 如果您发现 Aspose.Email 对您的项目有益，请考虑购买完整许可证 [Aspose 的购买页面](https://purchase。aspose.com/buy).

### 基本初始化和设置

一旦 Aspose.Email 包含在您的项目中，请初始化必要的组件：

```java
import com.aspose.email.SecurityOptions;
import com.aspose.email.SmtpClient;

String host = "mail.domain.com"; // 您的 SMTP 服务器地址
String username = "username";    // 身份验证的用户名
int smtpPort = 587;              // 端口号，TLS/STARTTLS 通常为 587
String password = "password";    // 身份验证密码

// 使用指定的凭据创建 SmtpClient 实例。
SmtpClient client = new SmtpClient(host, smtpPort, username, password, SecurityOptions.SSLExplicit);
```

## 实施指南

### SMTP 客户端配置
本节将指导您配置用于发送电子邮件的 SMTP 客户端。通过设置 `SmtpClient`，您可以使用指定的凭据和安全选项与您的电子邮件服务器建立连接。

#### 概述
配置涉及指定您的 SMTP 主机、端口、用户名、密码和安全选项 - 通常为安全连接的 SSLExplicit。

```java
import com.aspose.email.SecurityOptions;
import com.aspose.email.SmtpClient;

String host = "mail.domain.com";
String username = "username";
int smtpPort = 587;
String password = "password";

// 使用指定的凭据初始化 SmtpClient。
SmtpClient client = new SmtpClient(host, smtpPort, username, password, SecurityOptions.SSLExplicit);
```

### 电子邮件收件人集合
使用以下方式简化了收件人列表的管理 `MailAddressCollection`，它允许您轻松添加多个电子邮件地址。

#### 概述
此集合可用于存储和管理收件人的电子邮件，以便进行转发或发送操作。

```java
import com.aspose.email.MailAddressCollection;

// 创建一个新的 MailAddressCollection 实例。
MailAddressCollection recipients = new MailAddressCollection();

// 将多个收件人添加到集合中。
recipients.add("to1@domain.com");
recipients.add("to2@domain.com");
```

### 不使用 MailMessage 进行邮件转发
这个强大的功能允许您直接使用 `FileInputStream` 和 `SmtpClient`。

#### 概述
而不是创建新的 `MailMessage`，此方法使用现有的 EML 文件，从而可以高效地进行批量转发。

```java
import java.io.FileInputStream;
import java.io.IOException;

String fileName = "YOUR_DOCUMENT_DIRECTORY/test.eml"; // EML 文件的路径

// 打开电子邮件文件的 FileInputStream。
FileInputStream fos = new FileInputStream(fileName);

try {
    // 使用 SmtpClient 实例和收件人集合转发电子邮件。
    client.forward("Sender@domain.com\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}