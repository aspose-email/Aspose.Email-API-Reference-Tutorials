---
"date": "2025-05-30"
"description": "Découvrez comment charger par programmation des messages MAPI à partir de fichiers et les convertir au format MHT avec Aspose.Email pour .NET. Suivez ce guide étape par étape."
"title": "Comment charger et enregistrer des messages MAPI au format MHTML avec Aspose.Email pour .NET"
"url": "/fr/net/mapi-operations/load-save-mapi-messages-as-mhtml-aspose-email-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Comment charger et enregistrer des messages MAPI au format MHTML avec Aspose.Email pour .NET

## Introduction
La gestion programmatique des e-mails peut s'avérer complexe, notamment avec des formats complexes comme MAPI. Cependant, avec Aspose.Email pour .NET, vous pouvez facilement charger ces messages depuis des fichiers et les enregistrer au format MHT (MIME HTML) compatible avec le Web.

Ce guide vous explique comment utiliser Aspose.Email pour .NET pour convertir des messages MAPI au format MHTML. Vous apprendrez à configurer les options d'enregistrement et à exécuter efficacement des opérations sur les fichiers.

**Ce que vous apprendrez :**
- Configuration d'Aspose.Email pour .NET dans votre environnement de développement.
- Chargement des messages MAPI à l'aide de `MapiMessage` classe.
- Configuration de modèles HTML personnalisés pour l'enregistrement au format MHT.
- Enregistrement des messages MAPI sous forme de fichiers MHTML avec des options personnalisées.

## Prérequis

### Bibliothèques, versions et dépendances requises
Pour suivre ce tutoriel, vous aurez besoin de :
- **Aspose.Email pour .NET**: Assurez-vous d'avoir installé la version 22.10 ou une version ultérieure.
- **.NET Framework ou .NET Core/5+/6+**:En fonction de la configuration de votre projet.

### Configuration requise pour l'environnement
Assurez-vous que votre environnement de développement prend en charge les projets .NET. Vous pouvez utiliser Visual Studio, VS Code avec l'extension C# ou tout autre IDE prenant en charge le développement .NET.

### Prérequis en matière de connaissances
Une compréhension de base de :
- Programmation C#.
- Gestion des fichiers et des répertoires dans .NET.
- Travailler avec des bibliothèques tierces.

## Configuration d'Aspose.Email pour .NET
Démarrer avec Aspose.Email est simple. Voici comment l'installer :

**Utilisation de l'interface de ligne de commande .NET :**
```bash
dotnet add package Aspose.Email
```

**Utilisation de la console du gestionnaire de packages :**
```powershell
Install-Package Aspose.Email
```

**Utilisation de l'interface utilisateur du gestionnaire de packages NuGet :**
1. Ouvrez le gestionnaire de packages NuGet.
2. Recherchez « Aspose.Email » et installez la dernière version.

### Acquisition de licence
Pour commencer à utiliser Aspose.Email, vous pouvez :
- **Essai gratuit**: Téléchargez une licence d'essai pour tester toutes les fonctionnalités.
- **Licence temporaire**: Obtenez une licence temporaire pour un accès complet aux fonctionnalités sans limitations d'évaluation.
- **Achat**Achetez un abonnement si vous êtes prêt à l'intégrer dans votre environnement de production.

Une fois installée, initialisez la bibliothèque en incluant les espaces de noms nécessaires dans votre projet :
```csharp
using Aspose.Email;
using System;
```

## Guide de mise en œuvre

### Fonctionnalité 1 : Charger un message MAPI à partir d'un fichier

#### Aperçu
Cette fonctionnalité montre comment charger un message MAPI à partir d'un chemin de fichier spécifié à l'aide d'Aspose.Email, essentiel pour le traitement des e-mails stockés sous forme de messages MAPI.

#### Étapes à mettre en œuvre
**Étape 1**: Définir le chemin du répertoire
Remplacer `"YOUR_DOCUMENT_DIRECTORY"` avec votre répertoire actuel où le `MapiTask.msg` le fichier est localisé.
```csharp
string dataDir = "YOUR_DOCUMENT_DIRECTORY"; // Remplacez par le chemin du répertoire de votre document
```
**Étape 2**: Charger le message MAPI
Utilisez le `MapiMessage.FromFile()` méthode pour charger le message, en créant un `MapiMessage` objet de celui-ci.
```csharp
// Charger le MapiMessage à partir du fichier spécifié
dynamic msg = MapiMessage.FromFile(dataDir + "MapiTask.msg");
```

### Fonctionnalité 2 : Configurer les options d'enregistrement MHT

#### Aperçu
La configuration des options d'enregistrement vous permet de personnaliser l'enregistrement de votre message MAPI au format MHTML. Cette étape implique la définition des modèles et des options de format.

#### Étapes à mettre en œuvre
**Étape 1**: Initialiser `MhtSaveOptions`
Configurez les options d’enregistrement MHTML par défaut, qui seront modifiées pour une sortie personnalisée.
```csharp
dynamic opt = SaveOptions.DefaultMhtml;
```
**Étape 2**: Définir les options de format
Activez le rendu des champs de tâche et des informations d'en-tête dans votre fichier MHTML enregistré.
```csharp
opt.MhtFormatOptions = MhtFormatOptions.RenderTaskFields | MhtFormatOptions.WriteHeader;
```
**Étape 3**: Personnaliser les modèles
Définissez des modèles HTML pour diverses propriétés de tâches afin de contrôler leur apparence dans le fichier de sortie.
```csharp
// Effacer les modèles existants
opt.FormatTemplates.Clear();

// Ajouter des modèles HTML personnalisés pour des propriétés de tâches spécifiques
opt.FormatTemplates.Add(MhtTemplateName.Task.Subject, "<span class='headerLineTitle'>Subject:</span><span class='headerLineText'>{0}</span><br/>");
opt.FormatTemplates.Add(MhtTemplateName.Task.ActualWork, "<span class='headerLineTitle'>Actual Work:</span><span class='headerLineText'>{0}</span><br/>");
opt.FormatTemplates.Add(MhtTemplateName.Task.TotalWork, "<span class='headerLineTitle'>Total Work:</span><span class='headerLineText'>{0}</span><br/>");
opt.FormatTemplates.Add(MhtTemplateName.Task.Status, "<span class='headerLineTitle'>Status:</span><span class='headerLineText'>{0}</span><br/>");
opt.FormatTemplates.Add(MhtTemplateName.Task.Owner, "<span class='headerLineTitle'>Owner:</span><span class='headerLineText'>{0}</span><br/>");
opt.FormatTemplates.Add(MhtTemplateName.Task.Priority, "<span class='headerLineTitle'>Priority:</span><span class='headerLineText'>{0}</span><br/>");
```

### Fonctionnalité 3 : Enregistrer le message MAPI au format MHTML

#### Aperçu
Une fois configuré, enregistrez votre message MAPI chargé dans un fichier MHTML. Cette étape finalise le processus de conversion en utilisant les options précédemment définies.

#### Étapes à mettre en œuvre
**Étape 1**: Définir le chemin du fichier de sortie
Spécifiez où vous souhaitez enregistrer le fichier MHTML converti.
```csharp
string outputFile = dataDir + "MapiTask_out.mht";
```
**Étape 2**Enregistrer le message
Utilisez le `Save()` méthode avec vos options configurées pour convertir et stocker le message au format MHTML.
```csharp
// Enregistrez le message dans un fichier MHT en utilisant les options précédemment configurées
dynamic msg.Save(outputFile, opt);
```

## Applications pratiques
1. **Archivage des e-mails**: Archivez les e-mails des systèmes hérités en les convertissant dans un format MHTML adapté au Web.
2. **Intégration avec les systèmes de gestion des tâches**:Convertissez les messages MAPI liés aux tâches pour les utiliser dans les applications de gestion de projet modernes qui prennent en charge les formats HTML.
3. **Documenter et partager**:Générez des rapports partageables de tâches de messagerie dans un format accessible, parfait pour la documentation ou la collaboration.

## Considérations relatives aux performances
### Optimisation des performances
- Chargez uniquement les fichiers nécessaires pour réduire l’utilisation de la mémoire.
- Utilisez des méthodes asynchrones lorsque cela est possible pour éviter de bloquer les opérations.

### Directives d'utilisation des ressources
- Surveillez l’empreinte mémoire de l’application lors du traitement de gros volumes de messages.
- Jetez les objets correctement après utilisation pour libérer des ressources.

### Meilleures pratiques pour la gestion de la mémoire .NET avec Aspose.Email
- Utiliser `using` instructions pour éliminer automatiquement les objets.
- Mettez régulièrement à jour Aspose.Email pour tirer parti des améliorations et des optimisations des versions plus récentes.

## Conclusion
Dans ce tutoriel, vous avez appris à charger des messages MAPI à partir de fichiers et à les enregistrer au format MHTML avec Aspose.Email pour .NET. Vous disposez désormais des connaissances nécessaires pour implémenter ces fonctionnalités dans vos applications et ainsi améliorer vos capacités de gestion des e-mails.

**Prochaines étapes :**
- Expérimentez avec différents `MhtSaveOptions` paramètres.
- Découvrez les fonctionnalités supplémentaires fournies par Aspose.Email pour .NET.

## Section FAQ
1. **Puis-je utiliser Aspose.Email gratuitement ?**
   - Oui, vous pouvez commencer avec une licence d'essai gratuite de 30 jours pour tester toutes les fonctionnalités sans limitations.
2. **Quels formats Aspose.Email prend-il en charge en plus de MAPI et MHTML ?**
   - Il prend en charge divers formats de courrier électronique, notamment EML, MSG, PST, etc.
3. **Comment gérer les fichiers volumineux dans Aspose.Email ?**
   - Utilisez des techniques économes en mémoire comme le streaming pour lire/écrire des fichiers volumineux.
4. **Puis-je intégrer cette fonctionnalité dans une application Web ?**
   - Absolument ! Cette fonctionnalité est idéale pour les applications web nécessitant des fonctionnalités de gestion des e-mails.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}