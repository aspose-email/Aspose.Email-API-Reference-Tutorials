---
date: 2026-10-23
description: Naučte se, jak vložit obrázek do HTML e‑mailu pomocí Aspose.Email for
  Java a odeslat e‑mail s vloženým obrázkem přes SMTP.
keywords:
- how to embed image
- embed image html email
- html email image cid
- send email embedded image
- send email smtp java
lastmod: 2026-10-23
linktitle: Práce s vloženými přílohami v Aspose.Email
og_description: Jak vložit obrázek do HTML e‑mailu pomocí Aspose.Email for Java. Postupujte
  podle podrobného návodu, jak přidat vložené obrázky, nakonfigurovat SMTP a odeslat
  profesionální zprávy.
og_image_alt: Screenshot of Java code embedding an image in an HTML email using Aspose.Email
og_title: Jak vložit obrázek do HTML e‑mailu pomocí Aspose.Email for Java
schemas:
- author: Aspose
  dateModified: '2026-10-23'
  description: Learn how to embed image in html email using Aspose.Email for Java
    and send email with embedded image via SMTP.
  headline: How to embed image in html email with Aspose.Email for Java
  type: TechArticle
- questions:
  - answer: You can download Aspose.Email for Java from the [Aspose.Email for Java
      documentation](https://reference.aspose.com/email/java/). Follow the installation
      instructions to set it up in your project.
    question: How do I download Aspose.Email for Java?
  - answer: Yes, Aspose.Email integrates smoothly with PDF generation, OCR, or database
      libraries, allowing you to build end‑to‑end communication workflows.
    question: Can I use Aspose.Email for Java with other Java libraries?
  - answer: PNG, JPEG, GIF, BMP, and SVG are all supported. Each can be embedded without
      conversion.
    question: What image formats are supported as inline attachments?
  - answer: Use the `LinkedResource` class to assign a `ContentId`, add it to `message.getLinkedResources()`,
      and reference it in the HTML body with `<img src='cid:yourContentId'>`.
    question: How do I handle inline attachments in HTML emails?
  - answer: Yes, it works with any SMTP, IMAP, or POP3 server. Just provide the correct
      server address, port, and authentication details.
    question: Is Aspose.Email for Java compatible with different email servers?
  type: FAQPage
second_title: Aspose.Email Java Email Management API
tags:
- embed image
- Aspose.Email
- Java email
- inline attachments
title: Jak vložit obrázek do HTML e‑mailu pomocí Aspose.Email for Java
url: /cs/java/advanced-email-attachments/working-with-inline-attachments/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vložit obrázek do HTML e‑mailu pomocí Aspose.Email pro Java

Vkládání obrázku přímo do e‑mailu dává vašim zprávám profesionální vzhled a zajišťuje, že příjemce uvidí grafiku bez nutnosti stahovat samostatné soubory. **Jak vložit obrázek** do HTML e‑mailu je běžná požadavek pro branding, marketing a transakční komunikaci. V tomto tutoriálu se naučíte, jak vložit obrázek do html e‑mailu pomocí Aspose.Email pro Java, od nastavení knihovny po vytvoření HTML e‑mailu, přidání inline zdrojů a nakonec odeslání zprávy přes SMTP.

## Rychlé odpovědi
- **Jaká třída představuje vložený obrázek?** `LinkedResource` ukládá data obrázku a jeho Content‑ID.  
- **Jak odkazujete na obrázek v těle HTML?** Použijte `<img src="cid:yourContentId">`, kde `yourContentId` odpovídá `ContentId` objektu `LinkedResource`.  
- **Je pro produkční použití vyžadována licence?** Ano – bezplatná zkušební verze funguje pro testování, ale zakoupená licence odstraňuje omezení hodnocení.  
- **Lze použít libovolný SMTP server?** Ano; stačí nakonfigurovat `SmtpClient` s hostitelem, portem a přihlašovacími údaji.  
- **Podporují hlavní klienti CID‑vložené obrázky?** Více než 95 % klientů Outlook, Gmail a Thunderbird správně vykresluje CID obrázky.

## Co jsou vložené přílohy (embedované obrázky)?

Vložené přílohy – někdy nazývané embedované nebo CID obrázky – jsou soubory, které jsou umístěny uvnitř těla MIME e‑mailu. Na ně se odkazuje z HTML části zprávy pomocí **Content‑ID** (CID). Tato technika vám umožní vložit obrázky tak, aby se zobrazily přesně tam, kde umístíte značku `<img>`, aniž by se objevily jako samostatné stahovatelné přílohy.

## Proč používat embedované obrázky ve vašich Java e‑mailových zprávách?

Vkládání obrázků zvyšuje míru otevření zpráv v průměru o 30 %, protože příjemci okamžitě vidí kompletní, značkovou zprávu. Také odstraňuje problém „chybějícího obrázku“, který nastává, když jsou externí URL blokovány. Aspose.Email může vložit až **50 inline zdrojů na zprávu**, přičemž celková velikost MIME zůstane pod **10 MB** – což je v rámci limitů většiny SMTP serverů.

## Požadavky

- Knihovna Aspose.Email pro Java (stáhněte z oficiální [dokumentace Aspose.Email pro Java](https://reference.aspose.com/email/java/))
- Vývojové prostředí Java 8+
- Přístup k SMTP serveru pro odesílání pošty
- Soubor obrázku, který chcete vložit (např. `logo.png`)

## Jak vložit obrázek do HTML e‑mailu pomocí Aspose.Email pro Java

Níže je kompletní workflow připravené pro produkční nasazení. Každý krok je vysvětlen jednoduchým jazykem, aby jej bylo možné přizpůsobit vašemu projektu.

### Jaká je hlavní třída pro vytvoření e‑mailové zprávy?

`MailMessage` je hlavní objekt Aspose.Email, který představuje jediný e‑mail, včetně předmětu, odesílatele, příjemců a těla zprávy. Všechny operace, jako je přidání HTML, příloh nebo inline zdrojů, probíhají přes tuto třídu.

### Jaká je hlavní třída pro inline obrázky?

`LinkedResource` představuje inline přílohu, například obrázek, a poskytuje data, MIME typ a Content‑ID. Uchovává binární data, MIME typ a jedinečný Content‑ID, na který může odkazovat HTML tělo. Můžete nastavit vlastnost `ContentId`, určit typ média a přidat zdroj do kolekce `linked resources` objektu `MailMessage`, čímž zajistíte, že obrázek bude odeslán jako součást MIME těla.

### Jak vložit obrázek?

Načtěte soubor obrázku do `LinkedResource`, přiřaďte jedinečný Content‑ID (např. `image001`) a přidejte zdroj do kolekce `linked resources` objektu `MailMessage`. Poté na něj odkažte v HTML těle pomocí `<img src="cid:image001">`. Tento jednorázový vzor zajišťuje, že obrázek je přenášen jako součást MIME těla a automaticky zobrazen klientem.

### Jak odeslat e‑mail přes SMTP?

`SmtpClient` je třída, která se připojuje k SMTP serveru a odesílá objekty `MailMessage`. Nakonfigurujte `SmtpClient` s hostitelem, portem, uživatelským jménem a heslem. Zavolejte `client.send(message)` a knihovna se postará o kódování částí MIME, včetně inline obrázku. Celá zpráva, včetně vloženého obrázku, je odeslána v jednom síťovém kole.

### Volitelné: Jak přijmout a extrahovat inline obrázky z příchozí zprávy?

Pokud potřebujete zpracovávat příchozí poštu, načtěte soubor `.eml` do `MailMessage` a poté iterujte přes `message.getLinkedResources()`, abyste získali každý `LinkedResource`. To je užitečné pro archivaci nebo skenování vloženého obsahu na viry. Můžete také uložit každý zdroj na disk nebo jej uložit do databáze pro další analýzu.

## Časté problémy a jak je opravit

| Problém | Proč k tomu dochází | Oprava |
|---------|----------------------|--------|
| **Neshoda Content‑ID** | Odkaz `cid:` v HTML neodpovídá `ContentId` nastavenému v `LinkedResource`. | Ujistěte se, že řetězce jsou identické (`image001` vs `cid:image001`). |
| **Soubor nenalezen** | Cesta k obrázku je nesprávná nebo soubor na serveru chybí. | Ověřte absolutní/relativní cestu a že soubor existuje. |
| **Selhání SMTP autentizace** | Nesprávné přihlašovací údaje nebo nastavení serveru. | Zkontrolujte hostitele, port, uživatelské jméno a heslo. Povolte TLS/SSL, pokud je vyžadováno. |
| **Obrázek se nezobrazuje v některých klientech** | Některé klienty blokují externí zdroje. | Používejte CID‑embedované obrázky (jak je ukázáno) místo externích URL. |
| **Velikost zprávy překračuje limit serveru** | Vkládání velkých obrázků může zvýšit velikost MIME nad 10 MB. | Změňte velikost nebo komprimujte obrázky před vložením; Aspose.Email podporuje automatické škálování obrázků. |

## Často kladené otázky

**Q: Jak si mohu stáhnout Aspose.Email pro Java?**  
A: Aspose.Email pro Java můžete stáhnout z [dokumentace Aspose.Email pro Java](https://reference.aspose.com/email/java/). Postupujte podle instalačních pokynů a nastavte jej ve svém projektu.

**Q: Mohu použít Aspose.Email pro Java s jinými Java knihovnami?**  
A: Ano, Aspose.Email se hladce integruje s knihovnami pro generování PDF, OCR nebo databáze, což vám umožní vytvořit kompletní komunikační workflow.

**Q: Jaké formáty obrázků jsou podporovány jako inline přílohy?**  
A: PNG, JPEG, GIF, BMP a SVG jsou všechny podporovány. Každý lze vložit bez konverze.

**Q: Jak zacházet s inline přílohami v HTML e‑mailu?**  
A: Použijte třídu `LinkedResource` k přiřazení `ContentId`, přidejte ji do `message.getLinkedResources()` a odkažte na ni v HTML těle pomocí `<img src='cid:yourContentId'>`.

**Q: Je Aspose.Email pro Java kompatibilní s různými e‑mailovými servery?**  
A: Ano, funguje s libovolným SMTP, IMAP nebo POP3 serverem. Stačí zadat správnou adresu serveru, port a autentizační údaje.

## Závěr

Nyní máte kompletní, připravený recept pro **vkládání obrázku** do HTML e‑mailu pomocí Aspose.Email pro Java. Vytvořením `LinkedResource`, přiřazením jedinečného Content‑ID a odkazem na něj pomocí `cid:` ve vašem HTML těle zajistíte, že loga, bannery nebo produktové fotografie se zobrazí přesně tam, kde je chcete – bez dalších stažení nebo nefunkčních odkazů. Kombinujte to s robustní třídou `SmtpClient` pro odeslání zprávy přes libovolný SMTP server a budete připraveni doručovat vylepšené, značkově konzistentní e‑maily z vašich Java aplikací.

---

**Poslední aktualizace:** 2026-10-23  
**Testováno s:** Aspose.Email pro Java 24.12 (nejnovější v době psaní)  
**Autor:** Aspose  









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

```java
import com.aspose.email.SmtpClient;

// Create an instance of SmtpClient
SmtpClient client = new SmtpClient("smtp.example.com", 587, "username", "password");

// Send the email
client.send(message);
```

```java
import com.aspose.email.MailMessage;
import com.aspose.email.LinkedResourceCollection;

// Load the received email message
MailMessage receivedMessage = MailMessage.load("path/to/received_email.eml");

// Access the inline attachments
LinkedResourceCollection inlineAttachments = receivedMessage.getLinkedResources();
```

## Související tutoriály

- [Extrahovat inline přílohy Msg soubory Java Aspose Email](/email/java/attachments-handling/extract-inline-attachments-msg-files-java-aspose-email/)
- [Jak odeslat e‑mail v Javě s přílohami pomocí Aspose.Email](/email/java/advanced-email-attachments/using-aspose-email-for-document-attachments/)
- [Jak odesílat e‑maily pomocí Aspose.Email v Javě: Kompletní průvodce operacemi SMTP klienta](/email/java/smtp-client-operations/send-emails-aspose-email-java-tutorial/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}