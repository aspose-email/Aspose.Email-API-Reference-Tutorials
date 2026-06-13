---
date: '2026-06-13'
description: Lär dig hur du läser MSG files och parsar MSG attachments med Aspose.Email
  för Java, extraherar delivery/read receipts och vote results effektivt. Inkluderar
  setup, code och best practices.
keywords:
- how to read msg
- parse msg attachments
- Aspose.Email for Java
schemas:
- author: Aspose
  dateModified: '2026-06-13'
  description: Learn how to read MSG files and parse MSG attachments using Aspose.Email
    for Java, extracting delivery/read receipts and vote results efficiently. Includes
    setup, code, and best practices.
  headline: How to Read MSG Files with Aspose.Email for Java
  type: TechArticle
- description: Learn how to read MSG files and parse MSG attachments using Aspose.Email
    for Java, extracting delivery/read receipts and vote results efficiently. Includes
    setup, code, and best practices.
  name: How to Read MSG Files with Aspose.Email for Java
  steps:
  - name: Load the MSG File
    text: MapiMessage is the Aspose.Email class that represents an Outlook MSG message.
  - name: Iterate Over Recipients
    text: MapiRecipient represents a single recipient (To, CC, or BCC) in the MSG
      file.
  - name: Retrieve and Print Delivery Time
    text: DeliveryTime is a property of MapiRecipient that holds the timestamp when
      the message was delivered to the recipient’s server.
  - name: Retrieve and Print Read Time
    text: ReadTime is a property of MapiRecipient indicating when the recipient opened
      the message, if that information is available.
  - name: Load the MSG File
    text: MapiMessage is used again to access the voting information embedded in the
      MSG file.
  - name: Iterate Over Recipients
    text: MapiRecipient provides access to each participant’s voting choice and response
      time.
  - name: Retrieve and Print Response
    text: The `VotingResponse` property contains the actual vote (e.g., “Accept”,
      “Decline”, or custom options).
  - name: Retrieve and Print Response Time
    text: '`VotingResponseTime` records when the recipient submitted their vote, allowing
      chronological analysis of poll activity.'
  type: HowTo
- questions:
  - answer: Split the file into smaller segments or use the streaming API to read
      portions without full in‑memory loading.
    question: How do I handle MSG files larger than 500 MB?
  - answer: Yes, map the receipt and vote fields to your DB schema and use JDBC or
      an ORM to persist them.
    question: Can I store the extracted data directly into a database?
  - answer: Absolutely; Aspose.Email for Java is platform‑agnostic and runs on any
      OS with a supported JDK.
    question: Does the library work on Linux environments?
  - answer: Use `MailMessage.getAttachments()` after loading the MSG; the method returns
      a collection of all embedded files.
    question: Is there a way to extract attachments while reading receipts?
  - answer: Reach out via the official Aspose Email Forum for community help or open
      a support ticket with a valid license.
    question: What support options are available if I encounter bugs?
  type: FAQPage
title: Hur man läser MSG files med Aspose.Email för Java
url: /sv/java/email-parsing-analysis/aspose-email-java-msg-receipts-vote-results/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Hur man läser MSG-filer med Aspose.Email för Java

## Introduktion

Att programatiskt läsa MSG-filer låter dig hämta värdefull spårningsdata—leveransbekräftelser, läsbekräftelser och röstningsresultat—from Outlook-meddelanden. I den här guiden visar vi **hur man läser msg**-filer med Aspose.Email för Java, går igenom den nödvändiga konfigurationen och demonstrerar hur man effektivt extraherar mottagnings- och röstningsinformation.

## Snabba svar
- **Vilket bibliotek hanterar MSG-parsing?** Aspose.Email for Java.  
- **Kan jag extrahera läsbekräftelser?** Ja, API:et returnerar leverans- och lästidsstämplar.  
- **Är röstningsdata tillgänglig?** Absolut; du kan hämta varje mottagares röstningssvar.  
- **Behöver jag en licens?** En provversion fungerar för testning; en betald licens tar bort utvärderingsgränser.  
- **Vilken Java-version krävs?** Java 16 eller senare rekommenderas.

## Vad är Aspose.Email för Java?

Aspose.Email för Java är ett fristående Java‑bibliotek som möjliggör skapande, manipulering och konvertering av e‑postformat utan att kräva Microsoft Outlook. Det tillhandahåller en rik objektmodell för MSG, EML, PST och många andra format, vilket låter utvecklare arbeta med e‑postdata direkt från Java‑kod. (45 words)

## Varför använda Aspose.Email för Java för att läsa MSG-filer?

Aspose.Email för Java stöder **30+ e‑postformat** och kan bearbeta MSG-filer upp till **500 MB** utan att ladda hela filen i minnet. Dess högpresterande parsingsmotor minskar CPU‑ och minnesförbrukning, vilket gör den idealisk för storskalig e‑postarkivbearbetning och realtidsanalys‑scenarier. (48 words)

## Förutsättningar

- **Bibliotek & beroenden:** Aspose.Email för Java version 25.4 eller senare och en JDK 16+ runtime.  
- **IDE:** IntelliJ IDEA, Eclipse eller någon Java‑kompatibel IDE med Maven‑stöd.  
- **Grundläggande färdigheter:** Bekantskap med Java‑syntax och objektorienterade koncept.

## Licensanskaffning

För att använda Aspose.Email för Java behöver du en licens:

- **Gratis provversion:** Börja med den gratis provversionen som finns på [Aspose's website](https://releases.aspose.com/email/java/).  
- **Tillfällig licens:** Begär en tillfällig licens från [purchase page](https://purchase.aspose.com/temporary-license/).  
- **Köp:** Om du är nöjd med utvärderingen, köp en licens för full åtkomst till alla funktioner via sidan [Buy Aspose Products](https://purchase.aspose.com/buy) page.  

## Hur extraherar du läs- och leveransbekräftelseinformation från en MSG-fil?

Läs in MSG-filen, iterera genom dess mottagare och läs egenskaperna `DeliveryTime` och `ReadTime`. Detta tillvägagångssätt returnerar de exakta tidsstämplarna när varje mottagares e‑postserver levererade meddelandet och när mottagaren öppnade det, vilket ger dig exakt spårningsdata för analys. (53 words)

### Steg 1: Läs in MSG-filen
MapiMessage är Aspose.Email‑klassen som representerar ett Outlook MSG‑meddelande.  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```  

### Steg 2: Iterera över mottagare
MapiRecipient representerar en enskild mottagare (Till, CC eller BCC) i MSG-filen.  
```java
import com.aspose.email.MapiMessage;
import com.aspose.email.MapiRecipient;
import com.aspose.email.MapiPropertyTag;

public class RetrieveReceipts {
    public static void main(String[] args) {
        String dataDir = "YOUR_DOCUMENT_DIRECTORY/outlook/";
        MapiMessage msg = MapiMessage.fromFile(dataDir + "message.msg");
```  

### Steg 3: Hämta och skriv ut leveranstid
DeliveryTime är en egenskap hos MapiRecipient som innehåller tidsstämpeln när meddelandet levererades till mottagarens server.  
```java
        for (MapiRecipient recipient : msg.getRecipients()) {
            System.out.println("Recipient: " + recipient.getDisplayName());
```  

### Steg 4: Hämta och skriv ut lästid
ReadTime är en egenskap hos MapiRecipient som indikerar när mottagaren öppnade meddelandet, om den informationen är tillgänglig.  
```java
            System.out.println("Delivery time: " + 
                recipient.getProperties().get_Item(MapiPropertyTag.PR_RECIPIENT_TRACKSTATUS_TIME_DELIVERY).getDateTime());
```  

## Hur läser du röstningsresultat från en MSG-fil?

Efter att ha läst in meddelandet exponerar API:et varje mottagares röstningssvar och tiden de svarade, vilket möjliggör programmatisk aggregering av omröstningsresultat. Dessa data kan användas för att skapa sammanfattningsrapporter eller matas direkt in i business‑intelligence‑instrumentpaneler för snabba beslutsfattande. (53 words)

### Steg 1: Läs in MSG-filen
MapiMessage används igen för att komma åt röstningsinformationen som är inbäddad i MSG-filen.  
```java
            System.out.println("Read time: " + 
                recipient.getProperties().get_Item(MapiPropertyTag.PR_RECIPIENT_TRACKSTATUS_TIME_READ).getDateTime());
        }
    }
}
```  

### Steg 2: Iterera över mottagare
MapiRecipient ger åtkomst till varje deltagares röstningsval och svarstid.  
```java
import com.aspose.email.MapiMessage;
import com.aspose.email.MapiRecipient;
import com.aspose.email.MapiPropertyTag;

public class ReadVoteResults {
    public static void main(String[] args) {
        String dataDir = "YOUR_DOCUMENT_DIRECTORY/outlook/";
        MapiMessage msg = MapiMessage.fromFile(dataDir + "message.msg");
```  

### Steg 3: Hämta och skriv ut svar
`VotingResponse`‑egenskapen innehåller den faktiska rösten (t.ex. “Accept”, “Decline” eller anpassade alternativ).  
```java
        for (MapiRecipient recipient : msg.getRecipients()) {
            System.out.println("Recipient: " + recipient.getDisplayName());
```  

### Steg 4: Hämta och skriv ut svarstid
`VotingResponseTime` registrerar när mottagaren skickade in sin röst, vilket möjliggör kronologisk analys av omröstningsaktivitet.  
```java
            System.out.println("Response: " + 
                recipient.getProperties().get_Item(MapiPropertyTag.PR_RECIPIENT_AUTORESPONSE_PROP_RESPONSE).getString());
```  

## Praktiska tillämpningar

1. **E‑postkampanjspårning:** Mät öppningsfrekvens och leveransframgång genom att analysera mottagnings‑tidsstämplar.  
2. **Undersökningsanalys:** Konsolidera röstningsresultat från Outlook‑omröstningar för snabba beslutsfattande.  
3. **Kundfeedback‑hantering:** Hämta svarsdatan till CRM‑ eller analysplattformar för djupare insikter.

Att integrera dessa extraktioner med databaser eller BI‑verktyg förstärker värdet av den råa e‑postdatan.

## Prestandaöverväganden

- Bearbeta stora MSG-filer i **delar** för att hålla minnesanvändningen låg.  
- Använd **streaming‑API:er** när du hanterar tusentals meddelanden.  
- Lagra mottagardata i lätta samlingar såsom `ArrayList` eller `HashMap` för snabba uppslag.

## Vanliga problem och lösningar

- **Null‑tidsstämplar:** En saknad `ReadTime` betyder vanligtvis att mottagaren ännu inte har öppnat meddelandet.  
- **Stora bilagor:** Om en MSG innehåller enorma bilagor, aktivera `LoadOptions.setPreserveEmbeddedResources(false)` för att hoppa över att ladda dem i minnet.  
- **Kodningsproblem:** Säkerställ att rätt kodsida är inställd via `MailMessage.setCharset(Charset.forName("UTF-8"))` när du läser icke‑ASCII‑innehåll.

## Vanliga frågor

**Q: Hur hanterar jag MSG-filer som är större än 500 MB?**  
A: Dela filen i mindre segment eller använd streaming‑API:et för att läsa delar utan full in‑memory‑laddning.

**Q: Kan jag lagra den extraherade datan direkt i en databas?**  
A: Ja, mappa mottagnings‑ och röstningsfält till ditt DB‑schema och använd JDBC eller en ORM för att persistera dem.

**Q: Fungerar biblioteket i Linux‑miljöer?**  
A: Absolut; Aspose.Email för Java är plattformsoberoende och körs på alla OS med en stödjande JDK.

**Q: Finns det ett sätt att extrahera bilagor samtidigt som man läser mottagningsbekräftelser?**  
A: Använd `MailMessage.getAttachments()` efter att ha läst in MSG; metoden returnerar en samling av alla inbäddade filer.

**Q: Vilka supportalternativ finns tillgängliga om jag stöter på buggar?**  
A: Kontakta det officiella Aspose Email‑forumet för community‑hjälp eller öppna ett supportärende med en giltig licens.

## Resurser
- **Dokumentation:** [Aspose Email Documentation](https://reference.aspose.com/email/java/)  
- **Dokumentation (duplicerad):** [Aspose Email Documentation](https://reference.aspose.com/email/java/)  
- **Ladda ner SDK:** [Aspose Email Downloads](https://releases.aspose.com/email/java/)  
- **Nedladdningssektion:** [Download Section](https://releases.aspose.com/email/java/)  
- **Köp licens:** [Buy Aspose Products](https://purchase.aspose.com/buy)  
- **Gratis provversion:** Starta med en [Free Trial Version](https://releases.aspose.com/email/java/)  
- **Tillfällig licens:** [Request Temporary License](https://purchase.aspose.com/temporary-license/)  
- **Supportforum:** [Aspose Email Forum](https://forum.aspose.com/c/email/10)  
- **Supportforum (duplicerad):** [Aspose Email Forum](https://forum.aspose.com/c/email/10)  

**Senast uppdaterad:** 2026-06-13  
**Testat med:** Aspose.Email för Java 25.4  
**Författare:** Aspose

```java
            System.out.println("Response time: " + 
                recipient.getProperties().get_Item(MapiPropertyTag.PR_RECIPIENT_TRACKSTATUS_TIME).getDateTime());
        }
    }
}
```

## Relaterade handledningar

- [Hur man laddar och parsar Outlook MSG-filer med Aspose.Email för Java: En omfattande guide](/email/java/mapi-operations/outlook-msg-aspose-email-java-guide/)
- [Konvertera MSG till EML och hantera bilagor med Aspose.Email för Java](/email/java/attachments-handling/aspose-email-java-master-msg-attachments-parsing/)
- [Extrahera inbäddade bilagor Java – MSG-filer med Aspose.Email](/email/java/attachments-handling/extract-inline-attachments-msg-files-java-aspose-email/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}