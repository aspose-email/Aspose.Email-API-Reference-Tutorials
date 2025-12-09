---
date: 2025-11-30
description: Scopri come allegare un'immagine a un'email usando Aspose.Email per Java,
  inviare email HTML con immagine incorporata e ottimizzare le dimensioni dell'immagine
  per l'email.
linktitle: How to Attach Image to Email with Aspsoe.Email
second_title: Aspose.Email Java Email Management API
title: Come allegare un'immagine a un'email con Aspose.Email per Java
url: /it/java/advanced-email-attachments/embedding-images-as-attachments/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Come allegare un'immagine a un'email con Aspose.Email per Java

Nella comunicazione email moderna, **come allegare un'immagine a un'email** è più importante che mai—le immagini aumentano il coinvolgimento e aiutano a trasmettere il tuo messaggio istantaneamente. Questo tutorial ti guida attraverso l'intero processo di allegare un'immagine, incorporarla in un corpo HTML e garantire che il messaggio abbia un aspetto ottimale su tutti i client di posta. Tratteremo anche consigli di best‑practice per inviare un'email HTML con immagine incorporata e ottimizzare le dimensioni dell'immagine per l'email.

## Risposte rapide
- **Qual è la classe principale per creare un'email?** `MailMessage`
- **Quale classe consente di incorporare un'immagine nel corpo HTML?** `LinkedResource`
- **È necessaria una licenza per inviare email in produzione?** Sì, è richiesta una licenza commerciale di Aspose.Email.
- **Come posso ridurre le dimensioni dell'allegato?** Ottimizza l'immagine prima di aggiungerla (ad es., ridimensiona/comprimi).
- **Posso inviare più immagini?** Assolutamente—basta aggiungere un Content‑ID unico per ciascuna.

## Che cosa significa allegare un'immagine a un'email?
Allegare un'immagine significa aggiungere il file alla struttura MIME dell'email affinché il destinatario possa visualizzarlo. Quando incorpori l'immagine usando un Content‑ID (CID), l'immagine appare direttamente nel corpo HTML invece di essere un allegato separato, dando l'impressione di un'immagine in linea.

## Perché inviare email HTML con immagine incorporata?
Incorporare immagini all'interno dell'HTML ti permette di progettare newsletter più ricche, annunci di prodotto o ticket di supporto. I destinatari vedono il contenuto visivo subito, senza dover scaricare un allegato, il che migliora i tassi di apertura e il coinvolgimento complessivo.

## Prerequisiti
- **Aspose.Email for Java** – scarica dal sito ufficiale: [Aspose.Email Java download](https://releases.aspose.com/email/java/).
- Un **server SMTP** valido (ad es., Gmail, Outlook o il tuo relay di posta).
- Un file immagine che desideri incorporare (JPEG, PNG, GIF, ecc.).

> **Suggerimento professionale:** *Ottimizza le dimensioni dell'immagine per l'email* ridimensionandola a ≤600 px di larghezza e comprimendola a ≤100 KB. Questo riduce i tempi di caricamento ed evita di superare i limiti di dimensione della casella di posta.

## Creazione di un messaggio email
Per prima cosa, importa gli spazi dei nomi richiesti e istanzia un `MailMessage`. Questo oggetto conterrà l'oggetto, i destinatari e il corpo della tua email.

```java
// Import necessary libraries
import com.aspose.email.*;

// Create a new email message
MailMessage message = new MailMessage();
```

## Aggiunta dell'immagine come allegato
Successivamente, indica il percorso del file immagine sul disco e aggiungilo alla collezione di allegati del messaggio. L'allegato verrà poi referenziato da un Content‑ID.

```java
// Specify the path to the image file
String imagePath = "path/to/your/image.jpg";

// Attach the image to the email
Attachment attachment = new Attachment(imagePath);
message.getAttachments().add(attachment);
```

## Incorporamento dell'immagine allegata nell'HTML
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

> **Perché usare `LinkedResource`?** Indica al client di posta che l'immagine fa parte del corpo del messaggio, non è un download separato, il che è fondamentale per gli scenari di **invio di email HTML con immagine incorporata**.

## Invio dell'email
Infine, configura `SmtpClient` con i dettagli del tuo server e invia il messaggio. Assicurati che le credenziali SMTP abbiano l'autorizzazione a inviare per conto dell'indirizzo del mittente.

```java
// Initialize the SmtpClient
SmtpClient client = new SmtpClient("smtp.example.com", 587, "your_username", "your_password");

// Send the email
client.send(message);
```

Quando il destinatario apre l'email, il corpo HTML renderizzerà l'immagine in linea, fornendo un'esperienza visiva fluida.

## Problemi comuni e risoluzione
| Problema | Causa | Soluzione |
|----------|-------|-----------|
| Immagine non visualizzata | Content‑ID errato o `LinkedResource` mancante | Verifica che `linkedImage.setContentId("image1")` corrisponda a `src='cid:image1'` nell'HTML. |
| Dimensione email elevata | Immagine non ottimizzata (alta risoluzione) | Ridimensiona/comprimi l'immagine prima di allegarla; mira a ≤100 KB. |
| Email segnalata come spam | Mancano intestazioni MIME corrette | Assicurati che `SmtpClient` utilizzi TLS/STARTTLS e imposta un indirizzo `From` chiaro. |
| L'immagine in linea appare come allegato | Il client non supporta CID | Fornisci un URL di fallback nel tag `<img>` (`src='cid:image1' alt='Image'`). |

## Domande frequenti

**D: Come posso incorporare più immagini in una singola email?**  
R: Ripeti i passaggi di allegato e `LinkedResource` per ogni immagine, assegnando un Content‑ID unico (ad es., `image2`, `image3`) e riferendoli nell'HTML.

**D: Posso incorporare immagini in email di solo testo?**  
R: Il formato plain‑text non supporta immagini incorporate. Puoi includere solo URL che i destinatari possono cliccare per visualizzare l'immagine online.

**D: Quali formati di immagine sono sicuri per l'incorporamento nelle email?**  
R: JPEG, PNG e GIF sono ampiamente supportati. Usa JPEG per le fotografie e PNG per grafiche con trasparenza.

**D: È possibile controllare le dimensioni dell'immagine nell'email?**  
R: Sì—aggiungi gli attributi width/height al tag `<img>`, ad es., `<img src='cid:image1' width='400' height='300'>`.

**D: Esistono limiti di dimensione per le immagini incorporate?**  
R: Sebbene non vi siano limiti SMTP rigidi, la maggior parte dei provider di posta consiglia di mantenere la dimensione totale dell'email sotto 5 MB. Ottimizzare le dimensioni dell'immagine aiuta a rimanere ben al di sotto di questo limite.

## Conclusione
Ora sai **come allegare un'immagine a un'email** usando Aspose.Email per Java, incorporarla in un corpo HTML e applicare le best practice come **ottimizzare le dimensioni dell'immagine per l'email**. Questa tecnica ti consente di creare messaggi visivamente accattivanti che coinvolgono i destinatari e appaiono professionali su tutti i client di posta.

---

**Ultimo aggiornamento:** 2025-11-30  
**Testato con:** Aspose.Email for Java 24.11 (ultima versione al momento della stesura)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}