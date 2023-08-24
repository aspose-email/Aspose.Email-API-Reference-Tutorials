---
title: Hämta leveransstatusmeddelanden med C#
linktitle: Hämta leveransstatusmeddelanden med C#
second_title: Aspose.Email .NET Email Processing API
description: Lär dig hur du hämtar e-postmeddelanden om leveransstatus med C# och Aspose.Email för .NET.
type: docs
weight: 18
url: /sv/net/email-processing-and-analysis/retrieving-delivery-status-notifications-with-csharp/
---

## Introduktion

e-postkommunikation spelar leveransstatusmeddelanden (DSN) en avgörande roll för att informera avsändare om leveransstatus för deras e-postmeddelanden. Aspose.Email för .NET är ett kraftfullt bibliotek som tillhandahåller funktioner för att arbeta med e-post, inklusive hämtning av DSN. I den här guiden går vi igenom processen för att hämta leveransstatusmeddelanden med C# och Aspose.Email för .NET-biblioteket.

## Förutsättningar

Innan du börjar, se till att du har följande förutsättningar:

1. Visual Studio installerat.
2.  Aspose.Email för .NET-biblioteket. Du kan ladda ner den från[här](https://releases.aspose.com/email/net).
3. Grundläggande förståelse för C#-programmering.

## Steg

Följ dessa steg för att hämta leveransstatusmeddelanden med Aspose.Email för .NET:

### Steg 1: Skapa ett nytt projekt

Öppna Visual Studio och skapa ett nytt C#-konsolapplikationsprojekt.

### Steg 2: Lägg till Aspose.Email-referens

Kopiera den nedladdade Aspose.Email DLL till ditt projekts katalog. Högerklicka sedan på projektet i Solution Explorer, välj "Lägg till" > "Referens" och bläddra efter Aspose.Email DLL. Klicka på "OK" för att lägga till referensen till ditt projekt.

### Steg 3: Skriv kod för att hämta DSN:er

 Öppna`Program.cs` fil i ditt projekt och importera de nödvändiga namnrymden:

```csharp
using Aspose.Email;
using Aspose.Email.Imap;
using Aspose.Email.Mail;
```

 Inuti`Main` metod, skriv koden för att ansluta till e-postservern, hämta DSN:er och bearbeta dem:

```csharp
class Program
{
    static void Main(string[] args)
    {
        // Ställ in dina IMAP-serveruppgifter och värd
        string host = "your_imap_host";
        int port = 993;
        string username = "your_email";
        string password = "your_password";

        using (ImapClient client = new ImapClient(host, port, username, password))
        {
            // Välj mappen Inkorg
            client.SelectFolder(ImapFolderInfo.InBox);

            // Sök efter meddelanden med DSN
            MailQueryBuilder queryBuilder = new MailQueryBuilder();
            queryBuilder.HasFlags(Aspose.Email.Mail.MessageFlags.DeliveryNotification);
            MailQuery query = queryBuilder.GetQuery();
            ImapMessageInfoCollection messages = client.ListMessages(query);

            // Bearbeta hämtade DSN:er
            foreach (ImapMessageInfo messageInfo in messages)
            {
                MailMessage message = client.FetchMessage(messageInfo.SequenceNumber);

                // Bearbeta DSN-detaljer
                Console.WriteLine("Subject: " + message.Subject);
                Console.WriteLine("From: " + message.From);
                // ... Bearbeta andra DSN-detaljer

                // Markera meddelandet som läst eller ta bort det
                client.DeleteMessage(messageInfo.SequenceNumber);
            }
        }
    }
}
```

 Byta ut`"your_imap_host"`, `"your_email"` , och`"your_password"` med din faktiska IMAP-serverinformation.

### Steg 4: Kör applikationen

Bygg och kör din applikation. Den kommer att ansluta till din e-postserver, hämta DSN:er från mappen Inkorg, bearbeta deras uppgifter och eventuellt radera dem eller markera dem som lästa.

## Vanliga frågor

### Hur hittar jag IMAP-servervärden?

 Du kan hitta IMAP-servervärden från din e-postleverantörs dokumentation eller inställningar. Det är vanligtvis i formatet`imap.yourdomain.com`.

### Hur kan jag behandla andra DSN-uppgifter än ämne och avsändare?

 Du kan komma åt olika egenskaper hos`MailMessage` objekt för att hämta DSN-detaljer som mottagaradresser, leveransstatus, tidsstämpel och mer. Referera till[Aspose.Email dokumentation](https://reference.aspose.com/email/net/) för mer information.

### Är det nödvändigt att ta bort eller markera DSN som lästa?

Nej, det är inte nödvändigt. Om du vill ta bort eller markera DSN:er som lästa beror på din applikations krav. Den medföljande koden visar båda alternativen, men du kan anpassa den efter dina behov.

## Slutsats

Att hämta leveransstatusmeddelanden med C# och Aspose.Email för .NET är en enkel process. Aspose.Email-biblioteket förenklar kommunikationen med IMAP-servern och tillhandahåller lättanvända API:er för att behandla e-postmeddelanden. Med den här guiden kan du nu införliva DSN-hämtningsfunktionalitet i dina C#-applikationer.