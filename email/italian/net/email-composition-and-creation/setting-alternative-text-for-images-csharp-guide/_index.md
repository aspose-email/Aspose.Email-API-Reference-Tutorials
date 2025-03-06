---
title: Impostazione del testo alternativo per le immagini - Guida C#
linktitle: Impostazione del testo alternativo per le immagini - Guida C#
second_title: Aspose.Email API di elaborazione della posta elettronica .NET
description: Impara a impostare testo alternativo per le immagini nelle e-mail utilizzando Aspose.Email per .NET. Garantisci l'accessibilità con un testo alternativo chiaro. Documentazione e codice inclusi.
weight: 15
url: /it/net/email-composition-and-creation/setting-alternative-text-for-images-csharp-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Impostazione del testo alternativo per le immagini - Guida C#


Questa guida ti guiderà attraverso il processo di impostazione del testo alternativo per le immagini nelle e-mail utilizzando Aspose.Email per .NET. Il testo alternativo, noto anche come "testo alternativo", viene utilizzato per fornire una descrizione testuale di un'immagine nel caso in cui l'immagine non possa essere visualizzata. Aspose.Email per .NET è una potente libreria che ti consente di lavorare con email e allegati in vari formati. In questa guida ci concentreremo sull'impostazione del testo alternativo per le immagini nei messaggi di posta elettronica utilizzando C#.

## Prerequisiti

Prima di iniziare, assicurati di avere i seguenti prerequisiti:

1. Visual Studio o qualsiasi ambiente di sviluppo C# compatibile installato.
2. Aspose.Email per la libreria .NET. È possibile utilizzare Gestione pacchetti NuGet in Visual Studio.

## Passaggio 1: crea un nuovo progetto

1. Avviare Visual Studio e creare un nuovo progetto di applicazione console C#.

## Passaggio 2: installare Aspose.Email tramite NuGet

1. Fai clic con il pulsante destro del mouse sul progetto in Esplora soluzioni e seleziona "Gestisci pacchetti NuGet".
2. Cerca "Aspose.Email" e installa l'ultima versione del pacchetto.

## Passaggio 3: aggiungere le istruzioni Using

```csharp

using Aspose.Email.Mime;
```

## Passaggio 4: caricare e modificare il messaggio e-mail

1.  Caricare il messaggio e-mail utilizzando il file`MailMessage` classe:

```csharp
MailMessage message = new MailMessage();
message.Subject = "Sample Email with Alternative Text";
message.From = new MailAddress("sender@example.com");
message.To.Add("recipient@example.com");
```

3. Carica il contenuto HTML del messaggio email:

```csharp
var htmlView = AlternateView.CreateAlternateViewFromString("<html><body><img src='cid:logo.jpg' alt='Company Logo'></body></html>", null, "text/html");
```

## Passaggio 5: aggiungi AlternativeView per testo alternativo alle immagini

Aggiungi htmlview per il testo alternativo all'immagine come AlternateView nel messaggio. 
```csharp
message.AlternateViews.Add(htmlView);
```

## Passaggio 6: salva e invia l'e-mail

1. Salva il messaggio modificato in un file o invialo utilizzando il metodo desiderato:

```csharp
message.Save("output.eml", SaveOptions.DefaultEml);
```

## Conclusione

In questa guida hai imparato come impostare testo alternativo per le immagini nei messaggi di posta elettronica utilizzando Aspose.Email per .NET. Seguendo i passaggi sopra descritti, puoi assicurarti che il contenuto della tua email rimanga accessibile e informativo anche quando le immagini non possono essere visualizzate.

## FAQ

## Come posso scaricare la libreria Aspose.Email?

È possibile scaricare la libreria Aspose.Email dalle versioni Aspose o installarla tramite NuGet Package Manager in Visual Studio.

### Come faccio ad aggiungere immagini come risorse collegate in un'e-mail?

Per aggiungere immagini come risorse collegate in un'e-mail, puoi utilizzare il file`LinkedResource` classe. Assegna un ID contenuto alla risorsa collegata, quindi fai riferimento a questo ID contenuto nel corpo HTML utilizzando il file`cid:` schema. Per informazioni dettagliate consultare il[Documentazione di LinkedResource](https://reference.aspose.com/email/net/aspose.email/linkedresource/).
### Dove posso trovare ulteriore documentazione su Aspose.Email per .NET?

 È possibile trovare documentazione più dettagliata, tutorial ed esempi su come lavorare con Aspose.Email per .NET nel file[Riferimento API](https://reference.aspose.com/email/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
