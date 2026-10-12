---
date: 2026-10-12
description: Scopri come incorporare immagini nelle email HTML usando Aspose.Email
  per Java, inviare email HTML con immagini incorporate e ridurre le dimensioni degli
  allegati email.
keywords:
- reduce email attachment size
- create email with image
- optimize image for email
- send html email java
- embed cid image email
lastmod: 2026-10-12
linktitle: Come allegare un'immagine a un'email con Aspose.Email
og_description: Riduci le dimensioni degli allegati email e incorpora immagini nelle
  email HTML usando Aspose.Email per Java. Segui questa guida passo‑passo per inviare
  email HTML ricche in modo efficiente.
og_image_alt: 'Developer guide: embed images in HTML email while reducing attachment
  size with Aspose.Email for Java'
og_title: Ridurre le dimensioni degli allegati email con Aspose.Email per Java
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: Learn how to embed images in HTML email using Aspose.Email for Java,
    send HTML email with embedded images, and reduce email attachment size.
  headline: Reduce email attachment size with Aspose.Email for Java
  type: TechArticle
- questions:
  - answer: Repeat the attachment and `LinkedResource` steps for each image, assigning
      a unique Content‑ID (e.g., `image2`, `image3`) and referencing them in the HTML.
    question: How can I embed multiple images in a single email?
  - answer: Plain‑text format does not support embedded images. You can only include
      URLs that recipients can click to view the image online.
    question: Can I embed images in plain‑text emails?
  - answer: JPEG, PNG, and GIF are widely supported. Use JPEG for photographs and
      PNG for graphics with transparency.
    question: What image formats are safe for email embedding?
  - answer: Yes—add `width`/`height` attributes to the `<img>` tag, e.g., `<img src='cid:image1'
      width='400' height='300'>`.
    question: Is there a way to control image dimensions in the email?
  - answer: While there’s no strict SMTP limit, most mail providers recommend keeping
      total email size under 5 MB. Optimizing image size helps stay well within this
      limit.
    question: Are there size limits for embedded images?
  type: FAQPage
second_title: Aspose.Email Java Email Management API
tags:
- email attachment size
- Aspose.Email
- Java email API
- embed images email
- HTML email
title: Ridurre le dimensioni degli allegati email con Aspose.Email per Java
url: /it/java/advanced-email-attachments/embedding-images-as-attachments/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Riduci le dimensioni degli allegati email con Aspose.Email per Java

Incorporare le immagini direttamente in un'email HTML non solo rende il messaggio più curato, ma **riduce le dimensioni degli allegati email** perché l'immagine fa parte del corpo MIME anziché di un file separato. In questo tutorial imparerai a creare un'email con immagine, incorporare l'immagine usando un riferimento CID e applicare consigli di best‑practice per **ottimizzare l'immagine per l'email** così che il messaggio finale rimanga leggero. Vedrai anche come inviare email HTML in stile Java con Aspose.Email e mantenere il carico totale ben al di sotto dei limiti tipici delle caselle di posta.

## Risposte rapide
- **Quale classe crea il messaggio email?** `MailMessage` – il contenitore principale per oggetto, destinatari e corpo.  
- **Quale oggetto consente di incorporare un'immagine nel corpo HTML?** `LinkedResource` – avvolge lo stream dell'immagine e assegna un Content‑ID.  
- **È necessaria una licenza per l'uso in produzione?** Sì – è necessaria una licenza commerciale di Aspose.Email per rimuovere i limiti di valutazione.  
- **Come posso ridurre le dimensioni dell'allegato?** Ottimizza l'immagine (ridimensiona a ≤600 px, comprimi sotto 100 KB) prima di aggiungerla.  
- **Posso incorporare più immagini?** Assolutamente – aggiungi un Content‑ID unico per ogni immagine e riferisciti a loro con gli URI `cid:`.

## Cos'è l'email HTML con immagine incorporata?
Incorporare un'immagine significa inserire la foto nella struttura MIME dell'email in modo che il destinatario la veda in linea. L'immagine è referenziata da un **Content‑ID (CID)**, che il tag HTML `<img>` carica direttamente dal corpo del messaggio, eliminando gli allegati separati e mantenendo le dimensioni complessive più piccole.

## Perché inviare email HTML con immagine incorporata?
Incorporare immagini all'interno dell'HTML ti consente di progettare newsletter più ricche, annunci di prodotto o ticket di supporto. I destinatari vedono il contenuto visivo immediatamente, senza dover scaricare un allegato, il che migliora i tassi di apertura e l'engagement complessivo. La maggior parte dei client email supporta le immagini CID, e l'incorporamento evita passaggi di download aggiuntivi, portando a un rendering più veloce e a un minore utilizzo della larghezza di banda.

## Prerequisiti
- **Aspose.Email for Java** – scarica dal sito ufficiale: [Aspose.Email Java download](https://releases.aspose.com/email/java/).  
- Accesso a un server SMTP (Gmail, Outlook o il tuo relay).  
- Un file immagine (JPEG, PNG o GIF) che desideri incorporare.

> **Consiglio professionale:** *Ottimizza le dimensioni dell'immagine per l'email* ridimensionandola a una larghezza ≤600 px e comprimendola a ≤100 KB. Questo riduce i tempi di caricamento ed evita di superare i limiti di dimensione della casella di posta.

## Creazione di un messaggio email
`MailMessage` è l'oggetto di livello superiore di Aspose.Email che rappresenta una singola email. Contiene l'oggetto, il mittente, i destinatari e il corpo (testo semplice o HTML).  

La classe `MailMessage` è il modello centrale per costruire e inviare messaggi email in Aspose.Email per Java.

```java
// Import necessary libraries
import com.aspose.email.*;

// Create a new email message
MailMessage message = new MailMessage();
```

## Aggiungere l'immagine come allegato
`LinkedResource` rappresenta una parte MIME che può essere incorporata in linea in un'email.  
Prima dell'incorporamento, aggiungi il file immagine alla collezione di allegati del messaggio. L'allegato diventa uno stream che `LinkedResource` può poi referenziare.

```java
// Specify the path to the image file
String imagePath = "path/to/your/image.jpg";

// Attach the image to the email
Attachment attachment = new Attachment(imagePath);
message.getAttachments().add(attachment);
```

## Incorporare l'immagine allegata in HTML
`LinkedResource` è usato per collegare uno stream di immagine a un Content‑ID per la visualizzazione in linea.  
Per visualizzare l'immagine all'interno del corpo HTML, crea un `LinkedResource` che punti all'immagine allegata e imposta il suo Content‑ID (ad esempio, `image1`). Poi riferisci quell'ID nell'HTML usando lo schema URI `cid:`.

```java
// Create a LinkedResource for the attached image
LinkedResource linkedImage = new LinkedResource(attachment.getContentStream(), "image/jpeg");
linkedImage.setContentId("image1");

// Create an HTML body with the embedded image
String htmlBody = "<html><body><h1>Check out this image:</h1><img src='cid:image1'></body></html>";
message.setHtmlBody(htmlBody);
message.getLinkedResources().addItem(linkedImage);
```

> **Perché usare `LinkedResource`?** Segnala al client che l'immagine fa parte del corpo del messaggio, il che è essenziale per gli scenari **send html email java** che richiedono grafiche in linea.

## Invio dell'email
`SmtpClient` è la classe che gestisce la comunicazione SMTP per l'invio dei messaggi.  
`SmtpClient` gestisce la trasmissione effettiva. Configuralo con l'host del tuo server, la porta e le credenziali, quindi chiama `send` per inviare il `MailMessage`.  

`SmtpClient` è la classe di trasporto SMTP di Aspose.Email che invia in modo sicuro il `MailMessage` composto al server di posta di destinazione.

```java
// Initialize the SmtpClient
SmtpClient client = new SmtpClient("smtp.example.com", 587, "your_username", "your_password");

// Send the email
client.send(message);
```

Quando il destinatario apre l'email, il corpo HTML visualizza l'immagine in linea, offrendo un'esperienza visiva fluida mantenendo il carico complessivo ridotto.

## Come incorporare più immagini in un'email
`LinkedResource` rappresenta una parte MIME che può essere incorporata in linea in un'email.  
Aggiungi ogni immagine come allegato separato, crea un `LinkedResource` distinto per ciascuna e assegna un Content‑ID unico come `image2`, `image3`, ecc. Riferiscili nell'HTML con `src='cid:image2'`. Questo schema scala a newsletter con decine di grafiche senza gonfiare le dimensioni del messaggio.

## Suggerimenti per ridurre le dimensioni degli allegati email
- **Ridimensiona** l'immagine alle dimensioni esatte necessarie (tipicamente ≤600 px di larghezza).  
- **Comprimi** usando strumenti come ImageMagick o compressori online per mantenere il file sotto 100 KB.  
- **Scegli il formato giusto**: JPEG per foto, PNG per grafiche con trasparenza.  
- **Rimuovi i metadati EXIF** se non sono necessari.  
- **Usa JPEG progressivo** per un rendering progressivo più veloce nei client supportati.

## Problemi comuni e risoluzione
| Problema | Causa | Soluzione |
|----------|-------|-----------|
| Immagine non visualizzata | Content‑ID errato o `LinkedResource` mancante | Verifica che `linkedImage.setContentId("image1")` corrisponda al `src='cid:image1'` nell'HTML. |
| Dimensione email elevata | Immagine non ottimizzata (alta risoluzione) | Ridimensiona/comprimi l'immagine prima di allegarla; puntare a ≤100 KB. |
| Email segnalata come spam | Intestazioni MIME mancanti o non corrette | Assicurati che `SmtpClient` utilizzi TLS/STARTTLS e imposta un indirizzo `From` chiaro. |
| L'immagine in linea appare come allegato | Il client non supporta CID | Fornisci un URL di fallback nel tag `<img>` (`src='cid:image1' alt='Image'`). |

## Domande frequenti

**D: Come posso incorporare più immagini in una singola email?**  
R: Ripeti i passaggi di allegato e `LinkedResource` per ogni immagine, assegnando un Content‑ID unico (ad es., `image2`, `image3`) e riferendoli nell'HTML.

**D: Posso incorporare immagini in email di solo testo?**  
R: Il formato di solo testo non supporta immagini incorporate. Puoi includere solo URL che i destinatari possono cliccare per visualizzare l'immagine online.

**D: Quali formati immagine sono sicuri per l'incorporamento nelle email?**  
R: JPEG, PNG e GIF sono ampiamente supportati. Usa JPEG per fotografie e PNG per grafiche con trasparenza.

**D: È possibile controllare le dimensioni dell'immagine nell'email?**  
R: Sì—aggiungi gli attributi `width`/`height` al tag `<img>`, ad esempio `<img src='cid:image1' width='400' height='300'>`.

**D: Esistono limiti di dimensione per le immagini incorporate?**  
R: Sebbene non esista un limite SMTP rigido, la maggior parte dei provider di posta consiglia di mantenere la dimensione totale dell'email sotto 5 MB. Ottimizzare le dimensioni dell'immagine aiuta a rimanere ben al di sotto di questo limite.

---

**Last Updated:** 2026-10-12  
**Tested with:** Aspose.Email for Java 24.11 (latest at time of writing)  
**Author:** Aspose

## Tutorial correlati

- [Gestione del limite di dimensione degli allegati email con Aspose.Email](/email/java/advanced-email-attachments/managing-large-attachments/)
- [Creare e inviare email con allegati Aspose Email Java](/email/java/attachments-handling/build-send-emails-attachments-aspose-email-java/)
- [Come estrarre gli allegati da file msg usando Aspose.Email per Java](/email/java/advanced-email-attachments/extracting-attachments-from-email-messages/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}