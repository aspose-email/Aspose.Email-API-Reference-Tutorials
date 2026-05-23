---
date: '2026-02-22'
description: Lär dig hur du sätter en uppföljningsflagga i Outlook med Aspose.Email
  för Java, inklusive att sätta, läsa och ta bort flaggor för mottagare.
keywords:
- Manage Outlook follow-up flags
- Set follow-up flags in Outlook with Aspose.Email for Java
- Integrate email task management with Aspose.Email
title: Hur man ställer in en uppföljningsflagga i Outlook med Aspose.Email för Java
url: /sv/java/calendar-appointments/aspose-email-java-outlook-follow-up-flags/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Hur man sätter Outlook Follow Up Flag med Aspose.Email för Java

## Introduction
Om du någonsin har haft svårt att hålla reda på viktiga e‑postmeddelanden vet du hur värdefull Outlooks **outlook follow up flag** kan vara. I den här guiden visar vi **how to set an outlook follow up flag** programatiskt med Aspose.Email för Java, och vi täcker också hur man **set outlook follow up flag for recipients**, samt hur man **remove an outlook follow up flag** när en uppgift är slutförd. I slutet kommer du att kunna automatisera uppgiftsspårning, påminnelser och revisionsspår direkt från din Java‑kod.

**What you’ll learn**
- Skapa och tillämpa en follow‑up‑flagga på ett Outlook‑meddelande.  
- Sätta follow‑up‑flaggor för specifika mottagare.  
- Markera en flagga som slutförd och senare ta bort den.  
- Läsa flagg‑alternativ för rapportering eller efterlevnad.  

Låt oss förbereda miljön innan vi dyker ner i koden.

## Quick Answers
- **What does “how to set follow‑up” mean?** Att lägga till en flagga med start‑, påminnelse‑ och förfallodatum på ett Outlook‑objekt.  
- **Which library is required?** Aspose.Email för Java (v25.4 eller nyare).  
- **Do I need a license?** Ja, en prov‑ eller köpt licens krävs för full funktionalitet.  
- **Can I set flags for recipients only?** Absolut – använd `FollowUpManager.setFlagForRecipients`.  
- **Is it possible to remove a flag later?** Ja, anropa `FollowUpManager.clearFlag`.

## What is an Outlook Follow Up Flag?
En Outlook follow up flag är en inbyggd uppgiftmarkör som kan bifoga ett startdatum, en påminnelse och ett förfallodatum till vilket e‑postobjekt som helst. Den förvandlar ett vanligt e‑postmeddelande till ett spårat åtgärdselement, vilket hjälper dig och ditt team att hålla koll på pågående arbete.

## Why Use Aspose.Email for Java?
Aspose.Email erbjuder ett rent Java‑API som fungerar utan att Outlook är installerat, vilket låter dig manipulera .msg‑filer, sätta flaggor och hantera uppgifter på vilken plattform som helst – perfekt för **automate outlook tasks**, backend‑tjänster eller integration med projekt‑hanteringsverktyg.

## Prerequisites
- **Aspose.Email för Java** version 25.4 eller senare (även känt som **aspose email java**).  
- **JDK 16+** installerat.  
- Maven‑kompatibel IDE (IntelliJ IDEA, Eclipse, etc.).  
- Grundläggande kunskaper i Java och bekantskap med e‑postkoncept.

## Setting Up Aspose.Email for Java
### Maven Configuration
Lägg till följande beroende i din `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### License Acquisition
Aspose.Email kräver en licens för produktionsanvändning:

- **Free trial** – 30‑dagars utvärdering.  
- **Temporary license** – förlängd testning.  
- **Full license** – evig prenumeration.

Initiera licensen innan någon e‑postoperation:

```java
License license = new License();
license.setLicense("path/to/Aspose.Total.Java.lic");
```

## Set Outlook Follow Up Flag (Feature 1)
### Step 1: Create and Initialize the Message
```java
MailMessage mailMsg = new MailMessage();
mailMsg.setSender(new MailAddress("AETest12@gmail.com"));
mailMsg.getTo().addMailAddress(new MailAddress("receiver@gmail.com"));
mailMsg.setBody("This message will test if follow up options can be added to a new mapi message.");
MapiMessage mapi = MapiMessage.fromMailMessage(mailMsg);
```
*Vi bygger först ett `MailMessage`, sätter avsändare/mottagare och konverterar sedan till ett `MapiMessage` för flagg‑manipulation.*

### Step 2: Define Follow‑Up Dates (Outlook Flag Reminder)
```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 14, 40, 0);
Date dtStartDate = calendar.getTime();
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
calendar.add(Calendar.DATE, 1);
Date dtDueDate = calendar.getTime();
```
*Här sätter vi start‑, påminnelse‑ (den **outlook flag reminder**)‑ och förfallodatum med hjälp av `Calendar`‑klassen.*

### Step 3: Apply Follow‑Up Options
```java
FollowUpOptions options = new FollowUpOptions("Follow Up", dtStartDate, dtDueDate, dtReminderDate);
FollowUpManager.setOptions(mapi, options);
```
*`FollowUpOptions`‑objektet innehåller alla flagg‑detaljer, som vi applicerar med `FollowUpManager.setOptions`.*

### Step 4: Save the Message
```java
mapi.save(outputDir + "SetFollowUpflag_out.msg");
```
*Medelandet sparas som en `.msg`‑fil med flaggan bifogad.*

## How to Set Flag for Recipients (Feature 2)
### Overview
Ibland behöver du att flaggan bara ska visas **only for recipients**. Detta exempel markerar meddelandet som ett utkast först, och lägger sedan till flaggan.

#### Step 1: Mark as Draft
```java
mapi.setMessageFlags(MapiMessageFlags.MSGFLAG_UNSENT);
```
*Att markera meddelandet som oskickat säkerställer att Outlook behandlar det som ett utkast.*

#### Step 2: Set Recipient Flag
```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
FollowUpManager.setFlagForRecipients(mapi, "Follow up", dtReminderDate);
```
*Flaggan är nu synlig endast för mottagarna – ett klassiskt **flag for recipients**‑scenario.*

## How to Mark an Outlook Follow Up Flag as Completed (Feature 3)
### Step 1: Load the Message
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
```

### Step 2: Mark as Completed and Save
```java
FollowUpManager.markAsCompleted(mapi);
mapi.save(outputDir + "MarkedCompleted_out.msg");
```
*Flaggstatusen ändras till “Completed” och den uppdaterade filen sparas.*

## How to Remove an Outlook Follow Up Flag (Feature 4)
### Step 1: Load and Clear Flag
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpManager.clearFlag(mapi);
mapi.save(outputDir + "FollowUpFlagRemoved_out.msg");
```
*Meddelandet sparas utan någon follow‑up‑flagga.*

## How to Read Flag Options (Feature 5)
### Step 1: Retrieve Options
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpOptions options = FollowUpManager.getOptions(mapi);
```
*`options`‑objektet innehåller nu start‑, förfallodatum och påminnelse samt flagg‑ämnet – användbart när du behöver **read flag options** för rapportering.*

## Practical Applications
- **Task‑Management Integration:** Synkronisera flaggade e‑postmeddelanden med Jira, Trello eller Azure Boards.  
- **Automated Reminders:** Generera dagliga påminnelse‑e‑postmeddelanden för väntande follow‑ups.  
- **Compliance Audits:** Exportera flaggdata för regulatorisk rapportering.

## Performance Considerations
- **Date Calculations:** Beräkna datum en gång per batch istället för i loopar.  
- **Resource Management:** Stäng alla strömmar eller filhandtag efter att meddelanden sparats.  
- **Memory Usage:** Bearbeta stora postlådor i delar för att undvika minnespress.

## Common Issues and Solutions
| Issue | Cause | Fix |
|-------|-------|-----|
| Flag not appearing in Outlook | Message saved without proper `MessageFlags` | Ensure `setMessageFlags` is set to `MSGFLAG_UNSENT` before applying recipient flags. |
| Save throws `AccessDeniedException` | Incorrect file path or missing write permissions | Verify the output directory exists and the application has write rights. |
| Dates are off by one day | Time‑zone mismatch | Use `TimeZone.getTimeZone("GMT")` or your local zone consistently. |

## Frequently Asked Questions
**Q: What is Aspose.Email for Java?**  
A: It’s a pure‑Java API that lets you create, read, and manipulate email files (MSG, EML, etc.) without needing Outlook installed.

**Q: How do I obtain a free trial license?**  
A: Visit the [Aspose website](https://releases.aspose.com/email/java/) to download a 30‑day trial.

**Q: Can I set multiple follow‑up flags on a single message?**  
A: Outlook supports only one flag per message, but you can store additional task data in custom MAPI properties.

**Q: My message isn’t saved after setting a flag. What should I check?**  
A: Confirm the `outputDir` path is valid and that the application has permission to write to that location.

**Q: How can I remove flags from many messages at once?**  
A: Loop through your message collection and call `FollowUpManager.clearFlag` on each `MapiMessage`.

## Resources
- [Documentation](https://reference.aspose.com/email/java/)
- [Download Aspose.Email for Java](https://releases.aspose.com/email/java/)
- [Aspose.Email Free Trial](https://purchase.aspose.com/purchase/free-trial/aspose-email-java)

---

**Last Updated:** 2026-02-22  
**Tested With:** Aspose.Email for Java 25.4 (jdk16)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}