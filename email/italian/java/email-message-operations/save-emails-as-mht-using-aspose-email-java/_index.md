---
date: '2026-09-22'
description: Scopri come utilizzare una licenza Aspose.Email con Maven per salvare
  le email in file MHT in Java. Include configurazione, modelli personalizzati e gestione
  degli eventi del calendario.
keywords:
- aspose email license
- how to save mht
- how to convert mht
- maven dependency aspose email
lastmod: '2026-09-22'
og_description: Scopri come utilizzare una licenza Aspose.Email con Maven per salvare
  le email in file MHT in Java. Include configurazione, modelli personalizzati e supporto
  per il calendario.
og_image_alt: 'Tutorial: saving emails as MHT using Aspose.Email for Java with a license'
og_title: Come utilizzare una licenza Aspose.Email per salvare le email in formato
  MHT
schemas:
- author: Aspose
  dateModified: '2026-09-22'
  description: Learn how to use an Aspose.Email license with Maven to save emails
    as MHT files in Java. Includes setup, custom templates, and calendar event handling.
  headline: How to use an Aspose.Email license to save emails as MHT
  type: TechArticle
- description: Learn how to use an Aspose.Email license with Maven to save emails
    as MHT files in Java. Includes setup, custom templates, and calendar event handling.
  name: How to use an Aspose.Email license to save emails as MHT
  steps:
  - name: '**Free trial** – download from [Releases](https://releases.aspose.com/email/java/)
      and explore features without limitations.'
    text: '**Free trial** – download from [Releases](https://releases.aspose.com/email/java/)
      and explore features without limitations.'
  - name: '**Temporary license** – request a fully functional version via the [Temporary
      License Page](https://purchase.aspose.com/temporary-license/).'
    text: '**Temporary license** – request a fully functional version via the [Temporary
      License Page](https://purchase.aspose.com/temporary-license/).'
  - name: '**Purchase** – obtain a permanent license for long‑term projects.'
    text: '**Purchase** – obtain a permanent license for long‑term projects.'
  type: HowTo
- questions:
  - answer: Configure `MhtSaveOptions` to embed attachments; the library automatically
      includes them in the MHT package.
    question: How do I handle attachments when saving emails as MHT?
  - answer: Yes, use `MhtFormatOptions.WriteHeader` and provide custom template strings
      for each header field.
    question: Can I customize email headers in the output MHT file?
  - answer: A JDK 16 or higher is required. The library works with any IDE that supports
      Maven projects.
    question: What are the system requirements for using Aspose.Email Java?
  - answer: While MHT typically contains the full message, you can manipulate `MailMessage`
      properties to exclude unwanted sections before saving.
    question: Is it possible to save only specific parts of an email message?
  - answer: Verify file paths, ensure the license is correctly applied, and consult
      the Aspose.Email [support forum](https://forum.aspose.com/c/email/10) for detailed
      assistance.
    question: How can I troubleshoot issues with email loading or saving?
  type: FAQPage
tags:
- aspose email
- mht conversion
- java email processing
- maven
title: Come utilizzare una licenza Aspose.Email per salvare le email in formato MHT
url: /it/java/email-message-operations/save-emails-as-mht-using-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come utilizzare una licenza Aspose.Email per salvare le email come MHT

## Introduzione

Gestire i dati delle email in modo efficiente può essere una sfida, soprattutto quando si tratta di condivisione e archiviazione. In questa guida ti mostreremo **come salvare file MHT utilizzando Maven Aspose.Email per Java con una licenza Aspose.Email**, così potrai convertire le email in MHT con modelli personalizzati e mantenere intatti gli eventi del calendario. Avrai a disposizione una soluzione pronta all'uso che funziona in qualsiasi ambiente Java 16+ e rispetta i requisiti di licenza per l'uso in produzione.

## Risposte rapide
- **Quale libreria è necessaria?** Maven Aspose.Email per Java (v25.4+).  
- **Quale formato viene prodotto?** Un file MHT (MHTML) che raggruppa HTML, immagini e dati del calendario.  
- **Posso personalizzare l'intestazione?** Sì – usa `MhtFormatOptions` e stringhe di modello.  
- **È necessaria una licenza?** È richiesta una licenza Aspose.Email per la produzione; una prova gratuita è sufficiente per la valutazione.  
- **Quale versione di Java è necessaria?** JDK 16 o successiva.  

## Cos'è Maven Aspose.Email per Java?

Maven Aspose.Email per Java è una libreria che fornisce un'API completa per creare, leggere, convertire e manipolare messaggi email direttamente dal codice Java. Supporta oltre 30 formati email — inclusi MSG, EML e MHT — consentendoti di gestire praticamente qualsiasi file email tu possa incontrare.

## Perché convertire le email in MHT?

I file MHT incorporano tutte le risorse (HTML, immagini, dati del calendario) in un unico file, rendendoli visualizzabili immediatamente in qualsiasi browser moderno senza asset esterni. Questo formato preserva l'aspetto originale, supporta eventi ricorrenti del calendario e riduce il rischio di perdere allegati durante la condivisione.

## Prerequisiti
- **Aspose.Email per Java** (artefatto Maven `com.aspose:aspose-email:25.4` con classificatore `jdk16`).  
- **Maven** installato e configurato sulla tua macchina.  
- **JDK 16+** (la libreria è destinata a Java 16).  
- Un file di licenza **Aspose.Email** valido per l'uso in produzione.  
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

Aspose offre una prova gratuita per esplorare le sue funzionalità, insieme a opzioni per acquistare una licenza o ottenere una temporanea.

1. **Prova gratuita** – scarica da [Rilasci](https://releases.aspose.com/email/java/) ed esplora le funzionalità senza limitazioni.  
2. **Licenza temporanea** – richiedi una versione pienamente funzionale tramite la [Pagina Licenza Temporanea](https://purchase.aspose.com/temporary-license/).  
3. **Acquisto** – ottieni una licenza permanente per progetti a lungo termine.

### Inizializzazione di base

Una volta installata, inizializza la libreria nella tua applicazione Java:

```java
import com.aspose.email.License;

License license = new License();
license.setLicense("path/to/your/license/file");
```

Con questi passaggi completati, sei pronto a utilizzare le funzionalità di Aspose.Email per una gestione efficiente delle email.

## Guida all'implementazione

### Funzionalità 1: caricare MailMessage

#### Panoramica

`MailMessage` è l'oggetto principale di Aspose.Email che rappresenta un'email, includendo intestazioni, corpo, allegati ed eventi del calendario.

#### Passo‑per‑passo

**Importa le classi necessarie**

```java
import com.aspose.email.MailMessage;
```

**Carica l'email da file**

```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY" + "/email/";
MailMessage msg = MailMessage.load(dataDir + "Meeting with Recurring Occurrences.msg");
```

Questo frammento carica un messaggio email situato nella directory specificata.

### Funzionalità 2: configurare MhtSaveOptions

#### Panoramica

`MhtSaveOptions` configura come Aspose.Email salva un `MailMessage` come file MHT, controllando flag di formato, modelli e incorporamento delle risorse. Una configurazione corretta consente di incorporare intestazioni, renderizzare eventi del calendario e includere tutte le immagini.

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

Questa configurazione imposta le intestazioni e il rendering degli eventi del calendario nell'output MHT.

### Funzionalità 3: salvare MailMessage come MHT

#### Panoramica

Salvare il `MailMessage` configurato come file MHT scrive un documento unico e autonomo che può essere aperto nei browser o nei client email. Il metodo `save` rispetta le opzioni definite in precedenza.

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
- **Archiviazione email** – Converti e archivia email importanti in un formato web‑friendly per la conservazione a lungo termine.  
- **Documentazione legale** – Usa i file MHT come parte di prove legali dove è richiesta la fedeltà delle email.  
- **Condivisione cross‑platform** – Condividi email tra piattaforme senza problemi di compatibilità, poiché l'MHT raggruppa tutto in un unico file.  

L'integrazione con altri sistemi — come CRM o strumenti di gestione progetti — può migliorare la collaborazione incorporando dati email cruciali direttamente nei flussi di lavoro.

## Considerazioni sulle prestazioni
Aspose.Email per Java può elaborare file fino a 500 MB senza caricare l'intero documento in memoria, e tipicamente converte un'email di 100 pagine con immagini incorporate in meno di 2 secondi su un server standard. Per mantenere l'applicazione reattiva, gestisci attentamente l'uso della memoria e raggruppa le operazioni I/O quando possibile.

## Problemi comuni e soluzioni
`MhtFormatOptions` è un'enumerazione che controlla quali elementi (intestazioni, risorse, eventi del calendario) sono inclusi quando si salva un messaggio come MHT.

| Problema | Causa | Correzione |
|----------|-------|------------|
| **NullPointerException su `msg.save`** | Percorso di output errato | Verifica che `YOUR_OUTPUT_DIRECTORY` esista e sia scrivibile. |
| **Immagini mancanti in MHT** | `MhtFormatOptions` non impostato per incorporare le risorse | Aggiungi `MhtFormatOptions.EmbedResources` al flag delle opzioni. |
| **Eventi del calendario non renderizzati** | Flag `RenderCalendarEvent` omesso | Assicurati che `options.setMhtFormatOptions(MhtFormatOptions.WriteHeader \| MhtFormatOptions.RenderCalendarEvent);` |

## Domande frequenti

**D: Come gestisco gli allegati quando salvo le email come MHT?**  
R: Configura `MhtSaveOptions` per incorporare gli allegati; la libreria li include automaticamente nel pacchetto MHT.

**D: Posso personalizzare le intestazioni email nel file MHT di output?**  
R: Sì, usa `MhtFormatOptions.WriteHeader` e fornisci stringhe di modello personalizzate per ciascun campo di intestazione.

**D: Quali sono i requisiti di sistema per usare Aspose.Email Java?**  
R: È richiesto JDK 16 o superiore. La libreria funziona con qualsiasi IDE che supporti progetti Maven.

**D: È possibile salvare solo parti specifiche di un messaggio email?**  
R: Sebbene MHT tipicamente contenga l'intero messaggio, puoi manipolare le proprietà di `MailMessage` per escludere sezioni indesiderate prima del salvataggio.

**D: Come posso risolvere problemi di caricamento o salvataggio delle email?**  
R: Verifica i percorsi dei file, assicurati che la licenza sia applicata correttamente e consulta il [forum di supporto Aspose.Email](https://forum.aspose.com/c/email/10) per assistenza dettagliata.

**D: La libreria supporta la conversione di altri formati (EML, MSG) in MHT?**  
R: Assolutamente. `MailMessage.load` può leggere EML, MSG e altri formati supportati, dopodiché puoi salvarli come MHT usando le stesse opzioni.

## Risorse
- **Documentazione**: Per approfondire tutte le funzionalità, visita la [Documentazione Aspose Email Java](https://reference.aspose.com/email/java/).  
- **Download**: Inizia la tua prova gratuita scaricando da [Rilasci](https://releases.aspose.com/email/java/).  
- **Acquisto**: Esplora le opzioni di acquisto nella [Pagina Ufficiale di Acquisto](https://purchase.aspose.com/buy) per un utilizzo a lungo termine.  
- **Prova gratuita e licenza temporanea**: Accedi a funzionalità complete durante una prova gratuita o ottieni una licenza temporanea tramite questi link:  
  - [Prova gratuita](https://releases.aspose.com/email/java/)  
  - [Licenza temporanea](https://purchase.aspose.com/temporary-license/)

Esplora, implementa e trasforma la tua gestione delle email con Aspose.Email per Java oggi!

---

**Ultimo aggiornamento:** 2026-09-22  
**Testato con:** Aspose.Email per Java 25.4 (jdk16 classifier)  
**Autore:** Aspose  

---

## Tutorial correlati

- [Guida completa a Aspose.Email per Java: Licenza e gestione email](/email/java/getting-started/mastering-aspose-email-java-license-email-handling/)
- [Come convertire MSG in MHT usando Aspose.Email per Java – Guida passo‑per‑passo](/email/java/email-conversion-rendering/convert-mapi-messages-to-mht-aspose-email-java/)
- [Come salvare email MSG con Aspose.Email per Java](/email/java/email-message-operations/aspose-email-java-create-save-emails/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}