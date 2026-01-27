---
date: '2026-01-27'
description: Scopri come spostare cartelle e messaggi PST usando Aspose.Email per
  Java – una guida passo‑passo su come spostare i PST in modo efficiente.
keywords:
- Aspose.Email Java
- move PST folders
- email management with Aspose
- PST file manipulation in Java
title: Come spostare le cartelle e i messaggi PST con Aspose.Email Java
url: /it/java/email-message-operations/aspose-email-java-move-pst-messages-folders/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Gestione avanzata della posta elettronica con Aspose.Email Java: spostare cartelle e messaggi PST

Una gestione efficiente della posta elettronica è fondamentale, soprattutto quando si gestiscono grandi volumi di dati nei file PST di Outlook. In questa guida mostreremo **come spostare pst** cartelle e messaggi in modo programmatico usando Aspose.Email per Java, così potrai mantenere le cassette di posta ordinate e automatizzare le attività di migrazione.

## Risposte rapide
- **Quale libreria viene utilizzata?** Aspose.Email for Java  
- **Posso spostare sia cartelle che messaggi individuali?** Sì, usando le API `moveItem` e `moveSubfolders`  
- **È necessaria una licenza per la produzione?** È necessaria una licenza Aspose valida per l'uso commerciale  
- **Quale versione di Java è consigliata?** Java 16 o successiva  
- **È incluso un file PST di esempio?** Usa qualsiasi PST generato da Outlook per i test  

## Cos'è “come spostare pst” nel contesto dello sviluppo Java?
Spostare i dati PST significa spostare programmaticamente cartelle o elementi di posta all'interno di un file Personal Storage Table (PST). Questo è utile per pulizie di massa, archiviazione o migrazione di contenuti tra archivi di posta senza l'interazione manuale con Outlook.

## Perché usare Aspose.Email per Java per spostare dati PST?
- **Nessuna dipendenza da Outlook** – funziona su qualsiasi piattaforma con un runtime Java.  
- **API PST completa** – supporta la creazione, l'eliminazione di cartelle e lo spostamento di elementi.  
- **Alte prestazioni** – ottimizzato per cassette di posta di grandi dimensioni.  
- **Gestione robusta degli errori** – eccezioni dettagliate ti aiutano a risolvere rapidamente i problemi.

## Prerequisiti
- **Aspose.Email per Java** (ultima versione)  
- **JDK 16+** (o più recente)  
- Sistema di build Maven o Gradle  
- Un file `.pst` di esempio per i test  

## Configurazione di Aspose.Email per Java
Per utilizzare Aspose.Email, includilo nel tuo progetto. Se usi Maven, aggiungi la seguente dipendenza al file `pom.xml`:
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
2. **Licenza temporanea** – ottieni una licenza temporanea per un uso prolungato dal [sito di Aspose](https://purchase.aspose.com/temporary-license/).  
3. **Acquisto** – considera l'acquisto di una licenza completa se la libreria soddisfa le tue esigenze di produzione.  

### Inizializzazione e configurazione di base
Assicurati che la libreria sia correttamente referenziata nella configurazione del tuo progetto per iniziare a lavorare con i file PST:
```java
import com.aspose.email.PersonalStorage;
import com.aspose.email.StandardIpmFolder;

PersonalStorage pst = PersonalStorage.fromFile("YOUR_DOCUMENT_DIRECTORY/test.pst");
```

## Come spostare cartelle e messaggi PST
Di seguito le operazioni principali che dovrai conoscere quando vuoi spostare **come spostare pst** elementi in modo efficiente.

### Inizializzare e accedere al file PST
**Panoramica**: Impara a inizializzare un file PST e accedere alle sue cartelle predefinite come Posta in arrivo e Elementi eliminati.  

#### Passo 1: Caricare il file PST
```java
PersonalStorage pst = PersonalStorage.fromFile("YOUR_DOCUMENT_DIRECTORY/test.pst");
```

#### Passo 2: Accedere alle cartelle predefinite
- **Cartella Posta in arrivo**:
    ```java
    FolderInfo inbox = pst.getPredefinedFolder(StandardIpmFolder.Inbox);
    ```
- **Cartella Elementi eliminati**:
    ```java
    FolderInfo deletedItems = pst.getPredefinedFolder(StandardIpmFolder.DeletedItems);
    ```

### Spostare una sottocartella in un'altra cartella nel PST
**Panoramica**: Sposta un'intera sottocartella da una cartella a un'altra all'interno del file PST.

#### Passo 1: Accedere alle cartelle di origine e destinazione
```java
FolderInfo inbox = pst.getPredefinedFolder(StandardIpmFolder.Inbox);
FolderInfo deletedItems = pst.getPredefinedFolder(StandardIpmFolder.DeletedItems);
```

#### Passo 2: Ottenere una specifica sottocartella dalla Posta in arrivo
```java
FolderInfo subfolder = inbox.getSubFolder("Subfolder");
```

#### Passo 3: Spostare l'intera sottocartella
```java
pst.moveItem(subfolder, deletedItems);
```

### Spostare messaggi individuali tra cartelle nel PST
**Panoramica**: Sposta singoli messaggi email da una cartella a un'altra.

#### Passo 1: Recuperare i messaggi da una specifica sottocartella
```java
FolderInfo subfolder = inbox.getSubFolder("Subfolder");
MessageInfoCollection contents = subfolder.getContents();
```

#### Passo 2: Spostare il primo messaggio nella cartella Elementi eliminati
```java
pst.moveItem(contents.get_Item(0), deletedItems);
```

### Spostare tutte le sottocartelle da una cartella a un'altra nel PST
**Panoramica**: Trasferisci ogni sottocartella da una cartella di origine (ad es., Posta in arrivo) a una cartella di destinazione (ad es., Elementi eliminati).

#### Passo 1: Accedere alle cartelle di origine e destinazione
```java
FolderInfo inbox = pst.getPredefinedFolder(StandardIpmFolder.Inbox);
FolderInfo deletedItems = pst.getPredefinedFolder(StandardIpmFolder.DeletedItems);
```

#### Passo 2: Spostare tutte le sottocartelle
```java
inbox.moveSubfolders(deletedItems);
```

### Spostare tutti i contenuti di una sottocartella in un'altra cartella nel PST
**Panoramica**: Rilocare ogni messaggio all'interno di una sottocartella in una cartella diversa.

#### Passo 1: Accedere alle cartelle di origine e destinazione
```java
FolderInfo inbox = pst.getPredefinedFolder(StandardIpmFolder.Inbox);
FolderInfo deletedItems = pst.getPredefinedFolder(StandardIpmFolder.DeletedItems);
```

#### Passo 2: Ottenere una specifica sottocartella dalla Posta in arrivo
```java
FolderInfo subfolder = inbox.getSubFolder("Subfolder");
```

#### Passo 3: Spostare tutti i contenuti della sottocartella
```java
subfolder.moveContents(deletedItems);
```

## Applicazioni pratiche
Spostare cartelle e messaggi PST può essere utile in scenari come:
- **Migrazione dei dati** – passare da Outlook a un altro sistema di posta.  
- **Archiviazione delle email** – organizzare sistematicamente le vecchie email in cartelle di archivio.  
- **Operazioni di pulizia** – liberare le caselle di posta spostando elementi obsoleti.  

## Considerazioni sulle prestazioni
Quando lavori con file PST usando Aspose.Email in Java, tieni presente questi consigli:
- **Ottimizza l'uso delle risorse** – chiudi rapidamente gli oggetti `PersonalStorage` (try‑with‑resources o `dispose` esplicito).  
- **Gestione della memoria** – evita di caricare intere cartelle grandi in memoria; elabora gli elementi in batch.  

### Buone pratiche
- Rilascia sempre le risorse PST dopo le operazioni.  
- Verifica l'esistenza della cartella prima di tentare gli spostamenti per prevenire eccezioni.  

## Domande frequenti
**D1: Cos'è un file PST?**  
R1: Un file PST (Personal Storage Table) è utilizzato da Microsoft Outlook per memorizzare localmente messaggi email, contatti, elementi del calendario e altri dati.

**D2: Posso usare Aspose.Email per Java in progetti commerciali?**  
R2: Sì, puoi usarlo commercialmente a condizione di possedere una licenza valida ottenuta tramite le [opzioni di acquisto di Aspose](https://purchase.aspose.com/buy).

**D3: Come gestisco le eccezioni quando lavoro con file PST usando Aspose.Email?**  
R3: Avvolgi il tuo codice in blocchi `try‑catch` per catturare `IOException`, `InvalidOperationException` o eccezioni specifiche di Aspose e registra o rilancia secondo necessità.

**D4: Quali sono i requisiti di sistema per eseguire questo codice?**  
R4: Hai bisogno di JDK 16 o più recente e di un IDE compatibile come IntelliJ IDEA o Eclipse. Il JAR di Aspose.Email deve essere incluso nel classpath del tuo progetto.

**D5: Dove posso trovare ulteriori risorse su Aspose.Email per Java?**  
R5: Visita la documentazione ufficiale su [Aspose Email Java Reference](https://reference.aspose.com/email/java/).

**D6: Aspose.Email supporta file PST protetti da password?**  
R6: Sì, è possibile aprire PST crittografati fornendo la password durante la chiamata a `PersonalStorage.fromFile`.

**D7: Come posso verificare che un'operazione di spostamento sia riuscita?**  
R7: Dopo aver chiamato `moveItem` o `moveSubfolders`, interroga la cartella di destinazione con `getContents()` o `getSubFolders()` per confermare la presenza degli elementi spostati.

---

**Ultimo aggiornamento:** 2026-01-27  
**Testato con:** Aspose.Email per Java 25.4 (JDK 16)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

## Risorse
- **Documentazione**: [Aspose Email Java Reference](https://reference.aspose.com/email/java/)
- **Download**: [Aspose Email Java Releases](https://releases.aspose.com/email/java/)
- **Acquisto**: [Buy Aspose Products](https://purchase.aspose.com/buy)
- **Prova gratuita**: [Aspose Free Trials](https://releases.aspose.com/email/java/)
- **Licenza temporanea**: [Get a Temporary License](https://purchase.aspose.com/temporary-license/)