---
date: '2026-07-08'
description: Naučte se, jak vytvořit EWS klienta Java pomocí Aspose.Email pro efektivní
  správu e‑mailů, včetně mazání zpráv, přidávání a impersonace uživatele na Exchange
  Serveru.
keywords:
- create ews client java
- Aspose.Email Java
- Exchange Server EWS
- email impersonation Java
lastmod: '2026-07-08'
og_description: Naučte se, jak vytvořit EWS klienta Java pomocí Aspose.Email pro efektivní
  správu e‑mailů, včetně mazání zpráv, přidávání a impersonace uživatele na Exchange
  Serveru.
og_image_alt: 'Developer guide: Create EWS client Java with Aspose.Email for user
  management'
og_title: Vytvořte EWS klienta Java s Aspose.Email – Správa uživatelů
schemas:
- author: Aspose
  dateModified: '2026-07-08'
  description: Learn how to create EWS client Java using Aspose.Email for efficient
    email management, including message deletion, appending, and user impersonation
    on Exchange Server.
  headline: Create EWS Client Java with Aspose.Email – Manage Users
  type: TechArticle
- description: Learn how to create EWS client Java using Aspose.Email for efficient
    email management, including message deletion, appending, and user impersonation
    on Exchange Server.
  name: Create EWS Client Java with Aspose.Email – Manage Users
  steps:
  - name: '**Automated Email Cleanup:** Schedule a nightly job that clears out stale
      Draft folders across dozens of mailboxes.'
    text: '**Automated Email Cleanup:** Schedule a nightly job that clears out stale
      Draft folders across dozens of mailboxes.'
  - name: '**Batch Email Distribution:** Append a templated announcement to the Inbox
      of every employee with a single loop.'
    text: '**Batch Email Distribution:** Append a templated announcement to the Inbox
      of every employee with a single loop.'
  - name: '**Shared Mailbox Management:** Impersonate a department mailbox to archive
      old messages without granting each user full access.'
    text: '**Shared Mailbox Management:** Impersonate a department mailbox to archive
      old messages without granting each user full access.'
  type: HowTo
- questions:
  - answer: Check the endpoint URL, credentials, and network firewalls; enable detailed
      logging in Aspose.Email to capture HTTP request/response data.
    question: How do I troubleshoot connectivity issues with EWS?
  - answer: Yes—its batch APIs let you process **10,000+** messages per minute while
      keeping memory usage under 200 MB.
    question: Can Aspose.Email handle large volumes of emails efficiently?
  - answer: Managing shared mailboxes, performing bulk archiving, and running scheduled
      reports on behalf of multiple users without storing their passwords.
    question: What are typical use cases for user impersonation in EWS?
  - answer: Aspose.Email itself imposes no call limits; however, Exchange may enforce
      throttling policies that you need to respect.
    question: Are there limits on API calls imposed by Aspose.Email?
  - answer: Store them in encrypted configuration files or use Azure Key Vault / AWS
      Secrets Manager, and always use HTTPS for EWS endpoints.
    question: How can I keep credentials secure in my Java code?
  type: FAQPage
tags:
- create ews client java
- Aspose.Email
- Java Exchange
- email impersonation
- EWS client
title: Vytvořte EWS klienta Java s Aspose.Email – Správa uživatelů
url: /cs/java/exchange-server-integration/aspose-email-java-ews-client-user-management/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Ovládání správy e‑mailů: Aspose.Email Java pro uživatele a impersonaci EWS klienta

## Úvod

V tomto tutoriálu **create EWS client Java** aplikace s Aspose.Email, umožňující vám spravovat více poštovních schránek Exchange Serveru z jediné Java kódu. Provedeme vás vytvořením instancí `EWSClient`, mazáním zpráv, přidáváním nových e‑mailů a impersonací jiných uživatelů — úkoly, které šetří hodiny ruční práce v podnikovém prostředí.

### Co se naučíte
- Jak **create EWS client Java** objekty pomocí odlišných přihlašovacích údajů.  
- Efektivní techniky pro smazání každé zprávy z vybrané složky.  
- Kroky pro přidání připraveného e‑mailu do poštovní schránky uživatele.  
- Jak impersonovat jinou poštovní schránku pro scénáře sdílených schránek.

Nyní, když víte, co budeme probírat, připravme vývojové prostředí.

## Rychlé odpovědi
- **Jaký je první krok?** Přidejte Maven závislost Aspose.Email do vašeho `pom.xml`.  
- **Která třída představuje připojení k Exchange?** `EWSClient` (nebo její rozhraní `IEWSClient`).  
- **Mohu smazat všechny zprávy jedním voláním?** Ano — iterujte pomocí `listMessages` a zavolejte `deleteMessage` pro každé URI.  
- **Jak mohu odeslat e‑mail bez SMTP?** Použijte `appendMessage` k umístění `MailMessage` přímo do složky.  
- **Je impersonace bezpečná?** Běží pod původními přihlašovacími údaji a respektuje delegační zásady Exchange.

## Co je create EWS client Java?
`create ews client java` označuje vytvoření objektu `EWSClient` v Java aplikaci, aby bylo možné programově volat operace Exchange Web Services (EWS). Tento přístup odstraňuje potřebu ruční interakce s Outlookem a umožňuje automatizované zpracování poštovních schránek. Vytvořením dedikovaného klienta pro každého uživatele můžete izolovat přihlašovací údaje, vynutit zásady na úrovni schránek a škálovat řešení na desítky účtů bez duplicitního kódu.

## Proč používat Aspose.Email pro integraci s EWS?
Aspose.Email podporuje **50+** operací EWS, zvládá **více než stovky** stránek poštovních schránek, aniž by načítal celý úložiště do paměti, a zpracovává **až 10 000** zpráv za minutu na typickém serverovém hardware. Tyto kvantifikované schopnosti z něj činí špičkovou volbu pro rozsáhlou automatizaci e‑mailů. Knihovna také abstrahuje nízkoúrovňové SOAP detaily a poskytuje čisté, typově bezpečné API, které snižuje dobu vývoje a minimalizuje chyby.

## Požadavky
- **Java Development Kit (JDK)** ≥ 16.  
- **Maven** pro správu závislostí.  
- **Aspose.Email for Java** knihovna (přidejte přes Maven).  
- Základní znalost konceptů Exchange Web Services (EWS).

## Nastavení Aspose.Email pro Java
Přidejte knihovnu do vašeho Maven `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Získání licence
Aspose.Email nabízí bezplatnou zkušební verzi s možností požádat o dočasnou licenci pro plné funkce. Pro dlouhodobé používání zvažte zakoupení licence na [stránce nákupu Aspose](https://purchase.aspose.com/buy).

## Jak vytvořit EWS client Java?
Načtěte službu Exchange s příslušnými přihlašovacími údaji a získejte instanci `IEWSClient` — tento dvoukrokový vzor je jádrem každé následné operace. Můžete znovu použít stejný klient pro více akcí nebo vytvořit samostatné instance pro každého uživatele pro izolaci. **`IEWSClient` je rozhraní, které vystavuje všechny operace EWS, zatímco `EWSClient` poskytuje statickou tovární metodu pro získání implementace.**

Vytvoření klienta typicky zahrnuje zadání URL služby, uživatelského jména, hesla a volitelně informace o doméně. Po vytvoření klient automaticky zpracovává autentizaci, podepisování požadavků a parsování odpovědí.

### Vytvoření instancí EWSClient
**Definice:** `EWSClient` (zpřístupněný přes rozhraní `IEWSClient`) je hlavní objekt Aspose.Email pro komunikaci se serverem Exchange přes EWS.

#### Import požadovaných tříd
Začněte importováním potřebných tříd Aspose.Email:

```java
import com.aspose.email.EWSClient;
import com.aspose.email.IEWSClient;
```

#### Inicializace instancí EWSClient
Vytvořte objekty `IEWSClient` pro každou poštovní schránku, kterou chcete spravovat:

```java
IEWSClient client1 = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser1", "pwd", "domain");
IEWSClient client2 = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser2", "pwd", "domain");
```

*Vysvětlení:* Pomocná metoda `getEWSClient` se připojí k Exchange pomocí dodaných přihlašovacích údajů a vrátí připraveného klienta, který respektuje oprávnění aktuálního uživatele.

## Jak smazat zprávy ze složky?
Získejte všechny položky v cílové složce a trvale je smažte v jednom průchodu. Tato metoda eliminuje režii otevírání každé zprávy zvlášť. **`listMessages` vrací kolekci objektů `MessageInfo`, které obsahují jedinečné URI pro každou zprávu, a které následně předáte `deleteMessage` k odstranění položky ze serveru.**

Zpracování po dávkách snižuje počet síťových požadavků a zabraňuje časovým limitům při práci s velkými složkami. Vždy ověřte, že cílová složka je správná, protože smazání je nevratné bez zálohy.

### Seznam a smazání zpráv
Iterujte přes každé URI zprávy a zavolejte operaci smazání:

```java
String folder = "Drafts"; // Specify the folder.
ExchangeMessageInfoCollection messages1 = client1.listMessages(folder);
for (ExchangeMessageInfo messageInfo : messages1) {
    client1.deleteItem(messageInfo.getUniqueUri(), DeletionOptions.getDeletePermanently());
}

ExchangeMessageInfoCollection messages2 = client2.listMessages(folder);
for (ExchangeMessageInfo messageInfo : messages2) {
    client2.deleteItem(messageInfo.getUniqueUri(), DeletionOptions.getDeletePermanently());
}
```

*Vysvětlení:* `listMessages` vrací kolekci objektů `MessageInfo`; jejich hodnoty `getUniqueUri()` jsou předány `deleteMessage`, který trvale odstraní položky ze serveru.

## Jak přidat zprávu do složky?
Sestavte lokálně objekt `MailMessage` a uložte jej přímo do složky poštovní schránky — není potřeba SMTP server. **`MailMessage` představuje e‑mail s hlavičkami, tělem a přílohami; může být kompletně vytvořen v paměti před uložením do Exchange.**

Přidání obchází odesílací pipeline, což je ideální pro koncepty, šablony nebo programové vytváření zpráv, kde chcete, aby se zpráva okamžitě objevila v poštovní schránce uživatele.

### Vytvoření a odeslání zpráv
Sestavte e‑mail a přidejte jej do složky Drafts:

```java
String subj1 = String.format("NETWORKNET_33354 {0} {1}", "User", "User1");
client1.appendMessage(folder, new MailMessage("User1@exchange.conholdate.local", "To@aspsoe.com", subj1, ""));

String subj2 = String.format("NETWORKNET_33354 {0} {1}", "User", "User2");
client2.appendMessage(folder, new MailMessage("User2@exchange.conholdate.local", "To@aspose.com", subj2, ""));
```

*Vysvětlení:* `appendMessage` přijímá `MailMessage` a `FolderInfo` (např. Drafts) a zapisuje položku do poštovní schránky, čímž je okamžitě dostupná uživateli.

## Jak impersonovat uživatele v EWS?
Přepněte bezpečnostní kontext klienta na jinou poštovní schránku, proveďte akce a poté se vraťte k původnímu účtu. To je nezbytné pro správu sdílených schránek. **`impersonateUser` nastaví `ImpersonatedUserId` na podkladovém požadavku EWS, což umožní serveru zacházet s voláním, jako by pocházelo z cílové schránky.**

Po dokončení požadovaných operací zavolejte `resetImpersonation` k obnovení původních přihlašovacích údajů, čímž zajistíte, že následující volání budou prováděna pod správným bezpečnostním kontextem.

### Provádění impersonace uživatele
Dočasně změňte kontext klienta, aby jednal jako jiný uživatel:

```java
ExchangeMessageInfoCollection messInfoColl1 = client1.listMessages(folder);
client1.impersonateUser(0, "User2@exchange.conholdate.local");

ExchangeMessageInfoCollection messInfoColl2 = client1.listMessages(folder);
// Revert to the original user context.
client1.resetImpersonation();
ExchangeMessageInfoCollection messInfoColl3 = client1.listMessages(folder);
```

*Vysvětlení:* `impersonateUser` nastaví `ImpersonatedUserId` na podkladovém požadavku EWS, což vám umožní číst nebo zapisovat, jako byste byli cílovým uživatelem. Volání `resetImpersonation` obnoví původní přihlašovací údaje.

## Praktické aplikace
Using Aspose.Email Java enables robust email automation solutions:
1. **Automatické čištění e‑mailů:** Naplánujte noční úlohu, která vyčistí zastaralé složky Draft napříč desítkami poštovních schránek.  
2. **Dávková distribuce e‑mailů:** Přidejte šablonové oznámení do složky Inbox každého zaměstnance jedním cyklem.  
3. **Správa sdílených schránek:** Impersonujte poštovní schránku oddělení k archivaci starých zpráv, aniž byste každému uživateli poskytli plný přístup.

## Úvahy o výkonu
To keep your application responsive when handling large mailboxes:
- **Dávkové volání API** kde je to možné (např. smazat 500 zpráv na jeden požadavek).  
- **Streamovat zprávy** místo načítání celých těles do paměti.  
- **Okamžitě uvolňovat objekty klienta** pro uvolnění síťových socketů a HTTP spojení.

## Časté problémy a řešení
- **Chyby připojení:** Ověřte URL koncového bodu EWS, ujistěte se, že je povolen TLS 1.2, a potvrďte, že firewallová pravidla umožňují odchozí HTTPS.  
- **Oprávnění odmítnuto při impersonaci:** Služební účet musí mít v Exchange přiřazenou roli „ApplicationImpersonation“.  
- **Časové limity velkých složek:** Zvyšte timeout `HttpWebRequest` nebo zpracovávejte složku v menších částech.

## Často kladené otázky

**Q: Jak řešit problémy s připojením k EWS?**  
A: Zkontrolujte URL koncového bodu, přihlašovací údaje a síťové firewally; povolte podrobné logování v Aspose.Email pro zachycení dat HTTP požadavku/odpovědi.

**Q: Dokáže Aspose.Email efektivně zpracovávat velké objemy e‑mailů?**  
A: Ano — jeho dávkové API vám umožní zpracovat **10 000+** zpráv za minutu při využití paměti pod 200 MB.

**Q: Jaké jsou typické případy použití impersonace uživatele v EWS?**  
A: Správa sdílených schránek, provádění hromadného archivování a spouštění naplánovaných reportů jménem více uživatelů bez ukládání jejich hesel.

**Q: Existují omezení počtu volání API uvalená Aspose.Email?**  
A: Aspose.Email sám neklade žádná omezení; však Exchange může vynucovat politiky omezení (throttling), které je třeba respektovat.

**Q: Jak mohu zabezpečit přihlašovací údaje v mém Java kódu?**  
A: Ukládejte je do šifrovaných konfiguračních souborů nebo použijte Azure Key Vault / AWS Secrets Manager a vždy používejte HTTPS pro EWS koncové body.

---

**Poslední aktualizace:** 2026-07-08  
**Testováno s:** Aspose.Email for Java 23.10  
**Autor:** Aspose

## Související tutoriály

- [Jak vytvořit instanci EWSClient pomocí Aspose.Email pro Java: Průvodce integrací Exchange Serveru](/email/java/exchange-server-integration/ewsclient-instance-aspose-email-java/)
- [Jak se připojit k Microsoft Exchange Serveru pomocí Aspose.Email pro Java a EWS](/email/java/exchange-server-integration/connect-exchange-server-aspose-email-ews-java/)
- [Automatizace správy e‑mailů s Aspose.Email a Java EWS klientem: Kompletní průvodce](/email/java/exchange-server-integration/aspose-email-java-ews-client-tutorial/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}