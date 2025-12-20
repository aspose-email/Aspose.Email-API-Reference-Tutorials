---
date: '2025-12-20'
description: Scopri come gestire la condivisione del calendario, impostare le autorizzazioni
  dei delegati e creare l'accesso delegato utilizzando Aspose.Email per Java. Segui
  questo tutorial passo passo per inviare email di condivisione del calendario in
  modo efficiente.
keywords:
- Aspose.Email for Java
- create calendar invitations
- send calendar invitations
title: 'Gestisci la condivisione del calendario: Guida Aspose.Email per Java'
url: /it/java/calendar-appointments/create-send-calendar-invitations-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Gestire la Condivisione del Calendario: Guida Aspose.Email per Java

## Introduzione alla Gestione della Condivisione del Calendario
Gestire gli inviti alla condivisione del calendario può essere un compito complesso, soprattutto quando si hanno a che fare con più utenti su piattaforme diverse. In questo tutorial imparerai a **gestire la condivisione del calendario** con Aspose.Email per Java, coprendo tutto, dalla creazione dell'accesso delegato all'invio di email di condivisione del calendario. Alla fine, sarai in grado di impostare le autorizzazioni delegate, configurare le autorizzazioni del calendario e semplificare la collaborazione nella tua organizzazione.

**Cosa Imparerai**
- Come inizializzare il client EWS con Aspose.Email per Java  
- Creare un utente delegato e **impostare le autorizzazioni delegate**  
- **Creare l'accesso delegato** e configurare le autorizzazioni del calendario  
- Inviare programmaticamente una **email di condivisione del calendario** (invito)  
- Scenari reali in cui queste funzionalità aggiungono valore  

Prima di iniziare, assicuriamoci che tu abbia tutto il necessario.

## Risposte Rapide
- **Qual è lo scopo principale di questa guida?** Mostrare come **gestire la condivisione del calendario** usando Aspose.Email per Java.  
- **Quale versione della libreria è richiesta?** Aspose.Email per Java 25.4 (classificatore JDK 16).  
- **È necessaria una licenza?** Sì – è necessaria una licenza di prova o completa per l'uso in produzione.  
- **Quale ambiente è necessario?** JDK 16+, Maven e un account Exchange Online.  
- **Posso usarlo con altri server Exchange?** Sì, ma potresti dover regolare l'URL del servizio e i livelli di autorizzazione.

## Prerequisiti
- **Java Development Kit (JDK):** Versione 16 o successiva.  
- **Maven:** Per la gestione delle dipendenze e la compilazione del progetto.  
- **Libreria Aspose.Email per Java:** Versione 25.4 con supporto JDK 16.  

### Requisiti per la Configurazione dell'Ambiente
1. Installa JDK se non lo hai già fatto. Puoi scaricarlo dal [sito ufficiale di Oracle](https://www.oracle.com/java/technologies/javase-downloads.html).  
2. Assicurati che Maven sia installato e configurato sulla tua macchina.  
3. Scegli un IDE come IntelliJ IDEA o Eclipse per facilitare lo sviluppo.

### Prerequisiti di Conoscenza
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

### Ottenimento della Licenza
Aspose.Email per Java richiede una licenza per la piena funzionalità. Puoi:
- **Prova Gratuita:** Scarica dalla [pagina di rilascio di Aspose](https://releases.aspose.com/email/java/).  
- **Licenza Temporanea:** Richiedi una chiave temporanea sul sito web di Aspose.  
- **Acquisto:** Ottieni una licenza permanente per le distribuzioni in produzione.

### Inizializzazione e Configurazione di Base
Una volta che Maven ha risolto la dipendenza, inizializza il client EWS:

```java
IEWSClient client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser", "pwd", "domain");
```

## Guida all'Implementazione
Di seguito copriamo due funzionalità principali: creare e inviare un invito di condivisione del calendario, e **impostare le autorizzazioni delegate** per l'accesso al calendario.

### Funzionalità 1: Creare e Inviare un Invito di Condivisione del Calendario
#### Panoramica
Questa funzionalità ti guida attraverso l'inizializzazione del client, **creare l'accesso delegato**, e l'invio dell'email di invito.

#### Implementazione Passo‑per‑Passo
##### 1️⃣ Inizializza il Client EWS
```java
IEWSClient client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser", "pwd", "domain");
```
Questo collega la tua applicazione Java a Exchange Online.

##### 2️⃣ Crea Utente Delegato
```java
ExchangeDelegateUser delegateUser = new ExchangeDelegateUser("sharingfrom@domain.com", ExchangeDelegateFolderPermissionLevel.NotSpecified);
delegateUser.getFolderPermissions().setCalendarFolderPermissionLevel(ExchangeDelegateFolderPermissionLevel.Reviewer);
client.delegateAccess(delegateUser, "sharingfrom@domain.com");
```
Qui **creiamo l'accesso delegato** e assegniamo il livello `Reviewer`, che permette al delegato di visualizzare gli elementi del calendario.

##### 3️⃣ Invia Invito di Condivisione del Calendario
```java
MapiMessage mapiMessage = client.createCalendarSharingInvitationMessage("sharingfrom@domain.com");

MailConversionOptions options = new MailConversionOptions();
options.setConvertAsTnef(true);

MailMessage mail = mapiMessage.toMailMessage(options);
client.send(mail);
```
Il codice crea una **email di condivisione del calendario** (invito) e la invia tramite il client EWS.

### Funzionalità 2: Autorizzazione di Accesso al Calendario Delegato
#### Panoramica
Questa sezione mostra come **configurare le autorizzazioni del calendario** e garantire che il delegato abbia i diritti corretti.

#### Passaggi di Implementazione
##### 1️⃣ Inizializza il Client EWS (riutilizzo)
```java
IEWSClient client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser", "pwd", "domain");
```

##### 2️⃣ Crea e Imposta le Autorizzazioni Delegate
```java
ExchangeDelegateUser delegateUser = new ExchangeDelegateUser("sharingfrom@domain.com", ExchangeDelegateFolderPermissionLevel.NotSpecified);
delegateUser.getFolderPermissions().setCalendarFolderPermissionLevel(ExchangeDelegateFolderPermissionLevel.Reviewer);

client.delegateAccess(delegateUser, "sharingfrom@domain.com");
```
Questo snippet **imposta le autorizzazioni delegate** così l'utente può visualizzare le voci del calendario senza avere pieno accesso alla casella di posta.

## Applicazioni Pratiche
Scenari reali in cui **gestire la condivisione del calendario** è utile:

1. **Riunioni Aziendali** – Consente ai membri del team di visualizzare i programmi delle riunioni senza concedere pieni diritti sulla casella di posta.  
2. **Gestione Progetti** – I responsabili di progetto possono monitorare le scadenze mentre gli sviluppatori mantengono il controllo dei propri calendari.  
3. **Pianificazione Eventi** – I fornitori ricevono una **email di condivisione del calendario** per coordinare la logistica senza esporre dettagli interni.

## Considerazioni sulle Prestazioni
- **Gestione della Memoria:** Rilascia prontamente i grandi oggetti `MailMessage` nelle applicazioni ad alto volume.  
- **Gestione delle Eccezioni:** Avvolgi le chiamate di rete in blocchi try‑catch per gestire i problemi di connettività in modo fluido.  
- **Aggiornamenti della Libreria:** Mantieni Aspose.Email aggiornato per beneficiare di miglioramenti delle prestazioni e correzioni di bug.

## Domande Frequenti
**D: A cosa serve Aspose.Email per Java?**  
R: È una libreria completa per gestire email, calendari e contatti nelle applicazioni Java, supportando Outlook, Exchange e altri protocolli.

**D: Come configuro il mio ambiente per usare Aspose.Email?**  
R: Installa JDK 16+, Maven, aggiungi la dipendenza Aspose.Email a `pom.xml` e ottieni una licenza (di prova o completa).

**D: Posso usare questo codice con altre versioni di Exchange Online?**  
R: Sì, ma verifica che l'URL del servizio e i livelli di autorizzazione corrispondano alla configurazione del tuo server.

**D: Cosa devo fare se l'invito di condivisione del calendario non viene inviato?**  
R: Controlla la connettività di rete, le credenziali e che l'utente delegato abbia le autorizzazioni valide. Esamina i dettagli dell'eccezione per indizi.

**D: È possibile aggiungere autorizzazioni aggiuntive come modifica o accesso completo?**  
R: Assolutamente – sostituisci `ExchangeDelegateFolderPermissionLevel.Reviewer` con `Editor`, `Author` o `Owner` secondo necessità.

## Conclusione
Ora disponi di una soluzione completa, end‑to‑end, per **gestire la condivisione del calendario** con Aspose.Email per Java. Inizializzando il client EWS, **creando l'accesso delegato**, **impostando le autorizzazioni delegate**, e inviando una **email di condivisione del calendario**, puoi automatizzare la collaborazione nella tua organizzazione.

**Passi Successivi**
- Sperimenta altri livelli di autorizzazione (Editor, Owner).  
- Integra questa logica nei tuoi sistemi di pianificazione o HR esistenti.  
- Esplora funzionalità aggiuntive di Aspose.Email come eventi ricorrenti o richieste di riunione.

---

**Ultimo Aggiornamento:** 2025-12-20  
**Testato Con:** Aspose.Email per Java 25.4 (classificatore JDK 16)  
**Autore:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}