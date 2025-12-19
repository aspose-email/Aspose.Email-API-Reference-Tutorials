---
date: '2025-12-19'
description: Apprenez à définir des drapeaux de suivi dans Outlook en utilisant Aspose.Email
  pour Java, y compris comment définir le drapeau de suivi Outlook et comment supprimer
  le drapeau de suivi Outlook efficacement.
keywords:
- Manage Outlook follow-up flags
- Set follow-up flags in Outlook with Aspose.Email for Java
- Integrate email task management with Aspose.Email
title: Comment définir des indicateurs de suivi dans Outlook avec Aspose.Email pour
  Java
url: /fr/java/calendar-appointments/aspose-email-java-outlook-follow-up-flags/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Comment définir des indicateurs de suivi dans Outlook avec Aspose.Email pour Java

## Introduction
Si vous avez déjà eu du mal à suivre les e‑mails importants, vous savez à quel point les indicateurs de suivi d’Outlook peuvent être précieux. Dans ce guide, nous montrerons **comment définir des indicateurs de suivi** de manière programmatique avec Aspose.Email pour Java, et nous couvrirons également comment **définir un indicateur de suivi Outlook** pour les destinataires, ainsi que comment **supprimer un indicateur de suivi Outlook** lorsqu’une tâche est terminée. À la fin, vous pourrez automatiser le suivi des tâches, les rappels et les traces d’audit directement depuis votre code Java.

**Ce que vous apprendrez**
- Créer et appliquer un indicateur de suivi sur un message Outlook.  
- Définir des indicateurs de suivi pour des destinataires spécifiques.  
- Marquer un indicateur comme terminé et le supprimer ultérieurement.  
- Lire les options d’indicateur pour le reporting ou la conformité.  

Préparons l’environnement avant de plonger dans le code.

## Réponses rapides
- **Que signifie « comment définir un suivi » ?** Ajouter un indicateur avec des dates de début, de rappel et d’échéance à un élément Outlook.  
- **Quelle bibliothèque est requise ?** Aspose.Email pour Java (v25.4 ou plus récent).  
- **Ai‑je besoin d’une licence ?** Oui, une licence d’essai ou achetée est requise pour la fonctionnalité complète.  
- **Puis‑je définir des indicateurs uniquement pour les destinataires ?** Absolument – utilisez `FollowUpManager.setFlagForRecipients`.  
- **Est‑il possible de supprimer un indicateur plus tard ?** Oui, appelez `FollowUpManager.clearFlag`.

## Qu’est‑ce qu’un indicateur de suivi ?
Un indicateur de suivi est une fonctionnalité d’Outlook qui marque un e‑mail comme une tâche, en y joignant éventuellement des dates de début, de rappel et d’échéance. Il aide vous et votre équipe à rester au fait des actions en attente.

## Pourquoi utiliser Aspose.Email pour Java ?
Aspose.Email fournit une API pure‑Java qui fonctionne sans Outlook installé, vous permettant de manipuler des fichiers .msg, de définir des indicateurs et de gérer des tâches sur n’importe quelle plateforme—parfait pour les services back‑end, les flux de travail automatisés ou l’intégration avec des outils de gestion de projet.

## Prérequis
- **Aspose.Email pour Java** version 25.4 ou ultérieure.  
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

## Guide d’implémentation

### Comment définir des indicateurs de suivi (Fonction 1)
#### Vue d’ensemble
Cette section vous guide dans la création d’un message Outlook, la définition des dates de début/rappel/échéance, et l’application d’un indicateur de suivi.

#### Étape 1 : Créer et initialiser le message
```java
MailMessage mailMsg = new MailMessage();
mailMsg.setSender(new MailAddress("AETest12@gmail.com"));
mailMsg.getTo().addMailAddress(new MailAddress("receiver@gmail.com"));
mailMsg.setBody("This message will test if follow up options can be added to a new mapi message.");
MapiMessage mapi = MapiMessage.fromMailMessage(mailMsg);
```
*Nous créons d’abord un `MailMessage`, définissons l’expéditeur/le destinataire, puis le convertissons en `MapiMessage` pour la manipulation de l’indicateur.*

#### Étape 2 : Définir les dates de suivi
```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 14, 40, 0);
Date dtStartDate = calendar.getTime();
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
calendar.add(Calendar.DATE, 1);
Date dtDueDate = calendar.getTime();
```
*Ici nous définissons les dates de début, de rappel et d’échéance à l’aide de la classe `Calendar`.*

#### Étape 3 : Appliquer les options de suivi
```java
FollowUpOptions options = new FollowUpOptions("Follow Up", dtStartDate, dtDueDate, dtReminderDate);
FollowUpManager.setOptions(mapi, options);
```
*L’objet `FollowUpOptions` contient tous les détails de l’indicateur, que nous appliquons avec `FollowUpManager.setOptions`.*

#### Étape 4 : Enregistrer le message
```java
mapi.save(outputDir + "SetFollowUpflag_out.msg");
```
*Le message est enregistré en tant que fichier `.msg` avec l’indicateur attaché.*

### Comment définir un indicateur de suivi Outlook pour les destinataires (Fonction 2)
#### Vue d’ensemble
Parfois, vous devez marquer un message uniquement pour les destinataires. Cet exemple marque d’abord le message comme brouillon, puis ajoute l’indicateur.

#### Étape 1 : Marquer comme brouillon
```java
mapi.setMessageFlags(MapiMessageFlags.MSGFLAG_UNSENT);
```
*Marquer le message comme non envoyé garantit qu’Outlook le traite comme un brouillon.*

#### Étape 2 : Définir l’indicateur du destinataire
```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
FollowUpManager.setFlagForRecipients(mapi, "Follow up", dtReminderDate);
```
*L’indicateur est maintenant visible uniquement par les destinataires.*

### Comment marquer un indicateur de suivi Outlook comme terminé (Fonction 3)
#### Vue d’ensemble
Lorsque une tâche est terminée, vous pouvez marquer programmétiquement l’indicateur comme terminé.

#### Étape 1 : Charger le message
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
```

#### Étape 2 : Marquer comme terminé et enregistrer
```java
FollowUpManager.markAsCompleted(mapi);
mapi.save(outputDir + "MarkedCompleted_out.msg");
```
*Le statut de l’indicateur passe à « Terminé » et le fichier mis à jour est enregistré.*

### Comment supprimer un indicateur de suivi Outlook (Fonction 4)
#### Vue d’ensemble
Si un indicateur n’est plus nécessaire, vous pouvez le supprimer entièrement.

#### Étape 1 : Charger et effacer l’indicateur
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpManager.clearFlag(mapi);
mapi.save(outputDir + "FollowUpFlagRemoved_out.msg");
```
*Le message est enregistré sans aucun indicateur de suivi.*

### Comment lire les options d’indicateur de suivi (Fonction 5)
#### Vue d’ensemble
Pour l’audit ou le reporting, vous pouvez lire les paramètres d’indicateur existants.

#### Étape 1 : Récupérer les options
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpOptions options = FollowUpManager.getOptions(mapi);
```
*L’objet `options` contient maintenant les dates de début, d’échéance et de rappel, ainsi que le sujet de l’indicateur.*

## Applications pratiques
- **Intégration de gestion de tâches :** Synchroniser les e‑mails marqués avec Jira, Trello ou Azure Boards.  
- **Rappels automatisés :** Générer des e‑mails de rappel quotidiens pour les suivis en attente.  
- **Audits de conformité :** Exporter les données d’indicateur pour les rapports réglementaires.

## Considérations de performance
- **Calculs de dates :** Calculer les dates une fois par lot plutôt qu’à l’intérieur des boucles.  
- **Gestion des ressources :** Fermer tous les flux ou handles de fichiers après l’enregistrement des messages.  
- **Utilisation de la mémoire :** Traiter les grandes boîtes aux lettres par morceaux pour éviter la pression sur le tas.

## Problèmes courants et solutions
| Problème | Cause | Solution |
|----------|-------|----------|
| L’indicateur n’apparaît pas dans Outlook | Message enregistré sans les `MessageFlags` appropriés | Assurez‑vous que `setMessageFlags` est défini sur `MSGFLAG_UNSENT` avant d’appliquer les indicateurs aux destinataires. |
| Enregistrement génère `AccessDeniedException` | Chemin de fichier incorrect ou permissions d’écriture manquantes | Vérifiez que le répertoire de sortie existe et que l’application dispose des droits d’écriture. |
| Les dates sont décalées d’un jour | Incohérence de fuseau horaire | Utilisez `TimeZone.getTimeZone("GMT")` ou votre fuseau local de manière cohérente. |

## Questions fréquentes
**Q : Qu’est‑ce qu’Aspose.Email pour Java ?**  
R : C’est une API pure Java qui vous permet de créer, lire et manipuler des fichiers e‑mail (MSG, EML, etc.) sans nécessiter l’installation d’Outlook.

**Q : Comment obtenir une licence d’essai gratuite ?**  
R : Visitez le site [Aspose](https://releases.aspose.com/email/java/) pour télécharger un essai de 30 jours.

**Q : Puis‑je définir plusieurs indicateurs de suivi sur un même message ?**  
R : Outlook ne prend en charge qu’un seul indicateur par message, mais vous pouvez stocker des données de tâche supplémentaires dans des propriétés MAPI personnalisées.

**Q : Mon message n’est pas enregistré après avoir défini un indicateur. Que vérifier ?**  
R : Vérifiez que le chemin `outputDir` est valide et que l’application possède les permissions d’écriture sur cet emplacement.

**Q : Comment puis‑je supprimer les indicateurs de nombreux messages en une fois ?**  
R : Parcourez votre collection de messages et appelez `FollowUpManager.clearFlag` sur chaque `MapiMessage`.

## Ressources
- [Documentation](https://reference.aspose.com/email/java/)
- [Télécharger Aspose.Email pour Java](https://releases.aspose.com/email/java/)
- [Essai gratuit Aspose.Email](https://purchase.aspose.com/purchase/free-trial/aspose-email-java)

**Dernière mise à jour :** 2025-12-19  
**Testé avec :** Aspose.Email pour Java 25.4 (jdk16)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}