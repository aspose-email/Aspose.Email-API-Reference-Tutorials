---
date: 2026-04-21
description: Scopri come incorporare un'immagine in un'email HTML usando Aspose.Email
  per Java, inviare email HTML con immagine incorporata e ridurre la dimensione degli
  allegati email.
keywords:
- embed image html email
- send html email java
- create email with image
- reduce email attachment size
- embed multiple images email
linktitle: Come allegare un'immagine a un'email con Aspsoe.Email
second_title: Aspose.Email Java Email Management API
title: Come incorporare un'immagine in un'email HTML con Aspose.Email per Java
url: /it/java/advanced-email-attachments/embedding-images-as-attachments/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Come incorporare un'immagine in un'email HTML con Aspose.Email per Java

Nella comunicazione email moderna, **embed image html email** è più importante che mai—le immagini aumentano il coinvolgimento e aiutano a trasmettere il tuo messaggio istantaneamente. Questo tutorial ti guida attraverso l'intero processo di allegare un'immagine, incorporarla all'interno di un corpo HTML e garantire che il messaggio abbia un aspetto ottimale su tutti i client di posta. Tratteremo anche consigli di best‑practice per **send html email java**, creare email con immagine e **reduce email attachment size**.

## Risposte rapide
- **Qual è la classe principale per creare un'email?** `MailMessage`
- **Quale classe consente di incorporare un'immagine nel corpo HTML?** `LinkedResource`
- **È necessario una licenza per inviare email in produzione?** Sì, è richiesta una licenza commerciale di Aspose.Email.
- **Come posso ridurre la dimensione dell'allegato?** Ottimizza l'immagine prima di aggiungerla (ad es., ridimensiona/comprimi).
- **Posso inviare più immagini?** Assolutamente—basta aggiungere un Content‑ID unico per ciascuna.

## Cos'è embed image html email?
Allegare un'immagine significa aggiungere il file alla struttura MIME dell'email affinché il destinatario possa visualizzarla. Quando incorpori l'immagine usando un Content‑ID (CID), l'immagine appare direttamente all'interno del corpo HTML invece di essere un allegato separato, dando l'impressione di un'immagine in linea.

## Perché inviare email HTML con immagine incorporata?
Incorporare immagini dentro l'HTML ti permette di progettare newsletter più ricche, annunci di prodotto o ticket di supporto. I destinatari vedono il visual subito, senza dover scaricare un allegato, il che migliora i tassi di apertura e il coinvolgimento complessivo.

## Prerequisiti
- **Aspose.Email per Java** – scarica dal sito ufficiale: [Aspose.Email Java download](https://releases.aspose.com/email/java/).
- Un **SMTP server** valido (ad es., Gmail, Outlook o il tuo relay di posta).
- Un file immagine che desideri incorporare (JPEG, PNG, GIF, ecc.).

> **Suggerimento professionale:** *Ottimizza le dimensioni dell'immagine per l'email* ridimensionandola a ≤600 px di larghezza e comprimendola a ≤100 KB. Questo riduce i tempi di caricamento ed evita di superare i limiti di dimensione della casella.

## Creazione di un messaggio email
Per prima cosa, importa gli spazi dei nomi necessari e istanzia un `MailMessage`. Questo oggetto conterrà l'oggetto, i destinatari e il corpo della tua email.

```java
// Import necessary libraries
import com.aspose.email.*;

// Create a new email message
MailMessage message = new MailMessage();
```

## Aggiungere l'immagine come allegato
Successivamente, indica il file immagine sul disco e aggiungilo alla collezione di allegati del messaggio. L'allegato sarà poi referenziato da un Content‑ID.

```java
// Specify the path to the image file
String imagePath = "path/to/your/image.jpg";

// Attach the image to the email
Attachment attachment = new Attachment(imagePath);
message.getAttachments().add(attachment);
```

## Incorporare l'immagine allegata in HTML
Per visualizzare l'immagine all'interno del corpo dell'email, crea un `LinkedResource` che avvolge lo stream dell'allegato. Assegna un Content‑ID unico (ad es., `image1`) e riferiscilo nell'HTML usando lo schema URI `cid:`.

```java
// Create a LinkedResource for the attached image
LinkedResource linkedImage = new LinkedResource(attachment.getContentStream(), "image/jpeg");
linkedImage.setContentId("image1");

// Create an HTML body with the embedded image
String htmlBody = "<html><body><h1>Check out this image:</h1><img src='cid:image1'></body></html>";
message.setHtmlBody(htmlBody);
message.getLinkedResources().addItem(linkedImage);
```

> **Perché usare `LinkedResource`?** Indica al client di posta che l'immagine fa parte del corpo del messaggio, non è un download separato, il che è essenziale per gli scenari di **send HTML email with embedded image**.

## Invio dell'email
Infine, configura `SmtpClient` con i dettagli del tuo server e invia il messaggio. Assicurati che le credenziali SMTP abbiano l'autorizzazione a inviare per conto dell'indirizzo del mittente.

```java
// Initialize the SmtpClient
SmtpClient client = new SmtpClient("smtp.example.com", 587, "your_username", "your_password");

// Send the email
client.send(message);
```

Quando il destinatario apre l'email, il corpo HTML visualizzerà l'immagine in linea, fornendo un'esperienza visiva fluida.

## Come incorporare più immagini in un'email
Se ti serve più di un'immagine, ripeti i passaggi di allegato e `LinkedResource` per ogni file. Assegna Content‑ID distinti come `image2`, `image3` e riferiscili nell'HTML (`src='cid:image2'`, ecc.). Questo approccio scala facilmente per newsletter con diverse grafiche.

## Suggerimenti per ridurre la dimensione degli allegati email
- **Ridimensiona** l'immagine alle dimensioni esatte necessarie nell'email (tipicamente ≤600 px di larghezza).  
- **Comprimi** usando strumenti come ImageMagick o compressori online per mantenere il file sotto 100 KB.  
- **Scegli il formato giusto**: JPEG per foto, PNG per grafiche con trasparenza.  
- **Rimuovi i metadati EXIF** se non sono necessari.

## Problemi comuni e risoluzione
| Problema | Causa | Soluzione |
|----------|-------|-----------|
| Immagine non visualizzata | Content‑ID errato o `LinkedResource` mancante | Verifica che `linkedImage.setContentId("image1")` corrisponda a `src='cid:image1'` nell'HTML. |
| Dimensione email elevata | Immagine non ottimizzata (alta risoluzione) | Ridimensiona/comprimi l'immagine prima di allegarla; punta a ≤100 KB. |
| Email segnalata come spam | Mancano intestazioni MIME corrette | Assicurati che `SmtpClient` utilizzi TLS/STARTTLS e imposta un indirizzo `From` chiaro. |
| L'immagine in linea appare come allegato | Il client non supporta CID | Fornisci un URL di fallback nel tag `<img>` (`src='cid:image1' alt='Image'`). |

## Domande frequenti

**Q: Come posso incorporare più immagini in una singola email?**  
A: Ripeti i passaggi di allegato e `LinkedResource` per ogni immagine, assegnando un Content‑ID unico (ad es., `image2`, `image3`) e riferendoli nell'HTML.

**Q: Posso incorporare immagini in email di solo testo?**  
A: Il formato plain‑text non supporta immagini incorporate. Puoi includere solo URL che i destinatari possono cliccare per visualizzare l'immagine online.

**Q: Quali formati di immagine sono sicuri per l'incorporamento nelle email?**  
A: JPEG, PNG e GIF sono ampiamente supportati. Usa JPEG per fotografie e PNG per grafiche con trasparenza.

**Q: Esiste un modo per controllare le dimensioni dell'immagine nell'email?**  
A: Sì—aggiungi gli attributi width/height al tag `<img>`, ad es., `<img src='cid:image1' width='400' height='300'>`.

**Q: Ci sono limiti di dimensione per le immagini incorporate?**  
A: Sebbene non vi siano limiti SMTP rigidi, la maggior parte dei provider consiglia di mantenere la dimensione totale dell'email sotto 5 MB. Ottimizzare le dimensioni dell'immagine aiuta a rimanere ben al di sotto di questo limite.

---

**Ultimo aggiornamento:** 2026-04-21  
**Testato con:** Aspose.Email per Java 24.11 (latest at time of writing)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}