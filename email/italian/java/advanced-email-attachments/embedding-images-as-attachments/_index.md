---
date: 2026-01-29
description: Scopri come allegare un'immagine all'email usando Aspose.Email per Java,
  incorporare un'immagine in un'email HTML, inviare email HTML e ridurre le dimensioni
  dell'email con SMTP Java.
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

Nella comunicazione email moderna, **come allegare un'immagine a un'email** è più importante che mai: le immagini aumentano ilmettere il messaggio istantaneamente. In questa guida imparerai **come allegare un'immagine a un'email** usando Aspose.Email per Java, incorporare la affidabile.

## Risposte rapide
- **Qual è la classe principale per creare un'email?** `MailMessage`
- **Quale classe consente di incorporare un'immagine nel corpo HTML?** `LinkedResource`
- **È necessaria una licenza per inviare email in produzione?** Sì, è richiesta una licenza commerciale di Aspose.Email.
 dimensioni dell'allegato?** Ottimizza l'immagine prima di aggiungerla (ad es. ridimensiona/comprimi).
- **Posso inviare più immagini?** Assolutamente—basta aggiungere un Content‑ID univoco per ciascuna.
- **Quali impostazioni SMTP funzionano meglio con Java?** Usa TLS/STARTTLS sulla porta 587 per la maggior parte dei provider (`smtp email java`).

## Che cosa significa allegare un'immagine a un'email?
Allegare un'immagine significa aggiungere il file alla struttura MIME dell'email affinché il destinatario possa visualizzarlo. Quando incorpori l'immagine usando un Content‑ID (CID), l'immagine appare direttamente nel corpo HTML invece di essere un allegato separato, dando l'impressione di un'immagine in linea.

## Perché inviare email HTML con immagine incorporata?
Incorporare le immagini nell'HTML ti consente di progettare newsletter più ricche, annunci di prodotto o ticket di supporto. I destinatari vedono il contenuto visivo subito, senza dover scaricare un allegato, il che migliora i tassi di apertura e il coinvolgimento complessivo.

## Prerequisiti
Prima di iniziare, assicurati di avere:

- **Aspose.Email per Java** – scaricalo dal sito ufficiale: [Aspose.Email Java download](https://releases.aspose.com/email/java/).
- Un **server SMTP** valido (ad es. Gmail, Outlook o il tuo relay di posta).
- Un file immagine che desideri incorporare (JPEG, PNG, GIF, ecc.).

> **Consiglio professionale:** *Ottimizza le dimensioni dell'immagine per l'email* ridimensionandola a ≤600 px di larghezza e comprimendola a ≤100 KB. Questo riduce i tempi di caricamento ed evita di superare i limiti di dimensione della casella di posta.

## Creazione di un messaggio email
Per prima cosa, importa gli spazi dei nomi necessari e istanzia un `MailMessage`. Questo oggetto conterrà l'oggetto, i destinatari e il corpo della tua email.

```java
// Import necessary libraries
import com.aspose.email.*;

// Create a new email message
MailMessage message = new MailMessage();
```

## Aggiungere l'immlezione degli allegati del messaggio. L'allegato verrà poi referenziato tramite un Content‑ID.

```java
// Specify the path to the image file
String imagePath = "path/to/your/image.jpg";

// Attach the image to the email
Attachment attachment = new Attachment(imagePath);
message.getAttachments().add(attachment);
```

## Incorporare l'immagine allegata nell'HTML
Per visualizzare l'immagine all'interno del corpo dell'email, crea un `LinkedResource` che avvolge lo stream dell'allegato. Assegna un Content‑ID univoco (ad es. `image1`) e riferiscilo nell'HTML usando lo schema URI `cid:`.

```java
// Create a LinkedResource for the attached image
LinkedResource linkedImage = new LinkedResource(attachment.getContentStream(), "image/jpeg");
linkedImage.setContentId("image1");

// Create an HTML body with the embedded image
String htmlBody = "<html><body><h1>Check out this image:</h1><img src='cid:image1'></body></html>";
message.setHtmlBody(htmlBody);
message.getLinkedResources().addItem(linkedImage);
```

> **Perché usare `LinkedResource`?** Indica al client di posta che l'immagine fa parte del corpo del messaggio, non è un download separato, ed è fondamentale per gli scenari **inviare email HTML con immagine incorporata**.

## Invio dell'email
Infine, configura `SmtpClient` con i dettagli del tuo server e invia il messaggio. Assicurati che le credenziali SMTP abbiano l'autorizzazione a inviare per conto dell'indirizzo del mittente.

```java
// Initialize the SmtpClient
SmtpClient client = new SmtpClient("smtp.example.com", 587, "your_username", "your_password");

// Send the email
client.send(message);
```

Quando il destinatario apre l'email, il corpo HTML renderizzerà l'immagine in linea, offrendo un'esperienza visiva fluida.

## Guida passo‑passo per allegare un'immagine all'email
Di seguito trovi una checklist concisa che riepiloga il codice mostrato, assicurandoti di non dimenticare alcun passaggio cruciale quando **alleggi un'immagine a un'email**:

1. **Prepara l'immagine** – ridimensiona/comprimi per mantenere bassa la dimensione totale dell'email (`reduce email size`).
2. **Crea `MailMessage`** – imposta From, To, Subject e un eventuale fallback in plain‑text.
3. **Aggiungi l'immagine come `Attachment`** – registra il file nel contenitore MIME.
4. **Avvolgi l'allegato in un `LinkedResource`** – assegna un Content‑ID univoco.
5. **Compila il corpo HTML** – riferisci il Content‑ID con `cid:` (es. `<img src='cid:image1'>`).
6. **Aggiungi il `LinkedResource` al messaggio** – rende l'immagine in linea.
7. **Configura `SmtpClient`** – usa TLS/STARTTLS (`smtp email java`) e l'autenticazione corretta.
8. **Invia il messaggio** – verifica che l'email arrivi con l'immagine visualizzata correttamente.

## Problemi comuni e risoluzione
| Problema | Causa | Soluzione |
|----------|-------|-----------|
| Immagine non visualizzata | Content‑ID errato o `LinkedResource` mancante | Verifica che `linkedImage.setContentId("image1")` corrisponda a `src='cid:image1'` nell'HTML. |
| Email di grandi dimensioni | Immagine non ottimizzata (alta risoluzione) | Ridimensiona/comprimi l'immagine prima di allegarla; punta a ≤100 KB. |
| Email segnalata come spam | Mancano intestazioni MIME corrette | Assicurati che `SmtpClient` usi TLS/STARTTLS e imposta un indirizzo `From` chiaro. |
| L'immagine in linea appare come allegato | Il client non supporta CID | Fornisci un URL di**D: Come posso incorporare più immagini in una singola email?**  
R: Ripeti i passaggi di allegato e `LinkedResource` per ogni immagine, assegnando un Content‑ID univoco (es. `image2`, `image3`) e riferendoli nell'HTML.

**D: Posso incorporare immagini in email plain‑text?**  
R: Il formato plain‑text non supporta immagini incorporate. Puoi solo includere URL che i destinatari possono cliccare per visualizzare l'immagine online.

**D: Quali formati di immagine sono sicuri per l'incorporamento nelle email?**  
R: JPEG, PNG e GIF sono ampiamente supportati. Usa JPEG per le fotografie e PNG per grafiche con trasparenza.

**D: È possibile controllare le dimensioni dell'immagine nell'email?**  
R: Sì—aggiungi gli attributi width/height al tag `<img>`, ad es. `<img src='cid:image1' width='400' height='300'>`.

**D: Esistono limiti di dimensione per le immagini incorporate?**  
R: Sebbene non vi siano lim provider consiglia di mantenere la dimensione totale dell'email sotto i 5 MB. Ottimizzare le immagini aiuta a rimanere ben al di sotto di questo limite.

## Conclusione
Ora sai **come allegare un'immagine a un'email** usando Aspose.Email per Java, incorporarla in un corpo HTML e applicare le migliori pratiche come **ottimizzare le dimensioni dell'immagine per l'email**. Questa tecnica ti permette di creare messaggi visivamente accattivanti che coinvolgono i destinatari e appaiono professionali su tutti i client di posta.

---

**Ultimo aggiornamento:** 2026-01-29  
**Testato con:** Aspose.Email per Java 24.  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}