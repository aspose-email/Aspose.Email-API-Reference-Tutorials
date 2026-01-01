---
date: '2026-01-01'
description: Apprenez à créer un calendrier MAPI en Java et à enregistrer le calendrier
  au format PST à l'aide d'Aspose.Email pour Java. Guide étape par étape avec code,
  récurrence et destinataires.
keywords:
- Create MAPI Calendar Java
- Aspose.Email Java Calendar
- Java PST File Save
title: Comment créer un calendrier MAPI en Java avec Aspose.Email – Enregistrer le
  calendrier au format PST
url: /fr/java/calendar-appointments/create-save-mapi-calendar-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Comment créer un calendrier MAPI java avec Aspose.Email – Enregistrer le calendrier au format PST

## Introduction

Vous cherchez à simplifier l'automatisation des calendriers dans vos applications Java ? Avec **Aspose.Email for Java**, vous pouvez **create MAPI calendar java** des éléments, définir des modèles de récurrence, ajouter des participants, et **save calendar to PST** des fichiers en quelques lignes de code. Ce tutoriel vous guide à travers l'ensemble du processus — de la configuration de la bibliothèque à la génération d'une entrée de calendrier entièrement fonctionnelle prête à être distribuée.

### Ce que vous allez apprendre
- Comment **create MAPI calendar java** des événements en utilisant Aspose.Email.
- Configurer des modèles de récurrence quotidiens, hebdomadaires ou personnalisés.
- Ajouter des destinataires (organisateurs, participants) à vos invitations de calendrier.
- Conserver l'élément de calendrier en **save calendar to PST** pour la compatibilité Outlook.

Plongeons-nous et préparons votre environnement de développement.

## Réponses rapides
- **Which library?** Aspose.Email for Java  
- **Primary goal?** Créer **create MAPI calendar java** et **save calendar to PST**  
- **Prerequisites?** Java 8+, Maven, Aspose.Email license  
- **Typical implementation time?** 10‑15 minutes pour un événement de base  
- **Can I add recurrence?** Oui – quotidien, hebdomadaire, mensuel, etc.

## Qu'est-ce qu'un calendrier MAPI en Java ?
Un objet calendrier MAPI (Messaging Application Programming Interface) représente une réunion ou un rendez‑vous compatible Outlook. En utilisant Aspose.Email, vous pouvez construire ces objets de manière programmatique, permettant une intégration fluide avec Exchange, Outlook ou tout client qui consomme des fichiers PST.

## Pourquoi Aspose.Email pour l'automatisation des calendriers ?
- **Compatibilité totale avec Outlook** – les éléments générés fonctionnent dans Outlook, OWA et les clients mobiles.  
- **Support riche de la récurrence** – quotidien, hebdomadaire, mensuel et modèles personnalisés prêts à l'emploi.  
- **Aucune dépendance externe** – bibliothèque pure Java, aucune interopérabilité COM requise.  
- **Haute performance** – gestion efficace de gros fichiers PST et des opérations en masse.  

## Prérequis

Avant de commencer, assurez-vous d'avoir :

### Bibliothèques requises
- **Aspose.Email for Java**: Version 25.4 ou ultérieure.

### Exigences de configuration de l'environnement
- Un IDE Java tel qu'IntelliJ IDEA ou Eclipse.  
- Maven installé pour gérer les dépendances.

### Prérequis de connaissances
- Compétences de base en programmation Java.  
- Familiarité avec les concepts orientés objet.

## Configuration d'Aspose.Email pour Java

Add the Aspose.Email Maven dependency to your `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Acquisition de licence

Aspose.Email propose un essai gratuit, mais une licence débloque toutes les fonctionnalités :

- **Essai gratuit** : Testez sans limitations pendant 30 jours.  
- **Licence temporaire** : Demandez via le [site web d'Aspose](https://purchase.aspose.com/temporary-license/) si vous avez besoin de plus de temps.  
- **Achat** : Achetez une licence permanente depuis la [page d'achat](https://purchase.aspose.com/buy).

### Initialisation de base

After adding the dependency, initialize the library with your license file:

```java
com.aspose.email.License license = new com.aspose.email.License();
license.setLicense("path_to_your_license.lic");
```

## Guide d'implémentation

Maintenant que tout est configuré, créons **create MAPI calendar java** et **save calendar to PST**.

### Créer un calendrier MAPI avec récurrence

#### Vue d'ensemble

Nous allons créer un événement de calendrier, appliquer une récurrence quotidienne, ajouter des participants, et enfin le stocker dans un fichier PST.

#### Implémentation étape par étape

1. **Initialize Date and Recurrence Pattern**  

   First, define the start time and set a daily recurrence:

   ```java
   import java.util.Date;

   // Add hours to current date to get the start time
   Date startDate = addHours(new Date(), 12);

   MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
   recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
   ```

   *Explication* : `MapiCalendarEventRecurrence` contient les détails de la récurrence ; nous choisissons un modèle quotidien via `MapiCalendarDailyRecurrencePattern`.

2. **Set Up Recipients**  

   Add the people who should receive the meeting invitation:

   ```java
   import com.aspose.email.MapiRecipientCollection;
   import com.aspose.email.MapiRecipientType;

   MapiRecipientCollection recColl = new MapiRecipientCollection();
   recColl.add("recipient@gmail.com", "Attendee Name", MapiRecipientType.MAPI_TO);
   ```

   *Explication* : `MapiRecipientCollection` stocke chaque participant ; `MAPI_TO` les marque comme destinataires principaux.

3. **Create the MAPI Calendar Item**  

   Build the calendar object with all required details:

   ```java
   import com.aspose.email.MapiCalendar;

   MapiCalendar calendar = new MapiCalendar(
       "Organizer Name", 
       "Meeting Subject", 
       "Meeting Location", 
       startDate, 
       addHours(startDate, 1), // End time is one hour after start
       "Event Description",
       recColl,
       recurrence
   );
   ```

   *Explication* : Le constructeur attend l'organisateur, le sujet, le lieu, les heures de début/fin, la description, la liste des destinataires et la récurrence.

4. **Save to PST File**  

   Finally, persist the calendar by **save calendar to PST**:

   ```java
   import com.aspose.email.PersonalStorage;
   import com.aspose.email.FolderInfo;
   import com.aspose.email.StandardIpmFolder;

   PersonalStorage pst = PersonalStorage.create("calendar.pst", 0);
   FolderInfo calendarFolder = pst.createPredefinedFolder("Calendar", StandardIpmFolder.CALendars);

   // Save the MAPI Calendar item
   calendarFolder.addMapiMessageItem(calendar);
   ```

   *Explication* : `PersonalStorage.create` génère un nouveau fichier PST, et `addMapiMessageItem` insère l'entrée du calendrier dans le dossier "Calendar".

### Conseils de dépannage
- Vérifiez le chemin de la licence ; une licence invalide limitera les fonctionnalités.  
- Assurez‑vous que les adresses e‑mail des destinataires sont correctement formatées pour éviter les échecs d'invitation.  
- Fermez le PST (`pst.dispose()`) après les opérations pour libérer les descripteurs de fichiers.

## Applications pratiques

Voici des scénarios courants où **create MAPI calendar java** et **save calendar to PST** sont utiles :

1. **Planification automatisée de réunions** – Générer des invitations récurrentes pour les équipes projet sans effort manuel.  
2. **Plateformes de gestion d'événements** – Exporter les sessions de conférence en tant qu'éléments de calendrier compatibles Outlook.  
3. **Intégration CRM** – Synchroniser les rendez‑vous clients depuis un système CRM directement dans Outlook via des fichiers PST.

## Considérations de performance

- **Gestion des ressources** : Libérez les objets `PersonalStorage` après utilisation pour éviter les verrous de fichiers.  
- **Traitement par lots** : Pour de gros volumes, traitez les éléments de calendrier de façon asynchrone ou par lots pour maintenir une faible consommation de mémoire.  

## Conclusion

Vous avez maintenant appris comment **create MAPI calendar java** des objets, configurer la récurrence, ajouter des participants, et **save calendar to PST** en utilisant Aspose.Email. Cette approche permet à vos applications Java d'automatiser des flux de travail de planification sophistiqués avec une compatibilité Outlook.

For deeper exploration, check the official [documentation](https://reference.aspose.com/email/java/).

## Section FAQ

### Q : Puis-je créer des modèles de récurrence hebdomadaires ?
- **R** : Oui ! Utilisez `MapiCalendarWeeklyRecurrencePattern` pour définir des répétitions hebdomadaires.

### Q : Comment gérer les exceptions dans la récurrence d'un événement ?
- **R** : Appelez `setExceptions()` sur l'objet de récurrence pour spécifier les dates qui dévient du modèle.

### Q : Est‑il possible de mettre à jour un élément de calendrier existant ?
- **R** : Absolument. Chargez l'élément depuis le PST, modifiez ses propriétés, puis enregistrez-le à nouveau.

### Q : Puis‑je chiffrer le fichier PST ?
- **R** : Oui, Aspose.Email vous permet de définir un mot de passe sur `PersonalStorage` lors de la création du PST.

### Q : Que faire si je dois ajouter des pièces jointes à l'événement du calendrier ?
- **R** : Utilisez `calendar.getAttachments().addFileAttachment("path/to/file")` avant l'enregistrement.

## Ressources

- [Aspose.Email Documentation](https://reference.aspose.com/email/java/)
- [Download Aspose.Email for Java](https://releases.aspose.com/email/java/)
- [Purchase a License](https://purchase.aspose.com/buy)
- [Free Trial Version](https://releases.aspose.com/email/java/)
- [Request a Temporary License](https://purchase.aspose.com/temporary-license/)
- [Aspose Support Forum](https://forum.aspose.com/c/email/10)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-01  
**Tested With:** Aspose.Email for Java 25.4 (JDK 16)  
**Author:** Aspose