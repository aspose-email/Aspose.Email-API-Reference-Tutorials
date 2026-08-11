---
date: '2026-07-27'
description: Naučte se, jak nastavit příznak Outlook v Java pomocí Aspose.Email pro
  Java, včetně vytváření příznaků, příznaků pro příjemce, dokončení, odebrání a možností
  čtení.
keywords:
- set outlook flag java
- outlook follow up flag java
- aspose email java
lastmod: '2026-07-27'
og_description: Nastavte příznak Outlook v Java s Aspose.Email pro Java. Tento průvodce
  ukazuje, jak efektivně vytvářet, číst, dokončovat a odstraňovat Outlook follow‑up
  flags.
og_image_alt: 'Developer guide: Set Outlook flag Java using Aspose.Email'
og_title: Nastavení příznaku Outlook v Java – Kompletní průvodce programováním Aspose.Email
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
title: Nastavení příznaku Outlook v Java – Kompletní průvodce programováním Aspose.Email
url: /cs/java/calendar-appointments/aspose-email-java-outlook-follow-up-flags/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Nastavení Outlook vlajky v Javě pomocí Aspose.Email pro Java

## Úvod
Pokud potřebujete **set outlook flag java** programově, jste na správném místě. Follow‑up vlajka v Outlooku převádí běžný e‑mail na sledovaný úkol a Aspose.Email pro Java vám umožní spravovat tyto vlajky bez nainstalovaného Outlooku. V tomto tutoriálu projdeme vytvoření, čtení, dokončení a nakonec odstranění vlajek, plus jak aplikovat vlajky pro konkrétní příjemce. Na konci budete mít znovupoužitelný úryvek Java kódu, který automatizuje sledování úkolů přímo z vašich backendových služeb.

## Rychlé odpovědi
- **Co znamená “set outlook flag java”?** Přidání vlajky s datem zahájení, připomenutím a termínem do položky Outlooku pomocí Java kódu.  
- **Která knihovna je vyžadována?** Aspose.Email for Java (v25.4 nebo novější).  
- **Potřebuji licenci?** Ano – zkušební verze funguje pro hodnocení, ale pro produkci je vyžadována zakoupená licence.  
- **Mohu nastavit vlajky pouze pro příjemce?** Ano – použijte `FollowUpManager.setFlagForRecipients`.  
- **Je možné vlajku později odstranit?** Ano – zavolejte `FollowUpManager.clearFlag`.

## Co je Outlook Follow‑Up vlajka?
Outlook follow‑up vlajka je vestavěný označovač úkolu, který může k libovolné poštovní položce přiřadit datum zahájení, připomenutí a termín. Přemění e‑mail na sledovaný akční úkol, což vám i vašemu týmu pomáhá udržet přehled o nevyřízené práci.

## Proč použít Aspose.Email pro Java?
Aspose.Email pro Java podporuje **70+ e‑mailových formátů** (včetně MSG, EML, MHTML a TNEF) a dokáže zpracovat **více než 100 000 zpráv za minutu** na typickém 8‑jádrovém serveru, a to vše bez potřeby Outlooku na hostitelském stroji. To ho činí ideálním pro backendovou automatizaci, reportování o souladu a integraci s nástroji pro řízení projektů.

## Požadavky
- **Aspose.Email for Java** verze 25.4 nebo novější.  
- **Nainstalovaný JDK 16+**.  
- IDE kompatibilní s Maven (IntelliJ IDEA, Eclipse atd.).  
- Základní znalost Javy a povědomí o e‑mailových konceptech.

## Nastavení Aspose.Email pro Java
### Maven konfigurace
Přidejte následující závislost do vašeho `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Získání licence
Aspose.Email vyžaduje licenci pro produkční použití:

- **Bezplatná zkušební verze** – 30‑denní hodnocení.  
- **Dočasná licence** – rozšířené testování.  
- **Plná licence** – trvalé předplatné.

Inicializujte licenci před jakoukoliv e‑mailovou operací:

```java
License license = new License();
license.setLicense("path/to/Aspose.Total.Java.lic");
```

## Nastavení Outlook vlajky v Javě (Funkce 1)
### Přímá odpověď
Načtěte `MailMessage`, převedete ji na `MapiMessage`, nakonfigurujete `FollowUpOptions` a zavoláte `FollowUpManager.setOptions`. Tento postup vytvoří plně označenou položku Outlooku během několika řádků Java kódu.

### Krok 1: Vytvoření a inicializace zprávy
`MailMessage` je vysokou úrovní třída Aspose.Email, která představuje e‑mail. Po vytvoření zprávy ji převedete na `MapiMessage` pro manipulaci s vlajkou.

```java
MailMessage mailMsg = new MailMessage();
mailMsg.setSender(new MailAddress("AETest12@gmail.com"));
mailMsg.getTo().addMailAddress(new MailAddress("receiver@gmail.com"));
mailMsg.setBody("This message will test if follow up options can be added to a new mapi message.");
MapiMessage mapi = MapiMessage.fromMailMessage(mailMsg);
```
*Nejprve vytvoříme `MailMessage`, nastavíme odesílatele/příjemce a poté ji převedeme na `MapiMessage` pro manipulaci s vlajkou.*

### Krok 2: Definování dat pro Follow‑Up (Outlook připomenutí vlajky)
`FollowUpOptions` obsahuje datum zahájení, připomenutí a termín. Použijte `Calendar` z Javy k nastavení přesných časových razítek.

```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 14, 40, 0);
Date dtStartDate = calendar.getTime();
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
calendar.add(Calendar.DATE, 1);
Date dtDueDate = calendar.getTime();
```
*Zde nastavujeme datum zahájení, připomenutí (the **outlook flag reminder**) a termín pomocí třídy `Calendar`.*

### Krok 3: Použití možností Follow‑Up
Metoda `FollowUpManager.setOptions` připojí vlajku k `MapiMessage`.

```java
FollowUpOptions options = new FollowUpOptions("Follow Up", dtStartDate, dtDueDate, dtReminderDate);
FollowUpManager.setOptions(mapi, options);
```
*Objekt `FollowUpOptions` obsahuje všechny podrobnosti vlajky, které aplikujeme pomocí `FollowUpManager.setOptions`.*

### Krok 4: Uložení zprávy
Uložte označenou zprávu jako soubor `.msg`, aby ji Outlook mohl zobrazit s vlajkou.

```java
mapi.save(outputDir + "SetFollowUpflag_out.msg");
```
*Zpráva je uložena jako soubor `.msg` s připojenou vlajkou.*

## Jak nastavit vlajku pro příjemce (Funkce 2)?
Použijte `FollowUpManager.setFlagForRecipients` po označení zprávy jako konceptu. Tato metoda přidá follow‑up vlajku pouze do kopie příjemce, aniž by změnila pohled odesílatele. Vyžaduje nastavení `MessageFlags.MSGFLAG_UNSENT` před aplikací vlajky. Můžete také přizpůsobit datum zahájení, připomenutí a termín pomocí objektu `FollowUpOptions` před voláním metody.

### Přímá odpověď
Označte zprávu jako koncept pomocí `MessageFlags.MSGFLAG_UNSENT` a poté zavolejte `FollowUpManager.setFlagForRecipients`. Outlook zobrazí vlajku pouze příjemcům, ne odesílateli.

### Přehled
Někdy potřebujete, aby se vlajka objevila **only for recipients**. Tento příklad nejprve označí zprávu jako koncept a pak přidá vlajku.

#### Krok 1: Označení jako koncept
`MessageFlags` je výčtová hodnota MAPI, která řídí stav zprávy. Nastavení `MSGFLAG_UNSENT` říká Outlooku, že položka je koncept.

```java
mapi.setMessageFlags(MapiMessageFlags.MSGFLAG_UNSENT);
```
*Označení zprávy jako neodeslané zajišťuje, že Outlook ji bude považovat za koncept.*

#### Krok 2: Nastavení vlajky pro příjemce
`FollowUpManager.setFlagForRecipients` připojí vlajku výhradně k kopii příjemce.

```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
FollowUpManager.setFlagForRecipients(mapi, "Follow up", dtReminderDate);
```
*Vlajka je nyní viditelná pouze pro příjemce – klasický **flag for recipients** scénář.*

## Jak označit Outlook Follow Up vlajku jako dokončenou (Funkce 3)?
Načtěte soubor .msg do `MapiMessage` a poté zavolejte `FollowUpManager.completeFlag`. Tím se stav vlajky aktualizuje na „Completed“ a v Outlooku se zobrazí zaškrtnutí. Po dokončení zprávu uložte, aby se změna zachovala. Můžete také nastavit čas dokončení úpravou vlastnosti `FlagCompleteTime`, pokud je to potřeba pro audit.

### Přímá odpověď
Načtěte existující soubor `.msg` do `MapiMessage`, zavolejte `FollowUpManager.completeFlag` a soubor uložte. Stav vlajky se změní na „Completed“ a v Outlooku se zobrazí se zaškrtnutím.

### Krok 1: Načtení zprávy
`MapiMessage` dokáže načíst uložený soubor `.msg` a poskytuje plný přístup k jeho MAPI vlastnostem.

```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
```

### Krok 2: Označení jako dokončené a uložení
`FollowUpManager.completeFlag` aktualizuje stav vlajky, poté změny uložíte.

```java
FollowUpManager.markAsCompleted(mapi);
mapi.save(outputDir + "MarkedCompleted_out.msg");
```
*Stav vlajky se změní na „Completed“ a aktualizovaný soubor je uložen.*

## Jak odstranit Outlook Follow Up vlajku (Funkce 4)?
Otevřete soubor `.msg` pomocí `MapiMessage`, zavolejte `FollowUpManager.clearFlag` a poté zprávu uložte. Tím se odstraní všechny MAPI vlastnosti související s vlajkou, takže Outlook již nebude zobrazovat žádný follow‑up indikátor. Použijte to, když je úkol zrušen nebo již není relevantní. Ujistěte se, že také vymažete jakékoli vlastní vlastnosti připomenutí, aby nedocházelo k zbytkovým upozorněním.

### Přímá odpověď
Otevřete soubor `.msg` pomocí `MapiMessage`, zavolejte `FollowUpManager.clearFlag` a soubor uložte. Zpráva již v Outlooku nebude zobrazovat žádný follow‑up indikátor.

### Krok 1: Načtení a vymazání vlajky
`FollowUpManager.clearFlag` odstraní všechny vlastnosti související s vlajkou ze zprávy.

```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpManager.clearFlag(mapi);
mapi.save(outputDir + "FollowUpFlagRemoved_out.msg");
```
*Zpráva je uložena bez jakékoli follow‑up vlajky.*

## Jak číst možnosti vlajky (Funkce 5)?
Zavolejte `FollowUpManager.getOptions` na načteném `MapiMessage`, abyste získali objekt `FollowUpOptions`. Tento objekt poskytuje datum zahájení, termín, datum připomenutí a předmět vlajky, což vám umožní zobrazit nebo zaznamenat podrobnosti vlajky. Je užitečný pro reportování a audity souladu.

### Přímá odpověď
Použijte `FollowUpManager.getOptions` na načteném `MapiMessage`, abyste získali objekt `FollowUpOptions` obsahující datum zahájení, termín, datum připomenutí a předmět vlajky. To je užitečné pro reportování nebo audity souladu.

### Krok 1: Získání možností
Vrácený objekt `options` vám poskytuje úplný přehled o konfiguraci vlajky.

```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpOptions options = FollowUpManager.getOptions(mapi);
```
*Objekt `options` nyní obsahuje datum zahájení, termín a datum připomenutí, plus předmět vlajky – užitečné, když potřebujete **read flag options** pro reportování.*

## Praktické aplikace
- **Integrace správy úkolů:** Synchronizujte označené e‑maily s Jira, Trello nebo Azure Boards.  
- **Automatické připomenutí:** Generujte denní e‑mailová připomenutí pro nevyřízené follow‑upy.  
- **Audity souladu:** Exportujte data vlajek pro regulační reportování, využívajíc možnost programově číst možnosti vlajek.

## Úvahy o výkonu
- **Výpočty dat:** Vypočítejte data jednou na dávku místo uvnitř smyček.  
- **Správa zdrojů:** Zavřete všechny streamy nebo souborové handly po uložení zpráv.  
- **Využití paměti:** Zpracovávejte velké poštovní schránky po částech, aby nedošlo k přetížení haldy; Aspose.Email dokáže zvládnout stovky stránek poštovních schránek bez načítání celého souboru do paměti.

## Časté problémy a řešení
| Problém | Příčina | Řešení |
|-------|-------|-----|
| Vlajka se v Outlooku nezobrazuje | Zpráva uložena bez správných `MessageFlags` | Ujistěte se, že `setMessageFlags` je nastaven na `MSGFLAG_UNSENT` před aplikací vlajky pro příjemce. |
| Uložení vyvolá `AccessDeniedException` | Nesprávná cesta souboru nebo chybějící oprávnění k zápisu | Ověřte, že výstupní adresář existuje a aplikace má právo zapisovat do tohoto umístění. |
| Data jsou o jeden den posunuta | Nesoulad časových pásem | Použijte `TimeZone.getTimeZone("GMT")` nebo konzistentně svou lokální zónu. |

## Často kladené otázky
**Q: Co je Aspose.Email pro Java?**  
A: Jedná se o čistě Java API, které vám umožní vytvářet, číst a manipulovat s e‑mailovými soubory (MSG, EML atd.) bez potřeby instalovaného Outlooku.

**Q: Jak získám bezplatnou zkušební licenci?**  
A: Navštivte [Aspose website](https://releases.aspose.com/email/java/) a stáhněte si 30‑denní zkušební verzi.

**Q: Mohu nastavit více follow‑up vlajek na jednu zprávu?**  
A: Outlook podporuje pouze jednu vlajku na zprávu, ale můžete uložit další úkolová data do vlastních MAPI vlastností.

**Q: Moje zpráva se po nastavení vlajky neuloží. Co mám zkontrolovat?**  
A: Ověřte, že cesta `outputDir` je platná a aplikace má oprávnění zapisovat do daného umístění.

**Q: Jak mohu najednou odstranit vlajky z mnoha zpráv?**  
A: Projděte kolekci zpráv a pro každou `MapiMessage` zavolejte `FollowUpManager.clearFlag`.

## Zdroje
- [Dokumentace](https://reference.aspose.com/email/java/)
- [Stáhnout Aspose.Email pro Java](https://releases.aspose.com/email/java/)
- [Aspose.Email – bezplatná zkušební verze](https://purchase.aspose.com/purchase/free-trial/aspose-email-java)

---

**Last Updated:** 2026-07-27  
**Testováno s:** Aspose.Email for Java 25.4 (JDK 16)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Související tutoriály

- [Správa kategorií Outlook s Aspose.Email pro Java – komplexní průvodce](/email/java/calendar-appointments/manage-outlook-categories-aspose-email-java/)
- [Vytvoření Outlook poznámek v Javě s Aspose.Email – kompletní průvodce](/email/java/calendar-appointments/create-customize-outlook-notes-aspose-email-java/)
- [Vytvoření úkolů v Microsoft Exchange pomocí Aspose.Email pro Java: kompletní průvodce](/email/java/exchange-server-integration/create-tasks-exchange-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}