---
date: '2026-08-27'
description: Scopri come caricare file MSG e convertirli in MHTML con Aspose.Email
  per Java, includendo impostazioni personalizzate del fuso orario e consigli per
  l'elaborazione batch delle email.
keywords:
- how to load msg
- Aspose.Email Java
- convert MSG to MHTML
- email timezone offset
lastmod: '2026-08-27'
og_description: Scopri come caricare file msg ed esportarli come MHTML usando Aspose.Email
  per Java. Include la gestione del fuso orario e consigli per l'elaborazione batch.
og_image_alt: Guide to loading MSG files and saving as MHTML with Aspose.Email for
  Java
og_title: Come caricare msg e salvarli come MHTML con Aspose.Email per Java
schemas:
- author: Aspose
  dateModified: '2026-08-27'
  description: Learn how to load MSG files and convert them to MHTML with Aspose.Email
    for Java, including custom timezone settings and batch email processing tips.
  headline: How to load msg and save as MHTML using Aspose.Email for Java
  type: TechArticle
- description: Learn how to load MSG files and convert them to MHTML with Aspose.Email
    for Java, including custom timezone settings and batch email processing tips.
  name: How to load msg and save as MHTML using Aspose.Email for Java
  steps:
  - name: '**Reuse the license** – call `new License().setLicense(...)` once at application
      startup.'
    text: '**Reuse the license** – call `new License().setLicense(...)` once at application
      startup.'
  - name: '**Use try‑with‑resources** for automatic cleanup of streams.'
    text: '**Use try‑with‑resources** for automatic cleanup of streams.'
  - name: '**Log failures** to a separate file so you can retry problematic messages
      later.'
    text: '**Log failures** to a separate file so you can retry problematic messages
      later.'
  - name: '**Consider parallelism** with `ForkJoinPool` for large batches, but ensure
      each thread uses its own `MailMessage` instance.'
    text: '**Consider parallelism** with `ForkJoinPool` for large batches, but ensure
      each thread uses its own `MailMessage` instance.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Email supports EML, MHT, EMLX, and several other formats,
      totaling over 30 input types.
    question: Can I load emails from formats other than .msg?
  - answer: Use the streaming APIs (`MailMessage.load(InputStream, ...)`) to read
      and write data in chunks, which keeps memory consumption under 50 MB even for
      500‑page messages.
    question: How can I handle very large email files efficiently?
  - answer: Absolutely. You can add, remove, or replace attachments via the `msg.getAttachments()`
      collection, then call `save` to persist changes.
    question: Is it possible to modify attachments within a MailMessage?
  - answer: Pass a negative millisecond value to `setTimeZoneOffset`, e.g., `-3 *
      60 * 60 * 1000` for UTC‑3.
    question: What if my timezone offset is negative (behind UTC)?
  - answer: Yes, provided you have a valid commercial license. The free trial is limited
      to 20 MB per document.
    question: Can I use Aspose.Email in commercial projects?
  type: FAQPage
tags:
- email processing
- Aspose.Email
- Java email conversion
title: Come caricare file msg e salvarli come MHTML usando Aspose.Email per Java
url: /it/java/email-message-operations/load-save-emails-mhtml-aspose-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come caricare msg e salvare come MHTML usando Aspose.Email per Java

## Introduzione

Se hai bisogno di **come caricare msg** file, regolare i loro timestamp e poi **convertire msg in mhtml**, sei nel posto giusto. In questo tutorial ti guideremo attraverso il caricamento di una email `.msg`, l'applicazione di un offset di fuso orario personalizzato e il salvataggio del risultato come archivio MHTML — tutto con Aspose.Email per Java. Che tu stia gestendo un singolo messaggio o una **elaborazione batch di email**, questi passaggi ti forniranno una solida base per un'archiviazione e migrazione affidabili.

**Cosa imparerai**
- Come caricare un `MailMessage` da un file `.msg`.
- Come impostare un fuso orario personalizzato e la data corrente.
- Come salvare il messaggio come MHTML con formattazione precisa.
- Suggerimenti per scalare l'approccio a scenari batch.

Pronto a migliorare il tuo flusso di lavoro email? Prepariamo prima l'ambiente.

## Risposte rapide
- **Qual è la libreria principale?** Aspose.Email for Java.
- **Posso caricare MSG ed esportare in MHTML in un solo passaggio?** No, devi caricare, regolare, poi salvare.
- **Ho bisogno di una licenza per la produzione?** Sì, è necessaria una licenza valida di Aspose.Email.
- **La gestione del fuso orario è supportata?** Sì, tramite `setTimeZoneOffset`.
- **Può essere usato nell'elaborazione batch?** Assolutamente – avvolgi i passaggi in un ciclo.

## Cos'è Aspose.Email per Java?

Aspose.Email per Java è un'API completa che ti consente di creare, leggere, convertire e manipolare messaggi email senza richiedere Microsoft Outlook. Supporta più di 30 formati email e può elaborare messaggi di centinaia di pagine mantenendo un basso utilizzo di memoria.

## Perché convertire MSG in MHTML?

Convertire i file MSG in MHTML ti fornisce una rappresentazione web‑friendly, a file unico, che può essere aperta in qualsiasi browser moderno. Questo formato preserva lo stile originale, le immagini incorporate e gli allegati, rendendolo ideale per **archiviazione legale**, **condivisione cross‑platform** e **incorporamento di email in pagine web o documentazione**.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

### Librerie e dipendenze richieste
- **Aspose.Email for Java** versione 25.4 (classificatore jdk16) – la libreria supporta **oltre 50** formati di email in ingresso e uscita.
- Conoscenze di base di Java.
- Un IDE come IntelliJ IDEA o Eclipse.

### Requisiti di configurazione dell'ambiente
- JDK 16 o superiore installato.
- Maven per la gestione delle dipendenze.

## Configurazione di Aspose.Email per Java

Per aggiungere la libreria a un progetto Maven, includi la seguente dipendenza:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Passaggi per l'acquisizione della licenza

Inizia con una **prova gratuita** o ottieni una **licenza temporanea** per valutare le capacità complete della libreria senza limitazioni. Per un uso a lungo termine, considera l'acquisto di una licenza:

- [Prova gratuita](https://releases.aspose.com/email/java/)
- [Licenza temporanea](https://purchase.aspose.com/temporary-license/)
- [Acquista licenza](https://purchase.aspose.com/buy)

### Inizializzazione di base

La classe `License` registra la tua licenza Aspose.Email per sbloccare tutte le funzionalità.  
Dopo aver aggiunto la dipendenza, inizializza la licenza nel tuo codice Java:

```java
import com.aspose.email.License;

License license = new License();
license.setLicense("Aspose.Email.lic");
```
```java
import com.aspose.email.License;

License license = new License();
license.setLicense("path_to_your_license_file.lic");
```

## Come caricare msg e salvare come MHTML?

Carica il file MSG, regola il timestamp e salvalo come MHTML in tre semplici passaggi. Prima, istanzia un `MailMessage` dal file MSG usando `MsgLoadOptions`. Poi, imposta l'offset di fuso orario desiderato con `setTimeZoneOffset`. Infine, configura `MhtSaveOptions` e chiama `save` per produrre l'archivio MHTML.

### Funzione 1: caricamento di un MailMessage da un file

La classe `MailMessage` rappresenta un messaggio email con intestazioni, corpo e allegati.

```java
import com.aspose.email.MailMessage;
import com.aspose.email.MsgLoadOptions;
```
```java
import com.aspose.email.MailMessage;
import com.aspose.email.MsgLoadOptions;
```

```java
MsgLoadOptions loadOptions = new MsgLoadOptions();
MailMessage msg = MailMessage.load("sample.msg", loadOptions);
```
```java
String filename = "YOUR_DOCUMENT_DIRECTORY/MSG file with RTF Formatting.msg";
MailMessage msg = MailMessage.load(filename, new MsgLoadOptions());
```

`MsgLoadOptions` ti consente di controllare come il file MSG viene analizzato; le impostazioni predefinite funzionano per la maggior parte degli scenari.

### Funzione 2: impostazione della data corrente e offset del fuso orario personalizzato

L'oggetto `Date` contiene il timestamp che verrà scritto nell'intestazione **Date** dell'email.

```java
java.util.Date now = new java.util.Date();
msg.setDate(now);
```
```java
import java.util.Date;

msg.setDate(new Date());
```

L'offset è espresso in millisecondi; per UTC+5 si passa `5 * 60 * 60 * 1000`.

```java
int utcPlusFive = 5 * 60 * 60 * 1000;
msg.setTimeZoneOffset(utcPlusFive);
```
```java
msg.setTimeZoneOffset(5 * 60 * 60 * 1000); // 5 hours ahead of UTC in milliseconds.
```

### Funzione 3: salvataggio di un MailMessage come file MHTML

`MhtSaveOptions` definisce come l'email viene confezionata in un archivio MHTML, preservando immagini inline e allegati.

```java
import com.aspose.email.MhtSaveOptions;
MhtSaveOptions saveOptions = new MhtSaveOptions();
saveOptions.setWriteHeader(true);
```
```java
import com.aspose.email.MhtSaveOptions;
import com.aspose.email.MhtFormatOptions;

MhtSaveOptions mhtOptions = new MhtSaveOptions();
mhtOptions.setMhtFormatOptions(MhtFormatOptions.WriteHeader);
```

```java
msg.save("output.mhtml", saveOptions);
```
```java
msg.save("YOUR_OUTPUT_DIRECTORY/ExportToMHTWithCustomTimezone_out.mhtml", mhtOptions);
```

Il file `.mhtml` risultante mantiene la formattazione originale, le immagini e gli allegati, diventando una copia visiva fedele del MSG originale.

## Come impostare un offset del fuso orario personalizzato?

Puoi modificare il fuso orario chiamando `setTimeZoneOffset` sull'istanza `MailMessage`. Il metodo si aspetta un offset in millisecondi, consentendo valori sia positivi (est dell'UTC) sia negativi (ovest dell'UTC). Per esempio, UTC‑3 è `-3 * 60 * 60 * 1000`.

## Come elaborare file MSG in batch?

Avvolgi il flusso di lavoro a tre passaggi all'interno di un ciclo che itera su una directory di file `.msg`. Riutilizza una singola istanza `License` per evitare I/O ripetuti e rilascia ogni `MailMessage` dopo il salvataggio per mantenere basso l'utilizzo di memoria.

```java
File folder = new File("msg_folder");
for (File file : folder.listFiles((dir, name) -> name.toLowerCase().endsWith(".msg"))) {
    MailMessage msg = MailMessage.load(file.getAbsolutePath(), new MsgLoadOptions());
    // set date & timezone as shown earlier
    msg.save(file.getName().replace(".msg", ".mhtml"), new MhtSaveOptions());
    msg.dispose(); // releases native resources
}
```

### Suggerimenti per l'elaborazione batch
1. **Riutilizza la licenza** – chiama `new License().setLicense(...)` una sola volta all'avvio dell'applicazione.
2. **Usa try‑with‑resources** per la pulizia automatica degli stream.
3. **Registra i fallimenti** in un file separato così da poter riprovare i messaggi problematici più tardi.
4. **Considera il parallelismo** con `ForkJoinPool` per batch di grandi dimensioni, ma assicurati che ogni thread utilizzi la propria istanza di `MailMessage`.

## Problemi comuni e soluzioni

- **Picchi di memoria con file MSG enormi** – abilita lo streaming usando `MailMessage.load(InputStream, MsgLoadOptions)` e processa lo stream a blocchi.
- **Timestamp errati** – verifica che l'orologio di sistema sia impostato su UTC prima di applicare gli offset, o passa esplicitamente un'istanza `java.util.Calendar`.
- **Allegati mancanti in MHTML** – assicurati che `MhtSaveOptions.setWriteHeader(true)` sia attivo; questo incorpora gli allegati come risorse `cid:`.

## Domande frequenti

**Q: Posso caricare email da formati diversi da .msg?**  
A: Sì, Aspose.Email supporta EML, MHT, EMLX e diversi altri formati, per un totale di oltre 30 tipi di input.

**Q: Come posso gestire file email molto grandi in modo efficiente?**  
A: Usa le API di streaming (`MailMessage.load(InputStream, ...)`) per leggere e scrivere dati a blocchi, mantenendo il consumo di memoria sotto i 50 MB anche per messaggi di 500 pagine.

**Q: È possibile modificare gli allegati all'interno di un MailMessage?**  
A: Assolutamente. Puoi aggiungere, rimuovere o sostituire gli allegati tramite la collezione `msg.getAttachments()`, quindi chiamare `save` per persistere le modifiche.

**Q: Cosa succede se il mio offset del fuso orario è negativo (dietro UTC)?**  
A: Passa un valore millisecondi negativo a `setTimeZoneOffset`, ad esempio `-3 * 60 * 60 * 1000` per UTC‑3.

**Q: Posso usare Aspose.Email in progetti commerciali?**  
A: Sì, a condizione di possedere una licenza commerciale valida. La prova gratuita è limitata a 20 MB per documento.

**Q: Come elaborare migliaia di file MSG senza esaurire la memoria?**  
A: Elabora i file in batch, rilascia ogni `MailMessage` dopo il salvataggio e utilizza il pattern `try‑with‑resources` di Java per la pulizia automatica.

## Risorse
- [documentazione](https://reference.aspose.com/email/java/)
- [Documentazione](https://reference.aspose.com/email/java/)
- [Scarica libreria](https://releases.aspose.com/email/java/)
- [Acquista licenza](https://purchase.aspose.com/buy)
- [Prova gratuita](https://releases.aspose.com/email/java/)
- [Licenza temporanea](https://purchase.aspose.com/temporary-license/)
- [Forum di supporto](https://forum.aspose.com/c/email/10)

---

**Ultimo aggiornamento:** 2026-08-27  
**Testato con:** Aspose.Email for Java 25.4 (classificatore jdk16)  
**Autore:** Aspose

## Tutorial correlati

- [Come caricare e analizzare file Outlook MSG usando Aspose.Email per Java: Guida completa](/email/java/mapi-operations/outlook-msg-aspose-email-java-guide/)
- [Maven Aspose.Email per Java: salvare email come file MHT](/email/java/email-message-operations/save-emails-as-mht-using-aspose-email-java/)
- [Come estrarre gli allegati dai file msg usando Aspose.Email per Java](/email/java/advanced-email-attachments/extracting-attachments-from-email-messages/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}