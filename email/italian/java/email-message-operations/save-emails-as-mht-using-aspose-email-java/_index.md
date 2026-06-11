---
date: '2026-03-02'
description: Scopri come utilizzare Maven Aspose.Email per Java per salvare le email
  come file MHT. Questa guida passo passo copre l'installazione, i modelli personalizzati
  e la conversione da email a MHT.
keywords:
- save emails as MHT files
- Aspose.Email for Java
- convert emails to MHTML
title: 'Maven Aspose.Email per Java: Salva le email come file MHT'
url: /it/java/email-message-operations/save-emails-as-mht-using-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Maven Aspose.Email per Java: Come salvare le email come file MHT

## Introduzione

Gestire i dati delle email in modo efficiente può essere impegnativo, soprattutto quando si tratta di condivisione e archiviazione. In questa guida ti mostreremo **come salvare file MHT** usando **Maven Aspose.Email per Java**, così potrai convertire le email in MHT con modelli personalizzati e mantenere intatti gli eventi del calendario. Avrai a disposizione una soluzione pronta all'uso che funziona in qualsiasi ambiente Java 16+.

## Risposte rapide
- **Quale libreria serve?** Maven Aspose.Email per Java (v25.4+).  
- **Quale formato viene prodotto?** Un file MHT (MHTML) che raggruppa HTML, immagini e dati del calendario.  
- **Posso personalizzare l'intestazione?** Sì – usa `MhtFormatOptions` e stringhe di modello.  
- **È necessaria una licenza?** Una prova gratuita è sufficiente per la valutazione; per la produzione è richiesta una licenza permanente.  
- **Quale versione di Java è richiesta?** JDK 16 o successiva.

## Cos’è Maven Aspose.Email per Java?
Maven Aspose.Email per Java è una potente API che consente di creare, leggere, convertire e manipolare messaggi email direttamente dal codice Java. Supporta un'ampia gamma di formati—including MSG, EML e MHT—rendendola ideale per le attività di **conversione email java**.

## Perché convertire le email in MHT?
- **Compatibile con il Web**: i file MHT vengono visualizzati nei browser senza risorse esterne.  
- **Stabilità di archiviazione**: tutte le risorse sono incorporate, preservando l'aspetto originale.  
- **Supporto calendario**: è possibile renderizzare eventi ricorrenti con modelli personalizzati.  

## Prerequisiti
- **Aspose.Email per Java** (artefatto Maven `com.aspose:aspose-email:25.4` con classificatore `jdk16`).  
- **Maven** installato e configurato sulla tua macchina.  
- **JDK 16+** (la libreria è destinata a Java 16).  
- Conoscenze di base di Java (gestione file, dipendenze Maven).

## Configurazione di Aspose.Email per Java

### Dipendenza Maven

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

Aspose offre una prova gratuita per esplorare le sue funzionalità, oltre a opzioni per acquistare una licenza o ottenerne una temporanea.

1. **Prova gratuita**: scarica da [Releases](https://releases.aspose.com/email/java/) e prova le funzionalità senza limitazioni.  
2. **Licenza temporanea**: accedi a una versione pienamente funzionante richiedendola tramite la [Pagina Licenza Temporanea](https://purchase.aspose.com/temporary-license/).  
3. **Acquisto**: considera l'acquisto se Aspose.Email soddisfa le esigenze a lungo termine del tuo progetto.

### Inizializzazione di base

Una volta installata, inizializza la libreria nella tua applicazione Java:

```java
import com.aspose.email.License;

License license = new License();
license.setLicense("path/to/your/license/file");
```

Con questi passaggi completati, sei pronto a utilizzare le funzionalità di Aspose.Email per una gestione efficiente delle email.

## Guida all'implementazione

### Funzionalità 1: Caricare MailMessage

#### Panoramica
Caricare un messaggio email è il primo passo per elaborarlo e salvarlo come file MHT. Qui dimostriamo come caricare un file `.msg` usando `MailMessage`.

#### Passo‑per‑passo

**Importa le classi necessarie**

```java
import com.aspose.email.MailMessage;
```

**Carica l'email dal file**

```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY" + "/email/";
MailMessage msg = MailMessage.load(dataDir + "Meeting with Recurring Occurrences.msg");
```

Questo frammento carica un messaggio email situato nella directory specificata.

### Funzionalità 2: Configurare MhtSaveOptions

#### Panoramica
Configurare `MhtSaveOptions` è fondamentale per definire come la tua email verrà salvata come file MHT, inclusa la formattazione personalizzata per gli eventi del calendario.

#### Passo‑per‑passo

**Importa le classi necessarie**

```java
import com.aspose.email.MhtSaveOptions;
import com.aspose.email.MhtFormatOptions;
import com.aspose.email.MhtTemplateName;
```

**Imposta le opzioni di salvataggio e i modelli**

```java
MhtSaveOptions options = new MhtSaveOptions();
options.setMhtFormatOptions(MhtFormatOptions.WriteHeader | MhtFormatOptions.RenderCalendarEvent);

// Customize templates for email properties
for (Map.Entry<MhtTemplateName, String> entry : options.getFormatTemplates().entrySet()) {
    switch (entry.getKey()) {
        case START:
            options.getFormatTemplates().set_Item(MhtTemplateName.START,
                    "<span class='headerLineTitle'>Start:</span><span class='headerLineText'>{0}</span><br/>");
            break;
        // Add other cases similarly...
    }
}

// Ensure entries are added if absent
options.getFormatTemplates().addIfAbsent(MhtTemplateName.START,
            "<span class='headerLineTitle'>Start:</span><span class='headerLineText'>{0}</span><br/>");
```

Questa configurazione imposta intestazioni e rendering degli eventi del calendario nell'output MHT.

### Funzionalità 3: Salvare MailMessage come MHT

#### Panoramica
L'ultimo passo è salvare il tuo `MailMessage` configurato come file MHT usando le opzioni specificate.

#### Passo‑per‑passo

**Importa le classi necessarie**

```java
import com.aspose.email.MailMessage;
import com.aspose.email.MhtSaveOptions;
```

**Salva il messaggio email**

```java
msg.save("YOUR_OUTPUT_DIRECTORY" + "Meeting with Recurring Occurrences_out.mhtml", options);
```

Questo comando scrive l'email in un file MHT, pronto per la condivisione o l'archiviazione.

## Applicazioni pratiche
- **Archiviazione email**: converti e conserva email importanti in un formato web‑friendly.  
- **Documentazione legale**: usa i file MHT come parte di prove legali dove è necessario preservare i dettagli delle email.  
- **Condivisione cross‑platform**: condividi email tra piattaforme senza problemi di compatibilità.  

L'integrazione con altri sistemi, come CRM o strumenti di gestione progetti, può migliorare la collaborazione incorporando dati email cruciali direttamente nei flussi di lavoro.

## Considerazioni sulle prestazioni
Per garantire prestazioni ottimali:
- Gestisci efficacemente l'uso della memoria quando tratti grandi lotti di email.  
- Ottimizza le operazioni di I/O dei file per evitare colli di bottiglia durante il processo di salvataggio.  

Seguire le migliori pratiche di gestione della memoria in Java manterrà la tua applicazione reattiva.

## Problemi comuni e soluzioni
| Problema | Causa | Correzione |
|----------|-------|------------|
| **NullPointerException su `msg.save`** | Percorso di output errato | Verifica che `YOUR_OUTPUT_DIRECTORY` esista e sia scrivibile. |
| **Immagini mancanti in MHT** | `MhtFormatOptions` non impostato per incorporare le risorse | Aggiungi `MhtFormatOptions.EmbedResources` al flag delle opzioni. |
| **Eventi del calendario non renderizzati** | Flag `RenderCalendarEvent` omesso | Assicurati di usare `options.setMhtFormatOptions(MhtFormatOptions.WriteHeader \| MhtFormatOptions.RenderCalendarEvent);` |

## Domande frequenti

**D: Come gestisco gli allegati quando salvo le email come MHT?**  
R: Assicurati che `MhtSaveOptions` sia configurato per includere la logica di gestione degli allegati. La libreria supporta l'incorporamento degli allegati nel file MHT.

**D: Posso personalizzare le intestazioni email nel file MHT di output?**  
R: Sì, usa `MhtFormatOptions.WriteHeader` e definisci modelli personalizzati per i vari campi di intestazione come mostrato nel tutorial.

**D: Quali sono i requisiti di sistema per usare Aspose.Email Java?**  
R: È richiesto un JDK 16 o superiore. La libreria funziona senza problemi con la maggior parte degli IDE moderni che supportano progetti Maven.

**D: È possibile salvare solo parti specifiche di un messaggio email?**  
R: Sebbene il formato MHT includa tipicamente messaggi completi, puoi usare le proprietà di `MailMessage` per elaborare selettivamente e includere solo i contenuti desiderati.

**D: Come posso risolvere problemi di caricamento o salvataggio delle email?**  
R: Controlla che i percorsi dei file siano corretti, assicurati che la libreria sia configurata correttamente nel progetto e consulta il [forum di supporto Aspose.Email](https://forum.aspose.com/c/email/10) per assistenza.

**D: La libreria supporta la conversione di altri formati (EML, MSG) in MHT?**  
R: Assolutamente. `MailMessage.load` può leggere EML, MSG e altri formati, dopodiché è possibile salvarli come MHT usando le stesse opzioni.

## Risorse
- **Documentazione**: Per approfondire tutte le funzionalità, visita la [Documentazione Aspose Email Java](https://reference.aspose.com/email/java/).  
- **Download**: Inizia subito con la tua prova gratuita scaricando da [Releases](https://releases.aspose.com/email/java/).  
- **Acquisto**: Esplora le opzioni di acquisto nella [Pagina di Acquisto Ufficiale](https://purchase.aspose.com/buy) per un utilizzo a lungo termine.  
- **Prova gratuita e licenza temporanea**: Accedi a tutte le funzionalità durante la prova gratuita o ottieni una licenza temporanea tramite questi link:  
  - [Prova gratuita](https://releases.aspose.com/email/java/)  
  - [Licenza temporanea](https://purchase.aspose.com/temporary-license/)

Esplora, implementa e trasforma la gestione delle tue email con Aspose.Email per Java oggi stesso!

---

**Ultimo aggiornamento:** 2026-03-02  
**Testato con:** Aspose.Email per Java 25.4 (classificatore jdk16)  
**Autore:** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
