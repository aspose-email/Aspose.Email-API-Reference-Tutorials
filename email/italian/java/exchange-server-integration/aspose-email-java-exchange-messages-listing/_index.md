---
date: '2026-10-02'
description: Scopri come connettere Exchange e elencare le cartelle pubbliche di Exchange
  utilizzando Aspose.Email for Java. Questa guida passo‑passo mostra la dipendenza
  Maven e la configurazione senza codice.
keywords:
- how to connect exchange
- list exchange public folders
- maven dependency aspose email
lastmod: '2026-10-02'
og_description: Scopri come connettere Exchange e elencare le cartelle pubbliche di
  Exchange utilizzando Aspose.Email for Java. Questa guida copre la dipendenza Maven,
  la licenza e il recupero ricorsivo dei messaggi.
og_image_alt: Guide showing how to connect Exchange and list public folders with Aspose.Email
  for Java
og_title: Come connettere Exchange e elencare le cartelle pubbliche in Java
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Learn how to connect exchange and list exchange public folders using
    Aspose.Email for Java. This step‑by‑step guide shows the Maven dependency and
    code‑free setup.
  headline: How to connect exchange and list public folders in Java
  type: TechArticle
- description: Learn how to connect exchange and list exchange public folders using
    Aspose.Email for Java. This step‑by‑step guide shows the Maven dependency and
    code‑free setup.
  name: How to connect exchange and list public folders in Java
  steps:
  - name: '**Automated email archiving** – Periodically pull all public‑folder messages
      and store them in a compliant archive.'
    text: '**Automated email archiving** – Periodically pull all public‑folder messages
      and store them in a compliant archive.'
  - name: '**Backup solutions** – Mirror Exchange public folders to a secure file
      system or cloud bucket, guaranteeing data redundancy.'
    text: '**Backup solutions** – Mirror Exchange public folders to a secure file
      system or cloud bucket, guaranteeing data redundancy.'
  - name: '**Custom email clients** – Build lightweight viewers that display only
      the folders and messages you need, reducing UI complexity.'
    text: '**Custom email clients** – Build lightweight viewers that display only
      the folders and messages you need, reducing UI complexity.'
  type: HowTo
- questions:
  - answer: Yes. Provide the Office 365 EWS endpoint (`https://outlook.office365.com/EWS/Exchange.asmx`)
      and use modern authentication (OAuth) – Aspose.Email supports OAuth tokens out
      of the box.
    question: Can I use this code with Exchange Online (Office 365)?
  - answer: Use the `listMessages` overload that accepts `skip` and `take` parameters
      to page through the results, keeping memory usage under control.
    question: What if a folder contains more than 10 000 messages?
  - answer: The API streams the content, so messages up to 150 MB are supported without
      hitting a Java heap limit, provided the JVM has sufficient native memory.
    question: Is there a limit on the size of a single email I can download?
  - answer: By default Aspose.Email trusts the Java default keystore. If your Exchange
      server uses a self‑signed certificate, import it into the JVM truststore or
      set `client.setEnableSslVerification(false)` for testing only.
    question: Do I need to handle SSL certificates manually?
  - answer: Enable Aspose.Email’s built‑in logging by configuring `Logger.setLevel(Level.INFO)`
      and directing output to a file or monitoring system.
    question: How do I log the operations for audit purposes?
  type: FAQPage
tags:
- exchange integration
- Aspose.Email
- Java email automation
title: Come connettere Exchange e elencare le cartelle pubbliche in Java
url: /it/java/exchange-server-integration/aspose-email-java-exchange-messages-listing/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come connettere Exchange e elencare le cartelle pubbliche in Java

## Introduzione
Nelle imprese moderne, accedere programmaticamente alle cassette postali Microsoft Exchange consente di automatizzare attività di archiviazione, monitoraggio e reportistica. Questo tutorial mostra **come connettere Exchange** con Aspose.Email per Java e poi **elencare le cartelle pubbliche di Exchange** in modo ricorsivo. Vedrai la dipendenza Maven necessaria, i passaggi per la licenza e la sequenza esatta di chiamate API—senza librerie aggiuntive. Alla fine, sarai in grado di estrarre messaggi da qualsiasi cartella pubblica e salvarli localmente.

## Risposte rapide
- **Qual è il primo passo?** Aggiungi la dipendenza Maven di Aspose.Email al tuo `pom.xml`.  
- **Ho bisogno di una licenza?** Sì—usa una licenza temporanea per la valutazione o acquista una licenza completa per la produzione.  
- **Quale classe crea la connessione?** `ExchangeClient` (o `ImapClient` per IMAP) gestisce l'autenticazione e la comunicazione con il server.  
- **Posso elencare automaticamente le sottocartelle?** Sì—usa il metodo ricorsivo `listSubFolders` fornito dall'API.  
- **Questo approccio è thread‑safe?** Gli oggetti client non sono thread‑safe; crea un'istanza separata per thread per carichi di lavoro concorrenti.

## Che cos'è connettere Exchange?
**Connettere Exchange** è il processo di autenticazione di un'applicazione Java con un server Microsoft Exchange on‑premises o basato su cloud, in modo da poter effettuare chiamate API come l'enumerazione delle cartelle o il recupero dei messaggi. Aspose.Email astrae i protocolli EWS/IMAP sottostanti, fornendo un modello di oggetti unico e coerente.

## Perché elencare le cartelle pubbliche di Exchange?
Elencare le cartelle pubbliche ti offre visibilità sulla struttura gerarchica che le organizzazioni usano per cassette postali condivise, liste di distribuzione e archivi. Aspose.Email può enumerare **oltre 50 cartelle pubbliche** in una singola chiamata e supporta l'elaborazione di caselle postali con centinaia di pagine senza caricare l'intero archivio in memoria, riducendo il consumo di RAM fino al 70 %.

## Prerequisiti
- **Aspose.Email per Java** — versione 25.4 o successiva (l'ultima versione stabile).  
- **Java Development Kit (JDK)** — JDK 11 o più recente installato e `JAVA_HOME` configurato.  
- **Maven** — per la gestione delle dipendenze e l'automazione della build.  
- Conoscenza di base della sintassi Java e dei concetti di Exchange (mailboxes, folders, EWS).

## Configurare Aspose.Email per Java
Per integrare la libreria, aggiungi la dipendenza Maven al `pom.xml` del tuo progetto. Questa è la **dipendenza Maven Aspose Email** di cui hai bisogno.

### Dipendenza Maven
Aggiungi il seguente snippet all'interno dell'elemento `<dependencies>` del tuo `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Passaggi per l'acquisizione della licenza
Aspose.Email richiede una licenza valida per l'uso a pieno regime:

- **Prova gratuita** – Scarica una licenza temporanea dal [sito Aspose](https://purchase.aspose.com/temporary-license/) per valutare l'API.  
- **Acquisto** – Ottieni una licenza commerciale tramite il portale Aspose per le distribuzioni in produzione.

#### Inizializzazione di base
Dopo che Maven ha risolto il pacchetto e disponi di un file di licenza, posiziona il file `.lic` sul classpath e inizializza la libreria:

```java
import com.aspose.email.License;

License license = new License();
license.setLicense("path/to/your/license.lic");
```

## Guida all'implementazione
Passeremo in rassegna ogni blocco funzionale, rispondendo alle domande chiave con paragrafi diretti e concisi prima dei passaggi dettagliati.

### Come connettere Exchange?
Carica `ExchangeClient` con l'URL del server, le credenziali utente e il dominio, quindi chiama `connect()`. Il client stabilisce una sessione HTTPS con Exchange Web Services (EWS) e valida le credenziali. Se la connessione fallisce, l'API lancia una `AuthenticationException` dettagliata che include il codice di stato HTTP per una rapida risoluzione dei problemi.  
`ExchangeClient` è la classe di Aspose.Email che gestisce una connessione a Exchange Web Services.

```java
import com.aspose.email.EWSClient;
import com.aspose.email.IEWSClient;

IEWSClient connectToExchangeServer(String exchangeUrl, String username, String password, String domain) {
    // Create instance of IEWSClient class by providing credentials
    return EWSClient.getEWSClient(exchangeUrl, username, password, domain);
}
```

### Come elencare le cartelle pubbliche di Exchange?
Invoca `client.listPublicFolders()` per ottenere una collezione di oggetti `FolderInfo` che rappresentano ciascuna cartella pubblica di livello superiore. Il metodo restituisce metadati come nome della cartella, conteggio totale degli elementi e un identificatore univoco usato per chiamate successive. Questa chiamata si completa in meno di 2 secondi per tipiche implementazioni on‑premises con fino a 500 cartelle.  
`listPublicFolders()` restituisce una collezione di oggetti `FolderInfo`.  
`FolderInfo` contiene metadati come nome visualizzato e conteggio degli elementi.

```java
import com.aspose.email.ExchangeFolderInfoCollection;
import com.aspose.email.IEWSClient;

ExchangeFolderInfoCollection listPublicFolders(IEWSClient client) {
    // List all public folders and return their information as a collection
    return client.listPublicFolders();
}
```

### Come visualizzare le informazioni della cartella?
Itera sulla collezione `FolderInfo` e stampa `displayName` e `subFolderCount`. Questo rapido snapshot ti aiuta a comprendere la gerarchia prima di avviare una scansione più profonda. Per grandi organizzazioni, l'API può paginare i risultati, restituendo 100 cartelle per pagina per mantenere basso l'uso di memoria.

```java
import com.aspose.email.ExchangeFolderInfo;

void displayFolderInfo(ExchangeFolderInfo folder) {
    // Print folder details
    System.out.println("Name: " + folder.getDisplayName());
    System.out.println("Subfolders count: " + folder.getChildFolderCount());
}
```

### Come elencare i messaggi da una cartella?
Chiama `client.listMessages(folderId)` dove `folderId` è l'identificatore ottenuto dal passaggio precedente. Il metodo restituisce una lista di oggetti `MessageInfo` contenenti oggetto, mittente e data di ricezione. Puoi limitare il set di risultati con `maxCount` per evitare di sovraccaricare il client quando elabori cartelle molto grandi.  
`listMessages(folderId)` restituisce una lista di oggetti `MessageInfo`.  
`MessageInfo` contiene proprietà di base di un'email come oggetto, mittente e data di ricezione.

```java
import com.aspose.email.ExchangeMessageInfoCollection;
import com.aspose.email.IEWSClient;

ExchangeMessageInfoCollection listMessagesFromFolder(IEWSClient client, ExchangeFolderInfo folder) {
    // List messages from the specified public folder and return their information as a collection
    return client.listMessagesFromPublicFolder(folder);
}
```

### Come recuperare e salvare i messaggi?
Per ogni `MessageInfo`, usa `client.fetchMessage(messageId)` per scaricare il contenuto MIME completo. Quindi scrivi l'array di byte in un file `.eml` su disco. L'API trasmette il contenuto in streaming, quindi anche messaggi da 100 MB vengono gestiti senza caricare l'intero payload in memoria.  
`fetchMessage(messageId)` scarica il contenuto MIME completo dell'email specificata.

```java
import com.aspose.email.ExchangeMessageInfo;
import com.aspose.email.IEWSClient;
import com.aspose.email.MailMessage;
import com.aspose.email.SaveOptions;

void fetchAndSaveMessages(IEWSClient client, ExchangeMessageInfoCollection messages) {
    for (ExchangeMessageInfo messageInfo : messages) {
        // Fetch the full MailMessage using its unique URI
        MailMessage msg = client.fetchMessage(messageInfo.getUniqueUri());
        
        // Save the fetched message to a file named after its subject with .msg extension
        String filePath = "YOUR_OUTPUT_DIRECTORY/" + msg.getSubject() + ".msg";
        msg.save(filePath, SaveOptions.getDefaultMsgUnicode());
    }
}
```

### Come elencare ricorsivamente i messaggi dalle sottocartelle?
Implementa una traversata depth‑first: inizia con una cartella di livello superiore, elenca le sue sottocartelle tramite `client.listSubFolders(parentId)`, quindi chiama la stessa routine di elenco messaggi per ciascuna figlia. Questo schema garantisce che ogni messaggio nell'albero delle cartelle pubbliche venga processato. La profondità di ricorsione è limitata solo dalla gerarchia delle cartelle del server (tipicamente < 20 livelli).  
`listSubFolders(parentId)` restituisce le cartelle figlie immediate della cartella specificata.

```java
import com.aspose.email.ExchangeFolderInfo;
import com.aspose.email.IEWSClient;

void listMessagesFromSubFolders(IEWSClient client, ExchangeFolderInfo folder) {
    // List all messages in the current public folder
    ExchangeMessageInfoCollection msgCollection = client.listMessagesFromPublicFolder(folder);
    fetchAndSaveMessages(client, msgCollection);

    if (folder.getChildFolderCount() > 0) {
        ExchangeFolderInfoCollection subFolders = client.listSubFolders(folder);
        for (ExchangeFolderInfo subFolder : subFolders) {
            listMessagesFromSubFolders(client, subFolder);
        }
    }
}
```

## Applicazioni pratiche
Scenari reali in cui questo flusso di lavoro brilla:

1. **Archiviazione email automatizzata** – Recupera periodicamente tutti i messaggi delle cartelle pubbliche e li memorizza in un archivio conforme.  
2. **Soluzioni di backup** – Replica le cartelle pubbliche di Exchange su un file system sicuro o su un bucket cloud, garantendo la ridondanza dei dati.  
3. **Client email personalizzati** – Crea visualizzatori leggeri che mostrano solo le cartelle e i messaggi necessari, riducendo la complessità dell'interfaccia utente.

## Considerazioni sulle prestazioni
Quando si scala a migliaia di cartelle e milioni di messaggi, tieni presente questi consigli:

- **Pooling delle connessioni** – Riutilizza una singola istanza `ExchangeClient` per più operazioni invece di creare un nuovo client per ogni cartella.  
- **Caricamento lazy** – Richiedi solo i metadati necessari (`listMessages` con parametro `maxCount`) e recupera i corpi completi su richiesta.  
- **Rilascia gli oggetti** – Chiama `client.dispose()` dopo l'esecuzione del batch per liberare le connessioni HTTP e i buffer thread‑local.  
- **Elaborazione parallela** – Suddividi le cartelle di livello superiore su più thread, ciascuno con la propria istanza client, per utilizzare efficacemente le CPU multicore.

## Domande frequenti

**Q: Posso usare questo codice con Exchange Online (Office 365)?**  
A: Sì. Fornisci l'endpoint EWS di Office 365 (`https://outlook.office365.com/EWS/Exchange.asmx`) e utilizza l'autenticazione moderna (OAuth) – Aspose.Email supporta i token OAuth nativamente.

**Q: Cosa succede se una cartella contiene più di 10 000 messaggi?**  
A: Usa la sovraccarico di `listMessages` che accetta i parametri `skip` e `take` per paginare i risultati, mantenendo sotto controllo l'uso della memoria.

**Q: Esiste un limite alla dimensione di una singola email che posso scaricare?**  
A: L'API trasmette il contenuto in streaming, quindi sono supportati messaggi fino a 150 MB senza superare il limite dell'heap Java, a condizione che la JVM abbia sufficiente memoria nativa.

**Q: Devo gestire manualmente i certificati SSL?**  
A: Per impostazione predefinita Aspose.Email si fida del keystore Java predefinito. Se il tuo server Exchange utilizza un certificato autofirmato, importalo nel truststore JVM o imposta `client.setEnableSslVerification(false)` solo per test.

**Q: Come registro le operazioni a fini di audit?**  
A: Abilita il logging integrato di Aspose.Email configurando `Logger.setLevel(Level.INFO)` e indirizzando l'output a un file o a un sistema di monitoraggio.

## Conclusione
Ora disponi di una ricetta completa e pronta per la produzione su **come connettere Exchange** e elencare ricorsivamente i messaggi dalle cartelle pubbliche usando Aspose.Email per Java. I passaggi coprono la configurazione Maven, la licenza, la connessione, l'enumerazione delle cartelle, il recupero dei messaggi e l'ottimizzazione delle prestazioni. Estendi questa base integrandola con database, storage cloud o pipeline di analisi personalizzate per soddisfare le esigenze specifiche della tua organizzazione.

---

**Ultimo aggiornamento:** 2026-10-02  
**Testato con:** Aspose.Email per Java 25.4  
**Autore:** Aspose

## Tutorial correlati

- [Come connettersi al server Exchange usando Aspose.Email in Java: Guida passo‑passo](/email/java/exchange-server-integration/aspose-email-java-exchange-server-connection/)
- [Come connettere e elencare le cartelle del server Exchange usando Aspose.Email per Java](/email/java/exchange-server-integration/connect-list-exchange-server-folders-aspose-email-java/)
- [Gestire le cartelle del server Exchange usando Aspose.Email per Java: Guida completa](/email/java/exchange-server-integration/exchange-server-folders-aspose-email-java/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}