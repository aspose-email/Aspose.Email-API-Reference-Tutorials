---
"date": "2025-05-30"
"description": "Scopri come caricare a livello di codice messaggi MAPI da file e convertirli in formato MHT utilizzando Aspose.Email per .NET. Segui questa guida passo passo."
"title": "Come caricare e salvare i messaggi MAPI come MHTML utilizzando Aspose.Email per .NET"
"url": "/it/net/mapi-operations/load-save-mapi-messages-as-mhtml-aspose-email-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Come caricare e salvare i messaggi MAPI come MHTML utilizzando Aspose.Email per .NET

## Introduzione
Gestire i messaggi email a livello di codice può essere complicato, soprattutto con formati complessi come MAPI. Tuttavia, con Aspose.Email per .NET, è possibile caricare facilmente questi messaggi da file e salvarli in un formato MHT (MIME HTML) adatto al web.

Questa guida ti guiderà nell'utilizzo di Aspose.Email per .NET per convertire i messaggi MAPI in formato MHTML. Imparerai a configurare le opzioni di salvataggio ed eseguire operazioni sui file in modo efficiente.

**Cosa imparerai:**
- Configurazione di Aspose.Email per .NET nel tuo ambiente di sviluppo.
- Caricamento dei messaggi MAPI utilizzando `MapiMessage` classe.
- Configurazione di modelli HTML personalizzati per il salvataggio in formato MHT.
- Salvataggio dei messaggi MAPI come file MHTML con opzioni personalizzate.

## Prerequisiti

### Librerie, versioni e dipendenze richieste
Per seguire questo tutorial, avrai bisogno di:
- **Aspose.Email per .NET**: Assicurati di aver installato la versione 22.10 o successiva.
- **.NET Framework o .NET Core/5+/6+**: Dipende dalla configurazione del progetto.

### Requisiti di configurazione dell'ambiente
Assicurati che il tuo ambiente di sviluppo supporti i progetti .NET. Puoi utilizzare Visual Studio, VS Code con estensione C# o qualsiasi IDE che supporti lo sviluppo .NET.

### Prerequisiti di conoscenza
Una conoscenza di base di:
- Programmazione C#.
- Gestione di file e directory in .NET.
- Lavorare con librerie di terze parti.

## Impostazione di Aspose.Email per .NET
Iniziare a usare Aspose.Email è semplicissimo. Ecco come installarlo:

**Utilizzando la CLI .NET:**
```bash
dotnet add package Aspose.Email
```

**Utilizzo della console di Package Manager:**
```powershell
Install-Package Aspose.Email
```

**Utilizzo dell'interfaccia utente di NuGet Package Manager:**
1. Aprire il Gestore pacchetti NuGet.
2. Cerca "Aspose.Email" e installa la versione più recente.

### Acquisizione della licenza
Per iniziare a utilizzare Aspose.Email, puoi:
- **Prova gratuita**: Scarica una licenza di prova per testare tutte le funzionalità.
- **Licenza temporanea**: Ottieni una licenza temporanea per l'accesso a tutte le funzionalità senza limitazioni di valutazione.
- **Acquistare**Acquista un abbonamento se sei pronto a integrarlo nel tuo ambiente di produzione.

Una volta installata, inizializza la libreria includendo gli spazi dei nomi necessari nel tuo progetto:
```csharp
using Aspose.Email;
using System;
```

## Guida all'implementazione

### Funzionalità 1: carica il messaggio MAPI dal file

#### Panoramica
Questa funzionalità illustra come caricare un messaggio MAPI da un percorso file specificato utilizzando Aspose.Email, fondamentale per l'elaborazione delle email archiviate come messaggi MAPI.

#### Passaggi per l'implementazione
**Passo 1**: Definisci il percorso della directory
Sostituire `"YOUR_DOCUMENT_DIRECTORY"` con la tua directory effettiva in cui si trova `MapiTask.msg` il file si trova.
```csharp
string dataDir = "YOUR_DOCUMENT_DIRECTORY"; // Sostituisci con il percorso della directory del tuo documento
```
**Passo 2**: Carica il messaggio MAPI
Utilizzare il `MapiMessage.FromFile()` metodo per caricare il messaggio, creando un `MapiMessage` oggetto da esso.
```csharp
// Carica il MapiMessage dal file specificato
dynamic msg = MapiMessage.FromFile(dataDir + "MapiTask.msg");
```

### Funzionalità 2: Configurare le opzioni di salvataggio MHT

#### Panoramica
La configurazione delle opzioni di salvataggio consente di personalizzare il modo in cui il messaggio MAPI viene salvato in formato MHTML. Questa fase prevede l'impostazione di modelli e opzioni di formato.

#### Passaggi per l'implementazione
**Passo 1**: Inizializza `MhtSaveOptions`
Imposta le opzioni di salvataggio MHTML predefinite, che verranno modificate per l'output personalizzato.
```csharp
dynamic opt = SaveOptions.DefaultMhtml;
```
**Passo 2**: Imposta opzioni formato
Abilita il rendering dei campi attività e delle informazioni di intestazione nel file MHTML salvato.
```csharp
opt.MhtFormatOptions = MhtFormatOptions.RenderTaskFields | MhtFormatOptions.WriteHeader;
```
**Fase 3**: Personalizza i modelli
Definire modelli HTML per varie proprietà delle attività per controllarne l'aspetto nel file di output.
```csharp
// Cancella i modelli esistenti
opt.FormatTemplates.Clear();

// Aggiungi modelli HTML personalizzati per proprietà di attività specifiche
opt.FormatTemplates.Add(MhtTemplateName.Task.Subject, "<span class='headerLineTitle'>Subject:</span><span class='headerLineText'>{0}</span><br/>");
opt.FormatTemplates.Add(MhtTemplateName.Task.ActualWork, "<span class='headerLineTitle'>Actual Work:</span><span class='headerLineText'>{0}</span><br/>");
opt.FormatTemplates.Add(MhtTemplateName.Task.TotalWork, "<span class='headerLineTitle'>Total Work:</span><span class='headerLineText'>{0}</span><br/>");
opt.FormatTemplates.Add(MhtTemplateName.Task.Status, "<span class='headerLineTitle'>Status:</span><span class='headerLineText'>{0}</span><br/>");
opt.FormatTemplates.Add(MhtTemplateName.Task.Owner, "<span class='headerLineTitle'>Owner:</span><span class='headerLineText'>{0}</span><br/>");
opt.FormatTemplates.Add(MhtTemplateName.Task.Priority, "<span class='headerLineTitle'>Priority:</span><span class='headerLineText'>{0}</span><br/>");
```

### Funzionalità 3: Salva il messaggio MAPI come file MHTML

#### Panoramica
Una volta configurato, salva il messaggio MAPI caricato in un file MHTML. Questo passaggio finalizza il processo di conversione utilizzando le opzioni impostate in precedenza.

#### Passaggi per l'implementazione
**Passo 1**: Definisci il percorso del file di output
Specifica dove vuoi salvare il file MHTML convertito.
```csharp
string outputFile = dataDir + "MapiTask_out.mht";
```
**Passo 2**Salva il messaggio
Utilizzare il `Save()` metodo con le opzioni configurate per convertire e memorizzare il messaggio in formato MHTML.
```csharp
// Salva il messaggio in un file MHT utilizzando le opzioni configurate in precedenza
dynamic msg.Save(outputFile, opt);
```

## Applicazioni pratiche
1. **Archiviazione e-mail**: Archivia le email dai sistemi legacy convertendole in un formato MHTML adatto al Web.
2. **Integrazione con i sistemi di gestione delle attività**: Converti i messaggi MAPI correlati alle attività per utilizzarli nelle moderne applicazioni di gestione dei progetti che supportano i formati HTML.
3. **Documentazione e condivisione**: Genera report condivisibili delle attività di posta elettronica in un formato accessibile, perfetto per la documentazione o la collaborazione.

## Considerazioni sulle prestazioni
### Ottimizzazione delle prestazioni
- Carica solo i file necessari per ridurre l'utilizzo della memoria.
- Ove possibile, utilizzare metodi asincroni per evitare operazioni bloccanti.

### Linee guida per l'utilizzo delle risorse
- Monitorare l'occupazione di memoria dell'applicazione quando si gestiscono grandi volumi di messaggi.
- Smaltire correttamente gli oggetti dopo l'uso per liberare risorse.

### Best Practice per la gestione della memoria .NET con Aspose.Email
- Utilizzare `using` istruzioni per eliminare automaticamente gli oggetti.
- Aggiornare regolarmente Aspose.Email per sfruttare i miglioramenti e le ottimizzazioni presenti nelle versioni più recenti.

## Conclusione
In questo tutorial, hai imparato come caricare messaggi MAPI da file e salvarli come MHTML utilizzando Aspose.Email per .NET. Ora hai le conoscenze necessarie per implementare queste funzionalità nelle tue applicazioni, migliorando le capacità di gestione delle email.

**Prossimi passi:**
- Sperimenta con diversi `MhtSaveOptions` impostazioni.
- Esplora le funzionalità aggiuntive fornite da Aspose.Email per .NET.

## Sezione FAQ
1. **Posso usare Aspose.Email gratuitamente?**
   - Sì, puoi iniziare con una licenza di prova gratuita di 30 giorni per testare tutte le funzionalità senza limitazioni.
2. **Quali formati supporta Aspose.Email oltre a MAPI e MHTML?**
   - Supporta vari formati di posta elettronica, tra cui EML, MSG, PST e altri.
3. **Come gestire file di grandi dimensioni in Aspose.Email?**
   - Utilizzare tecniche che consentono di utilizzare molta memoria, come lo streaming, per leggere/scrivere file di grandi dimensioni.
4. **Posso integrare questa funzionalità in un'applicazione web?**
   - Assolutamente! Questa funzionalità è ideale per le applicazioni web che richiedono funzionalità di gestione della posta elettronica.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}