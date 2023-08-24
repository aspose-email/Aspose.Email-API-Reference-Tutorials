---
title: 使用 C# 检索递送状态通知
linktitle: 使用 C# 检索递送状态通知
second_title: Aspose.Email .NET 电子邮件处理 API
description: 了解如何使用 C# 和 Aspose.Email for .NET 检索电子邮件传送状态通知。
type: docs
weight: 18
url: /zh/net/email-processing-and-analysis/retrieving-delivery-status-notifications-with-csharp/
---

## 介绍

在电子邮件通信中，传递状态通知 (DSN) 在通知发件人其电子邮件的传递状态方面发挥着至关重要的作用。 Aspose.Email for .NET 是一个功能强大的库，提供处理电子邮件的功能，包括检索 DSN。在本指南中，我们将逐步介绍使用 C# 和 Aspose.Email for .NET 库检索传递状态通知的过程。

## 先决条件

在开始之前，请确保您具备以下先决条件：

1. 已安装 Visual Studio。
2.  Aspose.Email for .NET 库。您可以从以下位置下载：[这里](https://releases.aspose.com/email/net).
3. 对 C# 编程有基本了解。

## 脚步

请按照以下步骤使用 Aspose.Email for .NET 检索传递状态通知：

### 第 1 步：创建一个新项目

打开 Visual Studio 并创建一个新的 C# 控制台应用程序项目。

### 第2步：添加Aspose.Email引用

将下载的 Aspose.Email DLL 复制到您的项目目录。然后，在解决方案资源管理器中右键单击该项目，选择“添加”>“引用”，然后浏览找到 Aspose.Email DLL。单击“确定”将引用添加到您的项目中。

### 步骤 3：编写代码来检索 DSN

打开`Program.cs`在您的项目中创建文件并导入必要的命名空间：

```csharp
using Aspose.Email;
using Aspose.Email.Imap;
using Aspose.Email.Mail;
```

在 - 的里面`Main`方法，编写代码以连接到电子邮件服务器、检索 DSN 并处理它们：

```csharp
class Program
{
    static void Main(string[] args)
    {
        //设置您的 IMAP 服务器凭据和主机
        string host = "your_imap_host";
        int port = 993;
        string username = "your_email";
        string password = "your_password";

        using (ImapClient client = new ImapClient(host, port, username, password))
        {
            //选择收件箱文件夹
            client.SelectFolder(ImapFolderInfo.InBox);

            //搜索带有 DSN 的邮件
            MailQueryBuilder queryBuilder = new MailQueryBuilder();
            queryBuilder.HasFlags(Aspose.Email.Mail.MessageFlags.DeliveryNotification);
            MailQuery query = queryBuilder.GetQuery();
            ImapMessageInfoCollection messages = client.ListMessages(query);

            //处理检索到的 DSN
            foreach (ImapMessageInfo messageInfo in messages)
            {
                MailMessage message = client.FetchMessage(messageInfo.SequenceNumber);

                //处理 DSN 详细信息
                Console.WriteLine("Subject: " + message.Subject);
                Console.WriteLine("From: " + message.From);
                //...处理其他 DSN 详细信息

                //将消息标记为已读或将其删除
                client.DeleteMessage(messageInfo.SequenceNumber);
            }
        }
    }
}
```

代替`"your_imap_host"`, `"your_email"`， 和`"your_password"`与您实际的 IMAP 服务器详细信息。

### 第 4 步：运行应用程序

构建并运行您的应用程序。它将连接到您的电子邮件服务器，从收件箱文件夹中检索 DSN，处理其详细信息，并可选择删除它们或将它们标记为已读。

## 常见问题解答

### 如何找到 IMAP 服务器主机？

您可以从电子邮件服务提供商的文档或设置中找到 IMAP 服务器主机。它通常采用以下格式`imap.yourdomain.com`.

### 如何处理除主题和发件人之外的 DSN 详细信息？

您可以访问的各种属性`MailMessage`对象来检索 DSN 详细信息，例如收件人地址、传递状态、时间戳等。请参阅[Aspose.Email 文档](https://reference.aspose.com/email/net/)了解更多信息。

### 是否有必要删除 DSN 或将其标记为已读？

不，这是没有必要的。是否删除 DSN 或将 DSN 标记为已读取决于应用程序的要求。提供的代码演示了这两个选项，但您可以根据需要对其进行自定义。

## 结论

使用 C# 和 Aspose.Email for .NET 检索传递状态通知是一个简单的过程。 Aspose.Email 库简化了与 IMAP 服务器的通信，并提供易于使用的 API 来处理电子邮件消息。通过本指南，您现在可以将 DSN 检索功能合并到您的 C# 应用程序中。