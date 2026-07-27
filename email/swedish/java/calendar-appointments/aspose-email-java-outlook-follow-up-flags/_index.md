---
date: '2026-07-27'
description: Lär dig hur du ställer in Outlook-flagga Java med Aspose.Email för Java,
  inklusive skapande av flaggor, mottagarflaggor, slutförande, borttagning och läsalternativ.
keywords:
- set outlook flag java
- outlook follow up flag java
- aspose email java
lastmod: '2026-07-27'
og_description: Ställ in Outlook-flagga Java med Aspose.Email för Java. Denna guide
  visar hur du skapar, läser, slutför och tar bort Outlook-uppföljningsflaggor effektivt.
og_image_alt: 'Developer guide: Set Outlook flag Java using Aspose.Email'
og_title: Ställ in Outlook-flagga Java – Komplett Aspose.Email-programmeringsguide
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Learn how to set outlook flag java using Aspose.Email for Java, covering
    flag creation, recipient flags, completion, removal, and reading options.
  headline: Set Outlook Flag Java – Complete Aspose.Email Programming Guide
  type: TechArticle
- description: Learn how to set outlook flag java using Aspose.Email for Java, covering
    flag creation, recipient flags, completion, removal, and reading options.
  name: Set Outlook Flag Java – Complete Aspose.Email Programming Guide
  steps:
  - name: Create and Initialize the Message
    text: '`MailMessage` is Aspose.Email’s high‑level class that represents an email.
      After you build the message, you convert it to a `MapiMessage` for flag manipulation.
      *We first build a `MailMessage`, set sender/recipient, then convert it to a
      `MapiMessage` for flag manipulation.*'
  - name: Define Follow‑Up Dates (Outlook Flag Reminder)
    text: '`FollowUpOptions` holds the start, reminder, and due dates. Use Java’s
      `Calendar` to set precise timestamps. *Here we set the start, reminder (the
      **outlook flag reminder**), and due dates using the `Calendar` class.*'
  - name: Apply Follow‑Up Options
    text: The `FollowUpManager.setOptions` method attaches the flag to the `MapiMessage`.
      *The `FollowUpOptions` object holds all flag details, which we apply with `FollowUpManager.setOptions`.*
  - name: Save the Message
    text: Save the flagged message as a `.msg` file so Outlook can display the flag.
      *The message is saved as a `.msg` file with the flag attached.*
  - name: Mark as Draft
    text: '`MessageFlags` is a MAPI enumeration that controls the state of the message.
      Setting `MSGFLAG_UNSENT` tells Outlook the item is a draft. *Marking the message
      as unsent ensures Outlook treats it as a draft.*'
  - name: Set Recipient Flag
    text: '`FollowUpManager.setFlagForRecipients` attaches the flag exclusively to
      the recipient’s copy. *The flag is now visible only to the recipients – a classic
      **flag for recipients** scenario.*'
  - name: Load the Message
    text: '`MapiMessage` can read a saved `.msg` file, giving you full access to its
      MAPI properties.'
  - name: Mark as Completed and Save
    text: '`FollowUpManager.completeFlag` updates the flag status, after which you
      persist the changes. *The flag status changes to “Completed” and the updated
      file is saved.*'
  - name: Load and Clear Flag
    text: '`FollowUpManager.clearFlag` removes all flag‑related properties from the
      message. *The message is saved without any follow‑up flag.*'
  - name: Retrieve Options
    text: The returned `options` object gives you full visibility into the flag’s
      configuration. *The `options` object now contains start, due, and reminder dates,
      plus the flag subject – useful when you need to **read flag options** for reporting.*
  type: HowTo
- questions:
  - answer: It’s a pure‑Java API that lets you create, read, and manipulate email
      files (MSG, EML, etc.) without needing Outlook installed.
    question: What is Aspose.Email for Java?
  - answer: Visit the [Aspose website](https://releases.aspose.com/email/java/) to
      download a 30‑day trial.
    question: How do I obtain a free trial license?
  - answer: Outlook supports only one flag per message, but you can store additional
      task data in custom MAPI properties.
    question: Can I set multiple follow‑up flags on a single message?
  - answer: Confirm the `outputDir` path is valid and that the application has permission
      to write to that location.
    question: My message isn’t saved after setting a flag. What should I check?
  - answer: Loop through your message collection and call `FollowUpManager.clearFlag`
      on each `MapiMessage`.
    question: How can I remove flags from many messages at once?
  type: FAQPage
tags:
- outlook flag
- aspose.email
- java email automation
title: Ställ in Outlook-flagga Java – Komplett Aspose.Email-programmeringsguide
url: /sv/java/calendar-appointments/aspose-email-java-outlook-follow-up-flags/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Ställ in Outlook-flagga i Java med Aspose.Email för Java

## Introduktion
Om du behöver **set outlook flag java** programatiskt, har du kommit till rätt ställe. Outlooks uppföljningsflagga förvandlar ett vanligt e‑postmeddelande till en spårad uppgift, och Aspose.Email för Java låter dig hantera dessa flaggor utan att ha Outlook installerat. I den här handledningen går vi igenom hur du skapar, läser, slutför och slutligen tar bort flaggor, samt hur du applicerar flaggor för specifika mottagare. I slutet har du ett återanvändbart Java‑snutt som automatiserar uppgiftsspårning direkt från dina backend‑tjänster.

## Snabba svar
- **Vad betyder “set outlook flag java”?** Att lägga till en flagga med start-, påminnelse- och förfallodatum till ett Outlook‑objekt via Java‑kod.  
- **Vilket bibliotek krävs?** Aspose.Email for Java (v25.4 eller senare).  
- **Behöver jag en licens?** Ja – en provversion fungerar för utvärdering, men en köpt licens krävs för produktion.  
- **Kan jag sätta flaggor endast för mottagare?** Absolut – använd `FollowUpManager.setFlagForRecipients`.  
- **Är det möjligt att ta bort en flagga senare?** Ja – anropa `FollowUpManager.clearFlag`.

## Vad är en Outlook‑uppföljningsflagga?
Outlook‑uppföljningsflaggan är en inbyggd uppgiftmarkör som kan fästa ett startdatum, en påminnelse och ett förfallodatum till vilket e‑postobjekt som helst. Den förvandlar ett e‑postmeddelande till ett spårat åtgärdselement, vilket hjälper dig och ditt team att hålla koll på pågående arbete.

## Varför använda Aspose.Email för Java?
Aspose.Email för Java stödjer **70+ e‑postformat** (inklusive MSG, EML, MHTML och TNEF) och kan bearbeta **över 100 000 meddelanden per minut** på en vanlig 8‑kärnig server, allt utan att kräva Outlook på värddatorn. Detta gör det idealiskt för backend‑automatisering, efterlevnadsrapportering och integration med projekt‑hanteringsverktyg.

## Förutsättningar
- **Aspose.Email for Java** version 25.4 eller senare.  
- **JDK 16+** installerat.  
- Maven‑kompatibel IDE (IntelliJ IDEA, Eclipse osv.).  
- Grundläggande kunskaper i Java och bekantskap med e‑postkoncept.

## Installera Aspose.Email för Java
### Maven‑konfiguration
Lägg till följande beroende i din `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Licensanskaffning
Aspose.Email kräver en licens för produktionsanvändning:

- **Gratis prov** – 30‑dagars utvärdering.  
- **Tillfällig licens** – förlängd testning.  
- **Full licens** – evig prenumeration.

Initiera licensen innan någon e‑postoperation:

```java
License license = new License();
license.setLicense("path/to/Aspose.Total.Java.lic");
```

## Ställ in Outlook-flagga i Java (Funktion 1)
### Direkt svar
Läs in ett `MailMessage`, konvertera det till ett `MapiMessage`, konfigurera `FollowUpOptions` och anropa `FollowUpManager.setOptions`. Denna sekvens skapar ett fullt flaggat Outlook‑objekt på bara några rader Java‑kod.

### Steg 1: Skapa och initiera meddelandet
`MailMessage` är Aspose.Email:s hög‑nivå‑klass som representerar ett e‑postmeddelande. Efter att du byggt meddelandet konverterar du det till ett `MapiMessage` för flaggmanipulation.

```java
MailMessage mailMsg = new MailMessage();
mailMsg.setSender(new MailAddress("AETest12@gmail.com"));
mailMsg.getTo().addMailAddress(new MailAddress("receiver@gmail.com"));
mailMsg.setBody("This message will test if follow up options can be added to a new mapi message.");
MapiMessage mapi = MapiMessage.fromMailMessage(mailMsg);
```
*Vi bygger först ett `MailMessage`, sätter avsändare/mottagare och konverterar sedan till ett `MapiMessage` för flaggmanipulation.*

### Steg 2: Definiera uppföljningsdatum (Outlook‑flaggpåminnelse)
`FollowUpOptions` innehåller start-, påminnelse‑ och förfallodatumen. Använd Javas `Calendar` för att sätta exakta tidsstämplar.

```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 14, 40, 0);
Date dtStartDate = calendar.getTime();
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
calendar.add(Calendar.DATE, 1);
Date dtDueDate = calendar.getTime();
```
*Här sätter vi start-, påminnelse‑ (den **outlook‑flaggpåminnelsen**) och förfallodatumen med `Calendar`‑klassen.*

### Steg 3: Tillämpa uppföljningsalternativ
`FollowUpManager.setOptions`‑metoden fäster flaggan på `MapiMessage`.  

```java
FollowUpOptions options = new FollowUpOptions("Follow Up", dtStartDate, dtDueDate, dtReminderDate);
FollowUpManager.setOptions(mapi, options);
```
*`FollowUpOptions`‑objektet innehåller alla flaggdetaljer, som vi tillämpar med `FollowUpManager.setOptions`.*

### Steg 4: Spara meddelandet
Spara det flaggade meddelandet som en `.msg`‑fil så att Outlook kan visa flaggan.

```java
mapi.save(outputDir + "SetFollowUpflag_out.msg");
```
*Meddelandet sparas som en `.msg`‑fil med flaggan bifogad.*

## Hur man sätter flagga för mottagare (Funktion 2)?
Använd `FollowUpManager.setFlagForRecipients` efter att ha markerat meddelandet som ett utkast. Denna metod lägger till uppföljningsflaggan endast i mottagarens kopia, medan avsändarens vy förblir oförändrad. Det kräver att `MessageFlags.MSGFLAG_UNSENT` sätts innan flaggan appliceras. Du kan också anpassa start-, påminnelse- och förfallodatumen med ett `FollowUpOptions`‑objekt innan du anropar metoden.

### Direkt svar
Markera meddelandet som ett utkast med `MessageFlags.MSGFLAG_UNSENT`, anropa sedan `FollowUpManager.setFlagForRecipients`. Outlook visar flaggan endast för mottagarna, inte för avsändaren.

### Översikt
Ibland behöver du att flaggan visas **endast för mottagare**. Detta exempel markerar först meddelandet som ett utkast och lägger sedan till flaggan.

#### Steg 1: Markera som utkast
`MessageFlags` är en MAPI‑enumeration som styr meddelandets tillstånd. Att sätta `MSGFLAG_UNSENT` talar om för Outlook att objektet är ett utkast.

```java
mapi.setMessageFlags(MapiMessageFlags.MSGFLAG_UNSENT);
```
*Att markera meddelandet som oskickat säkerställer att Outlook behandlar det som ett utkast.*

#### Steg 2: Sätt mottagarflagga
`FollowUpManager.setFlagForRecipients` fäster flaggan exklusivt på mottagarens kopia.

```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
FollowUpManager.setFlagForRecipients(mapi, "Follow up", dtReminderDate);
```
*Flaggan är nu synlig endast för mottagarna – ett klassiskt **flagga för mottagare**‑scenario.*

## Hur man markerar en Outlook‑uppföljningsflagga som slutförd (Funktion 3)?
Läs in `.msg`‑filen i ett `MapiMessage`, anropa sedan `FollowUpManager.completeFlag`. Detta uppdaterar flaggstatusen till Slutförd och lägger till en bock i Outlook. Efter slutförandet sparar du meddelandet för att bevara ändringen. Du kan också justera slutförandetiden genom att ändra egenskapen `FlagCompleteTime` om det behövs för revisionsändamål.

### Direkt svar
Läs in den befintliga `.msg`‑filen i ett `MapiMessage`, anropa `FollowUpManager.completeFlag` och spara filen. Flaggan ändras till “Completed” och visas med en bock i Outlook.

### Steg 1: Läs in meddelandet
`MapiMessage` kan läsa en sparad `.msg`‑fil och ger dig full åtkomst till dess MAPI‑egenskaper.

```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
```

### Steg 2: Markera som slutförd och spara
`FollowUpManager.completeFlag` uppdaterar flaggstatusen, varpå du sparar ändringarna.

```java
FollowUpManager.markAsCompleted(mapi);
mapi.save(outputDir + "MarkedCompleted_out.msg");
```
*Flaggstatusen ändras till “Completed” och den uppdaterade filen sparas.*

## Hur man tar bort en Outlook‑uppföljningsflagga (Funktion 4)?
Öppna `.msg`‑filen med `MapiMessage`, anropa `FollowUpManager.clearFlag` och spara sedan meddelandet. Detta tar bort alla flagg‑relaterade MAPI‑egenskaper, så Outlook visar inte längre någon uppföljningsindikator. Använd detta när en uppgift avbryts eller inte längre är relevant. Se också till att rensa eventuella anpassade påminnelseegenskaper för att undvika kvarvarande notiser.

### Direkt svar
Öppna `.msg`‑filen med `MapiMessage`, anropa `FollowUpManager.clearFlag` och spara filen. Meddelandet visar inte längre någon uppföljningsindikator i Outlook.

### Steg 1: Läs in och rensa flagga
`FollowUpManager.clearFlag` tar bort alla flagg‑relaterade egenskaper från meddelandet.

```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpManager.clearFlag(mapi);
mapi.save(outputDir + "FollowUpFlagRemoved_out.msg");
```
*Meddelandet sparas utan någon uppföljningsflagga.*

## Hur man läser flagginställningar (Funktion 5)?
Anropa `FollowUpManager.getOptions` på ett inläst `MapiMessage` för att få ett `FollowUpOptions`‑objekt. Detta objekt ger start‑, förfallodatum och påminnelsedatum samt flaggämnet, vilket du kan visa eller logga. Det är användbart för rapportering och efterlevnadsgranskningar.

### Direkt svar
Använd `FollowUpManager.getOptions` på ett inläst `MapiMessage` för att hämta ett `FollowUpOptions`‑objekt som innehåller start‑, förfallodatum, påminnelse och flaggämne. Detta är praktiskt för rapportering eller efterlevnadsgranskningar.

### Steg 1: Hämta alternativ
Det returnerade `options`‑objektet ger dig full insyn i flaggans konfiguration.

```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpOptions options = FollowUpManager.getOptions(mapi);
```
*`options`‑objektet innehåller nu start‑, förfallodatum och påminnelse, samt flaggämnet – användbart när du behöver **läsa flagginställningar** för rapportering.*

## Praktiska tillämpningar
- **Uppgiftshanteringsintegration:** Synkronisera flaggade e‑postmeddelanden med Jira, Trello eller Azure Boards.  
- **Automatiserade påminnelser:** Generera dagliga påminnelse‑e‑postmeddelanden för väntande uppföljningar.  
- **Efterlevnadsgranskningar:** Exportera flaggdata för regulatorisk rapportering, med möjlighet att läsa flagginställningar programatiskt.

## Prestandaöverväganden
- **Datumberäkningar:** Beräkna datum en gång per batch istället för i loopar.  
- **Resurshantering:** Stäng alla strömmar eller filhandtag efter att meddelanden sparats.  
- **Minnesanvändning:** Bearbeta stora brevlådor i delar för att undvika heap‑tryck; Aspose.Email kan hantera hundratals‑sidiga brevlådor utan att läsa in hela filen i minnet.

## Vanliga problem och lösningar
| Problem | Orsak | Lösning |
|-------|-------|-----|
| Flaggan visas inte i Outlook | Meddelandet sparades utan korrekta `MessageFlags` | Se till att `setMessageFlags` är satt till `MSGFLAG_UNSENT` innan mottagarflaggor appliceras. |
| Spara kastar `AccessDeniedException` | Fel filväg eller saknade skrivbehörigheter | Verifiera att utdatamappen finns och att applikationen har skrivbehörighet. |
| Datum är fel med en dag | Tidszonskillnad | Använd `TimeZone.getTimeZone("GMT")` eller din lokala zon konsekvent. |

## Vanliga frågor
**Q: Vad är Aspose.Email för Java?**  
A: Det är ett rent Java‑API som låter dig skapa, läsa och manipulera e‑postfiler (MSG, EML osv.) utan att behöva Outlook installerat.

**Q: Hur får jag en gratis provlicens?**  
A: Besök [Aspose website](https://releases.aspose.com/email/java/) för att ladda ner en 30‑dagars provversion.

**Q: Kan jag sätta flera uppföljningsflaggor på ett enda meddelande?**  
A: Outlook stödjer endast en flagga per meddelande, men du kan lagra ytterligare uppgiftsdata i anpassade MAPI‑egenskaper.

**Q: Mitt meddelande sparas inte efter att en flagga satts. Vad bör jag kontrollera?**  
A: Bekräfta att `outputDir`‑sökvägen är giltig och att applikationen har rätt att skriva till den platsen.

**Q: Hur kan jag ta bort flaggor från många meddelanden samtidigt?**  
A: Loopa igenom din meddelandesamling och anropa `FollowUpManager.clearFlag` på varje `MapiMessage`.

## Resurser
- [Dokumentation](https://reference.aspose.com/email/java/)
- [Ladda ner Aspose.Email för Java](https://releases.aspose.com/email/java/)
- [Aspose.Email gratis provversion](https://purchase.aspose.com/purchase/free-trial/aspose-email-java)

---

**Senast uppdaterad:** 2026-07-27  
**Testad med:** Aspose.Email for Java 25.4 (JDK 16)  
**Författare:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Relaterade handledningar

- [Hantera Outlook‑kategorier med Aspose.Email för Java – En omfattande guide](/email/java/calendar-appointments/manage-outlook-categories-aspose-email-java/)
- [Skapa Outlook‑anteckningar java med Aspose.Email – Fullständig guide](/email/java/calendar-appointments/create-customize-outlook-notes-aspose-email-java/)
- [Skapa uppgifter i Microsoft Exchange med Aspose.Email för Java: En komplett guide](/email/java/exchange-server-integration/create-tasks-exchange-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}