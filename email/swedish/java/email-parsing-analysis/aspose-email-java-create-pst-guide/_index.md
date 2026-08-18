---
date: '2026-06-08'
description: Lär dig hur du skapar PST-filer med Aspose.Email for Java, inklusive
  hur du lägger till mappstrukturer och hur du söker igenom PST-innehåll effektivt.
  Steg‑för‑steg guide.
keywords:
- how to create pst
- how to add folder
- how to search pst
schemas:
- author: Aspose
  dateModified: '2026-06-08'
  description: Learn how to create PST files with Aspose.Email for Java, including
    how to add folder structures and how to search PST content efficiently. Step‑by‑step
    guide.
  headline: How to Create PST Files with Aspose.Email for Java
  type: TechArticle
- description: Learn how to create PST files with Aspose.Email for Java, including
    how to add folder structures and how to search PST content efficiently. Step‑by‑step
    guide.
  name: How to Create PST Files with Aspose.Email for Java
  steps:
  - name: Add Maven Dependency
    text: Add the Aspose.Email Maven dependency to your `pom.xml`. This pulls in all
      required binaries automatically.
  - name: Acquire and Apply a License
    text: A free trial is available, but a permanent license removes evaluation limits
      and enables full‑speed processing.
  - name: Initialize PersonalStorage
    text: The `PersonalStorage` class is Aspose.Email's top‑level object that represents
      a single PST file in memory. After instantiation, all read and write operations
      flow through this object.
  - name: Define Directory Paths
    text: Set source and destination paths for your email files and the PST output
      location.
  - name: Create the PST File
    text: Use `PersonalStorage.create()` with `FileFormatVersion.Unicode` to produce
      a modern Unicode PST that supports large folders and Unicode characters.
  - name: Build Search Query
    text: Construct a query that looks for a keyword in the subject or body, ignoring
      case.
  - name: Execute Query and Retrieve Messages
    text: Run the query on the target folder and iterate over the resulting `MapiMessage`
      collection.
  - name: Initialize PersonalStorage Object
    text: Assume `PersonalStorage` object (`pst`) is already created as shown previously.
  - name: Add to PST Folder
    text: 'Convert `MailMessage` to `MapiMessage` and add it:'
  type: HowTo
- questions:
  - answer: JDK 16 or higher is recommended for full compatibility with Aspose.Email
      for Java.
    question: What is the minimum Java version required?
  - answer: Yes, a trial mode is available but limits PST size to **10 MB** and disables
      certain optimizations.
    question: Can I use Aspose.Email without a license?
  - answer: Process messages in batches, dispose of `MapiMessage` objects promptly,
      and enable lazy loading via `PersonalStorage.setUseUnicode(true)`.
    question: How do I handle large PST files efficiently?
  - answer: Absolutely. When converting `MailMessage` to `MapiMessage`, call `mapiMsg.getAttachments().add(attachment)`
      to embed files.
    question: Is it possible to add attachments to emails in PST files?
  - answer: Aspose offers a dedicated support forum, detailed documentation, and email
      support for licensed customers.
    question: What kind of support is available for troubleshooting issues?
  type: FAQPage
title: Hur man skapar PST-filer med Aspose.Email for Java
url: /sv/java/email-parsing-analysis/aspose-email-java-create-pst-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Behärska e-posthantering med Aspose.Email för Java

Om du behöver **how to create pst**-filer programatiskt, har du kommit till rätt ställe. I den här handledningen går vi igenom varje steg som krävs för att generera en Unicode PST-fil, lägga till standard Outlook‑mappar, importera meddelanden och köra skiftlägesokänsliga sökningar — allt med Aspose.Email för Java. I slutet har du ett återanvändbart kodmönster som skalar från ett fåtal e‑postmeddelanden till flera gigabyte stora arkiv.

## Snabba svar
- **Hur kommer jag igång?** Add the Aspose.Email Maven dependency, obtain a license, and instantiate `PersonalStorage`.
- **Kan jag lägga till en Inkorg-mapp?** Yes – call `pst.getRootFolder().addSubFolder("Inbox")`.
- **Stöds skiftlägesokänslig sökning?** Use `PersonalStorageQueryBuilder` with `StringComparison.OrdinalIgnoreCase`.
- **Vilken filstorlek kan hanteras?** Aspose.Email processes PST files up to 2 GB without loading the whole file into memory.
- **Behöver jag en betald licens för produktion?** A permanent license removes trial limits and unlocks full performance features.

## Vad är how to create pst?
**how to create pst** refererar till den programatiska processen att generera en Outlook Personal Storage Table (PST)-fil med kod snarare än Outlook‑gränssnittet. Aspose.Email för Java tillhandahåller ett fullt hanterat API som skapar Unicode‑PST‑filer, lägger till mappar och lagrar `MapiMessage`‑objekt utan att Outlook måste vara installerat.

## Varför använda Aspose.Email för PST‑skapande?
Aspose.Email stöder **50+** e‑postrelaterade format (MSG, EML, MBOX, PST, etc.) och kan bearbeta PST‑filer med **upp till 2 GB** storlek samtidigt som minnesanvändningen hålls under **150 MB** tack vare dess lazy‑loading‑arkitektur. Denna kvantifierade kapacitet gör det idealiskt för företagsarkivering, migration och efterlevnadsscenarier.

## Förutsättningar

- **Java Development Kit (JDK)** – version 16 eller senare.
- **Maven** – för beroendehantering.
- Grundläggande kunskap om Java‑syntax; ingen tidigare erfarenhet av PST‑filer krävs.

## Hur skapar du en PST‑fil?

`PersonalStorage`‑klassen representerar en PST‑fil och tillhandahåller metoder för att skapa, öppna och manipulera dess innehåll. För att skapa en ny Unicode‑PST, anropa `PersonalStorage.create()` med önskad filsökväg och formatversion. Denna operation genererar en modern PST som stödjer stora mappar, Unicode‑tecken och effektiv strömning, vilket gör den lämplig för både småskaliga och företagsnivå‑arkiveringsuppgifter.

### Steg 1: Lägg till Maven‑beroende

Lägg till Aspose.Email Maven‑beroendet i din `pom.xml`. Detta hämtar automatiskt alla nödvändiga binärer.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Steg 2: Skaffa och tillämpa en licens

En gratis provversion finns tillgänglig, men en permanent licens tar bort utvärderingsgränser och möjliggör full hastighetsbehandling.

```java
import com.aspose.email.*;

public class AsposeEmailSetup {
    public static void main(String[] args) {
        // Set up license if available
        License license = new License();
        try {
            license.setLicense("path/to/your/license.lic");
        } catch (Exception e) {
            System.out.println("License not found, proceeding with trial version.");
        }

        System.out.println("Aspose.Email for Java is ready to use!");
    }
}
```

## Hur lägger du till en mapp i PST?

Skapa önskad mapphierarki under PST‑roten och referera till den när du infogar meddelanden. `FolderInfo`‑objektet representerar varje mapp och kan nästlas godtyckligt, vilket låter dig bygga strukturer som Inkorg, Skickade objekt eller anpassade projektmappar. Att lägga till mappar är en lättviktig operation som inte laddar meddelandeinnehåll, vilket bevarar prestanda även för stora PST‑filer.

### Steg 1: Initiera PersonalStorage

`PersonalStorage`‑klassen är Aspose.Email:s översta objekt som representerar en enskild PST‑fil i minnet. Efter instansiering flödar alla läs‑ och skrivoperationer genom detta objekt.

```java
import com.aspose.email.FileFormatVersion;
import com.aspose.email.PersonalStorage;
```

### Steg 2: Definiera katalogsökvägar

Ange käll- och destinationssökvägar för dina e‑postfiler och PST‑utdataplatsen.

```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY";
String outputDir = "YOUR_OUTPUT_DIRECTORY";
```

### Steg 3: Skapa PST‑filen

Använd `PersonalStorage.create()` med `FileFormatVersion.Unicode` för att skapa en modern Unicode‑PST som stödjer stora mappar och Unicode‑tecken.

```java
try {
    PersonalStorage pst = PersonalStorage.create(outputDir + "NewPSTFile_out.pst", FileFormatVersion.Unicode);

    // Perform operations here.
} finally {
    if (pst != null)
        pst.dispose();
}
```

## Hur söker man i PST?

`PersonalStorageQueryBuilder` är en builder‑klass som används för att konstruera sökfrågor för PST‑innehåll. Genom att konfigurera buildern med önskade kriterier och ange `StringComparison.OrdinalIgnoreCase` kan du utföra snabba, skiftlägesokänsliga sökningar över ämnen, brödtexter och anpassade egenskaper utan att ladda hela PST‑filen i minnet.

### Steg 1: Bygg sökfråga

Konstruera en fråga som söker efter ett nyckelord i ämnet eller brödtexten, utan att ta hänsyn till skiftläge.

```java
import com.aspose.email.MailQueryBuilder;
import com.aspose.email.MailQuery;
import com.aspose.email.MessageInfoCollection;

MailQueryBuilder builder = new MailQueryBuilder();
builder.getFrom().contains("automated", true);
```

### Steg 2: Utför frågan och hämta meddelanden

Kör frågan på mål‑mappen och iterera över den resulterande `MapiMessage`‑samlingen.

```java
try {
    MailQuery query = builder.getQuery();
    MessageInfoCollection coll = fi.getContents(query);

    // Process results as needed.
} finally {
    if (pst != null)
        pst.dispose();
}
```

## Skapa en fördefinierad mapp i PST

Att lägga till en fördefinierad mapp som **Inbox** hjälper till att organisera dina e‑postdata effektivt.

### Steg 1: Initiera PersonalStorage‑objekt

Anta att `PersonalStorage`‑objektet (`pst`) redan har skapats som visat tidigare.

### Steg 2: Skapa 'Inbox'-mappen

```java
try {
    FolderInfo fi = pst.createPredefinedFolder("Inbox", StandardIpmFolder.Inbox);
} finally {
    if (pst != null)
        pst.dispose();
}
```

## Lägga till meddelanden i en PST‑mapp

Fyll din PST‑mapp med e‑postmeddelanden genom att läsa in dem från filer och konvertera.

### Steg 1: Ladda e‑postmeddelande

```java
import com.aspose.email.MailMessage;
import com.aspose.email.MapiMessage;

MailMessage mailMessage = MailMessage.load(dataDir + "message.msg");
```

### Steg 2: Lägg till i PST‑mappen

Konvertera `MailMessage` till `MapiMessage` och lägg till den:

```java
try {
    fi.addMessage(MapiMessage.fromMailMessage(mailMessage));
} finally {
    if (pst != null)
        pst.dispose();
}
```

## Praktiska tillämpningar

Aspose.Email for Java isn’t just about creating PST files; it’s a versatile tool with numerous applications:
- **Email Archiving**: Automatisera arkivering av företags‑e‑post till PST‑filer, med stöd för lagringspolicyer i upp till 10 år.
- **Migration Tools**: Migrera sömlöst från äldre e‑postlagringar (t.ex. MBOX) till Outlook PST med ett enda API‑anrop per meddelande.
- **Data Analysis**: Extrahera metadata såsom avsändare, mottagare och tidsstämplar för affärs‑intelligens‑pipeline.
- **Backup Solutions**: Bygg robusta backup‑verktyg som lagrar inkrementella e‑poständringar utan att bearbeta hela brevlådan igen.

## Prestandaöverväganden

To ensure optimal performance when using Aspose.Email:
- **Resource Management**: Always call `pst.dispose()` or use try‑with‑resources to free native handles promptly.
- **Batch Processing**: Process emails in batches of **500** items to keep memory usage predictable.
- **Concurrency Handling**: The library is thread‑safe for read‑only operations; for writes, synchronize access to the `PersonalStorage` instance.

## Vanliga problem och lösningar

| Problem | Orsak | Lösning |
|-------|-------|----------|
| **OutOfMemoryError** när stora PST‑filer hanteras | Laddar hela PST‑filen i minnet | Aktivera `PersonalStorage.setUseUnicode(true)` och bearbeta meddelanden i strömmar. |
| **Folder not found**‑fel | Felaktig skiftlägeskänslig mappväg | Använd `StringComparison.OrdinalIgnoreCase` i frågor eller normalisera mappnamn. |
| **License not applied** | Licensfilen laddades inte innan första API‑anropet | Ladda licensen vid applikationsstart, innan några `PersonalStorage`‑objekt skapas. |

## Vanliga frågor

**Q: Vad är den minsta Java‑versionen som krävs?**  
A: JDK 16 eller högre rekommenderas för full kompatibilitet med Aspose.Email för Java.

**Q: Kan jag använda Aspose.Email utan licens?**  
A: Ja, ett provläge är tillgängligt men begränsar PST‑storlek till **10 MB** och inaktiverar vissa optimeringar.

**Q: Hur hanterar jag stora PST‑filer effektivt?**  
A: Bearbeta meddelanden i batchar, frigör `MapiMessage`‑objekt snabbt och aktivera lazy loading via `PersonalStorage.setUseUnicode(true)`.

**Q: Är det möjligt att lägga till bilagor i e‑post i PST‑filer?**  
A: Absolut. När du konverterar `MailMessage` till `MapiMessage`, anropa `mapiMsg.getAttachments().add(attachment)` för att bädda in filer.

**Q: Vilken typ av support finns tillgänglig för felsökning?**  
A: Aspose erbjuder ett dedikerat supportforum, detaljerad dokumentation och e‑postsupport för licensierade kunder.

## Resurser
- [Documentation](https://reference.aspose.com/email/java/)
- [Download](https://releases.aspose.com/email/java/)
- [Purchase](https://purchase.aspose.com/buy)
- [Free Trial](https://releases.aspose.com/email/java/)
- [Temporary License](https://purchase.aspose.com/temporary-license/)
- [Support Forum](https://forum.aspose.com/c/email/10)

---

**Senast uppdaterad:** 2026-06-08  
**Testad med:** Aspose.Email for Java 24.10  
**Författare:** Aspose

## Relaterade handledningar

- [Hur man skapar och hanterar Outlook PST‑filer med Aspose.Email för Java](/email/java/outlook-pst-ost-operations/aspose-email-java-manage-pst-files/)
- [Manipulera PST‑filer med Aspose.Email för Java: En omfattande guide](/email/java/outlook-pst-ost-operations/manipulate-pst-files-aspose-email-java/)
- [Extrahera e‑postbilagor Java – med Aspose.Email för PST‑filer – En steg‑för‑steg‑guide](/email/java/attachments-handling/extract-email-attachments-pst-aspose-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}