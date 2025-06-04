---
"date": "2025-05-29"
"description": "Lär dig hur du effektivt hanterar flera egenskaper i MAPI-meddelanden med Aspose.Email för Java. Den här guiden beskriver hur du ställer in float, double, long och fler typer."
"title": "Ställ in flera MAPI-egenskaper i Java med Aspose.Email&#50; En omfattande guide"
"url": "/sv/java/mapi-operations/aspose-email-java-set-mapi-properties/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Ställ in flera MAPI-egenskaper i Java med Aspose.Email: En omfattande guide

## Introduktion

Att hantera MAPI-meddelandeegenskaper effektivt är avgörande för att förbättra dina Java-applikationer. Med Aspose.Email för Java kan du sömlöst ställa in flera egenskaper, till exempel float, double, long, short, booleska och anpassade egenskaper. Den här guiden guidar dig genom olika metoder för att uppnå detta.

**Vad du kommer att lära dig:**
- Ställa in flera egenskaper i MAPI-meddelanden med Aspose.Email Java
- Förstå olika fastighetstyper och deras användningsområden
- Praktiska kodexempel för implementering

Låt oss börja med att täcka förutsättningarna.

## Förkunskapskrav

För att följa med, se till att du har:
- **Java-utvecklingspaket (JDK):** JDK 8 eller senare installerat.
- **Aspose.Email-bibliotek:** Version 25.4 rekommenderas.
- **Maven-inställningar:** Maven bör konfigureras i din IDE för beroendehantering.

### Obligatoriska bibliotek

Inkludera Aspose.Email som ett beroende i din `pom.xml`:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Licensförvärv
- **Gratis provperiod:** Börja med en gratis provperiod för att utforska funktioner.
- **Tillfällig licens:** Erhåll för utökad testning utan begränsningar.
- **Köpa:** Överväg att köpa om det passar dina behov.

## Konfigurera Aspose.Email för Java

Se till att Aspose.Email är korrekt konfigurerat i din utvecklingsmiljö:
1. **Importberoenden:** Lös Maven-beroenden.
2. **Ställ in licens:**
   - Ladda ner en licensfil från [Aspose](https://purchase.aspose.com/buy).
   - Applicera det med hjälp av:
     ```java
     com.aspose.email.License license = new com.aspose.email.License();
     license.setLicense("path/to/your/license.lic");
     ```

När installationen är klar, låt oss utforska hur man ställer in olika egenskaper.

## Implementeringsguide

### Ställa in flera flytande egenskaper

Att ställa in flyttalsegenskaper möjliggör effektiv lagring av numeriska data:

#### Översikt
Den här funktionen demonstrerar hur man lägger till flera flyttal som MAPI-meddelandeegenskaper med hjälp av Aspose.Email för Java.

#### Steg
1. **Skapa och initiera meddelandet**
   ```java
   import java.util.ArrayList;
   import com.aspose.email.MapiMessage;
   import com.aspose.email.MapiProperty;
   import com.aspose.email.system.collections.IList;

   MapiMessage msg = new MapiMessage();
   ```
2. **Lägg till flyttalvärden i en lista**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((float) 1);
   values.addItem((float) 2);
   ```
3. **Ange egenskapen med en unik identifierare**
   ```java
   msg.setProperty(new MapiProperty(0x23901004, values));
   ```
*Förklaring:* Egenskapstaggen `0x23901004` identifierar denna float-egenskapsuppsättning.

### Ställa in flera dubbelegenskaper

Dubbelegenskaper lagrar flyttal med hög precision:

#### Översikt
Det här avsnittet visar hur man lagrar flera dubbelvärden som MAPI-meddelandeegenskaper.

#### Steg
1. **Initiera meddelandet**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Fyll i dubbla värden**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((double) 1);
   values.addItem((double) 2);
   ```
3. **Tilldela till egenskapstagg**
   ```java
   msg.setProperty(new MapiProperty(0x23901005, values));
   ```

### Ställa in flera APPTIME-egenskaper

APPTIME-egenskaper lagrar tidslängder effektivt:

#### Översikt
Den här funktionen illustrerar användningen av dubbel precisionstal för tidsrepresentationer.

#### Steg
1. **Skapa meddelandeobjekt**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Lägg till tidsvärden**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem(30456.34);
   values.addItem(40655.45);
   ```
3. **Ange egenskapen**
   ```java
   msg.setProperty(new MapiProperty(0x23901007, values));
   ```

### Ställa in flera långa egenskaper

Långa egenskaper är idealiska för stora heltal:

#### Översikt
Den här funktionen fokuserar på att ange flera långa heltalsvärden i ett meddelande.

#### Steg
1. **Initiera MAPI-meddelande**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Lägg till långa värden**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((long) 30456);
   values.addItem((long) 40655);
   ```
3. **Definiera egenskapstagg**
   ```java
   msg.setProperty(new MapiProperty(0x23901014, values));
   ```

### Ställa in flera korta egenskaper

Korta egenskaper lagrar små heltalsdata effektivt:

#### Översikt
Den här guiden visar hur man ställer in korta heltal som meddelandeegenskaper.

#### Steg
1. **Initiera meddelandet**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Lägg till korta värden**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((short) 1);
   values.addItem((short) 2);
   ```
3. **Tilldela egenskapstagg**
   ```java
   msg.setProperty(new MapiProperty(0x23901002, values));
   ```

### Ställa in flera booleska egenskaper

Booleska egenskaper lagrar sanna/falska tillstånd:

#### Översikt
Lär dig hur du anger flera booleska värden i ett meddelande.

#### Steg
1. **Skapa meddelandeobjekt**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Lägg till booleska värden**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem(true);
   values.addItem(false);
   ```
3. **Ange egenskap med identifierare**
   ```java
   msg.setProperty(new MapiProperty(0x2390100b, values));
   ```

### Ställa in en null-egenskap

Att explicit ange en egenskap som null kan vara användbart:

#### Översikt
Det här avsnittet visar hur man tilldelar ett nullvärde till en egenskap.

#### Steg
1. **Initiera meddelandet**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Tilldela null-egenskap**
   ```java
   msg.setProperty(new MapiProperty(0x67400001, new byte[1]));
   ```

### Ställa in namngiven lång egenskap med anpassat ID och UUID

För komplexa scenarier, ange namngivna egenskaper:

#### Översikt
Den här funktionen demonstrerar att du ställer in en lång egenskap med en anpassad identifierare och UUID.

#### Steg
1. **Initiera meddelandet**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Lägg till långa värden**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((int) 4);
   UUID uuid = UUID.randomUUID();
   ```
3. **Skapa och mappa egendom**
   ```java
   MapiProperty property = new MapiProperty(msg.getNamedPropertyMapping().getNextAvailablePropertyId(com.aspose.email.MapiPropertyType.PT_MV_LONG), values);
   msg.getNamedPropertyMapping().addNamedPropertyMapping(property, (long) 0x00008028, uuid);
   msg.setProperty(property);
   ```

### Ställa in anpassad egenskap med namn

Anpassade egenskaper kan namnges för enklare identifiering:

#### Översikt
Den här guiden visar hur du anger anpassade namngivna egenskaper.

#### Steg
1. **Initiera meddelandeobjekt**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Definiera anpassad egenskap**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem("Custom Value");
   UUID uuid = UUID.randomUUID();
   
   MapiProperty property = new MapiProperty(msg.getNamedPropertyMapping().getNextAvailablePropertyId(com.aspose.email.MapiPropertyType.PT_STRING), values);
   msg.getNamedPropertyMapping().addNamedPropertyMapping(property, "CustomName", uuid);
   ```

### Ställa in och validera egenskaper

Det är avgörande att egenskaperna är korrekt inställda:

#### Översikt
Det här avsnittet behandlar hur man konfigurerar och validerar flera egenskaper i MAPI-meddelanden.

#### Steg
1. **Ange egenskap**
   Följ tidigare exempel för att ange en egenskap.
2. **Validera egenskap**
   ```java
   if (msg.getProperties().containsKey(0x23901004)) {
       System.out.println("Property is set correctly.");
   } else {
       System.err.println("Property setting failed.");
   }
   ```

## Slutsats

Den här guiden gav en omfattande metod för att hantera flera egenskaper i MAPI-meddelanden med hjälp av Aspose.Email för Java. Genom att följa dessa steg kan du effektivt lagra och hantera olika datatyper i dina applikationer.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}