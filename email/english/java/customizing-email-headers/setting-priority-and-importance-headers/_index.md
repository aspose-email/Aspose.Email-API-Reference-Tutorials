---
title: "Send Email with Priority and Importance Headers using Aspose.Email"
linktitle: Setting Priority and Importance Headers with Aspose.Email
second_title: Aspose.Email Java Email Management API
description: "Learn how to send email with priority and set high priority email headers using Aspose.Email for Java. Follow this step‑by‑step guide."
weight: 14
url: /java/customizing-email-headers/setting-priority-and-importance-headers/
date: 2026-01-22
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Send Email with Priority and Importance Headers using Aspose.Email

## Introduction

In this comprehensive guide, you’ll learn **how to send email with priority** using Aspose.Email for Java. Whether you’re delivering a time‑critical business proposal or simply want to highlight the urgency of a meeting request, setting the right priority and importance headers ensures your message gets the attention it deserves. We'll walk through creating the message, applying the priority, and sending it through an SMTP server.

## Quick Answers
- **What does “send email with priority” mean?** It adds standard email headers (e.g., *X-Priority*, *Importance*) that tell email clients the message is urgent.  
- **Which header sets the highest urgency?** `MailPriority.High` (maps to *X-Priority: 1* and *Importance: High*).  
- **Do I need a license to use Aspose.Email?** A free trial works for development; a license is required for production.  
- **Can I use this with Java 17?** Yes – Aspose.Email supports Java 8 and later.  
- **Is TLS required for SMTP?** It’s recommended; configure `SmtpClient` with `EnableSsl = true` if your server requires it.

## Prerequisites

Before diving into the code, ensure you have:

- Java Development Kit (JDK) installed on your machine.  
- Aspose.Email for Java library. You can download it from [here](https://releases.aspose.com/email/java/).  

## What is “send email with priority”?

Sending an email with priority means adding specific MIME headers that signal urgency to the recipient’s email client. Most clients display a visual cue (e.g., a red exclamation mark) when they detect high‑priority or high‑importance headers.

## Why set a high priority email?

- **Improved visibility:** Recipients can quickly spot urgent messages.  
- **Better workflow:** Critical alerts (system failures, meeting changes) are less likely to be missed.  
- **Professionalism:** Using the correct headers shows you understand email standards.

## Step 1: Create a Java Project

Start a new Java project in your favorite IDE (IntelliJ, Eclipse, VS Code, etc.). Add the Aspose.Email JAR to your project’s classpath or Maven/Gradle dependencies.

## Step 2: Import Aspose.Email Classes

These imports give you access to the core email‑handling classes.

```java
import com.aspose.email.*;
```

## Step 3: Create an Email Message (create email message java)

Now we’ll build a simple email, set the sender/receiver, and apply the priority header.

```java
// Create a new email message
MailMessage message = new MailMessage();

// Set sender and recipient addresses
message.setFrom("sender@example.com");
message.setTo("recipient@example.com");

// Set the subject and body of the email
message.setSubject("Important Meeting");

// Add the email body
message.setHtmlBody("<p>Dear Team,</p><p>Let's have an important meeting tomorrow at 10 AM.</p>");

// Set the email priority – this is how you **set high priority email**
message.setPriority(MailPriority.High);
```

> **Pro tip:** `MailPriority.High` automatically adds both *X-Priority* and *Importance* headers, covering the majority of email clients.

## Step 4: (Optional) Add Additional Headers or Attachments

If you need to customize further—e.g., add a custom *X-Importance* header or attach files—use `message.getHeaders().add()` or `message.getAttachments().add()` respectively. This step is optional for the basic “send email with priority” scenario.

## Step 5: Send the Email

Configure the SMTP client with your server details and dispatch the message.

```java
// Create an instance of the SmtpClient class
SmtpClient client = new SmtpClient("smtp.example.com", 587, "username", "password");

// Send the email
client.send(message);
```

Replace `"smtp.example.com"`, `"username"`, and `"password"` with your actual SMTP credentials. If your server requires SSL/TLS, set `client.setEnableSsl(true);` before calling `send`.

## Common Issues and How to Fix Them

| Issue | Reason | Solution |
|-------|--------|----------|
| Email arrives without priority | SMTP server strips custom headers | Verify server allows custom headers or use `client.setUseDefaultCredentials(false);` |
| Recipient sees no visual cue | Client ignores *Importance* header | Ensure you set `MailPriority.High` (adds both *X-Priority* and *Importance*) |
| Authentication failure | Wrong credentials or port | Double‑check username, password, and port (usually 587 for TLS) |

## Frequently Asked Questions

**Q: How can I change the priority of an email to “Low”?**  
A: Use `message.setPriority(MailPriority.Low);` in the same way you set `High`.

**Q: Can I use Aspose.Email with other programming languages?**  
A: Yes. Aspose.Email is available for .NET, Python, Android, and more. Visit the Aspose website for the full list.

**Q: Is it possible to set both priority and importance for an email?**  
A: Absolutely. The `MailPriority` enum sets both headers simultaneously, ensuring maximum compatibility.

**Q: Are there any limitations to email importance headers?**  
A: Some email clients may ignore them or apply their own rules. Always test with the target client.

**Q: How do I handle email attachments with Aspose.Email?**  
A: Use the `Attachment` class, e.g., `message.getAttachments().addItem(new Attachment("file.pdf"));`. See the Aspose.Email documentation for advanced scenarios.

## Conclusion

By following these steps, you now know **how to send email with priority** and how to **set high priority email** headers using Aspose.Email for Java. Incorporating priority and importance headers can dramatically improve the visibility of critical communications, making your applications more effective and professional.

---

**Last Updated:** 2026-01-22  
**Tested With:** Aspose.Email for Java 23.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}