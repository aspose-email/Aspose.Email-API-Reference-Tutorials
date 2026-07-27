---
date: '2026-07-27'
description: Scopri come impostare il flag Outlook in Java usando Aspose.Email per
  Java, coprendo la creazione del flag, i flag dei destinatari, il completamento,
  la rimozione e le opzioni di lettura.
keywords:
- set outlook flag java
- outlook follow up flag java
- aspose email java
lastmod: '2026-07-27'
og_description: Imposta il flag Outlook in Java con Aspose.Email per Java. Questa
  guida mostra come creare, leggere, completare e rimuovere i flag di follow‑up di
  Outlook in modo efficiente.
og_image_alt: 'Developer guide: Set Outlook flag Java using Aspose.Email'
og_title: Imposta flag Outlook Java – Guida completa di programmazione Aspose.Email
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Learn how to set outlook flag java using Aspose.Email for Java, covering
    flag creation, recipient flags, completion, removal, and reading options.
  headline: Set Outlook Flag Java – Complete Aspose.Email Programming Guide
  type: TechArticle
- description: Learn how to set outlook flag java using Aspose.Email for Java, covering
    flag creation, recipient flags, completion, removal, and reading options.
  name: Set Outlook Flag Java – Complete Aspose.Email Programming Guide
  steps:
  - name: Create and Initialize the Message
    text: '`MailMessage` is Aspose.Email’s high‑level class that represents an email.
      After you build the message, you convert it to a `MapiMessage` for flag manipulation.
      *We first build a `MailMessage`, set sender/recipient, then convert it to a
      `MapiMessage` for flag manipulation.*'
  - name: Define Follow‑Up Dates (Outlook Flag Reminder)
    text: '`FollowUpOptions` holds the start, reminder, and due dates. Use Java’s
      `Calendar` to set precise timestamps. *Here we set the start, reminder (the
      **outlook flag reminder**), and due dates using the `Calendar` class.*'
  - name: Apply Follow‑Up Options
    text: The `FollowUpManager.setOptions` method attaches the flag to the `MapiMessage`.
      *The `FollowUpOptions` object holds all flag details, which we apply with `FollowUpManager.setOptions`.*
  - name: Save the Message
    text: Save the flagged message as a `.msg` file so Outlook can display the flag.
      *The message is saved as a `.msg` file with the flag attached.*
  - name: Mark as Draft
    text: '`MessageFlags` is a MAPI enumeration that controls the state of the message.
      Setting `MSGFLAG_UNSENT` tells Outlook the item is a draft. *Marking the message
      as unsent ensures Outlook treats it as a draft.*'
  - name: Set Recipient Flag
    text: '`FollowUpManager.setFlagForRecipients` attaches the flag exclusively to
      the recipient’s copy. *The flag is now visible only to the recipients – a classic
      **flag for recipients** scenario.*'
  - name: Load the Message
    text: '`MapiMessage` can read a saved `.msg` file, giving you full access to its
      MAPI properties.'
  - name: Mark as Completed and Save
    text: '`FollowUpManager.completeFlag` updates the flag status, after which you
      persist the changes. *The flag status changes to “Completed” and the updated
      file is saved.*'
  - name: Load and Clear Flag
    text: '`FollowUpManager.clearFlag` removes all flag‑related properties from the
      message. *The message is saved without any follow‑up flag.*'
  - name: Retrieve Options
    text: The returned `options` object gives you full visibility into the flag’s
      configuration. *The `options` object now contains start, due, and reminder dates,
      plus the flag subject – useful when you need to **read flag options** for reporting.*
  type: HowTo
- questions:
  - answer: It’s a pure‑Java API that lets you create, read, and manipulate email
      files (MSG, EML, etc.) without needing Outlook installed.
    question: What is Aspose.Email for Java?
  - answer: Visit the [Aspose website](https://releases.aspose.com/email/java/) to
      download a 30‑day trial.
    question: How do I obtain a free trial license?
  - answer: Outlook supports only one flag per message, but you can store additional
      task data in custom MAPI properties.
    question: Can I set multiple follow‑up flags on a single message?
  - answer: Confirm the `outputDir` path is valid and that the application has permission
      to write to that location.
    question: My message isn’t saved after setting a flag. What should I check?
  - answer: Loop through your message collection and call `FollowUpManager.clearFlag`
      on each `MapiMessage`.
    question: How can I remove flags from many messages at once?
  type: FAQPage
tags:
- outlook flag
- aspose.email
- java email automation
title: Imposta flag Outlook Java – Guida completa di programmazione Aspose.Email
url: /it/java/calendar-appointments/aspose-email-java-outlook-follow-up-flags/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Imposta Flag Outlook Java usando Aspose.Email per Java

## Introduzione
Se hai bisogno di **impostare flag outlook java** programmaticamente, sei nel posto giusto. Il flag di follow‑up di Outlook trasforma una normale email in un’attività tracciata, e Aspose.Email per Java ti consente di gestire questi flag senza avere Outlook installato. In questo tutorial vedremo come creare, leggere, completare e infine rimuovere i flag, oltre a come applicarli a destinatari specifici. Alla fine avrai uno snippet Java riutilizzabile che automatizza il tracciamento delle attività direttamente dai tuoi servizi backend.

## Risposte Rapide
- **Cosa significa “impostare flag outlook java”?** Aggiungere un flag con data di inizio, promemoria e scadenza a un elemento Outlook tramite codice Java.  
- **Quale libreria è necessaria?** Aspose.Email per Java (v25.4 o successiva).  
- **È necessaria una licenza?** Sì – una versione di prova funziona per la valutazione, ma è richiesta una licenza acquistata per la produzione.  
- **Posso impostare flag solo per i destinatari?** Assolutamente sì – usa `FollowUpManager.setFlagForRecipients`.  
- **È possibile rimuovere un flag in seguito?** Sì – chiama `FollowUpManager.clearFlag`.

## Cos'è un Flag di Follow Up di Outlook?
Il flag di follow‑up di Outlook è un marcatore di attività integrato che può associare una data di inizio, un promemoria e una data di scadenza a qualsiasi elemento di posta. Trasforma un’email in un’attività tracciata, aiutando te e il tuo team a tenere sotto controllo il lavoro in sospeso.

## Perché usare Aspose.Email per Java?
Aspose.Email per Java supporta **oltre 70 formati di email** (inclusi MSG, EML, MHTML e TNEF) e può elaborare **oltre 100.000 messaggi al minuto** su un tipico server a 8 core, il tutto senza richiedere Outlook sulla macchina host. Questo lo rende ideale per l’automazione backend, la generazione di report di conformità e l’integrazione con strumenti di gestione progetti.

## Prerequisiti
- **Aspose.Email per Java** versione 25.4 o successiva.  
- **JDK 16+** installato.  
- IDE compatibile con Maven (IntelliJ IDEA, Eclipse, ecc.).  
- Conoscenze di base di Java e familiarità con i concetti di email.

## Configurazione di Aspose.Email per Java
### Configurazione Maven
Aggiungi la seguente dipendenza al tuo `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Acquisizione della Licenza
Aspose.Email richiede una licenza per l’uso in produzione:

- **Versione di prova gratuita** – valutazione di 30 giorni.  
- **Licenza temporanea** – test esteso.  
- **Licenza completa** – abbonamento perpetuo.

Inizializza la licenza prima di qualsiasi operazione email:

```java
License license = new License();
license.setLicense("path/to/Aspose.Total.Java.lic");
```

## Imposta Flag Outlook Java (Funzione 1)
### Risposta Diretta
Carica un `MailMessage`, convertilo in un `MapiMessage`, configura `FollowUpOptions` e chiama `FollowUpManager.setOptions`. Questa sequenza crea un elemento Outlook completamente flaggato in poche righe di codice Java.

### Passo 1: Creare e Inizializzare il Messaggio
`MailMessage` è la classe di alto livello di Aspose.Email che rappresenta un’email. Dopo aver costruito il messaggio, lo converti in un `MapiMessage` per la manipolazione del flag.

```java
MailMessage mailMsg = new MailMessage();
mailMsg.setSender(new MailAddress("AETest12@gmail.com"));
mailMsg.getTo().addMailAddress(new MailAddress("receiver@gmail.com"));
mailMsg.setBody("This message will test if follow up options can be added to a new mapi message.");
MapiMessage mapi = MapiMessage.fromMailMessage(mailMsg);
```
*Costruiamo prima un `MailMessage`, impostiamo mittente/destinatario, quindi lo convertiamo in un `MapiMessage` per la manipolazione del flag.*

### Passo 2: Definire le Date di Follow‑Up (Promemoria del Flag Outlook)
`FollowUpOptions` contiene le date di inizio, promemoria e scadenza. Usa `Calendar` di Java per impostare timestamp precisi.

```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 14, 40, 0);
Date dtStartDate = calendar.getTime();
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
calendar.add(Calendar.DATE, 1);
Date dtDueDate = calendar.getTime();
```
*Qui impostiamo la data di inizio, il promemoria (il **promemoria del flag outlook**) e la data di scadenza usando la classe `Calendar`.*

### Passo 3: Applicare le Opzioni di Follow‑Up
Il metodo `FollowUpManager.setOptions` allega il flag al `MapiMessage`.  

```java
FollowUpOptions options = new FollowUpOptions("Follow Up", dtStartDate, dtDueDate, dtReminderDate);
FollowUpManager.setOptions(mapi, options);
```
*L’oggetto `FollowUpOptions` contiene tutti i dettagli del flag, che applichiamo con `FollowUpManager.setOptions`.*

### Passo 4: Salvare il Messaggio
Salva il messaggio flaggato come file `.msg` affinché Outlook possa visualizzare il flag.

```java
mapi.save(outputDir + "SetFollowUpflag_out.msg");
```
*Il messaggio viene salvato come file `.msg` con il flag allegato.*

## Come Impostare il Flag per i Destinatari (Funzione 2)?
Usa `FollowUpManager.setFlagForRecipients` dopo aver contrassegnato il messaggio come bozza. Questo metodo aggiunge il flag di follow‑up solo alla copia del destinatario, lasciando invariata la visualizzazione del mittente. È necessario impostare `MessageFlags.MSGFLAG_UNSENT` prima di applicare il flag. Puoi anche personalizzare le date di inizio, promemoria e scadenza usando un oggetto `FollowUpOptions` prima di chiamare il metodo.

### Risposta Diretta
Contrassegna il messaggio come bozza usando `MessageFlags.MSGFLAG_UNSENT`, quindi chiama `FollowUpManager.setFlagForRecipients`. Outlook mostrerà il flag solo ai destinatari, non al mittente.

### Panoramica
A volte è necessario che il flag appaia **solo per i destinatari**. Questo esempio contrassegna prima il messaggio come bozza, poi aggiunge il flag.

#### Passo 1: Contrassegnare come Bozza
`MessageFlags` è un’enumerazione MAPI che controlla lo stato del messaggio. Impostare `MSGFLAG_UNSENT` indica a Outlook che l’elemento è una bozza.

```java
mapi.setMessageFlags(MapiMessageFlags.MSGFLAG_UNSENT);
```
*Contrassegnare il messaggio come non inviato garantisce che Outlook lo tratti come bozza.*

#### Passo 2: Impostare il Flag per il Destinatario
`FollowUpManager.setFlagForRecipients` allega il flag esclusivamente alla copia del destinatario.

```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
FollowUpManager.setFlagForRecipients(mapi, "Follow up", dtReminderDate);
```
*Il flag è ora visibile solo ai destinatari – uno scenario classico di **flag per destinatari**.*

## Come Segnare un Flag di Follow Up di Outlook come Completato (Funzione 3)?
Carica il file .msg in un `MapiMessage`, quindi chiama `FollowUpManager.completeFlag`. Questo aggiorna lo stato del flag a Completato e aggiunge un segno di spunta in Outlook. Dopo il completamento, salva il messaggio per rendere persistente la modifica. Puoi anche impostare l’ora di completamento modificando la proprietà `FlagCompleteTime` se necessario per scopi di audit.

### Risposta Diretta
Carica il file `.msg` esistente in un `MapiMessage`, chiama `FollowUpManager.completeFlag` e salva il file. Lo stato del flag cambia in “Completato” e appare con un segno di spunta in Outlook.

### Passo 1: Caricare il Messaggio
`MapiMessage` può leggere un file `.msg` salvato, fornendoti pieno accesso alle sue proprietà MAPI.

```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
```

### Passo 2: Segnare come Completato e Salvare
`FollowUpManager.completeFlag` aggiorna lo stato del flag, dopodiché persisti le modifiche.

```java
FollowUpManager.markAsCompleted(mapi);
mapi.save(outputDir + "MarkedCompleted_out.msg");
```
*Lo stato del flag cambia in “Completed” e il file aggiornato viene salvato.*

## Come Rimuovere un Flag di Follow Up di Outlook (Funzione 4)?
Apri il file .msg con `MapiMessage`, invoca `FollowUpManager.clearFlag` e poi salva il messaggio. Questo rimuove tutte le proprietà MAPI correlate al flag, così Outlook non mostrerà più alcun indicatore di follow‑up. Usa questa procedura quando un’attività è annullata o non più rilevante. Assicurati anche di cancellare eventuali proprietà di promemoria personalizzate per evitare notifiche residue.

### Risposta Diretta
Apri il file `.msg` con `MapiMessage`, invoca `FollowUpManager.clearFlag` e salva il file. Il messaggio non mostrerà più alcun indicatore di follow‑up in Outlook.

### Passo 1: Caricare e Rimuovere il Flag
`FollowUpManager.clearFlag` elimina tutte le proprietà correlate al flag dal messaggio.

```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpManager.clearFlag(mapi);
mapi.save(outputDir + "FollowUpFlagRemoved_out.msg");
```
*Il messaggio viene salvato senza alcun flag di follow‑up.*

## Come Leggere le Opzioni del Flag (Funzione 5)?
Chiama `FollowUpManager.getOptions` su un `MapiMessage` caricato per ottenere un oggetto `FollowUpOptions`. Questo oggetto fornisce le date di inizio, scadenza, promemoria e l’oggetto del flag, consentendoti di visualizzare o registrare i dettagli del flag. È utile per reportistica e audit di conformità.

### Risposta Diretta
Usa `FollowUpManager.getOptions` su un `MapiMessage` caricato per recuperare un oggetto `FollowUpOptions` contenente le date di inizio, scadenza, promemoria e l’oggetto del flag. Questo è utile per la reportistica o gli audit di conformità.

### Passo 1: Recuperare le Opzioni
L’oggetto `options` restituito ti offre piena visibilità sulla configurazione del flag.

```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpOptions options = FollowUpManager.getOptions(mapi);
```
*L’oggetto `options` ora contiene le date di inizio, scadenza e promemoria, più l’oggetto del flag – utile quando devi **leggere le opzioni del flag** per la reportistica.*

## Applicazioni Pratiche
- **Integrazione con Gestione Attività:** Sincronizza le email flaggate con Jira, Trello o Azure Boards.  
- **Promemoria Automatici:** Genera email di promemoria giornaliere per i follow‑up in sospeso.  
- **Audit di Conformità:** Esporta i dati dei flag per la reportistica normativa, sfruttando la possibilità di leggere le opzioni del flag programmaticamente.

## Considerazioni sulle Prestazioni
- **Calcoli delle Date:** Calcola le date una sola volta per batch anziché all’interno dei cicli.  
- **Gestione delle Risorse:** Chiudi tutti gli stream o handle di file dopo aver salvato i messaggi.  
- **Utilizzo della Memoria:** Elabora le cassette di posta di grandi dimensioni a blocchi per evitare pressione sull’heap; Aspose.Email può gestire cassette con centinaia di pagine senza caricare l’intero file in memoria.

## Problemi Comuni e Soluzioni
| Problema | Causa | Soluzione |
|----------|-------|-----------|
| Il flag non appare in Outlook | Messaggio salvato senza i `MessageFlags` corretti | Assicurati che `setMessageFlags` sia impostato a `MSGFLAG_UNSENT` prima di applicare i flag per i destinatari. |
| Salvataggio genera `AccessDeniedException` | Percorso file errato o permessi di scrittura insufficienti | Verifica che la directory di output esista e che l’applicazione abbia i diritti di scrittura. |
| Le date sono sfasate di un giorno | Discrepanza di fuso orario | Usa `TimeZone.getTimeZone("GMT")` o il tuo fuso locale in modo coerente. |

## Domande Frequenti
**D: Cos’è Aspose.Email per Java?**  
R: È un’API pure‑Java che consente di creare, leggere e manipolare file email (MSG, EML, ecc.) senza la necessità di Outlook installato.

**D: Come posso ottenere una licenza di prova gratuita?**  
R: Visita il [sito Aspose](https://releases.aspose.com/email/java/) per scaricare una prova di 30 giorni.

**D: Posso impostare più flag di follow‑up su un singolo messaggio?**  
R: Outlook supporta un solo flag per messaggio, ma è possibile memorizzare dati aggiuntivi di attività in proprietà MAPI personalizzate.

**D: Il mio messaggio non viene salvato dopo aver impostato un flag. Cosa devo controllare?**  
R: Verifica che il percorso `outputDir` sia valido e che l’applicazione abbia i permessi di scrittura nella directory indicata.

**D: Come posso rimuovere i flag da molti messaggi contemporaneamente?**  
R: Scorri la tua collezione di messaggi e chiama `FollowUpManager.clearFlag` su ciascun `MapiMessage`.

## Risorse
- [Documentazione](https://reference.aspose.com/email/java/)
- [Download Aspose.Email per Java](https://releases.aspose.com/email/java/)
- [Prova Gratuita Aspose.Email](https://purchase.aspose.com/purchase/free-trial/aspose-email-java)

---

**Ultimo Aggiornamento:** 2026-07-27  
**Testato Con:** Aspose.Email per Java 25.4 (JDK 16)  
**Autore:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial Correlati

- [Gestisci le Categorie di Outlook con Aspose.Email per Java - Guida Completa](/email/java/calendar-appointments/manage-outlook-categories-aspose-email-java/)
- [Crea note Outlook in Java con Aspose.Email – Guida Completa](/email/java/calendar-appointments/create-customize-outlook-notes-aspose-email-java/)
- [Crea Attività in Microsoft Exchange Usando Aspose.Email per Java: Guida Completa](/email/java/exchange-server-integration/create-tasks-exchange-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}