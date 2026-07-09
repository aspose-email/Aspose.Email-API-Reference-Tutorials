---
date: '2026-03-20'
description: Scopri come esportare il PST del calendario di Outlook usando Aspose.Email
  per Java – crea elementi di calendario MAPI, imposta la ricorrenza, aggiungi i partecipanti
  e salva in PST.
keywords:
- Create MAPI Calendar Java
- Aspose.Email Java Calendar
- Java PST File Save
title: Esporta il calendario PST di Outlook con Aspose.Email – Java
url: /it/java/calendar-appointments/create-save-mapi-calendar-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Esporta PST del calendario Outlook con Aspose.Email – Java

## Introduzione

Stai cercando di semplificare l'automazione del calendario nelle tue applicazioni Java e hai bisogno di **esportare PST del calendario Outlook**? Con **Aspose.Email for Java**, puoi **creare MAPI calendar Java** items, definire pattern di ricorrenza, aggiungere partecipanti e **salvare il calendario in PST** con poche righe di codice. Questo tutorial ti guida attraverso l'intero processo—dalla configurazione della libreria alla generazione di una voce di calendario completamente funzionale pronta per la distribuzione.

### Cosa imparerai
- Come **creare MAPI calendar Java** eventi usando Aspose.Email.  
- Configurare pattern di ricorrenza giornalieri, settimanali o personalizzati.  
- Aggiungere destinatari (organizzatori, partecipanti) ai tuoi inviti di calendario.  
- Persistere l'elemento del calendario tramite **salvare il calendario in PST** per la compatibilità con Outlook.  
- Come **automatizzare la programmazione delle riunioni** con codice riutilizzabile.

## Risposte rapide
- **Which library?** Aspose.Email for Java  
- **Primary goal?** Esportare PST del calendario Outlook e **salvare il calendario in PST**  
- **Prerequisites?** Java 8+, Maven, Aspose.Email license  
- **Typical implementation time?** 10‑15 minuti per un evento base  
- **Can I add recurrence?** Sì – giornaliera, settimanale, mensile, ecc.

## Esporta PST del calendario Outlook

In questa sezione ci concentriamo sul flusso end‑to‑end che ti consente di **esportare PST del calendario Outlook**. Dopo aver creato l'oggetto MAPI calendar, l'ultimo passaggio è memorizzarlo all'interno di un file PST che Outlook può leggere direttamente.

## Perché utilizzare Aspose.Email per l'automazione del calendario?

- **Compatibilità completa con Outlook** – gli elementi generati funzionano in Outlook, OWA e client mobili.  
- **Supporto ricco alle ricorrenze** – pattern giornalieri, settimanali, mensili e personalizzati pronti all'uso.  
- **Nessuna dipendenza esterna** – libreria Java pura, non è necessario interop COM.  
- **Alte prestazioni** – gestione efficiente di grandi file PST e operazioni in batch.  
- **Automatizzare la programmazione delle riunioni** – incorpora questa logica in job batch o servizi web per creare centinaia di inviti automaticamente.

## Prerequisiti

Prima di iniziare, assicurati di avere:

### Librerie richieste
- **Aspose.Email for Java**: Version 25.4 or later.

### Requisiti di configurazione dell'ambiente
- A Java IDE such as IntelliJ IDEA or Eclipse.  
- Maven installed to manage dependencies.

### Prerequisiti di conoscenza
- Competenze di base nella programmazione Java.  
- Familiarità con i concetti di programmazione orientata agli oggetti.

## Configurazione di Aspose.Email per Java

Add the Aspose.Email Maven dependency to your `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Acquisizione della licenza

Aspose.Email offre una prova gratuita, ma una licenza sblocca tutte le funzionalità:

- **Prova gratuita**: Test senza limitazioni per 30 giorni.  
- **Licenza temporanea**: Richiedi tramite [Aspose's website](https://purchase.aspose.com/temporary-license/) se hai bisogno di più tempo.  
- **Acquisto**: Acquista una licenza permanente dalla [pagina di acquisto](https://purchase.aspose.com/buy).

### Inizializzazione di base

After adding the dependency, initialize the library with your license file:

```java
com.aspose.email.License license = new com.aspose.email.License();
license.setLicense("path_to_your_license.lic");
```

## Guida all'implementazione

Now that you’re set up, let’s **create MAPI calendar Java** and **save calendar to PST**.

### Crea un MAPI Calendar con ricorrenza

#### Panoramica

We'll build a calendar event, apply a daily recurrence, add attendees, and finally store it in a PST file.

#### Implementazione passo‑passo

1. **Initialize Date and Recurrence Pattern**  

   First, define the start time and set a daily recurrence:

   ```java
   import java.util.Date;

   // Add hours to current date to get the start time
   Date startDate = addHours(new Date(), 12);

   MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
   recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
   ```

   *Spiegazione*: `MapiCalendarEventRecurrence` contiene i dettagli della ricorrenza; scegliamo un pattern giornaliero tramite `MapiCalendarDailyRecurrencePattern`.

2. **Set Up Recipients**  

   Add the people who should receive the meeting invitation:

   ```java
   import com.aspose.email.MapiRecipientCollection;
   import com.aspose.email.MapiRecipientType;

   MapiRecipientCollection recColl = new MapiRecipientCollection();
   recColl.add("recipient@gmail.com", "Attendee Name", MapiRecipientType.MAPI_TO);
   ```

   *Spiegazione*: `MapiRecipientCollection` memorizza ogni partecipante; `MAPI_TO` li contrassegna come destinatari principali.

3. **Create the MAPI Calendar Item**  

   Build the calendar object with all required details:

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

   *Spiegazione*: Il costruttore richiede organizzatore, oggetto, posizione, orari di inizio/fine, descrizione, elenco dei destinatari e ricorrenza.

4. **Save to PST File**  

   Finally, persist the calendar by **saving calendar to PST**:

   ```java
   import com.aspose.email.PersonalStorage;
   import com.aspose.email.FolderInfo;
   import com.aspose.email.StandardIpmFolder;

   PersonalStorage pst = PersonalStorage.create("calendar.pst", 0);
   FolderInfo calendarFolder = pst.createPredefinedFolder("Calendar", StandardIpmFolder.CALendars);

   // Save the MAPI Calendar item
   calendarFolder.addMapiMessageItem(calendar);
   ```

   *Spiegazione*: `PersonalStorage.create` genera un nuovo file PST e `addMapiMessageItem` inserisce la voce del calendario nella cartella "Calendar".

### Suggerimenti per la risoluzione dei problemi
- Verifica il percorso della licenza; una licenza non valida limiterà le funzionalità.  
- Assicurati che gli indirizzi email dei destinatari siano formattati correttamente per evitare errori di invito.  
- Chiudi il PST (`pst.dispose()`) dopo le operazioni per liberare i handle dei file.

## Applicazioni pratiche

Here are common scenarios where **creating MAPI calendar Java** and **saving calendar to PST** shines:

1. **Programmazione automatica delle riunioni** – Genera inviti ricorrenti per i team di progetto senza sforzo manuale.  
2. **Piattaforme di gestione eventi** – Esporta le sessioni della conferenza come voci di calendario compatibili con Outlook.  
3. **Integrazione CRM** – Sincronizza gli appuntamenti dei clienti da un sistema CRM direttamente in Outlook tramite file PST.

## Considerazioni sulle prestazioni

- **Gestione delle risorse**: Disporre degli oggetti `PersonalStorage` dopo l'uso per prevenire blocchi dei file.  
- **Elaborazione batch**: Per grandi volumi, elabora le voci di calendario in modo asincrono o a blocchi per mantenere basso l'uso della memoria.  

## Conclusione

You’ve now learned how to **export Outlook calendar PST** by creating MAPI calendar Java objects, configuring recurrence, adding attendees, and **saving calendar to PST** using Aspose.Email. This approach empowers your Java applications to automate sophisticated scheduling workflows with Outlook compatibility.

For deeper exploration, check the official [documentation](https://reference.aspose.com/email/java/).

## Sezione FAQ

### Q: Posso creare pattern di ricorrenza settimanali?
- **R**: Sì! Usa `MapiCalendarWeeklyRecurrencePattern` per definire ripetizioni settimanali.

### Q: Come gestisco le eccezioni nella ricorrenza dell'evento?
- **R**: Chiama `setExceptions()` sull'oggetto di ricorrenza per specificare le date che deviano dal pattern.

### Q: È possibile aggiornare una voce di calendario esistente?
- **R**: Assolutamente. Carica la voce dal PST, modifica le sue proprietà e salvala nuovamente.

### Q: Posso criptare il file PST?
- **R**: Sì, Aspose.Email consente di impostare una password su `PersonalStorage` durante la creazione del PST.

### Q: Cosa succede se devo aggiungere allegati all'evento del calendario?
- **R**: Usa `calendar.getAttachments().addFileAttachment("path/to/file")` prima di salvare.

## Risorse

- [Aspose.Email Documentation](https://reference.aspose.com/email/java/)
- [Download Aspose.Email for Java](https://releases.aspose.com/email/java/)
- [Purchase a License](https://purchase.aspose.com/buy)
- [Free Trial Version](https://releases.aspose.com/email/java/)
- [Request a Temporary License](https://purchase.aspose.com/temporary-license/)
- [Aspose Support Forum](https://forum.aspose.com/c/email/10)

---

**Last Updated:** 2026-03-20  
**Tested With:** Aspose.Email for Java 25.4 (JDK 16)  
**Author:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}