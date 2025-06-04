---
"date": "2025-05-30"
"description": "Découvrez comment automatiser la création de tâches MAPI récurrentes annuelles avec Aspose.Email pour .NET. Ce guide couvre la configuration, les propriétés des tâches, les modèles de récurrence et l'enregistrement au format MSG."
"title": "Créer des tâches MAPI récurrentes annuelles avec Aspose.Email pour .NET"
"url": "/fr/net/mapi-operations/aspose-email-net-create-mapi-task-yearly-recurrence/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Création de tâches MAPI récurrentes annuelles avec Aspose.Email pour .NET

## Introduction
Une gestion efficace des tâches est essentielle, tant dans le cadre professionnel que personnel, notamment face à des événements récurrents ou des échéances. Automatiser la création de fichiers de tâches s'intégrant parfaitement aux systèmes de messagerie permet de gagner du temps et de réduire les erreurs. Ce tutoriel vous guidera dans l'utilisation d'Aspose.Email pour .NET pour créer et enregistrer des tâches MAPI avec une récurrence annuelle, une exigence courante dans les logiciels de gestion de projet et de productivité.

**Ce que vous apprendrez :**
- Comment configurer Aspose.Email pour .NET.
- Créer un simple `MapiTask` avec des propriétés spécifiques.
- Mise en place de modèles de récurrence annuels pour les tâches.
- Enregistrer ces tâches sous `.msg` fichiers.

## Prérequis
Pour suivre ce tutoriel, assurez-vous d'avoir :
- **Aspose.Email pour .NET**: La bibliothèque principale permettant d'accéder aux fonctionnalités des tâches MAPI. Installez-la dans votre projet.
- **Environnement de développement**: Visual Studio 2022 ou version ultérieure sur Windows ou Linux avec le SDK .NET installé est recommandé.
- **Connaissances de base en C#**Familiarité avec la programmation C# et compréhension des manipulations de date et d'heure.

## Configuration d'Aspose.Email pour .NET
### Installation
Pour installer Aspose.Email, utilisez l’une de ces méthodes :

**.NET CLI :**
```shell
dotnet add package Aspose.Email
```

**Console du gestionnaire de paquets :**
```shell
Install-Package Aspose.Email
```

**Interface utilisateur du gestionnaire de packages NuGet**:Recherchez « Aspose.Email » et installez la dernière version.
### Acquisition de licence
- **Essai gratuit**:Commencez par un essai gratuit pour explorer les capacités de la bibliothèque.
- **Licence temporaire**: Obtenir un permis temporaire [ici](https://purchase.aspose.com/temporary-license/) pour des tests approfondis sans limitations.
- **Achat**: Pour une utilisation en production, achetez une licence auprès de [Aspose](https://purchase.aspose.com/buy).

## Guide de mise en œuvre
Cette section couvre la création d'une tâche MAPI avec des propriétés spécifiques et la configuration de la récurrence annuelle.
### Créer et enregistrer une MapiTask
#### Aperçu
Créer une tâche implique de définir ses propriétés, comme l'objet, le corps, la date de début, la date d'échéance et l'état. Nous l'enregistrerons sous forme de `.msg` fichier, la norme pour les tâches Outlook.
#### Étapes de mise en œuvre
**1. Configurer les répertoires**
Définissez les chemins d’accès à votre document et aux répertoires de sortie :
```csharp
string dataDir = "YOUR_DOCUMENT_DIRECTORY";
string outputDir = "YOUR_OUTPUT_DIRECTORY";
```
**2. Configurer le fuseau horaire**
Ajuster les dates en fonction du fuseau horaire local :
```csharp
TimeZone localZone = TimeZone.CurrentTimeZone;
TimeSpan timeSpan = localZone.GetUtcOffset(DateTime.Now);
DateTime StartDate = new DateTime(2023, 1, 1).Add(timeSpan);
DateTime DueDate = new DateTime(2023, 12, 31).Add(timeSpan);
```
**3. Créer MapiTask**
Instancier un `MapiTask` avec des propriétés spécifiées :
```csharp
MapiTask task = new MapiTask("Yearly Review Task", "Annual review of project milestones.", StartDate, DueDate);
task.State = MapiTaskState.NotStarted;
```
**4. Enregistrer la tâche sous forme de fichier .msg**
Enregistrez la tâche créée dans un répertoire de sortie :
```csharp
string filePath = outputDir + "/YearlyReviewTask_out.msg";
task.Save(filePath, TaskSaveFormat.Msg);
```
### Définir la récurrence annuelle pour MapiTask
#### Aperçu
Les schémas de récurrence sont essentiels pour les tâches qui se répètent au fil du temps. Nous allons ici établir un schéma de récurrence annuel.
#### Étapes de mise en œuvre
**1. Définir le modèle de récurrence**
Créer un `MapiCalendarYearlyRecurrencePattern`:
```csharp
MapiCalendarYearlyRecurrencePattern rec = new MapiCalendarYearlyRecurrencePattern
{
    DayOfMonth = 15,
    MonthOfYear = MapiMonth.January, // Début en janvier
    Type = MapiCalendarRecurrenceType.Month,
    EndType = MapiCalendarRecurrenceEndType.NeverEnding,
};
```
**2. Attribuer une récurrence à une tâche**
Attribuer le modèle de récurrence à la tâche :
```csharp
MapiTask task = new MapiTask("Yearly Review Task", "Annual review of project milestones.", DateTime.Now, DateTime.Now.AddDays(1));
task.Recurrence = rec;
```
**3. Enregistrer la tâche récurrente**
Enregistrez la tâche récurrente de la même manière qu'une tâche non récurrente :
```csharp
string filePath = outputDir + "/YearlyReviewTask_out.msg";
task.Save(filePath, TaskSaveFormat.Msg);
```
### Conseils de dépannage
- Assurer les chemins dans `dataDir` et `outputDir` sont correctes.
- Validez qu'Aspose.Email est correctement sous licence pour éviter les limitations.
- Vérifiez les paramètres de fuseau horaire si les tâches apparaissent avec des dates incorrectes.
## Applications pratiques
Considérez ces scénarios pour utiliser des tâches MAPI récurrentes annuelles :
1. **Gestion de projet**: Automatisez la création de tâches pour les revues annuelles de projet ou les jalons.
2. **planification d'événements**:Configurez des rappels pour les événements annuels, tels que les conférences ou les réunions.
3. **Applications de productivité personnelle**: Intégrez-le aux applications qui gèrent les horaires personnels et les listes de tâches annuelles.
## Considérations relatives aux performances
- Optimisez les chemins de fichiers pour minimiser les opérations d’E/S sur le disque.
- Gérez l'utilisation de la mémoire en supprimant les objets de manière appropriée à l'aide de `Dispose()` après la création de la tâche.
- Utilisez des méthodes asynchrones lorsque cela est applicable pour de meilleures performances dans les applications avec de lourdes charges.
## Conclusion
Vous savez maintenant comment créer et enregistrer des tâches MAPI avec une récurrence annuelle grâce à Aspose.Email pour .NET. Cette fonctionnalité améliore la productivité en automatisant les tâches répétitives et en garantissant la cohérence entre vos projets et vos plannings personnels.
**Prochaines étapes :**
- Expérimentez en modifiant les modèles de récurrence.
- Découvrez d'autres fonctionnalités fournies par Aspose.Email pour .NET dans la gestion des tâches et au-delà.
**Appel à l'action**:Essayez d’implémenter cette solution dans votre prochain projet pour simplifier la planification des tâches !
## Section FAQ
1. **Qu'est-ce qu'Aspose.Email pour .NET ?**
   - Une bibliothèque puissante qui permet la manipulation de messages électroniques, de calendriers et de tâches dans les applications .NET.
2. **Comment gérer les problèmes de licence avec Aspose.Email ?**
   - Commencez par un essai gratuit ou acquérez une licence temporaire pour bénéficier de toutes les fonctionnalités pendant les phases de test.
3. **Puis-je l’utiliser dans des environnements non Windows ?**
   - Oui, Aspose.Email est multiplateforme et fonctionne aussi bien sur Linux que sur Windows.
4. **Que faire si mon modèle de récurrence ne s’applique pas comme prévu ?**
   - Vérifiez votre `DayOfMonth` et `MonthOfYear` paramètres pour vous assurer qu'ils correspondent à votre calendrier prévu.
5. **Où puis-je trouver plus de ressources sur MapiTasks ?**
   - Visitez le [Documentation Aspose.Email](https://reference.aspose.com/email/net/) pour des guides complets et des références API.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}