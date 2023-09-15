---
title: Définition d'un texte alternatif pour les images - Guide C#
linktitle: Définition d'un texte alternatif pour les images - Guide C#
second_title: API de traitement des e-mails Aspose.Email .NET
description: Apprenez à définir un texte alternatif pour les images dans les e-mails à l'aide d'Aspose.Email pour .NET. Garantissez l’accessibilité avec un texte alternatif clair. Documentation et code inclus.
type: docs
weight: 15
url: /fr/net/email-composition-and-creation/setting-alternative-text-for-images-csharp-guide/
---

Ce guide vous guidera tout au long du processus de définition d'un texte alternatif pour les images dans les e-mails à l'aide d'Aspose.Email pour .NET. Le texte alternatif, également connu sous le nom de « texte alternatif », est utilisé pour fournir une description textuelle d'une image au cas où celle-ci ne pourrait pas être affichée. Aspose.Email for .NET est une bibliothèque puissante qui vous permet de travailler avec des e-mails et des pièces jointes dans différents formats. Dans ce guide, nous nous concentrerons sur la définition d'un texte alternatif pour les images dans les messages électroniques à l'aide de C#.

## Conditions préalables

Avant de commencer, assurez-vous de disposer des prérequis suivants :

1. Visual Studio ou tout environnement de développement C# compatible installé.
2. Aspose.Email pour la bibliothèque .NET. Vous pouvez utiliser NuGet Package Manager dans Visual Studio.

## Étape 1 : Créer un nouveau projet

1. Lancez Visual Studio et créez un nouveau projet d’application console C#.

## Étape 2 : Installez Aspose.Email via NuGet

1. Cliquez avec le bouton droit sur votre projet dans l'Explorateur de solutions et sélectionnez « Gérer les packages NuGet ».
2. Recherchez « Aspose.Email » et installez la dernière version du package.

## Étape 3 : ajouter des instructions using

```csharp
using Aspose.Email.Mail;
using Aspose.Email.Mime;
```

## Étape 4 : Charger et modifier le message électronique

1.  Chargez le message électronique à l'aide du`MailMessage` classe:

```csharp
MailMessage message = new MailMessage();
message.Subject = "Sample Email with Alternative Text";
message.From = new MailAddress("sender@example.com");
message.To.Add("recipient@example.com");
```

3. Chargez le contenu HTML du message électronique :

```csharp
var htmlView = AlternateView.CreateAlternateViewFromString("<html><body><img src='cid:logo.jpg' alt='Company Logo'></body></html>", null, "text/html");
```

## Étape 5 : Ajouter AlternativeView pour un texte alternatif aux images

Ajoutez htmlview pour le texte alternatif à l'image en tant qu'AlternateView dans le message. 
```csharp
message.AlternateViews.Add(htmlView);
```

## Étape 6 : Enregistrez et envoyez l'e-mail

1. Enregistrez le message modifié dans un fichier ou envoyez-le en utilisant la méthode souhaitée :

```csharp
message.Save("output.eml", SaveOptions.DefaultEml);
```

## Conclusion

Dans ce guide, vous avez appris à définir un texte alternatif pour les images dans les messages électroniques à l'aide d'Aspose.Email pour .NET. En suivant les étapes décrites ci-dessus, vous pouvez vous assurer que le contenu de votre courrier électronique reste accessible et informatif même lorsque les images ne peuvent pas être affichées.

## FAQ

## Comment puis-je télécharger la bibliothèque Aspose.Email ?

Vous pouvez télécharger la bibliothèque Aspose.Email à partir des versions Aspose ou l'installer via NuGet Package Manager dans Visual Studio.

### Comment ajouter des images en tant que ressources liées dans un e-mail ?

Pour ajouter des images en tant que ressources liées dans un e-mail, vous pouvez utiliser l'outil`LinkedResource` classe. Attribuez un ID de contenu à la ressource liée, puis référencez cet ID de contenu dans le corps HTML à l'aide du`cid:` schème. Pour des informations détaillées, consultez le[Documentation LinkedResource](https://reference.aspose.com/email/net/aspose.email/linkedresource/).
### Où puis-je trouver plus de documentation sur Aspose.Email pour .NET ?

 Vous pouvez trouver une documentation plus détaillée, des didacticiels et des exemples sur l'utilisation d'Aspose.Email pour .NET dans le[Référence API](https://reference.aspose.com/email/net/).