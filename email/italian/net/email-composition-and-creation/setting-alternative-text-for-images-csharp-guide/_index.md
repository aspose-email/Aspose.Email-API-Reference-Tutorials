---
"description": "Impara a impostare un testo alternativo per le immagini nelle email usando Aspose.Email per .NET. Garantisci l'accessibilità con un testo alternativo chiaro. Documentazione e codice inclusi."
"linktitle": "Impostazione del testo alternativo per le immagini - Guida C#"
"second_title": "API di elaborazione e-mail Aspose.Email .NET"
"title": "Impostazione del testo alternativo per le immagini - Guida C#"
"url": "/it/net/email-composition-and-creation/setting-alternative-text-for-images-csharp-guide/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Impostazione del testo alternativo per le immagini - Guida C#


Questa guida ti guiderà attraverso il processo di impostazione del testo alternativo per le immagini nelle email utilizzando Aspose.Email per .NET. Il testo alternativo, noto anche come "testo alt", viene utilizzato per fornire una descrizione testuale di un'immagine nel caso in cui questa non possa essere visualizzata. Aspose.Email per .NET è una potente libreria che consente di lavorare con email e allegati in vari formati. In questa guida, ci concentreremo sull'impostazione del testo alternativo per le immagini nei messaggi email utilizzando C#.

## Prerequisiti

Prima di iniziare, assicurati di avere i seguenti prerequisiti:

1. Visual Studio o qualsiasi altro ambiente di sviluppo C# compatibile installato.
2. Aspose.Email per la libreria .NET. È possibile utilizzare NuGet Package Manager in Visual Studio.

## Passaggio 1: creare un nuovo progetto

1. Avvia Visual Studio e crea un nuovo progetto di applicazione console C#.

## Passaggio 2: installare Aspose.Email tramite NuGet

1. Fai clic con il pulsante destro del mouse sul progetto in Esplora soluzioni e seleziona "Gestisci pacchetti NuGet".
2. Cerca "Aspose.Email" e installa la versione più recente del pacchetto.

## Passaggio 3: aggiungere istruzioni Using

```csharp

using Aspose.Email.Mime;
```

## Passaggio 4: caricare e modificare il messaggio di posta elettronica

1. Carica il messaggio di posta elettronica utilizzando `MailMessage` classe:

```csharp
MailMessage message = new MailMessage();
message.Subject = "Sample Email with Alternative Text";
message.From = new MailAddress("sender@example.com");
message.To.Add("recipient@example.com");
```

3. Carica il contenuto HTML del messaggio di posta elettronica:

```csharp
var htmlView = AlternateView.CreateAlternateViewFromString("<html><body><img src='cid:logo.jpg' alt='Company Logo'></body></html>", null, "text/html");
```

## Passaggio 5: aggiungere AlternativeView per testo alternativo alle immagini

Aggiungere htmlview per il testo alternativo all'immagine come AlternateView nel messaggio. 
```csharp
message.AlternateViews.Add(htmlView);
```

## Passaggio 6: salva e invia l'e-mail

1. Salva il messaggio modificato in un file o invialo utilizzando il metodo desiderato:

```csharp
message.Save("output.eml", SaveOptions.DefaultEml);
```

## Conclusione

In questa guida, hai imparato come impostare un testo alternativo per le immagini nei messaggi email utilizzando Aspose.Email per .NET. Seguendo i passaggi descritti sopra, puoi garantire che il contenuto delle tue email rimanga accessibile e informativo anche quando le immagini non possono essere visualizzate.

## Domande frequenti

## Come posso scaricare la libreria Aspose.Email?

È possibile scaricare la libreria Aspose.Email dalle versioni di Aspose oppure installarla tramite NuGet Package Manager in Visual Studio.

### Come faccio ad aggiungere immagini come risorse collegate in un'e-mail?

Per aggiungere immagini come risorse collegate in un'e-mail, puoi utilizzare `LinkedResource` classe. Assegna un ID contenuto alla risorsa collegata, quindi fai riferimento a questo ID contenuto nel corpo HTML utilizzando `cid:` schema. Per informazioni dettagliate, vedere il [Documentazione di LinkedResource](https://reference.aspose.com/email/net/aspose.email/linkedresource/).
### Dove posso trovare ulteriore documentazione su Aspose.Email per .NET?

Puoi trovare documentazione più dettagliata, tutorial ed esempi su come lavorare con Aspose.Email per .NET in [Riferimento API](https://reference.aspose.com/email/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}