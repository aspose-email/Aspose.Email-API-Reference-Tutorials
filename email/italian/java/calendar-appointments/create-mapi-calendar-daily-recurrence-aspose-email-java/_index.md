---
date: '2026-03-20'
description: Scopri come creare un calendario Outlook in Java con ricorrenza giornaliera
  ed eccezioni e salvare il calendario in PST usando Aspose.Email per Java.
keywords:
- MAPI Calendar creation
- daily recurrence events
- Java calendar exceptions
title: Crea calendario Outlook in Java con ricorrenza giornaliera ed eccezioni
url: /it/java/calendar-appointments/create-mapi-calendar-daily-recurrence-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Come creare outlook calendar java con ricorrenza giornaliera ed eccezioni

Gestire eventi ricorrenti in modo efficiente può essere difficile, soprattutto quando ti serve un **outlook calendar java** che supporti schemi di ricorrenza giornaliera ed eccezioni occasionali. In questo tutorial imparerai a creare oggetti Outlook calendar Java, configurare la ricorrenza giornaliera, aggiungere istanze di eccezione e infine **save calendar to PST** usando Aspose.Email for Java. Alla fine avrai uno snippet di codice riutilizzabile da inserire in qualsiasi servizio di pianificazione basato su Java.

## Risposte rapide
- **Quale libreria?** Aspose.Email for Java  
- **Attività principale?** Create an Outlook calendar Java with daily recurrence and exceptions  
- **JDK prerequisito?** Java 16 or higher  
- **Posso allegare file alle eccezioni?** Yes, using `MapiCalendarExceptionInfo`  
- **Dove è archiviato il calendario?** In a PST file via `PersonalStorage`

## Cos'è un Outlook calendar java?
Un oggetto Outlook calendar Java (implementato come un calendario MAPI) segue gli stessi standard degli appuntamenti di Microsoft Outlook. Memorizza regole di ricorrenza avanzate, gestione delle eccezioni, partecipanti e allegati, rendendolo perfetto per la pianificazione a livello aziendale.

## Perché usare Aspose.Email per Java?
Aspose.Email fornisce un'API pure‑Java che consente di lavorare con oggetti MAPI senza la necessità di installare Outlook. Questo approccio **aspose email tutorial java** permette la generazione lato server di file PST, serie di riunioni automatizzate e il pieno controllo della logica di ricorrenza.

## Prerequisiti

Prima di iniziare, assicurati di avere la seguente configurazione:

- **Aspose.Email Library**: Versione 25.4 (or later) – available via Maven or direct download.  
- **Java Development Kit (JDK)**: JDK 16 or newer.  
- **IDE**: IntelliJ IDEA, Eclipse, NetBeans or any Java‑compatible editor.

### Librerie e dipendenze richieste

Per integrare Aspose.Email nel tuo progetto usando Maven, aggiungi la seguente dipendenza al tuo `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Ottenimento della licenza

Per utilizzare Aspose.Email, è necessaria una licenza:

- **Free Trial** – esplora tutte le funzionalità gratuitamente.  
- **Temporary License** – richiedi per una valutazione estesa.  
- **Full License** – acquista per l'uso in produzione.

## Configurazione di Aspose.Email per Java

Prima, configura il tuo ambiente:

1. Verifica che JDK 16 sia installato e che `JAVA_HOME` sia configurato.  
2. Aggiungi la dipendenza Maven (or download the JAR) to your project.  

Ecco un piccolo snippet che mostra come caricare un file di licenza:

```java
import com.aspose.email.*;

public class InitializeAspose {
    public static void main(String[] args) {
        // Set up a license if available
        License license = new License();
        try {
            license.setLicense("path/to/your/license.lic");
        } catch (Exception e) {
            System.out.println("License not found, using trial version.");
        }
    }
}
```

## Guida all'implementazione

### Creazione di Outlook calendar java con ricorrenza giornaliera ed eccezioni

#### Panoramica
Questa funzionalità ti consente di automatizzare appuntamenti ricorrenti mantenendo la possibilità di saltare o modificare istanze specifiche.

#### Implementazione passo‑passo

**1. Imposta la data di inizio dell'evento**  
Determina quando dovrebbe iniziare la serie:

```java
Date startDate = addHours(newDate(2018, 7, 19), 12);
```

**2. Crea l'oggetto MAPI Calendar**  
Fornisci luogo, oggetto e descrizione:

```java
MapiCalendar calendar = new MapiCalendar("location1", "summary1", "description1", startDate, addHours(startDate, 1));
```

**3. Definisci un modello di ricorrenza giornaliera**  
Configura l'evento per ripetersi ogni giorno:

```java
MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
MapiCalendarRecurrencePattern pattern = recurrence.getRecurrencePattern();

pattern.setPatternType(MapiCalendarRecurrencePatternType.Day);
pattern.setPeriod(1); // Daily
pattern.setEndType(MapiCalendarRecurrenceEndType.NeverEnd);
```

**4. Aggiungi un'eccezione alla ricorrenza**  
Specifica una data da escludere (or altered):

```java
Date exceptionDate = addDays(startDate, 3);

MapiCalendarExceptionInfo exception = new MapiCalendarExceptionInfo();
exception.setLocation("exceptionLocation");
exception.setSubject("exceptionSubject");
exception.setBody("exceptionBody");

exception.setOriginalStartDate(exceptionDate);
exception.setStartDateTime(exceptionDate);
exception.setEndDateTime(addHours(exceptionDate, 5));

pattern.getExceptions().addItem(exception);
pattern.getModifiedInstanceDates().addItem(exceptionDate);
pattern.getDeletedInstanceDates().addItem(exceptionDate);

calendar.setRecurrence(recurrence);
```

### Allegare file alle eccezioni del calendario

#### Panoramica
Puoi allegare documenti di supporto (ad es., agenda) a qualsiasi istanza di eccezione.

**1. Crea e allega un file**

```java
MapiCalendarExceptionInfo exception = new MapiCalendarExceptionInfo();
exception.getAttachments().add("file.txt", "hello, world!".getBytes());
```

### Salvataggio di Outlook calendar java in PST (save calendar to pst)

#### Panoramica
Persisti il calendario in un file PST affinché Outlook o altri client possano leggerlo.

**1. Crea e salva il calendario in PST**

```java
final PersonalStorage pst = PersonalStorage.create(new ByteArrayOutputStream(), FileFormatVersion.Unicode);
try {
    FolderInfo calendarFolder = pst.createPredefinedFolder("Calendar", StandardIpmFolder.Appointments);
    calendarFolder.addMapiMessageItem(calendar);
} finally {
    pst.dispose();
}
```

## Applicazioni pratiche
- **Corporate Scheduling** – automatizza serie di riunioni, saltando automaticamente le festività.  
- **Project Management** – traccia traguardi ricorrenti con occasionali spostamenti di data.  
- **Event Planning** – gestisci conferenze plurigiorno dove alcune sessioni sono cancellate o riprogrammate.

### Possibilità di integrazione
Combina Aspose.Email con piattaforme CRM, API di gestione attività o motori di workflow personalizzati per guidare l'automazione end‑to‑end.

## Considerazioni sulle prestazioni
- **Dispose Resources** – chiama sempre `dispose()` su `PersonalStorage` per liberare i handle dei file.  
- **Stream Usage** – preferisci `ByteArrayOutputStream` o stream di file per evitare di caricare interi PST in memoria.  
- **Async Operations** – per la generazione di calendari in blocco, esegui la logica di creazione su un thread in background per mantenere l'interfaccia reattiva.

## Conclusione
Seguendo questa guida ora sai come **create outlook calendar java** oggetti con ricorrenza giornaliera, aggiungere eccezioni, allegare file e **save calendar to PST**. Queste capacità ti permettono di costruire funzionalità di pianificazione robuste senza mai toccare direttamente Outlook.

### Prossimi passi
- Sperimenta con schemi di ricorrenza settimanali o mensili.  
- Esplora proprietà MAPI aggiuntive come partecipanti, promemoria e categorie.  
- Rivedi la documentazione completa dell'API di Aspose.Email per scenari più avanzati.

## Domande frequenti

**Q: La libreria supporta appuntamenti sensibili al fuso orario?**  
A: Sì, puoi impostare le proprietà `StartTimeZone` e `EndTimeZone` su `MapiCalendar`.

**Q: Posso eliminare programmaticamente una singola occorrenza da una serie ricorrente?**  
A: Usa la collezione `DeletedInstanceDates` sul modello di ricorrenza per contrassegnare date specifiche come rimosse.

**Q: Ci sono limiti sulla dimensione di un file PST creato con Aspose.Email?**  
A: I file PST seguono i limiti del formato Unicode (fino a 2 GB per impostazione predefinita), ma è possibile configurare dimensioni maggiori tramite le impostazioni di `PersonalStorage`.

**Q: Come aggiungo partecipanti a una richiesta di riunione?**  
A: Crea oggetti `MapiRecipient`, imposta il loro `RecipientType` a `MapiRecipientType.MAPI_TO` e aggiungili alla collezione `Recipients` di `MapiMessage`.

**Q: È supportato il ricorrere di attività (non solo appuntamenti)?**  
A: Sì, Aspose.Email fornisce anche `MapiTask` con capacità di ricorrenza simili.

**Q: Posso usare questa guida come parte di una serie di aspose email tutorial java?**  
A: Assolutamente – i passaggi mostrati qui sono una parte fondamentale di qualsiasi tutorial Aspose.Email Java che tratta la creazione di calendari.

## Risorse
- [Documentazione Aspose.Email per Java](https://reference.aspose.com/email/java/)
- [Scarica Aspose.Email](https://releases.aspose.com/email/java/)
- [Acquista una licenza](https://purchase.aspose.com/buy)
- [Versione di prova gratuita](https://releases.aspose.com/email/java/)
- [Richiedi licenza temporanea](https://purchase.aspose.com/temporary-license/)
- [Forum di supporto Aspose](https://forum.aspose.com/c/email/10)

---

**Ultimo aggiornamento:** 2026-03-20  
**Testato con:** Aspose.Email for Java 25.4 (JDK 16)  
**Autore:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}