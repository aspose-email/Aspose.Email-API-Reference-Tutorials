---
date: '2026-02-22'
description: Apprenez comment définir un drapeau de suivi dans Outlook à l'aide d'Aspose.Email
  pour Java, y compris la définition, la lecture et la suppression des drapeaux pour
  les destinataires.
keywords:
- Manage Outlook follow-up flags
- Set follow-up flags in Outlook with Aspose.Email for Java
- Integrate email task management with Aspose.Email
title: Comment définir le drapeau de suivi Outlook à l'aide d'Aspose.Email pour Java
url: /fr/java/calendar-appointments/aspose-email-java-outlook-follow-up-flags/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Comment définir le drapeau de suivi Outlook à l'aide d'Aspose.Email pour Java

## Introduction
Si vous avez déjà eu du mal à suivre les e‑mails importants, vous savez à quel point le **drapeau de suivi Outlook** peut être précieux. Dans ce guide, nous montrerons **comment définir un drapeau de suivi Outlook** de manière programmatique avec Aspose.Email pour Java, et nous couvrirons également comment **définir le drapeau de suivi Outlook pour les destinataires**, ainsi que comment **supprimer un drapeau de suivi Outlook** lorsqu’une tâche est terminée. À la fin, vous pourrez automatiser le suivi des tâches, les rappels et les pistes d’audit directement depuis votre code Java.

**Ce que vous apprendrez**
- Créer et appliquer un drapeau de suivi sur un message Outlook.  
- Définir des drapeaux de suivi pour des destinataires spécifiques.  
- Marquer un drapeau comme terminé et le supprimer ultérieurement.  
- Lire les options du drapeau pour les rapports ou la conformité.  

Préparons l’environnement avant de plonger dans le code.

## Réponses rapides
- **Que signifie « comment définir le suivi » ?** Ajouter un drapeau avec des dates de début, de rappel et d’échéance à un élément Outlook.  
- **Quelle bibliothèque est requise ?** Aspose.Email pour Java (v25.4 ou plus récent).  
- **Ai‑je besoin d’une licence ?** Oui, une licence d’essai ou achetée est requise pour la pleine fonctionnalité.  
- **Puis‑je définir des drapeaux uniquement pour les destinataires ?** Absolument – utilisez `FollowUpManager.setFlagForRecipients`.  
- **Est‑il possible de supprimer un drapeau plus tard ?** Oui, appelez `FollowUpManager.clearFlag`.

## Qu’est‑ce qu’un drapeau de suivi Outlook ?
Un drapeau de suivi Outlook est un marqueur de tâche intégré qui peut associer une date de début, un rappel et une date d’échéance à n’importe quel élément de messagerie. Il transforme un e‑mail ordinaire en un élément d’action suivi, aidant vous et votre équipe à rester au fait du travail en attente.

## Pourquoi utiliser Aspose.Email pour Java ?
Aspose.Email fournit une API pure‑Java qui fonctionne sans Outlook installé, vous permettant de manipuler les fichiers .msg, de définir des drapeaux et de gérer les tâches sur n’importe quelle plateforme—parfait pour **automatiser les tâches Outlook**, les services backend ou l’intégration avec des outils de gestion de projet.

## Prérequis
- **Aspose.Email for Java** version 25.4 ou plus récente (également connu sous le nom de **aspose email java**).  
- **JDK 16+** installé.  
- IDE compatible Maven (IntelliJ IDEA, Eclipse, etc.).  
- Connaissances de base en Java et familiarité avec les concepts d’e‑mail.

## Configuration d’Aspose.Email pour Java
### Configuration Maven
Ajoutez la dépendance suivante à votre `pom.xml` :

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Acquisition de licence
Aspose.Email nécessite une licence pour une utilisation en production :

- **Essai gratuit** – évaluation de 30 jours.  
- **Licence temporaire** – test prolongé.  
- **Licence complète** – abonnement perpétuel.

Initialisez la licence avant toute opération d’e‑mail :

```java
License license = new License();
license.setLicense("path/to/Aspose.Total.Java.lic");
```

## Définir le drapeau de suivi Outlook (Fonctionnalité 1)
### Étape 1 : Créer et initialiser le message
```java
MailMessage mailMsg = new MailMessage();
mailMsg.setSender(new MailAddress("AETest12@gmail.com"));
mailMsg.getTo().addMailAddress(new MailAddress("receiver@gmail.com"));
mailMsg.setBody("This message will test if follow up options can be added to a new mapi message.");
MapiMessage mapi = MapiMessage.fromMailMessage(mailMsg);
```
*Nous créons d’abord un `MailMessage`, définissons l’expéditeur/le destinataire, puis le convertissons en `MapiMessage` pour la manipulation du drapeau.*

### Étape 2 : Définir les dates de suivi (Rappel du drapeau Outlook)
```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 14, 40, 0);
Date dtStartDate = calendar.getTime();
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
calendar.add(Calendar.DATE, 1);
Date dtDueDate = calendar.getTime();
```
*Ici nous définissons les dates de début, de rappel (le **rappel du drapeau Outlook**), et d’échéance en utilisant la classe `Calendar`.*

### Étape 3 : Appliquer les options de suivi
```java
FollowUpOptions options = new FollowUpOptions("Follow Up", dtStartDate, dtDueDate, dtReminderDate);
FollowUpManager.setOptions(mapi, options);
```
*L’objet `FollowUpOptions` contient tous les détails du drapeau, que nous appliquons avec `FollowUpManager.setOptions`.*

### Étape 4 : Enregistrer le message
```java
mapi.save(outputDir + "SetFollowUpflag_out.msg");
```
*Le message est enregistré sous forme de fichier `.msg` avec le drapeau attaché.*

## Comment définir le drapeau pour les destinataires (Fonctionnalité 2)
### Vue d’ensemble
Parfois vous avez besoin que le drapeau apparaisse **uniquement pour les destinataires**. Cet exemple marque d’abord le message comme brouillon, puis ajoute le drapeau.

#### Étape 1 : Marquer comme brouillon
```java
mapi.setMessageFlags(MapiMessageFlags.MSGFLAG_UNSENT);
```
*Marquer le message comme non envoyé garantit qu’Outlook le traite comme un brouillon.*

#### Étape 2 : Définir le drapeau du destinataire
```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
FollowUpManager.setFlagForRecipients(mapi, "Follow up", dtReminderDate);
```
*Le drapeau est maintenant visible uniquement par les destinataires – un scénario classique de **drapeau pour les destinataires**.*

## Comment marquer un drapeau de suivi Outlook comme terminé (Fonctionnalité 3)
### Étape 1 : Charger le message
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
```

### Étape 2 : Marquer comme terminé et enregistrer
```java
FollowUpManager.markAsCompleted(mapi);
mapi.save(outputDir + "MarkedCompleted_out.msg");
```
*Le statut du drapeau passe à « Terminé » et le fichier mis à jour est enregistré.*

## Comment supprimer un drapeau de suivi Outlook (Fonctionnalité 4)
### Étape 1 : Charger et effacer le drapeau
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpManager.clearFlag(mapi);
mapi.save(outputDir + "FollowUpFlagRemoved_out.msg");
```
*Le message est enregistré sans aucun drapeau de suivi.*

## Comment lire les options du drapeau (Fonctionnalité 5)
### Étape 1 : Récupérer les options
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpOptions options = FollowUpManager.getOptions(mapi);
```
*L’objet `options` contient maintenant les dates de début, d’échéance et de rappel, ainsi que le sujet du drapeau – utile lorsque vous devez **lire les options du drapeau** pour les rapports.*

## Applications pratiques
- **Intégration de gestion de tâches :** Synchroniser les e‑mails marqués avec Jira, Trello ou Azure Boards.  
- **Rappels automatisés :** Générer des e‑mails de rappel quotidiens pour les suivis en attente.  
- **Audits de conformité :** Exporter les données de drapeau pour les rapports réglementaires.

## Considérations de performance
- **Calculs de dates :** Calculer les dates une fois par lot plutôt qu’à l’intérieur des boucles.  
- **Gestion des ressources :** Fermer tous les flux ou poignées de fichiers après l’enregistrement des messages.  
- **Utilisation de la mémoire :** Traiter les grandes boîtes aux lettres par morceaux pour éviter la pression sur le tas.

## Problèmes courants et solutions
| Issue | Cause | Fix |
|-------|-------|-----|
| Le drapeau n’apparaît pas dans Outlook | Message enregistré sans les `MessageFlags` appropriés | Assurez‑vous que `setMessageFlags` est défini à `MSGFLAG_UNSENT` avant d’appliquer les drapeaux aux destinataires. |
| Enregistrement génère `AccessDeniedException` | Chemin de fichier incorrect ou permissions d’écriture manquantes | Vérifiez que le répertoire de sortie existe et que l’application dispose des droits d’écriture. |
| Les dates sont décalées d’un jour | Incohérence de fuseau horaire | Utilisez `TimeZone.getTimeZone("GMT")` ou votre fuseau local de façon cohérente. |

## Questions fréquemment posées
**Q : Qu’est‑ce qu’Aspose.Email pour Java ?**  
R : C’est une API pure‑Java qui vous permet de créer, lire et manipuler des fichiers e‑mail (MSG, EML, etc.) sans avoir besoin d’Outlook installé.

**Q : Comment obtenir une licence d’essai gratuite ?**  
R : Visitez le site [Aspose website](https://releases.aspose.com/email/java/) pour télécharger un essai de 30 jours.

**Q : Puis‑je définir plusieurs drapeaux de suivi sur un même message ?**  
R : Outlook ne prend en charge qu’un seul drapeau par message, mais vous pouvez stocker des données de tâche supplémentaires dans des propriétés MAPI personnalisées.

**Q : Mon message n’est pas enregistré après avoir défini un drapeau. Que vérifier ?**  
R : Confirmez que le chemin `outputDir` est valide et que l’application possède les permissions d’écriture sur cet emplacement.

**Q : Comment supprimer les drapeaux de nombreux messages en une fois ?**  
R : Parcourez votre collection de messages et appelez `FollowUpManager.clearFlag` sur chaque `MapiMessage`.

## Ressources
- [Documentation](https://reference.aspose.com/email/java/)
- [Download Aspose.Email for Java](https://releases.aspose.com/email/java/)
- [Aspose.Email Free Trial](https://purchase.aspose.com/purchase/free-trial/aspose-email-java)

---

**Last Updated:** 2026-02-22  
**Tested With:** Aspose.Email for Java 25.4 (jdk16)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}