---
"date": "2025-05-30"
"description": "Découvrez comment configurer et gérer des tâches hebdomadaires récurrentes avec Aspose.Email pour .NET. Ce guide explique comment créer, configurer et optimiser vos solutions de planification."
"title": "Comment créer des tâches MapiTask hebdomadaires récurrentes dans .NET avec Aspose.Email"
"url": "/fr/net/calendar-appointments/create-manage-weekly-maptasks-net-aspose-email/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Comment créer des tâches MapiTask hebdomadaires récurrentes dans .NET avec Aspose.Email

## Introduction

Gérer efficacement les tâches récurrentes est essentiel pour les développeurs travaillant sur des applications intégrant des fonctionnalités de planification ou de calendrier. Que vous développiez un outil interne de gestion des tâches ou que vous intégriez des fonctionnalités de calendrier à une application métier, la création et la gestion de tâches récurrentes hebdomadaires peuvent considérablement améliorer la productivité.

Dans ce tutoriel, nous allons explorer comment utiliser **Aspose.Email pour .NET** Pour créer des tâches MapiTask hebdomadaires récurrentes se terminant après une date spécifique. Cette fonctionnalité est précieuse pour les développeurs souhaitant automatiser la planification de leurs applications grâce aux fonctionnalités robustes d'Aspose.Email.

### Ce que vous apprendrez :
- Configuration d'Aspose.Email pour .NET
- Créer une MapiTask hebdomadaire récurrente avec une date de fin spécifiée
- Mise en œuvre de modèles de récurrence sur plusieurs jours
- Calcul du nombre d'occurrences en fonction de règles de récurrence personnalisées

Prêt à vous lancer dans la création de solutions de planification performantes ? C'est parti !

## Prérequis

Avant de commencer, assurez-vous d’avoir les éléments suivants :

- **Aspose.Email pour .NET** bibliothèque : vous pouvez l’installer à l’aide de NuGet ou d’autres gestionnaires de packages.
- **.NET Framework 4.6.1 ou version ultérieure** ou **.NET Core/5+**: Assurez-vous que votre environnement de développement est configuré avec une version .NET compatible.
- Connaissances de base de C# et familiarité avec les concepts de programmation orientée objet.

## Configuration d'Aspose.Email pour .NET

Pour commencer à utiliser Aspose.Email pour .NET, vous devez l'ajouter à votre projet. Voici comment :

**Utilisation de .NET CLI :**
```bash
dotnet add package Aspose.Email
```

**Utilisation de la console du gestionnaire de packages :**
```powershell
Install-Package Aspose.Email
```

**Interface utilisateur du gestionnaire de packages NuGet :**
- Recherchez « Aspose.Email » et installez la dernière version.

### Acquisition de licence

Vous pouvez acquérir une licence via :

- **Essai gratuit**:Testez les fonctionnalités sans limitations.
- **Licence temporaire**:Utilisez ceci pour évaluer les capacités étendues.
- **Achat**:Pour un accès complet, achetez une licence commerciale.

Une fois que vous avez votre fichier de licence, initialisez Aspose.Email en appliquant la licence dans votre code :
```csharp
Aspose.Email.License license = new Aspose.Email.License();
license.SetLicense("path_to_license_file.lic");
```

## Guide de mise en œuvre

Nous allons décomposer l'implémentation en deux fonctionnalités principales : la création d'une récurrence hebdomadaire sur une seule journée et la configuration de récurrences sur plusieurs jours.

### Création d'une MapiTask hebdomadaire récurrente se terminant après une date spécifique

#### Aperçu
Cette fonctionnalité vous permet de créer des tâches récurrentes un jour précis chaque semaine jusqu'à leur achèvement après une date donnée. Elle est idéale pour planifier des réunions ou des échéances récurrentes.

#### Étapes de mise en œuvre
**Étape 1 : Configurer le modèle de récurrence**
Ici, nous allons configurer le modèle de récurrence en utilisant `MapiCalendarWeeklyRecurrencePattern`.
```csharp
var rec = new MapiCalendarWeeklyRecurrencePattern
{
    EndType = MapiCalendarRecurrenceEndType.EndAfterDate,
    PatternType = MapiCalendarRecurrencePatternType.Week,
    Period = 1, // Récurrence hebdomadaire
    WeekStartDay = DayOfWeek.Sunday,
    DayOfWeek = MapiCalendarDayOfWeek.Friday, // Récurrence le vendredi
    EndDate = new DateTime(2015, 9, 1).Add(TimeZone.CurrentTimeZone.GetUtcOffset(DateTime.Now)),
    OccurrenceCount = GetOccurrenceCount(
        new DateTime(2015, 7, 16).Add(TimeZone.CurrentTimeZone.GetUtcOffset(DateTime.Now)),
        new DateTime(2015, 9, 1).Add(TimeZone.CurrentTimeZone.GetUtcOffset(DateTime.Now)), 
        "FREQ=WEEKLY;BYDAY=FR;INTERVAL=1")
};
```
**Étape 2 : Créer la MapiTask**
Maintenant que notre modèle de récurrence est configuré, créons une tâche et attribuons-lui ce modèle.
```csharp
MapiTask task = new MapiTask(
    "This is test task",
    "Sample Body",
    new DateTime(2015, 7, 16).Add(TimeZone.CurrentTimeZone.GetUtcOffset(DateTime.Now)),
    new DateTime(2015, 7, 16).Add(TimeZone.CurrentTimeZone.GetUtcOffset(DateTime.Now))
);
task.State = MapiTaskState.NotAssigned;

if (rec.OccurrenceCount == 0)
{
    rec.OccurrenceCount = 1; // Assurer au moins une occurrence
}

task.Recurrence = rec;
```
**Étape 3 : Enregistrer la tâche**
Enfin, enregistrez votre tâche dans un fichier .msg pour la persistance.
```csharp
string dataDir = "YOUR_DOCUMENT_DIRECTORY";
task.Save(dataDir + "/SetWeeklyEndAfterDateEveryDayRecurrence_out.msg", TaskSaveFormat.Msg);
```

### Création d'une MapiTask hebdomadaire récurrente sur plusieurs jours se terminant après une date spécifique

#### Aperçu
Cette fonctionnalité étend la configuration précédente pour autoriser les tâches qui se répètent plusieurs jours par semaine, offrant ainsi une flexibilité pour les besoins de planification plus complexes.

#### Étapes de mise en œuvre
**Étape 1 : Configurer le modèle de récurrence sur plusieurs jours**
Établissez un modèle qui comprend plusieurs jours de récurrence par semaine.
```csharp
var record = new MapiCalendarWeeklyRecurrencePattern
{
    EndType = MapiCalendarRecurrenceEndType.EndAfterDate,
    PatternType = MapiCalendarRecurrencePatternType.Week,
    Period = 2, // Se produit toutes les deux semaines
    WeekStartDay = DayOfWeek.Sunday,
    EndDate = new DateTime(2015, 9, 1).Add(TimeZone.CurrentTimeZone.GetUtcOffset(DateTime.Now)),
    DayOfWeek = MapiCalendarDayOfWeek.Friday | MapiCalendarDayOfWeek.Monday, // Récurrence les vendredis et lundis
    OccurrenceCount = GetOccurrenceCount(
        new DateTime(2015, 7, 16).Add(TimeZone.CurrentTimeZone.GetUtcOffset(DateTime.Now)), 
        new DateTime(2015, 9, 1).Add(TimeZone.CurrentTimeZone.GetUtcOffset(DateTime.Now)), 
        "FREQ=WEEKLY;BYDAY=FR,MO;INTERVAL=2")
};
```
**Étape 2 : Créer et attribuer la MapiTask**
Comme précédemment, créez une tâche et attribuez-lui ce modèle sur plusieurs jours.
```csharp
MapiTask task = new MapiTask(
    "This is test task",
    "Sample Body",
    new DateTime(2015, 7, 16).Add(TimeZone.CurrentTimeZone.GetUtcOffset(DateTime.Now)),
    new DateTime(2015, 7, 16).Add(TimeZone.CurrentTimeZone.GetUtcOffset(DateTime.Now))
);
task.State = MapiTaskState.NotAssigned;
task.Recurrence = record;
```
**Étape 3 : Enregistrer la tâche sur plusieurs jours**
Enregistrez votre tâche de la même manière pour vous assurer qu'elle est stockée correctement.
```csharp
string dataDir = "YOUR_DOCUMENT_DIRECTORY";
task.Save(dataDir + "/SetWeeklyEndAfterDateMultipleDaysRecurrence_out.msg", TaskSaveFormat.Msg);
```

## Applications pratiques

Voici quelques applications pratiques de ces fonctionnalités :

1. **Automatisation des réunions hebdomadaires**:Planifiez des réunions d’équipe récurrentes à des jours précis, comme le vendredi.
2. **Délais des tâches**: Définissez des délais hebdomadaires pour les tâches du projet qui se répètent chaque lundi et vendredi.
3. **planification d'événements**:Gérer les calendriers de planification d'événements qui nécessitent des suivis sur plusieurs jours chaque semaine.

## Considérations relatives aux performances

- **Optimiser l'utilisation de la mémoire**: Assurez-vous de supprimer correctement les objets pour éviter les fuites de mémoire, en particulier lorsque vous traitez de grands ensembles de données ou de nombreuses tâches récurrentes.
- **Calculs de dates efficaces**:Utilisez des algorithmes efficaces pour les calculs de date dans vos règles de récurrence afin de minimiser le temps de traitement.
- **Opérations asynchrones**:Lors de l'enregistrement de tâches sur un disque ou sur un réseau, envisagez des méthodes asynchrones pour améliorer les performances.

## Conclusion

Dans ce tutoriel, nous avons expliqué comment créer et gérer des MapiTasks hebdomadaires récurrentes avec Aspose.Email pour .NET. En suivant les étapes décrites ci-dessus, vous pourrez facilement implémenter des fonctionnalités de planification sophistiquées dans vos applications.

Pour explorer davantage les capacités d'Aspose.Email ou aborder des scénarios plus complexes, pensez à consulter leur documentation officielle et leurs forums communautaires.

## FAQ

**Q : Comment installer Aspose.Email pour .NET ?**
R : Vous pouvez l’installer via le gestionnaire de packages NuGet à l’aide de la commande `Install-Package Aspose.Email`.

**Q : Qu'est-ce qu'une MapiTask ?**
R : Une MapiTask représente une tâche Outlook avec des propriétés telles que l’objet, la date d’échéance et le modèle de récurrence.

**Q : Puis-je personnaliser davantage les modèles de récurrence ?**
R : Oui, vous pouvez utiliser différents types de récurrence comme quotidienne ou mensuelle en ajustant le `PatternType` propriété de `MapiCalendarRecurrencePattern`.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}