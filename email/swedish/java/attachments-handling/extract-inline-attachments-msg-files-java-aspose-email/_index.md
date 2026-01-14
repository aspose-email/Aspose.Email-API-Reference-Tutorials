---
date: '2025-12-17'
description: Lär dig hur du extraherar inline‑bilagor i Java och läser Outlook‑MSG
  i Java med Aspose.Email för Java. Steg‑för‑steg‑guide för att hantera Outlook‑MSG‑filer
  effektivt.
keywords:
- extract inline attachments MSG Java
- handle Outlook email formats Java
- use Aspose.Email library for Java
title: Extrahera inbäddade bilagor i Java – MSG‑filer med Aspose.Email
url: /sv/java/attachments-handling/extract-inline-attachments-msg-files-java-aspose-email/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Extrahera inbäddade bilagor i Java – MSG‑filer med Aspose.Email

## Introduktion

Om du behöver **extract inline attachments java** från Microsoft OutlookMSG‑filer, har du kommit till rätt ställe. Många utvecklare har problem med att läsa Outlookmsg‑java‑filer eftersom formatet döljer inbäddade bilder och dokument i meddelandetexten. I den här handledningen går vi igenom en ren, produktionsklar lösning som använder Aspose.Email‑biblioteket för Java för att lokalisera, identifiera och spara de inbäddade bilagorna.

När du är klar med guiden kan du:

* Ställa i Aspose.Email för Java i ett Maven‑projekt.
* **Read Outlookmsgjava**‑filer och lista deras bilagor.
* Upptäcka vilka bilagor som är inbäddade och skriva dem till disk.
* Tillämpa prestanda‑bästa praxis för massbearbetning.

## Snabba svar
- **What does “inline attachment” mean?** En bilaga som är inbäddad i e‑postens kropp (t.ex. bilder som visa i meddelandet).
- **Vilket bibliotek hanterar MSG-filer?** Aspose.Email för Java.
- **Behöver jag en licens?** En provversion fungerar för utvärdering; en permanent licens tar bort användningsbegränsningar.
- **Kan jag bearbeta många MSG-filer samtidigt?** Ja – batcha logiken och användbar trådpooler för skalbarhet.
- **Vilken Java-version krävs?** JDK16 eller senare.

## Vad är "extract inline attachments java"?

Att extrahera inbäddade bilagor i Java innebär att programmässigt öppnas en MSG‑fil, skanna dess bilagasamling och plocka ut endast de objekt som är markerade som *inline* (i motsats till vanliga filbilagor). Detta är nödvändigt när du behöver det visuella innehållet i ett e‑postmeddelande – såsom inbäddade logotyper eller skärmdumpar – sparat som separata bildfiler.

## Varför använda Aspose.Email för den här uppgiften?

Aspose.Email abstraherar de lågnivå‑MAPI‑strukturerna och ger dig ett enkelt, starkt typat API. Jämfört med att själv försöka tolka det binära MSG‑formatet erbjuder Aspose.Email:

* Hanterar alla MSG-varianter (Unicode, RTF, HTML).
* Tillhandahåller pålitlig egenskapsåtkomst för bilagors metadata.
* Erbjuder inbyggda licenskontroller och omfattande dokumentation.

## Förutsättningar

För att följa med, säkerställt att du har:

1. **Bibliotek och beroenden** 
* Aspose.Email för Java (senaste versionen). 
* Maven (eller en IDE med Maven‑stöd).

2. **Körtid** 
* JDK16 eller nyare installerat.

3. **Grundläggande kunskap** 
* Bekantskap med Java I/O och undantagshantering.

## Konfigurera Aspose.Email för Java

Lägg till Aspose.Email‑beroendet i din `pom.xml`. Koden nedan är oförändrad från den ursprungliga handledningen.

```xml
<dependency>
  <groupId>com.aspose</groupId>
  <artifactId>aspose-email</artifactId>
  <version>25.4</version>
  <classifier>jdk16</classifier>
</dependency>
```

### Licensförvärvssteg

* **Gratis provperiod:** Ladda ner prov-DLL/JAR från Aspose-webbplatsen.
* **Temporary License:** Begär en 30‑dagars utvärderingslicens för obegränsad testning.
* **Fullt köp:** Skaffa en permanent licens för produktionsdistributioner.

## Implementeringsguide

Nedan delar vi upplösningen i tre funktioner. Varje funktion innehåller en kort förklaring följt av den ursprungliga kodblocket (behåller exakt format).

### Funktion 1 – Ladda MSG-filen

Först laddas Outlook‑meddelandet i ett `MapiMessage`‑objekt.

```java
import com.aspose.email.MapiMessage;

String dataDir = "YOUR_DOCUMENT_DIRECTORY/email/";
MapiMessage message = MapiMessage.fromFile(dataDir + "MSG file with RTF Formatting.msg");
```

### Funktion 2 – Hämta bilagor

Därefter hämtas hela bilagssamlingen från meddelandet.

```java
import com.aspose.email.MapiAttachmentCollection;

MapiAttachmentCollection attachments = message.getAttachments();
```

### Funktion 3 – Identifiera och spara inline-bilagor

Loopar igenom varje bilaga, kontrollerar om den är inbäddad och skriver sedan den till disk.

```java
for (Object untypedAttachment : attachments) {
    MapiAttachment attachment = (MapiAttachment) untypedAttachment;
    if (IsAttachmentInline(attachment)) {
        try {
            SaveAttachment(attachment, UUID.randomUUID().toString());
        } catch (IOException e) {
            // Handle exception
        }
    }
}
```

#### Verktyg: Bestäm om en bilaga är inline

Hjälpmetoden inspekterar MAPI‑egenskaperna för att avgöra om en bilaga är inbäddad.

```java
import com.aspose.email.MapiAttachment;
import com.aspose.email.MapiObjectProperty;
import com.aspose.email.MapiProperty;

static boolean IsAttachmentInline(MapiAttachment attachment) {
    MapiObjectProperty objectData = attachment.getObjectData();
    if (objectData == null) return false;

    for (Object prop : attachment.getObjectData().getProperties().getValues()) {
        MapiProperty property = (MapiProperty) prop;
        if ("\u0003ObjInfo".equals(property.getName())) {
            byte[] data = property.getData();
            int odtPersist1 = data[1] << 8 | data[0];
            return (odtPersist1 & 0x40) == 0;
        }
    }
    return false;
}
```

#### Verktyg: Spara den inbyggda bilagan

Skriver det binära innehållet för den inbäddade bilagan till en fil på det lokala filsystemet.

```java
import com.aspose.email.MapiAttachment;
import java.io.FileOutputStream;
import java.io.IOException;

static void SaveAttachment(MapiAttachment attachment, String fileName) throws IOException {
    for (Object prop : attachment.getObjectData().getProperties().getValues()) {
        MapiProperty property = (MapiProperty) prop;
        if ("Package".equals(property.getName())) {
            try (FileOutputStream fs = new FileOutputStream(fileName)) {
                fs.write(property.getData(), 0, property.getData().length);
            }
        }
    }
}
```

## Praktiska tillämpningar

Att extrahera inbäddade bilagor är användbart i många verkliga scenarier:

* **Automatiserad e-postbehandling** – Hämta bilder från nyhetsbrev för analys.
* **Datamigrering** – Flytta inbäddat innehåll vid migrering från Exchange till en annan plattform.
* **Archiving Solutions** – Bevara den visuella integriteten i arkiverade meddelanden genom att lagra inbäddade resurser separat.

## Prestandaöverväganden

När du hanterar hundratals eller tusentals MSG‑filer, tänk på följande tips:

* **Batch Processing:** Gruppera filer i hanterbara batcher för att undvika minnesspikar.
* **Skicka resurser omgående:** Stäng strömmar (`prova-med-resurser`) och låt skräpsamlaren återvinna objekt.
* **Parallell Execution:** Använd en `ExecutorService` med snabb storlek för att köra flera extraktionsjobb parallellt, men övervaka CPU‑användning.

## Vanliga problem och felsökning

| Symptom | Trolig orsak | Fixa |
|--------|--------------|-----|
| `NullPointerException` på `attachment.getObjectData()` | Meddelandet saknar bifogad metadata (t.ex. skadad MSG) | Validera MSG-filen innan bearbetning eller fånga undantaget och logga filnamnet. |
| Sparad fil är tom eller skadad | Felaktigt egenskapsnamn (`"Package"` skiftlägeskänslighet) | Verifiera att egenskapsnamnet matchar MSG:s faktiska egenskap; Aspose.Email-dokumentationen listar den exakta strängen. |
| Prestandan försämras med stora filer | Strömmar stängs inte, vilket leder till minnesläckor | Använd try-with-resources (som visas) och överväg att öka JVM-heapen om det behövs. |

## Vanliga frågor

**F: Vilken Aspose.Email-version krävs minst?**
S: Handledningen använder version 25.4, men alla 24.x+-versioner som stöder JDK16 fungerar.

**F: Kan jag extrahera inline-bilagor från krypterade MSG-filer?**
S: Ja, förutsatt att du anger rätt dekrypteringslösenord när du laddar `MapiMessage`.

**F: Hur skiljer jag mellan inline-bilder och vanliga filbilagor?**
S: Använd `IsAttachmentInline`-hjälpen; den kontrollerar MAPI `ObjInfo`-flaggan som markerar en bilaga som inline.

**F: Finns det ett sätt att bevara det ursprungliga filnamnet på den inbäddade bilagan?**
S: Exemplet genererar ett UUID för unikhet, men du kan läsa egenskapen `attachment.getLongFileName()` och använda den när du anropar `SaveAttachment`.

**F: Fungerar den här metoden på Linux/macOS såväl som Windows?**
S: Absolut—Aspose.Email är plattformsoberoende så länge JDK är installerat.

## Resurser
- **Dokumentation:** [Aspose Email Documentation](https://docs.aspose.com/email/java/)

---

**Senast uppdaterad:** 2025-12-17
**Testad med:** Aspose.Email för Java 25.4 (JDK16)
**Författare:** Aspose 

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}