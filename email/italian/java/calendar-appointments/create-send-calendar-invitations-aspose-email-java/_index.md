---
date: '2026-09-17'
description: Come creare un invito di calendario con Aspose.Email per Java ti consente
  di condividere calendari, impostare permessi delegati e inviare email di condivisione
  in modo programmatico.
keywords:
- how to create calendar invitation
- calendar sharing invitation
- Aspose.Email Java
- delegate calendar permissions
lastmod: '2026-09-17'
og_description: Come creare un invito di calendario con Aspose.Email per Java ti consente
  di condividere calendari in modo programmatico, impostare permessi delegati e inviare
  email di condivisione tramite Exchange Web Services, migliorando la collaborazione
  del team.
og_image_alt: Guide showing how to create calendar invitation with Aspose.Email for
  Java
og_title: Come creare un invito di calendario con Aspose.Email per Java
schemas:
- author: Aspose
  dateModified: '2026-09-17'
  description: How to create calendar invitation with Aspose.Email for Java lets you
    share calendars, set delegate permissions, and send sharing emails programmatically.
  headline: How to create calendar invitation with Aspose.Email for Java
  type: TechArticle
- description: How to create calendar invitation with Aspose.Email for Java lets you
    share calendars, set delegate permissions, and send sharing emails programmatically.
  name: How to create calendar invitation with Aspose.Email for Java
  steps:
  - name: Install JDK if you haven't already. You can download it from [Oracle's official
      site](https://www.oracle.com/java/technologies/javase-downloads.html).
    text: Install JDK if you haven't already. You can download it from [Oracle's official
      site](https://www.oracle.com/java/technologies/javase-downloads.html).
  - name: Ensure Maven is installed and configured on your machine.
    text: Ensure Maven is installed and configured on your machine.
  - name: Choose an IDE such as IntelliJ IDEA or Eclipse for easier development.
    text: Choose an IDE such as IntelliJ IDEA or Eclipse for easier development.
  - name: '**Corporate meetings** – Let team members view meeting schedules without
      giving full mailbox rights.'
    text: '**Corporate meetings** – Let team members view meeting schedules without
      giving full mailbox rights.'
  - name: '**Project management** – Project leads can monitor timelines while developers
      retain control of their own calendars.'
    text: '**Project management** – Project leads can monitor timelines while developers
      retain control of their own calendars.'
  - name: '**Event planning** – Vendors receive a **calendar sharing email** to coordinate
      logistics without exposing internal details.'
    text: '**Event planning** – Vendors receive a **calendar sharing email** to coordinate
      logistics without exposing internal details.'
  type: HowTo
- questions:
  - answer: It’s a comprehensive library for handling emails, calendars, and contacts
      in Java applications, supporting Outlook, Exchange, and other protocols.
    question: What is Aspose.Email for Java used for?
  - answer: Install JDK 16+, Maven, add the Aspose.Email dependency to `pom.xml`,
      and obtain a license (trial or full).
    question: How do I set up my environment for using Aspose.Email?
  - answer: Yes, but verify the service URL and permission levels match your server’s
      configuration.
    question: Can I use this code with other versions of Exchange Online?
  - answer: Check network connectivity, credentials, and that the delegate user has
      valid permissions. Review exception details for clues.
    question: What should I do if the calendar sharing invitation fails to send?
  - answer: Absolutely – replace `ExchangeDelegateFolderPermissionLevel.Reviewer`
      with `Editor`, `Author`, or `Owner` as needed.
    question: Is it possible to add additional permissions like editing or full access?
  type: FAQPage
tags:
- calendar sharing
- Aspose.Email
- Java email API
- delegate permissions
- EWS client
title: Come creare un invito di calendario con Aspose.Email per Java
url: /it/java/calendar-appointments/create-send-calendar-invitations-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gestire la condivisione del calendario: guida Aspose.Email per Java

## Introduzione alla gestione della condivisione del calendario
Gestire gli inviti alla condivisione del calendario può essere un compito complesso, soprattutto quando si tratta di più utenti su piattaforme diverse. In questo tutorial **creerai un invito alla condivisione del calendario** con Aspose.Email per Java, coprendo tutto, dalla creazione dell'accesso delegato all'invio di email di condivisione del calendario. Alla fine, sarai in grado di impostare le autorizzazioni delegate, **configurare le autorizzazioni del calendario** e semplificare la collaborazione nella tua organizzazione.

**Cosa imparerai**
- Come inizializzare il client EWS con Aspose.Email per Java  
- Creare un utente delegato e **impostare le autorizzazioni delegate**  
- **Creare l'accesso delegato** e configurare le autorizzazioni del calendario  
- Inviare programmaticamente una **email di condivisione del calendario** (invito)  
- Scenari reali in cui queste funzionalità aggiungono valore  

Prima di immergerci, assicuriamoci che tu abbia tutto il necessario.

## Risposte rapide
- **Qual è lo scopo principale di questa guida?** Mostrare come **creare un invito alla condivisione del calendario** usando Aspose.Email per Java.  
- **Quale versione della libreria è richiesta?** Aspose.Email per Java 25.4 (classificatore JDK 16).  
- **Ho bisogno di una licenza?** Sì – è necessaria una licenza di prova o completa per l'uso in produzione.  
- **Quale ambiente è necessario?** JDK 16+, Maven e un account Exchange Online.  
- **Posso usarlo con altri server Exchange?** Sì, ma potresti dover regolare l'URL del servizio e i livelli di autorizzazione.

## Cos'è un invito alla condivisione del calendario?
Un invito alla condivisione del calendario è un messaggio email che concede a un altro utente l'accesso per visualizzare (o modificare) il tuo calendario senza concedere pieni diritti sulla casella di posta. Consente ai membri del team di vedere il tuo programma, proporre riunioni o gestire eventi mantenendo sicura la tua casella di posta.

## Perché configurare le autorizzazioni del calendario?
Configurare le autorizzazioni del calendario ti consente di controllare esattamente cosa può fare un delegato—se può solo leggere gli eventi, proporne di nuovi o modificare le voci esistenti. Impostazioni corrette delle autorizzazioni proteggono le informazioni sensibili mentre abilitano una collaborazione efficace. Ad esempio, concedere accesso in sola lettura impedisce modifiche accidentali, mentre i diritti di modifica permettono al delegato di programmare o modificare riunioni per tuo conto.

## Prerequisiti
- **Java Development Kit (JDK):** Versione 16 o successiva.  
- **Maven:** Per la gestione delle dipendenze e la compilazione del progetto.  
- **Libreria Aspose.Email per Java:** Versione 25.4 con supporto JDK 16.  

### Requisiti per la configurazione dell'ambiente
1. Installa JDK se non lo hai già fatto. Puoi scaricarlo dal [sito ufficiale di Oracle](https://www.oracle.com/java/technologies/javase-downloads.html).  
2. Assicurati che Maven sia installato e configurato sulla tua macchina.  
3. Scegli un IDE come IntelliJ IDEA o Eclipse per uno sviluppo più semplice.

### Prerequisiti di conoscenza
- Competenze di base nella programmazione Java  
- Familiarità con le dipendenze Maven  
- Opzionale: esperienza con Exchange Web Services (EWS)

## Configurazione di Aspose.Email per Java
### Configurazione Maven
Aggiungi la seguente dipendenza al tuo file `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Acquisizione della licenza
Aspose.Email per Java richiede una licenza per la piena funzionalità. Puoi:
- **Prova gratuita:** Scarica dalla [pagina di rilascio di Aspose](https://releases.aspose.com/email/java/).  
- **Licenza temporanea:** Richiedi una chiave temporanea sul sito di Aspose.  
- **Acquisto:** Ottieni una licenza permanente per le distribuzioni in produzione.

### Inizializzazione e configurazione di base
Una volta che Maven ha risolto la dipendenza, inizializza il client EWS:

```java
IEWSClient client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser", "pwd", "domain");
```

`ExchangeService` è la classe principale utilizzata per comunicare con Exchange Web Services.  

## Come creare un invito alla condivisione del calendario
Per creare un invito alla condivisione del calendario devi prima connetterti a Exchange usando il client `ExchangeService`, poi definire un delegato con il livello di autorizzazione desiderato e infine comporre un `MailMessage` che includa la richiesta di condivisione. I passaggi seguenti mostrano questo flusso di lavoro in Java.

Di seguito copriamo due funzionalità principali: creare e inviare un invito alla condivisione del calendario, e **impostare le autorizzazioni delegate** per l'accesso al calendario.

### Funzione 1: creare e inviare un invito alla condivisione del calendario
#### Panoramica
Questa funzionalità ti guida attraverso l'inizializzazione del client, **creare l'accesso delegato**, e l'invio dell'email di invito.

#### Implementazione passo‑a‑passo
##### 1️⃣ Inizializza il client EWS
`ExchangeService` rappresenta la connessione a un server Exchange ed è usato per inviare e ricevere messaggi.  

```java
IEWSClient client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser", "pwd", "domain");
```  
Questo collega la tua app Java a Exchange Online.

##### 2️⃣ Crea utente delegato
`DelegateUser` definisce l'indirizzo email del delegato e il livello di autorizzazione da concedere.  

```java
ExchangeDelegateUser delegateUser = new ExchangeDelegateUser("sharingfrom@domain.com", ExchangeDelegateFolderPermissionLevel.NotSpecified);
delegateUser.getFolderPermissions().setCalendarFolderPermissionLevel(ExchangeDelegateFolderPermissionLevel.Reviewer);
client.delegateAccess(delegateUser, "sharingfrom@domain.com");
```  
Qui **creiamo l'accesso delegato** e assegniamo il livello `Reviewer`, che consente al delegato di visualizzare gli elementi del calendario.

##### 3️⃣ Invia l'invito alla condivisione del calendario
`MailMessage` costruisce l'email che trasporta l'invito alla condivisione del calendario.  

```java
MapiMessage mapiMessage = client.createCalendarSharingInvitationMessage("sharingfrom@domain.com");

MailConversionOptions options = new MailConversionOptions();
options.setConvertAsTnef(true);

MailMessage mail = mapiMessage.toMailMessage(options);
client.send(mail);
```  
Il codice costruisce una **email di condivisione del calendario** (invito) e la invia tramite il client EWS.

### Funzione 2: autorizzazione di accesso al calendario delegato
#### Panoramica
Questa sezione mostra come **configurare le autorizzazioni del calendario** e garantire che il delegato abbia i diritti corretti.

#### Passaggi di implementazione
##### 1️⃣ Inizializza il client EWS (riutilizzo)
`ExchangeService` può essere riutilizzato per più operazioni dopo la configurazione iniziale.  

```java
IEWSClient client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser", "pwd", "domain");
```  

##### 2️⃣ Crea e imposta le autorizzazioni delegate
`ExchangeDelegateFolderPermissionLevel` elenca i livelli di accesso che un delegato può avere su una cartella del calendario.  

```java
ExchangeDelegateUser delegateUser = new ExchangeDelegateUser("sharingfrom@domain.com", ExchangeDelegateFolderPermissionLevel.NotSpecified);
delegateUser.getFolderPermissions().setCalendarFolderPermissionLevel(ExchangeDelegateFolderPermissionLevel.Reviewer);

client.delegateAccess(delegateUser, "sharingfrom@domain.com");
```  
Questo snippet **imposta le autorizzazioni delegate** così l'utente può visualizzare le voci del calendario senza avere pieno accesso alla casella di posta.

## Come configurare le autorizzazioni del calendario per i delegati
Quando un delegato ha bisogno di più di un accesso in sola lettura, puoi regolare `ExchangeDelegateFolderPermissionLevel` per concedere diritti di modifica, autore o proprietario. Scegli il livello minimo che soddisfa il requisito aziendale per mantenere la sicurezza pur fornendo la funzionalità necessaria. Ad esempio, assegnare il livello Editor consente al delegato di creare, modificare e cancellare eventi, mentre il livello Reviewer permette solo la visualizzazione.

- `Reviewer` – accesso in sola lettura.  
- `Editor` – accesso lettura/scrittura.  
- `Author` – crea e legge, ma non può eliminare.  
- `Owner` – controllo totale, incluse le modifiche alle autorizzazioni.  

**Pro tip:** Usa il livello di privilegio minimo che soddisfa il requisito aziendale per mantenere sicuri i dati del tuo calendario.

## Applicazioni pratiche
Scenari reali in cui **gestire la condivisione del calendario** brilla:
1. **Riunioni aziendali** – Consenti ai membri del team di visualizzare i programmi delle riunioni senza concedere pieni diritti sulla casella di posta.  
2. **Gestione progetti** – I responsabili di progetto possono monitorare le scadenze mentre gli sviluppatori mantengono il controllo dei propri calendari.  
3. **Pianificazione eventi** – I fornitori ricevono una **email di condivisione del calendario** per coordinare la logistica senza esporre dettagli interni.

## Considerazioni sulle prestazioni
- **Gestione della memoria:** Disporre rapidamente di oggetti `MailMessage` di grandi dimensioni nelle applicazioni ad alto volume.  
- **Gestione delle eccezioni:** Avvolgi le chiamate di rete in blocchi try‑catch per gestire i problemi di connettività in modo elegante.  
- **Aggiornamenti della libreria:** Aspose.Email per Java supporta oltre 50 protocolli e può elaborare calendari con fino a 10.000 elementi senza caricare l'intero file in memoria, quindi mantieni la libreria aggiornata per beneficiare di miglioramenti delle prestazioni e correzioni di bug.

## Problemi comuni e soluzioni
| Problema | Probabile causa | Soluzione |
|----------|-----------------|-----------|
| Invito non ricevuto | Filtri antispam o indirizzo email errato | Verifica l'indirizzo del destinatario e aggiungi il dominio di invio alla lista dei mittenti sicuri |
| Autorizzazione non applicata | Uso di `ExchangeDelegateFolderPermissionLevel` errato | Controlla che il livello di autorizzazione corrisponda all'accesso richiesto |
| Eccezione runtime su `createCalendarSharingInvitationMessage` | Licenza mancante o libreria obsoleta | Assicurati che sia caricata una licenza valida e che tu stia usando l'ultima versione di Aspose.Email |

## Domande frequenti
**D: Qual è l'uso di Aspose.Email per Java?**  
R: È una libreria completa per gestire email, calendari e contatti in applicazioni Java, supportando Outlook, Exchange e altri protocolli.

**D: Come configuro il mio ambiente per usare Aspose.Email?**  
R: Installa JDK 16+, Maven, aggiungi la dipendenza Aspose.Email a `pom.xml` e ottieni una licenza (di prova o completa).

**D: Posso usare questo codice con altre versioni di Exchange Online?**  
R: Sì, ma verifica che l'URL del servizio e i livelli di autorizzazione corrispondano alla configurazione del tuo server.

**D: Cosa devo fare se l'invito alla condivisione del calendario non viene inviato?**  
R: Controlla la connettività di rete, le credenziali e che l'utente delegato abbia autorizzazioni valide. Esamina i dettagli dell'eccezione per indizi.

**D: È possibile aggiungere autorizzazioni aggiuntive come modifica o accesso completo?**  
R: Assolutamente – sostituisci `ExchangeDelegateFolderPermissionLevel.Reviewer` con `Editor`, `Author` o `Owner` secondo necessità.

## Conclusione
Ora disponi di una soluzione completa, end‑to‑end, per **creare un invito alla condivisione del calendario** con Aspose.Email per Java. Inizializzando il client EWS, **creando l'accesso delegato**, **impostando le autorizzazioni delegate** e inviando una **email di condivisione del calendario**, puoi automatizzare la collaborazione nella tua organizzazione.

**Passaggi successivi**
- Sperimenta altri livelli di autorizzazione (Editor, Owner).  
- Integra questa logica nei tuoi sistemi di pianificazione o HR esistenti.  
- Esplora ulteriori funzionalità di Aspose.Email come eventi ricorrenti o richieste di riunione.

---

**Last Updated:** 2026-09-17  
**Tested With:** Aspose.Email for Java 25.4 (JDK 16 classifier)  
**Author:** Aspose

## Tutorial correlati

- [Come creare un elemento calendario Java usando Aspose.Email](/email/java/calendar-appointments/create-save-calendar-items-aspose-email-java/)
- [Aspose Email Java Filtra gli appuntamenti Exchange per data](/email/java/calendar-appointments/aspose-email-java-filter-exchange-appointments-by-date/)
- [Crea calendario Exchange Java con Aspose.Email – Guida completa](/email/java/calendar-appointments/mastering-exchange-calendar-management-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}