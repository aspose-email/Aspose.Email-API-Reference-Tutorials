---
title: Requesting Email Read Receipts using C# Code
linktitle: Requesting Email Read Receipts using C# Code
second_title: Aspose.Email .NET Email Processing API
description: Learn how to use C# code to request email read receipts using Aspose.Email for .NET, enhancing communication tracking.
type: docs
weight: 11
url: /net/email-notification-and-tracking/requesting-email-read-receipts-using-csharp-code/
---

In today's digital age, communication via email has become an integral part of our personal and professional lives. Often, when sending important emails, we want to ensure that the recipient has read and acknowledged our message. This is where email read receipts come into play. In this step-by-step tutorial, we will guide you through the process of requesting email read receipts using C# with Aspose.Email for .NET.

## Introduction to Email Read Receipts

Email read receipts, also known as email tracking or return receipts, allow you to receive notifications when the recipient opens and reads your email. It's a valuable feature, especially in business communications, as it provides confirmation of message delivery and engagement.

## Prerequisites

Before we dive into the code, make sure you have the following prerequisites in place:

- Visual Studio installed on your system.
- Aspose.Email for .NET library downloaded and referenced in your project.

## Step 1: Creating a MailMessage Instance

The first step in implementing email read receipts is to create an instance of the `MailMessage` class. This class represents an email message and allows you to set various properties of the email.

```csharp
MailMessage message = new MailMessage();
```

## Step 2: Specifying Message Details

Now, let's specify the details of the email message, including the sender, recipient, HTML body, and delivery notification options.

```csharp
message.From = "sender@sender.com";
message.To.Add("receiver@receiver.com");
message.HtmlBody = "<html><body>This is the Html body</body></html>";
message.DeliveryNotificationOptions = DeliveryNotificationOptions.OnSuccess;
message.Headers.Add("Return-Receipt-To", "sender@sender.com");
message.Headers.Add("Disposition-Notification-To", "sender@sender.com");
```

## Step 3: Creating an SmtpClient Instance

To send the email, we need to create an instance of the `SmtpClient` class, which is responsible for sending the message.

```csharp
SmtpClient client = new SmtpClient();
```

## Step 4: Configuring SMTP Settings

Configure your SMTP server settings by specifying the host server, username, password, and port number.

```csharp
client.Host = "smtp.server.com";
client.Username = "Username";
client.Password = "Password";
client.Port = 25;
```

## Step 5: Sending the Email

Finally, use the `client.Send` method to send the email message. If the message is sent successfully, a "Message Sent" notification will be displayed.

```csharp
try
{
    client.Send(message);
    Console.WriteLine("Message sent");
}
catch (Exception ex)
{
    System.Diagnostics.Trace.WriteLine(ex.ToString());
}
```

With these five simple steps, you can request email read receipts when sending emails using C# and Aspose.Email for .NET. This feature adds a layer of assurance to your email communications, ensuring that you know when your important messages are read.

## Complete Source Code
```csharp
// Create an Instance of MailMessage class
MailMessage message = new MailMessage();

// Specify From, To, HtmlBody, DeliveryNotificationOptions field
message.From = "sender@sender.com";
message.To.Add("receiver@receiver.com");
message.HtmlBody = "<html><body>This is the Html body</body></html>";
message.DeliveryNotificationOptions = DeliveryNotificationOptions.OnSuccess;
message.Headers.Add("Return-Receipt-To", "sender@sender.com");
message.Headers.Add("Disposition-Notification-To", "sender@sender.com");

// Create an instance of SmtpClient Class
SmtpClient client = new SmtpClient();

// Specify your mailing host server, Username, Password and Port No
client.Host = "smtp.server.com";
client.Username = "Username";
client.Password = "Password";
client.Port = 25;

try
{
	// Client.Send will send this message
	client.Send(message);
	// Display ‘Message Sent’, only if message sent successfully
	Console.WriteLine("Message sent");
}
catch (Exception ex)
{
	System.Diagnostics.Trace.WriteLine(ex.ToString());
}
```
## Conclusion

In this tutorial, we've explored how to request email read receipts using C# with Aspose.Email for .NET. Email tracking is a powerful tool for ensuring your messages are delivered and read by the intended recipients, particularly in professional settings. By following the steps outlined here, you can easily implement this functionality in your email application.

## Frequently Asked Questions (FAQs)

1. ### What is the purpose of email read receipts?
   Email read receipts provide confirmation that an email has been opened and read by the recipient. They are often used for tracking important or time-sensitive messages.

2. ### Can email read receipts be disabled by the recipient?
   Yes, email clients often allow users to disable the sending of read receipts. Therefore, it's not guaranteed that you will always receive them.

3. ### Are email read receipts a standard feature in all email clients?
   No, email read receipts are not universally supported. Whether they work or not depends on the email client and the recipient's settings.

4. ### Is it possible to track when an email is opened on a mobile device?
   Email tracking is typically based on the recipient's email client and settings, so it may or may not work on mobile devices, depending on various factors.

5. ### Are there privacy considerations when using email read receipts?
   Yes, there are privacy concerns related to email tracking. Some recipients may consider it invasive, so it's essential to use this feature responsibly and respect privacy preferences.