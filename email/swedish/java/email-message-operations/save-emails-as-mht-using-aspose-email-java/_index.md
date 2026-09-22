---
date: '2026-09-22'
description: Lär dig hur du använder en Aspose.Email-licens med Maven för att spara
  e-post som MHT-filer i Java. Inkluderar setup, custom templates, och calendar event
  handling.
keywords:
- aspose email license
- how to save mht
- how to convert mht
- maven dependency aspose email
lastmod: '2026-09-22'
og_description: Lär dig hur du använder en Aspose.Email-licens med Maven för att spara
  e-post som MHT-filer i Java. Inkluderar setup, custom templates, och calendar support.
og_image_alt: 'Tutorial: saving emails as MHT using Aspose.Email for Java with a license'
og_title: Hur man använder en Aspose.Email-licens för att spara e-post som MHT
schemas:
- author: Aspose
  dateModified: '2026-09-22'
  description: Learn how to use an Aspose.Email license with Maven to save emails
    as MHT files in Java. Includes setup, custom templates, and calendar event handling.
  headline: How to use an Aspose.Email license to save emails as MHT
  type: TechArticle
- description: Learn how to use an Aspose.Email license with Maven to save emails
    as MHT files in Java. Includes setup, custom templates, and calendar event handling.
  name: How to use an Aspose.Email license to save emails as MHT
  steps:
  - name: '**Free trial** – download from [Releases](https://releases.aspose.com/email/java/)
      and explore features without limitations.'
    text: '**Free trial** – download from [Releases](https://releases.aspose.com/email/java/)
      and explore features without limitations.'
  - name: '**Temporary license** – request a fully functional version via the [Temporary
      License Page](https://purchase.aspose.com/temporary-license/).'
    text: '**Temporary license** – request a fully functional version via the [Temporary
      License Page](https://purchase.aspose.com/temporary-license/).'
  - name: '**Purchase** – obtain a permanent license for long‑term projects.'
    text: '**Purchase** – obtain a permanent license for long‑term projects.'
  type: HowTo
- questions:
  - answer: Configure `MhtSaveOptions` to embed attachments; the library automatically
      includes them in the MHT package.
    question: How do I handle attachments when saving emails as MHT?
  - answer: Yes, use `MhtFormatOptions.WriteHeader` and provide custom template strings
      for each header field.
    question: Can I customize email headers in the output MHT file?
  - answer: A JDK 16 or higher is required. The library works with any IDE that supports
      Maven projects.
    question: What are the system requirements for using Aspose.Email Java?
  - answer: While MHT typically contains the full message, you can manipulate `MailMessage`
      properties to exclude unwanted sections before saving.
    question: Is it possible to save only specific parts of an email message?
  - answer: Verify file paths, ensure the license is correctly applied, and consult
      the Aspose.Email [support forum](https://forum.aspose.com/c/email/10) for detailed
      assistance.
    question: How can I troubleshoot issues with email loading or saving?
  type: FAQPage
tags:
- aspose email
- mht conversion
- java email processing
- maven
title: Hur man använder en Aspose.Email-licens för att spara e-post som MHT
url: /sv/java/email-message-operations/save-emails-as-mht-using-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man använder en Aspose.Email‑licens för att spara e‑post som MHT

## Introduktion

Att hantera e‑postdata effektivt kan vara en utmaning, särskilt när det gäller delning och arkivering. I den här guiden visar vi dig **hur du sparar MHT‑filer med Maven Aspose.Email för Java med en Aspose.Email‑licens**, så att du kan konvertera e‑post till MHT med anpassade mallar och behålla kalenderhändelser intakta. Du får en färdig‑till‑körning‑lösning som fungerar i alla Java 16+‑miljöer och uppfyller licenskraven för produktionsanvändning.

## Snabba svar
- **Vilket bibliotek behöver jag?** Maven Aspose.Email för Java (v25.4+).  
- **Vilket format produceras?** En MHT (MHTML)-fil som samlar HTML, bilder och kalenderdata.  
- **Kan jag anpassa rubriken?** Ja – använd `MhtFormatOptions` och mallsträngar.  
- **Behöver jag en licens?** En Aspose.Email‑licens krävs för produktion; en gratis provversion fungerar för utvärdering.  
- **Vilken Java‑version krävs?** JDK 16 eller senare.  

## Vad är Maven Aspose.Email för Java?

Maven Aspose.Email för Java är ett bibliotek som tillhandahåller ett omfattande API för att skapa, läsa, konvertera och manipulera e‑postmeddelanden direkt från Java‑kod. Det stöder över 30 e‑postformat—inklusive MSG, EML och MHT—så att du kan hantera i princip alla e‑postfiler du stöter på.

## Varför konvertera e‑post till MHT?

MHT‑filer bäddar in alla resurser (HTML, bilder, kalenderdata) i en enda fil, vilket gör dem omedelbart visningsbara i alla moderna webbläsare utan externa tillgångar. Detta format bevarar det ursprungliga utseendet, stödjer återkommande kalenderhändelser och minskar risken för saknade bilagor vid delning.

## Förutsättningar
- **Aspose.Email för Java** (Maven‑artefakt `com.aspose:aspose-email:25.4` med `jdk16`‑klassificerare).  
- **Maven** installerat och konfigurerat på din maskin.  
- **JDK 16+** (biblioteket är avsett för Java 16).  
- En giltig **Aspose.Email‑licens**‑fil för produktionsanvändning.  
- Grundläggande kunskaper i Java (filhantering, Maven‑beroenden).

## Installera Aspose.Email för Java

### Maven‑beroende

Lägg till följande beroende i din `pom.xml`‑fil:

```xml
<dependency>
  <groupId>com.aspose</groupId>
  <artifactId>aspose-email</artifactId>
  <version>25.4</version>
  <classifier>jdk16</classifier>
</dependency>
```

### Licensanskaffning

Aspose erbjuder en gratis provversion för att utforska dess funktioner, samt alternativ för att köpa en licens eller skaffa en tillfällig.

1. **Gratis provversion** – ladda ner från [Releases](https://releases.aspose.com/email/java/) och utforska funktionerna utan begränsningar.  
2. **Tillfällig licens** – begär en fullt funktionell version via [Temporary License Page](https://purchase.aspose.com/temporary-license/).  
3. **Köp** – skaffa en permanent licens för långsiktiga projekt.

### Grundläggande initiering

När den är installerad, initiera biblioteket i din Java‑applikation:

```java
import com.aspose.email.License;

License license = new License();
license.setLicense("path/to/your/license/file");
```

Med dessa steg klara är du redo att använda Aspose.Email‑funktionerna för effektiv e‑posthantering.

## Implementeringsguide

### Funktion 1: ladda MailMessage

#### Översikt

`MailMessage` är Aspose.Email:s kärnobjekt som representerar ett e‑postmeddelande, inklusive dess rubriker, kropp, bilagor och kalenderhändelser.

#### Steg‑för‑steg

**Importera nödvändiga klasser**

```java
import com.aspose.email.MailMessage;
```

**Läs in e‑post från fil**

```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY" + "/email/";
MailMessage msg = MailMessage.load(dataDir + "Meeting with Recurring Occurrences.msg");
```

Detta kodsnutt läser in ett e‑postmeddelande som ligger i den angivna katalogen.

### Funktion 2: konfigurera MhtSaveOptions

#### Översikt

`MhtSaveOptions` konfigurerar hur Aspose.Email sparar ett `MailMessage` som en MHT‑fil, styr formatflaggor, mallar och inbäddning av resurser. Rätt konfiguration låter dig bädda in rubriker, rendera kalenderhändelser och inbädda alla bilder.

#### Steg‑för‑steg

**Importera nödvändiga klasser**

```java
import com.aspose.email.MhtSaveOptions;
import com.aspose.email.MhtFormatOptions;
import com.aspose.email.MhtTemplateName;
```

**Ställ in sparalternativ och mallar**

```java
MhtSaveOptions options = new MhtSaveOptions();
options.setMhtFormatOptions(MhtFormatOptions.WriteHeader | MhtFormatOptions.RenderCalendarEvent);

// Customize templates for email properties
for (Map.Entry<MhtTemplateName, String> entry : options.getFormatTemplates().entrySet()) {
    switch (entry.getKey()) {
        case START:
            options.getFormatTemplates().set_Item(MhtTemplateName.START,
                    "<span class='headerLineTitle'>Start:</span><span class='headerLineText'>{0}</span><br/>");
            break;
        // Add other cases similarly...
    }
}

// Ensure entries are added if absent
options.getFormatTemplates().addIfAbsent(MhtTemplateName.START,
            "<span class='headerLineTitle'>Start:</span><span class='headerLineText'>{0}</span><br/>");
```

Denna konfiguration ställer in rubriker och rendering av kalenderhändelser i MHT‑utdata.

### Funktion 3: spara MailMessage som MHT

#### Översikt

Att spara det konfigurerade `MailMessage` som en MHT‑fil skriver ett enda, självständigt dokument som kan öppnas i webbläsare eller e‑postklienter. `save`‑metoden respekterar de alternativ du definierade tidigare.

#### Steg‑för‑steg

**Importera nödvändiga klasser**

```java
import com.aspose.email.MailMessage;
import com.aspose.email.MhtSaveOptions;
```

**Spara e‑postmeddelande**

```java
msg.save("YOUR_OUTPUT_DIRECTORY" + "Meeting with Recurring Occurrences_out.mhtml", options);
```

Detta kommando skriver e‑posten till en MHT‑fil, klar för delning eller arkivering.

## Praktiska tillämpningar
- **E‑postarkivering** – Konvertera och lagra viktiga e‑postmeddelanden i ett webbvänligt format för långsiktig bevarande.  
- **Juridisk dokumentation** – Använd MHT‑filer som en del av juridiska bevis där e‑postens äkthet krävs.  
- **Plattformsoberoende delning** – Dela e‑post över plattformar utan kompatibilitetsproblem, eftersom MHT samlar allt i en fil.  

Integration med andra system—såsom CRM‑ eller projektstyrningsverktyg—kan förbättra samarbetet genom att bädda in viktig e‑postdata direkt i arbetsflöden.

## Prestandaöverväganden
Aspose.Email för Java kan bearbeta filer upp till 500 MB utan att ladda hela dokumentet i minnet, och det konverterar vanligtvis ett 100‑sidigt e‑postmeddelande med inbäddade bilder på under 2 sekunder på en standardserver. För att hålla din applikation responsiv, hantera minnesanvändning noggrant och batcha I/O‑operationer där det är möjligt.

## Vanliga problem och lösningar
`MhtFormatOptions` är en uppräkning som styr vilka element (rubriker, resurser, kalenderhändelser) som inkluderas när ett meddelande sparas som MHT.

| Problem | Orsak | Lösning |
|-------|-------|-----|
| **NullPointerException på `msg.save`** | Felaktig utskrivningssökväg | Verifiera att `YOUR_OUTPUT_DIRECTORY` finns och är skrivbar. |
| **Saknade bilder i MHT** | `MhtFormatOptions` är inte inställd på att bädda in resurser | Lägg till `MhtFormatOptions.EmbedResources` till flaggan för alternativ. |
| **Kalenderhändelser renderas inte** | `RenderCalendarEvent`‑flaggan utelämnad | Säkerställ att `options.setMhtFormatOptions(MhtFormatOptions.WriteHeader \| MhtFormatOptions.RenderCalendarEvent);` |

## Vanliga frågor

**Q: Hur hanterar jag bilagor när jag sparar e‑post som MHT?**  
A: Konfigurera `MhtSaveOptions` för att bädda in bilagor; biblioteket inkluderar dem automatiskt i MHT‑paketet.

**Q: Kan jag anpassa e‑postrubriker i den genererade MHT‑filen?**  
A: Ja, använd `MhtFormatOptions.WriteHeader` och ange anpassade mallsträngar för varje rubrikfält.

**Q: Vilka systemkrav gäller för att använda Aspose.Email Java?**  
A: En JDK 16 eller högre krävs. Biblioteket fungerar med alla IDE:n som stödjer Maven‑projekt.

**Q: Är det möjligt att spara endast specifika delar av ett e‑postmeddelande?**  
A: Även om MHT vanligtvis innehåller hela meddelandet, kan du manipulera `MailMessage`‑egenskaper för att utesluta oönskade sektioner innan du sparar.

**Q: Hur kan jag felsöka problem med inläsning eller sparande av e‑post?**  
A: Verifiera filsökvägar, säkerställ att licensen är korrekt tillämpad, och konsultera Aspose.Email‑[supportforum](https://forum.aspose.com/c/email/10) för detaljerad hjälp.

**Q: Stöder biblioteket konvertering av andra format (EML, MSG) till MHT?**  
A: Absolut. `MailMessage.load` kan läsa EML, MSG och andra stödda format, varpå du kan spara dem som MHT med samma alternativ.

## Resurser
- **Dokumentation**: För en djupare genomgång av alla funktioner, besök [Aspose Email Java Documentation](https://reference.aspose.com/email/java/).  
- **Nedladdning**: Kom igång med din gratis provversion genom att ladda ner från [Releases](https://releases.aspose.com/email/java/).  
- **Köp**: Utforska köpalternativ på den [officiella köpsidan](https://purchase.aspose.com/buy) för långsiktig användning.  
- **Gratis provversion och tillfällig licens**: Få tillgång till omfattande funktioner under en gratis provperiod eller skaffa en tillfällig licens via dessa länkar:  
  - [Free Trial](https://releases.aspose.com/email/java/)  
  - [Temporary License](https://purchase.aspose.com/temporary-license/)

Utforska, implementera och förvandla din e‑posthantering med Aspose.Email för Java redan idag!

---

**Senast uppdaterad:** 2026-09-22  
**Testat med:** Aspose.Email för Java 25.4 (jdk16‑klassificerare)  
**Författare:** Aspose  

---

## Relaterade handledningar

- [Behärska Aspose.Email för Java: Licens‑ och e‑posthanteringsguide](/email/java/getting-started/mastering-aspose-email-java-license-email-handling/)
- [Hur man konverterar MSG till MHT med Aspose.Email för Java – Steg‑för‑steg‑guide](/email/java/email-conversion-rendering/convert-mapi-messages-to-mht-aspose-email-java/)
- [Hur man sparar MSG‑e‑post med Aspose.Email för Java](/email/java/email-message-operations/aspose-email-java-create-save-emails/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}