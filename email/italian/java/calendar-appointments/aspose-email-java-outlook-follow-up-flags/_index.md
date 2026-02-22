---
date: '2026-02-22'
description: Impara a impostare un flag di follow‑up in Outlook usando Aspose.Email
  per Java, inclusa l’impostazione, la lettura e la rimozione dei flag per i destinatari.
keywords:
- Manage Outlook follow-up flags
- Set follow-up flags in Outlook with Aspose.Email for Java
- Integrate email task management with Aspose.Email
title: Come impostare il flag di follow‑up di Outlook usando Aspose.Email per Java
url: /it/java/calendar-appointments/aspose-email-java-outlook-follow-up-flags/
weight: 1
---

 So: "# Come impostare il Outlook Follow Up Flag usando Aspose.Email per Java". That keeps term.

Proceed.

Now produce final answer.{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Come impostare il Outlook Follow Up Flag usando Aspose.Email per Java

## Introduzione
Se hai mai faticato a tenere traccia delle email importanti, sai quanto sia prezioso il **outlook follow up flag** di Outlook. In questa guida mostreremo **how to set an outlook follow up flag** in modo programmatico con Aspose.Email per Java, e tratteremo anche come **set outlook follow up flag for recipients**, oltre a come **remove an outlook follow up flag** quando un’attività è terminata. Alla fine, sarai in grado di automatizzare il tracciamento delle attività, i promemoria e le tracce di audit direttamente dal tuo codice Java.

**What you’ll learn**
- Creare e applicare un flag di follow‑up a un messaggio Outlook.  
- Impostare flag di follow‑up per destinatari specifici.  
- Contrassegnare un flag come completato e rimuoverlo successivamente.  
- Leggere le opzioni del flag per report o conformità.  

Prepariamo l’ambiente prima di immergerci nel codice.

## Risposte rapide
- **What does “how to set follow‑up” mean?** Aggiungere un flag con data di inizio, promemoria e data di scadenza a un elemento Outlook.  
- **Which library is required?** Aspose.Email for Java (v25.4 o più recente).  
- **Do I need a license?** Sì, è necessaria una licenza di prova o acquistata per la piena funzionalità.  
- **Can I set flags for recipients only?** Assolutamente – usa `FollowUpManager.setFlagForRecipients`.  
- **Is it possible to remove a flag later?** Sì, chiama `FollowUpManager.clearFlag`.

## Che cos’è un Outlook Follow Up Flag?
Un Outlook follow up flag è un marcatore di attività integrato che può allegare una data di inizio, un promemoria e una data di scadenza a qualsiasi elemento di posta. Trasforma un’email normale in un’attività tracciata, aiutando te e il tuo team a rimanere al passo con il lavoro in sospeso.

## Perché usare Aspose.Email per Java?
Aspose.Email fornisce un’API pure‑Java che funziona senza la necessità di Outlook installato, consentendo di manipolare file .msg, impostare flag e gestire attività su qualsiasi piattaforma—perfetto per **automate outlook tasks**, servizi backend o integrazioni con strumenti di project‑management.

## Prerequisiti
- **Aspose.Email for Java** versione 25.4 o successiva (conosciuta anche come **aspose email java**).  
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

### Acquisizione della licenza
Aspose.Email richiede una licenza per l’uso in produzione:

- **Free trial** – valutazione di 30 giorni.  
- **Temporary license** – test esteso.  
- **Full license** – abbonamento perpetuo.

Inizializza la licenza prima di qualsiasi operazione email:

```java
License license = new License();
license.setLicense("path/to/Aspose.Total.Java.lic");
```

## Impostare il Outlook Follow Up Flag (Feature 1)
### Passo 1: Creare e inizializzare il messaggio
```java
MailMessage mailMsg = new MailMessage();
mailMsg.setSender(new MailAddress("AETest12@gmail.com"));
mailMsg.getTo().addMailAddress(new MailAddress("receiver@gmail.com"));
mailMsg.setBody("This message will test if follow up options can be added to a new mapi message.");
MapiMessage mapi = MapiMessage.fromMailMessage(mailMsg);
```
*Costruiamo prima un `MailMessage`, impostiamo mittente/destinatario, poi lo convertiamo in un `MapiMessage` per la manipolazione del flag.*

### Passo 2: Definire le date di follow‑up (Outlook Flag Reminder)
```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 14, 40, 0);
Date dtStartDate = calendar.getTime();
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
calendar.add(Calendar.DATE, 1);
Date dtDueDate = calendar.getTime();
```
*Qui impostiamo la data di inizio, il promemoria (il **outlook flag reminder**) e la data di scadenza usando la classe `Calendar`.*

### Passo 3: Applicare le opzioni di follow‑up
```java
FollowUpOptions options = new FollowUpOptions("Follow Up", dtStartDate, dtDueDate, dtReminderDate);
FollowUpManager.setOptions(mapi, options);
```
*L’oggetto `FollowUpOptions` contiene tutti i dettagli del flag, che applichiamo con `FollowUpManager.setOptions`.*

### Passo 4: Salvare il messaggio
```java
mapi.save(outputDir + "SetFollowUpflag_out.msg");
```
*Il messaggio viene salvato come file `.msg` con il flag allegato.*

## Come impostare il flag per i destinatari (Feature 2)
### Panoramica
A volte è necessario che il flag appaia **only for recipients**. Questo esempio segna prima il messaggio come bozza, quindi aggiunge il flag.

#### Passo 1: Contrassegnare come bozza
```java
mapi.setMessageFlags(MapiMessageFlags.MSGFLAG_UNSENT);
```
*Contrassegnare il messaggio come non inviato garantisce che Outlook lo tratti come una bozza.*

#### Passo 2: Impostare il flag per i destinatari
```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
FollowUpManager.setFlagForRecipients(mapi, "Follow up", dtReminderDate);
```
*Il flag è ora visibile solo ai destinatari – uno scenario classico di **flag for recipients**.*

## Come contrassegnare un Outlook Follow Up Flag come completato (Feature 3)
### Passo 1: Caricare il messaggio
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
```

### Passo 2: Contrassegnare come completato e salvare
```java
FollowUpManager.markAsCompleted(mapi);
mapi.save(outputDir + "MarkedCompleted_out.msg");
```
*Lo stato del flag passa a “Completed” e il file aggiornato viene salvato.*

## Come rimuovere un Outlook Follow Up Flag (Feature 4)
### Passo 1: Caricare e cancellare il flag
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpManager.clearFlag(mapi);
mapi.save(outputDir + "FollowUpFlagRemoved_out.msg");
```
*Il messaggio viene salvato senza alcun flag di follow‑up.*

## Come leggere le opzioni del flag (Feature 5)
### Passo 1: Recuperare le opzioni
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpOptions options = FollowUpManager.getOptions(mapi);
```
*L’oggetto `options` ora contiene le date di inizio, scadenza e promemoria, più l’oggetto del flag – utile quando devi **read flag options** per la reportistica.*

## Applicazioni pratiche
- **Task‑Management Integration:** Sincronizza le email contrassegnate con Jira, Trello o Azure Boards.  
- **Automated Reminders:** Genera email di promemoria giornaliere per i follow‑up in sospeso.  
- **Compliance Audits:** Esporta i dati dei flag per la reportistica normativa.

## Considerazioni sulle prestazioni
- **Date Calculations:** Calcola le date una sola volta per batch anziché all’interno dei cicli.  
- **Resource Management:** Chiudi tutti gli stream o i handle dei file dopo aver salvato i messaggi.  
- **Memory Usage:** Elabora le caselle di posta di grandi dimensioni a blocchi per evitare pressione sulla heap.

## Problemi comuni e soluzioni
| Issue | Cause | Fix |
|-------|-------|-----|
| Flag not appearing in Outlook | Message saved without proper `MessageFlags` | Ensure `setMessageFlags` is set to `MSGFLAG_UNSENT` before applying recipient flags. |
| Save throws `AccessDeniedException` | Incorrect file path or missing write permissions | Verify the output directory exists and the application has write rights. |
| Dates are off by one day | Time‑zone mismatch | Use `TimeZone.getTimeZone("GMT")` or your local zone consistently. |

## Domande frequenti
**Q: What is Aspose.Email for Java?**  
A: It’s a pure‑Java API that lets you create, read, and manipulate email files (MSG, EML, etc.) without needing Outlook installed.

**Q: How do I obtain a free trial license?**  
A: Visit the [Aspose website](https://releases.aspose.com/email/java/) to download a 30‑day trial.

**Q: Can I set multiple follow‑up flags on a single message?**  
A: Outlook supports only one flag per message, but you can store additional task data in custom MAPI properties.

**Q: My message isn’t saved after setting a flag. What should I check?**  
A: Confirm the `outputDir` path is valid and that the application has permission to write to that location.

**Q: How can I remove flags from many messages at once?**  
A: Loop through your message collection and call `FollowUpManager.clearFlag` on each `MapiMessage`.

## Risorse
- [Documentation](https://reference.aspose.com/email/java/)
- [Download Aspose.Email for Java](https://releases.aspose.com/email/java/)
- [Aspose.Email Free Trial](https://purchase.aspose.com/purchase/free-trial/aspose-email-java)

---

**Last Updated:** 2026-02-22  
**Tested With:** Aspose.Email for Java 25.4 (jdk16)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}