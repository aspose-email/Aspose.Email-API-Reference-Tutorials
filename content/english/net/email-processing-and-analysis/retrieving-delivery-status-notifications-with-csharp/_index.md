---
title: Retrieving Delivery Status Notifications with C#
linktitle: Retrieving Delivery Status Notifications with C#
second_title: Aspose.Email .NET Email Processing API
description: Learn how to retrieve email Delivery Status Notifications using C# and Aspose.Email for .NET.
type: docs
weight: 18
url: /net/email-processing-and-analysis/retrieving-delivery-status-notifications-with-csharp/
---

## Introduction

In email communication, Delivery Status Notifications (DSNs) play a crucial role in informing senders about the delivery status of their emails. Aspose.Email for .NET is a powerful library that provides functionalities to work with emails, including retrieving DSNs. In this guide, we'll walk through the process of retrieving Delivery Status Notifications using C# and the Aspose.Email for .NET library.

## Prerequisites

Before you begin, ensure that you have the following prerequisites:

1. Visual Studio installed.
2. Aspose.Email for .NET library. You can download it from [here](https://releases.aspose.com/email/net).
3. Basic understanding of C# programming.

## Steps

Follow these steps to retrieve Delivery Status Notifications using Aspose.Email for .NET:

### Step 1: Create a New Project

Open Visual Studio and create a new C# console application project.

### Step 2: Add Aspose.Email Reference

Copy the downloaded Aspose.Email DLL to your project's directory. Then, right-click on the project in Solution Explorer, choose "Add" > "Reference," and browse for the Aspose.Email DLL. Click "OK" to add the reference to your project.

### Step 3: Write Code to Retrieve DSNs

Open the `Program.cs` file in your project and import the necessary namespaces:

```csharp
using Aspose.Email;
using Aspose.Email.Imap;
using Aspose.Email.Mail;
```

Inside the `Main` method, write the code to connect to the email server, retrieve DSNs, and process them:

```csharp
class Program
{
    static void Main(string[] args)
    {
        // Set your IMAP server credentials and host
        string host = "your_imap_host";
        int port = 993;
        string username = "your_email";
        string password = "your_password";

        using (ImapClient client = new ImapClient(host, port, username, password))
        {
            // Select the Inbox folder
            client.SelectFolder(ImapFolderInfo.InBox);

            // Search for messages with DSNs
            MailQueryBuilder queryBuilder = new MailQueryBuilder();
            queryBuilder.HasFlags(Aspose.Email.Mail.MessageFlags.DeliveryNotification);
            MailQuery query = queryBuilder.GetQuery();
            ImapMessageInfoCollection messages = client.ListMessages(query);

            // Process retrieved DSNs
            foreach (ImapMessageInfo messageInfo in messages)
            {
                MailMessage message = client.FetchMessage(messageInfo.SequenceNumber);

                // Process DSN details
                Console.WriteLine("Subject: " + message.Subject);
                Console.WriteLine("From: " + message.From);
                // ... Process other DSN details

                // Mark the message as read or delete it
                client.DeleteMessage(messageInfo.SequenceNumber);
            }
        }
    }
}
```

Replace `"your_imap_host"`, `"your_email"`, and `"your_password"` with your actual IMAP server details.

### Step 4: Run the Application

Build and run your application. It will connect to your email server, retrieve DSNs from the Inbox folder, process their details, and optionally delete them or mark them as read.

## FAQs

### How do I find the IMAP server host?

You can find the IMAP server host from your email service provider's documentation or settings. It's usually in the format of `imap.yourdomain.com`.

### How can I process DSN details other than subject and sender?

You can access various properties of the `MailMessage` object to retrieve DSN details such as recipient addresses, delivery status, timestamp, and more. Refer to the [Aspose.Email documentation](https://reference.aspose.com/email/net/) for more information.

### Is it necessary to delete or mark DSNs as read?

No, it's not necessary. Whether to delete or mark DSNs as read depends on your application's requirements. The provided code demonstrates both options, but you can customize it according to your needs.

## Conclusion

Retrieving Delivery Status Notifications using C# and Aspose.Email for .NET is a straightforward process. The Aspose.Email library simplifies the communication with the IMAP server and provides easy-to-use APIs to process email messages. With this guide, you can now incorporate DSN retrieval functionality into your C# applications.