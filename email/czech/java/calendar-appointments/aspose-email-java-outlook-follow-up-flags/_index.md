---
date: '2025-12-19'
description: Naučte se, jak nastavit příznaky pro následné zpracování v Outlooku pomocí
  Aspose.Email pro Javu, včetně toho, jak efektivně nastavit a odebrat příznak následného
  zpracování v Outlooku.
keywords:
- Manage Outlook follow-up flags
- Set follow-up flags in Outlook with Aspose.Email for Java
- Integrate email task management with Aspose.Email
title: Jak nastavit příznaky pro následné kroky v Outlooku pomocí Aspose.Email pro
  Javu
url: /cs/java/calendar-appointments/aspose-email-java-outlook-follow-up-flags/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak nastavit příznaky pro sledování v Outlooku pomocí Aspose.Email pro Java

## Úvod
Pokud jste někdy měli potíže sledovat důležité e‑maily, víte, jak cenné mohou být příznaky pro sledování v Outlooku. V tomto průvodci vám ukážeme **jak nastavit příznaky pro sledování** programově pomocí Aspose.Email pro Java a také se podíváme na **nastavení příznaku pro sledování v Outlooku** pro příjemce a jak **odstranit příznak pro sledování v Outlooku**, když je úkol dokončen. Na konci budete schopni automatizovat sledování úkolů, připomenutí a auditní stopy přímo z vašeho Java kódu.

**Co se naučíte**
- Vytvořit a aplikovat příznak pro sledování na zprávu Outlook.  
- Nastavit příznaky pro sledování pro konkrétní příjemce.  
- Označit příznak jako dokončený a později jej odstranit.  
- Číst možnosti příznaku pro reportování nebo soulad.  

Připravme si prostředí, než se ponoříme do kódu.

## Rychlé odpovědi
- **Co znamená „jak nastavit sledování“?** Přidání příznaku s daty zahájení, připomenutí a termínu k položce Outlook.  
- **Která knihovna je vyžadována?** Aspose.Email pro Java (v25.4 nebo novější).  
- **Potřebuji licenci?** Ano, pro plnou funkčnost je vyžadována zkušební nebo zakoupená licence.  
- **Mohu nastavit příznaky pouze pro příjemce?** Ano – použijte `FollowUpManager.setFlagForRecipients`.  
- **Je možné příznak později odstranit?** Ano, zavolejte `FollowUpManager.clearFlag`.

## Co je příznak pro sledování?
Příznak pro sledování je funkce Outlooku, která označuje e‑mail jako úkol, volitelně přidává data zahájení, připomenutí a termínu. Pomáhá vám i vašemu týmu sledovat nevyřízené akce.

## Proč používat Aspose.Email pro Java?
Aspose.Email poskytuje čisté Java API, které funguje bez nainstalovaného Outlooku, umožňuje manipulovat se soubory .msg, nastavovat příznaky a spravovat úkoly na jakékoli platformě – ideální pro backendové služby, automatizované pracovní postupy nebo integraci s nástroji pro řízení projektů.

## Požadavky
- **Aspose.Email pro Java** verze 25.4 nebo novější.  
- **JDK 16+** nainstalováno.  
- IDE kompatibilní s Maven (IntelliJ IDEA, Eclipse, atd.).  
- Základní znalost Javy a povědomí o e‑mailových konceptech.

## Nastavení Aspose.Email pro Java
### Konfigurace Maven
Přidejte následující závislost do souboru `pom.xml`:

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

- **Bezplatná zkušební verze** – 30denní hodnocení.  
- **Dočasná licence** – rozšířené testování.  
- **Plná licence** – trvalé předplatné.

Inicializujte licenci před jakoukoliv operací s e‑mailem:

```java
License license = new License();
license.setLicense("path/to/Aspose.Total.Java.lic");
```

## Průvodce implementací

### Jak nastavit příznaky pro sledování (Funkce 1)
#### Přehled
Tato část vás provede vytvořením zprávy Outlook, definováním dat zahájení/připomenutí/termínu a aplikací příznaku pro sledování.

#### Krok 1: Vytvořit a inicializovat zprávu
```java
MailMessage mailMsg = new MailMessage();
mailMsg.setSender(new MailAddress("AETest12@gmail.com"));
mailMsg.getTo().addMailAddress(new MailAddress("receiver@gmail.com"));
mailMsg.setBody("This message will test if follow up options can be added to a new mapi message.");
MapiMessage mapi = MapiMessage.fromMailMessage(mailMsg);
```
*Nejprve vytvoříme `MailMessage`, nastavíme odesílatele/příjemce a poté jej převedeme na `MapiMessage` pro manipulaci s příznakem.*

#### Krok 2: Definovat data pro sledování
```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 14, 40, 0);
Date dtStartDate = calendar.getTime();
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
calendar.add(Calendar.DATE, 1);
Date dtDueDate = calendar.getTime();
```
*Zde nastavujeme data zahájení, připomenutí a termínu pomocí třídy `Calendar`.*

#### Krok 3: Použít možnosti sledování
```java
FollowUpOptions options = new FollowUpOptions("Follow Up", dtStartDate, dtDueDate, dtReminderDate);
FollowUpManager.setOptions(mapi, options);
```
*Objekt `FollowUpOptions` obsahuje všechny podrobnosti příznaku, které aplikujeme pomocí `FollowUpManager.setOptions`.*

#### Krok 4: Uložit zprávu
```java
mapi.save(outputDir + "SetFollowUpflag_out.msg");
```
*Zpráva je uložena jako soubor `.msg` s připojeným příznakem.*

### Jak nastavit příznak pro sledování v Outlooku pro příjemce (Funkce 2)
#### Přehled
Někdy potřebujete označit zprávu pouze pro příjemce. Tento příklad nejprve označí zprávu jako koncept a poté přidá příznak.

#### Krok 1: Označit jako koncept
```java
mapi.setMessageFlags(MapiMessageFlags.MSGFLAG_UNSENT);
```
*Označení zprávy jako neodeslané zajišťuje, že Outlook ji bude považovat za koncept.*

#### Krok 2: Nastavit příznak pro příjemce
```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
FollowUpManager.setFlagForRecipients(mapi, "Follow up", dtReminderDate);
```
*Příznak je nyní viditelný pouze pro příjemce.*

### Jak označit příznak pro sledování v Outlooku jako dokončený (Funkce 3)
#### Přehled
Když je úkol hotov, můžete programově označit příznak jako dokončený.

#### Krok 1: Načíst zprávu
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
```

#### Krok 2: Označit jako dokončené a uložit
```java
FollowUpManager.markAsCompleted(mapi);
mapi.save(outputDir + "MarkedCompleted_out.msg");
```
*Stav příznaku se změní na „Completed“ a aktualizovaný soubor je uložen.*

### Jak odstranit příznak pro sledování v Outlooku (Funkce 4)
#### Přehled
Pokud příznak již není potřeba, můžete jej zcela vymazat.

#### Krok 1: Načíst a vymazat příznak
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpManager.clearFlag(mapi);
mapi.save(outputDir + "FollowUpFlagRemoved_out.msg");
```
*Zpráva je uložena bez jakéhokoli příznaku pro sledování.*

### Jak číst možnosti příznaku pro sledování (Funkce 5)
#### Přehled
Pro audit nebo reportování můžete potřebovat přečíst existující nastavení příznaku.

#### Krok 1: Získat možnosti
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpOptions options = FollowUpManager.getOptions(mapi);
```
*Objekt `options` nyní obsahuje data zahájení, termínu a připomenutí, plus předmět příznaku.*

## Praktické aplikace
- **Integrace s řízením úkolů:** Synchronizovat označené e‑maily s Jira, Trello nebo Azure Boards.  
- **Automatické připomenutí:** Generovat denní e‑maily s připomenutím nevyřízených sledování.  
- **Audity souladu:** Exportovat data příznaků pro regulatorní reportování.

## Úvahy o výkonu
- **Výpočty dat:** Vypočítat data jednou na dávku místo uvnitř smyček.  
- **Správa zdrojů:** Zavřít všechny streamy nebo souborové handly po uložení zpráv.  
- **Využití paměti:** Zpracovávat velké poštovní schránky po částech, aby se předešlo zatížení haldy.

## Časté problémy a řešení
| Problém | Příčina | Řešení |
|-------|-------|-----|
| Příznak se nezobrazuje v Outlooku | Zpráva uložena bez správných `MessageFlags` | Ujistěte se, že `setMessageFlags` je nastaven na `MSGFLAG_UNSENT` před aplikací příznaků pro příjemce. |
| Uložení vyvolá `AccessDeniedException` | Nesprávná cesta k souboru nebo chybějící oprávnění k zápisu | Ověřte, že výstupní adresář existuje a aplikace má oprávnění zapisovat do tohoto umístění. |
| Data jsou posunuta o jeden den | Neshoda časových pásem | Použijte `TimeZone.getTimeZone("GMT")` nebo konzistentně svou místní zónu. |

## Často kladené otázky
**Q: Co je Aspose.Email pro Java?**  
A: Jedná se o čisté Java API, které vám umožňuje vytvářet, číst a manipulovat s e‑mailovými soubory (MSG, EML, atd.) bez nutnosti instalace Outlooku.

**Q: Jak získám bezplatnou zkušební licenci?**  
A: Navštivte [web Aspose](https://releases.aspose.com/email/java/) a stáhněte si 30denní zkušební verzi.

**Q: Mohu nastavit více příznaků pro sledování na jedné zprávě?**  
A: Outlook podporuje pouze jeden příznak na zprávu, ale můžete uložit další úkolová data do vlastních MAPI vlastností.

**Q: Moje zpráva se neuloží po nastavení příznaku. Co mám zkontrolovat?**  
A: Ověřte, že cesta `outputDir` je platná a že aplikace má oprávnění zapisovat do tohoto umístění.

**Q: Jak mohu odstranit příznaky z mnoha zpráv najednou?**  
A: Projděte kolekci zpráv a zavolejte `FollowUpManager.clearFlag` na každém `MapiMessage`.

## Zdroje
- [Dokumentace](https://reference.aspose.com/email/java/)
- [Stáhnout Aspose.Email pro Java](https://releases.aspose.com/email/java/)
- [Bezplatná zkušební verze Aspose.Email](https://purchase.aspose.com/purchase/free-trial/aspose-email-java)

---

**Poslední aktualizace:** 2025-12-19  
**Testováno s:** Aspose.Email for Java 25.4 (jdk16)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}