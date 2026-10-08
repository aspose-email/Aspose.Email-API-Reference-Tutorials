---
date: 2026-10-07
description: Zjistěte, jak přidat zápatí e‑mailu a přizpůsobit SMTP hlavičky v Javě,
  vytvořit e‑mailovou zprávu v Javě a personalizovat branding pomocí Aspose.Email.
keywords:
- how to add footer
- send email custom headers
- Aspose.Email Java
- email footer Java
- SMTP header customization
lastmod: 2026-10-07
linktitle: Přizpůsobení SMTP hlaviček a zápatí pomocí Aspose.Email
og_description: Jak přidat zápatí a přizpůsobit SMTP hlavičky v Javě s Aspose.Email.
  Naučte se vkládat HTML zápatí, nastavit vlastní hlavičky a odesílat značkové e‑maily
  přes SMTP.
og_image_alt: Developer guide showing Java code for adding email footers and SMTP
  headers with Aspose.Email
og_title: Jak přidat zápatí a přizpůsobit SMTP hlavičky v Javě
schemas:
- author: Aspose
  dateModified: '2026-10-07'
  description: Learn how to add email footer and customize SMTP headers in Java, create
    email message java, and personalize branding with Aspose.Email.
  headline: How to add footer and customize SMTP headers in Java
  type: TechArticle
- description: Learn how to add email footer and customize SMTP headers in Java, create
    email message java, and personalize branding with Aspose.Email.
  name: How to add footer and customize SMTP headers in Java
  steps:
  - name: setting up your Java project
    text: Start a new Java project in your favorite IDE (IntelliJ IDEA, Eclipse, or
      NetBeans). Add the Aspose.Email JAR to your project’s classpath or import it
      via Maven/Gradle.
  - name: importing the required classes
    text: 'You’ll need a handful of classes from the Aspose.Email namespace. The import
      statement stays the same, so you can copy it directly:'
  - name: creating an email message
    text: '`MailMessage` is Aspose.Email’s top‑level object that represents a single
      email in memory. After instantiation, you can set the sender, recipients, subject,
      and body.'
  - name: sending the email
    text: Finally, configure the `SmtpClient` with your server details and send the
      message. `SmtpClient` is the class that handles the SMTP protocol communication
      for Aspose.Email. > **Warning:** Make sure the SMTP credentials have permission
      to send from the `From` address you specified; otherwise the serve
  type: HowTo
- questions:
  - answer: 'You can download Aspose.Email for Java from the website using this link:
      [Download Aspose.Email for Java](https://releases.aspose.com/email/java/).'
    question: How do I download Aspose.Email for Java?
  - answer: Yes, you can customize multiple headers and footers in a single email
      message. Simply add the desired headers and footers as shown in the examples
      provided.
    question: Can I customize multiple headers and footers in a single email?
  - answer: There is no strict limit to the length of customized headers and footers.
      However, it’s recommended to keep them concise and relevant to maintain a professional
      appearance.
    question: Is there a limit to the length of customized headers and footers?
  - answer: Yes, you can use HTML formatting in the email content, including headers
      and footers. This allows you to create visually appealing and informative emails.
    question: Can I use HTML formatting in the email content?
  - answer: Use the SMTP settings provided by your email service provider or your
      organization’s IT department. These typically include the SMTP server address,
      port number, and authentication credentials.
    question: What SMTP settings should I use to send customized emails?
  type: FAQPage
second_title: Aspose.Email Java Email Management API
tags:
- email footer
- Aspose.Email
- Java email API
- SMTP customization
- email branding
title: Jak přidat zápatí a přizpůsobit SMTP hlavičky v Javě
url: /cs/java/configuring-smtp-servers/customizing-smtp-headers-and-footers/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak přidat patičku a přizpůsobit SMTP hlavičky v Javě

## Úvod

Pokud hledáte **jak přidat patičku** a zároveň upravit SMTP hlavičky, jste na správném místě. V tomto tutoriálu vás provedeme vytvořením e‑mailové zprávy v Javě, přidáním vlastní SMTP hlavičky a připojením profesionální HTML patičky – vše pomocí výkonné knihovny Aspose.Email pro Java. Na konci budete mít plně značkový e‑mail připravený k odeslání přes váš vlastní SMTP server.

## Rychlé odpovědi
- **Jaká je hlavní knihovna?** Aspose.Email for Java  
- **Která metoda přidává vlastní e‑mailovou patičku?** `setHtmlBody()` s vaším HTML úryvkem  
- **Mohu nastavit vlastní SMTP hlavičky?** Ano, pomocí `message.getHeaders().add()`  
- **Potřebuji licenci pro produkci?** Platná licence Aspose.Email je vyžadována pro komerční použití  
- **Jaká verze Javy je podporována?** Java 8 a novější  

## Co znamená „jak přidat e‑mailovou patičku“ v praxi?

Přidání e‑mailové patičky znamená připojení znovupoužitelného HTML bloku (často obsahujícího právní text, branding nebo odkazy na odhlášení) na konec těla zprávy. To zajišťuje, že každý odchozí e‑mail nese konzistentní informace bez ručního kopírování. Dobře navržená patička může také posílit identitu značky a splnit regulační požadavky v různých jurisdikcích.

## Proč přizpůsobit SMTP hlavičky?

Vlastní SMTP hlavičky vám poskytují jemnější kontrolu nad tím, jak downstream mail servery zpracovávají vaše zprávy – například příznaky priority, vlastní sledovací ID nebo určení názvu maileru. Umožňují ovlivnit rozhodnutí o směrování, spustit automatické zpracování a vložit metadata pro analytiku nebo reportování souladu, což může zlepšit doručitelnost a sledovatelnost.

## Požadavky

Před tím, než se ponoříte do procesu přizpůsobení, ujistěte se, že máte následující požadavky připravené:

- Aspose.Email for Java: Stáhněte a nainstalujte knihovnu Aspose.Email for Java ze [stránky ke stažení Aspose.Email for Java](https://releases.aspose.com/email/java/).

## Jak vytvořit e‑mailovou zprávu v Javě pomocí Aspose.Email

Můžete vytvořit plně vybavený objekt `MailMessage` během několika řádků Java kódu. Tento objekt později bude obsahovat vaši vlastní hlavičku a patičku.

### Krok 1: nastavení Java projektu

Založte nový Java projekt ve vašem oblíbeném IDE (IntelliJ IDEA, Eclipse nebo NetBeans). Přidejte JAR Aspose.Email do classpath vašeho projektu nebo jej importujte pomocí Maven/Gradle.

### Krok 2: import požadovaných tříd

Budete potřebovat několik tříd z jmenného prostoru Aspose.Email. Importní příkaz zůstává stejný, takže jej můžete zkopírovat přímo:

```java
import com.aspose.email.*;
```

### Krok 3: vytvoření e‑mailové zprávy

`MailMessage` je nejvyšší objekt Aspose.Email, který představuje jeden e‑mail v paměti. Po vytvoření můžete nastavit odesílatele, příjemce, předmět a tělo zprávy.

```java
// Create a new message
MailMessage message = new MailMessage();

// Set sender and recipient
message.setFrom("sender@example.com");
message.setTo("recipient@example.com");

// Set subject
message.setSubject("Customized Email Header and Footer");
```

### Jak přidat vlastní SMTP hlavičku

Vlastní SMTP hlavičky vám poskytují další kontrolu nad tím, jak přijímající server zpracovává poštu. Například můžete nastavit prioritu nebo určit název maileru.

Metoda `getHeaders().add()` vám umožní vložit vlastní hlavičku do kolekce hlaviček e‑mailu.

```java
// Customize headers
message.getHeaders().add("X-Priority", "1");
message.getHeaders().add("X-Mailer", "Aspose.Email");
```

> **Tip:** Používejte standardní názvy hlaviček (např. `X-Priority`), aby byla zajištěna kompatibilita napříč různými mail servery.

### Jak přidat e‑mailovou patičku

Pro **přidání e‑mailové patičky** (nebo **přidání HTML patičky do e‑mailu**) jednoduše vložte váš HTML úryvek na konec těla zprávy. Tento přístup vám také umožní **personalizovat branding e‑mailu** pomocí log nebo právních upozornění.

Metoda `setHtmlBody()` nastaví HTML obsah zprávy, což vám umožní spojit HTML patičky s hlavním tělem.

```java
// Customize footer
String footerText = "This email is sent using Aspose.Email for Java.";
message.setHtmlBody("<p>Your email content here.</p><p>" + footerText + "</p>");
```

Můžete nahradit `footerText` libovolným HTML – obrázky, stylovaný text nebo dokonce dynamický obsah.

### Krok 6: odeslání e‑mailu

Nakonec nakonfigurujte `SmtpClient` s údaji o vašem serveru a odešlete zprávu. `SmtpClient` je třída, která zajišťuje komunikaci protokolu SMTP pro Aspose.Email.

```java
// Initialize the SMTP client
SmtpClient client = new SmtpClient("smtp.example.com", 587, "username", "password");

// Send the message
client.send(message);
```

> **Varování:** Ujistěte se, že SMTP přihlašovací údaje mají oprávnění odesílat z adresy `From` **...**; jinak server může zprávu odmítnout.

## Časté problémy a řešení

| Problém | Řešení |
|-------|----------|
| **Hlavičky se nezobrazují** | Ověřte, že SMTP server neodstraňuje vlastní hlavičky. Někteří poskytovatelé odstraňují nestandardní hlavičky. |
| **HTML patička se nezobrazuje** | Zajistěte, aby e‑mailový klient podporoval HTML a aby byl váš HTML kód dobře formátovaný (uzavřené značky, správné kódování). |
| **Chyby autentizace** | Zkontrolujte uživatelské jméno/heslo a že nastavení TLS/SSL odpovídá požadavkům vašeho serveru. |

## Často kladené otázky

**Q: Jak stáhnu Aspose.Email pro Java?**  
A: Aspose.Email pro Java můžete stáhnout z webu pomocí tohoto odkazu: [Download Aspose.Email for Java](https://releases.aspose.com/email/java/).

**Q: Mohu přizpůsobit více hlaviček a patiček v jednom e‑mailu?**  
A: Ano, můžete přizpůsobit více hlaviček a patiček v jedné e‑mailové zprávě. Stačí přidat požadované hlavičky a patičky, jak je ukázáno v poskytnutých příkladech.

**Q: Existuje limit na délku vlastních hlaviček a patiček?**  
A: Neexistuje přísný limit délky vlastních hlaviček a patiček. Přesto se doporučuje, aby byly stručné a relevantní, aby zachovaly profesionální vzhled.

**Q: Mohu použít HTML formátování v obsahu e‑mailu?**  
A: Ano, můžete použít HTML formátování v obsahu e‑mailu, včetně hlaviček a patiček. To vám umožní vytvářet vizuálně atraktivní a informativní e‑maily.

**Q: Jaká SMTP nastavení mám použít pro odesílání přizpůsobených e‑mailů?**  
A: Použijte SMTP nastavení poskytnutá vaším poskytovatelem e‑mailových služeb nebo IT oddělením vaší organizace. Obvykle zahrnují adresu SMTP serveru, číslo portu a přihlašovací údaje.

---

**Poslední aktualizace:** 2026-10-07  
**Testováno s:** Aspose.Email for Java 24.12  
**Autor:** Aspose

## Související tutoriály

- [Jak přidat hlavičky v Java e‑mailu pomocí Aspose.Email](/email/java/customizing-email-headers/)
- [Jak odesílat e‑maily pomocí Aspose.Email v Javě: Kompletní průvodce operacemi SMTP klienta](/email/java/smtp-client-operations/send-emails-aspose-email-java-tutorial/)
- [Vytvoření a konfigurace e‑mailové zprávy Aspose Email Java](/email/java/email-message-operations/create-configure-mail-message-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}