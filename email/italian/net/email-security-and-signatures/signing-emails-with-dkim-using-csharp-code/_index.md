---
title: Firma di e-mail con DKIM utilizzando il codice C#
linktitle: Firma di e-mail con DKIM utilizzando il codice C#
second_title: Aspose.Email API di elaborazione della posta elettronica .NET
description: Impara a proteggere le e-mail con DKIM utilizzando C# e Aspose.Email per .NET. Guida passo passo con il codice sorgente. Migliora la fiducia e l'autenticità delle e-mail.
weight: 11
url: /it/net/email-security-and-signatures/signing-emails-with-dkim-using-csharp-code/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Firma di e-mail con DKIM utilizzando il codice C#


Nel mondo digitale di oggi, garantire l'autenticità e l'integrità delle comunicazioni e-mail è di fondamentale importanza. Un modo per raggiungere questo obiettivo è utilizzare le firme DomainKeys Identified Mail (DKIM). In questa guida passo passo, esploreremo come firmare e-mail con DKIM utilizzando C# e la potente libreria Aspose.Email per .NET.

## Introduzione al DKIM

### Cos'è il DKIM?
DKIM sta per DomainKeys Identified Mail. È un metodo di autenticazione e-mail che consente al mittente di firmare digitalmente un'e-mail, fornendo una firma crittografica che verifica l'autenticità dell'e-mail.

### Perché DKIM è importante?
DKIM aiuta a prevenire lo spoofing delle e-mail e gli attacchi di phishing garantendo che le e-mail in arrivo provengano da fonti legittime e non siano state manomesse durante il transito.

## Prerequisiti

Prima di iniziare, assicurati di disporre dei seguenti prerequisiti:

1.  Aspose.Email per .NET: assicurati di avere la libreria Aspose.Email per .NET installata nel tuo progetto. Puoi scaricarlo da[Qui](https://releases.aspose.com/email/net/).

2. Chiave privata DKIM: avrai bisogno di una chiave privata DKIM per firmare le tue e-mail. Assicurati di averlo pronto. 

## Passaggio 1: inizializza i parametri DKIM

```csharp
string privateKeyFile = Path.Combine(RunExamples.GetDataDir_SMTP().Replace("_Send", string.Empty), RunExamples.GetDataDir_SMTP() + "key2.pem");

RSACryptoServiceProvider rsa = PemReader.GetPrivateKey(privateKeyFile);
DKIMSignatureInfo signInfo = new DKIMSignatureInfo("test", "yandex.ru");
signInfo.Headers.Add("From");
signInfo.Headers.Add("Subject");
```

In questo passaggio inizializziamo i parametri DKIM. Carichiamo la chiave privata dal file, specifichiamo il selettore e il dominio ed elenchiamo le intestazioni che dovrebbero essere incluse nella firma DKIM.

## Passaggio 2: crea e prepara l'e-mail

```csharp
MailMessage mailMessage = new MailMessage("useremail@gmail.com", "test@gmail.com");
mailMessage.Subject = "Signed DKIM message text body";
mailMessage.Body = "This is a text body signed DKIM message";
```

Qui creiamo un'istanza di`MailMessage` classe e impostare il mittente, il destinatario, l'oggetto e il corpo dell'e-mail.

## Passaggio 3: firma l'e-mail

```csharp
MailMessage signedMsg = mailMessage.DKIMSign(rsa, signInfo);
```

Ora firmiamo l'e-mail utilizzando i parametri DKIM e la chiave privata che abbiamo inizializzato in precedenza.

## Passaggio 4: invia l'e-mail firmata

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
 In questo passaggio, inviamo l'e-mail firmata utilizzando un client SMTP. Assicurati di sostituire`"your.email@gmail.com"` E`"your.password"` con le tue credenziali Gmail.

## Completa il codice sorgente
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

La firma delle e-mail con DKIM è un passaggio cruciale per garantire la sicurezza e l'autenticità delle tue comunicazioni e-mail. Con l'aiuto di Aspose.Email per .NET e C#, puoi facilmente implementare le firme DKIM nel processo di invio di e-mail.

---

## Domande frequenti

### D1: Cos'è DKIM e perché è importante per la sicurezza della posta elettronica?

DKIM sta per DomainKeys Identified Mail ed è importante per la sicurezza della posta elettronica perché verifica l'autenticità dei messaggi di posta elettronica, prevenendo spoofing e phishing.

### Q2: Come posso ottenere una chiave privata DKIM?

Puoi ottenere una chiave privata DKIM tramite il tuo fornitore di servizi di posta elettronica o generandone una utilizzando strumenti crittografici.

### Q3: Posso utilizzare Aspose.Email per .NET con altri provider di posta elettronica oltre a Gmail?

Sì, Aspose.Email per .NET può essere utilizzato con vari provider di posta elettronica, non limitato a Gmail.

### Q4: quali intestazioni devo includere nella firma DKIM?

Le intestazioni comuni da includere nella firma DKIM sono "Da", "Oggetto" e qualsiasi altra intestazione importante per l'autenticazione della posta elettronica.

### D5: DKIM è l'unico metodo per l'autenticazione della posta elettronica?

No, esistono altri metodi come SPF e DMARC utilizzati insieme a DKIM per una maggiore sicurezza della posta elettronica.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
