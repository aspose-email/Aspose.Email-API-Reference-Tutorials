---
"description": "Lär dig hur du anger mottagaradresser i C# med Aspose.Email för .NET. Skapa, konfigurera och skicka e-postmeddelanden effektivt."
"linktitle": "Ange mottagaradresser i C#"
"second_title": "Aspose.Email .NET e-postbehandlings-API"
"title": "Ange mottagaradresser i C#"
"url": "/sv/net/email-composition-and-creation/specifying-recipient-addresses-in-csharp/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Ange mottagaradresser i C#



Den här guiden guidar dig genom processen att ange mottagaradresser i C# med hjälp av biblioteket Aspose.Email för .NET. Aspose.Email är ett kraftfullt .NET API som låter dig arbeta med e-postmeddelanden och olika e-postrelaterade uppgifter. I den här handledningen går vi igenom hur du lägger till mottagaradresser i ett e-postmeddelande med hjälp av biblioteket.

## Förkunskapskrav

Innan du börjar, se till att du har följande:

1. Visual Studio eller annan C#-utvecklingsmiljö installerad.
2. Aspose.Email för .NET-biblioteket. Du kan hämta det från [Aspose.Email för .NET-utgåvor](https://releases.aspose.com/email/net/).

## Steg

Följ dessa steg för att ange mottagaradresser i C# med Aspose.Email för .NET:

### 1. Skapa ett nytt C#-projekt

Börja med att skapa ett nytt C#-projekt i din utvecklingsmiljö.

### 2. Lägg till referens till Aspose.Email

1. Ladda ner och installera Aspose.Email för .NET-biblioteket om du inte redan har gjort det.
2. Öppna ditt C#-projekt.
3. Högerklicka på "Referenser" i lösningsutforskaren och välj "Lägg till referens".
4. Bläddra och välj Aspose.Email DLL-filerna som du laddade ner.

### 3. Importera nödvändiga namnrymder

Importera de namnrymder som behövs för att använda Aspose.Email-klasser i din C#-kodfil:

```csharp
using Aspose.Email;

```

### 4. Skapa och konfigurera e-postmeddelandet

Skapa en ny instans av `MailMessage` klassen för att representera ditt e-postmeddelande. Konfigurera avsändaren och ämnet för e-postmeddelandet:

```csharp
MailMessage message = new MailMessage();
message.From = new MailAddress("sender@example.com");
message.Subject = "Hello from Aspose.Email";
```

### 5. Lägg till mottagaradresser

Du kan lägga till mottagaradresser med hjälp av `To`, `Cc`och `Bcc` egenskaper hos `MailMessage` klass. Så här kan du lägga till mottagaradresser:

```csharp
message.To.Add(new MailAddress("recipient1@example.com"));
message.Cc.Add(new MailAddress("recipient2@example.com"));
message.Bcc.Add(new MailAddress("recipient3@example.com"));
```

### 6. Slutför e-postmeddelandet

Lägg till e-postmeddelandets brödtext och annat nödvändigt innehåll i ditt e-postmeddelande:

```csharp
message.Body = "This is the email body.";
```

### 7. Skicka e-postmeddelandet

För att skicka e-postmeddelandet kan du använda `SmtpClient` klassen som tillhandahålls av Aspose.Email. Konfigurera SMTP-serverinställningarna och skicka e-postmeddelandet:

```csharp
SmtpClient client = new SmtpClient("smtp.example.com", 587, "your_username", "your_password");
client.SecurityOptions = SecurityOptions.Auto;

client.Send(message);
```

## Vanliga frågor

### Hur kan jag lägga till flera mottagare till `To`, `Cc`, eller `Bcc` fält?

Du kan lägga till flera mottagare genom att ringa `Add` metoden flera gånger på respektive `MailAddressCollection`:

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

Du kan använda try-catch-block för att hantera undantag som kan uppstå vid e-postutskick:

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

För mer information och avancerade funktioner i Aspose.Email för .NET, se [Aspose API-referenser](https://reference.aspose.com/email/net/).

Detta avslutar guiden om hur man anger mottagaradresser i C# med hjälp av Aspose.Email för .NET. Du har lärt dig hur man skapar ett e-postmeddelande, lägger till mottagaradresser och skickar e-postmeddelandet med hjälp av bibliotekets funktioner.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}