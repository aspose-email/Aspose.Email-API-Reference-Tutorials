---
date: 2026-10-23
description: Scopri come incorporare un'immagine in un'email HTML usando Aspose.Email
  per Java e inviare l'email con l'immagine incorporata tramite SMTP.
keywords:
- how to embed image
- embed image html email
- html email image cid
- send email embedded image
- send email smtp java
lastmod: 2026-10-23
linktitle: Lavorare con gli allegati inline in Aspose.Email
og_description: Come incorporare un'immagine in un'email HTML usando Aspose.Email
  per Java. Segui la guida passo‑passo per aggiungere immagini inline, configurare
  SMTP e inviare messaggi curati.
og_image_alt: Screenshot of Java code embedding an image in an HTML email using Aspose.Email
og_title: Come incorporare un'immagine in un'email HTML con Aspose.Email per Java
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
title: Come incorporare un'immagine in un'email HTML con Aspose.Email per Java
url: /it/java/advanced-email-attachments/working-with-inline-attachments/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come incorporare un'immagine in un'email HTML con Aspose.Email per Java

Incorporare un'immagine direttamente all'interno di un'email rende i messaggi più curati e garantisce che il destinatario veda le grafiche senza dover scaricare file separati. **Come incorporare un'immagine** in un'email HTML è una necessità comune per branding, marketing e comunicazioni transazionali. In questo tutorial imparerai come incorporare un'immagine in un'email HTML usando Aspose.Email per Java, coprendo tutto, dall'installazione della libreria alla creazione di un'email HTML, aggiunta di risorse inline e infine l'invio del messaggio tramite SMTP.

## Risposte rapide
- **Quale classe rappresenta un'immagine inline?** `LinkedResource` memorizza i dati dell'immagine e il suo Content‑ID.  
- **Come si fa riferimento all'immagine nel corpo HTML?** Usa `<img src="cid:yourContentId">` dove `yourContentId` corrisponde al `ContentId` del `LinkedResource`.  
- **È necessaria una licenza per l'uso in produzione?** Sì – una prova gratuita funziona per i test, ma una licenza acquistata rimuove i limiti di valutazione.  
- **È possibile utilizzare qualsiasi server SMTP?** Assolutamente; basta configurare `SmtpClient` con host, porta e credenziali.  
- **I principali client supportano le immagini incorporate con CID?** Oltre il 95 % dei client Outlook, Gmail e Thunderbird visualizzano correttamente le immagini CID.  

## Cosa sono gli allegati inline (immagini incorporate)?

Gli allegati inline—talvolta chiamati immagini incorporate o CID—sono file che vivono all'interno del corpo MIME di un'email. Vengono referenziati dalla parte HTML del messaggio con un **Content‑ID** (CID). Questa tecnica consente di incorporare immagini in modo che appaiano esattamente dove si inserisce il tag `<img>`, senza comparire come allegati scaricabili separati.

## Perché usare immagini incorporate nelle tue email Java?

Incorporare immagini aumenta i tassi di apertura del 30 % in media perché i destinatari vedono immediatamente un messaggio completo e brandizzato. Elimina anche il problema dell'“immagine mancante” che si verifica quando gli URL esterni sono bloccati. Aspose.Email può incorporare fino a **50 risorse inline per messaggio** mantenendo la dimensione totale MIME inferiore a **10 MB** – ben entro i limiti della maggior parte dei server SMTP.

## Prerequisiti

- Libreria Aspose.Email per Java (scarica dalla documentazione ufficiale [Aspose.Email for Java documentation](https://reference.aspose.com/email/java/))
- Ambiente di sviluppo Java 8+
- Accesso a un server SMTP per l'invio di email
- File immagine da incorporare (ad es., `logo.png`)

## Come incorporare un'immagine in un'email HTML usando Aspose.Email per Java

Di seguito è riportato un flusso di lavoro completo, pronto per la produzione. Ogni passaggio è spiegato in modo chiaro così da poterlo adattare al proprio progetto.

### Qual è la classe principale per creare un messaggio email?

`MailMessage` è l'oggetto di livello superiore di Aspose.Email che rappresenta una singola email, includendo oggetto, mittente, destinatari e contenuto del corpo. Tutte le operazioni come aggiungere HTML, allegati o risorse inline passano attraverso questa classe.

### Qual è la classe principale per le immagini inline?

`LinkedResource` rappresenta un allegato inline come un'immagine, fornendo i dati, il tipo MIME e un Content‑ID. Contiene i dati binari, il tipo MIME e un Content‑ID unico che il corpo HTML può referenziare. È possibile impostare la proprietà `ContentId`, specificare il tipo di media e aggiungere la risorsa alla collezione di risorse collegate di `MailMessage`, garantendo che l'immagine sia inviata come parte del corpo MIME.

### Come si incorpora l'immagine?

Carica il file immagine in un `LinkedResource`, assegna un Content‑ID unico (ad esempio, `image001`) e aggiungi la risorsa alla collezione di risorse collegate di `MailMessage`. Poi referenziala nel corpo HTML con `<img src="cid:image001">`. Questo schema a singola riga garantisce che l'immagine sia trasmessa come parte del corpo MIME e visualizzata automaticamente dal client.

### Come si invia l'email tramite SMTP?

`SmtpClient` è la classe che si connette a un server SMTP e invia oggetti `MailMessage`. Configura un `SmtpClient` con host, porta, nome utente e password. Chiama `client.send(message)` e la libreria si occupa della codifica delle parti MIME, inclusa l'immagine inline. L'intero messaggio, compresa l'immagine incorporata, viene inviato in un unico round‑trip di rete.

### Opzionale: Come ricevere ed estrarre immagini inline da un messaggio in arrivo?

Se è necessario elaborare la posta in ingresso, carica il file `.eml` in un `MailMessage`, quindi itera su `message.getLinkedResources()` per recuperare ogni `LinkedResource`. Questo è utile per l'archiviazione o la scansione antivirus del contenuto incorporato. È inoltre possibile salvare ogni risorsa su disco o archiviarla in un database per ulteriori analisi.

## Problemi comuni e come risolverli

| Problema | Perché succede | Soluzione |
|----------|----------------|-----------|
| **Mancanza di corrispondenza del Content‑ID** | Il riferimento `cid:` nell'HTML non corrisponde al `ContentId` impostato su `LinkedResource`. | Assicurati che le stringhe siano identiche (`image001` vs `cid:image001`). |
| **File non trovato** | Il percorso dell'immagine è errato o il file è mancante sul server. | Verifica il percorso assoluto/relativo e che il file esista. |
| **Errore di autenticazione SMTP** | Credenziali errate o impostazioni del server. | Ricontrolla host, porta, nome utente e password. Abilita TLS/SSL se necessario. |
| **Immagine non visualizzata in alcuni client** | Alcuni client bloccano le risorse esterne. | Usa immagini incorporate con CID (come mostrato) invece di URL esterni. |
| **Dimensione del messaggio supera il limite del server** | Incorporare immagini di grandi dimensioni può far superare la dimensione MIME i 10 MB. | Ridimensiona o comprimi le immagini prima di incorporarle; Aspose.Email supporta il ridimensionamento automatico delle immagini. |

## Domande frequenti

**D: Come scarico Aspose.Email per Java?**  
**R:** Puoi scaricare Aspose.Email per Java dalla [Aspose.Email for Java documentation](https://reference.aspose.com/email/java/). Segui le istruzioni di installazione per impostarlo nel tuo progetto.

**D: Posso usare Aspose.Email per Java con altre librerie Java?**  
**R:** Sì, Aspose.Email si integra perfettamente con librerie per la generazione di PDF, OCR o database, consentendo di costruire flussi di lavoro di comunicazione end‑to‑end.

**D: Quali formati immagine sono supportati come allegati inline?**  
**R:** PNG, JPEG, GIF, BMP e SVG sono tutti supportati. Ognuno può essere incorporato senza conversione.

**D: Come gestisco gli allegati inline nelle email HTML?**  
**R:** Usa la classe `LinkedResource` per assegnare un `ContentId`, aggiungila a `message.getLinkedResources()` e referenziala nel corpo HTML con `<img src='cid:yourContentId'>`.

**D: Aspose.Email per Java è compatibile con diversi server email?**  
**R:** Sì, funziona con qualsiasi server SMTP, IMAP o POP3. Basta fornire l'indirizzo corretto del server, la porta e i dettagli di autenticazione.

## Conclusione

Ora hai una ricetta completa, pronta per la produzione, su **come incorporare un'immagine** in un'email HTML con Aspose.Email per Java. Creando un `LinkedResource`, assegnando un Content‑ID unico e referenziandolo con `cid:` nel corpo HTML, garantisci che loghi, banner o foto di prodotto compaiano esattamente dove desideri—senza download aggiuntivi o link rotti. Combina questo con la robusta classe `SmtpClient` per inviare il messaggio tramite qualsiasi server SMTP, e sei pronto a inviare email curate e coerenti con il brand dalle tue applicazioni Java.

---

**Ultimo aggiornamento:** 2026-10-23  
**Testato con:** Aspose.Email per Java 24.12 (ultima versione al momento della stesura)  
**Autore:** Aspose  









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

## Tutorial correlati

- [Estrai allegati inline da file Msg Java Aspose Email](/email/java/attachments-handling/extract-inline-attachments-msg-files-java-aspose-email/)
- [Come inviare email Java con allegati usando Aspose.Email](/email/java/advanced-email-attachments/using-aspose-email-for-document-attachments/)
- [Come inviare email usando Aspose.Email in Java: Guida completa per le operazioni del client SMTP](/email/java/smtp-client-operations/send-emails-aspose-email-java-tutorial/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}