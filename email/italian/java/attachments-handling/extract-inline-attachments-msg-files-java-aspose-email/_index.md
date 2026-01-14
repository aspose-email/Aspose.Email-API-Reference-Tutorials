---
date: '2025-12-17'
description: Scopri come estrarre gli allegati inline in Java e leggere i file Outlook MSG
  in Java usando Aspose.Email per Java. Guida passo‑passo per gestire i file MSG di
  Outlook in modo efficiente.
keywords:
- extract inline attachments MSG Java
- handle Outlook email formats Java
- use Aspose.Email library for Java
title: Estrai allegati inline Java – file MSG con Aspose.Email
url: /it/java/attachments-handling/extract-inline-attachments-msg-files-java-aspose-email/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Estrai allegati inline Java – file MSG usando Aspose.Email

## Introduzione

Se hai bisogno di **extract inline attachs java** dai file Microsoft OutlookMSG, sei nel posto giusto. Molti sviluppatori hanno difficoltà a leggere i file Outlookmsgjava perché il formato nasconde immagini e documenti incorporati nel corpo del messaggio. In questo tutorial illustreremo una soluzione pulita, pronta per la produzione, che utilizza la libreria Aspose.Email per Java per individuare, identificare e salvare quegli allegati inline.

Al termine di questa guida sarai in grado di:

* Configurare Aspose.Email per Java in un progetto Maven.
* **Leggi il file Outlookmsgjava** ed enumera i loro allegati.
* Rilevare quali allegati sono inline e scriverli su disco.
* Applicare le migliori pratiche di performance per l'elaborazione in batch.

## Risposte rapide
- **Cosa significa “inline attach”?** Un allegato che è incorporato nel corpo dell'email (ad esempio, immagini condivise all'interno del messaggio).
- **Quale libreria gestisce i file MSG?** Aspose.Email per Java.
- **È necessaria una licenza?** Una versione di prova funziona per la valutazione; una licenza permanente rimuove i limiti di utilizzo.
- **Posso elaborare molti file MSG contemporaneamente?** Sì – raggruppa la logica in batch e utilizza pool di thread per la scalabilità.
- **Quale versione di Java è richiesta?** JDK16 o successiva.

## Cos'è l'"estrazione degli allegati in linea Java"?

Estrarre allegati inline in Java significa aprire programmaticamente un file MSG, scansionare la sua collezione di allegati e estrarre solo quegli elementi contrassegnati come *inline* (in opposizione ai normali allegati di file). Questo è essenziale quando è necessario salvare il contenuto visivo di un'email — come loghi o screenshot incorporati — come file immagine separati.

## Perché utilizzare Aspose.Email per questa attività?

Aspose.Email astrae le strutture MAPI a basso livello e fornisce un'API semplice e tipizzata. Rispetto al tentativo di analizzare manualmente il formato binario MSG, Aspose.Email:

* Gestisci tutte le varianti di MSG (Unicode, RTF, HTML).
* Fornisce un accesso affidabile alle proprietà dei metadati degli allegati.
* Offre controlli di licenza integrati e una documentazione estesa.

## Prerequisiti

Per seguire, assicurazioni di avere:

1. **Librerie e dipendenze** 
* Aspose.Email per Java (ultima versione). 
* Maven (o un IDE con supporto Maven).

2. **Tempo di esecuzione** 
* JDK16 o superiore installato.

3. **Conoscenze di base** 
* Familiarità con Java I/O e la gestione delle eccezioni.

## Configurazione di Aspose.Email per Java

Aggiungi la dipendenza Aspose.Email al tuo `pom.xml`. Lo snippet qui è identico a quello del tutorial originale.

```xml
<dependency>
  <groupId>com.aspose</groupId>
  <artifactId>aspose-email</artifactId>
  <version>25.4</version>
  <classifier>jdk16</classifier>
</dependency>
```

### Passaggi di acquisizione della licenza

* **Prova gratuita:** Scarica il DLL/JAR di prova dal sito Aspose.
* **Licenza temporanea:** Richiedi una licenza di valutazione di 30 giorni per test senza restrizioni.
* **Acquisto completo:** Ottieni una licenza permanente per le distribuzioni in produzione.

## Guida all'implementazione

Sotto suddividiamo la soluzione in tre funzionalità focalizzate. Ogni funzionalità contiene una breve spiegazione seguita dal blocco del codice originale (conservato esattamente).

### Caratteristica 1 – Carica il file MSG

Per prima cosa, carica il messaggio Outlook in un oggetto `MapiMessage`.

```java
import com.aspose.email.MapiMessage;

String dataDir = "YOUR_DOCUMENT_DIRECTORY/email/";
MapiMessage message = MapiMessage.fromFile(dataDir + "MSG file with RTF Formatting.msg");
```

### Caratteristica 2 – Recupera gli allegati

Successivamente, ottieni l'intera collezione di allegati dal messaggio.

```java
import com.aspose.email.MapiAttachmentCollection;

MapiAttachmentCollection attachments = message.getAttachments();
```

### Caratteristica 3 – Identifica e salva gli allegati inline

Itera su ciascun allegato, verifica se è inline e poi scrivilo su disco.

```java
for (Object untypedAttachment : attachments) {
    MapiAttachment attachment = (MapiAttachment) untypedAttachment;
    if (IsAttachmentInline(attachment)) {
        try {
            SaveAttachment(attachment, UUID.randomUUID().toString());
        } catch (IOException e) {
            // Handle exception
        }
    }
}
```

#### Utilità: Determina se un allegato è inline

Il metodo di supporto ispeziona le proprietà MAPI per decidere se un allegato è incorporato.

```java
import com.aspose.email.MapiAttachment;
import com.aspose.email.MapiObjectProperty;
import com.aspose.email.MapiProperty;

static boolean IsAttachmentInline(MapiAttachment attachment) {
    MapiObjectProperty objectData = attachment.getObjectData();
    if (objectData == null) return false;

    for (Object prop : attachment.getObjectData().getProperties().getValues()) {
        MapiProperty property = (MapiProperty) prop;
        if ("\u0003ObjInfo".equals(property.getName())) {
            byte[] data = property.getData();
            int odtPersist1 = data[1] << 8 | data[0];
            return (odtPersist1 & 0x40) == 0;
        }
    }
    return false;
}
```

#### Utilità: Salva l'allegato inline

Scrivere il contenuto del binario dell'allegato inline in un file sul filesystem locale.

```java
import com.aspose.email.MapiAttachment;
import java.io.FileOutputStream;
import java.io.IOException;

static void SaveAttachment(MapiAttachment attachment, String fileName) throws IOException {
    for (Object prop : attachment.getObjectData().getProperties().getValues()) {
        MapiProperty property = (MapiProperty) prop;
        if ("Package".equals(property.getName())) {
            try (FileOutputStream fs = new FileOutputStream(fileName)) {
                fs.write(property.getData(), 0, property.getData().length);
            }
        }
    }
}
```

## Applicazioni pratiche

Estrarre allegati inline è utile in molti scenari reali:

* **Elaborazione automatizzata delle email** – Estrarre immagini dalle newsletter per analisi.
* **Migrazione dati** – Spostare contenuti incorporati durante la migrazione da Exchange a un'altra piattaforma.
* **Soluzioni di archiviazione** – Conservare la fedeltà visiva dei messaggi archiviati memorizzando separatamente le risorse inline.

## Considerazioni sulle prestazioni

Quando si gestiscono centinaia o migliaia di file MSG, tieni presenti questi consigli:

* **Elaborazione batch:** Raggruppa i file in batch gestibili per evitare picchi di memoria.
* **Rilasciare tempestivamente le risorse:** Chiudi gli stream (`try‑with‑resources`) e consenti al garbage collector di recuperare gli oggetti.
* **Esecuzione parallela:** Usa un `ExecutorService` a dimensione fissa per eseguire più job di estrazione contemporaneamente, ma monitora l'uso della CPU.

## Problemi comuni e risoluzione dei problemi

| Sintomo | Probabile causa | Soluzione |
|---------|----------------|----------|
| `NullPointerException` su `attachment.getObjectData()` | Il messaggio manca dei metadati dell'allegato (es. MSG corrotto) | Convalida il file MSG prima dell'elaborazione o cattura l'eccezione e registra il nome del file. |
| Il file salvato è vuoto o corrotto | Nome proprietà errato (`"Pacchetto"` distinzione tra maiuscole e minuscole) | Verifica che il nome della proprietà corrisponde a quella reale del MSG; la documentazione di Aspose.Email elenca la stringa esatta. |
| Le prestazioni peggiorano con file di grandi dimensioni | Stream non chiusi, causando perdite di memoria | Usa try‑with‑resources (come mostrato) e considera di aumentare l'heap JVM se necessario. |

## Domande frequenti

**D: Qual è la versione minima di Aspose.Email richiesta?**
R: Il tutorial utilizza la versione25.4, ma qualsiasi versione 24.x+ che supporta JDK16 funzionerà.

**D: Posso estrarre allegati inline da file MSG crittografati?**
R: Sì, a condizione di fornire la password di decrittazione corretta quando si carica il `MapiMessage`.

**D: Come distinguere tra immagini inline e allegati di file regolari?**
R: Usa l'helper `IsAttachmentInline`; controlla il flag MAPI `ObjInfo` che segna un allegato come inline.

**D: Esiste un modo per preservare il nome file originale dell'allegato inline?**
R: L'esempio genera un UUID per l'unicità, ma è possibile leggere la proprietà `attachment.getLongFileName()` e usarla quando si chiama `SaveAttachment`.

**D: Questo approccio funziona su Linux/macOS così come su Windows?**
R: Assolutamente—Aspose.Email è indipendente dalla piattaforma purché sia ​​installato il JDK.

## Risorse
- **Documentazione:** [Documentazione Aspose Email](https://docs.aspose.com/email/java/)

---

**Ultimo aggiornamento:** 2025-12-17
**Testato con:** Aspose.Email per Java 25.4 (JDK16)
**Autore:** Chiedi

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}