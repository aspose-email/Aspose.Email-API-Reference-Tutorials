---
"date": "2025-05-29"
"description": "Naučte se, jak efektivně spravovat více vlastností ve zprávách MAPI pomocí Aspose.Email pro Javu. Tato příručka se zabývá nastavením typů float, double, long a dalších."
"title": "Nastavení více vlastností MAPI v Javě pomocí Aspose.Email – Komplexní průvodce"
"url": "/cs/java/mapi-operations/aspose-email-java-set-mapi-properties/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Nastavení více vlastností MAPI v Javě pomocí Aspose.Email: Komplexní průvodce

## Zavedení

Efektivní správa vlastností zpráv MAPI je klíčová pro vylepšení vašich aplikací v Javě. S Aspose.Email pro Javu můžete bez problémů nastavit více vlastností, jako například float, double, long, short, boolean a vlastní vlastnosti. Tato příručka vás provede různými metodami, jak toho dosáhnout.

**Co se naučíte:**
- Nastavení více vlastností ve zprávách MAPI pomocí Aspose.Email v Javě
- Pochopení různých typů nemovitostí a jejich využití
- Praktické příklady kódu pro implementaci

Začněme tím, že si probereme předpoklady.

## Předpoklady

Abyste mohli pokračovat, ujistěte se, že máte:
- **Vývojová sada pro Javu (JDK):** Nainstalovaný JDK 8 nebo novější.
- **Knihovna Aspose.Email:** Doporučuje se verze 25.4.
- **Nastavení Mavenu:** Maven by měl být ve vašem IDE nakonfigurován pro správu závislostí.

### Požadované knihovny

Zahrňte Aspose.Email jako závislost do svého `pom.xml`:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Získání licence
- **Bezplatná zkušební verze:** Začněte s bezplatnou zkušební verzí a prozkoumejte funkce.
- **Dočasná licence:** Získejte pro rozšířené testování bez omezení.
- **Nákup:** Pokud to vyhovuje vašim potřebám, zvažte koupi.

## Nastavení Aspose.Email pro Javu

Ujistěte se, že je Aspose.Email ve vašem vývojovém prostředí správně nakonfigurován:
1. **Závislosti importu:** Vyřešte závislosti Mavenu.
2. **Nastavit licenci:**
   - Stáhněte si licenční soubor z [Aspose](https://purchase.aspose.com/buy).
   - Aplikujte pomocí:
     ```java
     com.aspose.email.License license = new com.aspose.email.License();
     license.setLicense("path/to/your/license.lic");
     ```

Po dokončení nastavení se pojďme podívat na to, jak nastavit různé vlastnosti.

## Průvodce implementací

### Nastavení vlastností více floatů

Nastavení vlastností float umožňuje efektivní ukládání číselných dat:

#### Přehled
Tato funkce demonstruje přidání více hodnot s desetinnou čárkou jako vlastností zpráv MAPI pomocí Aspose.Email pro Javu.

#### Kroky
1. **Vytvoření a inicializace zprávy**
   ```java
   import java.util.ArrayList;
   import com.aspose.email.MapiMessage;
   import com.aspose.email.MapiProperty;
   import com.aspose.email.system.collections.IList;

   MapiMessage msg = new MapiMessage();
   ```
2. **Přidání čísel s plovoucí desetinnou čárkou do seznamu**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((float) 1);
   values.addItem((float) 2);
   ```
3. **Nastavte vlastnost s jedinečným identifikátorem**
   ```java
   msg.setProperty(new MapiProperty(0x23901004, values));
   ```
*Vysvětlení:* Štítek vlastnosti `0x23901004` identifikuje tuto sadu vlastností float.

### Nastavení více vlastností typu Double

Vlastnosti Double ukládají čísla s plovoucí desetinnou čárkou s vysokou přesností:

#### Přehled
Tato část ukazuje ukládání více hodnot typu double jako vlastností zpráv MAPI.

#### Kroky
1. **Inicializace zprávy**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Naplnit dvojité hodnoty**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((double) 1);
   values.addItem((double) 2);
   ```
3. **Přiřadit k tagu vlastnosti**
   ```java
   msg.setProperty(new MapiProperty(0x23901005, values));
   ```

### Nastavení více vlastností APPTIME

Vlastnosti APPTIME efektivně ukládají dobu trvání:

#### Přehled
Tato funkce ilustruje použití čísel s dvojitou přesností pro reprezentaci času.

#### Kroky
1. **Vytvořit objekt zprávy**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Přidat časové hodnoty**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem(30456.34);
   values.addItem(40655.45);
   ```
3. **Nastavte vlastnost**
   ```java
   msg.setProperty(new MapiProperty(0x23901007, values));
   ```

### Nastavení více dlouhých vlastností

Dlouhé vlastnosti jsou ideální pro velká celá čísla:

#### Přehled
Tato funkce se zaměřuje na nastavení více dlouhých celočíselných hodnot ve zprávě.

#### Kroky
1. **Inicializace zprávy MAPI**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Přidat dlouhé hodnoty**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((long) 30456);
   values.addItem((long) 40655);
   ```
3. **Definovat štítek vlastnosti**
   ```java
   msg.setProperty(new MapiProperty(0x23901014, values));
   ```

### Nastavení více vlastností Short

Krátké vlastnosti efektivně ukládají malá celočíselná data:

#### Přehled
Tato příručka ukazuje nastavení krátkých celých čísel jako vlastností zprávy.

#### Kroky
1. **Inicializace zprávy**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Přidat krátké hodnoty**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((short) 1);
   values.addItem((short) 2);
   ```
3. **Přiřadit štítek vlastnosti**
   ```java
   msg.setProperty(new MapiProperty(0x23901002, values));
   ```

### Nastavení více booleovských vlastností

Logické vlastnosti ukládají stavy true/false:

#### Přehled
Naučte se, jak nastavit více booleovských hodnot ve zprávě.

#### Kroky
1. **Vytvořit objekt zprávy**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Přidat booleovské hodnoty**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem(true);
   values.addItem(false);
   ```
3. **Nastavit vlastnost s identifikátorem**
   ```java
   msg.setProperty(new MapiProperty(0x2390100b, values));
   ```

### Nastavení vlastnosti Null

Explicitní nastavení vlastnosti na hodnotu null může být užitečné:

#### Přehled
Tato část ukazuje přiřazení hodnoty null vlastnosti.

#### Kroky
1. **Inicializace zprávy**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Přiřadit vlastnost Null**
   ```java
   msg.setProperty(new MapiProperty(0x67400001, new byte[1]));
   ```

### Nastavení pojmenované dlouhé vlastnosti s vlastním ID a UUID

Pro složité scénáře nastavte pojmenované vlastnosti:

#### Přehled
Tato funkce demonstruje nastavení vlastnosti typu long s vlastním identifikátorem a UUID.

#### Kroky
1. **Inicializace zprávy**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Přidat dlouhé hodnoty**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((int) 4);
   UUID uuid = UUID.randomUUID();
   ```
3. **Vytvořit a namapovat nemovitost**
   ```java
   MapiProperty property = new MapiProperty(msg.getNamedPropertyMapping().getNextAvailablePropertyId(com.aspose.email.MapiPropertyType.PT_MV_LONG), values);
   msg.getNamedPropertyMapping().addNamedPropertyMapping(property, (long) 0x00008028, uuid);
   msg.setProperty(property);
   ```

### Nastavení uživatelské vlastnosti s názvem

Vlastnosti lze pro snazší identifikaci pojmenovat:

#### Přehled
Tato příručka ukazuje nastavení vlastností s vlastním názvem.

#### Kroky
1. **Inicializace objektu zprávy**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Definovat vlastní vlastnost**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem("Custom Value");
   UUID uuid = UUID.randomUUID();
   
   MapiProperty property = new MapiProperty(msg.getNamedPropertyMapping().getNextAvailablePropertyId(com.aspose.email.MapiPropertyType.PT_STRING), values);
   msg.getNamedPropertyMapping().addNamedPropertyMapping(property, "CustomName", uuid);
   ```

### Nastavení a ověřování vlastností

Správné nastavení vlastností je klíčové:

#### Přehled
Tato část popisuje nastavení a ověřování více vlastností ve zprávách MAPI.

#### Kroky
1. **Nastavit vlastnost**
   Pro nastavení vlastnosti postupujte podle předchozích příkladů.
2. **Ověřit vlastnost**
   ```java
   if (msg.getProperties().containsKey(0x23901004)) {
       System.out.println("Property is set correctly.");
   } else {
       System.err.println("Property setting failed.");
   }
   ```

## Závěr

Tato příručka poskytla komplexní přístup ke správě více vlastností ve zprávách MAPI pomocí Aspose.Email pro Javu. Dodržováním těchto kroků můžete efektivně ukládat a spravovat různé datové typy ve svých aplikacích.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}