---
date: 2026-04-28
description: Scopri come incorporare un'immagine in un'email HTML usando Aspose.Email
  per Java e inviare l'email con l'immagine incorporata tramite SMTP.
keywords:
- embed image in html email
- send email with embedded image
- how to embed image java
- create html email java
- send email via smtp java
linktitle: Lavorare con gli allegati inline in Aspose.Email
second_title: Aspose.Email Java Email Management API
title: Come incorporare un'immagine in un'email HTML con Aspose.Email per Java
url: /it/java/advanced-email-attachments/working-with-inline-attachments/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Come incorporare un'immagine in un'email HTML con Aspose.Email per Java

Incorporare un'immagine direttamente all'interno di un'email rende i tuoi messaggi più curati e garantisce che il destinatario veda le grafiche senza dover scaricare file separati. In questo tutorial imparerai **come incorporare un'immagine in un'email HTML** usando Aspose.Email per Java, coprendo tutto, dall'installazione della libreria alla creazione di un'email HTML, aggiunta di risorse inline e infine l'invio del messaggio tramite SMTP.

## Risposte rapide
- **Qual è la classe principale per le immagini inline?** `LinkedResource`
- **Quale metodo fa riferimento all'immagine in HTML?** Usa `cid:yourContentId` nel tag `<img>`
- **È necessaria una licenza per lo sviluppo?** Una prova gratuita funziona per i test; è necessaria una licenza per la produzione
- **Posso inviare l'email tramite qualsiasi server SMTP?** Sì, basta configurare `SmtpClient` con i dettagli del tuo server
- **Questo approccio è compatibile con tutti i principali client email?** La maggior parte dei client moderni (Outlook, Gmail, Thunderbird) supporta le immagini incorporate con CID

## Come incorporare un'immagine in un'email HTML usando Aspose.Email per Java

Quando **incorpi un'immagine in un'email HTML**, l'immagine diventa parte del corpo MIME, quindi viene visualizzata immediatamente nel client del destinatario. Di seguito percorriamo l'intero processo, da un semplice messaggio HTML a un'email completa con un'immagine inline.

### Cosa sono gli allegati inline (immagini incorporate)?

Gli allegati inline — a volte chiamati immagini incorporate o CID — sono file che vivono all'interno del corpo MIME di un'email. Vengono referenziati dalla parte HTML del messaggio con un **Content‑ID** (CID). Questa tecnica ti consente di **incorporare immagini nelle email** in modo che appaiano esattamente dove inserisci il tag `<img>`, senza comparire come allegati scaricabili separati.

### Perché usare immagini incorporate nelle tue email Java?

- **Aspetto professionale:** Loghi, banner e foto di prodotto vengono visualizzati istantaneamente.
- **Migliore coinvolgimento:** I destinatari sono più propensi a leggere un'email che appare completa.
- **Nessun click aggiuntivo:** Gli utenti non devono scaricare un allegato per vedere l'immagine.
- **Branding coerente:** Le risorse del tuo brand rimangono in linea con il contenuto del messaggio.

### Prerequisiti

- Libreria Aspose.Email per Java (scarica dalla [documentazione ufficiale di Aspose.Email per Java](https://reference.aspose.com/email/java/))
- Ambiente di sviluppo Java 8+
- Accesso a un server SMTP per l'invio di email
- File immagine da incorporare (ad es., `logo.png`)

## Guida passo‑passo

### Passo 1: Crea un messaggio email HTML di base

Per prima cosa, configura un semplice `MailMessage` con un corpo HTML. Questo sarà la tela su cui inseriremo l'immagine in seguito.

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

### Passo 2: Aggiungi un'immagine inline usando `LinkedResource`

Ora incorporiamo un'immagine. La classe `LinkedResource` rappresenta l'allegato inline. Assegna un **Content‑ID** unico e riferiscilo nel corpo HTML con `cid:`.

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

### Passo 3: Invia l'email tramite `SmtpClient`

Configura le impostazioni SMTP e invia il messaggio. L'immagine incorporata viaggia insieme all'email, così il destinatario la vede immediatamente.

```java
import com.aspose.email.SmtpClient;

// Create an instance of SmtpClient
SmtpClient client = new SmtpClient("smtp.example.com", 587, "username", "password");

// Send the email
client.send(message);
```

### Passo 4: Ricevi ed estrai le immagini inline (opzionale)

Se devi elaborare messaggi in arrivo che contengono immagini incorporate, puoi caricare il file `.eml` e accedere ai suoi `LinkedResources`.

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
|----------|----------------|-----------|
| **Mancata corrispondenza del Content‑ID** | Il riferimento `cid:` in HTML non corrisponde al `ContentId` impostato su `LinkedResource`. | Assicurati che le stringhe siano identiche (`image001` vs `cid:image001`). |
| **File non trovato** | Il percorso dell'immagine è errato o il file manca. | Verifica il percorso assoluto/relativo e che il file esista sul server. |
| **Errore di autenticazione SMTP** | Credenziali o impostazioni del server errate. | Ricontrolla host, porta, nome utente e password. Abilita TLS/SSL se necessario. |
| **Immagine non visualizzata in alcuni client** | Alcuni client bloccano risorse esterne. | Usa immagini incorporate con CID (come mostrato) invece di URL esterni. |

## Domande frequenti

**D: Come scarico Aspose.Email per Java?**  
R: Puoi scaricare Aspose.Email per Java dalla [documentazione](https://reference.aspose.com/email/java/). Segui le istruzioni di installazione per configurarlo nel tuo progetto.

**D: Posso usare Aspose.Email per Java con altre librerie Java?**  
R: Sì, Aspose.Email si integra senza problemi con altre librerie Java, consentendoti di combinare l'elaborazione delle email con la generazione di PDF, OCR o l'accesso a database.

**D: Quali formati di file sono supportati per gli allegati inline?**  
R: Sono supportati formati immagine comuni come PNG, JPEG, GIF, così come altri tipi di documento (ad es., SVG) come risorse inline.

**D: Come gestisco gli allegati inline nelle email HTML?**  
R: Usa la classe `LinkedResource` per assegnare un `ContentId`, aggiungilo a `message.getLinkedResources()` e riferiscilo nel corpo HTML con `<img src='cid:yourContentId'>`.

**D: Aspose.Email per Java è compatibile con diversi server email?**  
R: Sì, funziona con qualsiasi server SMTP/IMAP/POP3. Basta fornire l'indirizzo corretto del server, la porta e i dettagli di autenticazione.

## Conclusione

Ora hai una ricetta completa e pronta per la produzione per **incorporare un'immagine in un'email HTML** con Aspose.Email per Java. Creando un `LinkedResource`, assegnando un Content‑ID unico e riferendolo con `cid:` nel corpo HTML, garantisci che loghi, banner o foto di prodotto appaiano esattamente dove desideri — senza download aggiuntivi o link rotti. Combina questo con la robusta classe `SmtpClient` per inviare il messaggio tramite qualsiasi server SMTP, e sarai pronto a inviare email curate e coerenti con il brand dalle tue applicazioni Java.

---

**Ultimo aggiornamento:** 2026-04-28  
**Testato con:** Aspose.Email for Java 24.12 (latest at time of writing)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}