---
"date": "2025-05-30"
"description": "Découvrez comment automatiser les tâches récurrentes hebdomadaires avec Aspose.Email pour .NET. Suivez notre guide complet pour configurer et implémenter MapiTasks avec des modèles de récurrence."
"title": "Créer des tâches hebdomadaires récurrentes avec Aspose.Email .NET pour le calendrier et les rendez-vous"
"url": "/fr/net/calendar-appointments/create-weekly-recurring-tasks-aspose-email-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Créer des tâches hebdomadaires récurrentes avec Aspose.Email .NET pour le calendrier et les rendez-vous

## Introduction

Gérer des tâches récurrentes peut s'avérer complexe, surtout lorsqu'elles doivent se répéter chaque semaine et s'intégrer parfaitement à votre flux de travail. Ce tutoriel vous guide dans la création de tâches récurrentes hebdomadaires à l'aide de la puissante bibliothèque Aspose.Email pour .NET, idéale pour automatiser les rappels ou planifier des mises à jour régulières.

**Ce que vous apprendrez :**
- Comment créer une MapiTask avec une récurrence hebdomadaire.
- Configuration et configuration d'Aspose.Email pour .NET.
- Calcul des occurrences de tâches entre les dates à l'aide de règles de récurrence.
- Applications concrètes de l’intégration de tâches récurrentes dans les processus métier.

Rationalisons votre processus de gestion des tâches !

## Prérequis

Avant de commencer, assurez-vous d’avoir les éléments suivants :
- **Aspose.Email pour .NET** installé. Les instructions d'installation sont fournies ci-dessous.
- Un IDE compatible (par exemple, Visual Studio) pour le développement C#.
- Compréhension de base de la programmation C# et familiarité avec les manipulations de dates.

### Configuration d'Aspose.Email pour .NET

Pour commencer, installez la bibliothèque Aspose.Email dans votre projet :

**.NET CLI**
```bash
dotnet add package Aspose.Email
```

**Gestionnaire de paquets**
```powershell
Install-Package Aspose.Email
```

**Interface utilisateur du gestionnaire de packages NuGet :**
Recherchez « Aspose.Email » et sélectionnez la dernière version à installer.

#### Acquisition de licence
- **Essai gratuit :** Téléchargez un essai gratuit à partir de [Téléchargements d'Aspose](https://releases.aspose.com/email/net/).
- **Licence temporaire :** Demandez une licence temporaire à [Licence temporaire Aspose](https://purchase.aspose.com/temporary-license/) pour des tests prolongés.
- **Achat:** Pour une utilisation à long terme, pensez à acheter une licence via [Achat Aspose](https://purchase.aspose.com/buy).

Une fois le package installé et votre licence configurée, initialisez Aspose.Email comme suit :
```csharp
// Exemple d'initialisation de base (pas obligatoire dans tous les contextes)
var license = new Aspose.Email.License();
license.SetLicense("path_to_your_license_file.lic");
```

## Guide de mise en œuvre

Cette section couvre deux fonctionnalités principales : la création d'une tâche récurrente hebdomadaire et le calcul des occurrences.

### Fonctionnalité 1 : Création de tâches hebdomadaires avec récurrence

**Aperçu:**
Apprenez à créer une MapiTask qui se répète chaque semaine à l'aide d'Aspose.Email `MapiCalendarWeeklyRecurrencePattern`, automatisant la création de tâches sans intervention manuelle pour chaque occurrence.

#### Étape 1 : Définir les dates et ajuster le fuseau horaire
```csharp
// Définir les dates de début, d'échéance et de fin de la tâche
DateTime StartDate = new DateTime(2015, 7, 16);
DateTime DueDate = new DateTime(2015, 7, 16);
DateTime EndByDate = new DateTime(2015, 9, 1);

// Ajuster les dates en fonction du décalage horaire local
timeZone localZone = TimeZone.CurrentTimeZone;
TimeSpan ts = localZone.GetUtcOffset(DateTime.Now);
StartDate = StartDate.Add(ts);
DueDate = DueDate.Add(ts);
EndByDate = EndByDate.Add(ts);
```
**Explication:**
Les dates de début, d'échéance et de fin de la tâche sont ajustées en fonction du décalage horaire actuel afin de garantir l'exactitude dans différentes régions.

#### Étape 2 : Créer et configurer MapiTask
```csharp
// Créer une nouvelle MapiTask avec les détails spécifiés
MapiTask task = new MapiTask("This is a test task", "Sample Body", StartDate, DueDate);
task.State = MapiTaskState.NotAssigned;
```
**Explication:**
Initialiser le `MapiTask` Objet avec un titre, un corps, une date de début et une date d'échéance. Définissez l'état de la tâche sur `NotAssigned`, le marquant comme en attente.

#### Étape 3 : Définir un modèle de récurrence hebdomadaire
```csharp
// Configurer le modèle de récurrence hebdomadaire pour la tâche
var rec = new MapiCalendarWeeklyRecurrencePattern
{
    EndType = MapiCalendarRecurrenceEndType.EndAfterNOccurrences,
    PatternType = MapiCalendarRecurrencePatternType.Week,
    Period = 1,
    WeekStartDay = DayOfWeek.Sunday,
    DayOfWeek = MapiCalendarDayOfWeek.Friday,
    OccurrenceCount = GetOccurrenceCount(StartDate, EndByDate, "FREQ=WEEKLY;BYDAY=FR"),
};

// Assurez-vous qu'il y a au moins une occurrence
if (rec.OccurrenceCount == 0)
{
    rec.OccurrenceCount = 1;
}
task.Recurrence = rec;
```
**Explication:**
Cet extrait configure la tâche pour qu'elle se répète chaque semaine le vendredi. `GetOccurrenceCount` La fonction calcule le nombre d'occurrences entre les dates de début et de fin.

#### Étape 4 : Enregistrer la tâche
```csharp
// Enregistrer la tâche dans un fichier dans le répertoire de sortie spécifié
string outputPath = "@YOUR_OUTPUT_DIRECTORY/Weekly_out.msg";
task.Save(outputPath, TaskSaveFormat.Msg);
```
**Explication:**
La tâche terminée est enregistrée au format MSG. Assurez-vous de remplacer `@YOUR_OUTPUT_DIRECTORY` avec votre chemin actuel.

### Fonctionnalité 2 : Calcul des occurrences entre deux dates avec la règle de récurrence

**Aperçu:**
Déterminez le nombre de fois qu'un événement récurrent se produit entre deux dates à l'aide d'Aspose.Email `CalendarRecurrence` classe.

#### Étape 1 : Définir les dates et la règle de récurrence
```csharp
// Définir les dates de début et de fin pour calculer les occurrences
DateTime Start = new DateTime(2015, 7, 16);
DateTime EndBy = new DateTime(2015, 9, 1);
string RRule = "FREQ=WEEKLY;BYDAY=FR";
```
**Explication:**
Ces variables définissent la plage de dates et une règle pour les occurrences hebdomadaires le vendredi.

#### Étape 2 : Calculer les occurrences
```csharp
// Obtenir le nombre d'occurrences entre les deux dates en fonction de la règle de récurrence
uint occurrenceCount = GetOccurrenceCount(Start, EndBy, RRule);
```
**Explication:**
La fonction calcule combien de fois la tâche se répète au cours de la période spécifiée.

#### Étape 3 : Mise en œuvre `GetOccurrenceCount` Méthode
```csharp
private static uint GetOccurrenceCount(DateTime start, DateTime endBy, string rrule)
{
    // Créer un objet CalendarRecurrence au format DTSTART et RRULE
    CalendarRecurrence pattern = new CalendarRecurrence(string.Format("DTSTART:{0}\r\nRRULE:{1}", start.ToString("yyyyMMdd"), rrule));

    // Générer des occurrences dans la plage de dates spécifiée
    DateCollection dates = pattern.GenerateOccurrences(start, endBy);

    // Renvoie le nombre d'occurrences générées
    return (uint)dates.Count;
}
```
**Explication:**
Le `CalendarRecurrence` l'objet est initialisé avec une date de début et une règle de récurrence, générant des occurrences qui se situent dans la plage donnée.

## Applications pratiques

Explorez des scénarios réels dans lesquels des tâches récurrentes hebdomadaires peuvent être intégrées :
1. **Gestion de projet :** Automatisez les rappels réguliers de mise à jour de statut pour les membres de l'équipe selon un calendrier défini.
2. **Finance:** Planifier la génération et la distribution hebdomadaires de rapports financiers aux parties prenantes.
3. **Assistance clientèle :** Organisez des appels de suivi hebdomadaires ou des e-mails aux principaux clients pour obtenir des commentaires sur le service.
4. **Administration des RH :** Mettre en œuvre des calendriers d’évaluation des performances récurrents pour les employés.
5. **Soins de santé :** Automatisez la planification des examens de routine des patients ou des rappels de médicaments.

## Considérations relatives aux performances

Lorsque vous travaillez avec Aspose.Email dans .NET, tenez compte de ces conseils :
- Surveillez l’utilisation de la mémoire pour garantir une gestion efficace des ressources.
- Optimisez les manipulations de dates et les configurations de tâches pour plus de rapidité.
- Examinez régulièrement les indicateurs de performance et ajustez les paramètres selon les besoins.

**Meilleures pratiques :**
- Éliminer les objets de manière appropriée en utilisant `using` déclarations ou élimination manuelle pour libérer rapidement des ressources.
- Testez la solution dans un environnement de test avant de la déployer en production.

## Conclusion

En suivant ce guide, vous avez appris à automatiser efficacement les tâches hebdomadaires récurrentes avec Aspose.Email pour .NET. Cet outil améliore votre capacité à gérer les tâches répétitives et garantit que rien ne passe entre les mailles du filet.

### Prochaines étapes :
- Expérimentez différents modèles de récurrence.
- Découvrez d’autres fonctionnalités d’Aspose.Email pour des fonctionnalités supplémentaires.
- Partagez cette solution au sein de votre équipe ou de votre organisation pour accroître son impact.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}