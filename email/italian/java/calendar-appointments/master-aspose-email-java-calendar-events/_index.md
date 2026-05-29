---
date: '2026-02-24'
description: Scopri come esportare il calendario in PST con Aspose.Email per Java,
  inclusa la possibilità di aggiungere partecipanti, impostare le date di inizio e
  fine e gestire gli appuntamenti in modo efficiente.
keywords:
- Aspose.Email Java Calendar Events
- Create Calendar Events in Java
- Manage Calendar Appointments with Java
- export calendar to pst
title: Esporta il calendario in PST con Aspose.Email per Java
url: /it/java/calendar-appointments/master-aspose-email-java-calendar-events/
weight: 1
---

.

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Esporta il calendario in PST con Aspose.Email per Java

Se stai sviluppando un'applicazione Java che deve condividere dati di pianificazione con Outlook, spesso avrai bisogno di **esportare il calendario in PST**. In questo tutorial ti guideremo passo passo su tutto ciò che ti serve — dalla creazione di un semplice appuntamento all'aggiunta dei partecipanti e, infine, alla scrittura degli eventi in un file PST, il tutto con Aspose.Email per Java.

## Risposte rapide
- **Qual è l'obiettivo principale?** Esportare gli eventi del calendario in un file PST.  
- **Quale libreria è necessaria?** Aspose.Email per Java (v25.4+).  
- **Ho bisogno di una licenza?** Sì, una licenza valida di Aspose.Email rimuove i limiti di valutazione.  
- **Posso aggiungere partecipanti?** Assolutamente – usa `MapiRecipientCollection`.  
- **Quale versione di Java è supportata?** JDK 16 o superiore.

## Che cosa significa **export calendar to pst**?
Esportare un calendario in PST significa convertire gli oggetti `MapiCalendar` presenti in memoria in una Microsoft Outlook Personal Storage Table (PST). Il file risultante può essere aperto direttamente in Outlook, condiviso con i colleghi o importato in qualsiasi sistema che comprenda il formato PST.

## Perché utilizzare Aspose.Email per Java per esportare il calendario in PST?
- **Supporto MAPI completo** – crea, modifica e salva appuntamenti senza la necessità di avere Outlook installato.  
- **Cross‑platform** – funziona su Windows, Linux e macOS.  
- **API completa** – gestisci partecipanti, ricorrenze, promemoria e altro.  
- **Ottimizzato per le prestazioni** – gestisci grandi volumi di eventi con un basso utilizzo di memoria.

## Prerequisiti
- **Librerie e dipendenze**: Aspose.Email per Java versione 25.4 o successiva.  
- **Ambiente**: JDK 16 o superiore, Maven per la gestione delle dipendenze.  
- **Conoscenze**: Programmazione Java di base e familiarità con Maven.

## Come configurare Aspose.Email per Java
Aggiungi la dipendenza Aspose.Email al tuo `pom.xml`:

```xml
<dependency>
  <groupId>com.aspose</groupId>
  <artifactId>aspose-email</artifactId>
  <version>25.4</version>
  <classifier>jdk16</classifier>
</dependency>
```

### Acquisizione della licenza
Sblocca tutte le funzionalità di Aspose.Email senza limitazioni di valutazione ottenendo una licenza:

1. **Free Trial**: Visita la [pagina di download di Aspose](https://releases.aspose.com/email/java/) per una licenza temporanea.  
2. **Temporary License**: Richiedi tramite la [pagina di acquisto](https://purchase.aspose.com/temporary-license/).  
3. **Purchase License**: Considera l’acquisto dal [portale di acquisto di Aspose](https://purchase.aspose.com/buy) per un utilizzo a lungo termine.

Una volta ottenuta la licenza, inizializzala nella tua applicazione per abilitare tutte le funzionalità.

## Come **creare un appuntamento** (Create Calendar Event Java)

### Passo 1: Definisci le date di inizio e fine (java calendar start date / java calendar end date)
Il metodo seguente mostra come impostare le date di inizio e fine per un appuntamento e restituire un oggetto `MapiCalendar`:

```java
import com.aspose.email.MapiCalendar;
import java.util.Calendar;
import java.util.Date;

public MapiCalendar createAppointment() {
    Calendar cal = Calendar.getInstance();
    
    // Setting the start date
    cal.set(Calendar.YEAR, 2023);
    cal.set(Calendar.MONTH, Calendar.OCTOBER);
    cal.set(Calendar.DAY_OF_MONTH, 1);
    Date startDate = cal.getTime();
    
    // Setting the end date
    cal.set(Calendar.HOUR_OF_DAY, 10);
    Date endDate = cal.getTime();
    
    return new MapiCalendar("Conference Room", "Important Meeting",
        "Discuss project milestones and updates.", startDate, endDate);
}
```

*Spiegazione*: Questo snippet crea un `MapiCalendar` con una posizione specifica, oggetto, descrizione e le **java calendar start date** / **java calendar end date** che hai definito.

## Come **aggiungere partecipanti** (java add meeting attendees)

### Passo 2: Costruisci la lista dei partecipanti
Usa `MapiRecipientCollection` per specificare chi deve ricevere l’invito alla riunione:

```java
import com.aspose.email.MapiCalendar;
import com.aspose.email.MapiRecipientCollection;
import com.aspose.email.MapiRecipientType;
import java.util.Date;

public MapiCalendar createMeetingWithAttendees(Date startDate, Date endDate) {
    MapiRecipientCollection attendees = new MapiRecipientCollection();
    
    // Adding primary recipients
    attendees.add("attendee1@example.com", "John Doe", MapiRecipientType.MAPI_TO);
    attendees.add("attendee2@example.com", "Jane Smith", MapiRecipientType.MAPI_TO);
    
    return new MapiCalendar(
        "Main Office Boardroom",
        "Team Meeting",
        "Discuss quarterly goals.",
        startDate,
        endDate,
        "organizer@example.com",
        attendees
    );
}
```

*Spiegazione*: Questo codice crea una riunione, imposta l’organizzatore e allega la lista **java add meeting attendees** in modo che tutti ricevano un invito corretto.

## Come **esportare il calendario in pst** (Create PST with calendar events)

### Passo 3: Crea un file PST e aggiungi gli eventi
Il metodo qui sotto dimostra come creare un file PST Unicode e memorizzare sia l’appuntamento semplice sia la riunione con i partecipanti:

```java
import com.aspose.email.FileFormatVersion;
import com.aspose.email.FolderInfo;
import com.aspose.email.PersonalStorage;
import com.aspose.email.StandardIpmFolder;

public void createPSTWithCalendarEvents() {
    String pstFilePath = "/path/to/output/MapiCalendarToPST_out.pst";
    
    PersonalStorage pst = PersonalStorage.create(pstFilePath, FileFormatVersion.Unicode);
    FolderInfo calendarFolder = pst.createPredefinedFolder("Calendar", StandardIpmFolder.Appointments);

    MapiCalendar appointment = createAppointment();
    calendarFolder.addMapiMessageItem(appointment);
    
    Date startDate = new Date(); // Use actual dates from your event
    Date endDate = new Date();
    MapiCalendar meeting = createMeetingWithAttendees(startDate, endDate);
    calendarFolder.addMapiMessageItem(meeting);
}
```

*Spiegazione*: Questo snippet **esporta il calendario in PST** creando un contenitore PST, aggiungendo una cartella predefinita “Calendar” e inserendo gli oggetti `MapiCalendar` precedentemente costruiti.

## Applicazioni pratiche
1. **Pianificazione aziendale** – Automatizza la creazione e la distribuzione di riunioni interne.  
2. **Gestione eventi** – Tieni traccia di conferenze, workshop e liste dei partecipanti.  
3. **Integrazione CRM** – Sincronizza gli appuntamenti con gli strumenti di gestione delle relazioni con i clienti.  
4. **Pianificazione progetti** – Archivia le tappe del progetto come elementi del calendario.  
5. **Collaborazione di team remoti** – Genera file PST per la condivisione offline.

## Considerazioni sulle prestazioni
- **Dispose gli oggetti** che non ti servono più per liberare memoria.  
- **Scegli collezioni efficienti** per liste di partecipanti di grandi dimensioni.  
- **Cache gli eventi frequentemente accessibili** se interroghi il PST più volte.

## Problemi comuni e soluzioni
| Problema | Soluzione |
|----------|-----------|
| **File PST non creato** | Verifica i permessi di scrittura sulla directory di destinazione e assicurati che il percorso della cartella esista. |
| **I partecipanti non ricevono gli inviti** | Conferma che ogni `MapiRecipient` utilizzi `MapiRecipientType.MAPI_TO` e che l'email dell'organizzatore sia valida. |
| **Discrepanza di data** | Usa `Calendar` in modo coerente per le date di inizio/fine; evita di mescolare `java.util.Date` con altre librerie di data senza conversione. |

## Domande frequenti

**D: Come posso iniziare con Aspose.Email per Java?**  
R: Aggiungi la dipendenza Maven mostrata sopra, ottieni una licenza e segui i passaggi di questa guida per creare ed esportare eventi del calendario.

**D: Posso personalizzare il nome e il percorso del file PST?**  
R: Sì, modifica la variabile `pstFilePath` in `createPSTWithCalendarEvents()` con qualsiasi percorso valido sul tuo sistema.

**D: È possibile aggiungere schemi di ricorrenza agli appuntamenti?**  
R: Assolutamente – `MapiCalendar` espone proprietà di ricorrenza come `RecurrencePattern` che puoi configurare prima di salvare.

**D: Aspose.Email supporta altri formati di calendario oltre al PST?**  
R: Sì, puoi esportare in iCalendar (`.ics`) e altri formati usando i metodi API appropriati.

**D: Qual è la dimensione massima di un file PST che posso creare?**  
R: Con il formato Unicode (`FileFormatVersion.Unicode`), i file PST possono crescere fino a 2 TB, limitati solo dallo spazio disco disponibile.

---

**Ultimo aggiornamento:** 2026-02-24  
**Testato con:** Aspose.Email per Java 25.4 (jdk16 classifier)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}