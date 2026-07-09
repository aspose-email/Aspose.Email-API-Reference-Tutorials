---
date: '2026-03-20'
description: Scopri come creare un invito di condivisione del calendario, configurare
  le autorizzazioni del calendario e impostare l'accesso delegato utilizzando Aspose.Email
  per Java.
keywords:
- Aspose.Email for Java
- create calendar invitations
- send calendar invitations
title: Crea invito di condivisione del calendario con Aspose.Email per Java
url: /it/java/calendar-appointments/create-send-calendar-invitations-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Gestire la Condivisione del Calendario: Guida Aspose.Email per Java

## Introduzione alla Gestione della Condivisione del Calendario
Gestire gli inviti di condivisione del calendario può essere un compito complesso, soprattutto quando si ha a che fare con più utenti su piattaforme diverse. In questo tutorial **creerai un invito di condivisione del calendario** con Aspose.Email per Java, coprendo tutto, dalla creazione dell'accesso delegato all'invio di email di condivisione del calendario. Alla fine, sarai in grado di impostare le autorizzazioni delegate, **configurare le autorizzazioni del calendario** e semplificare la collaborazione nella tua organizzazione.

**Cosa Imparerai**
- Come inizializzare il client EWS con Aspose.Email per Java  
- Creare un utente delegato e **impostare le autorizzazioni delegate**  
- **Creare l'accesso delegato** e configurare le autorizzazioni del calendario  
- Inviare programmaticamente una **email di condivisione del calendario** (invito)  
- Scenari reali in cui queste funzionalità aggiungono valore  

Prima di iniziare, assicuriamoci che tu abbia tutto il necessario.

## Risposte Rapide
- **Qual è lo scopo principale di questa guida?** Mostrare come **creare un invito di condivisione del calendario** usando Aspose.Email per Java.  
- **Quale versione della libreria è richiesta?** Aspose.Email per Java 25.4 (classificatore JDK 16).  
- **Ho bisogno di una licenza?** Sì – è necessaria una licenza di prova o completa per l'uso in produzione.  
- **Quale ambiente è necessario?** JDK 16+, Maven e un account Exchange Online.  
- **Posso usarlo con altri server Exchange?** Sì, ma potresti dover regolare l'URL del servizio e i livelli di autorizzazione.

## Cos'è un invito di condivisione del calendario?
Un invito di condivisione del calendario è un messaggio email che concede a un altro utente l'accesso per visualizzare (o modificare) il tuo calendario senza concedere i diritti completi sulla casella di posta. È comunemente usato per il coordinamento del team, la pianificazione di progetti e la gestione di eventi.

## Perché configurare le autorizzazioni del calendario?
Configurare le autorizzazioni del calendario ti permette di controllare esattamente cosa può fare un delegato—se può solo leggere gli eventi, proporne di nuovi o modificare le voci esistenti. Impostazioni corrette delle autorizzazioni proteggono le informazioni sensibili consentendo al contempo una collaborazione efficace.

## Prerequisiti
- **Java Development Kit (JDK):** Versione 16 o successiva.  
- **Maven:** Per la gestione delle dipendenze e la compilazione del progetto.  
- **Aspose.Email per Java Library:** Versione 25.4 con supporto JDK 16.  

### Requisiti per la Configurazione dell'Ambiente
1. Installa JDK se non lo hai già fatto. Puoi scaricarlo dal [sito ufficiale di Oracle](https://www.oracle.com/java/technologies/javase-downloads.html).  
2. Assicurati che Maven sia installato e configurato sulla tua macchina.  
3. Scegli un IDE come IntelliJ IDEA o Eclipse per uno sviluppo più semplice.

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

### Acquisizione della Licenza
Aspose.Email per Java richiede una licenza per la piena funzionalità. Puoi:
- **Prova Gratuita:** Scarica dalla [pagina di rilascio di Aspose](https://releases.aspose.com/email/java/).  
- **Licenza Temporanea:** Richiedi una chiave temporanea sul sito web di Aspose.  
- **Acquisto:** Ottieni una licenza permanente per le distribuzioni in produzione.

### Inizializzazione e Configurazione di Base
Una volta che Maven ha risolto la dipendenza, inizializza il client EWS:

```java
IEWSClient client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser", "pwd", "domain");
```

## Come creare un invito di condivisione del calendario
Di seguito copriamo due funzionalità principali: creare e inviare un invito di condivisione del calendario, e **impostare le autorizzazioni delegate** per l'accesso al calendario.

### Funzionalità 1: Creare e Inviare un Invito di Condivisione del Calendario
#### Panoramica
Questa funzionalità ti guida attraverso l'inizializzazione del client, **creare l'accesso delegato**, e l'invio dell'email di invito.

#### Implementazione Passo‑per‑Passo
##### 1️⃣ Inizializzare il Client EWS
```java
IEWSClient client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser", "pwd", "domain");
```
Questo collega la tua applicazione Java a Exchange Online.

##### 2️⃣ Creare Utente Delegato
```java
ExchangeDelegateUser delegateUser = new ExchangeDelegateUser("sharingfrom@domain.com", ExchangeDelegateFolderPermissionLevel.NotSpecified);
delegateUser.getFolderPermissions().setCalendarFolderPermissionLevel(ExchangeDelegateFolderPermissionLevel.Reviewer);
client.delegateAccess(delegateUser, "sharingfrom@domain.com");
```
Qui **creiamo l'accesso delegato** e assegniamo il livello `Reviewer`, che consente al delegato di visualizzare gli elementi del calendario.

##### 3️⃣ Inviare l'Invito di Condivisione del Calendario
```java
MapiMessage mapiMessage = client.createCalendarSharingInvitationMessage("sharingfrom@domain.com");

MailConversionOptions options = new MailConversionOptions();
options.setConvertAsTnef(true);

MailMessage mail = mapiMessage.toMailMessage(options);
client.send(mail);
```
Il codice crea una **email di condivisione del calendario** (invito) e la invia tramite il client EWS.

### Funzionalità 2: Autorizzazione di Accesso al Calendario per Delegato
#### Panoramica
Questa sezione mostra come **configurare le autorizzazioni del calendario** e garantire che il delegato abbia i diritti corretti.

#### Passi di Implementazione
##### 1️⃣ Inizializzare il Client EWS (riutilizzo)
```java
IEWSClient client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser", "pwd", "domain");
```

##### 2️⃣ Creare e Impostare le Autorizzazioni Delegate
```java
ExchangeDelegateUser delegateUser = new ExchangeDelegateUser("sharingfrom@domain.com", ExchangeDelegateFolderPermissionLevel.NotSpecified);
delegateUser.getFolderPermissions().setCalendarFolderPermissionLevel(ExchangeDelegateFolderPermissionLevel.Reviewer);

client.delegateAccess(delegateUser, "sharingfrom@domain.com");
```
Questo snippet **imposta le autorizzazioni delegate** così l'utente può visualizzare le voci del calendario senza accesso completo alla casella di posta.

## Come configurare le autorizzazioni del calendario per i delegati
Quando hai bisogno che un delegato faccia più che visualizzare gli eventi—come modificare o eliminare—puoi cambiare il `ExchangeDelegateFolderPermissionLevel`:
- `Reviewer` – accesso in sola lettura.  
- `Editor` – accesso lettura/scrittura.  
- `Author` – creare e leggere, ma non può eliminare.  
- `Owner` – controllo totale, incluse le modifiche alle autorizzazioni.

**Consiglio Pro:** Usa il livello di privilegio più basso che soddisfa il requisito aziendale per mantenere sicuri i dati del tuo calendario.

## Applicazioni Pratiche
Scenari reali in cui **gestire la condivisione del calendario** brilla:
1. **Riunioni Aziendali** – Consenti ai membri del team di visualizzare i programmi delle riunioni senza concedere i diritti completi sulla casella di posta.  
2. **Gestione Progetti** – I responsabili di progetto possono monitorare le scadenze mentre gli sviluppatori mantengono il controllo dei propri calendari.  
3. **Pianificazione Eventi** – I fornitori ricevono una **email di condivisione del calendario** per coordinare la logistica senza esporre dettagli interni.

## Considerazioni sulle Prestazioni
- **Gestione della Memoria:** Disporre rapidamente degli oggetti `MailMessage` di grandi dimensioni in applicazioni ad alto volume.  
- **Gestione delle Eccezioni:** Avvolgi le chiamate di rete in blocchi try‑catch per gestire i problemi di connettività in modo elegante.  
- **Aggiornamenti della Libreria:** Mantieni Aspose.Email aggiornato per beneficiare di miglioramenti delle prestazioni e correzioni di bug.

## Problemi Comuni e Soluzioni
| Problema | Probabile Causa | Soluzione |
|-------|--------------|----------|
| Invito non ricevuto | Filtri spam o indirizzo email errato | Verifica l'indirizzo del destinatario e aggiungi il dominio di invio alla lista dei mittenti sicuri |
| Autorizzazione non applicata | Uso di `ExchangeDelegateFolderPermissionLevel` errato | Controlla che il livello di autorizzazione corrisponda all'accesso richiesto |
| Eccezione runtime su `createCalendarSharingInvitationMessage` | Licenza mancante o libreria obsoleta | Assicurati che sia caricata una licenza valida e che tu stia usando l'ultima versione di Aspose.Email |

## Domande Frequenti
**Q: A cosa serve Aspose.Email per Java?**  
A: È una libreria completa per gestire email, calendari e contatti in applicazioni Java, supportando Outlook, Exchange e altri protocolli.

**Q: Come configuro il mio ambiente per usare Aspose.Email?**  
A: Installa JDK 16+, Maven, aggiungi la dipendenza Aspose.Email a `pom.xml` e ottieni una licenza (di prova o completa).

**Q: Posso usare questo codice con altre versioni di Exchange Online?**  
A: Sì, ma verifica che l'URL del servizio e i livelli di autorizzazione corrispondano alla configurazione del tuo server.

**Q: Cosa devo fare se l'invito di condivisione del calendario non viene inviato?**  
A: Controlla la connettività di rete, le credenziali e che l'utente delegato abbia autorizzazioni valide. Esamina i dettagli dell'eccezione per indizi.

**Q: È possibile aggiungere autorizzazioni aggiuntive come modifica o accesso completo?**  
A: Assolutamente – sostituisci `ExchangeDelegateFolderPermissionLevel.Reviewer` con `Editor`, `Author` o `Owner` secondo necessità.

## Conclusione
Ora hai una soluzione completa, end‑to‑end per **creare un invito di condivisione del calendario** con Aspose.Email per Java. Inizializzando il client EWS, **creando l'accesso delegato**, **impostando le autorizzazioni delegate**, e inviando una **email di condivisione del calendario**, puoi automatizzare la collaborazione nella tua organizzazione.

**Passi Successivi**
- Sperimenta altri livelli di autorizzazione (Editor, Owner).  
- Integra questa logica nei tuoi sistemi di pianificazione o HR esistenti.  
- Esplora funzionalità aggiuntive di Aspose.Email come eventi ricorrenti o richieste di riunione.

---

**Last Updated:** 2026-03-20  
**Tested With:** Aspose.Email for Java 25.4 (JDK 16 classifier)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}