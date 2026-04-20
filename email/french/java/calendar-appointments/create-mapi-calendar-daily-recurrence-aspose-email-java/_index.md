---
date: '2026-03-20'
description: Apprenez à créer un calendrier Outlook en Java avec une récurrence quotidienne
  et des exceptions, puis à enregistrer le calendrier au format PST à l’aide d’Aspose.Email
  pour Java.
keywords:
- MAPI Calendar creation
- daily recurrence events
- Java calendar exceptions
title: Créer un calendrier Outlook en Java avec récurrence quotidienne et exceptions
url: /fr/java/calendar-appointments/create-mapi-calendar-daily-recurrence-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Comment créer outlook calendar java avec récurrence quotidienne et exceptions

Gérer efficacement les événements récurrents peut être difficile, surtout lorsque vous avez besoin d'un **outlook calendar java** qui prend en charge les modèles de récurrence quotidienne et les exceptions occasionnelles. Dans ce tutoriel, vous apprendrez comment créer des objets Outlook calendar Java, configurer la récurrence quotidienne, ajouter des instances d'exception, et enfin **save calendar to PST** en utilisant Aspose.Email for Java. À la fin, vous disposerez d'un extrait de code réutilisable que vous pourrez intégrer à n'importe quel service de planification basé sur Java.

## Réponses rapides
- **Quelle bibliothèque ?** Aspose.Email for Java  
- **Tâche principale ?** Create an Outlook calendar Java with daily recurrence and exceptions  
- **JDK requis ?** Java 16 or higher  
- **Puis-je joindre des fichiers aux exceptions ?** Yes, using `MapiCalendarExceptionInfo`  
- **Où le calendrier est‑il stocké ?** In a PST file via `PersonalStorage`

## Qu'est‑ce qu'un Outlook calendar java ?
Un objet Outlook calendar Java (implémenté comme un calendrier MAPI) suit les mêmes normes que les rendez‑vous Microsoft Outlook. Il stocke des règles de récurrence riches, la gestion des exceptions, les participants et les pièces jointes, ce qui le rend idéal pour une planification de niveau entreprise.

## Pourquoi utiliser Aspose.Email for Java ?
Aspose.Email fournit une API pure‑Java qui vous permet de travailler avec des objets MAPI sans nécessiter l'installation d'Outlook. Cette approche **aspose email tutorial java** permet la génération côté serveur de fichiers PST, des séries de réunions automatisées, et un contrôle complet de la logique de récurrence.

## Prérequis
Avant de commencer, assurez-vous d'avoir la configuration suivante :
- **Aspose.Email Library** : Version 25.4 (ou ultérieure) – disponible via Maven ou téléchargement direct.  
- **Java Development Kit (JDK)** : JDK 16 ou plus récent.  
- **IDE** : IntelliJ IDEA, Eclipse, NetBeans, ou tout éditeur compatible Java.

### Bibliothèques et dépendances requises
Pour intégrer Aspose.Email à votre projet avec Maven, ajoutez la dépendance suivante à votre `pom.xml` :

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Obtention de licence
Pour utiliser Aspose.Email, vous aurez besoin d'une licence :
- **Free Trial** – explorez toutes les fonctionnalités gratuitement.  
- **Temporary License** – demandez une évaluation prolongée.  
- **Full License** – achetez pour les déploiements en production.

## Configuration d'Aspose.Email pour Java
Tout d'abord, configurez votre environnement :

1. Vérifiez que JDK 16 est installé et que `JAVA_HOME` est configuré.  
2. Ajoutez la dépendance Maven (ou téléchargez le JAR) à votre projet.  

Voici un petit extrait montrant comment charger un fichier de licence :

```java
import com.aspose.email.*;

public class InitializeAspose {
    public static void main(String[] args) {
        // Set up a license if available
        License license = new License();
        try {
            license.setLicense("path/to/your/license.lic");
        } catch (Exception e) {
            System.out.println("License not found, using trial version.");
        }
    }
}
```

## Guide d'implémentation

### Création d'Outlook calendar java avec récurrence quotidienne et exceptions

#### Vue d'ensemble
Cette fonctionnalité vous permet d'automatiser des rendez‑vous récurrents tout en pouvant ignorer ou modifier des instances spécifiques.

#### Implémentation étape par étape

**1. Définir la date de début de l'événement**  
Déterminez quand la série doit commencer :

```java
Date startDate = addHours(newDate(2018, 7, 19), 12);
```

**2. Créer l'objet MAPI Calendar**  
Fournissez le lieu, le sujet et la description :

```java
MapiCalendar calendar = new MapiCalendar("location1", "summary1", "description1", startDate, addHours(startDate, 1));
```

**3. Définir un modèle de récurrence quotidienne**  
Configurez l'événement pour qu'il se répète chaque jour :

```java
MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
MapiCalendarRecurrencePattern pattern = recurrence.getRecurrencePattern();

pattern.setPatternType(MapiCalendarRecurrencePatternType.Day);
pattern.setPeriod(1); // Daily
pattern.setEndType(MapiCalendarRecurrenceEndType.NeverEnd);
```

**4. Ajouter une exception à la récurrence**  
Spécifiez une date qui doit être exclue (ou modifiée) :

```java
Date exceptionDate = addDays(startDate, 3);

MapiCalendarExceptionInfo exception = new MapiCalendarExceptionInfo();
exception.setLocation("exceptionLocation");
exception.setSubject("exceptionSubject");
exception.setBody("exceptionBody");

exception.setOriginalStartDate(exceptionDate);
exception.setStartDateTime(exceptionDate);
exception.setEndDateTime(addHours(exceptionDate, 5));

pattern.getExceptions().addItem(exception);
pattern.getModifiedInstanceDates().addItem(exceptionDate);
pattern.getDeletedInstanceDates().addItem(exceptionDate);

calendar.setRecurrence(recurrence);
```

### Ajout de fichiers aux exceptions du calendrier

#### Vue d'ensemble
Vous pouvez joindre des documents de support (par ex., des ordres du jour) à n'importe quelle instance d'exception.

**1. Créer et attacher un fichier**

```java
MapiCalendarExceptionInfo exception = new MapiCalendarExceptionInfo();
exception.getAttachments().add("file.txt", "hello, world!".getBytes());
```

### Enregistrement d'Outlook calendar java au format PST (save calendar to pst)

#### Vue d'ensemble
Enregistrez le calendrier dans un fichier PST afin qu'Outlook ou d'autres clients puissent le lire.

**1. Créer et enregistrer le calendrier au format PST**

```java
final PersonalStorage pst = PersonalStorage.create(new ByteArrayOutputStream(), FileFormatVersion.Unicode);
try {
    FolderInfo calendarFolder = pst.createPredefinedFolder("Calendar", StandardIpmFolder.Appointments);
    calendarFolder.addMapiMessageItem(calendar);
} finally {
    pst.dispose();
}
```

## Applications pratiques
- **Corporate Scheduling** – automatiser les séries de réunions, en sautant automatiquement les jours fériés.  
- **Project Management** – suivre les jalons récurrents avec des décalages de dates occasionnels.  
- **Event Planning** – gérer des conférences sur plusieurs jours où certaines sessions sont annulées ou reprogrammées.

### Possibilités d'intégration
Combinez Aspose.Email avec des plateformes CRM, des API de gestion de tâches ou des moteurs de flux de travail personnalisés pour piloter une automatisation de bout en bout.

## Considérations de performance
- **Dispose Resources** – appelez toujours `dispose()` sur `PersonalStorage` pour libérer les poignées de fichiers.  
- **Stream Usage** – privilégiez `ByteArrayOutputStream` ou les flux de fichiers pour éviter de charger des PST entiers en mémoire.  
- **Async Operations** – pour la génération massive de calendriers, exécutez la logique de création sur un thread d'arrière‑plan afin de garder l'interface réactive.

## Conclusion
En suivant ce guide, vous savez maintenant comment **create outlook calendar java** des objets avec récurrence quotidienne, ajouter des exceptions, joindre des fichiers, et **save calendar to PST**. Ces capacités vous permettent de créer des fonctionnalités de planification robustes sans jamais toucher directement à Outlook.

### Prochaines étapes
- Expérimentez les modèles de récurrence hebdomadaires ou mensuels.  
- Explorez des propriétés MAPI supplémentaires telles que les participants, les rappels et les catégories.  
- Examinez la documentation complète de l'API Aspose.Email pour des scénarios plus avancés.

## Questions fréquentes

**Q : La bibliothèque prend‑elle en charge les rendez‑vous sensibles au fuseau horaire ?**  
R : Oui, vous pouvez définir les propriétés `StartTimeZone` et `EndTimeZone` sur `MapiCalendar`.

**Q : Puis‑je supprimer programmatiquement une occurrence unique d'une série récurrente ?**  
R : Utilisez la collection `DeletedInstanceDates` du modèle de récurrence pour marquer des dates spécifiques comme supprimées.

**Q : Existe‑t‑il des limites de taille pour un fichier PST créé avec Aspose.Email ?**  
R : Les fichiers PST respectent les limites du format Unicode (jusqu'à 2 Go par défaut), mais vous pouvez configurer des tailles plus importantes via les paramètres de `PersonalStorage`.

**Q : Comment ajouter des participants à une demande de réunion ?**  
R : Créez des objets `MapiRecipient`, définissez leur `RecipientType` sur `MapiRecipientType.MAPI_TO`, puis ajoutez‑les à la collection `Recipients` du `MapiMessage`.

**Q : La bibliothèque prend‑elle en charge les tâches récurrentes (et pas seulement les rendez‑vous) ?**  
R : Oui, Aspose.Email fournit également `MapiTask` avec des capacités de récurrence similaires.

**Q : Puis‑je utiliser ce guide dans le cadre d’une série de tutoriels aspose email tutorial java ?**  
R : Absolument – les étapes présentées ici constituent une partie essentielle de tout tutoriel Aspose.Email Java traitant de la création de calendriers.

## Ressources
- [Documentation Aspose.Email pour Java](https://reference.aspose.com/email/java/)
- [Télécharger Aspose.Email](https://releases.aspose.com/email/java/)
- [Acheter une licence](https://purchase.aspose.com/buy)
- [Version d'essai gratuite](https://releases.aspose.com/email/java/)
- [Demander une licence temporaire](https://purchase.aspose.com/temporary-license/)
- [Forum de support Aspose](https://forum.aspose.com/c/email/10)

---

**Dernière mise à jour :** 2026-03-20  
**Testé avec :** Aspose.Email for Java 25.4 (JDK 16)  
**Auteur :** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}