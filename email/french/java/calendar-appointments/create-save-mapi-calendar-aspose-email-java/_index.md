---
date: '2026-03-20'
description: Apprenez à exporter le PST du calendrier Outlook à l'aide d'Aspose.Email
  pour Java – créez des éléments de calendrier MAPI, définissez la récurrence, ajoutez
  des participants et enregistrez le PST.
keywords:
- Create MAPI Calendar Java
- Aspose.Email Java Calendar
- Java PST File Save
title: Exporter le calendrier Outlook PST avec Aspose.Email – Java
url: /fr/java/calendar-appointments/create-save-mapi-calendar-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Exporter le PST du calendrier Outlook avec Aspose.Email – Java

## Introduction

Vous cherchez à rationaliser l'automatisation des calendriers dans vos applications Java et avez besoin d'**exporter des fichiers PST de calendrier Outlook** ? Avec **Aspose.Email for Java**, vous pouvez **créer des éléments MAPI calendar Java**, définir des modèles de récurrence, ajouter des participants, et **enregistrer le calendrier dans un PST** en quelques lignes de code seulement. Ce tutoriel vous guide à travers l'ensemble du processus — de la configuration de la bibliothèque à la génération d'une entrée de calendrier pleinement fonctionnelle prête à être distribuée.

### Ce que vous apprendrez
- Comment **créer des événements MAPI calendar Java** en utilisant Aspose.Email.  
- Configurer des modèles de récurrence quotidiens, hebdomadaires ou personnalisés.  
- Ajouter des destinataires (organisateurs, participants) à vos invitations de calendrier.  
- Conserver l'élément de calendrier en **enregistrant le calendrier dans un PST** pour la compatibilité Outlook.  
- Comment **automatiser la planification de réunions** avec du code réutilisable.

## Réponses rapides
- **Quelle bibliothèque ?** Aspose.Email for Java  
- **Objectif principal ?** Exporter le PST du calendrier Outlook et **enregistrer le calendrier dans un PST**  
- **Prérequis ?** Java 8+, Maven, licence Aspose.Email  
- **Temps d'implémentation typique ?** 10‑15 minutes pour un événement de base  
- **Puis-je ajouter une récurrence ?** Oui – quotidienne, hebdomadaire, mensuelle, etc.

## Exporter le PST du calendrier Outlook

Dans cette section, nous nous concentrons sur le flux de bout en bout qui vous permet d'**exporter des fichiers PST de calendrier Outlook**. Après avoir créé l'objet MAPI calendar, l'étape finale consiste à le stocker dans un fichier PST que Outlook peut lire directement.

## Pourquoi utiliser Aspose.Email pour l'automatisation des calendriers ?

- **Compatibilité totale avec Outlook** – les éléments générés fonctionnent dans Outlook, OWA et les clients mobiles.  
- **Support complet de la récurrence** – modèles quotidiens, hebdomadaires, mensuels et personnalisés prêts à l'emploi.  
- **Aucune dépendance externe** – bibliothèque pure Java, aucune interop COM requise.  
- **Haute performance** – gestion efficace de gros fichiers PST et d'opérations en masse.  
- **Automatiser la planification de réunions** – intégrez cette logique dans des jobs batch ou des services web pour créer des centaines d'invitations automatiquement.

## Prérequis

Avant de commencer, assurez-vous d'avoir :

### Bibliothèques requises
- **Aspose.Email for Java** : version 25.4 ou ultérieure.

### Exigences de configuration de l'environnement
- Un IDE Java tel qu'IntelliJ IDEA ou Eclipse.  
- Maven installé pour gérer les dépendances.

### Prérequis de connaissances
- Compétences de base en programmation Java.  
- Familiarité avec les concepts orientés objet.

## Configuration d'Aspose.Email pour Java

Ajoutez la dépendance Maven Aspose.Email à votre `pom.xml` :

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Acquisition de licence

Aspose.Email offre un essai gratuit, mais une licence débloque toutes les fonctionnalités :

- **Essai gratuit** : testez sans limitation pendant 30 jours.  
- **Licence temporaire** : demandez via le [site web d'Aspose](https://purchase.aspose.com/temporary-license/) si vous avez besoin de plus de temps.  
- **Achat** : achetez une licence permanente depuis la [page d'achat](https://purchase.aspose.com/buy).

### Initialisation de base

Après avoir ajouté la dépendance, initialisez la bibliothèque avec votre fichier de licence :

```java
com.aspose.email.License license = new com.aspose.email.License();
license.setLicense("path_to_your_license.lic");
```

## Guide d'implémentation

Vous êtes maintenant prêt, créons **MAPI calendar Java** et **enregistrons le calendrier dans un PST**.

### Créer un calendrier MAPI avec récurrence

#### Vue d'ensemble

Nous allons créer un événement de calendrier, appliquer une récurrence quotidienne, ajouter des participants, et enfin le stocker dans un fichier PST.

#### Implémentation étape par étape

1. **Initialiser la date et le modèle de récurrence**  

   Tout d'abord, définissez l'heure de début et définissez une récurrence quotidienne :

   ```java
   import java.util.Date;

   // Add hours to current date to get the start time
   Date startDate = addHours(new Date(), 12);

   MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
   recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
   ```

   *Explication* : `MapiCalendarEventRecurrence` contient les détails de la récurrence ; nous choisissons un modèle quotidien via `MapiCalendarDailyRecurrencePattern`.

2. **Configurer les destinataires**  

   Ajoutez les personnes qui doivent recevoir l'invitation à la réunion :

   ```java
   import com.aspose.email.MapiRecipientCollection;
   import com.aspose.email.MapiRecipientType;

   MapiRecipientCollection recColl = new MapiRecipientCollection();
   recColl.add("recipient@gmail.com", "Attendee Name", MapiRecipientType.MAPI_TO);
   ```

   *Explication* : `MapiRecipientCollection` stocke chaque participant ; `MAPI_TO` les désigne comme destinataires principaux.

3. **Créer l'élément MAPI Calendar**  

   Construisez l'objet calendrier avec tous les détails requis :

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

4. **Enregistrer dans un fichier PST**  

   Enfin, persistez le calendrier en **enregistrant le calendrier dans un PST** :

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
- Assurez-vous que les adresses e‑mail des destinataires sont correctement formatées pour éviter les échecs d'invitation.  
- Fermez le PST (`pst.dispose()`) après les opérations pour libérer les handles de fichier.

## Applications pratiques

Voici des scénarios courants où **créer des MAPI calendar Java** et **enregistrer le calendrier dans un PST** brillent :

1. **Planification automatisée de réunions** – générez des invitations de réunions récurrentes pour les équipes projet sans effort manuel.  
2. **Plateformes de gestion d'événements** – exportez les sessions de conférence en tant qu'éléments de calendrier compatibles Outlook.  
3. **Intégration CRM** – synchronisez les rendez-vous clients d'un système CRM directement dans Outlook via des fichiers PST.

## Considérations de performance

- **Gestion des ressources** : libérez les objets `PersonalStorage` après utilisation pour éviter les verrous de fichiers.  
- **Traitement par lots** : pour de gros volumes, traitez les éléments de calendrier de façon asynchrone ou par lots pour maintenir une faible utilisation de la mémoire.  

## Conclusion

Vous avez maintenant appris comment **exporter le PST du calendrier Outlook** en créant des objets MAPI calendar Java, en configurant la récurrence, en ajoutant des participants, et en **enregistrant le calendrier dans un PST** à l'aide d'Aspose.Email. Cette approche permet à vos applications Java d'automatiser des flux de travail de planification sophistiqués avec une compatibilité Outlook.

Pour explorer davantage, consultez la [documentation officielle](https://reference.aspose.com/email/java/).

## Section FAQ

### Q : Puis-je créer des modèles de récurrence hebdomadaires ?
- **R** : Oui ! Utilisez `MapiCalendarWeeklyRecurrencePattern` pour définir des répétitions hebdomadaires.

### Q : Comment gérer les exceptions dans la récurrence d'événement ?
- **R** : Appelez `setExceptions()` sur l'objet de récurrence pour spécifier les dates qui dévient du modèle.

### Q : Est-il possible de mettre à jour un élément de calendrier existant ?
- **R** : Absolument. Chargez l'élément depuis le PST, modifiez ses propriétés, puis enregistrez-le à nouveau.

### Q : Puis-je chiffrer le fichier PST ?
- **R** : Oui, Aspose.Email vous permet de définir un mot de passe sur `PersonalStorage` lors de la création du PST.

### Q : Que faire si je dois ajouter des pièces jointes à l'événement du calendrier ?
- **R** : Utilisez `calendar.getAttachments().addFileAttachment("path/to/file")` avant d'enregistrer.

## Ressources

- [Documentation Aspose.Email](https://reference.aspose.com/email/java/)
- [Télécharger Aspose.Email pour Java](https://releases.aspose.com/email/java/)
- [Acheter une licence](https://purchase.aspose.com/buy)
- [Version d'essai gratuite](https://releases.aspose.com/email/java/)
- [Demander une licence temporaire](https://purchase.aspose.com/temporary-license/)
- [Forum de support Aspose](https://forum.aspose.com/c/email/10)

---

**Dernière mise à jour :** 2026-03-20  
**Testé avec :** Aspose.Email for Java 25.4 (JDK 16)  
**Auteur :** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}