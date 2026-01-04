---
date: '2026-01-04'
description: Apprenez à créer un calendrier Exchange en Java en utilisant Aspose.Email
  pour Java. Inclut la dépendance Maven, la connexion à Exchange en Java et la gestion
  des rendez‑vous.
keywords:
- Exchange Calendar Management
- Aspose.Email for Java
- Java Exchange Server Integration
title: Créer un calendrier Exchange Java avec Aspose.Email – Guide complet
url: /fr/java/calendar-appointments/mastering-exchange-calendar-management-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Créer un calendrier Exchange Java avec Aspose.Email

## Introduction

Gérer les e‑mails et les calendriers dans un environnement professionnel peut être complexe, surtout lorsque vous devez **créer des programmes exchange calendar java** qui fonctionnent pour plusieurs utilisateurs et fuseaux horaires. Heureusement, **Aspose.Email for Java** simplifie ces tâches en offrant des API robustes pour la gestion des calendriers Exchange Server. Dans ce guide complet, vous apprendrez à vous connecter à un serveur Exchange, à créer des dossiers de calendrier et à gérer les rendez‑vous — le tout avec du code Java clair, étape par étape.

**Ce que vous allez apprendre**
- Comment **se connecter à exchange java** avec Aspose.Email  
- Comment ajouter la **dépendance maven aspose email** à votre projet  
- Créer un nouveau dossier de calendrier et gérer les rendez‑vous  
- Mettre à jour, lister et annuler des rendez‑vous  

Commençons !

## Réponses rapides
- **Quelle est la bibliothèque principale ?** Aspose.Email for Java  
- **Comment ajouter la bibliothèque ?** Utilisez la dépendance Maven indiquée ci‑dessous  
- **Puis‑je créer un dossier de calendrier ?** Oui, avec un seul appel d’API  
- **Ai‑je besoin d’une licence ?** Une version d’essai suffit pour le développement ; une licence complète est requise en production  
- **Est‑ce compatible avec Office 365 ?** Absolument – le même code fonctionne avec Exchange Online  

## Qu’est‑ce que « create exchange calendar java » ?
Créer un calendrier Exchange en Java signifie interagir programme‑ment avec une boîte aux lettres Exchange pour ajouter, modifier ou supprimer des éléments de calendrier. Cette approche est idéale pour l’automatisation de la planification, les outils de gestion de réunions ou la synchronisation de calendriers à l’échelle de l’entreprise.

## Pourquoi utiliser Aspose.Email pour Java ?
- **API complète** – Gère les Exchange Web Services (EWS) sans manipulation SOAP de bas niveau.  
- **Multiplateforme** – Fonctionne sous Windows, Linux et macOS avec n’importe quel runtime JDK 16+.  
- **Aucune dépendance externe** – La bibliothèque regroupe tout ce dont vous avez besoin pour communiquer avec Exchange.  

## Prérequis
- Bibliothèque **Aspose.Email for Java** (version 25.4 ou ultérieure)  
- JDK 16 ou supérieur  
- Accès à un serveur Exchange (Office 365 ou sur site)  
- IDE tel qu’IntelliJ IDEA, Eclipse ou NetBeans  

## Dépendance Maven Aspose Email
Ajoutez le fragment suivant à votre `pom.xml`. Il s’agit de la **dépendance maven aspose email** nécessaire pour récupérer la bibliothèque depuis Maven Central.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Étapes d’obtention de licence
1. **Essai gratuit :** Téléchargez une version d’essai depuis le [site Aspose](https://releases.aspose.com/email/java/) pour tester les fonctionnalités.  
2. **Licence temporaire :** Obtenez une licence temporaire pour un accès complet aux fonctionnalités via [ce lien](https://purchase.aspose.com/temporary-license/).  
3. **Achat :** Si vous êtes satisfait, envisagez d’acheter une licence complète sur la [page d’achat d’Aspose](https://purchase.aspose.com/buy).

## Se connecter à Exchange Java
**Vue d’ensemble :** Cette section montre comment **se connecter à exchange java** en utilisant le client EWS.

### Étape 1 : établir la connexion
```java
import com.aspose.email.EWSClient;
import com.aspose.email.IEWSClient;

public class ConnectToExchangeServer {
    public static void main(String[] args) {
        IEWSClient client = null;
        try {
            // Connect to Exchange Server with provided URL and credentials
            client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "username", "password");
            System.out.println("Connected to Exchange server.");
        } finally {
            if (client != null)
                client.dispose();
        }
    }
}
```
**Explication :** Remplacez `"username"` et `"password"` par vos véritables identifiants. Ce code crée une instance `IEWSClient` que vous réutiliserez pour toutes les opérations de calendrier suivantes.

## Créer un dossier de calendrier
**Vue d’ensemble :** Créez un dossier dédié à l’intérieur du calendrier de la boîte aux lettres pour organiser les rendez‑vous associés.

### Étape 2 : créer un nouveau dossier de calendrier
```java
import com.aspose.email.MailboxInfo;

public class CreateCalendarFolder {
    public static void main(String[] args) {
        IEWSClient client = null;
        try {
            // Connect to Exchange Server (Replace with actual credentials)
            client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "username", "password");

            // Create a new calendar folder named 'new calendar'
            String calendarUri = client.getMailboxInfo().getCalendarUri();
            client.createFolder(calendarUri, "new calendar", null, "IPF.Appointment");
        } finally {
            if (client != null)
                client.dispose();
        }
    }
}
```
**Explication :** Le dossier `"new calendar"` apparaît sous la hiérarchie principale du calendrier, prêt à stocker les rendez‑vous créés ultérieurement.

## Créer un rendez‑vous dans le dossier de calendrier
**Vue d’ensemble :** Ajoutez une réunion ou un événement au dossier de calendrier nouvellement créé.

### Étape 3 : configurer les détails du rendez‑vous
```java
import com.aspose.email.Appointment;
import com.aspose.email.MailAddress;
import java.util.Calendar;
import java.util.Date;
import java.util.UUID;

public class CreateAppointment {
    public static void main(String[] args) {
        IEWSClient client = null;
        try {
            // Connect to Exchange Server (Replace with actual credentials)
            client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "username", "password");

            // Setup appointment details
            Calendar calendar = Calendar.getInstance();
            Date startTime = calendar.getTime();
            calendar.add(Calendar.HOUR, 1);
            Date endTime = calendar.getTime();
            String timeZone = "America/New_York";

            Appointment appointment = new Appointment("Room 121", startTime, endTime,
                    MailAddress.to_MailAddress("email1@aspose.com"),
                    MailAddressCollection.to_MailAddressCollection("email2@aspose.com"));
            appointment.setTimeZone(timeZone);
            appointment.setSummary("EMAILNET-35198 - ".concat(UUID.randomUUID().toString()));
            appointment.setDescription("EMAILNET-35198 Ability to add Java event to Secondary Calendar of Office 365");

            // List subfolders and get the URI for the new calendar folder created earlier
            String newCalendarFolderUri = client.listSubFolders(client.getMailboxInfo().getCalendarUri()).get_Item(0).getUri();

            // Create appointment in the specified calendar folder
            client.createAppointment(appointment, newCalendarFolderUri);
        } finally {
            if (client != null)
                client.dispose();
        }
    }
}
```
**Explication :** Ce code construit un objet `Appointment`, définit son fuseau horaire, ajoute des participants et le stocke dans le dossier de calendrier personnalisé.

## Mettre à jour le rendez‑vous
**Vue d’ensemble :** Modifiez les propriétés d’un rendez‑vous existant, comme le lieu ou le sujet.

### Étape 4 : définir le rendez‑vous existant
```java
import com.aspose.email.Appointment;

public class UpdateAppointment {
    public static void main(String[] args) {
        IEWSClient client = null;
        try {
            // Connect to Exchange Server (Replace with actual credentials)
            client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "username", "password");

            // Setup appointment details for existing appointment
            Appointment appointment = new Appointment();
            appointment.setLocation("Room 122");

            // Specify the URI of the calendar folder where the appointment exists
            String newCalendarFolderUri = "YOUR_DOCUMENT_DIRECTORY";

            // Update the location of the existing appointment
            client.updateAppointment(appointment, newCalendarFolderUri);
        } finally {
            if (client != null)
                client.dispose();
        }
    }
}
```
**Explication :** Remplacez `"YOUR_DOCUMENT_DIRECTORY"` par l’URI réel du dossier contenant le rendez‑vous que vous souhaitez mettre à jour. Cet extrait montre comment changer le champ de localisation.

## Problèmes courants et astuces
- **Erreurs d’authentification :** Vérifiez que le compte possède l’accès EWS et que l’authentification multifacteur est désactivée ou qu’un mot de passe d’application est utilisé.  
- **URI du dossier introuvable :** Utilisez `client.listSubFolders()` pour découvrir l’URI correct du calendrier avant de créer ou mettre à jour des éléments.  
- **Mauvais fuseaux horaires :** Définissez toujours le fuseau horaire sur l’objet `Appointment` afin d’éviter les surprises liées à l’heure d’été.  

## Questions fréquemment posées

**Q : Ai‑je besoin d’une licence pour le développement ?**  
R : Un essai gratuit suffit pour le développement et les tests, mais une licence complète est requise pour les déploiements en production.

**Q : Puis‑je utiliser cela avec Exchange sur site ?**  
R : Oui. Il suffit de changer l’URL EWS pour pointer vers votre serveur sur site.

**Q : Java 8 est‑il pris en charge ?**  
R : La bibliothèque prend en charge JDK 16 et supérieur ; les versions antérieures ne sont pas recommandées pour la dernière version.

**Q : Comment supprimer un rendez‑vous ?**  
R : Utilisez `client.deleteAppointment(appointmentId, calendarFolderUri);` après avoir récupéré l’ID unique du rendez‑vous.

**Q : Et si je dois gérer des réunions récurrentes ?**  
R : Aspose.Email fournit une classe `Recurrence` que vous pouvez attacher à un `Appointment` avant de l’enregistrer.

---

**Dernière mise à jour :** 2026-01-04  
**Testé avec :** Aspose.Email for Java 25.4 (jdk16 classifier)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}