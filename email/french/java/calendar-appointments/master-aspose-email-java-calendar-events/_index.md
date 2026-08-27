---
date: '2026-08-01'
description: Découvrez comment exporter le calendar au format PST avec Aspose.Email
  for Java, y compris comment ajouter des attendees, définir les start and end dates,
  et gérer les appointments efficacement.
keywords:
- export calendar to pst
- export recurring appointments
- Aspose.Email Java Calendar Events
lastmod: '2026-08-01'
og_description: Exportez le calendar au format PST en utilisant Aspose.Email for Java.
  Découvrez étape par étape comment créer des appointments, ajouter des attendees
  et générer des Outlook PST files.
og_image_alt: 'Developer guide: Export calendar to PST using Aspose.Email for Java'
og_title: Exporter le calendar au format PST – Guide complet avec Aspose.Email for
  Java
schemas:
- author: Aspose
  dateModified: '2026-08-01'
  description: Learn how to export calendar to PST with Aspose.Email for Java, including
    how to add attendees, set start and end dates, and manage appointments efficiently.
  headline: Export calendar to PST with Aspose.Email for Java
  type: TechArticle
- description: Learn how to export calendar to PST with Aspose.Email for Java, including
    how to add attendees, set start and end dates, and manage appointments efficiently.
  name: Export calendar to PST with Aspose.Email for Java
  steps:
  - name: '**Free Trial**: Visit the [Aspose download page](https://releases.aspose.com/email/java/)
      for a temporary license.'
    text: '**Free Trial**: Visit the [Aspose download page](https://releases.aspose.com/email/java/)
      for a temporary license.'
  - name: '**Temporary License**: Apply via the [purchase page](https://purchase.aspose.com/temporary-license/).'
    text: '**Temporary License**: Apply via the [purchase page](https://purchase.aspose.com/temporary-license/).'
  - name: '**Purchase License**: Consider purchasing from [Aspose''s purchase portal](https://purchase.aspose.com/buy)
      for long‑term use.'
    text: '**Purchase License**: Consider purchasing from [Aspose''s purchase portal](https://purchase.aspose.com/buy)
      for long‑term use.'
  - name: '**Business Scheduling** – Automate internal meeting creation and distribution.'
    text: '**Business Scheduling** – Automate internal meeting creation and distribution.'
  - name: '**Event Management** – Track conferences, workshops, and participant lists.'
    text: '**Event Management** – Track conferences, workshops, and participant lists.'
  - name: '**CRM Integration** – Sync appointments with customer relationship tools.'
    text: '**CRM Integration** – Sync appointments with customer relationship tools.'
  - name: '**Project Planning** – Store project milestones as calendar items.'
    text: '**Project Planning** – Store project milestones as calendar items.'
  - name: '**Remote Team Collaboration** – Generate PST files for offline sharing.'
    text: '**Remote Team Collaboration** – Generate PST files for offline sharing.'
  type: HowTo
- questions:
  - answer: Add the Maven dependency shown above, obtain a license, and follow the
      steps in this guide to create and export calendar events.
    question: How do I get started with Aspose.Email for Java?
  - answer: Yes, change the `pstFilePath` variable in `createPSTWithCalendarEvents()`
      to any valid path on your system.
    question: Can I customize the PST file name and location?
  - answer: Absolutely – `MapiCalendar` exposes a `RecurrencePattern` property that
      you can configure before saving.
    question: Is it possible to add recurrence patterns to appointments?
  - answer: Yes, you can export to iCalendar (`.ics`) and other formats using the
      appropriate API methods.
    question: Does Aspose.Email support other calendar formats besides PST?
  - answer: With the Unicode format (`FileFormatVersion.Unicode`), PST files can grow
      up to 2 TB, limited only by available disk space.
    question: What is the maximum size of a PST file I can create?
  type: FAQPage
tags:
- export calendar to pst
- Aspose.Email
- Java calendar appointments
title: Exporter le calendar au format PST avec Aspose.Email for Java
url: /fr/java/calendar-appointments/master-aspose-email-java-calendar-events/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Exporter le calendrier au format PST avec Aspose.Email pour Java

Si vous développez une application Java qui doit partager des données de planification avec Outlook, vous aurez souvent besoin d’**exporter le calendrier au PST**. Dans ce tutoriel, nous passerons en revue tout ce dont vous avez besoin — de la création d’un simple rendez‑vous à l’ajout de participants, puis à l’écriture des événements dans un fichier PST, le tout avec Aspose.Email pour Java. À la fin, vous disposerez d’une solution prête pour la production qui fonctionne sous Windows, Linux et macOS.

## Réponses rapides
- **Quel est l'objectif principal ?** Exporter les événements du calendrier vers un fichier PST.  
- **Quelle bibliothèque est requise ?** Aspose.Email pour Java (v25.4+).  
- **Ai‑je besoin d’une licence ?** Oui, une licence valide Aspose.Email supprime les limites d’évaluation.  
- **Puis‑je ajouter des participants ?** Absolument – utilisez `MapiRecipientCollection`.  
- **Quelle version de Java est prise en charge ?** JDK 16 ou supérieur.

## Qu’est‑ce que **export calendar to pst** ?
`MapiCalendar` est la classe d’Aspose.Email qui modélise un élément de calendrier Outlook, incluant le sujet, le lieu et les détails de timing.

Exporter un calendrier au PST signifie convertir les objets `MapiCalendar` en mémoire en une Microsoft Outlook Personal Storage Table (PST). Le fichier PST généré peut être ouvert directement dans Outlook, partagé avec des collègues ou importé dans tout système qui comprend le format PST, en conservant tous les détails de l’événement tels que les participants, les récurrences et les rappels.

## Pourquoi utiliser Aspose.Email pour Java pour exporter le calendrier au PST ?
Vous pouvez générer un fichier PST entièrement compatible sans installer Outlook. Aspose.Email fournit **un support MAPI complet**, fonctionne sur **tous les principaux systèmes d’exploitation**, et peut gérer **jusqu’à 2 TB** de données au format PST Unicode—suffisant pour des archives à l’échelle de l’entreprise. L’API vous permet également de gérer les participants, les modèles de récurrence, les rappels et les propriétés personnalisées avec quelques appels de méthode, réduisant considérablement l’effort de développement.

## Prérequis
- **Bibliothèques et dépendances** : Aspose.Email pour Java version 25.4 ou ultérieure.  
- **Environnement** : JDK 16 ou supérieur, Maven pour la gestion des dépendances.  
- **Connaissances** : programmation Java de base et familiarité avec Maven.

## Comment configurer Aspose.Email pour Java
Ajoutez la dépendance Aspose.Email à votre `pom.xml` et rafraîchissez votre projet Maven. Cette étape unique rend l’ensemble de l’API MAPI disponible sur votre classpath.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

```xml
<dependency>
  <groupId>com.aspose</groupId>
  <artifactId>aspose-email</artifactId>
  <version>25.4</version>
  <classifier>jdk16</classifier>
</dependency>
```

### Acquisition de licence
Débloquez toutes les fonctionnalités d’Aspose.Email sans les limitations d’évaluation en acquérant une licence :

1. **Essai gratuit** : Visitez la [page de téléchargement Aspose](https://releases.aspose.com/email/java/) pour une licence temporaire.  
2. **Licence temporaire** : Postulez via la [page d'achat](https://purchase.aspose.com/temporary-license/).  
3. **Achat de licence** : Envisagez d'acheter via le [portail d'achat Aspose](https://purchase.aspose.com/buy) pour une utilisation à long terme.

Une fois que vous avez votre licence, initialisez‑la dans votre application pour activer toutes les fonctionnalités.

## Comment **créer un rendez‑vous** (Créer un événement de calendrier Java)
Chargez un objet `MapiCalendar`, définissez ses propriétés principales, puis renvoyez‑le prêt pour un traitement ultérieur. Cette méthode crée une entrée de calendrier avec un sujet, un lieu, une description, ainsi que la **date de début du calendrier Java** / **date de fin du calendrier Java** que vous avez définies.

```java
public static MapiCalendar createAppointment(String subject, String location,
                                             String description, Calendar start, Calendar end) {
    MapiCalendar appointment = new MapiCalendar();
    appointment.setSubject(subject);
    appointment.setLocation(location);
    appointment.setBody(description);
    appointment.setStartDate(start);
    appointment.setEndDate(end);
    return appointment;
}
```

```java
import com.aspose.email.MapiCalendar;
import java.util.Calendar;
import java.util.Date;

public MapiCalendar createAppointment() {
    Calendar cal = Calendar.getInstance();
    
    // Setting the start date
    cal.set(Calendar.YEAR, 2023);
    cal.set(Calendar.MONTH, Calendar.OCTOBER);
    cal.set(Calendar.DAY_OF_MONTH, 1);
    Date startDate = cal.getTime();
    
    // Setting the end date
    cal.set(Calendar.HOUR_OF_DAY, 10);
    Date endDate = cal.getTime();
    
    return new MapiCalendar("Conference Room", "Important Meeting",
        "Discuss project milestones and updates.", startDate, endDate);
}
```

*Explication* : La classe `MapiCalendar` est la représentation Aspose.Email d’un élément de calendrier Outlook. Après avoir défini les champs de base, vous pouvez également configurer la récurrence, les rappels et les catégories avant l’enregistrement.

## Comment **ajouter des participants** (ajouter des participants à une réunion en Java)
Créez une `MapiRecipientCollection`, remplissez‑la avec chaque participant, puis attachez‑la à la réunion. Cela garantit que chaque participant reçoit une invitation appropriée lorsque le PST est ouvert.

`MapiRecipientCollection` est une classe de collection qui contient des objets `MapiRecipient` représentant les participants à la réunion. `MapiRecipient` représente un participant individuel avec des propriétés telles que l’adresse e‑mail et le type de destinataire.

```java
public static MapiRecipientCollection buildAttendees(List<String> emails) {
    MapiRecipientCollection attendees = new MapiRecipientCollection();
    for (String email : emails) {
        MapiRecipient recipient = new MapiRecipient(email, email, MapiRecipientType.MAPI_TO);
        attendees.add(recipient);
    }
    return attendees;
}
```

```java
import com.aspose.email.MapiCalendar;
import com.aspose.email.MapiRecipientCollection;
import com.aspose.email.MapiRecipientType;
import java.util.Date;

public MapiCalendar createMeetingWithAttendees(Date startDate, Date endDate) {
    MapiRecipientCollection attendees = new MapiRecipientCollection();
    
    // Adding primary recipients
    attendees.add("attendee1@example.com", "John Doe", MapiRecipientType.MAPI_TO);
    attendees.add("attendee2@example.com", "Jane Smith", MapiRecipientType.MAPI_TO);
    
    return new MapiCalendar(
        "Main Office Boardroom",
        "Team Meeting",
        "Discuss quarterly goals.",
        startDate,
        endDate,
        "organizer@example.com",
        attendees
    );
}
```

*Explication* : `MapiRecipient` définit un seul participant à la réunion. Définir le type sur `MAPI_TO` marque l’adresse comme participant principal, tandis que `MAPI_CC` ou `MAPI_BCC` peuvent être utilisés pour des participants optionnels.

## Comment **exporter le calendrier au PST** (Créer un PST avec des événements de calendrier)
Créez un fichier PST Unicode, ajoutez un dossier « Calendar », puis insérez les objets `MapiCalendar` précédemment construits. Le PST peut ensuite être ouvert dans Outlook ou distribué aux utilisateurs finaux.

`PersonalStorage` est la classe Aspose.Email utilisée pour créer, ouvrir et manipuler les fichiers PST.

```java
public static void createPSTWithCalendarEvents(String pstFilePath,
                                                List<MapiCalendar> events) throws Exception {
    // Create a new Unicode PST (supports up to 2 TB)
    PersonalStorage pst = PersonalStorage.create(pstFilePath, FileFormatVersion.Unicode);
    // Add the default Calendar folder
    FolderInfo calendarFolder = pst.getRootFolder().addSubFolder("Calendar", 
                                   StandardIpmFolder.Calendar);
    // Insert each event
    for (MapiCalendar event : events) {
        calendarFolder.addMapiMessageItem(event);
    }
}
```

```java
import com.aspose.email.FileFormatVersion;
import com.aspose.email.FolderInfo;
import com.aspose.email.PersonalStorage;
import com.aspose.email.StandardIpmFolder;

public void createPSTWithCalendarEvents() {
    String pstFilePath = "/path/to/output/MapiCalendarToPST_out.pst";
    
    PersonalStorage pst = PersonalStorage.create(pstFilePath, FileFormatVersion.Unicode);
    FolderInfo calendarFolder = pst.createPredefinedFolder("Calendar", StandardIpmFolder.Appointments);

    MapiCalendar appointment = createAppointment();
    calendarFolder.addMapiMessageItem(appointment);
    
    Date startDate = new Date(); // Use actual dates from your event
    Date endDate = new Date();
    MapiCalendar meeting = createMeetingWithAttendees(startDate, endDate);
    calendarFolder.addMapiMessageItem(meeting);
}
```

*Explication* : `PersonalStorage` est le point d’entrée pour la manipulation des PST. En utilisant le format Unicode, vous évitez la limite de 2 Go des anciennes versions de PST et bénéficiez d’un I/O plus rapide sur les archives volumineuses.

## Applications pratiques
1. **Planification d'entreprise** – Automatiser la création et la distribution de réunions internes.  
2. **Gestion d'événements** – Suivre les conférences, ateliers et listes de participants.  
3. **Intégration CRM** – Synchroniser les rendez‑vous avec les outils de gestion de la relation client.  
4. **Planification de projet** – Stocker les jalons du projet sous forme d’éléments de calendrier.  
5. **Collaboration d'équipe à distance** – Générer des fichiers PST pour le partage hors ligne.

## Considérations de performance
- **Libérez les objets** dont vous n’avez plus besoin pour libérer la mémoire rapidement.  
- **Utilisez des collections efficaces** (par ex., `ArrayList` pour les listes de participants) lors du traitement de milliers de participants.  
- **Mettez en cache les événements fréquemment accédés** si vous interrogez le PST de manière répétée, réduisant les I/O disque.

## Problèmes courants et solutions
| Problème | Solution |
|----------|----------|
| **Fichier PST non créé** | Vérifiez les permissions d'écriture sur le répertoire cible et assurez‑vous que le chemin du dossier existe. |
| **Les participants ne reçoivent pas les invitations** | Confirmez que chaque `MapiRecipient` utilise `MapiRecipientType.MAPI_TO` et que l'email de l'organisateur est valide. |
| **Incohérence de date** | Utilisez `Calendar` de manière cohérente pour les dates de début/fin ; évitez de mélanger `java.util.Date` avec d'autres bibliothèques de dates sans conversion. |

## Questions fréquemment posées

**Q : Comment démarrer avec Aspose.Email pour Java ?**  
R : Ajoutez la dépendance Maven indiquée ci‑dessus, obtenez une licence, puis suivez les étapes de ce guide pour créer et exporter des événements de calendrier.

**Q : Puis‑je personnaliser le nom et l’emplacement du fichier PST ?**  
R : Oui, modifiez la variable `pstFilePath` dans `createPSTWithCalendarEvents()` pour tout chemin valide sur votre système.

**Q : Est‑il possible d’ajouter des modèles de récurrence aux rendez‑vous ?**  
R : Absolument – `MapiCalendar` expose une propriété `RecurrencePattern` que vous pouvez configurer avant l’enregistrement.

**Q : Aspose.Email prend‑il en charge d’autres formats de calendrier que le PST ?**  
R : Oui, vous pouvez exporter vers iCalendar (`.ics`) et d’autres formats en utilisant les méthodes API appropriées.

**Q : Quelle est la taille maximale d’un fichier PST que je peux créer ?**  
R : Avec le format Unicode (`FileFormatVersion.Unicode`), les fichiers PST peuvent atteindre jusqu’à 2 TB, limité uniquement par l’espace disque disponible.

---

**Dernière mise à jour :** 2026-08-01  
**Testé avec :** Aspose.Email pour Java 25.4 (jdk16 classifier)  
**Auteur :** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriels associés

- [Maîtriser Aspose.Email pour Java : gérer efficacement les fichiers PST Outlook](/email/java/outlook-pst-ost-operations/aspose-email-java-manage-outlook-pst-files/)
- [Maîtriser la création et l’enregistrement d’éléments de calendrier avec Aspose.Email pour Java](/email/java/calendar-appointments/create-save-calendar-items-aspose-email-java/)
- [Comment lire plusieurs événements de calendrier à partir d’un fichier ICS avec Aspose.Email en Java](/email/java/calendar-appointments/read-multiple-ics-events-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}