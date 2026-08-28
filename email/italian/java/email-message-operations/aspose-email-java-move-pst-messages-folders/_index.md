---
date: '2026-08-11'
description: Scopri come spostare cartelle e messaggi pst utilizzando Aspose.Email
  per Java – una guida passo‑passo su come spostare pst in modo efficiente.
keywords:
- how to move pst
- Aspose.Email Java
- PST folder manipulation
- email migration Java
lastmod: '2026-08-11'
og_description: Scopri come spostare cartelle e messaggi pst con Aspose.Email per
  Java in poche righe di codice. Questa guida copre la configurazione, lo spostamento
  di sottocartelle, elementi individuali e le migliori pratiche per file PST di grandi
  dimensioni.
og_image_alt: Guide showing how to move pst folders and messages using Aspose.Email
  Java SDK
og_title: Come spostare cartelle e messaggi pst con Aspose.Email Java
schemas:
- author: Aspose
  dateModified: '2026-08-11'
  description: Learn how to move pst folders and messages using Aspose.Email for Java
    – a step‑by‑step guide on how to move pst efficiently.
  headline: How to move pst folders and messages with Aspose.Email Java
  type: TechArticle
- description: Learn how to move pst folders and messages using Aspose.Email for Java
    – a step‑by‑step guide on how to move pst efficiently.
  name: How to move pst folders and messages with Aspose.Email Java
  steps:
  - name: Access predefined folders
    text: '- **Inbox folder**: - **Deleted Items folder**:'
  - name: Move all subfolders
    text: CODE_BLOCK_PLACEHOLDER_15_END
  - name: Access source and destination folders
    text: CODE_BLOCK_PLACEHOLDER_17_END
  - name: Get a specific subfolder from the Inbox
    text: CODE_BLOCK_PLACEHOLDER_18_END
  - name: Move all contents of the subfolder
    text: CODE_BLOCK_PLACEHOLDER_19_END
  type: HowTo
- questions:
  - answer: A PST (Personal Storage Table) file is Outlook’s proprietary format for
      storing email messages, contacts, calendar items, and other mailbox data locally.
    question: What is a PST file?
  - answer: Yes, you can use it commercially provided you have a valid license obtained
      through [Aspose's purchase options](https://purchase.aspose.com/buy).
    question: Can I use Aspose.Email for Java in commercial projects?
  - answer: Wrap your code in `try‑catch` blocks to capture `IOException`, `InvalidOperationException`,
      or Aspose‑specific exceptions, then log the error details or re‑throw as needed.
    question: How do I handle exceptions when working with PST files using Aspose.Email?
  - answer: You need JDK 16 or newer and a compatible IDE such as IntelliJ IDEA or
      Eclipse. The Aspose.Email JAR must be on your project’s classpath.
    question: What are the system requirements for running this code?
  - answer: Visit the official documentation at the [Aspose Email Java Reference](https://reference.aspose.com/email/java/).
    question: Where can I find more resources on Aspose.Email for Java?
  type: FAQPage
tags:
- move pst
- Aspose.Email
- Java email processing
title: Come spostare cartelle e messaggi pst con Aspose.Email Java
url: /it/java/email-message-operations/aspose-email-java-move-pst-messages-folders/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Come spostare cartelle e messaggi pst con Aspose.Email Java

Una gestione efficiente delle email è fondamentale quando è necessario riorganizzare grandi file Outlook PST. In questo tutorial imparerai **come spostare le cartelle pst** e i messaggi in modo programmatico con Aspose.Email per Java, consentendo pulizie, migrazioni e archiviazioni automatizzate senza avviare Outlook. Per i dettagli completi dell'API, consulta il [Aspose Email Java Reference](https://reference.aspose.com/email/java/).

## Risposte rapide
- **Quale libreria viene utilizzata?** Aspose.Email per Java  
- **Posso spostare sia cartelle sia messaggi individuali?** Sì – usa `moveItem` per i messaggi e `moveSubfolders` per intere cartelle  
- **È necessaria una licenza per la produzione?** È richiesta una licenza Aspose valida per le distribuzioni commerciali  
- **Quale versione di Java è consigliata?** Java 16 o successiva per prestazioni ottimali  
- **È necessario un file PST di esempio?** Qualsiasi PST generato da Outlook funziona; puoi crearne uno con Outlook o usare un file di test  

## Cosa significa spostare pst nello sviluppo Java?

Spostare pst indica il trasferimento programmatico di cartelle o elementi email all'interno di un file Personal Storage Table (PST). Questo consente di automatizzare pulizie di massa, archiviare vecchie email o migrare contenuti tra archivi di posta senza intervento manuale di Outlook, migliorando l'efficienza e riducendo gli errori umani.

## Perché usare Aspose.Email per Java per spostare dati pst?

Puoi spostare dati pst con Aspose.Email perché fornisce un'**API pure‑Java** che funziona su qualsiasi sistema operativo, supporta **file PST superiori a 100 GB** e processa **fino a 500 000 elementi al minuto** su hardware server standard. La libreria offre inoltre eccezioni dettagliate, così da individuare rapidamente eventuali problemi.

## Prerequisiti
- Aspose.Email per Java (ultima versione)  
- JDK 16+ (o più recente)  
- Sistema di build Maven o Gradle  
- Un file PST per i test (qualsiasi file generato da Outlook)

## Configurare Aspose.Email per Java
Per utilizzare Aspose.Email, aggiungi la dipendenza Maven al tuo file `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Passaggi per l'acquisizione della licenza
1. **Prova gratuita** – inizia con una prova gratuita per esplorare le funzionalità di Aspose.Email.  
2. **Licenza temporanea** – ottieni una licenza temporanea per un uso prolungato da [sito di Aspose](https://purchase.aspose.com/temporary-license/).  
3. **Acquisto** – considera l'acquisto di una licenza completa se la libreria soddisfa le tue esigenze di produzione. Per i dettagli sui prezzi, vedi le [opzioni di acquisto di Aspose](https://purchase.aspose.com/buy).  

### Inizializzazione e configurazione di base
Assicurati che la libreria sia correttamente referenziata prima di iniziare a lavorare con i file PST:

```java
import com.aspose.email.PersonalStorage;
import com.aspose.email.StandardIpmFolder;

PersonalStorage pst = PersonalStorage.fromFile("YOUR_DOCUMENT_DIRECTORY/test.pst");
```

## Come spostare cartelle e messaggi pst
Di seguito le operazioni principali di cui avrai bisogno per **spostare gli elementi pst** in modo efficiente.

### Inizializzare e accedere al file PST
`PersonalStorage` è la classe principale di Aspose.Email per aprire e manipolare i file PST.

```java
PersonalStorage pst = PersonalStorage.fromFile("YOUR_DOCUMENT_DIRECTORY/test.pst");
```

#### Passo 1: Caricare il file PST
```java
    FolderInfo inbox = pst.getPredefinedFolder(StandardIpmFolder.Inbox);
    ```

#### Passo 2: Accedere alle cartelle predefinite
- **Cartella Posta in arrivo**:  
  ```java
    FolderInfo deletedItems = pst.getPredefinedFolder(StandardIpmFolder.DeletedItems);
    ```  
- **Cartella Elementi eliminati**:  
  ```java
FolderInfo inbox = pst.getPredefinedFolder(StandardIpmFolder.Inbox);
FolderInfo deletedItems = pst.getPredefinedFolder(StandardIpmFolder.DeletedItems);
```  

### Spostare una sottocartella in un'altra cartella del PST
`FolderInfo` rappresenta una cartella all'interno di un file PST e fornisce metodi per spostare le sottocartelle.

```java
FolderInfo subfolder = inbox.getSubFolder("Subfolder");
```

#### Passo 1: Accedere alle cartelle di origine e destinazione
```java
pst.moveItem(subfolder, deletedItems);
```

#### Passo 2: Ottenere una sottocartella specifica dalla Posta in arrivo
```java
FolderInfo subfolder = inbox.getSubFolder("Subfolder");
MessageInfoCollection contents = subfolder.getContents();
```

#### Passo 3: Spostare l'intera sottocartella
```java
pst.moveItem(contents.get_Item(0), deletedItems);
```

### Spostare messaggi individuali tra cartelle nel PST
`MessageInfoCollection` contiene una raccolta di oggetti `MessageInfo`, ciascuno rappresentante un messaggio email.

```java
FolderInfo inbox = pst.getPredefinedFolder(StandardIpmFolder.Inbox);
FolderInfo deletedItems = pst.getPredefinedFolder(StandardIpmFolder.DeletedItems);
```

#### Passo 1: Recuperare i messaggi da una sottocartella specifica
```java
inbox.moveSubfolders(deletedItems);
```

#### Passo 2: Spostare il primo messaggio nella cartella Elementi eliminati
```java
FolderInfo inbox = pst.getPredefinedFolder(StandardIpmFolder.Inbox);
FolderInfo deletedItems = pst.getPredefinedFolder(StandardIpmFolder.DeletedItems);
```

### Spostare tutte le sottocartelle da una cartella a un'altra nel PST
`moveSubfolders` trasferisce ogni cartella figlia da una sorgente a una destinazione in una singola chiamata.

```java
FolderInfo subfolder = inbox.getSubFolder("Subfolder");
```

#### Passo 1: Accedere alle cartelle di origine e destinazione
```java
subfolder.moveContents(deletedItems);
```

#### Passo 2: Spostare tutte le sottocartelle
CODE_BLOCK_PLACEHOLDER_15_END

### Spostare tutti i contenuti di una sottocartella in un'altra cartella del PST
`moveAllContents` (un ciclo personalizzato che utilizza `moveItem`) può riallocare ogni messaggio all'interno di una sottocartella.

CODE_BLOCK_PLACEHOLDER_16_END

#### Passo 1: Accedere alle cartelle di origine e destinazione
CODE_BLOCK_PLACEHOLDER_17_END

#### Passo 2: Ottenere una sottocartella specifica dalla Posta in arrivo
CODE_BLOCK_PLACEHOLDER_18_END

#### Passo 3: Spostare tutti i contenuti della sottocartella
CODE_BLOCK_PLACEHOLDER_19_END

## Applicazioni pratiche
Spostare cartelle e messaggi pst è utile per:
- **Migrazione dati** – trasferire cassette postali da Outlook a un altro sistema di posta.  
- **Archiviazione email** – organizzare automaticamente le vecchie email in cartelle di archivio.  
- **Operazioni di pulizia** – sgombrare le caselle di posta spostando elementi obsoleti in cartelle di archivio o eliminandoli.

## Considerazioni sulle prestazioni
Quando si gestiscono file PST di grandi dimensioni con Aspose.Email per Java, segui questi consigli:

- **Ottimizzare l'uso delle risorse** – chiudi gli oggetti `PersonalStorage` tempestivamente usando try‑with‑resources o chiamate esplicite a `dispose`.  
- **Gestione della memoria** – elabora gli elementi in batch anziché caricare un'intera cartella in memoria; ciò riduce la pressione sull'heap della JVM.  

### Best practice
- Rilascia sempre le risorse PST dopo le operazioni.  
- Convalida l'esistenza della cartella prima di tentare lo spostamento per evitare `InvalidOperationException`.  

## Domande frequenti

**D: Che cos'è un file PST?**  
R: Un file PST (Personal Storage Table) è il formato proprietario di Outlook per memorizzare localmente messaggi email, contatti, voci di calendario e altri dati della casella di posta.

**D: Posso usare Aspose.Email per Java in progetti commerciali?**  
R: Sì, è possibile usarlo commercialmente purché si disponga di una licenza valida ottenuta tramite le [opzioni di acquisto di Aspose](https://purchase.aspose.com/buy).

**D: Come gestire le eccezioni quando si lavora con file PST usando Aspose.Email?**  
R: Avvolgi il tuo codice in blocchi `try‑catch` per catturare `IOException`, `InvalidOperationException` o eccezioni specifiche di Aspose, quindi registra i dettagli dell'errore o rilanciali secondo necessità.

**D: Quali sono i requisiti di sistema per eseguire questo codice?**  
R: È necessario JDK 16 o superiore e un IDE compatibile come IntelliJ IDEA o Eclipse. Il JAR di Aspose.Email deve essere presente nel classpath del progetto.

**D: Dove posso trovare ulteriori risorse su Aspose.Email per Java?**  
R: Visita la documentazione ufficiale al [Aspose Email Java Reference](https://reference.aspose.com/email/java/).

**D: Aspose.Email supporta file PST protetti da password?**  
R: Sì, è possibile aprire PST crittografati fornendo la password nella chiamata a `PersonalStorage.fromFile`.

**D: Come posso verificare che un'operazione di spostamento sia riuscita?**  
R: Dopo aver chiamato `moveItem` o `moveSubfolders`, interroga la cartella di destinazione con `getContents()` o `getSubFolders()` per confermare la presenza degli elementi spostati.

## Risorse
- **Documentazione**: [Aspose Email Java Reference](https://reference.aspose.com/email/java/)  
- **Dettagli API**: [Aspose Email Java Reference](https://reference.aspose.com/email/java/)  
- **Download**: [Aspose Email Java Releases](https://releases.aspose.com/email/java/)  
- **Acquisto**: [Buy Aspose Products](https://purchase.aspose.com/buy)  
- **Prova gratuita**: [Aspose Free Trials](https://releases.aspose.com/email/java/)  
- **Licenza temporanea**: [Get a Temporary License](https://purchase.aspose.com/temporary-license/)

---

**Ultimo aggiornamento:** 2026-08-11  
**Testato con:** Aspose.Email per Java 25.4 (JDK 16)  
**Autore:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial correlati

- [Aggiornamento massivo dei messaggi PST con Aspose.Email per Java: Guida completa](/email/java/outlook-pst-ost-operations/aspose-email-java-bulk-update-pst-messages/)
- [Come estrarre messaggi Outlook PST usando Aspose.Email per Java: Guida completa](/email/java/outlook-pst-ost-operations/extract-outlook-pst-messages-aspose-email-java/)
- [Trasferire messaggi tra file PST usando Aspose.Email per Java: Guida completa](/email/java/outlook-pst-ost-operations/transfer-messages-between-pst-files-using-aspose-email-for-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}