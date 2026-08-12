---
date: 2026-04-28
description: Naučte se, jak vložit obrázek do HTML e‑mailu pomocí Aspose.Email pro
  Javu a odeslat e‑mail s vloženým obrázkem přes SMTP.
keywords:
- embed image in html email
- send email with embedded image
- how to embed image java
- create html email java
- send email via smtp java
linktitle: Práce s vloženými přílohami v Aspose.Email
second_title: Aspose.Email Java Email Management API
title: Jak vložit obrázek do HTML e‑mailu pomocí Aspose.Email pro Javu
url: /cs/java/advanced-email-attachments/working-with-inline-attachments/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Jak vložit obrázek do html e‑mailu pomocí Aspose.Email pro Java

Vložení obrázku přímo do e‑mailu dodá vašim zprávám profesionální vzhled a zajistí, že příjemce uvidí grafiku bez nutnosti stahovat samostatné soubory. V tomto tutoriálu se naučíte **jak vložit obrázek do html e‑mailu** pomocí Aspose.Email pro Java, od nastavení knihovny až po vytvoření HTML e‑mailu, přidání vložených zdrojů a nakonec odeslání zprávy přes SMTP.

## Rychlé odpovědi
- **Jaká třída je primární pro vložené obrázky?** `LinkedResource`
- **Která metoda odkazuje na obrázek v HTML?** Použijte `cid:yourContentId` v tagu `<img>`
- **Potřebuji licenci pro vývoj?** Pro testování stačí bezplatná zkušební verze; pro produkci je licence vyžadována
- **Mohu e‑mail odeslat přes libovolný SMTP server?** Ano, stačí nakonfigurovat `SmtpClient` s údaji o vašem serveru
- **Je tento přístup kompatibilní se všemi hlavními e‑mailovými klienty?** Většina moderních klientů (Outlook, Gmail, Thunderbird) podporuje CID‑vložené obrázky

## Jak vložit obrázek do html e‑mailu pomocí Aspose.Email pro Java

Když **vložíte obrázek do html e‑mailu**, obrázek se stane součástí těla MIME, takže se okamžitě zobrazí v klientovi příjemce. Níže projdeme celý proces, od jednoduché HTML zprávy až po plně vybavený e‑mail s vloženým obrázkem.

### Co jsou inline přílohy (vložené obrázky)?

Inline přílohy – někdy nazývané vložené nebo CID obrázky – jsou soubory, které žijí uvnitř těla MIME e‑mailu. Na ně se odkazuje z HTML části zprávy pomocí **Content‑ID** (CID). Tato technika vám umožní **vložit obrázky do e‑mailu**, aby se zobrazily přesně tam, kde umístíte tag `<img>`, aniž by se objevily jako samostatné stahovatelné přílohy.

### Proč používat vložené obrázky ve vašich Java e‑mailových zprávách?

- **Profesionální vzhled:** Loga, bannery a produktové obrázky se zobrazí okamžitě.
- **Vyšší zapojení:** Příjemci pravděpodobněji přečtou e‑mail, který vypadá kompletně.
- **Žádné další kliky:** Uživatelé nemusí stahovat přílohu, aby viděli obrázek.
- **Konzistentní brand:** Vaše značkové materiály zůstávají v linii se obsahem zprávy.

### Předpoklady

- Knihovna Aspose.Email pro Java (stáhněte z oficiální [Aspose.Email for Java documentation](https://reference.aspose.com/email/java/))
- Vývojové prostředí Java 8+
- Přístup k SMTP serveru pro odesílání pošty
- Soubor obrázku, který chcete vložit (např. `logo.png`)

## Průvodce krok za krokem

### Krok 1: Vytvořte základní HTML e‑mailovou zprávu

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

### Krok 2: Přidejte inline obrázek pomocí `LinkedResource`

Nyní vložíme obrázek. Třída `LinkedResource` představuje inline přílohu. Přiřaďte jedinečný **Content‑ID** a odkažte na něj v HTML těle pomocí `cid:`.

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

> **Tip:** Udržujte `ContentId` jednoduchý a jedinečný v rámci zprávy, aby nedošlo ke konfliktům.

### Krok 3: Odeslání e‑mailu přes `SmtpClient`

Nakonfigurujte nastavení SMTP a odešlete zprávu. Vložený obrázek cestuje spolu s e‑mailem, takže jej příjemce uvidí okamžitě.

```java
import com.aspose.email.SmtpClient;

// Create an instance of SmtpClient
SmtpClient client = new SmtpClient("smtp.example.com", 587, "username", "password");

// Send the email
client.send(message);
```

### Krok 4: Přijmutí a extrakce inline obrázků (volitelné)

Pokud potřebujete zpracovat příchozí zprávy, které obsahují vložené obrázky, můžete načíst soubor `.eml` a získat jeho `LinkedResources`.

```java
import com.aspose.email.MailMessage;
import com.aspose.email.LinkedResourceCollection;

// Load the received email message
MailMessage receivedMessage = MailMessage.load("path/to/received_email.eml");

// Access the inline attachments
LinkedResourceCollection inlineAttachments = receivedMessage.getLinkedResources();
```

## Časté problémy a jak je vyřešit

| Problém | Proč k tomu dochází | Řešení |
|-------|----------------|-----|
| **Neshoda Content‑ID** | Odkaz `cid:` v HTML neodpovídá `ContentId` nastavenému na `LinkedResource`. | Ujistěte se, že řetězce jsou identické (`image001` vs `cid:image001`). |
| **Soubor nenalezen** | Cesta k obrázku je nesprávná nebo soubor chybí. | Ověřte absolutní/relativní cestu a že soubor existuje na serveru. |
| **Selhání autentizace SMTP** | Nesprávné přihlašovací údaje nebo nastavení serveru. | Zkontrolujte hostitele, port, uživatelské jméno a heslo. Povolte TLS/SSL, pokud je vyžadováno. |
| **Obrázek se nezobrazuje v některých klientech** | Některé klienty blokují externí zdroje. | Používejte CID‑vložené obrázky (jak je ukázáno) místo externích URL. |

## Často kladené otázky

**Q: Jak si stáhnu Aspose.Email pro Java?**  
A: Aspose.Email pro Java si můžete stáhnout z [dokumentace](https://reference.aspose.com/email/java/). Postupujte podle instalačních instrukcí a nastavte knihovnu ve svém projektu.

**Q: Můžu použít Aspose.Email pro Java s jinými Java knihovnami?**  
A: Ano, Aspose.Email se hladce integruje s ostatními Java knihovnami, což vám umožní kombinovat zpracování e‑mailů s generováním PDF, OCR nebo přístupem k databázím.

**Q: Jaké formáty souborů jsou podporovány pro inline přílohy?**  
A: Běžné formáty obrázků jako PNG, JPEG, GIF, stejně jako další typy dokumentů (např. SVG) jsou podporovány jako inline zdroje.

**Q: Jak zacházet s inline přílohami v HTML e‑mailu?**  
A: Použijte třídu `LinkedResource` k přiřazení `ContentId`, přidejte ji do `message.getLinkedResources()` a odkažte na ni v HTML těle pomocí `<img src='cid:yourContentId'>`.

**Q: Je Aspose.Email pro Java kompatibilní s různými e‑mailovými servery?**  
A: Ano, funguje s libovolným SMTP/IMAP/POP3 serverem. Stačí zadat správnou adresu serveru, port a autentizační údaje.

## Závěr

Nyní máte kompletní, připravený recept na **vložený obrázek do html e‑mailu** s Aspose.Email pro Java. Vytvořením `LinkedResource`, přiřazením jedinečného Content‑ID a odkazem pomocí `cid:` ve vašem HTML těle zajistíte, že loga, bannery nebo produktové fotografie se objeví přesně tam, kde je chcete – bez dalších stahování nebo nefunkčních odkazů. Kombinujte to s robustní třídou `SmtpClient` pro odeslání zprávy přes libovolný SMTP server a budete připraveni doručovat vyladěné, značkově konzistentní e‑maily z vašich Java aplikací.

---

**Poslední aktualizace:** 2026-04-28  
**Testováno s:** Aspose.Email pro Java 24.12 (nejnovější v době psaní)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}