---
date: '2026-08-27'
description: Lär dig hur du laddar MSG-filer och konverterar dem till MHTML med Aspose.Email
  for Java, inklusive anpassade tidszonsinställningar och tips för batch-e-postbehandling.
keywords:
- how to load msg
- Aspose.Email Java
- convert MSG to MHTML
- email timezone offset
lastmod: '2026-08-27'
og_description: Lär dig hur du laddar msg-filer och exporterar dem som MHTML med Aspose.Email
  for Java. Inkluderar hantering av tidszoner och tips för batchbearbetning.
og_image_alt: Guide to loading MSG files and saving as MHTML with Aspose.Email for
  Java
og_title: Hur man laddar msg och sparar som MHTML med Aspose.Email for Java
schemas:
- author: Aspose
  dateModified: '2026-08-27'
  description: Learn how to load MSG files and convert them to MHTML with Aspose.Email
    for Java, including custom timezone settings and batch email processing tips.
  headline: How to load msg and save as MHTML using Aspose.Email for Java
  type: TechArticle
- description: Learn how to load MSG files and convert them to MHTML with Aspose.Email
    for Java, including custom timezone settings and batch email processing tips.
  name: How to load msg and save as MHTML using Aspose.Email for Java
  steps:
  - name: '**Reuse the license** – call `new License().setLicense(...)` once at application
      startup.'
    text: '**Reuse the license** – call `new License().setLicense(...)` once at application
      startup.'
  - name: '**Use try‑with‑resources** for automatic cleanup of streams.'
    text: '**Use try‑with‑resources** for automatic cleanup of streams.'
  - name: '**Log failures** to a separate file so you can retry problematic messages
      later.'
    text: '**Log failures** to a separate file so you can retry problematic messages
      later.'
  - name: '**Consider parallelism** with `ForkJoinPool` for large batches, but ensure
      each thread uses its own `MailMessage` instance.'
    text: '**Consider parallelism** with `ForkJoinPool` for large batches, but ensure
      each thread uses its own `MailMessage` instance.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Email supports EML, MHT, EMLX, and several other formats,
      totaling over 30 input types.
    question: Can I load emails from formats other than .msg?
  - answer: Use the streaming APIs (`MailMessage.load(InputStream, ...)`) to read
      and write data in chunks, which keeps memory consumption under 50 MB even for
      500‑page messages.
    question: How can I handle very large email files efficiently?
  - answer: Absolutely. You can add, remove, or replace attachments via the `msg.getAttachments()`
      collection, then call `save` to persist changes.
    question: Is it possible to modify attachments within a MailMessage?
  - answer: Pass a negative millisecond value to `setTimeZoneOffset`, e.g., `-3 *
      60 * 60 * 1000` for UTC‑3.
    question: What if my timezone offset is negative (behind UTC)?
  - answer: Yes, provided you have a valid commercial license. The free trial is limited
      to 20 MB per document.
    question: Can I use Aspose.Email in commercial projects?
  type: FAQPage
tags:
- email processing
- Aspose.Email
- Java email conversion
title: Hur man laddar msg och sparar som MHTML med Aspose.Email for Java
url: /sv/java/email-message-operations/load-save-emails-mhtml-aspose-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man laddar msg och sparar som MHTML med Aspose.Email för Java

## Introduktion

Om du behöver **how to load msg**-filer, justera deras tidsstämplar och sedan **convert msg to mhtml**, är du på rätt plats. I den här handledningen går vi igenom hur man laddar ett `.msg`‑e‑postmeddelande, applicerar en anpassad tidszonsförskjutning och sparar resultatet som ett MHTML‑arkiv – allt med Aspose.Email för Java. Oavsett om du hanterar ett enskilt meddelande eller en **batch email processing**‑pipeline, ger dessa steg dig en solid grund för pålitlig arkivering och migrering.

**Vad du kommer att lära dig**
- Hur man laddar en `MailMessage` från en `.msg`‑fil.
- Hur man ställer in en anpassad tidszon och aktuellt datum.
- Hur man sparar meddelandet som MHTML med exakt formatering.
- Tips för att skala tillvägagångssättet för batch‑scenarier.

Redo att förbättra ditt e‑postflöde? Låt oss först förbereda miljön.

## Snabba svar
- **Vad är det primära biblioteket?** Aspose.Email for Java.
- **Kan jag ladda MSG och exportera till MHTML i ett steg?** No, you load, adjust, then save.
- **Behöver jag en licens för produktion?** Yes, a valid Aspose.Email license is required.
- **Stöds tidszons‑hantering?** Yes, via `setTimeZoneOffset`.
- **Kan detta användas i batch‑bearbetning?** Absolutely – wrap the steps in a loop.

## Vad är Aspose.Email för Java?

Aspose.Email för Java är ett omfattande API som låter dig skapa, läsa, konvertera och manipulera e‑postmeddelanden utan att kräva Microsoft Outlook. Det stödjer mer än 30 e‑postformat och kan bearbeta meddelanden på flera hundra sidor samtidigt som minnesanvändningen hålls låg.

## Varför konvertera MSG till MHTML?

Att konvertera MSG‑filer till MHTML ger dig en webbvänlig, en‑fil‑representation som kan öppnas i vilken modern webbläsare som helst. Detta format bevarar originalstil, inbäddade bilder och bilagor, vilket gör det idealiskt för **legal archiving**, **cross‑platform sharing** och **embedding emails into web pages or documentation**.

## Förutsättningar

Innan vi börjar, se till att du har följande:

### Nödvändiga bibliotek och beroenden
- **Aspose.Email for Java**‑bibliotek version 25.4 (jdk16‑klassificering) – biblioteket stödjer **50+** in‑ och utdata‑e‑postformat.
- Grundläggande Java‑kunskaper.
- En IDE såsom IntelliJ IDEA eller Eclipse.

### Krav för miljöinställning
- JDK 16 eller nyare installerat.
- Maven för beroendehantering.

## Installera Aspose.Email för Java

För att lägga till biblioteket i ett Maven‑projekt, inkludera följande beroende:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Steg för att skaffa licens

Börja med en **free trial** eller skaffa en **temporary license** för att utvärdera bibliotekets fulla funktioner utan begränsningar. För långsiktig användning, överväg att köpa en licens:

- [Free Trial](https://releases.aspose.com/email/java/)
- [Temporary License](https://purchase.aspose.com/temporary-license/)
- [Purchase License](https://purchase.aspose.com/buy)

### Grundläggande initiering

`License`‑klassen registrerar din Aspose.Email‑licens för att låsa upp alla funktioner.
Efter att ha lagt till beroendet, initiera licensen i din Java‑kod:

```java
import com.aspose.email.License;

License license = new License();
license.setLicense("Aspose.Email.lic");
```
```java
import com.aspose.email.License;

License license = new License();
license.setLicense("path_to_your_license_file.lic");
```

## Hur man laddar msg och sparar som MHTML?

Ladda MSG‑filen, justera tidsstämpeln och spara den som MHTML i tre enkla steg. Först, skapa en `MailMessage` från MSG‑filen med `MsgLoadOptions`. Därefter, ange önskad tidszonsförskjutning med `setTimeZoneOffset`. Slutligen, konfigurera `MhtSaveOptions` och anropa `save` för att skapa MHTML‑arkivet.

### Funktion 1: ladda en MailMessage från en fil

`MailMessage`‑klassen representerar ett e‑postmeddelande med rubriker, kropp och bilagor.

```java
import com.aspose.email.MailMessage;
import com.aspose.email.MsgLoadOptions;
```
```java
import com.aspose.email.MailMessage;
import com.aspose.email.MsgLoadOptions;
```

```java
MsgLoadOptions loadOptions = new MsgLoadOptions();
MailMessage msg = MailMessage.load("sample.msg", loadOptions);
```
```java
String filename = "YOUR_DOCUMENT_DIRECTORY/MSG file with RTF Formatting.msg";
MailMessage msg = MailMessage.load(filename, new MsgLoadOptions());
```

`MsgLoadOptions` låter dig styra hur MSG‑filen parsas; standardinställningarna fungerar för de flesta scenarier.

### Funktion 2: ställa in aktuellt datum och anpassad tidszonsförskjutning

`Date`‑objektet innehåller tidsstämpeln som kommer att skrivas till e‑postens **Date**‑rubrik.

```java
java.util.Date now = new java.util.Date();
msg.setDate(now);
```
```java
import java.util.Date;

msg.setDate(new Date());
```

Förskjutningen uttrycks i millisekunder; för UTC+5 skickar du `5 * 60 * 60 * 1000`.

```java
int utcPlusFive = 5 * 60 * 60 * 1000;
msg.setTimeZoneOffset(utcPlusFive);
```
```java
msg.setTimeZoneOffset(5 * 60 * 60 * 1000); // 5 hours ahead of UTC in milliseconds.
```

### Funktion 3: spara en MailMessage som en MHTML‑fil

`MhtSaveOptions` definierar hur e‑posten paketeras till ett MHTML‑arkiv, med bevarande av inbäddade bilder och bilagor.

```java
import com.aspose.email.MhtSaveOptions;
MhtSaveOptions saveOptions = new MhtSaveOptions();
saveOptions.setWriteHeader(true);
```
```java
import com.aspose.email.MhtSaveOptions;
import com.aspose.email.MhtFormatOptions;

MhtSaveOptions mhtOptions = new MhtSaveOptions();
mhtOptions.setMhtFormatOptions(MhtFormatOptions.WriteHeader);
```

```java
msg.save("output.mhtml", saveOptions);
```
```java
msg.save("YOUR_OUTPUT_DIRECTORY/ExportToMHTWithCustomTimezone_out.mhtml", mhtOptions);
```

Den resulterande `.mhtml`‑filen behåller den ursprungliga formateringen, bilderna och bilagorna, vilket gör den till en trogen visuell kopia av den ursprungliga MSG‑filen.

## Hur man ställer in en anpassad tidszonsförskjutning?

Du kan ändra tidszonen genom att anropa `setTimeZoneOffset` på `MailMessage`‑instansen. Metoden förväntar sig en förskjutning i millisekunder, vilket tillåter både positiva (öst om UTC) och negativa (väst om UTC) värden. Till exempel är UTC‑3 `-3 * 60 * 60 * 1000`.

## Hur man bearbetar MSG‑filer i batch?

Packa in det trestegs‑arbetsflödet i en loop som itererar över en katalog med `.msg`‑filer. Återanvänd en enda `License`‑instans för att undvika upprepad I/O, och avlossa varje `MailMessage` efter sparning för att hålla minnesanvändningen låg.

```java
File folder = new File("msg_folder");
for (File file : folder.listFiles((dir, name) -> name.toLowerCase().endsWith(".msg"))) {
    MailMessage msg = MailMessage.load(file.getAbsolutePath(), new MsgLoadOptions());
    // set date & timezone as shown earlier
    msg.save(file.getName().replace(".msg", ".mhtml"), new MhtSaveOptions());
    msg.dispose(); // releases native resources
}
```

### Tips för batch‑bearbetning
1. **Reuse the license** – anropa `new License().setLicense(...)` en gång vid applikationens start.
2. **Use try‑with‑resources** för automatisk rensning av strömmar.
3. **Log failures** till en separat fil så att du kan försöka igen med problematiska meddelanden senare.
4. **Consider parallelism** med `ForkJoinPool` för stora batcher, men se till att varje tråd använder sin egen `MailMessage`‑instans.

## Vanliga problem och lösningar

- **Memory spikes with huge MSG files** – aktivera streaming genom att använda `MailMessage.load(InputStream, MsgLoadOptions)` och bearbeta strömmen i delar.
- **Incorrect timestamps** – verifiera att systemklockan är inställd på UTC innan förskjutningar appliceras, eller skicka explicit en `java.util.Calendar`‑instans.
- **Missing attachments in MHTML** – säkerställ `MhtSaveOptions.setWriteHeader(true)`; detta bäddar in bilagor som `cid:`‑resurser.

## Vanliga frågor

**Q: Kan jag ladda e‑post från andra format än .msg?**  
A: Ja, Aspose.Email stödjer EML, MHT, EMLX och flera andra format, totalt över 30 indata‑typer.

**Q: Hur kan jag hantera mycket stora e‑postfiler effektivt?**  
A: Använd streaming‑API:erna (`MailMessage.load(InputStream, ...)`) för att läsa och skriva data i delar, vilket håller minnesförbrukningen under 50 MB även för meddelanden på 500 sidor.

**Q: Är det möjligt att ändra bilagor i en MailMessage?**  
A: Absolut. Du kan lägga till, ta bort eller ersätta bilagor via samlingen `msg.getAttachments()`, och sedan anropa `save` för att spara ändringarna.

**Q: Vad händer om min tidszonsförskjutning är negativ (bakom UTC)?**  
A: Skicka ett negativt millisekundvärde till `setTimeZoneOffset`, t.ex. `-3 * 60 * 60 * 1000` för UTC‑3.

**Q: Kan jag använda Aspose.Email i kommersiella projekt?**  
A: Ja, förutsatt att du har en giltig kommersiell licens. Gratisprovet är begränsat till 20 MB per dokument.

**Q: Hur bearbetar jag tusentals MSG‑filer utan att få slut på minne?**  
A: Bearbeta filer i batcher, frigör varje `MailMessage` efter sparning, och använd Javas `try‑with‑resources`‑mönster för automatisk rensning.

## Resurser
- [documentation](https://reference.aspose.com/email/java/)
- [Documentation](https://reference.aspose.com/email/java/)
- [Download Library](https://releases.aspose.com/email/java/)
- [Purchase License](https://purchase.aspose.com/buy)
- [Free Trial](https://releases.aspose.com/email/java/)
- [Temporary License](https://purchase.aspose.com/temporary-license/)
- [Support Forum](https://forum.aspose.com/c/email/10)

---

**Senast uppdaterad:** 2026-08-27  
**Testat med:** Aspose.Email for Java 25.4 (jdk16 classifier)  
**Författare:** Aspose

## Relaterade handledningar

- [How to Load and Parse Outlook MSG Files Using Aspose.Email for Java: A Comprehensive Guide](/email/java/mapi-operations/outlook-msg-aspose-email-java-guide/)
- [Maven Aspose.Email for Java: Save Emails as MHT Files](/email/java/email-message-operations/save-emails-as-mht-using-aspose-email-java/)
- [How to extract attachments from msg files using Aspose.Email for Java](/email/java/advanced-email-attachments/extracting-attachments-from-email-messages/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}