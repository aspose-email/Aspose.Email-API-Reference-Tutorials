---
date: '2026-09-17'
description: Scopri come creare un calendario Outlook in Java con ricorrenza giornaliera
  ed eccezioni e salvare il calendario in PST utilizzando Aspose.Email per Java.
keywords:
- create outlook calendar
- outlook calendar daily recurrence
- java calendar exceptions
- Aspose.Email Java
- MAPI PST generation
lastmod: '2026-09-17'
og_description: Crea un calendario Outlook in Java usando Aspose.Email. Scopri la
  ricorrenza giornaliera, la gestione delle eccezioni e il salvataggio in PST in una
  guida passo‑passo.
og_image_alt: Code example creating Outlook calendar with recurrence and PST export
  using Aspose.Email for Java
og_title: Crea un calendario Outlook in Java con ricorrenza giornaliera ed eccezioni
schemas:
- author: Aspose
  dateModified: '2026-09-17'
  description: Learn how to create outlook calendar java with daily recurrence and
    exceptions, and save calendar to PST using Aspose.Email for Java.
  headline: Create outlook calendar java with daily recurrence and exceptions
  type: TechArticle
- questions:
  - answer: Yes, you can set the `StartTimeZone` and `EndTimeZone` properties on `MapiCalendar`.
    question: Does the library support time‑zone aware appointments?
  - answer: Use the `DeletedInstanceDates` collection on the recurrence pattern to
      mark specific dates as removed.
    question: Can I programmatically delete a single occurrence from a recurring series?
  - answer: PST files follow the Unicode format limits (up to 2 GB by default), but
      you can configure larger sizes via `PersonalStorage` settings.
    question: Are there limits on the size of a PST file created with Aspose.Email?
  - answer: Create `MapiRecipient` objects, set their `RecipientType` to `MapiRecipientType.MAPI_TO`,
      and add them to the `Recipients` collection of the `MapiMessage`.
    question: How do I add attendees to a meeting request?
  - answer: Yes, Aspose.Email also provides `MapiTask` with similar recurrence capabilities.
    question: Is there support for recurring tasks (not just appointments)?
  type: FAQPage
tags:
- outlook calendar
- Aspose.Email
- Java scheduling
- PST file
title: Crea un calendario Outlook in Java con ricorrenza giornaliera ed eccezioni
url: /it/java/calendar-appointments/create-mapi-calendar-daily-recurrence-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea Outlook calendar Java con ricorrenza giornaliera ed eccezioni

Gestire eventi ricorrenti in modo efficiente può essere difficile, soprattutto quando hai bisogno di un **outlook calendar java** che supporti modelli di ricorrenza giornaliera ed eccezioni occasionali. In questo tutorial imparerai a creare oggetti Outlook calendar Java, configurare la ricorrenza giornaliera, aggiungere istanze di eccezione e infine **save calendar to PST** usando Aspose.Email per Java. Alla fine avrai uno snippet di codice riutilizzabile da inserire in qualsiasi servizio di pianificazione basato su Java.

## Risposte rapide
- **Quale libreria?** Aspose.Email for Java  
- **Compito principale?** Crea un Outlook calendar Java con ricorrenza giornaliera ed eccezioni  
- **JDK prerequisito?** Java 16 o superiore  
- **Posso allegare file alle eccezioni?** Sì, usando `MapiCalendarExceptionInfo`  
- **Dove è memorizzato il calendario?** In un file PST tramite `PersonalStorage`  

## Cos'è un Outlook calendar java?
Un oggetto Outlook calendar Java è una rappresentazione programmatica di un appuntamento Outlook, costruita sulla specifica MAPI (Messaging Application Programming Interface), che include proprietà come oggetto, posizione, orari di inizio/fine, regole di ricorrenza, partecipanti e allegati. Questo oggetto può essere manipolato, serializzato e memorizzato in file PST senza richiedere Outlook.

## Perché usare Aspose.Email per Java?
Aspose.Email for Java ti consente di lavorare con oggetti MAPI senza installare Outlook. La libreria supporta **50+ MAPI properties**, può generare file PST Unicode fino a **2 GB** in meno di **2 secondi** per dati tipici di appuntamenti, e funziona su qualsiasi piattaforma che supporti Java 16+. Questo approccio pure‑Java consente la creazione di calendari lato server, serie di riunioni automatizzate e il pieno controllo della logica di ricorrenza.

## Prerequisiti

Prima di iniziare, assicurati di avere la seguente configurazione:
- **Libreria Aspose.Email**: Versione 25.4 (o successiva) – disponibile via Maven o download diretto.  
- **Java Development Kit (JDK)**: JDK 16 o più recente.  
- **IDE**: IntelliJ IDEA, Eclipse, NetBeans, o qualsiasi editor compatibile con Java.

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

### Acquisizione della licenza

Per usare Aspose.Email, avrai bisogno di una licenza:
- **Prova gratuita** – esplora tutte le funzionalità senza costi.  
- **Licenza temporanea** – richiedi per una valutazione estesa.  
- **Licenza completa** – acquista per distribuzioni in produzione.

## Configurazione di Aspose.Email per Java

Prima, configura il tuo ambiente:

1. Verifica che JDK 16 sia installato e che `JAVA_HOME` sia configurato.  
2. Aggiungi la dipendenza Maven (o scarica il JAR) al tuo progetto.  

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

### Creazione di Outlook calendar Java con ricorrenza giornaliera ed eccezioni

#### Panoramica
Questa funzionalità ti consente di automatizzare appuntamenti ricorrenti mantenendo la possibilità di saltare o modificare istanze specifiche.

#### Implementazione passo‑passo

**1. Imposta la data di inizio dell'evento**  
Determina quando la serie dovrebbe iniziare:

```java
Date startDate = addHours(newDate(2018, 7, 19), 12);
```

**2. Crea l'oggetto calendario MAPI**  
La classe `MapiCalendar` è l'oggetto di livello superiore che rappresenta un singolo elemento di calendario in memoria. Fornisci posizione, oggetto e descrizione:

```java
MapiCalendar calendar = new MapiCalendar("location1", "summary1", "description1", startDate, addHours(startDate, 1));
```

**3. Definisci un modello di ricorrenza giornaliera**  
La classe `MapiCalendarRecurrencePattern` memorizza la regola che ripete l'appuntamento ogni giorno. Configura l'evento per ripetersi ogni giorno:

```java
MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
MapiCalendarRecurrencePattern pattern = recurrence.getRecurrencePattern();

pattern.setPatternType(MapiCalendarRecurrencePatternType.Day);
pattern.setPeriod(1); // Daily
pattern.setEndType(MapiCalendarRecurrenceEndType.NeverEnd);
```

**4. Aggiungi un'eccezione alla ricorrenza**  
`MapiCalendarExceptionInfo` descrive una singola occorrenza che devia dal modello—sia esclusa sia modificata. Specifica una data da escludere (o modificare):

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
Puoi allegare documenti di supporto (ad esempio, agenda) a qualsiasi istanza di eccezione.

**1. Crea e allega un file**

```java
MapiCalendarExceptionInfo exception = new MapiCalendarExceptionInfo();
exception.getAttachments().add("file.txt", "hello, world!".getBytes());
```

## Salvataggio di Outlook calendar Java in PST (save calendar to pst)

#### Panoramica
Persisti il calendario in un file PST affinché Outlook o altri client possano leggerlo.

**1. Crea e salva il calendario in PST**  
La classe `PersonalStorage` fornisce metodi per creare un nuovo file PST e aggiungere elementi MAPI.

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
- **Pianificazione aziendale** – automatizza serie di riunioni, saltando automaticamente le festività.  
- **Gestione progetti** – traccia traguardi ricorrenti con occasionali spostamenti di data.  
- **Organizzazione eventi** – gestisci conferenze multi‑giorno dove alcune sessioni sono cancellate o riprogrammate.

### Possibilità di integrazione
Combina Aspose.Email con piattaforme CRM, API di gestione attività o motori di workflow personalizzati per guidare l'automazione end‑to‑end.

## Considerazioni sulle prestazioni
- **Rilascia le risorse** – chiama sempre `dispose()` su `PersonalStorage` per liberare i handle dei file.  
- **Uso degli stream** – preferisci `ByteArrayOutputStream` o stream di file per evitare di caricare interi PST in memoria.  
- **Operazioni asincrone** – per la generazione di calendari in blocco, esegui la logica di creazione su un thread in background per mantenere l'interfaccia reattiva.

## Conclusione
Seguendo questa guida ora sai come **create outlook calendar java** oggetti con ricorrenza giornaliera, aggiungere eccezioni, allegare file e **save calendar to PST**. Queste capacità ti permettono di costruire funzionalità di pianificazione robuste senza mai toccare direttamente Outlook.

### Prossimi passi
- Sperimenta con modelli di ricorrenza settimanale o mensile.  
- Esplora ulteriori proprietà MAPI come partecipanti, promemoria e categorie.  
- Consulta la documentazione API completa di Aspose.Email per scenari più avanzati.

## Domande frequenti

**D: La libreria supporta appuntamenti con fuso orario?**  
R: Sì, puoi impostare le proprietà `StartTimeZone` e `EndTimeZone` su `MapiCalendar`.

**D: Posso eliminare programmaticamente una singola occorrenza da una serie ricorrente?**  
R: Usa la collezione `DeletedInstanceDates` sul modello di ricorrenza per contrassegnare date specifiche come rimosse.

**D: Ci sono limiti alla dimensione di un file PST creato con Aspose.Email?**  
R: I file PST seguono i limiti del formato Unicode (fino a 2 GB per impostazione predefinita), ma è possibile configurare dimensioni maggiori tramite le impostazioni di `PersonalStorage`.

**D: Come aggiungo partecipanti a una richiesta di riunione?**  
R: Crea oggetti `MapiRecipient`, imposta il loro `RecipientType` a `MapiRecipientType.MAPI_TO` e aggiungili alla collezione `Recipients` del `MapiMessage`.

**D: È supportato il ricorrere di attività (non solo appuntamenti)?**  
R: Sì, Aspose.Email fornisce anche `MapiTask` con capacità di ricorrenza simili.

**D: Posso usare questa guida come parte di una serie di tutorial Java di Aspose.Email?**  
R: Assolutamente – i passaggi mostrati qui sono una parte fondamentale di qualsiasi tutorial Java di Aspose.Email che tratta la creazione di calendari.

## Risorse
- [Documentazione Aspose.Email per Java](https://reference.aspose.com/email/java/)
- [Download Aspose.Email](https://releases.aspose.com/email/java/)
- [Acquista una licenza](https://purchase.aspose.com/buy)
- [Versione di prova gratuita](https://releases.aspose.com/email/java/)
- [Richiedi licenza temporanea](https://purchase.aspose.com/temporary-license/)
- [Forum di supporto Aspose](https://forum.aspose.com/c/email/10)

---

**Ultimo aggiornamento:** 2026-09-17  
**Testato con:** Aspose.Email for Java 25.4 (JDK 16)  
**Autore:** Aspose

## Tutorial correlati

- [Esporta PST del calendario Outlook con Aspose.Email – Java](/email/java/calendar-appointments/create-save-mapi-calendar-aspose-email-java/)
- [Come creare un elemento calendario Java usando Aspose.Email](/email/java/calendar-appointments/create-save-calendar-items-aspose-email-java/)
- [Crea invito di condivisione calendario con Aspose.Email per Java](/email/java/calendar-appointments/create-send-calendar-invitations-aspose-email-java/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}