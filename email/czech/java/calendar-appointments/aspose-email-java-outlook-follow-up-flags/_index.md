---
date: '2026-02-22'
description: Naučte se, jak nastavit vlajku pro následné sledování v Outlooku pomocí
  Aspose.Email pro Javu, včetně nastavení, čtení a odstraňování vlajek pro příjemce.
keywords:
- Manage Outlook follow-up flags
- Set follow-up flags in Outlook with Aspose.Email for Java
- Integrate email task management with Aspose.Email
title: Jak nastavit příznak sledování v Outlooku pomocí Aspose.Email pro Javu
url: /cs/java/calendar-appointments/aspose-email-java-outlook-follow-up-flags/
weight: 1
---

: Keep bold formatting **text**.

Let's write.

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak nastavit příznak sledování v Outlooku pomocí Aspose.Email pro Java

## Úvod
Pokud jste někdy měli potíže sledovat důležité e‑maily, víte, jak cenný může být **outlook follow up flag** v Outlooku. V tomto průvodci vám ukážeme, **jak nastavit outlook follow up flag** programově pomocí Aspose.Email pro Java, a také jak **nastavit outlook follow up flag pro příjemce**, stejně jako **odstranit outlook follow up flag**, když je úkol dokončen. Na konci budete schopni automatizovat sledování úkolů, připomenutí a auditní záznamy přímo z vašeho Java kódu.

**Co se naučíte**
- Vytvořit a použít příznak sledování na zprávě Outlooku.  
- Nastavit příznaky sledování pro konkrétní příjemce.  
- Označit příznak jako dokončený a později jej odstranit.  
- Načíst možnosti příznaku pro reportování nebo soulad s předpisy.  

Připravme si prostředí, než se ponoříme do kódu.

## Rychlé odpovědi
- **Co znamená „jak nastavit sledování“?** Přidání příznaku s datem zahájení, připomenutím a termínem dokončení k položce Outlooku.  
- **Která knihovna je vyžadována?** Aspose.Email pro Java (v25.4 nebo novější).  
- **Potřebuji licenci?** Ano, pro plnou funkčnost je vyžadována zkušební nebo zakoupená licence.  
- **Mohu nastavit příznaky jen pro příjemce?** Rozhodně – použijte `FollowUpManager.setFlagForRecipients`.  
- **Je možné příznak později odstranit?** Ano, zavolejte `FollowUpManager.clearFlag`.

## Co je Outlook Follow Up Flag?
Outlook follow up flag je vestavěný označovač úkolu, který může k libovolné poštovní položce připojit datum zahájení, připomenutí a termín dokončení. Přemění běžný e‑mail na sledovatelnou akci, což vám i vašemu týmu pomáhá zůstat na vrcholu nevyřízené práce.

## Proč používat Aspose.Email pro Java?
Aspose.Email poskytuje čistě Java API, které funguje bez nainstalovaného Outlooku, umožňuje manipulovat s .msg soubory, nastavovat příznaky a spravovat úkoly na jakékoli platformě – ideální pro **automate outlook tasks**, backendové služby nebo integraci s nástroji pro řízení projektů.

## Předpoklady
- **Aspose.Email pro Java** verze 25.4 nebo novější (také známý jako **aspose email java**).  
- **JDK 16+** nainstalováno.  
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

- **Free trial** – 30‑denní zkušební verze.  
- **Temporary license** – rozšířené testování.  
- **Full license** – trvalé předplatné.

Inicializujte licenci před jakoukoliv operací s e‑mailem:

```java
License license = new License();
license.setLicense("path/to/Aspose.Total.Java.lic");
```

## Nastavit Outlook Follow Up Flag (Funkce 1)
### Krok 1: Vytvořit a inicializovat zprávu
```java
MailMessage mailMsg = new MailMessage();
mailMsg.setSender(new MailAddress("AETest12@gmail.com"));
mailMsg.getTo().addMailAddress(new MailAddress("receiver@gmail.com"));
mailMsg.setBody("This message will test if follow up options can be added to a new mapi message.");
MapiMessage mapi = MapiMessage.fromMailMessage(mailMsg);
```
*Nejprve vytvoříme `MailMessage`, nastavíme odesílatele/příjemce a poté ji převedeme na `MapiMessage` pro manipulaci s příznakem.*

### Krok 2: Definovat data sledování (Outlook Flag Reminder)
```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 14, 40, 0);
Date dtStartDate = calendar.getTime();
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
calendar.add(Calendar.DATE, 1);
Date dtDueDate = calendar.getTime();
```
*Zde nastavujeme datum zahájení, připomenutí (tedy **outlook flag reminder**) a termín dokončení pomocí třídy `Calendar`.*

### Krok 3: Použít možnosti sledování
```java
FollowUpOptions options = new FollowUpOptions("Follow Up", dtStartDate, dtDueDate, dtReminderDate);
FollowUpManager.setOptions(mapi, options);
```
*Objekt `FollowUpOptions` obsahuje všechny podrobnosti příznaku, které aplikujeme pomocí `FollowUpManager.setOptions`.*

### Krok 4: Uložit zprávu
```java
mapi.save(outputDir + "SetFollowUpflag_out.msg");
```
*Zpráva je uložena jako soubor `.msg` s připojeným příznakem.*

## Jak nastavit příznak pro příjemce (Funkce 2)
### Přehled
Někdy potřebujete, aby se příznak zobrazoval **pouze pro příjemce**. Tento příklad nejprve označí zprávu jako koncept a pak přidá příznak.

#### Krok 1: Označit jako koncept
```java
mapi.setMessageFlags(MapiMessageFlags.MSGFLAG_UNSENT);
```
*Označení zprávy jako neodeslané zajistí, že Outlook ji bude považovat za koncept.*

#### Krok 2: Nastavit příznak pro příjemce
```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
FollowUpManager.setFlagForRecipients(mapi, "Follow up", dtReminderDate);
```
*Příznak je nyní viditelný jen pro příjemce – klasický scénář **flag for recipients**.*

## Jak označit Outlook Follow Up Flag jako dokončený (Funkce 3)
### Krok 1: Načíst zprávu
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
```

### Krok 2: Označit jako dokončený a uložit
```java
FollowUpManager.markAsCompleted(mapi);
mapi.save(outputDir + "MarkedCompleted_out.msg");
```
*Stav příznaku se změní na „Completed“ a aktualizovaný soubor je uložen.*

## Jak odstranit Outlook Follow Up Flag (Funkce 4)
### Krok 1: Načíst a vymazat příznak
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpManager.clearFlag(mapi);
mapi.save(outputDir + "FollowUpFlagRemoved_out.msg");
```
*Zpráva je uložena bez jakéhokoli příznaku sledování.*

## Jak načíst možnosti příznaku (Funkce 5)
### Krok 1: Získat možnosti
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpOptions options = FollowUpManager.getOptions(mapi);
```
*Objekt `options` nyní obsahuje datum zahájení, termín, datum připomenutí a předmět příznaku – užitečné, když potřebujete **read flag options** pro reportování.*

## Praktické aplikace
- **Task‑Management Integration:** Synchronizace označených e‑mailů s Jira, Trello nebo Azure Boards.  
- **Automated Reminders:** Generování denních připomenutí e‑mailů pro nevyřízené sledování.  
- **Compliance Audits:** Export dat příznaků pro regulatorní reportování.

## Úvahy o výkonu
- **Date Calculations:** Vypočítejte data jednou na dávku místo uvnitř smyček.  
- **Resource Management:** Po uložení zpráv uzavřete všechny proudy nebo souborové handle.  
- **Memory Usage:** Zpracovávejte velké poštovní schránky po částech, aby nedošlo k přetížení haldy.

## Časté problémy a řešení
| Problém | Příčina | Řešení |
|-------|-------|-----|
| Příznak se nezobrazuje v Outlooku | Zpráva uložena bez správných `MessageFlags` | Ujistěte se, že `setMessageFlags` je nastaven na `MSGFLAG_UNSENT` před aplikací příznaku pro příjemce. |
| Uložení vyvolá `AccessDeniedException` | Nesprávná cesta k souboru nebo chybějící oprávnění k zápisu | Ověřte, že výstupní adresář existuje a aplikace má právo zapisovat do tohoto umístění. |
| Data jsou posunuta o jeden den | Nesoulad časových pásem | Použijte `TimeZone.getTimeZone("GMT")` nebo konzistentně svou lokální zónu. |

## Často kladené otázky
**Q: Co je Aspose.Email pro Java?**  
A: Jedná se o čisté Java API, které vám umožní vytvářet, číst a manipulovat s e‑mailovými soubory (MSG, EML atd.) bez nutnosti mít nainstalovaný Outlook.

**Q: Jak získám zkušební licenci?**  
A: Navštivte [Aspose website](https://releases.aspose.com/email/java/) a stáhněte si 30‑denní zkušební verzi.

**Q: Můžu nastavit více příznaků sledování na jedné zprávě?**  
A: Outlook podporuje pouze jeden příznak na zprávu, ale můžete uložit další úkolová data do vlastních MAPI vlastností.

**Q: Moje zpráva se neuloží po nastavení příznaku. Co mám zkontrolovat?**  
A: Ověřte, že cesta `outputDir` je platná a že aplikace má oprávnění zapisovat do tohoto umístění.

**Q: Jak mohu odstranit příznaky z mnoha zpráv najednou?**  
A: Projděte kolekci zpráv a pro každou `MapiMessage` zavolejte `FollowUpManager.clearFlag`.

## Zdroje
- [Documentation](https://reference.aspose.com/email/java/)
- [Download Aspose.Email for Java](https://releases.aspose.com/email/java/)
- [Aspose.Email Free Trial](https://purchase.aspose.com/purchase/free-trial/aspose-email-java)

---

**Poslední aktualizace:** 2026-02-22  
**Testováno s:** Aspose.Email pro Java 25.4 (jdk16)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}