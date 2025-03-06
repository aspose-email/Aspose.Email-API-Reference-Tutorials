---
title: Signieren von E-Mails mit DKIM unter Verwendung von C#-Code
linktitle: Signieren von E-Mails mit DKIM unter Verwendung von C#-Code
second_title: Aspose.Email .NET E-Mail-Verarbeitungs-API
description: Erfahren Sie, wie Sie E-Mails mit DKIM mit C# und Aspose.Email für .NET sichern. Schritt-für-Schritt-Anleitung mit Quellcode. Verbessern Sie das Vertrauen und die Authentizität Ihrer E-Mails.
weight: 11
url: /de/net/email-security-and-signatures/signing-emails-with-dkim-using-csharp-code/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Signieren von E-Mails mit DKIM unter Verwendung von C#-Code


In der heutigen digitalen Welt ist die Gewährleistung der Authentizität und Integrität der E-Mail-Kommunikation von größter Bedeutung. Eine Möglichkeit, dies zu erreichen, ist die Verwendung von DKIM-Signaturen (DomainKeys Identified Mail). In dieser Schritt-für-Schritt-Anleitung erfahren Sie, wie Sie E-Mails mit DKIM unter Verwendung von C# und der leistungsstarken Bibliothek Aspose.Email für .NET signieren.

## Einführung in DKIM

### Was ist DKIM?
DKIM steht für DomainKeys Identified Mail. Es handelt sich um eine E-Mail-Authentifizierungsmethode, die es dem Absender ermöglicht, eine E-Mail digital zu signieren und eine kryptografische Signatur bereitzustellen, die die Authentizität der E-Mail überprüft.

### Warum ist DKIM wichtig?
DKIM trägt dazu bei, E-Mail-Spoofing und Phishing-Angriffe zu verhindern, indem es sicherstellt, dass eingehende E-Mails aus legitimen Quellen stammen und während der Übertragung nicht manipuliert wurden.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

1.  Aspose.Email für .NET: Stellen Sie sicher, dass die Aspose.Email für .NET-Bibliothek in Ihrem Projekt installiert ist. Sie können es herunterladen unter[Hier](https://releases.aspose.com/email/net/).

2. Privater DKIM-Schlüssel: Sie benötigen einen privaten DKIM-Schlüssel, um Ihre E-Mails zu signieren. Stellen Sie sicher, dass Sie es bereit haben. 

## Schritt 1: DKIM-Parameter initialisieren

```csharp
string privateKeyFile = Path.Combine(RunExamples.GetDataDir_SMTP().Replace("_Send", string.Empty), RunExamples.GetDataDir_SMTP() + "key2.pem");

RSACryptoServiceProvider rsa = PemReader.GetPrivateKey(privateKeyFile);
DKIMSignatureInfo signInfo = new DKIMSignatureInfo("test", "yandex.ru");
signInfo.Headers.Add("From");
signInfo.Headers.Add("Subject");
```

In diesem Schritt initialisieren wir die DKIM-Parameter. Wir laden den privaten Schlüssel aus der Datei, geben den Selektor und die Domäne an und listen die Header auf, die in der DKIM-Signatur enthalten sein sollen.

## Schritt 2: Erstellen und bereiten Sie die E-Mail vor

```csharp
MailMessage mailMessage = new MailMessage("useremail@gmail.com", "test@gmail.com");
mailMessage.Subject = "Signed DKIM message text body";
mailMessage.Body = "This is a text body signed DKIM message";
```

Hier erstellen wir eine Instanz von`MailMessage` Klasse und legen Sie den Absender, den Empfänger, den Betreff und den Text der E-Mail fest.

## Schritt 3: Unterschreiben Sie die E-Mail

```csharp
MailMessage signedMsg = mailMessage.DKIMSign(rsa, signInfo);
```

Jetzt signieren wir die E-Mail mit den DKIM-Parametern und dem privaten Schlüssel, die wir zuvor initialisiert haben.

## Schritt 4: Senden Sie die signierte E-Mail

```csharp
try
{
    SmtpClient client = new SmtpClient("smtp.gmail.com", 587, "your.email@gmail.com", "your.password");
    client.Send(signedMsg);                
}
finally
{
    // Bereinigungscode, falls vorhanden
}
```
 In diesem Schritt versenden wir die signierte E-Mail über einen SMTP-Client. Stellen Sie sicher, dass Sie ersetzen`"your.email@gmail.com"` Und`"your.password"` mit Ihren Gmail-Anmeldeinformationen.

## Vollständiger Quellcode
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

## Abschluss

Das Signieren von E-Mails mit DKIM ist ein entscheidender Schritt zur Gewährleistung der Sicherheit und Authentizität Ihrer E-Mail-Kommunikation. Mithilfe von Aspose.Email für .NET und C# können Sie DKIM-Signaturen problemlos in Ihren E-Mail-Versandprozess implementieren.

---

## Häufig gestellte Fragen

### F1: Was ist DKIM und warum ist es für die E-Mail-Sicherheit wichtig?

DKIM steht für DomainKeys Identified Mail und ist wichtig für die E-Mail-Sicherheit, da es die Authentizität von E-Mail-Nachrichten überprüft und so Spoofing und Phishing verhindert.

### F2: Wie erhalte ich einen privaten DKIM-Schlüssel?

Sie können einen privaten DKIM-Schlüssel über Ihren E-Mail-Dienstanbieter erhalten oder ihn mithilfe kryptografischer Tools generieren.

### F3: Kann ich Aspose.Email für .NET mit anderen E-Mail-Anbietern als Gmail verwenden?

Ja, Aspose.Email für .NET kann mit verschiedenen E-Mail-Anbietern verwendet werden, nicht nur mit Gmail.

### F4: Welche Header sollte ich in die DKIM-Signatur einfügen?

Übliche Header, die in die DKIM-Signatur einbezogen werden, sind „Von“, „Betreff“ und alle anderen Header, die für die E-Mail-Authentifizierung wichtig sind.

### F5: Ist DKIM die einzige Methode zur E-Mail-Authentifizierung?

Nein, es gibt andere Methoden wie SPF und DMARC, die in Verbindung mit DKIM für eine verbesserte E-Mail-Sicherheit verwendet werden.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
