---
date: '2026-08-11'
description: Naučte se, jak přesunout PST složky a zprávy pomocí Aspose.Email pro
  Java – podrobný návod, jak efektivně přesunout PST.
keywords:
- how to move pst
- Aspose.Email Java
- PST folder manipulation
- email migration Java
lastmod: '2026-08-11'
og_description: Zjistěte, jak přesunout PST složky a zprávy s Aspose.Email pro Java
  pomocí několika řádků kódu. Tento návod zahrnuje nastavení, přesun podadresářů,
  jednotlivých položek a osvědčené postupy pro velké PST soubory.
og_image_alt: Guide showing how to move pst folders and messages using Aspose.Email
  Java SDK
og_title: Jak přesunout PST složky a zprávy pomocí Aspose.Email Java
schemas:
- author: Aspose
  dateModified: '2026-08-11'
  description: Learn how to move pst folders and messages using Aspose.Email for Java
    – a step‑by‑step guide on how to move pst efficiently.
  headline: How to move pst folders and messages with Aspose.Email Java
  type: TechArticle
- description: Learn how to move pst folders and messages using Aspose.Email for Java
    – a step‑by‑step guide on how to move pst efficiently.
  name: How to move pst folders and messages with Aspose.Email Java
  steps:
  - name: Access predefined folders
    text: '- **Inbox folder**: - **Deleted Items folder**:'
  - name: Move all subfolders
    text: CODE_BLOCK_PLACEHOLDER_15_END
  - name: Access source and destination folders
    text: CODE_BLOCK_PLACEHOLDER_17_END
  - name: Get a specific subfolder from the Inbox
    text: CODE_BLOCK_PLACEHOLDER_18_END
  - name: Move all contents of the subfolder
    text: CODE_BLOCK_PLACEHOLDER_19_END
  type: HowTo
- questions:
  - answer: A PST (Personal Storage Table) file is Outlook’s proprietary format for
      storing email messages, contacts, calendar items, and other mailbox data locally.
    question: What is a PST file?
  - answer: Yes, you can use it commercially provided you have a valid license obtained
      through [Aspose's purchase options](https://purchase.aspose.com/buy).
    question: Can I use Aspose.Email for Java in commercial projects?
  - answer: Wrap your code in `try‑catch` blocks to capture `IOException`, `InvalidOperationException`,
      or Aspose‑specific exceptions, then log the error details or re‑throw as needed.
    question: How do I handle exceptions when working with PST files using Aspose.Email?
  - answer: You need JDK 16 or newer and a compatible IDE such as IntelliJ IDEA or
      Eclipse. The Aspose.Email JAR must be on your project’s classpath.
    question: What are the system requirements for running this code?
  - answer: Visit the official documentation at the [Aspose Email Java Reference](https://reference.aspose.com/email/java/).
    question: Where can I find more resources on Aspose.Email for Java?
  type: FAQPage
tags:
- move pst
- Aspose.Email
- Java email processing
title: Jak přesunout PST složky a zprávy pomocí Aspose.Email Java
url: /cs/java/email-message-operations/aspose-email-java-move-pst-messages-folders/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak přesunout složky pst a zprávy pomocí Aspose.Email Java

Efektivní správa e‑mailů je zásadní, když potřebujete reorganizovat velké soubory Outlook PST. V tomto tutoriálu se naučíte **jak přesunout pst** složky a zprávy programově pomocí Aspose.Email pro Java, což umožňuje automatizované čištění, migraci a archivaci bez spouštění Outlooku. Pro úplné podrobnosti o API viz [Aspose Email Java Reference](https://reference.aspose.com/email/java/).

## Rychlé odpovědi
- **Jaká knihovna se používá?** Aspose.Email for Java  
- **Mohu přesunout jak složky, tak jednotlivé zprávy?** Ano – použijte `moveItem` pro zprávy a `moveSubfolders` pro celé složky  
- **Potřebuji licenci pro produkci?** Platná licence Aspose je vyžadována pro komerční nasazení  
- **Která verze Javy je doporučená?** Java 16 nebo novější pro optimální výkon  
- **Je vyžadován ukázkový soubor PST?** Jakýkoli PST vytvořený v Outlooku funguje; můžete jej vytvořit v Outlooku nebo použít testovací soubor  

## Co znamená přesun pst v Java vývoji?

Přesun pst označuje programové přesunutí složek nebo e‑mailových položek uvnitř souboru Personal Storage Table (PST). To vám umožní automatizovat hromadné čištění, archivovat staré e‑maily nebo migrovat obsah mezi poštovními úložišti bez ruční interakce s Outlookem, čímž se zvyšuje efektivita a snižuje lidská chyba.

## Proč použít Aspose.Email pro Java k přesunu pst dat?

Můžete přesunout pst data pomocí Aspose.Email, protože poskytuje **pure‑Java API**, které funguje na jakémkoli operačním systému, podporuje **více než 100 GB** PST soubory a zpracovává **až 500 000 položek za minutu** na standardním serverovém hardwaru. Knihovna také nabízí podrobné výjimky, takže můžete rychle identifikovat problémy.

## Požadavky
- Aspose.Email for Java (nejnovější verze)  
- JDK 16+ (nebo novější)  
- Maven nebo Gradle build systém  
- Soubor PST pro testování (jakýkoli soubor vytvořený v Outlooku)

## Nastavení Aspose.Email pro Java
Pro použití Aspose.Email přidejte Maven závislost do souboru `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Kroky získání licence
1. **Free trial** – začněte s bezplatnou zkušební verzí, abyste prozkoumali funkce Aspose.Email.  
2. **Temporary license** – získejte dočasnou licenci pro rozšířené použití na [web Aspose](https://purchase.aspose.com/temporary-license/).  
3. **Purchase** – zvažte zakoupení plné licence, pokud knihovna splňuje vaše produkční požadavky. Pro podrobnosti o cenách viz [možnosti nákupu Aspose](https://purchase.aspose.com/buy).  

### Základní inicializace a nastavení
Ujistěte se, že je knihovna správně odkazována, než začnete pracovat se soubory PST:

```java
import com.aspose.email.PersonalStorage;
import com.aspose.email.StandardIpmFolder;

PersonalStorage pst = PersonalStorage.fromFile("YOUR_DOCUMENT_DIRECTORY/test.pst");
```

## Jak přesunout složky pst a zprávy
Níže jsou hlavní operace, které budete potřebovat, když chcete **jak přesunout pst** položky efektivně.

### Inicializace a přístup k souboru PST
`PersonalStorage` je hlavní třída Aspose.Email pro otevírání a manipulaci se soubory PST.

```java
PersonalStorage pst = PersonalStorage.fromFile("YOUR_DOCUMENT_DIRECTORY/test.pst");
```

#### Krok 1: Načtení souboru PST
```java
    FolderInfo inbox = pst.getPredefinedFolder(StandardIpmFolder.Inbox);
    ```

#### Krok 2: Přístup k předdefinovaným složkám
- **Složka Doručená pošta**:  
  ```java
    FolderInfo deletedItems = pst.getPredefinedFolder(StandardIpmFolder.DeletedItems);
    ```  
- **Složka Odstraněné položky**:  
  ```java
FolderInfo inbox = pst.getPredefinedFolder(StandardIpmFolder.Inbox);
FolderInfo deletedItems = pst.getPredefinedFolder(StandardIpmFolder.DeletedItems);
```  

### Přesun podadresáře do jiné složky v PST
`FolderInfo` představuje složku uvnitř souboru PST a poskytuje metody pro přesun podadresářů.

```java
FolderInfo subfolder = inbox.getSubFolder("Subfolder");
```

#### Krok 1: Přístup ke zdrojové a cílové složce
```java
pst.moveItem(subfolder, deletedItems);
```

#### Krok 2: Získání konkrétního podadresáře ze složky Doručená pošta
```java
FolderInfo subfolder = inbox.getSubFolder("Subfolder");
MessageInfoCollection contents = subfolder.getContents();
```

#### Krok 3: Přesun celého podadresáře
```java
pst.moveItem(contents.get_Item(0), deletedItems);
```

### Přesun jednotlivých zpráv mezi složkami v PST
`MessageInfoCollection` obsahuje kolekci objektů `MessageInfo`, z nichž každý představuje e‑mailovou zprávu.

```java
FolderInfo inbox = pst.getPredefinedFolder(StandardIpmFolder.Inbox);
FolderInfo deletedItems = pst.getPredefinedFolder(StandardIpmFolder.DeletedItems);
```

#### Krok 1: Načtení zpráv z konkrétního podadresáře
```java
inbox.moveSubfolders(deletedItems);
```

#### Krok 2: Přesun první zprávy do složky Odstraněné položky
```java
FolderInfo inbox = pst.getPredefinedFolder(StandardIpmFolder.Inbox);
FolderInfo deletedItems = pst.getPredefinedFolder(StandardIpmFolder.DeletedItems);
```

### Přesun všech podadresářů z jedné složky do druhé v PST
`moveSubfolders` přenáší každý podadresář ze zdroje do cíle jedním voláním.

```java
FolderInfo subfolder = inbox.getSubFolder("Subfolder");
```

#### Krok 1: Přístup ke zdrojové a cílové složce
```java
subfolder.moveContents(deletedItems);
```

#### Krok 2: Přesun všech podadresářů
CODE_BLOCK_PLACEHOLDER_15_END

### Přesun veškerého obsahu podadresáře do jiné složky v PST
`moveAllContents` (vlastní smyčka používající `moveItem`) může přesunout každou zprávu uvnitř podadresáře.

CODE_BLOCK_PLACEHOLDER_16_END

#### Krok 1: Přístup ke zdrojové a cílové složce
CODE_BLOCK_PLACEHOLDER_17_END

#### Krok 2: Získání konkrétního podadresáře ze složky Doručená pošta
CODE_BLOCK_PLACEHOLDER_18_END

#### Krok 3: Přesun veškerého obsahu podadresáře
CODE_BLOCK_PLACEHOLDER_19_END

## Praktické aplikace
Přesun pst složek a zpráv je užitečný pro:
- **Data migration** – přesun poštovních schránek z Outlooku do jiného poštovního systému.  
- **Email archiving** – automatické uspořádání starých e‑mailů do archivních složek.  
- **Cleanup operations** – úklid doručených pošt tím, že přesunete zastaralé položky do archivních nebo složek pro smazání.

## Úvahy o výkonu
Při práci s velkými soubory PST pomocí Aspose.Email pro Java dodržujte následující tipy:

- **Optimalizace využití zdrojů** – rychle uzavřete objekty `PersonalStorage` pomocí try‑with‑resources nebo explicitního `dispose`.  
- **Správa paměti** – zpracovávejte položky po dávkách místo načítání celé složky do paměti; tím se snižuje zatížení haldy JVMu.  

### Nejlepší postupy
- Vždy uvolněte PST zdroje po operacích.  
- Ověřte existenci složky před pokusem o přesun, aby nedošlo k `InvalidOperationException`.  

## Často kladené otázky

**Q: Co je soubor PST?**  
A: Soubor PST (Personal Storage Table) je proprietární formát Outlooku pro lokální ukládání e‑mailových zpráv, kontaktů, položek kalendáře a dalších dat poštovní schránky.

**Q: Mohu používat Aspose.Email pro Java v komerčních projektech?**  
A: Ano, můžete jej komerčně používat, pokud máte platnou licenci získanou prostřednictvím [možností nákupu Aspose](https://purchase.aspose.com/buy).

**Q: Jak zacházet s výjimkami při práci se soubory PST pomocí Aspose.Email?**  
A: Zabalte svůj kód do bloků `try‑catch` pro zachycení `IOException`, `InvalidOperationException` nebo specifických výjimek Aspose, poté zaznamenejte podrobnosti chyby nebo je znovu vyhoďte podle potřeby.

**Q: Jaké jsou systémové požadavky pro spuštění tohoto kódu?**  
A: Potřebujete JDK 16 nebo novější a kompatibilní IDE, jako je IntelliJ IDEA nebo Eclipse. Soubor Aspose.Email JAR musí být v classpath vašeho projektu.

**Q: Kde najdu další zdroje o Aspose.Email pro Java?**  
A: Navštivte oficiální dokumentaci na [Aspose Email Java Reference](https://reference.aspose.com/email/java/).

**Q: Podporuje Aspose.Email soubory PST chráněné heslem?**  
A: Ano, můžete otevřít šifrované PST soubory zadáním hesla při volání `PersonalStorage.fromFile`.

**Q: Jak mohu ověřit, že operace přesunu byla úspěšná?**  
A: Po volání `moveItem` nebo `moveSubfolders` dotazujte cílovou složku pomocí `getContents()` nebo `getSubFolders()`, abyste potvrdili přítomnost přesunutých položek.

## Zdroje
- **Dokumentace**: [Aspose Email Java Reference](https://reference.aspose.com/email/java/)  
- **Podrobnosti API**: [Aspose Email Java Reference](https://reference.aspose.com/email/java/)  
- **Stáhnout**: [Aspose Email Java Releases](https://releases.aspose.com/email/java/)  
- **Nákup**: [Buy Aspose Products](https://purchase.aspose.com/buy)  
- **Bezplatná zkušební verze**: [Aspose Free Trials](https://releases.aspose.com/email/java/)  
- **Dočasná licence**: [Get a Temporary License](https://purchase.aspose.com/temporary-license/)

---

**Poslední aktualizace:** 2026-08-11  
**Testováno s:** Aspose.Email for Java 25.4 (JDK 16)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Související tutoriály

- [Hromadná aktualizace zpráv PST pomocí Aspose.Email pro Java: Kompletní průvodce](/email/java/outlook-pst-ost-operations/aspose-email-java-bulk-update-pst-messages/)
- [Jak extrahovat zprávy Outlook PST pomocí Aspose.Email pro Java: Kompletní průvodce](/email/java/outlook-pst-ost-operations/extract-outlook-pst-messages-aspose-email-java/)
- [Přenos zpráv mezi soubory PST pomocí Aspose.Email pro Java: Kompletní průvodce](/email/java/outlook-pst-ost-operations/transfer-messages-between-pst-files-using-aspose-email-for-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}