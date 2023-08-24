---
title: Specifica degli indirizzi dei destinatari in C#
linktitle: Specifica degli indirizzi dei destinatari in C#
second_title: Aspose.Email API di elaborazione della posta elettronica .NET
description: Scopri come specificare gli indirizzi dei destinatari in C# utilizzando Aspose.Email per .NET. Crea, configura e invia e-mail in modo efficiente.
type: docs
weight: 19
url: /it/net/email-composition-and-creation/specifying-recipient-addresses-in-csharp/
---


Questa guida ti guiderà attraverso il processo di specifica degli indirizzi dei destinatari in C# utilizzando la libreria Aspose.Email per .NET. Aspose.Email è una potente API .NET che ti consente di lavorare con messaggi di posta elettronica e varie attività relative alla posta elettronica. In questo tutorial, tratteremo come aggiungere gli indirizzi dei destinatari a un messaggio di posta elettronica utilizzando la libreria.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

1. Visual Studio o qualsiasi ambiente di sviluppo C# installato.
2. Aspose.Email per la libreria .NET. Puoi ottenerlo da[Aspose.Email per le versioni .NET](https://releases.aspose.com/email/net/).

## Passi

Seguire questi passaggi per specificare gli indirizzi dei destinatari in C# utilizzando Aspose.Email per .NET:

### 1. Creare un nuovo progetto C#

Inizia creando un nuovo progetto C# nel tuo ambiente di sviluppo.

### 2. Aggiungere il riferimento ad Aspose.Email

1. Scarica e installa la libreria Aspose.Email per .NET se non l'hai già fatto.
2. Apri il tuo progetto C#.
3. Fare clic con il pulsante destro del mouse su "Riferimenti" in Esplora soluzioni e selezionare "Aggiungi riferimento".
4. Sfoglia e seleziona i file DLL Aspose.Email che hai scaricato.

### 3. Importare gli spazi dei nomi necessari

Nel file di codice C#, importa gli spazi dei nomi necessari per l'utilizzo delle classi Aspose.Email:

```csharp
using Aspose.Email;
using Aspose.Email.Mail;
```

### 4. Creare e configurare il messaggio e-mail

 Crea una nuova istanza di`MailMessage` classe per rappresentare il tuo messaggio di posta elettronica. Configura il mittente e l'oggetto dell'e-mail:

```csharp
MailMessage message = new MailMessage();
message.From = new MailAddress("sender@example.com");
message.Subject = "Hello from Aspose.Email";
```

### 5. Aggiungi gli indirizzi dei destinatari

È possibile aggiungere gli indirizzi dei destinatari utilizzando il file`To`, `Cc` , E`Bcc` proprietà del`MailMessage` classe. Ecco come puoi aggiungere gli indirizzi dei destinatari:

```csharp
message.To.Add(new MailAddress("recipient1@example.com"));
message.Cc.Add(new MailAddress("recipient2@example.com"));
message.Bcc.Add(new MailAddress("recipient3@example.com"));
```

### 6. Completa il messaggio e-mail

Aggiungi il corpo dell'e-mail e qualsiasi altro contenuto necessario al tuo messaggio e-mail:

```csharp
message.Body = "This is the email body.";
```

### 7. Invia l'e-mail

 Per inviare l'e-mail è possibile utilizzare il file`SmtpClient` classe fornita da Aspose.Email. Configura le impostazioni del server SMTP e invia l'e-mail:

```csharp
SmtpClient client = new SmtpClient("smtp.example.com", 587, "your_username", "your_password");
client.SecurityOptions = SecurityOptions.Auto;

client.Send(message);
```

## Domande frequenti

###  Come posso aggiungere più destinatari al file`To`, `Cc`, or `Bcc` fields?

 Puoi aggiungere più destinatari chiamando il`Add` metodo più volte sul rispettivo`MailAddressCollection`:

```csharp
message.To.Add(new MailAddress("recipient1@example.com"));
message.To.Add(new MailAddress("recipient2@example.com"));
```

### Posso specificare i nomi dei destinatari insieme ai loro indirizzi email?

Sì, puoi specificare sia il nome che l'indirizzo email del destinatario quando aggiungi i destinatari:

```csharp
message.To.Add(new MailAddress("recipient@example.com", "Recipient Name"));
```

### Come gestisco le eccezioni quando invio un'e-mail?

Puoi utilizzare i blocchi try-catch per gestire le eccezioni che potrebbero verificarsi durante l'invio di email:

```csharp
try
{
    client.Send(message);
    Console.WriteLine("Email sent successfully.");
}
catch (Exception ex)
{
    Console.WriteLine($"An error occurred: {ex.Message}");
}
```

 Per ulteriori informazioni e funzionalità avanzate di Aspose.Email per .NET, fare riferimento a[Riferimenti API Aspose](https://reference.aspose.com/email/net/).

Con questo si conclude la guida sulla specifica degli indirizzi dei destinatari in C# utilizzando Aspose.Email per .NET. Hai imparato come creare un messaggio e-mail, aggiungere indirizzi di destinatari e inviare l'e-mail utilizzando le funzionalità della libreria.