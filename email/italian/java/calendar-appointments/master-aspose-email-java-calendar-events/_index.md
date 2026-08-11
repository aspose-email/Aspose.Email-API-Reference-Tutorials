---
date: '2026-08-01'
description: Scopri come esportare il calendario in PST con Aspose.Email for Java,
  inclusi i passaggi per aggiungere partecipanti, impostare le date di inizio e fine
  e gestire gli appuntamenti in modo efficiente.
keywords:
- export calendar to pst
- export recurring appointments
- Aspose.Email Java Calendar Events
lastmod: '2026-08-01'
og_description: Esporta il calendario in PST usando Aspose.Email for Java. Scopri
  passo dopo passo come creare appuntamenti, aggiungere partecipanti e generare file
  Outlook PST.
og_image_alt: 'Developer guide: Export calendar to PST using Aspose.Email for Java'
og_title: Esporta il calendario in PST – Guida completa con Aspose.Email for Java
schemas:
- author: Aspose
  dateModified: '2026-08-01'
  description: Learn how to export calendar to PST with Aspose.Email for Java, including
    how to add attendees, set start and end dates, and manage appointments efficiently.
  headline: Export calendar to PST with Aspose.Email for Java
  type: TechArticle
- description: Learn how to export calendar to PST with Aspose.Email for Java, including
    how to add attendees, set start and end dates, and manage appointments efficiently.
  name: Export calendar to PST with Aspose.Email for Java
  steps:
  - name: '**Free Trial**: Visit the [Aspose download page](https://releases.aspose.com/email/java/)
      for a temporary license.'
    text: '**Free Trial**: Visit the [Aspose download page](https://releases.aspose.com/email/java/)
      for a temporary license.'
  - name: '**Temporary License**: Apply via the [purchase page](https://purchase.aspose.com/temporary-license/).'
    text: '**Temporary License**: Apply via the [purchase page](https://purchase.aspose.com/temporary-license/).'
  - name: '**Purchase License**: Consider purchasing from [Aspose''s purchase portal](https://purchase.aspose.com/buy)
      for long‑term use.'
    text: '**Purchase License**: Consider purchasing from [Aspose''s purchase portal](https://purchase.aspose.com/buy)
      for long‑term use.'
  - name: '**Business Scheduling** – Automate internal meeting creation and distribution.'
    text: '**Business Scheduling** – Automate internal meeting creation and distribution.'
  - name: '**Event Management** – Track conferences, workshops, and participant lists.'
    text: '**Event Management** – Track conferences, workshops, and participant lists.'
  - name: '**CRM Integration** – Sync appointments with customer relationship tools.'
    text: '**CRM Integration** – Sync appointments with customer relationship tools.'
  - name: '**Project Planning** – Store project milestones as calendar items.'
    text: '**Project Planning** – Store project milestones as calendar items.'
  - name: '**Remote Team Collaboration** – Generate PST files for offline sharing.'
    text: '**Remote Team Collaboration** – Generate PST files for offline sharing.'
  type: HowTo
- questions:
  - answer: Add the Maven dependency shown above, obtain a license, and follow the
      steps in this guide to create and export calendar events.
    question: How do I get started with Aspose.Email for Java?
  - answer: Yes, change the `pstFilePath` variable in `createPSTWithCalendarEvents()`
      to any valid path on your system.
    question: Can I customize the PST file name and location?
  - answer: Absolutely – `MapiCalendar` exposes a `RecurrencePattern` property that
      you can configure before saving.
    question: Is it possible to add recurrence patterns to appointments?
  - answer: Yes, you can export to iCalendar (`.ics`) and other formats using the
      appropriate API methods.
    question: Does Aspose.Email support other calendar formats besides PST?
  - answer: With the Unicode format (`FileFormatVersion.Unicode`), PST files can grow
      up to 2 TB, limited only by available disk space.
    question: What is the maximum size of a PST file I can create?
  type: FAQPage
tags:
- export calendar to pst
- Aspose.Email
- Java calendar appointments
title: Esporta il calendario in PST con Aspose.Email for Java
url: /it/java/calendar-appointments/master-aspose-email-java-calendar-events/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Esporta il calendario in PST con Aspose.Email per Java

Se stai sviluppando un'applicazione Java che deve condividere dati di pianificazione con Outlook, spesso avrai bisogno di **esportare il calendario in PST**. In questo tutorial ti guideremo passo passo attraverso tutto ciò che ti serve — dalla creazione di un semplice appuntamento all'aggiunta dei partecipanti e, infine, alla scrittura degli eventi in un file PST, il tutto con Aspose.Email per Java. Alla fine avrai una soluzione pronta per la produzione che funziona su Windows, Linux e macOS.

## Risposte rapide
- **Qual è l'obiettivo principale?** Esportare gli eventi del calendario in un file PST.  
- **Quale libreria è necessaria?** Aspose.Email per Java (v25.4+).  
- **È necessaria una licenza?** Sì, una licenza valida di Aspose.Email rimuove i limiti di valutazione.  
- **Posso aggiungere partecipanti?** Assolutamente sì – usa `MapiRecipientCollection`.  
- **Quale versione di Java è supportata?** JDK 16 o superiore.

## Cos'è **export calendar to pst**?
`MapiCalendar` è la classe di Aspose.Email che modella un elemento di calendario di Outlook, includendo oggetto, luogo e dettagli temporali.

Esportare un calendario in PST significa convertire gli oggetti `MapiCalendar` in memoria in una Microsoft Outlook Personal Storage Table (PST). Il file PST generato può essere aperto direttamente in Outlook, condiviso con colleghi o importato in qualsiasi sistema che comprenda il formato PST, preservando tutti i dettagli dell'evento come partecipanti, ricorrenze e promemoria.

## Perché usare Aspose.Email per Java per esportare il calendario in PST?
Puoi generare un file PST completamente compatibile senza installare Outlook. Aspose.Email fornisce **supporto MAPI completo**, funziona su **tutti i principali sistemi operativi** e può gestire **fino a 2 TB** di dati nel formato Unicode PST — sufficiente per archivi a livello enterprise. L'API consente inoltre di gestire partecipanti, pattern di ricorrenza, promemoria e proprietà personalizzate con poche chiamate di metodo, riducendo drasticamente lo sforzo di sviluppo.

## Prerequisiti
- **Librerie e dipendenze**: Aspose.Email per Java versione 25.4 o successiva.  
- **Ambiente**: JDK 16 o superiore, Maven per la gestione delle dipendenze.  
- **Conoscenze**: Programmazione Java di base e familiarità con Maven.

## Come configurare Aspose.Email per Java
Aggiungi la dipendenza Aspose.Email al tuo `pom.xml` e aggiorna il progetto Maven. Questo unico passaggio rende disponibile l'intera API MAPI nel tuo classpath.

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

### Acquisizione della licenza
Sblocca tutte le funzionalità di Aspose.Email senza limitazioni di valutazione ottenendo una licenza:

1. **Prova gratuita**: visita la [pagina di download di Aspose](https://releases.aspose.com/email/java/) per una licenza temporanea.  
2. **Licenza temporanea**: richiedila tramite la [pagina di acquisto](https://purchase.aspose.com/temporary-license/).  
3. **Acquisto della licenza**: considera l'acquisto dal [portale di acquisto di Aspose](https://purchase.aspose.com/buy) per un utilizzo a lungo termine.

Una volta ottenuta la licenza, inizializzala nella tua applicazione per abilitare tutte le funzionalità.

## Come **creare appuntamento** (Create Calendar Event Java)

Carica un oggetto `MapiCalendar`, imposta le sue proprietà principali e restituiscilo pronto per ulteriori elaborazioni. Questo metodo crea una voce di calendario con oggetto, luogo, descrizione e le **date di inizio e fine del calendario Java** che hai definito.

```java
public static MapiCalendar createAppointment(String subject, String location,
                                             String description, Calendar start, Calendar end) {
    MapiCalendar appointment = new MapiCalendar();
    appointment.setSubject(subject);
    appointment.setLocation(location);
    appointment.setBody(description);
    appointment.setStartDate(start);
    appointment.setEndDate(end);
    return appointment;
}
```

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

*Spiegazione*: la classe `MapiCalendar` è la rappresentazione di Aspose.Email di un elemento di calendario di Outlook. Dopo aver impostato i campi di base, puoi anche configurare ricorrenze, promemoria e categorie prima del salvataggio.

## Come **aggiungere partecipanti** (java add meeting attendees)

Crea una `MapiRecipientCollection`, popolala con ogni partecipante e allegala alla riunione. Questo garantisce che ogni partecipante riceva un invito corretto quando il PST viene aperto.

`MapiRecipientCollection` è una classe di collezione che contiene oggetti `MapiRecipient` che rappresentano i partecipanti alla riunione. `MapiRecipient` rappresenta un singolo partecipante con proprietà come indirizzo email e tipo di destinatario.

```java
public static MapiRecipientCollection buildAttendees(List<String> emails) {
    MapiRecipientCollection attendees = new MapiRecipientCollection();
    for (String email : emails) {
        MapiRecipient recipient = new MapiRecipient(email, email, MapiRecipientType.MAPI_TO);
        attendees.add(recipient);
    }
    return attendees;
}
```

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

*Spiegazione*: `MapiRecipient` definisce un singolo partecipante alla riunione. Impostare il tipo su `MAPI_TO` contrassegna l'indirizzo come partecipante principale, mentre `MAPI_CC` o `MAPI_BCC` possono essere usati per partecipanti opzionali.

## Come **esportare il calendario in pst** (Create PST with calendar events)

Crea un file PST Unicode, aggiungi una cartella "Calendar" e inserisci gli oggetti `MapiCalendar` precedentemente costruiti. Il PST può quindi essere aperto in Outlook o distribuito agli utenti finali.

`PersonalStorage` è la classe di Aspose.Email usata per creare, aprire e manipolare file PST.

```java
public static void createPSTWithCalendarEvents(String pstFilePath,
                                                List<MapiCalendar> events) throws Exception {
    // Create a new Unicode PST (supports up to 2 TB)
    PersonalStorage pst = PersonalStorage.create(pstFilePath, FileFormatVersion.Unicode);
    // Add the default Calendar folder
    FolderInfo calendarFolder = pst.getRootFolder().addSubFolder("Calendar", 
                                   StandardIpmFolder.Calendar);
    // Insert each event
    for (MapiCalendar event : events) {
        calendarFolder.addMapiMessageItem(event);
    }
}
```

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

*Spiegazione*: `PersonalStorage` è il punto di ingresso per la manipolazione dei PST. Utilizzando il formato Unicode eviti il limite di 2 GB delle versioni PST più vecchie e benefici di I/O più veloce su archivi di grandi dimensioni.

## Applicazioni pratiche
1. **Pianificazione aziendale** – Automatizza la creazione e distribuzione di riunioni interne.  
2. **Gestione eventi** – Traccia conferenze, workshop e liste dei partecipanti.  
3. **Integrazione CRM** – Sincronizza gli appuntamenti con gli strumenti di gestione delle relazioni con i clienti.  
4. **Pianificazione di progetto** – Archivia le tappe del progetto come elementi di calendario.  
5. **Collaborazione di team remoti** – Genera file PST per la condivisione offline.

## Considerazioni sulle prestazioni
- **Elimina gli oggetti** che non ti servono più per liberare memoria tempestivamente.  
- **Usa collezioni efficienti** (ad es., `ArrayList` per le liste dei partecipanti) quando gestisci migliaia di partecipanti.  
- **Metti in cache gli eventi** frequentemente accessi se interroghi il PST più volte, riducendo I/O su disco.

## Problemi comuni e soluzioni
| Problema | Soluzione |
|----------|-----------|
| **File PST non creato** | Verifica i permessi di scrittura sulla directory di destinazione e assicurati che il percorso della cartella esista. |
| **I partecipanti non ricevono gli inviti** | Conferma che ogni `MapiRecipient` utilizzi `MapiRecipientType.MAPI_TO` e che l'email dell'organizzatore sia valida. |
| **Discrepanza di data** | Usa `Calendar` in modo coerente per le date di inizio/fine; evita di mescolare `java.util.Date` con altre librerie di data senza conversione. |

## Domande frequenti

**D: Come posso iniziare con Aspose.Email per Java?**  
R: Aggiungi la dipendenza Maven mostrata sopra, ottieni una licenza e segui i passaggi di questa guida per creare ed esportare eventi di calendario.

**D: Posso personalizzare il nome e la posizione del file PST?**  
R: Sì, modifica la variabile `pstFilePath` in `createPSTWithCalendarEvents()` con qualsiasi percorso valido sul tuo sistema.

**D: È possibile aggiungere pattern di ricorrenza agli appuntamenti?**  
R: Assolutamente – `MapiCalendar` espone una proprietà `RecurrencePattern` che puoi configurare prima del salvataggio.

**D: Aspose.Email supporta altri formati di calendario oltre al PST?**  
R: Sì, puoi esportare in iCalendar (`.ics`) e altri formati usando i metodi API appropriati.

**D: Qual è la dimensione massima di un file PST che posso creare?**  
R: Con il formato Unicode (`FileFormatVersion.Unicode`), i file PST possono crescere fino a 2 TB, limitati solo dallo spazio disponibile su disco.

---

**Ultimo aggiornamento:** 2026-08-01  
**Testato con:** Aspose.Email per Java 25.4 (classificatore jdk16)  
**Autore:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial correlati

- [Master Aspose.Email per Java: Gestisci efficientemente i file PST di Outlook](/email/java/outlook-pst-ost-operations/aspose-email-java-manage-outlook-pst-files/)
- [Master Creazione e Salvataggio di Elementi di Calendario con Aspose.Email per Java](/email/java/calendar-appointments/create-save-calendar-items-aspose-email-java/)
- [Come leggere più eventi di calendario da un file ICS usando Aspose.Email in Java](/email/java/calendar-appointments/read-multiple-ics-events-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}