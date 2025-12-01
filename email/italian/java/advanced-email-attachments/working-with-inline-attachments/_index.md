---
date: 2025-12-01
description: Scopri come inviare email con immagine incorporata usando Aspose.Email
  per Java. Questa guida mostra come incorporare immagini nelle email e creare email
  HTML in Java con allegati inline.
language: it
linktitle: Working with Inline Attachments in Aspose.Email
second_title: Aspose.Email Java Email Management API
title: Come inviare un'email con immagine incorporata usando Aspose.Email per Java
url: /java/advanced-email-attachments/working-with-inline-attachments/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Come inviare email con immagine incorporata usando Aspose.Email per Java

Incorporare le immagini direttamente all'interno di un'email rende i messaggi più curati e garantisce che il destinatario veda la grafica senza dover scaricare file separati. In questo tutorial imparerai **come inviare email con immagine incorporata** usando Aspose.Email per Java, coprendo tutto, dall'installazione della libreria alla creazione di un'email HTML, aggiunta di risorse inline e invio del messaggio.

## Risposte rapide
- **Qual è la classe principale per le immagini inline?** `LinkedResource`
- **Quale metodo fa riferimento all'immagine in HTML?** Usa `cid:yourContentId` nel tag `<img>`
- **È necessaria una licenza per lo sviluppo?** Una versione di prova gratuita è sufficiente per i test; è richiesta una licenza per la produzione
- **Posso inviare l'email tramite qualsiasi server SMTP?** Sì, basta configurare `SmtpClient` con i dettagli del tuo server
- **Questo approccio è compatibile con tutti i principali client di posta?** La maggior parte dei client moderni (Outlook, Gmail, Thunderbird) supporta le immagini incorporate con CID

## Cosa sono gli allegati inline (immagini incorporate)?

Gli allegati inline—talvolta chiamati immagini incorporate o immagini CID—sono file che vivono all'interno del corpo MIME di un'email. Vengono referenziati dalla parte HTML del messaggio con un **Content‑ID** (CID). Questa tecnica ti consente di **incorporare immagini nelle email** così da apparire esattamente dove posizioni il tag `<img>`, senza apparire come allegati scaricabili separati.

## Perché usare immagini incorporate nelle tue email Java?

- **Aspetto professionale:** Loghi, banner e foto di prodotto vengono visualizzati istantaneamente.
- **Migliore coinvolgimento:** I destinatari sono più propensi a leggere un'email che appare completa.
- **Nessun click aggiuntivo:** Gli utenti non devono scaricare un allegato per vedere l'immagine.
- **Branding coerente:** I tuoi asset di marca rimangono in linea con il contenuto del messaggio.

## Prerequisiti

- Libreria Aspose.Email per Java (scaricabile dalla documentazione ufficiale [Aspose.Email for Java documentation](https://reference.aspose.com/email/java/))
- Ambiente di sviluppo Java 8+
- Accesso a un server SMTP per l'invio della posta
- File immagine da incorporare (ad esempio `logo.png`)

## Guida passo‑passo

### Passo 1: Creare un messaggio email HTML di base

Per prima cosa, imposta un semplice `MailMessage` con un corpo HTML. Questo sarà il canvas dove incorporeremo l'immagine in seguito.

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

### Passo 2: Aggiungere un'immagine inline usando `LinkedResource`

Ora incorporiamo un'immagine. La classe `LinkedResource` rappresenta l'allegato inline. Assegna un **Content‑ID** univoco e riferiscilo nel corpo HTML con `cid:`.

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

> **Suggerimento professionale:** Mantieni il `ContentId` semplice e unico all'interno del messaggio per evitare conflitti.

### Passo 3: Inviare l'email tramite `SmtpClient`

Configura le impostazioni SMTP e invia il messaggio. L'immagine incorporata viaggia insieme all'email, così il destinatario la vede immediatamente.

```java
import com.aspose.email.SmtpClient;

// Create an instance of SmtpClient
SmtpClient client = new SmtpClient("smtp.example.com", 587, "username", "password");

// Send the email
client.send(message);
```

### Passo 4: Ricevere ed estrarre le immagini inline (opzionale)

Se devi elaborare messaggi in arrivo che contengono immagini incorporate, puoi caricare il file `.eml` e accedere alle sue `LinkedResources`.

```java
import com.aspose.email.MailMessage;
import com.aspose.email.LinkedResourceCollection;

// Load the received email message
MailMessage receivedMessage = MailMessage.load("path/to/received_email.eml");

// Access the inline attachments
LinkedResourceCollection inlineAttachments = receivedMessage.getLinkedResources();
```

## Problemi comuni e come risolverli

| Problema | Perché accade | Soluzione |
|----------|---------------|-----------|
| **Mancata corrispondenza del Content‑ID** | Il riferimento `cid:` in HTML non corrisponde al `ContentId` impostato su `LinkedResource`. | Assicurati che le stringhe siano identiche (`image001` vs `cid:image001`). |
| **File non trovato** | Il percorso dell'immagine è errato o il file è assente. | Verifica il percorso assoluto/relativo e che il file esista sul server. |
| **Autenticazione SMTP fallita** | Credenziali o impostazioni del server errate. | Ricontrolla host, porta, nome utente e password. Abilita TLS/SSL se necessario. |
| **Immagine non visualizzata in alcuni client** | Alcuni client bloccano risorse esterne. | Usa immagini incorporate con CID (come mostrato) anziché URL esterni. |

## Domande frequenti

**D: Come scarico Aspose.Email per Java?**  
R: Puoi scaricare Aspose.Email per Java dalla [documentazione](https://reference.aspose.com/email/java/). Segui le istruzioni di installazione per configurarlo nel tuo progetto.

**D: Posso usare Aspose.Email per Java con altre librerie Java?**  
R: Sì, Aspose.Email si integra senza problemi con altre librerie Java, consentendoti di combinare l'elaborazione delle email con la generazione di PDF, OCR o l'accesso a database.

**D: Quali formati di file sono supportati per gli allegati inline?**  
R: Formati immagine comuni come PNG, JPEG, GIF, così come altri tipi di documento (ad esempio SVG) sono supportati come risorse inline.

**D: Come gestisco gli allegati inline nelle email HTML?**  
R: Usa la classe `LinkedResource` per assegnare un `ContentId`, aggiungila a `message.getLinkedResources()` e riferiscilo nel corpo HTML con `<img src='cid:yourContentId'>`.

**D: Aspose.Email per Java è compatibile con diversi server di posta?**  
R: Sì, funziona con qualsiasi server SMTP/IMAP/POP3. Basta fornire l'indirizzo corretto del server, la porta e i dettagli di autenticazione.

---

**Ultimo aggiornamento:** 2025-12-01  
**Testato con:** Aspose.Email per Java 24.12 (ultima versione al momento della scrittura)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}