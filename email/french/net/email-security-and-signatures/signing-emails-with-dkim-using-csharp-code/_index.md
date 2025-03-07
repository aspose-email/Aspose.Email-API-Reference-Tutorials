---
title: Signature d'e-mails avec DKIM à l'aide du code C#
linktitle: Signature d'e-mails avec DKIM à l'aide du code C#
second_title: API de traitement des e-mails Aspose.Email .NET
description: Apprenez à sécuriser les e-mails avec DKIM en utilisant C# et Aspose.Email pour .NET. Guide étape par étape avec le code source. Améliorez la confiance et l’authenticité des e-mails.
weight: 11
url: /fr/net/email-security-and-signatures/signing-emails-with-dkim-using-csharp-code/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Signature d'e-mails avec DKIM à l'aide du code C#


Dans le monde numérique d'aujourd'hui, garantir l'authenticité et l'intégrité des communications par courrier électronique est d'une importance primordiale. Une façon d’y parvenir consiste à utiliser les signatures DomainKeys Identified Mail (DKIM). Dans ce guide étape par étape, nous explorerons comment signer des e-mails avec DKIM en utilisant C# et la puissante bibliothèque Aspose.Email pour .NET.

## Présentation du DKIM

### Qu’est-ce que le DKIM ?
DKIM signifie DomainKeys Identified Mail. Il s'agit d'une méthode d'authentification d'e-mail qui permet à l'expéditeur de signer numériquement un e-mail, fournissant une signature cryptographique qui vérifie l'authenticité de l'e-mail.

### Pourquoi le DKIM est-il important ?
DKIM aide à prévenir les attaques d'usurpation d'e-mails et de phishing en garantissant que les e-mails entrants proviennent de sources légitimes et n'ont pas été falsifiés pendant leur transit.

## Conditions préalables

Avant de commencer, assurez-vous que les conditions préalables suivantes sont remplies :

1.  Aspose.Email pour .NET : assurez-vous que la bibliothèque Aspose.Email pour .NET est installée dans votre projet. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/email/net/).

2. Clé privée DKIM : Vous aurez besoin d'une clé privée DKIM pour signer vos e-mails. Assurez-vous de l'avoir prêt. 

## Étape 1 : initialiser les paramètres DKIM

```csharp
string privateKeyFile = Path.Combine(RunExamples.GetDataDir_SMTP().Replace("_Send", string.Empty), RunExamples.GetDataDir_SMTP() + "key2.pem");

RSACryptoServiceProvider rsa = PemReader.GetPrivateKey(privateKeyFile);
DKIMSignatureInfo signInfo = new DKIMSignatureInfo("test", "yandex.ru");
signInfo.Headers.Add("From");
signInfo.Headers.Add("Subject");
```

Dans cette étape, nous initialisons les paramètres DKIM. Nous chargeons la clé privée à partir du fichier, spécifions le sélecteur et le domaine et répertorions les en-têtes qui doivent être inclus dans la signature DKIM.

## Étape 2 : Créer et préparer l'e-mail

```csharp
MailMessage mailMessage = new MailMessage("useremail@gmail.com", "test@gmail.com");
mailMessage.Subject = "Signed DKIM message text body";
mailMessage.Body = "This is a text body signed DKIM message";
```

Ici, nous créons une instance du`MailMessage` classe et définissez l’expéditeur, le destinataire, l’objet et le corps de l’e-mail.

## Étape 3 : Signez l'e-mail

```csharp
MailMessage signedMsg = mailMessage.DKIMSign(rsa, signInfo);
```

Maintenant, nous signons l'e-mail en utilisant les paramètres DKIM et la clé privée que nous avons initialisés précédemment.

## Étape 4 : Envoyer l'e-mail signé

```csharp
try
{
    SmtpClient client = new SmtpClient("smtp.gmail.com", 587, "your.email@gmail.com", "your.password");
    client.Send(signedMsg);                
}
finally
{
    // Code de nettoyage, le cas échéant
}
```
 Dans cette étape, nous envoyons l'e-mail signé à l'aide d'un client SMTP. Assurez-vous de remplacer`"your.email@gmail.com"` et`"your.password"` avec vos identifiants Gmail.

## Code source complet
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

## Conclusion

La signature des e-mails avec DKIM est une étape cruciale pour garantir la sécurité et l'authenticité de vos communications par e-mail. Avec l'aide d'Aspose.Email pour .NET et C#, vous pouvez facilement implémenter les signatures DKIM dans votre processus d'envoi d'e-mails.

---

## Questions fréquemment posées

### Q1 : Qu'est-ce que DKIM et pourquoi est-il important pour la sécurité de la messagerie ?

DKIM signifie DomainKeys Identified Mail, et il est important pour la sécurité du courrier électronique car il vérifie l'authenticité des messages électroniques, empêchant ainsi l'usurpation d'identité et le phishing.

### Q2 : Comment obtenir une clé privée DKIM ?

Vous pouvez obtenir une clé privée DKIM via votre fournisseur de services de messagerie ou en en générant une à l'aide d'outils cryptographiques.

### Q3 : Puis-je utiliser Aspose.Email pour .NET avec d'autres fournisseurs de messagerie que Gmail ?

Oui, Aspose.Email pour .NET peut être utilisé avec différents fournisseurs de messagerie, sans se limiter à Gmail.

### Q4 : Quels en-têtes dois-je inclure dans la signature DKIM ?

Les en-têtes courants à inclure dans la signature DKIM sont « De », « Objet » et tout autre en-tête important pour l'authentification des e-mails.

### Q5 : DKIM est-il la seule méthode d'authentification des e-mails ?

Non, il existe d'autres méthodes comme SPF et DMARC qui sont utilisées conjointement avec DKIM pour améliorer la sécurité des e-mails.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
