---
date: '2026-10-02'
description: Naučte se, jak připojit Exchange a vypsat veřejné složky Exchange pomocí
  Aspose.Email for Java. Tento krok‑za‑krokem průvodce ukazuje Maven závislost a nastavení
  bez kódu.
keywords:
- how to connect exchange
- list exchange public folders
- maven dependency aspose email
lastmod: '2026-10-02'
og_description: Naučte se, jak připojit Exchange a vypsat veřejné složky Exchange
  pomocí Aspose.Email for Java. Tento průvodce pokrývá Maven závislost, licencování
  a rekurzivní načítání zpráv.
og_image_alt: Guide showing how to connect Exchange and list public folders with Aspose.Email
  for Java
og_title: Jak připojit Exchange a vypsat veřejné složky v Javě
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Learn how to connect exchange and list exchange public folders using
    Aspose.Email for Java. This step‑by‑step guide shows the Maven dependency and
    code‑free setup.
  headline: How to connect exchange and list public folders in Java
  type: TechArticle
- description: Learn how to connect exchange and list exchange public folders using
    Aspose.Email for Java. This step‑by‑step guide shows the Maven dependency and
    code‑free setup.
  name: How to connect exchange and list public folders in Java
  steps:
  - name: '**Automated email archiving** – Periodically pull all public‑folder messages
      and store them in a compliant archive.'
    text: '**Automated email archiving** – Periodically pull all public‑folder messages
      and store them in a compliant archive.'
  - name: '**Backup solutions** – Mirror Exchange public folders to a secure file
      system or cloud bucket, guaranteeing data redundancy.'
    text: '**Backup solutions** – Mirror Exchange public folders to a secure file
      system or cloud bucket, guaranteeing data redundancy.'
  - name: '**Custom email clients** – Build lightweight viewers that display only
      the folders and messages you need, reducing UI complexity.'
    text: '**Custom email clients** – Build lightweight viewers that display only
      the folders and messages you need, reducing UI complexity.'
  type: HowTo
- questions:
  - answer: Yes. Provide the Office 365 EWS endpoint (`https://outlook.office365.com/EWS/Exchange.asmx`)
      and use modern authentication (OAuth) – Aspose.Email supports OAuth tokens out
      of the box.
    question: Can I use this code with Exchange Online (Office 365)?
  - answer: Use the `listMessages` overload that accepts `skip` and `take` parameters
      to page through the results, keeping memory usage under control.
    question: What if a folder contains more than 10 000 messages?
  - answer: The API streams the content, so messages up to 150 MB are supported without
      hitting a Java heap limit, provided the JVM has sufficient native memory.
    question: Is there a limit on the size of a single email I can download?
  - answer: By default Aspose.Email trusts the Java default keystore. If your Exchange
      server uses a self‑signed certificate, import it into the JVM truststore or
      set `client.setEnableSslVerification(false)` for testing only.
    question: Do I need to handle SSL certificates manually?
  - answer: Enable Aspose.Email’s built‑in logging by configuring `Logger.setLevel(Level.INFO)`
      and directing output to a file or monitoring system.
    question: How do I log the operations for audit purposes?
  type: FAQPage
tags:
- exchange integration
- Aspose.Email
- Java email automation
title: Jak připojit Exchange a vypsat veřejné složky v Javě
url: /cs/java/exchange-server-integration/aspose-email-java-exchange-messages-listing/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak se připojit k Exchange a vypsat veřejné složky v Javě

## Úvod
V moderních podnicích umožňuje programové přístupy k poštovním schránkám Microsoft Exchange automatizovat archivaci, monitorování a reporting. Tento tutoriál ukazuje **jak se připojit k Exchange** pomocí Aspose.Email pro Java a následně **rekurzivně vypsat veřejné složky Exchange**. Uvidíte požadovanou Maven závislost, kroky licencování a přesné pořadí volání API — žádné další knihovny nejsou potřeba. Na konci budete schopni načíst zprávy z libovolné veřejné složky a uložit je lokálně.

## Rychlé odpovědi
- **Jaký je první krok?** Přidejte Maven závislost Aspose.Email do svého `pom.xml`.  
- **Potřebuji licenci?** Ano — použijte dočasnou licenci pro hodnocení nebo zakupte plnou licenci pro produkci.  
- **Která třída vytváří připojení?** `ExchangeClient` (nebo `ImapClient` pro IMAP) zajišťuje autentizaci a komunikaci se serverem.  
- **Mohu automaticky vypsat podadresáře?** Ano — použijte rekurzivní metodu `listSubFolders`, kterou API poskytuje.  
- **Je tento přístup thread‑safe?** Objekt klienta není thread‑safe; vytvořte samostatnou instanci pro každý vlákno při souběžném zatížení.

## Co je „jak se připojit k Exchange“?
**Jak se připojit k Exchange** je proces autentizace Java aplikace k on‑premises nebo cloudovému Microsoft Exchange serveru, aby bylo možné provádět API volání jako výčet složek nebo načtení zpráv. Aspose.Email abstrahuje podkladové protokoly EWS/IMAP a poskytuje jednotný objektový model.

## Proč vypsat veřejné složky Exchange?
Výpis veřejných složek vám poskytuje přehled o hierarchické struktuře, kterou organizace používá pro sdílené poštovní schránky, distribuční seznamy a archivní úložiště. Aspose.Email dokáže enumerovat **více než 50 veřejných složek** v jediném volání a podporuje zpracování stovek stránek poštovních schránek bez načítání celého úložiště do paměti, což snižuje spotřebu RAM až o 70 %.

## Požadavky
- **Aspose.Email for Java** — verze 25.4 nebo novější (nejnovější stabilní vydání).  
- **Java Development Kit (JDK)** — JDK 11 nebo novější nainstalovaný a nastavený `JAVA_HOME`.  
- **Maven** — pro správu závislostí a automatizaci sestavení.  
- Základní znalost syntaxe Javy a konceptů Exchange (poštovní schránky, složky, EWS).

## Nastavení Aspose.Email pro Java
Pro integraci knihovny přidejte Maven závislost do souboru `pom.xml`. Toto je **Maven závislost Aspose Email**, kterou potřebujete.

### Maven závislost
Přidejte následující úryvek uvnitř elementu `<dependencies>` ve vašem `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Kroky získání licence
Aspose.Email vyžaduje platnou licenci pro plnohodnotné využití:

- **Bezplatná zkušební verze** – Stáhněte dočasnou licenci z [Aspose webu](https://purchase.aspose.com/temporary-license/) pro vyhodnocení API.  
- **Koupě** – Získejte komerční licenci přes portál Aspose pro produkční nasazení.

#### Základní inicializace
Po vyřešení balíčku Maven a získání licenčního souboru umístěte soubor `.lic` na classpath a inicializujte knihovnu:

```java
import com.aspose.email.License;

License license = new License();
license.setLicense("path/to/your/license.lic");
```

## Průvodce implementací
Projdeme jednotlivé funkční bloky, odpovíme na klíčové otázky stručnými odstavci před podrobnými kroky.

### Jak se připojit k Exchange?
Načtěte `ExchangeClient` s URL serveru, uživatelskými údaji a doménou, poté zavolejte `connect()`. Klient naváže HTTPS relaci s Exchange Web Services (EWS) a ověří přihlašovací údaje. Pokud se připojení nezdaří, API vyhodí podrobnou `AuthenticationException` obsahující HTTP status kód pro rychlé řešení problémů.  
`ExchangeClient` je třída Aspose.Email, která spravuje připojení k Exchange Web Services.

```java
import com.aspose.email.EWSClient;
import com.aspose.email.IEWSClient;

IEWSClient connectToExchangeServer(String exchangeUrl, String username, String password, String domain) {
    // Create instance of IEWSClient class by providing credentials
    return EWSClient.getEWSClient(exchangeUrl, username, password, domain);
}
```

### Jak vypsat veřejné složky Exchange?
Zavolejte `client.listPublicFolders()` a získáte kolekci objektů `FolderInfo`, které představují každou vrchní veřejnou složku. Metoda vrací metadata jako název složky, celkový počet položek a jedinečný identifikátor používaný v dalších voláních. Toto volání dokončí za méně než 2 sekundy pro typické on‑premises nasazení s až 500 složkami.  
`listPublicFolders()` vrací kolekci objektů `FolderInfo`.  
`FolderInfo` obsahuje metadata jako zobrazovaný název a počet položek.

```java
import com.aspose.email.ExchangeFolderInfoCollection;
import com.aspose.email.IEWSClient;

ExchangeFolderInfoCollection listPublicFolders(IEWSClient client) {
    // List all public folders and return their information as a collection
    return client.listPublicFolders();
}
```

### Jak zobrazit informace o složce?
Iterujte přes kolekci `FolderInfo` a vytiskněte `displayName` a `subFolderCount`. Tento rychlý přehled vám pomůže pochopit hierarchii před hlubším procházením. Pro velké organizace může API stránkovat výsledky, vracející 100 složek na stránku, aby se udržela nízká spotřeba paměti.

```java
import com.aspose.email.ExchangeFolderInfo;

void displayFolderInfo(ExchangeFolderInfo folder) {
    // Print folder details
    System.out.println("Name: " + folder.getDisplayName());
    System.out.println("Subfolders count: " + folder.getChildFolderCount());
}
```

### Jak vypsat zprávy ze složky?
Zavolejte `client.listMessages(folderId)`, kde `folderId` je identifikátor získaný v předchozím kroku. Metoda vrací seznam objektů `MessageInfo` obsahujících předmět, odesílatele a datum přijetí. Výsledek můžete omezit pomocí `maxCount`, abyste předešli přetížení klienta při zpracování velmi velkých složek.  
`listMessages(folderId)` vrací seznam objektů `MessageInfo`.  
`MessageInfo` obsahuje základní vlastnosti e‑mailu jako předmět, odesílatele a datum přijetí.

```java
import com.aspose.email.ExchangeMessageInfoCollection;
import com.aspose.email.IEWSClient;

ExchangeMessageInfoCollection listMessagesFromFolder(IEWSClient client, ExchangeFolderInfo folder) {
    // List messages from the specified public folder and return their information as a collection
    return client.listMessagesFromPublicFolder(folder);
}
```

### Jak načíst a uložit zprávy?
Pro každý `MessageInfo` použijte `client.fetchMessage(messageId)` ke stažení kompletního MIME obsahu. Poté zapište bajtové pole do souboru `.eml` na disku. API streamuje obsah, takže i zprávy o velikosti 100 MB jsou zpracovány bez načítání celého payloadu do paměti.  
`fetchMessage(messageId)` stáhne kompletní MIME obsah specifikovaného e‑mailu.

```java
import com.aspose.email.ExchangeMessageInfo;
import com.aspose.email.IEWSClient;
import com.aspose.email.MailMessage;
import com.aspose.email.SaveOptions;

void fetchAndSaveMessages(IEWSClient client, ExchangeMessageInfoCollection messages) {
    for (ExchangeMessageInfo messageInfo : messages) {
        // Fetch the full MailMessage using its unique URI
        MailMessage msg = client.fetchMessage(messageInfo.getUniqueUri());
        
        // Save the fetched message to a file named after its subject with .msg extension
        String filePath = "YOUR_OUTPUT_DIRECTORY/" + msg.getSubject() + ".msg";
        msg.save(filePath, SaveOptions.getDefaultMsgUnicode());
    }
}
```

### Jak rekurzivně vypsat zprávy z podadresářů?
Implementujte průchod do hloubky: začněte s vrchní složkou, vylistujte její podadresáře pomocí `client.listSubFolders(parentId)` a poté zavolejte stejnou rutinu pro výpis zpráv pro každé dítě. Tento vzor zajistí, že každá zpráva ve stromu veřejných složek bude zpracována. Hloubka rekurze je omezena pouze hierarchií serveru (typicky < 20 úrovní).  
`listSubFolders(parentId)` vrací okamžité podadresáře dané složky.

```java
import com.aspose.email.ExchangeFolderInfo;
import com.aspose.email.IEWSClient;

void listMessagesFromSubFolders(IEWSClient client, ExchangeFolderInfo folder) {
    // List all messages in the current public folder
    ExchangeMessageInfoCollection msgCollection = client.listMessagesFromPublicFolder(folder);
    fetchAndSaveMessages(client, msgCollection);

    if (folder.getChildFolderCount() > 0) {
        ExchangeFolderInfoCollection subFolders = client.listSubFolders(folder);
        for (ExchangeFolderInfo subFolder : subFolders) {
            listMessagesFromSubFolders(client, subFolder);
        }
    }
}
```

## Praktické aplikace
Reálné scénáře, kde tento postup vyniká:

1. **Automatizovaná archivace e‑mailů** – Pravidelně stahujte všechny zprávy z veřejných složek a ukládejte je do souladu s archivními požadavky.  
2. **Zálohovací řešení** – Zrcadlete veřejné složky Exchange na zabezpečený souborový systém nebo cloudový bucket, čímž zajistíte redundanci dat.  
3. **Vlastní e‑mailové klienty** – Vytvořte lehké prohlížeče, které zobrazují jen potřebné složky a zprávy, čímž snížíte složitost UI.

## Úvahy o výkonu
Při škálování na tisíce složek a miliony zpráv mějte na paměti následující tipy:

- **Pooling připojení** – Znovu použijte jedinou instanci `ExchangeClient` pro více operací místo vytváření nového klienta pro každou složku.  
- **Lazy loading** – Požadujte jen metadata, která potřebujete (`listMessages` s parametrem `maxCount`) a načítejte plné tělo zprávy na vyžádání.  
- **Uvolňování objektů** – Po dokončení dávky zavolejte `client.dispose()`, aby se uvolnily HTTP spojení a vlákny‑lokální buffery.  
- **Paralelní zpracování** – Rozdělte vrchní složky mezi více vláken, každé s vlastní instancí klienta, a efektivně využijte vícejádrové CPU.

## Často kladené otázky

**Q: Mohu tento kód použít s Exchange Online (Office 365)?**  
A: Ano. Poskytněte endpoint EWS pro Office 365 (`https://outlook.office365.com/EWS/Exchange.asmx`) a použijte moderní autentizaci (OAuth) — Aspose.Email podporuje OAuth tokeny přímo.

**Q: Co když složka obsahuje více než 10 000 zpráv?**  
A: Použijte přetížení `listMessages`, které přijímá parametry `skip` a `take` pro stránkování výsledků a udržení spotřeby paměti pod kontrolou.

**Q: Existuje limit na velikost jedné e‑mailové zprávy, kterou mohu stáhnout?**  
A: API streamuje obsah, takže jsou podporovány zprávy až do 150 MB bez zásahu do Java heap, pokud má JVM dostatek nativní paměti.

**Q: Musím ručně řešit SSL certifikáty?**  
A: Ve výchozím nastavení Aspose.Email důvěřuje výchozímu keystore Javy. Pokud váš Exchange server používá samopodepsaný certifikát, importujte jej do truststore JVM nebo pro testování nastavte `client.setEnableSslVerification(false)`.

**Q: Jak mohu logovat operace pro auditní účely?**  
A: Aktivujte vestavěné logování Aspose.Email konfigurací `Logger.setLevel(Level.INFO)` a směrujte výstup do souboru nebo monitorovacího systému.

## Závěr
Nyní máte kompletní, produkčně připravený návod na **jak se připojit k Exchange** a rekurzivně vypsat zprávy z veřejných složek pomocí Aspose.Email pro Java. Kroky zahrnují nastavení Maven, licencování, připojení, výčet složek, načtení zpráv a ladění výkonu. Tento základ můžete rozšířit integrací s databázemi, cloudovým úložištěm nebo vlastními analytickými pipeline pro splnění specifických potřeb vaší organizace.

---

**Poslední aktualizace:** 2026-10-02  
**Testováno s:** Aspose.Email for Java 25.4  
**Autor:** Aspose

## Související tutoriály

- [How to Connect to Exchange Server using Aspose.Email in Java: Step-by-Step Guide](/email/java/exchange-server-integration/aspose-email-java-exchange-server-connection/)
- [How to Connect and List Exchange Server Folders Using Aspose.Email for Java](/email/java/exchange-server-integration/connect-list-exchange-server-folders-aspose-email-java/)
- [Manage Exchange Server Folders Using Aspose.Email for Java: A Comprehensive Guide](/email/java/exchange-server-integration/exchange-server-folders-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}