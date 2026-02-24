---
date: '2026-02-24'
description: Apprenez à exporter le calendrier au format PST avec Aspose.Email pour
  Java, y compris comment ajouter des participants, définir les dates de début et
  de fin, et gérer les rendez‑vous efficacement.
keywords:
- Aspose.Email Java Calendar Events
- Create Calendar Events in Java
- Manage Calendar Appointments with Java
- export calendar to pst
title: Exporter le calendrier vers PST avec Aspose.Email pour Java
url: /fr/java/calendar-appointments/master-aspose-email-java-calendar-events/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Exporter le calendrier au format PST avec Aspose.Email pour Java

Si vous développez une application Java qui doit partager des données de planification avec Outlook, vous aurez souvent besoin d'**exporter le calendrier au format PST**. Dans ce tutoriel, nous passerons en revue tout ce dont vous avez besoin — de la création d'un rendez‑vous simple à l'ajout de participants, puis à l'écriture des événements dans un fichier PST, le tout avec Aspose.Email pour Java.

## Réponses rapides
- **Quel est l'objectif principal ?** Exporter les événements du calendrier vers un fichier PST.  
- **Quelle bibliothèque est requise ?** Aspose.Email pour Java (v25.4+).  
- **Ai‑je besoin d'une licence ?** Oui, une licence valide d'Aspose.Email supprime les limites d'évaluation.  
- **Puis‑je ajouter des participants ?** Absolument – utilisez `MapiRecipientCollection`.  
- **Quelle version de Java est prise en charge ?** JDK 16 ou supérieur.

## Qu'est-ce que **export calendar to pst** ?
Exporter un calendrier au format PST signifie convertir des objets `MapiCalendar` en mémoire en une Microsoft Outlook Personal Storage Table (PST). Le fichier résultant peut être ouvert directement dans Outlook, partagé avec des collègues, ou importé dans tout système qui comprend le format PST.

## Pourquoi utiliser Aspose.Email pour Java pour exporter le calendrier au format PST ?
- **Full MAPI support** – créer, modifier et enregistrer des rendez‑vous sans nécessiter l'installation d'Outlook.  
- **Cross‑platform** – fonctionne sur Windows, Linux et macOS.  
- **Rich API** – gérer les participants, les récurrences, les rappels, etc.  
- **Performance‑optimized** – gérer de gros volumes d'événements avec une faible empreinte mémoire.

## Prérequis
- **Libraries & Dependencies** : Aspose.Email pour Java version 25.4 ou ultérieure.  
- **Environment** : JDK 16 ou supérieur, Maven pour la gestion des dépendances.  
- **Knowledge** : Programmation Java de base et familiarité avec Maven.

## Comment configurer Aspose.Email pour Java
Ajoutez la dépendance Aspose.Email à votre `pom.xml` :

```xml
<dependency>
  <groupId>com.aspose</groupId>
  <artifactId>aspose-email</artifactId>
  <version>25.4</version>
  <classifier>jdk16</classifier>
</dependency>
```

### Acquisition de licence
Débloquez toutes les fonctionnalités d'Aspose.Email sans les limitations d'évaluation en obtenant une licence :

1. **Free Trial** : Visitez la [page de téléchargement d'Aspose](https://releases.aspose.com/email/java/) pour une licence temporaire.  
2. **Temporary License** : Postulez via la [page d'achat](https://purchase.aspose.com/temporary-license/).  
3. **Purchase License** : Envisagez d'acheter via le [portail d'achat d'Aspose](https://purchase.aspose.com/buy) pour une utilisation à long terme.

Une fois votre licence obtenue, initialisez‑la dans votre application pour activer toutes les fonctionnalités.

## Comment **créer un rendez‑vous** (Create Calendar Event Java)

### Étape 1 : Définir les dates de début et de fin (java calendar start date / java calendar end date)
La méthode suivante montre comment définir les dates de début et de fin d'un rendez‑vous et retourner un objet `MapiCalendar` :

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

*Explication* : Ce fragment crée un `MapiCalendar` avec un emplacement, un sujet, une description spécifiques, ainsi que les **java calendar start date** / **java calendar end date** que vous avez définis.

## Comment **ajouter des participants** (java add meeting attendees)

### Étape 2 : Construire la liste des participants
Utilisez `MapiRecipientCollection` pour spécifier qui doit recevoir l'invitation à la réunion :

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

*Explication* : Ce code crée une réunion, définit l'organisateur, et attache la liste **java add meeting attendees** afin que chacun reçoive une invitation appropriée.

## Comment **exporter le calendrier au format PST** (Create PST with calendar events)

### Étape 3 : Créer un fichier PST et ajouter les événements
La méthode ci‑dessous montre comment créer un fichier PST Unicode et stocker à la fois le rendez‑vous simple et la réunion avec participants :

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

*Explication* : Ce fragment **exporte le calendrier au format PST** en créant un conteneur PST, en ajoutant un dossier « Calendar » prédéfini, et en insérant les objets `MapiCalendar` précédemment construits.

## Applications pratiques
1. **Business Scheduling** – Automatiser la création et la distribution de réunions internes.  
2. **Event Management** – Suivre les conférences, ateliers et listes de participants.  
3. **CRM Integration** – Synchroniser les rendez‑vous avec les outils de gestion de la relation client.  
4. **Project Planning** – Stocker les jalons de projet sous forme d'éléments de calendrier.  
5. **Remote Team Collaboration** – Générer des fichiers PST pour le partage hors ligne.

## Considérations de performance
- **Dispose objects** que vous n'utilisez plus pour libérer la mémoire.  
- **Choose efficient collections** pour les grandes listes de participants.  
- **Cache frequently accessed events** si vous interrogez le PST de façon répétée.

## Problèmes courants et solutions
| Problème | Solution |
|----------|----------|
| **Fichier PST non créé** | Vérifiez les permissions d'écriture sur le répertoire cible et assurez‑vous que le chemin du dossier existe. |
| **Participants ne reçoivent pas les invitations** | Confirmez que chaque `MapiRecipient` utilise `MapiRecipientType.MAPI_TO` et que l'email de l'organisateur est valide. |
| **Incohérence de date** | Utilisez `Calendar` de façon cohérente pour les dates de début/fin ; évitez de mélanger `java.util.Date` avec d'autres bibliothèques de dates sans conversion. |

## Questions fréquemment posées

**Q : Comment démarrer avec Aspose.Email pour Java ?**  
R : Ajoutez la dépendance Maven indiquée ci‑dessus, obtenez une licence, et suivez les étapes de ce guide pour créer et exporter des événements de calendrier.

**Q : Puis‑je personnaliser le nom et l'emplacement du fichier PST ?**  
R : Oui, modifiez la variable `pstFilePath` dans `createPSTWithCalendarEvents()` pour tout chemin valide sur votre système.

**Q : Est‑il possible d'ajouter des modèles de récurrence aux rendez‑vous ?**  
R : Absolument – `MapiCalendar` expose des propriétés de récurrence comme `RecurrencePattern` que vous pouvez configurer avant l'enregistrement.

**Q : Aspose.Email prend‑il en charge d'autres formats de calendrier en plus du PST ?**  
R : Oui, vous pouvez exporter vers iCalendar (`.ics`) et d'autres formats en utilisant les méthodes API appropriées.

**Q : Quelle est la taille maximale d'un fichier PST que je peux créer ?**  
R : Avec le format Unicode (`FileFormatVersion.Unicode`), les fichiers PST peuvent atteindre jusqu'à 2 TB, limité uniquement par l'espace disque disponible.

---

**Dernière mise à jour :** 2026-02-24  
**Testé avec :** Aspose.Email pour Java 25.4 (classificateur jdk16)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}