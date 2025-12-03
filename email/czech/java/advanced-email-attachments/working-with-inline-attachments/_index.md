---
date: 2025-12-01
description: Naučte se, jak odesílat e‑mail s vloženým obrázkem pomocí Aspose.Email
  pro Javu. Tento průvodce ukazuje, jak vložit obrázky do e‑mailu a vytvořit HTML
  e‑mail v Javě s vloženými přílohami.
language: cs
linktitle: Working with Inline Attachments in Aspose.Email
second_title: Aspose.Email Java Email Management API
title: Jak odeslat e‑mail s vloženým obrázkem pomocí Aspose.Email pro Javu
url: /java/advanced-email-attachments/working-with-inline-attachments/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Jak odeslat e‑mail s vloženým obrázkem pomocí Aspose.Email pro Java

Vkládání obrázků přímo do e‑mailu dává vašim zprávám profesionální vzhled a zajišťuje, že příjemce uvidí grafiku, aniž by musel stahovat samostatné soubory. V tomto tutoriálu se naučíte **jak odeslat e‑mail s vloženým obrázkem** pomocí Aspose.Email pro Java, přičemž pokryjeme vše od nastavení knihovny po vytvoření HTML e‑mailu, přidání inline zdrojů a nakonec odeslání zprávy.

## Rychlé odpovědi
- **Jaká je hlavní třída pro inline obrázky?** `LinkedResource`
- **Která metoda odkazuje na obrázek v HTML?** Použijte `cid:yourContentId` v tagu `<img>`
- **Potřebuji licenci pro vývoj?** Bezplatná zkušební verze funguje pro testování; licence je vyžadována pro produkci
- **Mohu e‑mail odeslat přes libovolný SMTP server?** Ano, stačí nakonfigurovat `SmtpClient` s podrobmi o vašem serveru
- **Je tento přístup kompatibilní se všemi hlavními e‑mailovými klienty?** Většina moderních klientů (Outlook, Gmail, Thunderbird) podporuje CID‑vložené obrázky

## Co jsou inline přílohy (vložené obrázky)?

Inline přílohy — někdy nazývané vložené nebo CID obrázky — jsou soubory, které jsou umístěny uvnitř MIME těla e‑mailu. Na ně se odkazuje z HTML části zprávy pomocí **Content‑ID** (CID). Tato technika vám umožní **vložit obrázky do e‑mailu**, aby se zobrazily přesně tam, kde umístíte tag `<img>`, aniž by se objevily jako samostatné ke stažení přílohy.

## Proč používat vložené obrázky ve vašich Java e‑mailových zprávách?

- **Profesionální vzhled:** Loga, bannery a produktové obrázky se zobrazí okamžitě.
- **Lepší zapojení:** Příjemci pravděpodobněji přečtou e‑mail, který vypadá kompletně.
- **Žádné další kliky:** Uživatelé nemusí stahovat přílohu, aby viděli obrázek.
- **Konzistentní branding:** Vaše značkové materiály zůstávají v souladu s obsahem zprávy.

## Požadavky

- Knihovna Aspose.Email pro Java (stáhněte z oficiální [Aspose.Email for Java documentation](https://reference.aspose.com/email/java/))
- Vývojové prostředí Java 8+
- Přístup k SMTP serveru pro odesílání pošty
- Soubor obrázku, který chcete vložit (např. `logo.png`)

## Průvodce krok za krokem

### Krok 1: Vytvořte základní HTML e‑mailovou zprávu

Nejprve nastavte jednoduchý `MailMessage` s HTML tělem. Toto bude plátno, do kterého později vložíme obrázek.

```java
// Import necessary classes
import com.aspose.email.MailAddress;
import com.aspose.email.MailMessage;

// Create a new email message
MailMessage message = new MailMessage();
message.setSubject("Hello, World!");
message.setFrom(new MailAddress("sender@example.com"));
message.setTo(new MailAddress("recipient@example.com"));
message.setHtmlBody("<html><body>This is a sample email with inline attachments.</body></html>");
```

### Krok 2: Přidejte inline obrázek pomocí `LinkedResource`

Nyní vložíme obrázek. Třída `LinkedResource` představuje inline přílohu. Přidělte jedinečný **Content‑ID** a odkažte na něj v HTML těle pomocí `cid:`.

```java
import com.aspose.email.LinkedResource;

// Create a LinkedResource for the image
LinkedResource linkedResource = new LinkedResource("path/to/your/image.png");
linkedResource.setContentId("image001"); // Unique ID for the inline image

// Add the LinkedResource to the HTML body
message.getLinkedResources().add(linkedResource);

// Reference the inline image in the HTML body
message.setHtmlBody("<html><body>This is an inline image: <img src='cid:image001'></body></html>");
```

> **Tip:** Udržujte `ContentId` jednoduchý a jedinečný v rámci zprávy, aby nedocházelo ke konfliktům.

### Krok 3: Odeslat e‑mail pomocí `SmtpClient`

Nakonfigurujte nastavení SMTP a odešlete zprávu. Vložený obrázek cestuje spolu s e‑mailem, takže jej příjemce uvidí okamžitě.

```java
import com.aspose.email.SmtpClient;

// Create an instance of SmtpClient
SmtpClient client = new SmtpClient("smtp.example.com", 587, "username", "password");

// Send the email
client.send(message);
```

### Krok 4: Přijmout a extrahovat inline obrázky (volitelné)

Pokud potřebujete zpracovat příchozí zprávy, které obsahují vložené obrázky, můžete načíst soubor `.eml` a získat jeho `LinkedResources`.

```java
import com.aspose.email.MailMessage;
import com.aspose.email.LinkedResourceCollection;

// Load the received email message
MailMessage receivedMessage = MailMessage.load("path/to/received_email.eml");

// Access the inline attachments
LinkedResourceCollection inlineAttachments = receivedMessage.getLinkedResources();
```

## Časté problémy a jak je opravit

| Problém | Proč k tomu dochází | Řešení |
|-------|----------------|-----|
| **Neshoda Content‑ID** | Odkaz `cid:` v HTML neodpovídá `ContentId` nastavenému na `LinkedResource`. | Ujistěte se, že řetězce jsou identické (`image001` vs `cid:image001`). |
| **Soubor nenalezen** | Cesta k obrázku je nesprávná nebo soubor chybí. | Ověřte absolutní/relativní cestu a že soubor existuje na serveru. |
| **Selhání SMTP autentizace** | Špatné přihlašovací údaje nastavení serveru. | Zkontrolujte hostitele, port, uživatelské jméno a heslo. Povolte TLS/SSL, pokud je vyžadováno. |
| **Obrázek se nezobrazuje v některých klientech** | Některé klienty blokují externí zdroje. | Použijte CID‑vložené obrázky (jak je ukázáno) místo externích URL. |

## Často kladené otázky

**Q: Jak si mohu stáhnout Aspose.Email pro Java?**  
A: Aspose.Email pro Java můžete stáhnout z [documentation](https://reference.aspose.com/email/java/). Postupujte podle instalačních pokynů a nastavte jej ve svém projektu.

**Q: Mohu používat Aspose.Email pro Java s jinými Java knihovnami?**  
A: Ano, Aspose.Email se hladce integruje s ostatními Java knihovnami, což vám umožní kombinovat zpracování e‑mailů s generováním PDF, OCR nebo přístupem k databázi.

**Q: Jaké formáty souborů jsou podporovány pro inline přílohy?**  
A: Běžné formáty obrázků jako PNG, JPEG, GIF, stejně jako další typy dokumentů (např. SVG) jsou podporovány jako inline zdroje.

**Q: Jak zacházet s inline přílohami v HTML e‑mailových zprávách?**  
A: Použijte třídu `LinkedResource` k přiřazení `ContentId`, přidejte ji do `message.getLinkedResources()` a odkažte na ni v HTML těle pomocí `<img src='cid:yourContentId'>`.

**Q: Je Aspose.Email pro Java kompatibilní s různými e‑mailovými servery?**  
A: Ano, funguje s libovolným SMTP/IMAP/POP3 serverem. Stačí zadat správnou adresu serveru, port a údaje pro autentizaci.

---

**Poslední aktualizace:** 2025-12-01  
**Testováno s:** Aspose.Email pro Java 24.12 (nejnovější v době psaní)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}