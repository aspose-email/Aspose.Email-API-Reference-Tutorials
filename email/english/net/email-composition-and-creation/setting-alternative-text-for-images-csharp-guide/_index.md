---
title: Setting Alternative Text for Images - C# Guide
linktitle: Setting Alternative Text for Images - C# Guide
second_title: Aspose.Email .NET Email Processing API
description: Learn to set alternative text for images in emails using Aspose.Email for .NET. Ensure accessibility with clear alt text. Documentation and code included.
weight: 15
url: /net/email-composition-and-creation/setting-alternative-text-for-images-csharp-guide/
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Setting Alternative Text for Images - C# Guide


This guide will walk you through the process of setting alternative text for images in emails using Aspose.Email for .NET. Alternative text, also known as "alt text," is used to provide a textual description of an image in case the image cannot be displayed. Aspose.Email for .NET is a powerful library that allows you to work with emails and attachments in various formats. In this guide, we will focus on setting alternative text for images in email messages using C#.

## Prerequisites

Before you begin, make sure you have the following prerequisites:

1. Visual Studio or any compatible C# development environment installed.
2. Aspose.Email for .NET library. You can use NuGet Package Manager in Visual Studio.

## Step 1: Create a New Project

1. Launch Visual Studio and create a new C# console application project.

## Step 2: Install Aspose.Email via NuGet

1. Right-click on your project in the Solution Explorer and select "Manage NuGet Packages."
2. Search for "Aspose.Email" and install the latest version of the package.

## Step 3: Add Using Statements

```csharp

using Aspose.Email.Mime;
```

## Step 4: Load and Modify the Email Message

1. Load the email message using the `MailMessage` class:

```csharp
MailMessage message = new MailMessage();
message.Subject = "Sample Email with Alternative Text";
message.From = new MailAddress("sender@example.com");
message.To.Add("recipient@example.com");
```

3. Load the HTML content of the email message:

```csharp
var htmlView = AlternateView.CreateAlternateViewFromString("<html><body><img src='cid:logo.jpg' alt='Company Logo'></body></html>", null, "text/html");
```

## Step 5: Add AlternativeView for Alternative Text to Images

Add htmlview for Alternative Text to Image as AlternateView into message. 
```csharp
message.AlternateViews.Add(htmlView);
```

## Step 6: Save and Send the Email

1. Save the modified message to a file or send it using your desired method:

```csharp
message.Save("output.eml", SaveOptions.DefaultEml);
```

## Conclusion

In this guide, you learned how to set alternative text for images in email messages using Aspose.Email for .NET. By following the steps outlined above, you can ensure that your email content remains accessible and informative even when images cannot be displayed.

## FAQ

## How can I download the Aspose.Email library?

You can download the Aspose.Email library from the Aspose Releases or install it via NuGet Package Manager in Visual Studio.

### How do I add images as linked resources in an email?

To add images as linked resources in an email, you can use the `LinkedResource` class. Assign a content ID to the linked resource, and then reference this content ID in the HTML body using the `cid:` scheme. For detailed information, see the [LinkedResource documentation](https://reference.aspose.com/email/net/aspose.email/linkedresource/).
### Where can I find more documentation on Aspose.Email for .NET?

You can find more detailed documentation, tutorials, and examples on working with Aspose.Email for .NET in the [API Reference](https://reference.aspose.com/email/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
