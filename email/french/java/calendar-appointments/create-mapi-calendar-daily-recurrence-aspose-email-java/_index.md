---
date: '2026-09-17'
description: Apprenez à créer un calendrier Outlook en Java avec une récurrence quotidienne
  et des exceptions, et à enregistrer le calendrier au format PST en utilisant Aspose.Email
  for Java.
keywords:
- create outlook calendar
- outlook calendar daily recurrence
- java calendar exceptions
- Aspose.Email Java
- MAPI PST generation
lastmod: '2026-09-17'
og_description: Créer un calendrier Outlook en Java avec Aspose.Email. Apprenez la
  récurrence quotidienne, la gestion des exceptions et l’enregistrement au format
  PST dans un guide étape par étape.
og_image_alt: Code example creating Outlook calendar with recurrence and PST export
  using Aspose.Email for Java
og_title: Créer un calendrier Outlook en Java avec une récurrence quotidienne et des
  exceptions
schemas:
- author: Aspose
  dateModified: '2026-09-17'
  description: Learn how to create outlook calendar java with daily recurrence and
    exceptions, and save calendar to PST using Aspose.Email for Java.
  headline: Create outlook calendar java with daily recurrence and exceptions
  type: TechArticle
- questions:
  - answer: Yes, you can set the `StartTimeZone` and `EndTimeZone` properties on `MapiCalendar`.
    question: Does the library support time‑zone aware appointments?
  - answer: Use the `DeletedInstanceDates` collection on the recurrence pattern to
      mark specific dates as removed.
    question: Can I programmatically delete a single occurrence from a recurring series?
  - answer: PST files follow the Unicode format limits (up to 2 GB by default), but
      you can configure larger sizes via `PersonalStorage` settings.
    question: Are there limits on the size of a PST file created with Aspose.Email?
  - answer: Create `MapiRecipient` objects, set their `RecipientType` to `MapiRecipientType.MAPI_TO`,
      and add them to the `Recipients` collection of the `MapiMessage`.
    question: How do I add attendees to a meeting request?
  - answer: Yes, Aspose.Email also provides `MapiTask` with similar recurrence capabilities.
    question: Is there support for recurring tasks (not just appointments)?
  type: FAQPage
tags:
- outlook calendar
- Aspose.Email
- Java scheduling
- PST file
title: Créer un calendrier Outlook en Java avec une récurrence quotidienne et des
  exceptions
url: /fr/java/calendar-appointments/create-mapi-calendar-daily-recurrence-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un calendrier Outlook Java avec récurrence quotidienne et exceptions

Gérer efficacement les événements récurrents peut être difficile, surtout lorsque vous avez besoin d'un **outlook calendar java** qui prend en charge les modèles de récurrence quotidienne et les exceptions occasionnelles. Dans ce tutoriel, vous apprendrez comment créer des objets Outlook calendar Java, configurer la récurrence quotidienne, ajouter des instances d'exception, et enfin **save calendar to PST** en utilisant Aspose.Email for Java. À la fin, vous disposerez d'un extrait de code réutilisable que vous pourrez intégrer à tout service de planification basé sur Java.

## Réponses rapides
- **Quelle bibliothèque ?** Aspose.Email for Java  
- **Tâche principale ?** Créer un calendrier Outlook Java avec récurrence quotidienne et exceptions  
- **JDK requis ?** Java 16 ou supérieur  
- **Puis-je joindre des fichiers aux exceptions ?** Oui, en utilisant `MapiCalendarExceptionInfo`  
- **Où le calendrier est‑il stocké ?** Dans un fichier PST via `PersonalStorage`  

## Qu’est‑ce qu’un Outlook calendar java ?
Un objet Outlook calendar Java est une représentation programmatique d'un rendez‑vous Outlook, construit sur la spécification MAPI (Messaging Application Programming Interface), qui comprend des propriétés telles que le sujet, le lieu, les heures de début/fin, les règles de récurrence, les participants et les pièces jointes. Cet objet peut être manipulé, sérialisé et stocké dans des fichiers PST sans nécessiter Outlook.

## Pourquoi utiliser Aspose.Email for Java ?
Aspose.Email for Java vous permet de travailler avec des objets MAPI sans installer Outlook. La bibliothèque prend en charge **plus de 50 propriétés MAPI**, peut générer des fichiers PST Unicode jusqu’à **2 Go** en moins de **2 secondes** pour des données de rendez‑vous typiques, et s’exécute sur toute plateforme supportant Java 16+. Cette approche pure‑Java permet la création de calendriers côté serveur, des séries de réunions automatisées, et un contrôle total sur la logique de récurrence.

## Prérequis
Avant de commencer, assurez‑vous d’avoir la configuration suivante :
- **Bibliothèque Aspose.Email** : Version 25.4 (ou ultérieure) – disponible via Maven ou téléchargement direct.  
- **Kit de développement Java (JDK)** : JDK 16 ou plus récent.  
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

### Acquisition de licence
Pour utiliser Aspose.Email, vous aurez besoin d’une licence :
- **Essai gratuit** – explorez toutes les fonctionnalités sans frais.  
- **Licence temporaire** – demandez une évaluation prolongée.  
- **Licence complète** – achetez pour les déploiements en production.  

## Configuration d’Aspose.Email pour Java
Tout d’abord, configurez votre environnement :
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

## Guide de mise en œuvre

### Création d’un outlook calendar java avec récurrence quotidienne et exceptions

#### Vue d’ensemble
Cette fonctionnalité vous permet d’automatiser les rendez‑vous récurrents tout en pouvant ignorer ou modifier des instances spécifiques.

#### Implémentation étape par étape

**1. Configurer la date de début de l’événement**  
Déterminez quand la série doit commencer :
```java
Date startDate = addHours(newDate(2018, 7, 19), 12);
```

**2. Créer l’objet calendrier MAPI**  
La classe `MapiCalendar` est l’objet de niveau supérieur qui représente un seul élément de calendrier en mémoire. Fournissez le lieu, le sujet et la description :
```java
MapiCalendar calendar = new MapiCalendar("location1", "summary1", "description1", startDate, addHours(startDate, 1));
```

**3. Définir un modèle de récurrence quotidienne**  
La classe `MapiCalendarRecurrencePattern` stocke la règle qui répète le rendez‑vous chaque jour. Configurez l’événement pour qu’il se répète quotidiennement :
```java
MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
MapiCalendarRecurrencePattern pattern = recurrence.getRecurrencePattern();

pattern.setPatternType(MapiCalendarRecurrencePatternType.Day);
pattern.setPeriod(1); // Daily
pattern.setEndType(MapiCalendarRecurrenceEndType.NeverEnd);
```

**4. Ajouter une exception à la récurrence**  
`MapiCalendarExceptionInfo` décrit une occurrence unique qui dévie du modèle—soit exclue, soit modifiée. Spécifiez une date qui doit être exclue (ou modifiée) :
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

#### Vue d’ensemble
Vous pouvez joindre des documents de support (par ex., des ordres du jour) à n’importe quelle instance d’exception.

**1. Créer et attacher un fichier**
```java
MapiCalendarExceptionInfo exception = new MapiCalendarExceptionInfo();
exception.getAttachments().add("file.txt", "hello, world!".getBytes());
```

## Enregistrement d’un outlook calendar java au PST (save calendar to pst)

#### Vue d’ensemble
Enregistrez le calendrier dans un fichier PST afin qu’Outlook ou d’autres clients puissent le lire.

**1. Créer et enregistrer le calendrier au PST**  
La classe `PersonalStorage` fournit des méthodes pour créer un nouveau fichier PST et y ajouter des éléments MAPI.
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
- **Planification d’entreprise** – automatiser les séries de réunions, en sautant automatiquement les jours fériés.  
- **Gestion de projet** – suivre les jalons récurrents avec des décalages de dates occasionnels.  
- **Planification d’événements** – gérer des conférences sur plusieurs jours où certaines sessions sont annulées ou reprogrammées.  

### Possibilités d’intégration
Combinez Aspose.Email avec des plateformes CRM, des API de gestion de tâches ou des moteurs de workflow personnalisés pour piloter une automatisation de bout en bout.

## Considérations de performance
- **Libérer les ressources** – appelez toujours `dispose()` sur `PersonalStorage` pour libérer les poignées de fichiers.  
- **Utilisation des flux** – privilégiez `ByteArrayOutputStream` ou les flux de fichiers pour éviter de charger des PST entiers en mémoire.  
- **Opérations asynchrones** – pour la génération massive de calendriers, exécutez la logique de création sur un thread d’arrière‑plan afin de garder l’interface réactive.  

## Conclusion
En suivant ce guide, vous savez maintenant comment **create outlook calendar java** des objets avec récurrence quotidienne, ajouter des exceptions, joindre des fichiers, et **save calendar to PST**. Ces capacités vous permettent de créer des fonctionnalités de planification robustes sans jamais toucher directement à Outlook.

### Prochaines étapes
- Expérimentez les modèles de récurrence hebdomadaires ou mensuels.  
- Explorez des propriétés MAPI supplémentaires telles que les participants, les rappels et les catégories.  
- Examinez la documentation complète de l’API Aspose.Email pour des scénarios plus avancés.  

## Questions fréquemment posées

**Q : La bibliothèque prend‑elle en charge les rendez‑vous sensibles au fuseau horaire ?**  
R : Oui, vous pouvez définir les propriétés `StartTimeZone` et `EndTimeZone` sur `MapiCalendar`.  

**Q : Puis‑je supprimer programmétiquement une occurrence unique d’une série récurrente ?**  
R : Utilisez la collection `DeletedInstanceDates` du modèle de récurrence pour marquer des dates spécifiques comme supprimées.  

**Q : Existe‑t‑il des limites de taille pour un fichier PST créé avec Aspose.Email ?**  
R : Les fichiers PST respectent les limites du format Unicode (jusqu’à 2 Go par défaut), mais vous pouvez configurer des tailles plus grandes via les paramètres de `PersonalStorage`.  

**Q : Comment ajouter des participants à une demande de réunion ?**  
R : Créez des objets `MapiRecipient`, définissez leur `RecipientType` à `MapiRecipientType.MAPI_TO`, et ajoutez‑les à la collection `Recipients` du `MapiMessage`.  

**Q : Existe‑t‑il une prise en charge des tâches récurrentes (pas seulement les rendez‑vous) ?**  
R : Oui, Aspose.Email fournit également `MapiTask` avec des capacités de récurrence similaires.  

**Q : Puis‑je utiliser ce guide dans le cadre d’une série de tutoriels Aspose.Email Java ?**  
R : Absolument – les étapes présentées ici constituent une partie essentielle de tout tutoriel Aspose.Email Java traitant de la création de calendriers.  

## Ressources
- [Documentation Aspose.Email pour Java](https://reference.aspose.com/email/java/)
- [Télécharger Aspose.Email](https://releases.aspose.com/email/java/)
- [Acheter une licence](https://purchase.aspose.com/buy)
- [Version d’essai gratuite](https://releases.aspose.com/email/java/)
- [Demander une licence temporaire](https://purchase.aspose.com/temporary-license/)
- [Forum de support Aspose](https://forum.aspose.com/c/email/10)

---

**Dernière mise à jour :** 2026-09-17  
**Testé avec :** Aspose.Email for Java 25.4 (JDK 16)  
**Auteur :** Aspose

## Tutoriels associés

- [Exporter le PST du calendrier Outlook avec Aspose.Email – Java](/email/java/calendar-appointments/create-save-mapi-calendar-aspose-email-java/)
- [Comment créer un élément de calendrier Java en utilisant Aspose.Email](/email/java/calendar-appointments/create-save-calendar-items-aspose-email-java/)
- [Créer une invitation de partage de calendrier avec Aspose.Email pour Java](/email/java/calendar-appointments/create-send-calendar-invitations-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}