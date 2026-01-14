---
date: '2026-01-01'
description: Scopri come creare un calendario MAPI in Java e salvare il calendario
  in PST usando Aspose.Email per Java. Guida passo‑passo con codice, ricorrenze e
  destinatari.
keywords:
- Create MAPI Calendar Java
- Aspose.Email Java Calendar
- Java PST File Save
title: Come creare un calendario MAPI in Java con Aspose.Email – Salvare il calendario
  in PST
url: /it/java/calendar-appointments/create-save-mapi-calendar-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Come creare MAPI calendar java con Aspose.Email – Salva calendario in PST

## Introduzione

Stai cercando di semplificare l'automazione del calendario nelle tue applicazioni Java? Con **Aspose.Email for Java**, puoi **create MAPI calendar java** items, definire i pattern di ricorrenza, aggiungere partecipanti e **save calendar to PST** file con poche righe di codice. Questo tutorial ti guida attraverso l'intero processo—dalla configurazione della libreria alla generazione di una voce di calendario completamente funzionale pronta per la distribuzione.

### Cosa imparerai
- Come **create MAPI calendar java** eventi usando Aspose.Email.  
- Configare pattern di ricorrenza giornalieri, settimanali o personalizzati.  
- Aggiungere destinatari (organizzatori, partecipanti) ai tuoi inviti di calendario.  
- Persistire l'elemento del calendario tramite **save calendar to PST** per la compatibilità con Outlook.  

Iniziamo e prepariamo il tuo ambiente di sviluppo.

## Risposte rapide
- **Quale libreria?** Aspose.Email for Java  
- **Obiettivo principale?** Create MAPI calendar java e **save calendar to PST**  
- **Prerequisiti?** Java 8+, Maven, licenza Aspose.Email  
- **Tempo tipico di implementazione?** 10‑15 minuti per un evento base  
- **Posso aggiungere ricorrenza?** Sì – giornaliera, settimanale, mensile, ecc.

## Cos'è un MAPI Calendar in Java?
Un oggetto calendario MAPI (Messaging Application Programming Interface) rappresenta una riunione o un appuntamento compatibile con Outlook. Usando Aspose.Email, puoi costruire questi oggetti programmaticamente, consentendo un'integrazione fluida con Exchange, Outlook o qualsiasi client che utilizza file PST.

## Perché usare Aspose.Email per l'automazione del calendario?
- **Compatibilità completa con Outlook** – gli elementi generati funzionano in Outlook, OWA e client mobili.  
- **Supporto ricco alla ricorrenza** – pattern giornalieri, settimanali, mensili e personalizzati pronti all'uso.  
- **Nessuna dipendenza esterna** – libreria Java pura, non è necessario COM interop.  
- **Alte prestazioni** – gestione efficiente di file PST di grandi dimensioni e operazioni in batch.

## Prerequisiti

Prima di iniziare, assicurati di avere:

### Librerie richieste
- **Aspose.Email for Java**: Versione 25.4 o successiva.

### Requisiti di configurazione dell'ambiente
- Un IDE Java come IntelliJ IDEA o Eclipse.  
- Maven installato per gestire le dipendenze.

### Prerequisiti di conoscenza
- Competenze di base nella programmazione Java.  
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
- **Prova gratuita**: Test senza limitazioni per 30 giorni.  
- **Licenza temporanea**: Richiedi tramite [Aspose's website](https://purchase.aspose.com/temporary-license/) se hai bisogno di più tempo.  
- **Acquisto**: Acquista una licenza permanente dalla [purchase page](https://purchase.aspose.com/buy).

### Inizializzazione di base

Dopo aver aggiunto la dipendenza, inizializza la libreria con il tuo file di licenza:

```java
com.aspose.email.License license = new com.aspose.email.License();
license.setLicense("path_to_your_license.lic");
```

## Guida all'implementazione

Ora che sei pronto, creiamo **create MAPI calendar java** e **save calendar to PST**.

### Creare un MAPI Calendar con ricorrenza

#### Panoramica

Costruiremo un evento di calendario, applicheremo una ricorrenza giornaliera, aggiungeremo partecipanti e infine lo memorizzeremo in un file PST.

#### Implementazione passo‑a‑passo

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

*Spiegazione*: `MapiRecipientCollection` memorizza ogni partecipante; `MAPI_TO` li segna come destinatari principali.

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

*Spiegazione*: Il costruttore richiede organizzatore, oggetto, luogo, orari di inizio/fine, descrizione, elenco dei destinatari e ricorrenza.

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

*Spiegazione*: `PersonalStorage.create` genera un nuovo file PST, e `addMapiMessageItem` inserisce la voce del calendario nella cartella "Calendar".

### Suggerimenti per la risoluzione dei problemi
- Verifica il percorso della licenza; una licenza non valida limiterà le funzionalità.  
- Assicurati che gli indirizzi email dei destinatari siano formattati correttamente per evitare errori di invito.  
- Chiudi il PST (`pst.dispose()`) dopo le operazioni per liberare i handle dei file.

## Applicazioni pratiche

Ecco scenari comuni in cui **create MAPI calendar java** e **save calendar to PST** si distinguono:
1. **Programmazione automatica delle riunioni** – Genera inviti ricorrenti per i team di progetto senza sforzo manuale.  
2. **Piattaforme di gestione eventi** – Esporta le sessioni della conferenza come voci di calendario compatibili con Outlook.  
3. **Integrazione CRM** – Sincronizza gli appuntamenti dei clienti da un sistema CRM direttamente in Outlook tramite file PST.

## Considerazioni sulle prestazioni
- **Gestione delle risorse**: Disporre degli oggetti `PersonalStorage` dopo l'uso per prevenire blocchi dei file.  
- **Elaborazione batch**: Per grandi volumi, elabora le voci di calendario in modo asincrono o a blocchi per mantenere basso l'uso della memoria.

## Conclusione

Ora hai imparato come **create MAPI calendar java** oggetti, configurare la ricorrenza, aggiungere partecipanti e **save calendar to PST** usando Aspose.Email. Questo approccio consente alle tue applicazioni Java di automatizzare flussi di lavoro di pianificazione sofisticati con compatibilità Outlook.

Per approfondire, consulta la [documentazione](https://reference.aspose.com/email/java/) ufficiale.

## Sezione FAQ

### D: Posso creare pattern di ricorrenza settimanali?
- **R**: Sì! Usa `MapiCalendarWeeklyRecurrencePattern` per definire ripetizioni settimanali.

### D: Come gestisco le eccezioni nella ricorrenza dell'evento?
- **R**: Chiama `setExceptions()` sull'oggetto di ricorrenza per specificare le date che deviano dal pattern.

### D: È possibile aggiornare una voce di calendario esistente?
- **R**: Assolutamente. Carica la voce dal PST, modifica le sue proprietà e salvala nuovamente.

### D: Posso crittografare il file PST?
- **R**: Sì, Aspose.Email consente di impostare una password su `PersonalStorage` durante la creazione del PST.

### D: Cosa succede se devo aggiungere allegati all'evento del calendario?
- **R**: Usa `calendar.getAttachments().addFileAttachment("path/to/file")` prima di salvare.

## Risorse

- [Aspose.Email Documentation](https://reference.aspose.com/email/java/)
- [Download Aspose.Email for Java](https://releases.aspose.com/email/java/)
- [Purchase a License](https://purchase.aspose.com/buy)
- [Free Trial Version](https://releases.aspose.com/email/java/)
- [Request a Temporary License](https://purchase.aspose.com/temporary-license/)
- [Aspose Support Forum](https://forum.aspose.com/c/email/10)

---

**Last Updated:** 2026-01-01  
**Tested With:** Aspose.Email for Java 25.4 (JDK 16)  
**Author:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
