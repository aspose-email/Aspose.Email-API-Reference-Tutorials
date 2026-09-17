---
date: '2026-09-17'
description: Apprenez à exporter le PST du calendrier Outlook à l'aide d'Aspose.Email
  pour Java – créez des éléments de calendrier MAPI, définissez la récurrence, ajoutez
  des participants et enregistrez le PST.
keywords:
- export outlook calendar pst
- how to export pst
- how to add recurrence
- how to add attendees
- save calendar to pst
lastmod: '2026-09-17'
og_description: Exportez le PST du calendrier Outlook avec Aspose.Email pour Java.
  Apprenez à créer des éléments de calendrier MAPI, à ajouter la récurrence, les participants,
  et à enregistrer le PST en quelques minutes.
og_image_alt: Guide to exporting Outlook calendar PST files with Aspose.Email for
  Java
og_title: Exporter le PST du calendrier Outlook avec Aspose.Email – Java
schemas:
- author: Aspose
  dateModified: '2026-09-17'
  description: Learn how to export Outlook calendar PST using Aspose.Email for Java
    – create MAPI calendar items, set recurrence, add attendees, and save to PST.
  headline: Export Outlook calendar PST with Aspose.Email – Java
  type: TechArticle
- description: Learn how to export Outlook calendar PST using Aspose.Email for Java
    – create MAPI calendar items, set recurrence, add attendees, and save to PST.
  name: Export Outlook calendar PST with Aspose.Email – Java
  steps:
  - name: '**Initialize date and recurrence pattern**'
    text: '**Initialize date and recurrence pattern**'
  - name: '**Set up recipients**'
    text: '**Set up recipients**'
  - name: '**Create the MAPI calendar item**'
    text: '**Create the MAPI calendar item**'
  - name: '**Save to PST file**'
    text: '**Save to PST file**'
  - name: '**Automated meeting scheduling** – Generate recurring meeting invites for
      project teams without manual effort.'
    text: '**Automated meeting scheduling** – Generate recurring meeting invites for
      project teams without manual effort.'
  - name: '**Event management platforms** – Export conference sessions as Outlook‑compatible
      calendar items.'
    text: '**Event management platforms** – Export conference sessions as Outlook‑compatible
      calendar items.'
  - name: '**CRM integration** – Sync customer appointments from a CRM system directly
      into Outlook via PST files.'
    text: '**CRM integration** – Sync customer appointments from a CRM system directly
      into Outlook via PST files.'
  type: HowTo
- questions:
  - answer: Aspose.Email for Java
    question: Which library?
  - answer: Export Outlook calendar PST and **save calendar to PST**
    question: Primary goal?
  - answer: Java 8+, Maven, Aspose.Email license
    question: Prerequisites?
  - answer: 10‑15 minutes for a basic event
    question: Typical implementation time?
  - answer: Yes – daily, weekly, monthly, etc.
    question: Can I add recurrence?
  type: FAQPage
tags:
- export outlook calendar pst
- Aspose.Email
- Java calendar automation
title: Exporter le PST du calendrier Outlook avec Aspose.Email – Java
url: /fr/java/calendar-appointments/create-save-mapi-calendar-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Exporter le calendrier Outlook PST avec Aspose.Email – Java

## Introduction

Vous cherchez à simplifier l'automatisation des calendriers dans vos applications Java et avez besoin d'**exporter des fichiers Outlook calendar PST** ? Avec **Aspose.Email for Java**, vous pouvez **créer des éléments MAPI calendar Java**, définir des modèles de récurrence, ajouter des participants et **enregistrer le calendrier dans un PST** en quelques lignes de code seulement. Ce tutoriel vous guide à travers l'ensemble du processus — de la configuration de la bibliothèque à la génération d'une entrée de calendrier pleinement fonctionnelle prête à être distribuée.

### Ce que vous apprendrez
- Comment **créer des événements MAPI calendar Java** avec Aspose.Email.  
- Configurer des modèles de récurrence quotidiens, hebdomadaires ou personnalisés.  
- Ajouter des destinataires (organisateurs, participants) à vos invitations de calendrier.  
- Persister l'élément de calendrier en **enregistrant le calendrier dans un PST** pour la compatibilité Outlook.  
- Comment **automatiser la planification de réunions** avec du code réutilisable.

## Réponses rapides
- **Quelle bibliothèque ?** Aspose.Email for Java  
- **Objectif principal ?** Exporter le calendrier Outlook PST et **enregistrer le calendrier dans un PST**  
- **Prérequis ?** Java 8+, Maven, licence Aspose.Email  
- **Temps d'implémentation typique ?** 10‑15 minutes pour un événement de base  
- **Puis‑je ajouter une récurrence ?** Oui – quotidien, hebdomadaire, mensuel, etc.

## Exporter le calendrier Outlook PST

Dans cette section, nous nous concentrons sur le flux de bout en bout qui vous permet d'**exporter des fichiers Outlook calendar PST**. Après avoir créé l'objet MAPI calendar, l'étape finale consiste à le stocker dans un fichier PST que Outlook peut lire directement.

## Pourquoi utiliser Aspose.Email pour l'automatisation des calendriers ?

Exportez le calendrier Outlook PST avec Aspose.Email car il offre une méthode fiable côté serveur pour produire des éléments compatibles Outlook sans interopérabilité COM. La bibliothèque prend en charge **plus de 50 formats d'entrée et de sortie**, peut gérer des fichiers PST dépassant 2 Go, et traite des milliers d'entrées de calendrier par minute sur du matériel serveur typique. Son moteur de récurrence intégré couvre les modèles quotidien, hebdomadaire, mensuel et personnalisé, éliminant le besoin de calculs de dates manuels.

## Prérequis

Avant de commencer, assurez‑vous d'avoir :

### Bibliothèques requises
- **Aspose.Email for Java** : version 25.4 ou ultérieure (compatible Java 8‑21).

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

Aspose.Email propose une version d'essai gratuite, mais une licence débloque toutes les fonctionnalités :

- **Essai gratuit** : testez sans limitation pendant 30 jours.  
- **Licence temporaire** : demandez‑la via le [site Web d'Aspose](https://purchase.aspose.com/temporary-license/) si vous avez besoin de plus de temps.  
- **Achat** : achetez une licence permanente depuis la [page d'achat](https://purchase.aspose.com/buy).

### Initialisation de base

Après avoir ajouté la dépendance, initialisez la bibliothèque avec votre fichier de licence :

```java
com.aspose.email.License license = new com.aspose.email.License();
license.setLicense("path_to_your_license.lic");
```

## Guide d'implémentation

Maintenant que tout est configuré, créons **MAPI calendar Java** et **enregistrons le calendrier dans un PST**.

### Créer un MAPI calendar avec récurrence

#### Vue d'ensemble

Nous allons construire un événement de calendrier, appliquer une récurrence quotidienne, ajouter des participants, puis le stocker dans un fichier PST.

#### Implémentation étape par étape

1. **Initialiser la date et le modèle de récurrence**  

   `MapiCalendarEventRecurrence` est la classe qui stocke les détails de récurrence d'un élément de calendrier.  
   `MapiCalendarDailyRecurrencePattern` définit un planning de répétition quotidien simple.  

   Commencez par définir l'heure de début et définir une récurrence quotidienne :

   ```java
   import java.util.Date;

   // Add hours to current date to get the start time
   Date startDate = addHours(new Date(), 12);

   MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
   recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
   ```

2. **Configurer les destinataires**  

   `MapiRecipientCollection` représente la liste des personnes invitées à la réunion.  
   `MAPI_TO` est le drapeau qui marque un destinataire comme participant principal.  

   Ajoutez les personnes qui doivent recevoir l'invitation de réunion :

   ```java
   import com.aspose.email.MapiRecipientCollection;
   import com.aspose.email.MapiRecipientType;

   MapiRecipientCollection recColl = new MapiRecipientCollection();
   recColl.add("recipient@gmail.com", "Attendee Name", MapiRecipientType.MAPI_TO);
   ```

3. **Créer l'élément MAPI calendar**  

   La classe `MapiMessage` (utilisée ici comme objet de calendrier) encapsule toutes les propriétés de l'événement telles que l'organisateur, le sujet, le lieu, les heures de début/fin, la description, la liste des destinataires et la récurrence.  

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

4. **Enregistrer dans un fichier PST**  

   `PersonalStorage` est l'API de haut niveau d'Aspose.Email pour créer et manipuler les fichiers PST.  
   `addMapiMessageItem` insère un message MAPI (y compris les éléments de calendrier) dans un dossier spécifié.  

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

### Conseils de dépannage
- Vérifiez le chemin de la licence ; une licence invalide limitera les fonctionnalités.  
- Assurez‑vous que les adresses e‑mail des destinataires sont correctement formatées pour éviter les échecs d'invitation.  
- Fermez le PST (`pst.dispose()`) après les opérations afin de libérer les poignées de fichier.

## Applications pratiques

Voici des scénarios courants où **créer MAPI calendar Java** et **enregistrer le calendrier dans un PST** sont particulièrement utiles :

1. **Planification automatisée de réunions** – Générer des invitations récurrentes pour les équipes de projet sans effort manuel.  
2. **Plateformes de gestion d'événements** – Exporter les sessions de conférence sous forme d'éléments de calendrier compatibles Outlook.  
3. **Intégration CRM** – Synchroniser les rendez‑vous clients depuis un système CRM directement dans Outlook via des fichiers PST.

## Considérations de performance

- **Gestion des ressources** : libérez les objets `PersonalStorage` après utilisation pour éviter les verrous de fichiers.  
- **Traitement par lots** : pour de gros volumes, traitez les éléments de calendrier de façon asynchrone ou par segments afin de limiter la consommation de mémoire.  
- **Scalabilité** : Aspose.Email peut écrire dans des fichiers PST de plus de 2 Go tout en maintenant la consommation mémoire sous 200 Mo.

## Conclusion

Vous avez maintenant appris comment **exporter le calendrier Outlook PST** en créant des objets MAPI calendar Java, en configurant la récurrence, en ajoutant des participants et en **enregistrant le calendrier dans un PST** à l'aide d'Aspose.Email. Cette approche permet à vos applications Java d'automatiser des flux de travail de planification sophistiqués avec une compatibilité Outlook.

Pour explorer davantage, consultez la [documentation officielle](https://reference.aspose.com/email/java/).

## Section FAQ

### Q : Puis‑je créer des modèles de récurrence hebdomadaires ?
- **R** : Oui ! Utilisez `MapiCalendarWeeklyRecurrencePattern` pour définir des répétitions hebdomadaires.

### Q : Comment gérer les exceptions dans la récurrence d'un événement ?
- **R** : Appelez `setExceptions()` sur l'objet de récurrence pour spécifier les dates qui dévient du modèle.

### Q : Est‑il possible de mettre à jour un élément de calendrier existant ?
- **R** : Absolument. Chargez l'élément depuis le PST, modifiez ses propriétés, puis enregistrez‑le à nouveau.

### Q : Puis‑je chiffrer le fichier PST ?
- **R** : Oui, Aspose.Email vous permet de définir un mot de passe sur `PersonalStorage` lors de la création du PST.

### Q : Que faire si je dois ajouter des pièces jointes à l'événement de calendrier ?
- **R** : Utilisez `calendar.getAttachments().addFileAttachment("path/to/file")` avant l'enregistrement.

## Ressources

- [Documentation Aspose.Email](https://reference.aspose.com/email/java/)
- [Télécharger Aspose.Email for Java](https://releases.aspose.com/email/java/)
- [Acheter une licence](https://purchase.aspose.com/buy)
- [Version d'essai gratuite](https://releases.aspose.com/email/java/)
- [Demander une licence temporaire](https://purchase.aspose.com/temporary-license/)
- [Forum de support Aspose](https://forum.aspose.com/c/email/10)

---

**Dernière mise à jour :** 2026-09-17  
**Testé avec :** Aspose.Email for Java 25.4 (JDK 16)  
**Auteur :** Aspose

## Tutoriels associés

- [Comment créer et gérer des fichiers PST Outlook avec Aspose.Email for Java](/email/java/outlook-pst-ost-operations/aspose-email-java-manage-pst-files/)
- [Comment créer des fichiers PST avec Aspose.Email for Java](/email/java/email-parsing-analysis/aspose-email-java-create-pst-guide/)
- [Comment créer un élément de calendrier Java avec Aspose.Email](/email/java/calendar-appointments/create-save-calendar-items-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}