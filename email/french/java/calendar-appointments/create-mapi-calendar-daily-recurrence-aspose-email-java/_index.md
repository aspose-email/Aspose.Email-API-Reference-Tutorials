---
date: '2025-12-20'
description: Apprenez à créer un calendrier MAPI en Java, à gérer les modèles de récurrence
  quotidienne et à gérer les exceptions à l'aide d'Aspose.Email pour Java.
keywords:
- MAPI Calendar creation
- daily recurrence events
- Java calendar exceptions
title: Créer un calendrier MAPI en Java avec récurrence quotidienne et exceptions
url: /fr/java/calendar-appointments/create-mapi-calendar-daily-recurrence-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Comment créer mapi calendar java avec récurrence quotidienne et exceptions

Gérer efficacement les événements récurrents peut être difficile, surtout lorsqu'il faut gérer des exceptions ou des modifications. Dans ce tutoriel, vous allez **create mapi calendar java** objects, configurer des modèles de récurrence quotidienne et ajouter des exceptions en utilisant Aspose.Email for Java. Vous apprendrez comment automatiser les tâches de planification de manière transparente au sein de vos applications.

## Réponses rapides
- **Quelle bibliothèque ?** Aspose.Email for Java  
- **Tâche principale ?** Create a MAPI calendar with daily recurrence and exceptions  
- **JDK requis ?** Java 16 or higher  
- **Puis-je joindre des fichiers aux exceptions ?** Oui, using `MapiCalendarExceptionInfo`  
- **Où le calendrier est‑il stocké ?** Dans un PST file via `PersonalStorage`

### Qu'est-ce qu'un calendrier MAPI ?
Un calendrier MAPI (Messaging Application Programming Interface) est un format standard utilisé par Microsoft Outlook et d'autres clients de messagerie pour stocker les données de rendez‑vous. Il prend en charge des règles de récurrence riches, des exceptions et des pièces jointes, ce qui le rend idéal pour la planification d'entreprise.

### Pourquoi utiliser Aspose.Email for Java ?
Aspose.Email fournit une API pure‑Java qui vous permet de créer, modifier et enregistrer des objets MAPI sans dépendre d'Outlook. Cela signifie que vous pouvez créer des fonctionnalités de planification côté serveur, générer des fichiers PST et gérer des scénarios de récurrence complexes de manière programmatique.

## Prérequis

Avant de commencer, assurez-vous d'avoir la configuration suivante :

- **Bibliothèque Aspose.Email** : Version 25.4 (ou ultérieure) – disponible via Maven ou téléchargement direct.  
- **Java Development Kit (JDK)** : JDK 16 ou plus récent.  
- **IDE** : IntelliJ IDEA, Eclipse, NetBeans, ou tout éditeur compatible Java.

### Bibliothèques et dépendances requises

Pour intégrer Aspose.Email à votre projet avec Maven, ajoutez la dépendance suivante à votre `pom.xml` :

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Obtention de licence

Pour utiliser Aspose.Email, vous aurez besoin d'une licence :

- **Essai gratuit** – explorez toutes les fonctionnalités sans frais.  
- **Licence temporaire** – demandez‑la pour une évaluation prolongée.  
- **Licence complète** – achetez‑la pour les déploiements en production.

## Configuration d'Aspose.Email pour Java

Tout d'abord, configurez votre environnement :

1. Vérifiez que JDK 16 est installé et que `JAVA_HOME` est configuré.  
2. Ajoutez la dépendance Maven (ou téléchargez le JAR) à votre projet.  

Voici un petit extrait montrant comment charger un fichier de licence :

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

### Création d'un calendrier MAPI avec récurrence quotidienne et exceptions

#### Vue d'ensemble
Cette fonctionnalité vous permet d'automatiser les rendez‑vous récurrents tout en pouvant ignorer ou modifier des instances spécifiques.

#### Implémentation étape par étape

**1. Configurer la date de début de l'événement**  
Déterminez quand la série doit commencer :

```java
Date startDate = addHours(newDate(2018, 7, 19), 12);
```

**2. Créer l'objet calendrier MAPI**  
Fournissez le lieu, le sujet et la description :

```java
MapiCalendar calendar = new MapiCalendar("location1", "summary1", "description1", startDate, addHours(startDate, 1));
```

**3. Définir un modèle de récurrence quotidienne**  
Configurez l'événement pour qu'il se répète chaque jour :

```java
MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
MapiCalendarRecurrencePattern pattern = recurrence.getRecurrencePattern();

pattern.setPatternType(MapiCalendarRecurrencePatternType.Day);
pattern.setPeriod(1); // Daily
pattern.setEndType(MapiCalendarRecurrenceEndType.NeverEnd);
```

**4. Ajouter une exception à la récurrence**  
Spécifiez une date qui doit être exclue (ou modifiée) :

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

### Joindre des fichiers aux exceptions du calendrier

#### Vue d'ensemble
Vous pouvez joindre des documents de support (par ex., des ordres du jour) à n'importe quelle instance d'exception.

**1. Créer et joindre un fichier**

```java
MapiCalendarExceptionInfo exception = new MapiCalendarExceptionInfo();
exception.getAttachments().add("file.txt", "hello, world!".getBytes());
```

### Enregistrement du calendrier MAPI dans des fichiers PST

#### Vue d'ensemble
Enregistrez le calendrier dans un fichier PST afin qu'Outlook ou d'autres clients puissent le lire.

**1. Créer et enregistrer le calendrier dans un PST**

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
- **Planification d'entreprise** – automatiser les séries de réunions, en sautant automatiquement les jours fériés.  
- **Gestion de projet** – suivre les jalons récurrents avec des décalages de dates occasionnels.  
- **Organisation d'événements** – gérer des conférences sur plusieurs jours où certaines sessions sont annulées ou reprogrammées.

### Possibilités d'intégration
Combinez Aspose.Email avec des plateformes CRM, des API de gestion de tâches ou des moteurs de flux de travail personnalisés pour piloter une automatisation de bout en bout.

## Considérations de performance
- **Libérer les ressources** – appelez toujours `dispose()` sur `PersonalStorage` pour libérer les poignées de fichiers.  
- **Utilisation des flux** – privilégiez `ByteArrayOutputStream` ou les flux de fichiers pour éviter de charger des PST entiers en mémoire.  
- **Opérations asynchrones** – pour la génération massive de calendriers, exécutez la logique de création sur un thread d'arrière‑plan afin de garder l'interface réactive.

## Conclusion
En suivant ce guide, vous savez maintenant comment **create mapi calendar java** objects avec une récurrence quotidienne, ajouter des exceptions, joindre des fichiers et tout stocker dans un fichier PST. Ces capacités vous permettent de créer des fonctionnalités de planification robustes sans jamais toucher directement à Outlook.

### Prochaines étapes
- Expérimentez les modèles de récurrence hebdomadaires ou mensuels.  
- Explorez des propriétés MAPI supplémentaires telles que les participants, les rappels et les catégories.  
- Consultez la documentation complète de l'API Aspose.Email pour des scénarios plus avancés.

## Questions fréquemment posées

**Q : La bibliothèque prend‑elle en charge les rendez‑vous sensibles au fuseau horaire ?**  
R : Oui, vous pouvez définir les propriétés `StartTimeZone` et `EndTimeZone` sur `MapiCalendar`.

**Q : Puis‑je supprimer programmétiquement une occurrence unique d'une série récurrente ?**  
R : Utilisez la collection `DeletedInstanceDates` du modèle de récurrence pour marquer des dates spécifiques comme supprimées.

**Q : Existe‑t‑il des limites de taille pour un fichier PST créé avec Aspose.Email ?**  
R : Les fichiers PST respectent les limites du format Unicode (jusqu'à 2 Go par défaut), mais vous pouvez configurer des tailles plus grandes via les paramètres de `PersonalStorage`.

**Q : Comment ajouter des participants à une demande de réunion ?**  
R : Créez des objets `MapiRecipient`, définissez leur `RecipientType` sur `MapiRecipientType.MAPI_TO` et ajoutez‑les à la collection `Recipients` du `MapiMessage`.

**Q : La bibliothèque prend‑elle en charge les tâches récurrentes (et pas seulement les rendez‑vous) ?**  
R : Oui, Aspose.Email propose également `MapiTask` avec des capacités de récurrence similaires.

## Ressources
- [Documentation Aspose.Email pour Java](https://reference.aspose.com/email/java/)
- [Télécharger Aspose.Email](https://releases.aspose.com/email/java/)
- [Acheter une licence](https://purchase.aspose.com/buy)
- [Version d'essai gratuite](https://releases.aspose.com/email/java/)
- [Demander une licence temporaire](https://purchase.aspose.com/temporary-license/)
- [Forum de support Aspose](https://forum.aspose.com/c/email/10)

---

**Dernière mise à jour :** 2025-12-20  
**Testé avec :** Aspose.Email for Java 25.4 (JDK 16)  
**Auteur :** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
