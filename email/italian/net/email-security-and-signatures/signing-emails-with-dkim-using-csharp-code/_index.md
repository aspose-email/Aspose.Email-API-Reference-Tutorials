---
"description": "Impara a proteggere le email con DKIM usando C# e Aspose.Email per .NET. Guida passo passo con codice sorgente. Migliora l'affidabilità e l'autenticità delle email."
"linktitle": "Firma di e-mail con DKIM utilizzando il codice C#"
"second_title": "API di elaborazione e-mail Aspose.Email .NET"
"title": "Firma di e-mail con DKIM utilizzando il codice C#"
"url": "/it/net/email-security-and-signatures/signing-emails-with-dkim-using-csharp-code/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Firma di e-mail con DKIM utilizzando il codice C#


Nel mondo digitale odierno, garantire l'autenticità e l'integrità delle comunicazioni email è di fondamentale importanza. Un modo per raggiungere questo obiettivo è utilizzare le firme DomainKeys Identified Mail (DKIM). In questa guida passo passo, esploreremo come firmare le email con DKIM utilizzando C# e la potente libreria Aspose.Email per .NET.

## Introduzione al DKIM

### Che cosa è DKIM?
DKIM è l'acronimo di DomainKeys Identified Mail. Si tratta di un metodo di autenticazione e-mail che consente al mittente di firmare digitalmente un'e-mail, fornendo una firma crittografica che ne verifica l'autenticità.

### Perché il DKIM è importante?
DKIM aiuta a prevenire gli attacchi di spoofing e phishing delle e-mail, assicurando che le e-mail in arrivo provengano da fonti legittime e non siano state manomesse durante il transito.

## Prerequisiti

Prima di iniziare, assicurati di avere i seguenti prerequisiti:

1. Aspose.Email per .NET: assicurati di aver installato la libreria Aspose.Email per .NET nel tuo progetto. Puoi scaricarla da [Qui](https://releases.aspose.com/email/net/).

2. Chiave privata DKIM: per firmare le email avrai bisogno di una chiave privata DKIM. Assicurati di averla a portata di mano. 

## Passaggio 1: inizializzare i parametri DKIM

```csharp
string privateKeyFile = Path.Combine(RunExamples.GetDataDir_SMTP().Replace("_Send", string.Empty), RunExamples.GetDataDir_SMTP() + "key2.pem");

RSACryptoServiceProvider rsa = PemReader.GetPrivateKey(privateKeyFile);
DKIMSignatureInfo signInfo = new DKIMSignatureInfo("test", "yandex.ru");
signInfo.Headers.Add("From");
signInfo.Headers.Add("Subject");
```

In questa fase, inizializziamo i parametri DKIM. Carichiamo la chiave privata dal file, specifichiamo il selettore e il dominio ed elenchiamo le intestazioni da includere nella firma DKIM.

## Passaggio 2: creare e preparare l'e-mail

```csharp
MailMessage mailMessage = new MailMessage("useremail@gmail.com", "test@gmail.com");
mailMessage.Subject = "Signed DKIM message text body";
mailMessage.Body = "This is a text body signed DKIM message";
```

Qui creiamo un'istanza di `MailMessage` classe e imposta il mittente, il destinatario, l'oggetto e il corpo dell'e-mail.

## Passaggio 3: firmare l'e-mail

```csharp
MailMessage signedMsg = mailMessage.DKIMSign(rsa, signInfo);
```

Ora firmiamo l'e-mail utilizzando i parametri DKIM e la chiave privata inizializzati in precedenza.

## Passaggio 4: inviare l'e-mail firmata

```csharp
try
{
    SmtpClient client = new SmtpClient("smtp.gmail.com", 587, "your.email@gmail.com", "your.password");
    client.Send(signedMsg);                
}
finally
{
    // Codice di pulizia, se presente
}
```
In questa fase, inviamo l'email firmata utilizzando un client SMTP. Assicurati di sostituire `"your.email@gmail.com"` E `"your.password"` con le tue credenziali Gmail.

## Codice sorgente completo
```csharp

string privateKeyFile = Path.Combine(RunExamples.GetDataDir_SMTP().Replace("_Send", string.Empty), RunExamples.GetDataDir_SMTP()+ "key2.pem");

RSACryptoServiceProvider rsa = PemReader.GetPrivateKey(privateKeyFile);
DKIMSignatureInfo signInfo = new DKIMSignatureInfo("test", "yandex.ru");
signInfo.Headers.Add("From");
signInfo.Headers.Add("Subject");

MailMessage mailMessage = new MailMessage("useremail@gmail.com", "test@gmail.com");
mailMessage.Subject = "Signed DKIM message text body";
mailMessage.Body = "This is a text body signed DKIM message";
MailMessage signedMsg = mailMessage.DKIMSign(rsa, signInfo);

try
{
	SmtpClient client = new SmtpClient("smtp.gmail.com", 587, "your.email@gmail.com", "your.password");
	client.Send(signedMsg);                
}
finally
{}
```

## Conclusione

Firmare le email con DKIM è un passaggio fondamentale per garantire la sicurezza e l'autenticità delle tue comunicazioni email. Con l'aiuto di Aspose.Email per .NET e C#, puoi implementare facilmente le firme DKIM nel tuo processo di invio email.

---

## Domande frequenti

### D1: Cos'è DKIM e perché è importante per la sicurezza della posta elettronica?

DKIM è l'acronimo di DomainKeys Identified Mail ed è importante per la sicurezza della posta elettronica perché verifica l'autenticità dei messaggi di posta elettronica, prevenendo lo spoofing e il phishing.

### D2: Come posso ottenere una chiave privata DKIM?

Puoi ottenere una chiave privata DKIM tramite il tuo fornitore di servizi di posta elettronica oppure generandone una utilizzando strumenti crittografici.

### D3: Posso utilizzare Aspose.Email per .NET con altri provider di posta elettronica oltre a Gmail?

Sì, Aspose.Email per .NET può essere utilizzato con vari provider di posta elettronica, non limitato a Gmail.

### D4: Quali intestazioni dovrei includere nella firma DKIM?

Le intestazioni più comuni da includere nella firma DKIM sono "Da", "Oggetto" e qualsiasi altra intestazione importante per l'autenticazione della posta elettronica.

### D5: DKIM è l'unico metodo per l'autenticazione e-mail?

No, esistono altri metodi, come SPF e DMARC, che vengono utilizzati insieme a DKIM per una maggiore sicurezza della posta elettronica.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}