---
title: Recupero delle notifiche sullo stato di consegna con C#
linktitle: Recupero delle notifiche sullo stato di consegna con C#
second_title: Aspose.Email API di elaborazione della posta elettronica .NET
description: Scopri come recuperare le notifiche sullo stato di recapito della posta elettronica utilizzando C# e Aspose.Email per .NET.
type: docs
weight: 18
url: /it/net/email-processing-and-analysis/retrieving-delivery-status-notifications-with-csharp/
---

## introduzione

Nella comunicazione e-mail, le notifiche sullo stato di consegna (DSN) svolgono un ruolo cruciale nell'informare i mittenti sullo stato di consegna delle loro e-mail. Aspose.Email per .NET è una potente libreria che fornisce funzionalità per lavorare con le e-mail, incluso il recupero dei DSN. In questa guida, esamineremo il processo di recupero delle notifiche sullo stato di consegna utilizzando C# e la libreria Aspose.Email per .NET.

## Prerequisiti

Prima di iniziare, assicurati di possedere i seguenti prerequisiti:

1. Visual Studio installato.
2.  Aspose.Email per la libreria .NET. Puoi scaricarlo da[Qui](https://releases.aspose.com/email/net).
3. Conoscenza di base della programmazione C#.

## Passi

Seguire questi passaggi per recuperare le notifiche sullo stato di consegna utilizzando Aspose.Email per .NET:

### Passaggio 1: crea un nuovo progetto

Apri Visual Studio e crea un nuovo progetto di applicazione console C#.

### Passaggio 2: aggiungere il riferimento Aspose.Email

Copia la DLL Aspose.Email scaricata nella directory del tuo progetto. Quindi, fai clic con il pulsante destro del mouse sul progetto in Esplora soluzioni, scegli "Aggiungi" > "Riferimento" e cerca la DLL Aspose.Email. Fai clic su "OK" per aggiungere il riferimento al tuo progetto.

### Passaggio 3: scrivere il codice per recuperare i DSN

 Apri il`Program.cs` file nel tuo progetto e importa gli spazi dei nomi necessari:

```csharp
using Aspose.Email;
using Aspose.Email.Imap;
using Aspose.Email.Mail;
```

 Dentro il`Main` metodo, scrivere il codice per connettersi al server di posta elettronica, recuperare i DSN ed elaborarli:

```csharp
class Program
{
    static void Main(string[] args)
    {
        // Imposta le credenziali e l'host del tuo server IMAP
        string host = "your_imap_host";
        int port = 993;
        string username = "your_email";
        string password = "your_password";

        using (ImapClient client = new ImapClient(host, port, username, password))
        {
            // Seleziona la cartella Posta in arrivo
            client.SelectFolder(ImapFolderInfo.InBox);

            // Cerca messaggi con DSN
            MailQueryBuilder queryBuilder = new MailQueryBuilder();
            queryBuilder.HasFlags(Aspose.Email.Mail.MessageFlags.DeliveryNotification);
            MailQuery query = queryBuilder.GetQuery();
            ImapMessageInfoCollection messages = client.ListMessages(query);

            // Elabora i DSN recuperati
            foreach (ImapMessageInfo messageInfo in messages)
            {
                MailMessage message = client.FetchMessage(messageInfo.SequenceNumber);

                // Elabora i dettagli DSN
                Console.WriteLine("Subject: " + message.Subject);
                Console.WriteLine("From: " + message.From);
                // ... Elabora altri dettagli DSN

                // Contrassegna il messaggio come letto o eliminalo
                client.DeleteMessage(messageInfo.SequenceNumber);
            }
        }
    }
}
```

 Sostituire`"your_imap_host"`, `"your_email"` , E`"your_password"` con i dettagli effettivi del server IMAP.

### Passaggio 4: eseguire l'applicazione

Costruisci ed esegui la tua applicazione. Si collegherà al tuo server di posta elettronica, recupererà i DSN dalla cartella Posta in arrivo, elaborerà i loro dettagli e, facoltativamente, li eliminerà o li contrassegnerà come letti.

## Domande frequenti

### Come posso trovare l'host del server IMAP?

 Puoi trovare l'host del server IMAP nella documentazione o nelle impostazioni del tuo fornitore di servizi di posta elettronica. Di solito è nel formato di`imap.yourdomain.com`.

### Come posso elaborare i dettagli DSN diversi dall'oggetto e dal mittente?

 È possibile accedere a varie proprietà del`MailMessage` oggetto per recuperare dettagli DSN come indirizzi dei destinatari, stato di consegna, timestamp e altro. Fare riferimento al[Documentazione Aspose.Email](https://reference.aspose.com/email/net/) per maggiori informazioni.

### È necessario eliminare o contrassegnare i DSN come letti?

No, non è necessario. Se eliminare o contrassegnare i DSN come letti dipende dai requisiti dell'applicazione. Il codice fornito mostra entrambe le opzioni, ma puoi personalizzarlo in base alle tue esigenze.

## Conclusione

Il recupero delle notifiche sullo stato della consegna utilizzando C# e Aspose.Email per .NET è un processo semplice. La libreria Aspose.Email semplifica la comunicazione con il server IMAP e fornisce API facili da usare per elaborare i messaggi di posta elettronica. Con questa guida ora puoi incorporare la funzionalità di recupero DSN nelle tue applicazioni C#.