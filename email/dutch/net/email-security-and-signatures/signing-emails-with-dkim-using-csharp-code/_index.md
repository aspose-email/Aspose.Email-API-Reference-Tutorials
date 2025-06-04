---
"description": "Leer e-mails beveiligen met DKIM met C# en Aspose.Email voor .NET. Stapsgewijze handleiding met broncode. Verbeter het vertrouwen en de authenticiteit van e-mails."
"linktitle": "E-mails ondertekenen met DKIM met behulp van C#-code"
"second_title": "Aspose.Email .NET e-mailverwerkings-API"
"title": "E-mails ondertekenen met DKIM met behulp van C#-code"
"url": "/nl/net/email-security-and-signatures/signing-emails-with-dkim-using-csharp-code/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# E-mails ondertekenen met DKIM met behulp van C#-code


In de huidige digitale wereld is het waarborgen van de authenticiteit en integriteit van e-mailcommunicatie van het grootste belang. Eén manier om dit te bereiken, is door gebruik te maken van DomainKeys Identified Mail (DKIM)-handtekeningen. In deze stapsgewijze handleiding leggen we uit hoe u e-mails kunt ondertekenen met DKIM met behulp van C# en de krachtige Aspose.Email voor .NET-bibliotheek.

## Inleiding tot DKIM

### Wat is DKIM?
DKIM staat voor DomainKeys Identified Mail. Het is een e-mailauthenticatiemethode waarmee de afzender een e-mail digitaal kan ondertekenen met een cryptografische handtekening die de authenticiteit van de e-mail verifieert.

### Waarom is DKIM belangrijk?
Met DKIM kunt u e-mailspoofing en phishingaanvallen voorkomen door ervoor te zorgen dat binnenkomende e-mails afkomstig zijn van betrouwbare bronnen en dat er tijdens de verzending niet mee is geknoeid.

## Vereisten

Voordat we beginnen, moet u ervoor zorgen dat u aan de volgende voorwaarden voldoet:

1. Aspose.Email voor .NET: Zorg ervoor dat de Aspose.Email voor .NET-bibliotheek in uw project is geïnstalleerd. U kunt deze downloaden van [hier](https://releases.aspose.com/email/net/).

2. DKIM-privésleutel: Je hebt een DKIM-privésleutel nodig om je e-mails te ondertekenen. Zorg ervoor dat je deze bij de hand hebt. 

## Stap 1: DKIM-parameters initialiseren

```csharp
string privateKeyFile = Path.Combine(RunExamples.GetDataDir_SMTP().Replace("_Send", string.Empty), RunExamples.GetDataDir_SMTP() + "key2.pem");

RSACryptoServiceProvider rsa = PemReader.GetPrivateKey(privateKeyFile);
DKIMSignatureInfo signInfo = new DKIMSignatureInfo("test", "yandex.ru");
signInfo.Headers.Add("From");
signInfo.Headers.Add("Subject");
```

In deze stap initialiseren we de DKIM-parameters. We laden de privésleutel uit het bestand, specificeren de selector en het domein en geven een overzicht van de headers die in de DKIM-handtekening moeten worden opgenomen.

## Stap 2: De e-mail maken en voorbereiden

```csharp
MailMessage mailMessage = new MailMessage("useremail@gmail.com", "test@gmail.com");
mailMessage.Subject = "Signed DKIM message text body";
mailMessage.Body = "This is a text body signed DKIM message";
```

Hier maken we een instantie van de `MailMessage` klasse en stel de afzender, ontvanger, het onderwerp en de hoofdtekst van het e-mailbericht in.

## Stap 3: Onderteken de e-mail

```csharp
MailMessage signedMsg = mailMessage.DKIMSign(rsa, signInfo);
```

Nu ondertekenen we de e-mail met de DKIM-parameters en de privésleutel die we eerder hebben geïnitialiseerd.

## Stap 4: Verstuur de ondertekende e-mail

```csharp
try
{
    SmtpClient client = new SmtpClient("smtp.gmail.com", 587, "your.email@gmail.com", "your.password");
    client.Send(signedMsg);                
}
finally
{
    // Opruimcode, indien van toepassing
}
```
In deze stap versturen we de ondertekende e-mail via een SMTP-client. Zorg ervoor dat u `"your.email@gmail.com"` En `"your.password"` met uw Gmail-inloggegevens.

## Volledige broncode
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

Het ondertekenen van e-mails met DKIM is een cruciale stap om de veiligheid en authenticiteit van uw e-mailcommunicatie te waarborgen. Met Aspose.Email voor .NET en C# kunt u eenvoudig DKIM-handtekeningen implementeren in uw e-mailverzendingsproces.

---

## Veelgestelde vragen

### Vraag 1: Wat is DKIM en waarom is het belangrijk voor e-mailbeveiliging?

DKIM staat voor DomainKeys Identified Mail en is belangrijk voor de beveiliging van e-mail, omdat het de authenticiteit van e-mailberichten verifieert en spoofing en phishing voorkomt.

### V2: Hoe verkrijg ik een DKIM-privésleutel?

U kunt een DKIM-privésleutel verkrijgen via uw e-mailprovider of door er een te genereren met behulp van cryptografische hulpmiddelen.

### V3: Kan ik Aspose.Email voor .NET gebruiken met andere e-mailproviders dan Gmail?

Ja, Aspose.Email voor .NET kan worden gebruikt met verschillende e-mailproviders, niet beperkt tot Gmail.

### V4: Welke headers moet ik in de DKIM-handtekening opnemen?

Algemene headers die u in de DKIM-handtekening kunt opnemen, zijn 'Van', 'Onderwerp' en andere headers die belangrijk zijn voor e-mailverificatie.

### V5: Is DKIM de enige methode voor e-mailverificatie?

Nee, er zijn andere methoden zoals SPF en DMARC die in combinatie met DKIM worden gebruikt voor verbeterde e-mailbeveiliging.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}