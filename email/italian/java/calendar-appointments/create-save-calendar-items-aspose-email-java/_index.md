---
date: '2026-05-18'
description: Guida passo‑passo su come creare un elemento calendario Java con Aspose.Email
  per Java, includendo il codice per salvare come .ics, aggiungere promemoria e lavorare
  con MAPI.
keywords:
- how to create calendar item java
- Aspose.Email Java
- calendar item Java
- ICS format Java
- MAPI calendar Java
schemas:
- author: Aspose
  dateModified: '2026-05-18'
  description: Step‑by‑step guide on how to create calendar item java with Aspose.Email
    for Java, including code to save as .ics, add reminders, and work with MAPI.
  headline: How to Create Calendar Item Java Using Aspose.Email
  type: TechArticle
- description: Step‑by‑step guide on how to create calendar item java with Aspose.Email
    for Java, including code to save as .ics, add reminders, and work with MAPI.
  name: How to Create Calendar Item Java Using Aspose.Email
  steps:
  - name: '**Add Dependency:** Ensure your `pom.xml` includes the necessary dependency
      as shown above.'
    text: '**Add Dependency:** Ensure your `pom.xml` includes the necessary dependency
      as shown above.'
  - name: '**Download and Include JAR:** Alternatively, download the JAR file from
      [Aspose Downloads](https://releases.aspose.com/email/java/) and add it to your
      project’s classpath.'
    text: '**Download and Include JAR:** Alternatively, download the JAR file from
      [Aspose Downloads](https://releases.aspose.com/email/java/) and add it to your
      project’s classpath.'
  - name: '**License Setup:** If you have a license file, initialize it in your code
      to unlock full features:'
    text: '**License Setup:** If you have a license file, initialize it in your code
      to unlock full features:'
  - name: '**Initialize MapiCalendar:**'
    text: '**Initialize MapiCalendar:**'
  - name: '**Set Appointment Details:**'
    text: '**Set Appointment Details:**'
  - name: '**Define Start and End Dates:**'
    text: '**Define Start and End Dates:**'
  - name: '**Add Reminders (Optional):**'
    text: '**Add Reminders (Optional):**'
  - name: '**Save the Appointment:**'
    text: '**Save the Appointment:**'
  type: HowTo
- questions:
  - answer: Yes – set the `Recurrence` property on `MapiCalendar` and define the recurrence
      pattern (daily, weekly, etc.).
    question: Can I generate recurring appointments?
  - answer: Absolutely – use `MapiCalendar.fromFile("path.ics")` to load and manipulate
      existing calendar data.
    question: Is it possible to read existing .ics files?
  - answer: It does; the library converts UTC to the target zone based on the `TimeZoneInfo`
      object you provide.
    question: Does Aspose.Email support time‑zone conversion automatically?
  - answer: Attach a `MapiReminderAudio` object to the `Reminders` collection and
      specify the path to a .wav file.
    question: How do I add an audio reminder?
  - answer: Up to **2 GB** per file without performance degradation, thanks to streaming
      APIs.
    question: What is the maximum file size Aspose.Email can handle?
  type: FAQPage
title: Come creare un elemento di calendario Java usando Aspose.Email
url: /it/java/calendar-appointments/create-save-calendar-items-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Come creare un elemento di calendario Java usando Aspose.Email

Nelle moderne applicazioni aziendali, l'automazione degli inviti a riunioni e delle voci di calendario fa risparmiare innumerevoli ore. Questo tutorial mostra **come creare un elemento di calendario java** con Aspose.Email, coprendo tutto, dall'inizializzazione dell'oggetto al salvataggio di un appuntamento come file *.ics*, aggiungendo promemoria visivi e audio, ed estraendo lo stato dei destinatari dai messaggi MAPI. Alla fine, sarai in grado di incorporare funzionalità di calendario complete direttamente nei tuoi servizi Java.

## Risposte rapide
- **Quale libreria è necessaria?** Aspose.Email for Java (v25.4 o successiva).  
- **Posso salvare come .ics?** Sì – chiama `MapiCalendar.save(..., SaveOptions.getIcs())`.  
- **È necessaria una licenza per la produzione?** Una licenza valida di Aspose.Email rimuove i limiti di valutazione.  
- **Quale versione di Java è supportata?** JDK 8 + (inclusi Java 11 e 17).  
- **Maven è supportato?** Assolutamente – aggiungi la dipendenza Maven a `pom.xml`.

La classe `SaveOptions` fornisce le opzioni di salvataggio; `getIcs()` restituisce le impostazioni per il formato iCalendar.

## Come creare un elemento di calendario in Java?

Carica la classe `MapiCalendar`, imposta le proprietà richieste (oggetto, luogo, orari di inizio/fine) e chiama `save` con il formato ICS – l'intera operazione può essere eseguita in meno di dieci righe di codice. Aspose.Email gestisce automaticamente la conversione del fuso orario e le regole di ricorrenza, garantendo che il file *.ics* generato sia conforme a RFC 5545.

## Perché utilizzare Aspose.Email per la gestione del calendario?

Aspose.Email supporta **70+** formati di email e calendario, elabora file fino a **2 GB** senza caricare l'intero documento in memoria, e offre un approccio **single‑API** per gli standard MAPI e iCalendar. Questa capacità quantificata significa che puoi generare, modificare e leggere elementi di calendario in modo affidabile su larga scala.

## Prerequisiti
- **Java Development Kit (JDK):** Versione 8 o superiore.  
- **Maven:** Per la gestione delle dipendenze.  
- **Aspose.Email for Java:** Versione 25.4 o più recente (si consiglia l'ultima release).

## Configurazione dell'ambiente

Per includere Aspose.Email nel tuo progetto Maven, aggiungi la seguente dipendenza al tuo `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

## Acquisizione della licenza

Aspose.Email offre una licenza di prova gratuita che rimuove la maggior parte delle restrizioni di valutazione. Per l'uso in produzione, acquista un abbonamento o richiedi una licenza temporanea per i test.

## Configurazione di Aspose.Email per Java

1. **Aggiungi dipendenza:** Assicurati che il tuo `pom.xml` includa la dipendenza necessaria come mostrato sopra.  
2. **Scarica e includi il JAR:** In alternativa, scarica il file JAR da [Aspose Downloads](https://releases.aspose.com/email/java/) e aggiungilo al classpath del tuo progetto.  
3. **Configurazione della licenza:** Se disponi di un file di licenza, inizializzalo nel tuo codice per sbloccare tutte le funzionalità:

   ```java
   License license = new License();
   license.setLicense("Path_to_Aspose.Email_License_File");
   ```

La classe `License` carica e applica un file di licenza Aspose.Email, abilitando l'uso di tutte le funzionalità.

## Guida all'implementazione

Di seguito percorriamo i passaggi fondamentali necessari per **creare oggetti calendar item java**, arricchirli con promemoria e salvarli come file *.ics*.

### Creazione e salvataggio di elementi di calendario

#### Panoramica
Questa sezione dimostra come creare programmaticamente un appuntamento di calendario, allegare promemoria visivi e audio, e salvare il risultato nel formato iCalendar universale.

#### Implementazione passo‑a‑passo

1. **Inizializza MapiCalendar:**  
   La classe `MapiCalendar` rappresenta un oggetto calendario nel formato MAPI. Funziona come punto di ingresso per impostare tutte le proprietà dell'appuntamento.

   ```java
   MapiCalendar appointment = new MapiCalendar();
   ```

2. **Imposta i dettagli dell'appuntamento:**  
   Fornisci un oggetto chiaro, una posizione e un corpo descrittivo per la riunione.

   ```java
   appointment.setLocation("LAKE ARGYLE WA 6743");
   appointment.setSubject("Appointment");
   appointment.setBody("This is a very important meeting");
   ```

3. **Definisci le date di inizio e fine:**  
   Utilizza `GregorianCalendar` per specificare i timestamp esatti di inizio e fine, tenendo conto delle considerazioni sul fuso orario.

   ```java
   Calendar cal = GregorianCalendar.getInstance();
   cal.set(2016, 10, 2); // Month is zero-based.
   Date startDate = cal.getTime();

   cal.setTime(startDate);
   cal.add(Calendar.DAY_OF_MONTH, 1); // End date is one day later.
   Date endDate = cal.getTime();

   appointment.setStartDate(startDate);
   appointment.setEndDate(endDate);
   ```

4. **Aggiungi promemoria (opzionale):**  
   Puoi allegare un promemoria visivo (pop‑up) e un promemoria audio (file wav) per migliorare la notifica ai partecipanti.  
   *Consiglio:* Imposta `ReminderMinutesBeforeStart` a `15` per un avviso di 15 minuti prima dell'inizio.  
   La classe `MapiReminderAudio` rappresenta un promemoria audio allegato a un elemento di calendario.

5. **Salva l'appuntamento:**  
   Salva l'elemento di calendario come file *.ics* nella cartella di destinazione desiderata.

   ```java
   String dataDir = "YOUR_OUTPUT_DIRECTORY/";
   appointment.save(dataDir + "CalendarItem_out.ics\
   ```

## Problemi comuni e consigli

- **Discrepanze di fuso orario:** Specifica sempre il fuso orario quando imposti `StartDate` e `EndDate` per evitare errori di ora legale.  
- **Liste di partecipanti grandi:** Per riunioni con più di 200 partecipanti, utilizza il batching di `MapiRecipientCollection` per rimanere entro i limiti di memoria.  
  La classe `MapiRecipientCollection` contiene un elenco di partecipanti alla riunione.  
- **Licenza mancante:** Se il file di licenza non è caricato, l'API passa a una modalità di prova che limita il numero di elementi salvati a **10** per esecuzione.

## Domande frequenti

**Q: Posso generare appuntamenti ricorrenti?**  
**A:** Sì – imposta la proprietà `Recurrence` su `MapiCalendar` e definisci il modello di ricorrenza (giornaliero, settimanale, ecc.).

**Q: È possibile leggere file .ics esistenti?**  
**A:** Assolutamente – usa `MapiCalendar.fromFile("path.ics")` per caricare e manipolare i dati di calendario esistenti.

**Q: Aspose.Email supporta automaticamente la conversione del fuso orario?**  
**A:** Sì; la libreria converte UTC nella zona target basandosi sull'oggetto `TimeZoneInfo` fornito.

**Q: Come aggiungo un promemoria audio?**  
**A:** Allega un oggetto `MapiReminderAudio` alla collezione `Reminders` e specifica il percorso a un file .wav.

**Q: Qual è la dimensione massima del file che Aspose.Email può gestire?**  
**A:** Fino a **2 GB** per file senza degrado delle prestazioni, grazie alle API di streaming.

---

**Ultimo aggiornamento:** 2026-05-18  
**Testato con:** Aspose.Email for Java 25.4  
**Autore:** Aspose

## Tutorial correlati

- [Gestisci la condivisione del calendario - Guida Aspose.Email per Java](/email/java/calendar-appointments/create-send-calendar-invitations-aspose-email-java/)
- [Come estrarre elementi del calendario Outlook in ICS usando Aspose.Email per Java](/email/java/calendar-appointments/extract-outlook-calendar-to-ics-aspose-email-java/)
- [Come leggere più eventi di calendario da un file ICS usando Aspose.Email in Java](/email/java/calendar-appointments/read-multiple-ics-events-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}