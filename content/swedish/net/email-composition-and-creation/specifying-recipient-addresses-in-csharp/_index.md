---
title: Ange mottagaradresser i C#
linktitle: Ange mottagaradresser i C#
second_title: Aspose.Email .NET Email Processing API
description: Lär dig hur du anger mottagaradresser i C# med Aspose.Email för .NET. Skapa, konfigurera och skicka e-post effektivt.
type: docs
weight: 19
url: /sv/net/email-composition-and-creation/specifying-recipient-addresses-in-csharp/
---


Den här guiden leder dig genom processen att ange mottagaradresser i C# med hjälp av Aspose.Email for .NET-biblioteket. Aspose.Email är ett kraftfullt .NET API som låter dig arbeta med e-postmeddelanden och olika e-postrelaterade uppgifter. I den här handledningen kommer vi att täcka hur man lägger till mottagaradresser i ett e-postmeddelande med hjälp av biblioteket.

## Förutsättningar

Innan du börjar, se till att du har följande:

1. Visual Studio eller någon C#-utvecklingsmiljö installerad.
2. Aspose.Email för .NET-biblioteket. Du kan få det från[Aspose.Email för .NET-versioner](https://releases.aspose.com/email/net/).

## Steg

Följ dessa steg för att ange mottagaradresser i C# med Aspose.Email för .NET:

### 1. Skapa ett nytt C#-projekt

Börja med att skapa ett nytt C#-projekt i din utvecklingsmiljö.

### 2. Lägg till referens till Aspose.Email

1. Ladda ner och installera Aspose.Email for .NET-biblioteket om du inte redan har gjort det.
2. Öppna ditt C#-projekt.
3. Högerklicka på "Referenser" i Solution Explorer och välj "Lägg till referens".
4. Bläddra och välj Aspose.Email DLL-filerna som du laddade ner.

### 3. Importera nödvändiga namnrymder

I din C#-kodfil, importera de nödvändiga namnrymden för att använda Aspose.Email-klasser:

```csharp
using Aspose.Email;
using Aspose.Email.Mail;
```

### 4. Skapa och konfigurera e-postmeddelandet

 Skapa en ny instans av`MailMessage` klass för att representera ditt e-postmeddelande. Konfigurera avsändaren och ämnet för e-postmeddelandet:

```csharp
MailMessage message = new MailMessage();
message.From = new MailAddress("sender@example.com");
message.Subject = "Hello from Aspose.Email";
```

### 5. Lägg till mottagaradresser

Du kan lägga till mottagaradresser med hjälp av`To`, `Cc` , och`Bcc` egenskaper hos`MailMessage` klass. Så här kan du lägga till mottagaradresser:

```csharp
message.To.Add(new MailAddress("recipient1@example.com"));
message.Cc.Add(new MailAddress("recipient2@example.com"));
message.Bcc.Add(new MailAddress("recipient3@example.com"));
```

### 6. Fyll i e-postmeddelandet

Lägg till e-posttexten och allt annat nödvändigt innehåll i ditt e-postmeddelande:

```csharp
message.Body = "This is the email body.";
```

### 7. Skicka e-postmeddelandet

 För att skicka e-postmeddelandet kan du använda`SmtpClient` klass tillhandahållen av Aspose.Email. Konfigurera SMTP-serverinställningarna och skicka e-postmeddelandet:

```csharp
SmtpClient client = new SmtpClient("smtp.example.com", 587, "your_username", "your_password");
client.SecurityOptions = SecurityOptions.Auto;

client.Send(message);
```

## Vanliga frågor

###  Hur kan jag lägga till flera mottagare till`To`, `Cc`, or `Bcc` fields?

 Du kan lägga till flera mottagare genom att ringa`Add` metod flera gånger på respektive`MailAddressCollection`:

```csharp
message.To.Add(new MailAddress("recipient1@example.com"));
message.To.Add(new MailAddress("recipient2@example.com"));
```

### Kan jag ange mottagarnamn tillsammans med deras e-postadresser?

Ja, du kan ange både mottagarens namn och e-postadress när du lägger till mottagare:

```csharp
message.To.Add(new MailAddress("recipient@example.com", "Recipient Name"));
```

### Hur hanterar jag undantag när jag skickar ett e-postmeddelande?

Du kan använda try-catch-block för att hantera undantag som kan inträffa under e-postsändning:

```csharp
try
{
    client.Send(message);
    Console.WriteLine("Email sent successfully.");
}
catch (Exception ex)
{
    Console.WriteLine($"An error occurred: {ex.Message}");
}
```

 För mer information och avancerade funktioner i Aspose.Email för .NET, se[Aspose API-referenser](https://reference.aspose.com/email/net/).

Detta avslutar guiden om att ange mottagaradresser i C# med Aspose.Email för .NET. Du har lärt dig hur du skapar ett e-postmeddelande, lägger till mottagaradresser och skickar e-postmeddelandet med hjälp av bibliotekets funktioner.