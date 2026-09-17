---
date: '2026-09-17'
description: Scopri come esportare il PST del calendario Outlook usando Aspose.Email
  per Java – crea elementi calendario MAPI, imposta recurrence, aggiungi attendees
  e salva su PST.
keywords:
- export outlook calendar pst
- how to export pst
- how to add recurrence
- how to add attendees
- save calendar to pst
lastmod: '2026-09-17'
og_description: Esporta il PST del calendario Outlook usando Aspose.Email per Java.
  Scopri come creare elementi calendario MAPI, aggiungere recurrence, attendees e
  salvare su PST in pochi minuti.
og_image_alt: Guide to exporting Outlook calendar PST files with Aspose.Email for
  Java
og_title: Esporta PST del calendario Outlook con Aspose.Email – Java
schemas:
- author: Aspose
  dateModified: '2026-09-17'
  description: Learn how to export Outlook calendar PST using Aspose.Email for Java
    – create MAPI calendar items, set recurrence, add attendees, and save to PST.
  headline: Export Outlook calendar PST with Aspose.Email – Java
  type: TechArticle
- description: Learn how to export Outlook calendar PST using Aspose.Email for Java
    – create MAPI calendar items, set recurrence, add attendees, and save to PST.
  name: Export Outlook calendar PST with Aspose.Email – Java
  steps:
  - name: '**Initialize date and recurrence pattern**'
    text: '**Initialize date and recurrence pattern**'
  - name: '**Set up recipients**'
    text: '**Set up recipients**'
  - name: '**Create the MAPI calendar item**'
    text: '**Create the MAPI calendar item**'
  - name: '**Save to PST file**'
    text: '**Save to PST file**'
  - name: '**Automated meeting scheduling** – Generate recurring meeting invites for
      project teams without manual effort.'
    text: '**Automated meeting scheduling** – Generate recurring meeting invites for
      project teams without manual effort.'
  - name: '**Event management platforms** – Export conference sessions as Outlook‑compatible
      calendar items.'
    text: '**Event management platforms** – Export conference sessions as Outlook‑compatible
      calendar items.'
  - name: '**CRM integration** – Sync customer appointments from a CRM system directly
      into Outlook via PST files.'
    text: '**CRM integration** – Sync customer appointments from a CRM system directly
      into Outlook via PST files.'
  type: HowTo
- questions:
  - answer: Aspose.Email for Java
    question: Which library?
  - answer: Export Outlook calendar PST and **save calendar to PST**
    question: Primary goal?
  - answer: Java 8+, Maven, Aspose.Email license
    question: Prerequisites?
  - answer: 10‑15 minutes for a basic event
    question: Typical implementation time?
  - answer: Yes – daily, weekly, monthly, etc.
    question: Can I add recurrence?
  type: FAQPage
tags:
- export outlook calendar pst
- Aspose.Email
- Java calendar automation
title: Esporta PST del calendario Outlook con Aspose.Email – Java
url: /it/java/calendar-appointments/create-save-mapi-calendar-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Esporta PST del calendario Outlook con Aspose.Email – Java

## Introduzione

Stai cercando di semplificare l'automazione del calendario nelle tue applicazioni Java e hai bisogno di **esportare file PST del calendario Outlook**? Con **Aspose.Email for Java**, puoi **creare elementi MAPI calendar Java**, definire modelli di ricorrenza, aggiungere partecipanti e **salvare il calendario in PST** con poche righe di codice. Questo tutorial ti guida attraverso l'intero processo—dalla configurazione della libreria alla generazione di una voce di calendario completamente funzionale pronta per la distribuzione.

### Cosa imparerai
- Come **creare eventi MAPI calendar Java** usando Aspose.Email.  
- Configurare modelli di ricorrenza giornalieri, settimanali o personalizzati.  
- Aggiungere destinatari (organizzatori, partecipanti) ai tuoi inviti di calendario.  
- Persistere l'elemento del calendario mediante **salvataggio del calendario in PST** per la compatibilità con Outlook.  
- Come **automatizzare la programmazione delle riunioni** con codice riutilizzabile.

## Risposte rapide
- **Which library?** Aspose.Email for Java  
- **Primary goal?** Esportare PST del calendario Outlook e **salvare il calendario in PST**  
- **Prerequisites?** Java 8+, Maven, Aspose.Email license  
- **Typical implementation time?** 10‑15 minutes for a basic event  
- **Can I add recurrence?** Sì – giornaliera, settimanale, mensile, ecc.

## Esporta PST del calendario Outlook

In questa sezione ci concentriamo sul flusso end‑to‑end che ti consente di **esportare file PST del calendario Outlook**. Dopo aver creato l'oggetto calendario MAPI, l'ultimo passaggio è memorizzarlo all'interno di un file PST che Outlook può leggere direttamente.

## Perché usare Aspose.Email per l'automazione del calendario?

Esporta PST del calendario Outlook con Aspose.Email perché offre un metodo affidabile, lato server, per produrre elementi compatibili con Outlook senza interop COM. La libreria supporta **50+ formati di input e output**, può gestire file PST superiori a 2 GB e processa migliaia di voci di calendario al minuto su hardware server tipico. Il suo motore di ricorrenza integrato copre modelli giornalieri, settimanali, mensili e personalizzati, eliminando la necessità di calcoli manuali delle date.

## Prerequisiti

Prima di iniziare, assicurati di avere:

### Librerie richieste
- **Aspose.Email for Java**: Versione 25.4 o successiva (supporta Java 8‑21).

### Requisiti di configurazione dell'ambiente
- Un IDE Java come IntelliJ IDEA o Eclipse.  
- Maven installato per gestire le dipendenze.

### Prerequisiti di conoscenza
- Competenze di programmazione Java di base.  
- Familiarità con i concetti di programmazione orientata agli oggetti.

## Configurazione di Aspose.Email per Java

Aggiungi la dipendenza Maven di Aspose.Email al tuo `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Acquisizione della licenza

Aspose.Email offre una versione di prova gratuita, ma una licenza sblocca tutte le funzionalità:

- **Free trial**: Versione di prova gratuita: test senza limitazioni per 30 giorni.  
- **Temporary license**: Richiedi tramite [Aspose's website](https://purchase.aspose.com/temporary-license/) se hai bisogno di più tempo.  
- **Purchase**: Acquista una licenza permanente dalla [purchase page](https://purchase.aspose.com/buy).

### Inizializzazione di base

Dopo aver aggiunto la dipendenza, inizializza la libreria con il tuo file di licenza:

```java
com.aspose.email.License license = new com.aspose.email.License();
license.setLicense("path_to_your_license.lic");
```

## Guida all'implementazione

Ora che sei pronto, **creiamo MAPI calendar Java** e **salviamo il calendario in PST**.

### Crea un calendario MAPI con ricorrenza

#### Panoramica

Costruiremo un evento di calendario, applicheremo una ricorrenza giornaliera, aggiungeremo partecipanti e infine lo memorizzeremo in un file PST.

#### Implementazione passo‑a‑passo

1. **Initialize date and recurrence pattern**  

   `MapiCalendarEventRecurrence` è la classe che memorizza i dettagli della ricorrenza per un elemento di calendario.  
   `MapiCalendarDailyRecurrencePattern` definisce un semplice programma di ripetizione giornaliera.  

   Per prima cosa, definisci l'ora di inizio e imposta una ricorrenza giornaliera:

   ```java
   import java.util.Date;

   // Add hours to current date to get the start time
   Date startDate = addHours(new Date(), 12);

   MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
   recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
   ```

2. **Set up recipients**  

   `MapiRecipientCollection` rappresenta l'elenco delle persone invitate alla riunione.  
   `MAPI_TO` è il flag che contrassegna un destinatario come partecipante principale.  

   Aggiungi le persone che dovrebbero ricevere l'invito alla riunione:

   ```java
   import com.aspose.email.MapiRecipientCollection;
   import com.aspose.email.MapiRecipientType;

   MapiRecipientCollection recColl = new MapiRecipientCollection();
   recColl.add("recipient@gmail.com", "Attendee Name", MapiRecipientType.MAPI_TO);
   ```

3. **Create the MAPI calendar item**  

   La classe `MapiMessage` (usata qui come oggetto calendario) incapsula tutte le proprietà dell'evento, come organizzatore, oggetto, luogo, orari di inizio/fine, descrizione, elenco destinatari e ricorrenza.  

   Costruisci l'oggetto calendario con tutti i dettagli richiesti:

   ```java
   import com.aspose.email.MapiCalendar;

   MapiCalendar calendar = new MapiCalendar(
       "Organizer Name", 
       "Meeting Subject", 
       "Meeting Location", 
       startDate, 
       addHours(startDate, 1), // End time is one hour after start
       "Event Description",
       recColl,
       recurrence
   );
   ```

4. **Save to PST file**  

   `PersonalStorage` è l'API di livello superiore di Aspose.Email per creare e manipolare file PST.  
   `addMapiMessageItem` inserisce un messaggio MAPI (inclusi gli elementi di calendario) in una cartella specificata.  

   Infine, persisti il calendario mediante **salvataggio del calendario in PST**:

   ```java
   import com.aspose.email.PersonalStorage;
   import com.aspose.email.FolderInfo;
   import com.aspose.email.StandardIpmFolder;

   PersonalStorage pst = PersonalStorage.create("calendar.pst", 0);
   FolderInfo calendarFolder = pst.createPredefinedFolder("Calendar", StandardIpmFolder.CALendars);

   // Save the MAPI Calendar item
   calendarFolder.addMapiMessageItem(calendar);
   ```

### Suggerimenti per la risoluzione dei problemi
- Verifica il percorso della licenza; una licenza non valida limiterà le funzionalità.  
- Assicurati che gli indirizzi email dei destinatari siano formattati correttamente per evitare fallimenti negli inviti.  
- Chiudi il PST (`pst.dispose()`) dopo le operazioni per liberare i handle dei file.

## Applicazioni pratiche

Ecco scenari comuni in cui **creare MAPI calendar Java** e **salvare il calendario in PST** è particolarmente utile:

1. **Programmazione automatizzata delle riunioni** – Genera inviti ricorrenti per i team di progetto senza sforzo manuale.  
2. **Piattaforme di gestione eventi** – Esporta le sessioni delle conferenze come elementi di calendario compatibili con Outlook.  
3. **Integrazione CRM** – Sincronizza gli appuntamenti dei clienti da un sistema CRM direttamente in Outlook tramite file PST.

## Considerazioni sulle prestazioni

- **Gestione delle risorse**: rilascia gli oggetti `PersonalStorage` dopo l'uso per evitare blocchi dei file.  
- **Elaborazione batch**: per grandi volumi, elabora gli elementi del calendario in modo asincrono o a blocchi per mantenere basso l'uso della memoria.  
- **Scalabilità**: Aspose.Email può scrivere su file PST più grandi di 2 GB mantenendo il consumo di memoria sotto i 200 MB.

## Conclusione

Ora sai come **esportare PST del calendario Outlook** creando oggetti MAPI calendar Java, configurando la ricorrenza, aggiungendo partecipanti e **salvando il calendario in PST** usando Aspose.Email. Questo approccio consente alle tue applicazioni Java di automatizzare flussi di lavoro di programmazione sofisticati con compatibilità Outlook.

Per un'esplorazione più approfondita, consulta la [documentazione](https://reference.aspose.com/email/java/) ufficiale.

## Sezione FAQ

### D: Posso creare modelli di ricorrenza settimanali?
- **A**: Sì! Usa `MapiCalendarWeeklyRecurrencePattern` per definire ripetizioni settimanali.

### D: Come gestisco le eccezioni nella ricorrenza di un evento?
- **A**: Chiama `setExceptions()` sull'oggetto di ricorrenza per specificare le date che deviano dal modello.

### D: È possibile aggiornare un elemento calendario esistente?
- **A**: Assolutamente. Carica l'elemento dal PST, modifica le sue proprietà e salvalo nuovamente.

### D: Posso crittografare il file PST?
- **A**: Sì, Aspose.Email ti consente di impostare una password su `PersonalStorage` quando crei il PST.

### D: E se devo aggiungere allegati all'evento del calendario?
- **A**: Usa `calendar.getAttachments().addFileAttachment("path/to/file")` prima di salvare.

## Risorse

- [Aspose.Email Documentation](https://reference.aspose.com/email/java/)
- [Download Aspose.Email for Java](https://releases.aspose.com/email/java/)
- [Purchase a License](https://purchase.aspose.com/buy)
- [Free trial version](https://releases.aspose.com/email/java/)
- [Request a Temporary License](https://purchase.aspose.com/temporary-license/)
- [Aspose support forum](https://forum.aspose.com/c/email/10)

---

**Last updated:** 2026-09-17  
**Tested with:** Aspose.Email for Java 25.4 (JDK 16)  
**Author:** Aspose

## Tutorial correlati

- [Come creare e gestire file PST Outlook usando Aspose.Email per Java](/email/java/outlook-pst-ost-operations/aspose-email-java-manage-pst-files/)
- [Come creare file PST con Aspose.Email per Java](/email/java/email-parsing-analysis/aspose-email-java-create-pst-guide/)
- [Come creare un elemento calendario Java usando Aspose.Email](/email/java/calendar-appointments/create-save-calendar-items-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}