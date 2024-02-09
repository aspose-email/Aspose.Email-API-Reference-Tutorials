---
title: E-mails ondertekenen met DKIM met behulp van C#-code
linktitle: E-mails ondertekenen met DKIM met behulp van C#-code
second_title: Aspose.Email .NET E-mailverwerkings-API
description: Leer e-mails beveiligen met DKIM met behulp van C# en Aspose.Email voor .NET. Stap-voor-stap handleiding met broncode. Verbeter het vertrouwen en de authenticiteit van e-mails.
type: docs
weight: 11
url: /nl/net/email-security-and-signatures/signing-emails-with-dkim-using-csharp-code/
---

In de digitale wereld van vandaag is het garanderen van de authenticiteit en integriteit van e-mailcommunicatie van het allergrootste belang. Eén manier om dit te bereiken is door DomainKeys Identified Mail (DKIM)-handtekeningen te gebruiken. In deze stapsgewijze handleiding onderzoeken we hoe u e-mails kunt ondertekenen met DKIM met behulp van C# en de krachtige Aspose.Email voor .NET-bibliotheek.

## Inleiding tot DKIM

### Wat is DKIM?
DKIM staat voor DomainKeys Identified Mail. Het is een e-mailauthenticatiemethode waarmee de afzender een e-mail digitaal kan ondertekenen, waarbij een cryptografische handtekening wordt verstrekt die de authenticiteit van de e-mail verifieert.

### Waarom is DKIM belangrijk?
DKIM helpt bij het voorkomen van e-mailspoofing en phishing-aanvallen door ervoor te zorgen dat inkomende e-mails afkomstig zijn van legitieme bronnen en dat er tijdens de verzending niet mee is geknoeid.

## Vereisten

Voordat we beginnen, zorg ervoor dat u aan de volgende vereisten voldoet:

1.  Aspose.Email voor .NET: Zorg ervoor dat de Aspose.Email voor .NET-bibliotheek in uw project is geïnstalleerd. Je kunt het downloaden van[hier](https://releases.aspose.com/email/net/).

2. DKIM-privésleutel: u hebt een DKIM-privésleutel nodig om uw e-mails te ondertekenen. Zorg ervoor dat je het klaar hebt. 

## Stap 1: Initialiseer DKIM-parameters

```csharp
string privateKeyFile = Path.Combine(RunExamples.GetDataDir_SMTP().Replace("_Send", string.Empty), RunExamples.GetDataDir_SMTP() + "key2.pem");

RSACryptoServiceProvider rsa = PemReader.GetPrivateKey(privateKeyFile);
DKIMSignatureInfo signInfo = new DKIMSignatureInfo("test", "yandex.ru");
signInfo.Headers.Add("From");
signInfo.Headers.Add("Subject");
```

In deze stap initialiseren we de DKIM-parameters. We laden de privésleutel uit het bestand, specificeren de selector en het domein en vermelden de headers die in de DKIM-handtekening moeten worden opgenomen.

## Stap 2: Maak en bereid de e-mail voor

```csharp
MailMessage mailMessage = new MailMessage("useremail@gmail.com", "test@gmail.com");
mailMessage.Subject = "Signed DKIM message text body";
mailMessage.Body = "This is a text body signed DKIM message";
```

Hier maken we een exemplaar van de`MailMessage` class en stel de afzender, ontvanger, onderwerp en hoofdtekst van de e-mail in.

## Stap 3: Onderteken de e-mail

```csharp
MailMessage signedMsg = mailMessage.DKIMSign(rsa, signInfo);
```

Nu ondertekenen we de e-mail met de DKIM-parameters en de privésleutel die we eerder hebben geïnitialiseerd.

## Stap 4: Verzend de ondertekende e-mail

```csharp
try
{
    SmtpClient client = new SmtpClient("smtp.gmail.com", 587, "your.email@gmail.com", "your.password");
    client.Send(signedMsg);                
}
finally
{
    // Opschoningscode, indien aanwezig
}
```
 In deze stap verzenden we de ondertekende e-mail via een SMTP-client. Zorg ervoor dat u vervangt`"your.email@gmail.com"` En`"your.password"` met uw Gmail-inloggegevens.

## Voltooi de broncode
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

## Conclusie

Het ondertekenen van e-mails met DKIM is een cruciale stap bij het garanderen van de veiligheid en authenticiteit van uw e-mailcommunicatie. Met behulp van Aspose.Email voor .NET en C# kunt u eenvoudig DKIM-handtekeningen implementeren in uw e-mailverzendproces.

---

## Veel Gestelde Vragen

### Vraag 1: Wat is DKIM en waarom is het belangrijk voor e-mailbeveiliging?

DKIM staat voor DomainKeys Identified Mail en is belangrijk voor e-mailbeveiliging omdat het de authenticiteit van e-mailberichten verifieert en spoofing en phishing voorkomt.

### Vraag 2: Hoe verkrijg ik een DKIM-privésleutel?

kunt een DKIM-privésleutel verkrijgen via uw e-mailserviceprovider of door er een te genereren met behulp van cryptografische hulpmiddelen.

### V3: Kan ik Aspose.Email voor .NET gebruiken met andere e-mailproviders dan Gmail?

Ja, Aspose.Email voor .NET kan worden gebruikt met verschillende e-mailproviders, niet beperkt tot Gmail.

### V4: Welke headers moet ik opnemen in de DKIM-handtekening?

Veelgebruikte headers die in de DKIM-handtekening moeten worden opgenomen, zijn 'Van', 'Onderwerp' en andere headers die belangrijk zijn voor e-mailauthenticatie.

### Vraag 5: Is DKIM de enige methode voor e-mailauthenticatie?

Nee, er zijn andere methoden zoals SPF en DMARC die in combinatie met DKIM worden gebruikt voor verbeterde e-mailbeveiliging.