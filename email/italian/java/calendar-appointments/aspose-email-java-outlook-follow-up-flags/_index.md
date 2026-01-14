---
date: '2025-12-19'
description: Scopri come impostare i flag di follow‑up in Outlook usando Aspose.Email
  per Java, incluso come impostare il flag di follow‑up di Outlook e rimuovere il
  flag di follow‑up di Outlook in modo efficiente.
keywords:
- Manage Outlook follow-up flags
- Set follow-up flags in Outlook with Aspose.Email for Java
- Integrate email task management with Aspose.Email
title: Come impostare i flag di follow-up in Outlook usando Aspose.Email per Java
url: /it/java/calendar-appointments/aspose-email-java-outlook-follow-up-flags/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Come impostare i flag di follow‑up in Outlook usando Aspose.Email per Java

## Introduzione
Se hai mai faticato a tenere traccia delle email importanti, sai quanto siano utili i flag di follow‑up di Outlook. In questa guida ti mostreremo **come impostare i flag di follow‑up** in modo programmatico con Aspose.Email per Java, e copriremo anche come **impostare il flag di follow‑up di Outlook** per i destinatari, così come come **rimuovere il flag di follow‑up di Outlook** quando un’attività è terminata. Alla fine, sarai in grado di automatizzare il tracciamento delle attività, i promemoria e i percorsi di audit direttamente dal tuo codice Java.

**Cosa imparerai**
- Creare e applicare un flag di follow‑up a un messaggio Outlook.  
- Impostare flag di follow‑up per destinatari specifici.  
- Contrassegnare un flag come completato e successivamente rimuoverlo.  
- Leggere le opzioni del flag per report o conformità.  

Prepariamo l'ambiente prima di immergerci nel codice.

## Risposte rapide
- **Cosa significa “how to set follow-up”?** Aggiungere un flag con date di inizio, promemoria e scadenza a un elemento Outlook.  
- **Quale libreria è necessaria?** Aspose.Email per Java (v25.4 o successiva).  
- **È necessaria una licenza?** Sì, è richiesta una licenza di prova o acquistata per la piena funzionalità.  
- **Posso impostare i flag solo per i destinatari?** Assolutamente – usa `FollowUpManager.setFlagForRecipients`.  
- **È possibile rimuovere un flag in seguito?** Sì, chiama `FollowUpManager.clearFlag`.

## Cos'è un flag di follow‑up?
Un flag di follow‑up è una funzionalità di Outlook che contrassegna un'email come attività, allegando facoltativamente date di inizio, promemoria e scadenza. Aiuta te e il tuo team a rimanere al passo con le azioni in sospeso.

## Perché usare Aspose.Email per Java?
Aspose.Email fornisce un'API pure‑Java che funziona senza Outlook installato, consentendoti di manipolare file .msg, impostare flag e gestire attività su qualsiasi piattaforma—perfetta per servizi backend, flussi di lavoro automatizzati o integrazioni con strumenti di gestione progetti.

## Prerequisiti
- **Aspose.Email per Java** versione 25.4 o successiva.  
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
Aspose.Email richiede una licenza per l'uso in produzione:

- **Prova gratuita** – valutazione di 30 giorni.  
- **Licenza temporanea** – test esteso.  
- **Licenza completa** – abbonamento perpetuo.

Inizializza la licenza prima di qualsiasi operazione email:

```java
License license = new License();
license.setLicense("path/to/Aspose.Total.Java.lic");
```

## Guida all'implementazione

### Come impostare i flag di follow‑up (Funzione 1)
#### Panoramica
Questa sezione ti guida nella creazione di un messaggio Outlook, nella definizione delle date di inizio/promemoria/scadenza e nell'applicazione di un flag di follow‑up.

#### Passo 1: Creare e inizializzare il messaggio
```java
MailMessage mailMsg = new MailMessage();
mailMsg.setSender(new MailAddress("AETest12@gmail.com"));
mailMsg.getTo().addMailAddress(new MailAddress("receiver@gmail.com"));
mailMsg.setBody("This message will test if follow up options can be added to a new mapi message.");
MapiMessage mapi = MapiMessage.fromMailMessage(mailMsg);
```
*Costruiamo prima un `MailMessage`, impostiamo mittente/destinatario, poi lo convertiamo in un `MapiMessage` per la manipolazione del flag.*

#### Passo 2: Definire le date di follow‑up
```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 14, 40, 0);
Date dtStartDate = calendar.getTime();
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
calendar.add(Calendar.DATE, 1);
Date dtDueDate = calendar.getTime();
```
*Qui impostiamo le date di inizio, promemoria e scadenza usando la classe `Calendar`.*

#### Passo 3: Applicare le opzioni di follow‑up
```java
FollowUpOptions options = new FollowUpOptions("Follow Up", dtStartDate, dtDueDate, dtReminderDate);
FollowUpManager.setOptions(mapi, options);
```
*L'oggetto `FollowUpOptions` contiene tutti i dettagli del flag, che applichiamo con `FollowUpManager.setOptions`.*

#### Passo 4: Salvare il messaggio
```java
mapi.save(outputDir + "SetFollowUpflag_out.msg");
```
*Il messaggio viene salvato come file `.msg` con il flag allegato.*

### Come impostare il flag di follow‑up di Outlook per i destinatari (Funzione 2)
#### Panoramica
A volte è necessario contrassegnare un messaggio solo per i destinatari. Questo esempio segna prima il messaggio come bozza, poi aggiunge il flag.

#### Passo 1: Contrassegnare come bozza
```java
mapi.setMessageFlags(MapiMessageFlags.MSGFLAG_UNSENT);
```
*Contrassegnare il messaggio come non inviato garantisce che Outlook lo tratti come bozza.*

#### Passo 2: Impostare il flag per il destinatario
```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
FollowUpManager.setFlagForRecipients(mapi, "Follow up", dtReminderDate);
```
*Il flag è ora visibile solo ai destinatari.*

### Come contrassegnare un flag di follow‑up di Outlook come completato (Funzione 3)
#### Panoramica
Quando un'attività è terminata, puoi contrassegnare programmaticamente il flag come completato.

#### Passo 1: Caricare il messaggio
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
```

#### Passo 2: Contrassegnare come completato e salvare
```java
FollowUpManager.markAsCompleted(mapi);
mapi.save(outputDir + "MarkedCompleted_out.msg");
```
*Lo stato del flag cambia in “Completed” e il file aggiornato viene salvato.*

### Come rimuovere il flag di follow‑up di Outlook (Funzione 4)
#### Panoramica
Se un flag non è più necessario, puoi cancellarlo completamente.

#### Passo 1: Caricare e cancellare il flag
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpManager.clearFlag(mapi);
mapi.save(outputDir + "FollowUpFlagRemoved_out.msg");
```
*Il messaggio viene salvato senza alcun flag di follow‑up.*

### Come leggere le opzioni del flag di follow‑up (Funzione 5)
#### Panoramica
Per audit o report, potresti dover leggere le impostazioni del flag esistente.

#### Passo 1: Recuperare le opzioni
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpOptions options = FollowUpManager.getOptions(mapi);
```
*L'oggetto `options` ora contiene le date di inizio, scadenza e promemoria, oltre all'oggetto del flag.*

## Applicazioni pratiche
- **Integrazione con la gestione delle attività:** Sincronizza le email contrassegnate con Jira, Trello o Azure Boards.  
- **Promemoria automatizzati:** Genera email di promemoria giornaliere per i follow‑up in sospeso.  
- **Audit di conformità:** Esporta i dati dei flag per la reportistica normativa.

## Considerazioni sulle prestazioni
- **Calcoli delle date:** Calcola le date una sola volta per batch anziché all'interno dei cicli.  
- **Gestione delle risorse:** Chiudi tutti gli stream o handle di file dopo il salvataggio dei messaggi.  
- **Utilizzo della memoria:** Processa le caselle di posta di grandi dimensioni a blocchi per evitare pressione sull'heap.

## Problemi comuni e soluzioni
| Problema | Causa | Soluzione |
|----------|-------|-----------|
| Il flag non appare in Outlook | Messaggio salvato senza i corretti `MessageFlags` | Assicurarsi che `setMessageFlags` sia impostato a `MSGFLAG_UNSENT` prima di applicare i flag per i destinatari. |
| Salvataggio genera `AccessDeniedException` | Percorso file errato o permessi di scrittura mancanti | Verificare che la directory di output esista e che l'applicazione abbia i permessi di scrittura. |
| Le date sono sfasate di un giorno | Mancata corrispondenza del fuso orario | Usare `TimeZone.getTimeZone("GMT")` o il proprio fuso locale in modo coerente. |

## Domande frequenti
**D: Cos'è Aspose.Email per Java?**  
**R:** È un'API pure‑Java che consente di creare, leggere e manipolare file email (MSG, EML, ecc.) senza la necessità di Outlook installato.

**D: Come ottengo una licenza di prova gratuita?**  
**R:** Visita il [sito Aspose](https://releases.aspose.com/email/java/) per scaricare una prova di 30 giorni.

**D: Posso impostare più flag di follow‑up su un singolo messaggio?**  
**R:** Outlook supporta un solo flag per messaggio, ma è possibile memorizzare dati aggiuntivi di attività in proprietà MAPI personalizzate.

**D: Il mio messaggio non viene salvato dopo aver impostato un flag. Cosa devo controllare?**  
**R:** Verifica che il percorso `outputDir` sia valido e che l'applicazione disponga dei permessi di scrittura su quella posizione.

**D: Come posso rimuovere i flag da molti messaggi contemporaneamente?**  
**R:** Scorri la tua collezione di messaggi e chiama `FollowUpManager.clearFlag` su ciascun `MapiMessage`.

## Risorse
- [Documentazione](https://reference.aspose.com/email/java/)
- [Scarica Aspose.Email per Java](https://releases.aspose.com/email/java/)
- [Prova gratuita Aspose.Email](https://purchase.aspose.com/purchase/free-trial/aspose-email-java)

---

**Last Updated:** 2025-12-19  
**Tested With:** Aspose.Email for Java 25.4 (jdk16)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}