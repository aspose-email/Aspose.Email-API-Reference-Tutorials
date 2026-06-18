---
date: '2026-06-08'
description: Scopri come creare file PST con Aspose.Email for Java, inclusa la creazione
  di strutture di cartelle e la ricerca efficiente del contenuto dei PST. Guida passo‑passo.
keywords:
- how to create pst
- how to add folder
- how to search pst
schemas:
- author: Aspose
  dateModified: '2026-06-08'
  description: Learn how to create PST files with Aspose.Email for Java, including
    how to add folder structures and how to search PST content efficiently. Step‑by‑step
    guide.
  headline: How to Create PST Files with Aspose.Email for Java
  type: TechArticle
- description: Learn how to create PST files with Aspose.Email for Java, including
    how to add folder structures and how to search PST content efficiently. Step‑by‑step
    guide.
  name: How to Create PST Files with Aspose.Email for Java
  steps:
  - name: Add Maven Dependency
    text: Add the Aspose.Email Maven dependency to your `pom.xml`. This pulls in all
      required binaries automatically.
  - name: Acquire and Apply a License
    text: A free trial is available, but a permanent license removes evaluation limits
      and enables full‑speed processing.
  - name: Initialize PersonalStorage
    text: The `PersonalStorage` class is Aspose.Email's top‑level object that represents
      a single PST file in memory. After instantiation, all read and write operations
      flow through this object.
  - name: Define Directory Paths
    text: Set source and destination paths for your email files and the PST output
      location.
  - name: Create the PST File
    text: Use `PersonalStorage.create()` with `FileFormatVersion.Unicode` to produce
      a modern Unicode PST that supports large folders and Unicode characters.
  - name: Build Search Query
    text: Construct a query that looks for a keyword in the subject or body, ignoring
      case.
  - name: Execute Query and Retrieve Messages
    text: Run the query on the target folder and iterate over the resulting `MapiMessage`
      collection.
  - name: Initialize PersonalStorage Object
    text: Assume `PersonalStorage` object (`pst`) is already created as shown previously.
  - name: Add to PST Folder
    text: 'Convert `MailMessage` to `MapiMessage` and add it:'
  type: HowTo
- questions:
  - answer: JDK 16 or higher is recommended for full compatibility with Aspose.Email
      for Java.
    question: What is the minimum Java version required?
  - answer: Yes, a trial mode is available but limits PST size to **10 MB** and disables
      certain optimizations.
    question: Can I use Aspose.Email without a license?
  - answer: Process messages in batches, dispose of `MapiMessage` objects promptly,
      and enable lazy loading via `PersonalStorage.setUseUnicode(true)`.
    question: How do I handle large PST files efficiently?
  - answer: Absolutely. When converting `MailMessage` to `MapiMessage`, call `mapiMsg.getAttachments().add(attachment)`
      to embed files.
    question: Is it possible to add attachments to emails in PST files?
  - answer: Aspose offers a dedicated support forum, detailed documentation, and email
      support for licensed customers.
    question: What kind of support is available for troubleshooting issues?
  type: FAQPage
title: Come creare file PST con Aspose.Email for Java
url: /it/java/email-parsing-analysis/aspose-email-java-create-pst-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Padroneggiare la gestione della posta elettronica con Aspose.Email per Java

Se hai bisogno di **how to create pst** file in modo programmatico, sei nel posto giusto. In questo tutorial percorreremo ogni passaggio necessario per generare un file PST Unicode, aggiungere le cartelle standard di Outlook, importare messaggi e eseguire ricerche case‑insensitive—tutto usando Aspose.Email per Java. Alla fine, avrai un modello di codice riutilizzabile che scala da una manciata di email a archivi multi‑gigabyte.

## Risposte rapide
- **Come inizio?** Aggiungi la dipendenza Maven di Aspose.Email, ottieni una licenza e istanzia `PersonalStorage`.
- **Posso aggiungere una cartella Inbox?** Sì – chiama `pst.getRootFolder().addSubFolder("Inbox")`.
- **La ricerca case‑insensitive è supportata?** Usa `PersonalStorageQueryBuilder` con `StringComparison.OrdinalIgnoreCase`.
- **Quale dimensione di file può essere gestita?** Aspose.Email elabora file PST fino a 2 GB senza caricare l'intero file in memoria.
- **È necessaria una licenza a pagamento per la produzione?** Una licenza permanente rimuove i limiti di prova e sblocca tutte le funzionalità di prestazioni.

## Cos'è how to create pst?
**how to create pst** si riferisce al processo programmatico di generazione di un file Outlook Personal Storage Table (PST) usando codice anziché l'interfaccia di Outlook. Aspose.Email per Java fornisce un'API completamente gestita che crea file PST Unicode, aggiunge cartelle e memorizza oggetti `MapiMessage` senza richiedere l'installazione di Outlook.

## Perché usare Aspose.Email per la creazione di PST?
Aspose.Email supporta **50+** formati relativi all'email (MSG, EML, MBOX, PST, ecc.) e può elaborare file PST con **fino a 2 GB** di dimensione mantenendo l'uso della memoria sotto **150 MB** grazie alla sua architettura lazy‑loading. Questa capacità quantificata lo rende ideale per scenari di archiviazione aziendale, migrazione e conformità.

## Prerequisiti
- **Java Development Kit (JDK)** – versione 16 o successiva.
- **Maven** – per la gestione delle dipendenze.
- Familiarità di base con la sintassi Java; non è richiesta esperienza pregressa con i file PST.

## Come creare un file PST?
La classe `PersonalStorage` rappresenta un file PST e fornisce metodi per creare, aprire e manipolare il suo contenuto. Per creare un nuovo PST Unicode, chiama `PersonalStorage.create()` con il percorso file desiderato e la versione del formato. Questa operazione genera un PST moderno che supporta cartelle grandi, caratteri Unicode e streaming efficiente, rendendolo adatto sia per attività di archiviazione su piccola scala sia a livello aziendale.

### Passo 1: Aggiungere la dipendenza Maven
Aggiungi la dipendenza Maven di Aspose.Email al tuo `pom.xml`. Questo scarica automaticamente tutti i binari necessari.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Passo 2: Ottenere e applicare una licenza
È disponibile una prova gratuita, ma una licenza permanente rimuove i limiti di valutazione e abilita l'elaborazione a piena velocità.

```java
import com.aspose.email.*;

public class AsposeEmailSetup {
    public static void main(String[] args) {
        // Set up license if available
        License license = new License();
        try {
            license.setLicense("path/to/your/license.lic");
        } catch (Exception e) {
            System.out.println("License not found, proceeding with trial version.");
        }

        System.out.println("Aspose.Email for Java is ready to use!");
    }
}
```

## Come aggiungere una cartella a PST?
Crea la gerarchia di cartelle desiderata sotto la radice del PST, quindi fai riferimento ad essa quando inserisci i messaggi. L'oggetto `FolderInfo` rappresenta ogni cartella e può essere annidato arbitrariamente, consentendoti di costruire strutture come Inbox, Sent Items o cartelle di progetto personalizzate. L'aggiunta di cartelle è un'operazione leggera che non carica il contenuto dei messaggi, preservando le prestazioni anche per PST di grandi dimensioni.

### Passo 1: Inizializzare PersonalStorage
La classe `PersonalStorage` è l'oggetto di livello superiore di Aspose.Email che rappresenta un singolo file PST in memoria. Dopo l'istanziazione, tutte le operazioni di lettura e scrittura passano attraverso questo oggetto.

```java
import com.aspose.email.FileFormatVersion;
import com.aspose.email.PersonalStorage;
```

### Passo 2: Definire i percorsi delle directory
Imposta i percorsi di origine e destinazione per i tuoi file email e la posizione di output del PST.

```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY";
String outputDir = "YOUR_OUTPUT_DIRECTORY";
```

### Passo 3: Creare il file PST
Usa `PersonalStorage.create()` con `FileFormatVersion.Unicode` per produrre un PST Unicode moderno che supporta cartelle grandi e caratteri Unicode.

```java
try {
    PersonalStorage pst = PersonalStorage.create(outputDir + "NewPSTFile_out.pst", FileFormatVersion.Unicode);

    // Perform operations here.
} finally {
    if (pst != null)
        pst.dispose();
}
```

## Come cercare nel PST?
`PersonalStorageQueryBuilder` è una classe builder usata per costruire query di ricerca per il contenuto del PST. Configurando il builder con i criteri desiderati e specificando `StringComparison.OrdinalIgnoreCase`, è possibile eseguire ricerche rapide, case‑insensitive, su oggetti, corpi e proprietà personalizzate senza caricare l'intero PST in memoria.

### Passo 1: Costruire la query di ricerca
Costruisci una query che cerca una parola chiave nell'oggetto o nel corpo, ignorando il caso.

```java
import com.aspose.email.MailQueryBuilder;
import com.aspose.email.MailQuery;
import com.aspose.email.MessageInfoCollection;

MailQueryBuilder builder = new MailQueryBuilder();
builder.getFrom().contains("automated", true);
```

### Passo 2: Eseguire la query e recuperare i messaggi
Esegui la query sulla cartella target e itera sulla collezione risultante di `MapiMessage`.

```java
try {
    MailQuery query = builder.getQuery();
    MessageInfoCollection coll = fi.getContents(query);

    // Process results as needed.
} finally {
    if (pst != null)
        pst.dispose();
}
```

## Creare una cartella predefinita in PST
Aggiungere una cartella predefinita come **Inbox** aiuta a organizzare efficacemente i dati email.

### Passo 1: Inizializzare l'oggetto PersonalStorage
Assumi che l'oggetto `PersonalStorage` (`pst`) sia già stato creato come mostrato in precedenza.

### Passo 2: Creare la cartella 'Inbox'
```java
try {
    FolderInfo fi = pst.createPredefinedFolder("Inbox", StandardIpmFolder.Inbox);
} finally {
    if (pst != null)
        pst.dispose();
}
```

## Aggiungere messaggi a una cartella PST
Popola la tua cartella PST con messaggi email caricandoli da file e convertendoli.

### Passo 1: Caricare il messaggio email
```java
import com.aspose.email.MailMessage;
import com.aspose.email.MapiMessage;

MailMessage mailMessage = MailMessage.load(dataDir + "message.msg");
```

### Passo 2: Aggiungere alla cartella PST
Converti `MailMessage` in `MapiMessage` e aggiungilo:

```java
try {
    fi.addMessage(MapiMessage.fromMailMessage(mailMessage));
} finally {
    if (pst != null)
        pst.dispose();
}
```

## Applicazioni pratiche
Aspose.Email per Java non serve solo a creare file PST; è uno strumento versatile con numerose applicazioni:
- **Email Archiving**: Automatizza l'archiviazione delle email aziendali in file PST, supportando politiche di conservazione fino a 10 anni.
- **Migration Tools**: Migra senza problemi da archivi di posta legacy (es. MBOX) a Outlook PST con una singola chiamata API per messaggio.
- **Data Analysis**: Estrai metadati come mittente, destinatario e timestamp per pipeline di business intelligence.
- **Backup Solutions**: Costruisci utility di backup robuste che memorizzano modifiche email incrementali senza rielaborare l'intera casella di posta.

## Considerazioni sulle prestazioni
Per garantire prestazioni ottimali quando si usa Aspose.Email:
- **Resource Management**: Chiama sempre `pst.dispose()` o usa try‑with‑resources per liberare rapidamente le risorse native.
- **Batch Processing**: Elabora le email in batch di **500** elementi per mantenere prevedibile l'uso della memoria.
- **Concurrency Handling**: La libreria è thread‑safe per operazioni di sola lettura; per scritture, sincronizza l'accesso all'istanza `PersonalStorage`.

## Problemi comuni e soluzioni

| Problema | Causa | Soluzione |
|----------|-------|-----------|
| **OutOfMemoryError** durante la gestione di PST di grandi dimensioni | Caricamento dell'intero PST in memoria | Abilita `PersonalStorage.setUseUnicode(true)` e processa i messaggi in streaming. |
| **Folder not found** error | Caso del percorso della cartella errato | Usa `StringComparison.OrdinalIgnoreCase` nelle query o normalizza i nomi delle cartelle. |
| **License not applied** | File di licenza non caricato prima della prima chiamata API | Carica la licenza all'avvio dell'applicazione, prima di creare qualsiasi oggetto `PersonalStorage`. |

## Domande frequenti

**Q: Qual è la versione minima di Java richiesta?**  
A: JDK 16 o superiore è consigliata per la piena compatibilità con Aspose.Email per Java.

**Q: Posso usare Aspose.Email senza licenza?**  
A: Sì, è disponibile una modalità di prova ma limita la dimensione del PST a **10 MB** e disabilita alcune ottimizzazioni.

**Q: Come gestire file PST di grandi dimensioni in modo efficiente?**  
A: Elabora i messaggi in batch, elimina prontamente gli oggetti `MapiMessage` e abilita il lazy loading tramite `PersonalStorage.setUseUnicode(true)`.

**Q: È possibile aggiungere allegati alle email nei file PST?**  
A: Assolutamente. Quando converti `MailMessage` in `MapiMessage`, chiama `mapiMsg.getAttachments().add(attachment)` per incorporare i file.

**Q: Che tipo di supporto è disponibile per la risoluzione dei problemi?**  
A: Aspose offre un forum di supporto dedicato, documentazione dettagliata e supporto via email per i clienti con licenza.

## Risorse
- [Documentation](https://reference.aspose.com/email/java/)
- [Download](https://releases.aspose.com/email/java/)
- [Purchase](https://purchase.aspose.com/buy)
- [Free Trial](https://releases.aspose.com/email/java/)
- [Temporary License](https://purchase.aspose.com/temporary-license/)
- [Support Forum](https://forum.aspose.com/c/email/10)

---

**Last Updated:** 2026-06-08  
**Tested With:** Aspose.Email for Java 24.10  
**Author:** Aspose

## Tutorial correlati

- [Come creare e gestire file Outlook PST usando Aspose.Email per Java](/email/java/outlook-pst-ost-operations/aspose-email-java-manage-pst-files/)
- [Manipolare file PST usando Aspose.Email per Java: una guida completa](/email/java/outlook-pst-ost-operations/manipulate-pst-files-aspose-email-java/)
- [Estrarre allegati email Java - Usando Aspose.Email per file PST – Guida passo‑passo](/email/java/attachments-handling/extract-email-attachments-pst-aspose-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}