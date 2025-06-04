---
"description": "Scopri come specificare gli indirizzi dei destinatari in C# utilizzando Aspose.Email per .NET. Crea, configura e invia email in modo efficiente."
"linktitle": "Specificare gli indirizzi dei destinatari in C#"
"second_title": "API di elaborazione e-mail Aspose.Email .NET"
"title": "Specificare gli indirizzi dei destinatari in C#"
"url": "/it/net/email-composition-and-creation/specifying-recipient-addresses-in-csharp/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Specificare gli indirizzi dei destinatari in C#



Questa guida ti guiderà attraverso il processo di specifica degli indirizzi dei destinatari in C# utilizzando la libreria Aspose.Email per .NET. Aspose.Email è una potente API .NET che consente di lavorare con messaggi di posta elettronica e varie attività correlate alla posta elettronica. In questo tutorial, spiegheremo come aggiungere gli indirizzi dei destinatari a un messaggio di posta elettronica utilizzando la libreria.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

1. Visual Studio o qualsiasi ambiente di sviluppo C# installato.
2. Aspose.Email per la libreria .NET. Puoi scaricarlo da [Aspose.Email per le versioni .NET](https://releases.aspose.com/email/net/).

## Passi

Per specificare gli indirizzi dei destinatari in C# utilizzando Aspose.Email per .NET, seguire questi passaggi:

### 1. Crea un nuovo progetto C#

Per prima cosa, crea un nuovo progetto C# nel tuo ambiente di sviluppo.

### 2. Aggiungere un riferimento a Aspose.Email

1. Se non l'hai già fatto, scarica e installa la libreria Aspose.Email per .NET.
2. Apri il tuo progetto C#.
3. Fare clic con il pulsante destro del mouse su "Riferimenti" in Esplora soluzioni e selezionare "Aggiungi riferimento".
4. Sfoglia e seleziona i file DLL Aspose.Email che hai scaricato.

### 3. Importare gli spazi dei nomi necessari

Nel file di codice C#, importa gli spazi dei nomi necessari per utilizzare le classi Aspose.Email:

```csharp
using Aspose.Email;

```

### 4. Creare e configurare il messaggio di posta elettronica

Crea una nuova istanza di `MailMessage` classe per rappresentare il tuo messaggio email. Configura il mittente e l'oggetto dell'email:

```csharp
MailMessage message = new MailMessage();
message.From = new MailAddress("sender@example.com");
message.Subject = "Hello from Aspose.Email";
```

### 5. Aggiungi gli indirizzi dei destinatari

È possibile aggiungere gli indirizzi dei destinatari utilizzando `To`, `Cc`, E `Bcc` proprietà del `MailMessage` classe. Ecco come puoi aggiungere gli indirizzi dei destinatari:

```csharp
message.To.Add(new MailAddress("recipient1@example.com"));
message.Cc.Add(new MailAddress("recipient2@example.com"));
message.Bcc.Add(new MailAddress("recipient3@example.com"));
```

### 6. Completa il messaggio email

Aggiungi il corpo dell'email e qualsiasi altro contenuto necessario al tuo messaggio email:

```csharp
message.Body = "This is the email body.";
```

### 7. Invia l'e-mail

Per inviare l'email puoi utilizzare il `SmtpClient` classe fornita da Aspose.Email. Configura le impostazioni del server SMTP e invia l'email:

```csharp
SmtpClient client = new SmtpClient("smtp.example.com", 587, "your_username", "your_password");
client.SecurityOptions = SecurityOptions.Auto;

client.Send(message);
```

## Domande frequenti

### Come posso aggiungere più destinatari al `To`, `Cc`, O `Bcc` campi?

È possibile aggiungere più destinatari chiamando il `Add` metodo più volte sul rispettivo `MailAddressCollection`:

```csharp
message.To.Add(new MailAddress("recipient1@example.com"));
message.To.Add(new MailAddress("recipient2@example.com"));
```

### Posso specificare i nomi dei destinatari insieme ai loro indirizzi email?

Sì, puoi specificare sia il nome che l'indirizzo email del destinatario quando aggiungi destinatari:

```csharp
message.To.Add(new MailAddress("recipient@example.com", "Recipient Name"));
```

### Come gestisco le eccezioni quando invio un'e-mail?

È possibile utilizzare i blocchi try-catch per gestire le eccezioni che potrebbero verificarsi durante l'invio di e-mail:

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

Per ulteriori informazioni e funzionalità avanzate di Aspose.Email per .NET, fare riferimento a [Riferimenti API Aspose](https://reference.aspose.com/email/net/).

Si conclude così la guida sulla specifica degli indirizzi dei destinatari in C# utilizzando Aspose.Email per .NET. Hai imparato come creare un messaggio email, aggiungere indirizzi dei destinatari e inviarlo utilizzando le funzionalità della libreria.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}