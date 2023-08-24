---
title: Récupération des notifications d'état de livraison avec C#
linktitle: Récupération des notifications d'état de livraison avec C#
second_title: API de traitement des e-mails Aspose.Email .NET
description: Découvrez comment récupérer les notifications d'état de livraison par courrier électronique à l'aide de C# et Aspose.Email pour .NET.
type: docs
weight: 18
url: /fr/net/email-processing-and-analysis/retrieving-delivery-status-notifications-with-csharp/
---

## Introduction

Dans la communication par courrier électronique, les notifications d'état de livraison (DSN) jouent un rôle crucial en informant les expéditeurs sur l'état de livraison de leurs e-mails. Aspose.Email for .NET est une bibliothèque puissante qui fournit des fonctionnalités pour travailler avec les e-mails, notamment la récupération des DSN. Dans ce guide, nous passerons en revue le processus de récupération des notifications d'état de livraison à l'aide de C# et de la bibliothèque Aspose.Email pour .NET.

## Conditions préalables

Avant de commencer, assurez-vous de disposer des conditions préalables suivantes :

1. Visual Studio installé.
2.  Aspose.Email pour la bibliothèque .NET. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/email/net).
3. Compréhension de base de la programmation C#.

## Pas

Suivez ces étapes pour récupérer les notifications d'état de livraison à l'aide d'Aspose.Email pour .NET :

### Étape 1 : Créer un nouveau projet

Ouvrez Visual Studio et créez un nouveau projet d'application console C#.

### Étape 2 : ajouter une référence Aspose.Email

Copiez la DLL Aspose.Email téléchargée dans le répertoire de votre projet. Ensuite, cliquez avec le bouton droit sur le projet dans l'Explorateur de solutions, choisissez « Ajouter » > « Référence » et recherchez la DLL Aspose.Email. Cliquez sur "OK" pour ajouter la référence à votre projet.

### Étape 3 : Écrire du code pour récupérer les DSN

 Ouvrez le`Program.cs` fichier dans votre projet et importez les espaces de noms nécessaires :

```csharp
using Aspose.Email;
using Aspose.Email.Imap;
using Aspose.Email.Mail;
```

 À l'intérieur de`Main` méthode, écrivez le code pour vous connecter au serveur de messagerie, récupérez les DSN et traitez-les :

```csharp
class Program
{
    static void Main(string[] args)
    {
        // Définissez les informations d'identification de votre serveur IMAP et votre hôte
        string host = "your_imap_host";
        int port = 993;
        string username = "your_email";
        string password = "your_password";

        using (ImapClient client = new ImapClient(host, port, username, password))
        {
            // Sélectionnez le dossier Boîte de réception
            client.SelectFolder(ImapFolderInfo.InBox);

            // Rechercher des messages avec des DSN
            MailQueryBuilder queryBuilder = new MailQueryBuilder();
            queryBuilder.HasFlags(Aspose.Email.Mail.MessageFlags.DeliveryNotification);
            MailQuery query = queryBuilder.GetQuery();
            ImapMessageInfoCollection messages = client.ListMessages(query);

            // Traiter les DSN récupérés
            foreach (ImapMessageInfo messageInfo in messages)
            {
                MailMessage message = client.FetchMessage(messageInfo.SequenceNumber);

                // Traiter les détails du DSN
                Console.WriteLine("Subject: " + message.Subject);
                Console.WriteLine("From: " + message.From);
                // ... Traiter d'autres détails DSN

                // Marquer le message comme lu ou le supprimer
                client.DeleteMessage(messageInfo.SequenceNumber);
            }
        }
    }
}
```

 Remplacer`"your_imap_host"`, `"your_email"` , et`"your_password"` avec les détails réels de votre serveur IMAP.

### Étape 4 : Exécutez l'application

Créez et exécutez votre application. Il se connectera à votre serveur de messagerie, récupérera les DSN du dossier Boîte de réception, traitera leurs détails et éventuellement les supprimera ou les marquera comme lus.

## FAQ

### Comment trouver l’hôte du serveur IMAP ?

 Vous pouvez trouver l'hôte du serveur IMAP dans la documentation ou dans les paramètres de votre fournisseur de services de messagerie. C'est généralement sous la forme de`imap.yourdomain.com`.

### Comment puis-je traiter les détails du DSN autres que le sujet et l'expéditeur ?

 Vous pouvez accéder à diverses propriétés du`MailMessage` objet pour récupérer les détails DSN tels que les adresses des destinataires, l’état de livraison, l’horodatage, etc. Se référer au[Documentation Aspose.Email](https://reference.aspose.com/email/net/) pour plus d'informations.

### Est-il nécessaire de supprimer ou de marquer les DSN comme lus ?

Non, ce n'est pas nécéssaire. La suppression ou le marquage des DSN comme lus dépend des exigences de votre application. Le code fourni illustre les deux options, mais vous pouvez le personnaliser en fonction de vos besoins.

## Conclusion

La récupération des notifications d'état de livraison à l'aide de C# et Aspose.Email pour .NET est un processus simple. La bibliothèque Aspose.Email simplifie la communication avec le serveur IMAP et fournit des API faciles à utiliser pour traiter les messages électroniques. Avec ce guide, vous pouvez désormais intégrer la fonctionnalité de récupération DSN dans vos applications C#.