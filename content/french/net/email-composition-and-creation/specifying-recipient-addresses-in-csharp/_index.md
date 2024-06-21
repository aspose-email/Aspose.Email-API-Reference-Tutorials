---
title: Spécification des adresses de destinataire en C#
linktitle: Spécification des adresses de destinataire en C#
second_title: API de traitement des e-mails Aspose.Email .NET
description: Découvrez comment spécifier les adresses des destinataires en C# à l'aide d'Aspose.Email pour .NET. Créez, configurez et envoyez des e-mails efficacement.
type: docs
weight: 19
url: /fr/net/email-composition-and-creation/specifying-recipient-addresses-in-csharp/
---


Ce guide vous guidera tout au long du processus de spécification des adresses de destinataires en C# à l'aide de la bibliothèque Aspose.Email pour .NET. Aspose.Email est une puissante API .NET qui vous permet de travailler avec des messages électroniques et diverses tâches liées au courrier électronique. Dans ce didacticiel, nous expliquerons comment ajouter des adresses de destinataires à un message électronique à l'aide de la bibliothèque.

## Conditions préalables

Avant de commencer, assurez-vous d'avoir les éléments suivants :

1. Visual Studio ou tout environnement de développement C# installé.
2.  Aspose.Email pour la bibliothèque .NET. Vous pouvez l'obtenir auprès du[Aspose.Email pour les versions .NET](https://releases.aspose.com/email/net/).

## Pas

Suivez ces étapes pour spécifier les adresses des destinataires en C# à l'aide d'Aspose.Email pour .NET :

### 1. Créez un nouveau projet C#

Commencez par créer un nouveau projet C# dans votre environnement de développement.

### 2. Ajouter une référence à Aspose.Email

1. Téléchargez et installez la bibliothèque Aspose.Email pour .NET si vous ne l'avez pas déjà fait.
2. Ouvrez votre projet C#.
3. Cliquez avec le bouton droit sur les « Références » dans l'Explorateur de solutions et sélectionnez « Ajouter une référence ».
4. Parcourez et sélectionnez les fichiers DLL Aspose.Email que vous avez téléchargés.

### 3. Importez les espaces de noms nécessaires

Dans votre fichier de code C#, importez les espaces de noms nécessaires à l'utilisation des classes Aspose.Email :

```csharp
using Aspose.Email;

```

### 4. Créez et configurez le message électronique

 Créez une nouvelle instance du`MailMessage` classe pour représenter votre message électronique. Configurez l'expéditeur et le sujet de l'e-mail :

```csharp
MailMessage message = new MailMessage();
message.From = new MailAddress("sender@example.com");
message.Subject = "Hello from Aspose.Email";
```

### 5. Ajouter des adresses de destinataires

Vous pouvez ajouter des adresses de destinataires à l'aide du`To`, `Cc` , et`Bcc` propriétés du`MailMessage` classe. Voici comment ajouter des adresses de destinataires :

```csharp
message.To.Add(new MailAddress("recipient1@example.com"));
message.Cc.Add(new MailAddress("recipient2@example.com"));
message.Bcc.Add(new MailAddress("recipient3@example.com"));
```

### 6. Complétez le message électronique

Ajoutez le corps de l'e-mail et tout autre contenu nécessaire à votre e-mail :

```csharp
message.Body = "This is the email body.";
```

### 7. Envoyez l'e-mail

 Pour envoyer l'e-mail, vous pouvez utiliser le`SmtpClient` classe fournie par Aspose.Email. Configurez les paramètres du serveur SMTP et envoyez l'e-mail :

```csharp
SmtpClient client = new SmtpClient("smtp.example.com", 587, "your_username", "your_password");
client.SecurityOptions = SecurityOptions.Auto;

client.Send(message);
```

## FAQ

###  Comment puis-je ajouter plusieurs destinataires au`To`, `Cc`, or `Bcc` fields?

 Vous pouvez ajouter plusieurs destinataires en appelant le`Add` méthode plusieurs fois sur le respectif`MailAddressCollection`:

```csharp
message.To.Add(new MailAddress("recipient1@example.com"));
message.To.Add(new MailAddress("recipient2@example.com"));
```

### Puis-je spécifier les noms des destinataires ainsi que leurs adresses e-mail ?

Oui, vous pouvez spécifier à la fois le nom et l'adresse e-mail du destinataire lors de l'ajout de destinataires :

```csharp
message.To.Add(new MailAddress("recipient@example.com", "Recipient Name"));
```

### Comment gérer les exceptions lors de l’envoi d’un e-mail ?

Vous pouvez utiliser des blocs try-catch pour gérer les exceptions qui peuvent survenir lors de l'envoi d'e-mails :

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

 Pour plus d'informations et les fonctionnalités avancées d'Aspose.Email pour .NET, reportez-vous au[Références de l'API Aspose](https://reference.aspose.com/email/net/).

Ceci conclut le guide sur la spécification des adresses de destinataires en C# à l'aide d'Aspose.Email pour .NET. Vous avez appris à créer un e-mail, à ajouter des adresses de destinataires et à envoyer l'e-mail à l'aide des fonctionnalités de la bibliothèque.