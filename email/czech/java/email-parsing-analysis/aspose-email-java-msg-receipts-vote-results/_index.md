---
date: '2026-06-13'
description: Naučte se, jak číst soubory MSG a zpracovávat přílohy MSG pomocí Aspose.Email
  for Java, efektivně extrahovat doručovací/potvrzovací zprávy a výsledky hlasování.
  Obsahuje nastavení, kód a osvědčené postupy.
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
title: Jak číst soubory MSG s Aspose.Email for Java
url: /cs/java/email-parsing-analysis/aspose-email-java-msg-receipts-vote-results/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak číst soubory MSG pomocí Aspose.Email pro Java

## Úvod

Programatické čtení souborů MSG vám umožní získat cenná sledovací data—doručovací potvrzení, potvrzení o přečtení a výsledky hlasování—z Outlookových zpráv. V tomto průvodci ukážeme **jak číst msg** soubory pomocí Aspose.Email pro Java, projdeme požadované nastavení a ukážeme, jak efektivně extrahovat informace o doručení a hlasování.

## Rychlé odpovědi
- **Jaká knihovna zpracovává parsování MSG?** Aspose.Email pro Java.  
- **Mohu extrahovat potvrzení o přečtení?** Ano, API vrací časové razítka doručení a přečtení.  
- **Jsou data o hlasování přístupná?** Rozhodně; můžete získat hlasovací odpověď každého příjemce.  
- **Potřebuji licenci?** Zkušební verze funguje pro testování; placená licence odstraňuje omezení hodnocení.  
- **Která verze Javy je vyžadována?** Doporučuje se Java 16 nebo novější.

## Co je Aspose.Email pro Java?

Aspose.Email pro Java je samostatná knihovna Java, která umožňuje vytváření, manipulaci a konverzi e‑mailových formátů bez potřeby Microsoft Outlook. Poskytuje bohatý objektový model pro MSG, EML, PST a mnoho dalších formátů, což vývojářům umožňuje pracovat s e‑mailovými daty přímo z Java kódu. (45 words)

## Proč používat Aspose.Email pro Java k čtení souborů MSG?

Aspose.Email pro Java podporuje **více než 30 e‑mailových formátů** a dokáže zpracovat soubory MSG až do **500 MB** bez načítání celého souboru do paměti. Jeho vysoce výkonný parsovací engine snižuje spotřebu CPU a paměti, což jej činí ideálním pro zpracování velkorozsáhlých e‑mailových archivů a scénáře analýzy v reálném čase. (48 words)

## Předpoklady

- **Knihovny a závislosti:** Aspose.Email pro Java verze 25.4 nebo novější a runtime JDK 16+.  
- **IDE:** IntelliJ IDEA, Eclipse nebo jakékoli Java‑kompatibilní IDE s podporou Maven.  
- **Základní dovednosti:** Znalost syntaxe Javy a objektově orientovaných konceptů.

## Získání licence

Pro použití Aspose.Email pro Java potřebujete licenci:

- **Bezplatná zkušební verze:** Začněte s bezplatnou zkušební verzí dostupnou na [webu Aspose](https://releases.aspose.com/email/java/).  
- **Dočasná licence:** Požádejte o dočasnou licenci na [stránce nákupu](https://purchase.aspose.com/temporary-license/).  
- **Nákup:** Pokud jste s hodnocením spokojeni, zakupte licenci pro plný přístup ke všem funkcím prostřednictvím stránky [Buy Aspose Products](https://purchase.aspose.com/buy).

## Jak extrahovat informace o potvrzení o přečtení a doručení ze souboru MSG?

Načtěte soubor MSG, projděte jeho příjemce a přečtěte vlastnosti `DeliveryTime` a `ReadTime`. Tento přístup vrací přesná časová razítka, kdy poštovní server každého příjemce doručil zprávu a kdy ji příjemce otevřel, což vám poskytne přesná sledovací data pro analýzu. (53 words)

### Krok 1: Načtení souboru MSG
MapiMessage je třída Aspose.Email, která představuje Outlook zprávu MSG.  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```  

### Krok 2: Procházení příjemců
MapiRecipient představuje jednoho příjemce (To, CC nebo BCC) v souboru MSG.  
```java
import com.aspose.email.MapiMessage;
import com.aspose.email.MapiRecipient;
import com.aspose.email.MapiPropertyTag;

public class RetrieveReceipts {
    public static void main(String[] args) {
        String dataDir = "YOUR_DOCUMENT_DIRECTORY/outlook/";
        MapiMessage msg = MapiMessage.fromFile(dataDir + "message.msg");
```  

### Krok 3: Získání a výpis času doručení
DeliveryTime je vlastnost MapiRecipient, která obsahuje časové razítko, kdy byla zpráva doručena na server příjemce.  
```java
        for (MapiRecipient recipient : msg.getRecipients()) {
            System.out.println("Recipient: " + recipient.getDisplayName());
```  

### Krok 4: Získání a výpis času přečtení
ReadTime je vlastnost MapiRecipient, která uvádí, kdy příjemce zprávu otevřel, pokud jsou tyto informace dostupné.  
```java
            System.out.println("Delivery time: " + 
                recipient.getProperties().get_Item(MapiPropertyTag.PR_RECIPIENT_TRACKSTATUS_TIME_DELIVERY).getDateTime());
```  

## Jak číst výsledky hlasování ze souboru MSG?

Po načtení zprávy API odhalí hlasovací odpověď každého příjemce a čas, kdy odpověděl, což vám umožní programově agregovat výsledky ankety. Tato data lze použít k vytvoření souhrnných zpráv nebo přímo napojit na dashboardy business intelligence pro rychlé rozhodování. (53 words)

### Krok 1: Načtení souboru MSG
MapiMessage se opět používá k přístupu k hlasovacím informacím vloženým do souboru MSG.  
```java
            System.out.println("Read time: " + 
                recipient.getProperties().get_Item(MapiPropertyTag.PR_RECIPIENT_TRACKSTATUS_TIME_READ).getDateTime());
        }
    }
}
```  

### Krok 2: Procházení příjemců
MapiRecipient poskytuje přístup k hlasovacímu výběru každého účastníka a času odpovědi.  
```java
import com.aspose.email.MapiMessage;
import com.aspose.email.MapiRecipient;
import com.aspose.email.MapiPropertyTag;

public class ReadVoteResults {
    public static void main(String[] args) {
        String dataDir = "YOUR_DOCUMENT_DIRECTORY/outlook/";
        MapiMessage msg = MapiMessage.fromFile(dataDir + "message.msg");
```  

### Krok 3: Získání a výpis odpovědi
Vlastnost `VotingResponse` obsahuje skutečný hlas (např. „Accept“, „Decline“ nebo vlastní možnosti).  
```java
        for (MapiRecipient recipient : msg.getRecipients()) {
            System.out.println("Recipient: " + recipient.getDisplayName());
```  

### Krok 4: Získání a výpis času odpovědi
`VotingResponseTime` zaznamenává, kdy příjemce odeslal svůj hlas, což umožňuje chronologickou analýzu aktivity ankety.  
```java
            System.out.println("Response: " + 
                recipient.getProperties().get_Item(MapiPropertyTag.PR_RECIPIENT_AUTORESPONSE_PROP_RESPONSE).getString());
```  

## Praktické aplikace

1. **Sledování e‑mailových kampaní:** Měření míry otevření a úspěšnosti doručení analýzou časových razítek potvrzení.  
2. **Analýza průzkumů:** Konsolidace výsledků hlasování z Outlookových anket pro rychlé rozhodování.  
3. **Řízení zpětné vazby zákazníků:** Přenášení dat o odpovědích do CRM nebo analytických platforem pro hlubší poznatky.

Integrace těchto extrahovaných dat s databázemi nebo nástroji BI zvyšuje hodnotu surových e‑mailových dat.

## Úvahy o výkonu

- Zpracovávejte velké soubory MSG v **částech**, aby byl nízký odběr paměti.  
- Používejte **streamovací API**, když pracujete s tisíci zprávami.  
- Ukládejte data příjemců v lehkých kolekcích, jako jsou `ArrayList` nebo `HashMap`, pro rychlé vyhledávání.

## Časté problémy a řešení

- **Null časová razítka:** Chybějící `ReadTime` obvykle znamená, že příjemce zprávu ještě neotevřel.  
- **Velké přílohy:** Pokud MSG obsahuje obrovské přílohy, povolte `LoadOptions.setPreserveEmbeddedResources(false)`, aby se nepřekládaly do paměti.  
- **Problémy s kódováním:** Ujistěte se, že je nastavena správná kódová stránka pomocí `MailMessage.setCharset(Charset.forName("UTF-8"))` při čtení ne‑ASCII obsahu.

## Často kladené otázky

**Q: Jak mohu pracovat se soubory MSG většími než 500 MB?**  
A: Rozdělte soubor na menší segmenty nebo použijte streamingové API k načtení částí bez úplného načtení do paměti.

**Q: Mohu uložit extrahovaná data přímo do databáze?**  
A: Ano, namapujte pole pro potvrzení a hlasování do schématu DB a použijte JDBC nebo ORM k jejich uložení.

**Q: Funguje knihovna v Linuxových prostředích?**  
A: Rozhodně; Aspose.Email pro Java je platformově nezávislý a běží na jakémkoli OS s podporovaným JDK.

**Q: Existuje způsob, jak extrahovat přílohy při čtení potvrzení?**  
A: Použijte `MailMessage.getAttachments()` po načtení MSG; metoda vrací kolekci všech vložených souborů.

**Q: Jaké možnosti podpory jsou k dispozici, pokud narazím na chyby?**  
A: Kontaktujte oficiální Aspose Email Forum pro komunitní pomoc nebo otevřete support ticket s platnou licencí.

## Zdroje
- **Dokumentace:** [Aspose Email Documentation](https://reference.aspose.com/email/java/)  
- **Dokumentace (duplikát):** [Aspose Email Documentation](https://reference.aspose.com/email/java/)  
- **Stáhnout SDK:** [Aspose Email Downloads](https://releases.aspose.com/email/java/)  
- **Sekce ke stažení:** [Download Section](https://releases.aspose.com/email/java/)  
- **Zakoupit licenci:** [Buy Aspose Products](https://purchase.aspose.com/buy)  
- **Bezplatná zkušební verze:** Začněte s [Free Trial Version](https://releases.aspose.com/email/java/)  
- **Dočasná licence:** [Request Temporary License](https://purchase.aspose.com/temporary-license/)  
- **Fórum podpory:** [Aspose Email Forum](https://forum.aspose.com/c/email/10)  
- **Fórum podpory (duplikát):** [Aspose Email Forum](https://forum.aspose.com/c/email/10)

---

**Poslední aktualizace:** 2026-06-13  
**Testováno s:** Aspose.Email pro Java 25.4  
**Autor:** Aspose

```java
            System.out.println("Response time: " + 
                recipient.getProperties().get_Item(MapiPropertyTag.PR_RECIPIENT_TRACKSTATUS_TIME).getDateTime());
        }
    }
}
```

## Související tutoriály

- [Jak načíst a parsovat Outlook MSG soubory pomocí Aspose.Email pro Java: komplexní průvodce](/email/java/mapi-operations/outlook-msg-aspose-email-java-guide/)
- [Převod MSG na EML a správa příloh pomocí Aspose.Email pro Java](/email/java/attachments-handling/aspose-email-java-master-msg-attachments-parsing/)
- [Extrahovat vložené přílohy v Javě – MSG soubory s Aspose.Email](/email/java/attachments-handling/extract-inline-attachments-msg-files-java-aspose-email/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}