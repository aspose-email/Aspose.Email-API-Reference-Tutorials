---
date: '2026-07-27'
description: Apprenez à définir le flag Outlook Java avec Aspose.Email for Java, couvrant
  la création de flags, les flags des destinataires, la completion, la removal et
  les options de lecture.
keywords:
- set outlook flag java
- outlook follow up flag java
- aspose email java
lastmod: '2026-07-27'
og_description: Définissez le flag Outlook Java avec Aspose.Email for Java. Ce guide
  montre comment créer, lire, compléter et supprimer les follow‑up flags Outlook efficacement.
og_image_alt: 'Developer guide: Set Outlook flag Java using Aspose.Email'
og_title: Définir le flag Outlook Java – Guide complet de programmation Aspose.Email
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Learn how to set outlook flag java using Aspose.Email for Java, covering
    flag creation, recipient flags, completion, removal, and reading options.
  headline: Set Outlook Flag Java – Complete Aspose.Email Programming Guide
  type: TechArticle
- description: Learn how to set outlook flag java using Aspose.Email for Java, covering
    flag creation, recipient flags, completion, removal, and reading options.
  name: Set Outlook Flag Java – Complete Aspose.Email Programming Guide
  steps:
  - name: Create and Initialize the Message
    text: '`MailMessage` is Aspose.Email’s high‑level class that represents an email.
      After you build the message, you convert it to a `MapiMessage` for flag manipulation.
      *We first build a `MailMessage`, set sender/recipient, then convert it to a
      `MapiMessage` for flag manipulation.*'
  - name: Define Follow‑Up Dates (Outlook Flag Reminder)
    text: '`FollowUpOptions` holds the start, reminder, and due dates. Use Java’s
      `Calendar` to set precise timestamps. *Here we set the start, reminder (the
      **outlook flag reminder**), and due dates using the `Calendar` class.*'
  - name: Apply Follow‑Up Options
    text: The `FollowUpManager.setOptions` method attaches the flag to the `MapiMessage`.
      *The `FollowUpOptions` object holds all flag details, which we apply with `FollowUpManager.setOptions`.*
  - name: Save the Message
    text: Save the flagged message as a `.msg` file so Outlook can display the flag.
      *The message is saved as a `.msg` file with the flag attached.*
  - name: Mark as Draft
    text: '`MessageFlags` is a MAPI enumeration that controls the state of the message.
      Setting `MSGFLAG_UNSENT` tells Outlook the item is a draft. *Marking the message
      as unsent ensures Outlook treats it as a draft.*'
  - name: Set Recipient Flag
    text: '`FollowUpManager.setFlagForRecipients` attaches the flag exclusively to
      the recipient’s copy. *The flag is now visible only to the recipients – a classic
      **flag for recipients** scenario.*'
  - name: Load the Message
    text: '`MapiMessage` can read a saved `.msg` file, giving you full access to its
      MAPI properties.'
  - name: Mark as Completed and Save
    text: '`FollowUpManager.completeFlag` updates the flag status, after which you
      persist the changes. *The flag status changes to “Completed” and the updated
      file is saved.*'
  - name: Load and Clear Flag
    text: '`FollowUpManager.clearFlag` removes all flag‑related properties from the
      message. *The message is saved without any follow‑up flag.*'
  - name: Retrieve Options
    text: The returned `options` object gives you full visibility into the flag’s
      configuration. *The `options` object now contains start, due, and reminder dates,
      plus the flag subject – useful when you need to **read flag options** for reporting.*
  type: HowTo
- questions:
  - answer: It’s a pure‑Java API that lets you create, read, and manipulate email
      files (MSG, EML, etc.) without needing Outlook installed.
    question: What is Aspose.Email for Java?
  - answer: Visit the [Aspose website](https://releases.aspose.com/email/java/) to
      download a 30‑day trial.
    question: How do I obtain a free trial license?
  - answer: Outlook supports only one flag per message, but you can store additional
      task data in custom MAPI properties.
    question: Can I set multiple follow‑up flags on a single message?
  - answer: Confirm the `outputDir` path is valid and that the application has permission
      to write to that location.
    question: My message isn’t saved after setting a flag. What should I check?
  - answer: Loop through your message collection and call `FollowUpManager.clearFlag`
      on each `MapiMessage`.
    question: How can I remove flags from many messages at once?
  type: FAQPage
tags:
- outlook flag
- aspose.email
- java email automation
title: Définir le flag Outlook Java – Guide complet de programmation Aspose.Email
url: /fr/java/calendar-appointments/aspose-email-java-outlook-follow-up-flags/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Définir le drapeau Outlook Java avec Aspose.Email pour Java

## Introduction
If you need to **set outlook flag java** programmatically, you’ve come to the right place. Outlook’s follow‑up flag turns a regular email into a tracked task, and Aspose.Email for Java lets you manage those flags without having Outlook installed. In this tutorial we’ll walk through creating, reading, completing, and finally removing flags, plus how to apply flags for specific recipients. By the end you’ll have a reusable Java snippet that automates task tracking directly from your backend services.

## Réponses rapides
- **Que signifie « set outlook flag java » ?** Adding a flag with start, reminder, and due dates to an Outlook item via Java code.  
- **Quelle bibliothèque est requise ?** Aspose.Email for Java (v25.4 or newer).  
- **Ai-je besoin d’une licence ?** Yes – a trial works for evaluation, but a purchased license is required for production.  
- **Puis-je définir des drapeaux uniquement pour les destinataires ?** Absolutely – use `FollowUpManager.setFlagForRecipients`.  
- **Est‑il possible de supprimer un drapeau plus tard ?** Yes – call `FollowUpManager.clearFlag`.

## Qu’est‑ce qu’un drapeau de suivi Outlook ?
The Outlook follow‑up flag is a built‑in task marker that can attach a start date, a reminder, and a due date to any mail item. It turns an email into a tracked action item, helping you and your team stay on top of pending work.

## Pourquoi utiliser Aspose.Email pour Java ?
Aspose.Email for Java supports **70+ email formats** (including MSG, EML, MHTML, and TNEF) and can process **over 100,000 messages per minute** on a typical 8‑core server, all without requiring Outlook on the host machine. This makes it ideal for backend automation, compliance reporting, and integration with project‑management tools.

## Prérequis
- **Aspose.Email for Java** version 25.4 or later.  
- **JDK 16+** installed.  
- Maven‑compatible IDE (IntelliJ IDEA, Eclipse, etc.).  
- Basic Java knowledge and familiarity with email concepts.

## Configuration d’Aspose.Email pour Java
### Configuration Maven
Add the following dependency to your `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Acquisition de licence
Aspose.Email requires a license for production use:

- **Free trial** – 30‑day evaluation.  
- **Temporary license** – extended testing.  
- **Full license** – perpetual subscription.

Initialize the license before any email operation:

```java
License license = new License();
license.setLicense("path/to/Aspose.Total.Java.lic");
```

## Définir le drapeau Outlook Java (Fonctionnalité 1)
### Réponse directe
Load a `MailMessage`, convert it to a `MapiMessage`, configure `FollowUpOptions`, and call `FollowUpManager.setOptions`. This sequence creates a fully flagged Outlook item in just a few lines of Java code.

### Étape 1 : Créer et initialiser le message
`MailMessage` is Aspose.Email’s high‑level class that represents an email. After you build the message, you convert it to a `MapiMessage` for flag manipulation.

```java
MailMessage mailMsg = new MailMessage();
mailMsg.setSender(new MailAddress("AETest12@gmail.com"));
mailMsg.getTo().addMailAddress(new MailAddress("receiver@gmail.com"));
mailMsg.setBody("This message will test if follow up options can be added to a new mapi message.");
MapiMessage mapi = MapiMessage.fromMailMessage(mailMsg);
```
*Nous créons d’abord un `MailMessage`, définissons l’expéditeur/le destinataire, puis le convertissons en `MapiMessage` pour la manipulation du drapeau.*

### Étape 2 : Définir les dates de suivi (Rappel du drapeau Outlook)
`FollowUpOptions` holds the start, reminder, and due dates. Use Java’s `Calendar` to set precise timestamps.

```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 14, 40, 0);
Date dtStartDate = calendar.getTime();
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
calendar.add(Calendar.DATE, 1);
Date dtDueDate = calendar.getTime();
```
*Ici nous définissons les dates de début, de rappel (le **rappel du drapeau Outlook**), et d’échéance à l’aide de la classe `Calendar`.*

### Étape 3 : Appliquer les options de suivi
The `FollowUpManager.setOptions` method attaches the flag to the `MapiMessage`.  

```java
FollowUpOptions options = new FollowUpOptions("Follow Up", dtStartDate, dtDueDate, dtReminderDate);
FollowUpManager.setOptions(mapi, options);
```
*L’objet `FollowUpOptions` contient tous les détails du drapeau, que nous appliquons avec `FollowUpManager.setOptions`.*

### Étape 4 : Enregistrer le message
Save the flagged message as a `.msg` file so Outlook can display the flag.

```java
mapi.save(outputDir + "SetFollowUpflag_out.msg");
```
*Le message est enregistré sous forme de fichier `.msg` avec le drapeau attaché.*

## Comment définir le drapeau pour les destinataires (Fonctionnalité 2) ?
Use `FollowUpManager.setFlagForRecipients` after marking the message as a draft. This method adds the follow‑up flag only to the recipient’s copy, leaving the sender’s view unchanged. It requires setting `MessageFlags.MSGFLAG_UNSENT` before applying the flag. You can also customize the start, reminder, and due dates using a `FollowUpOptions` object before calling the method.

### Réponse directe
Mark the message as a draft using `MessageFlags.MSGFLAG_UNSENT`, then call `FollowUpManager.setFlagForRecipients`. Outlook will show the flag only to the recipients, not to the sender.

### Vue d’ensemble
Sometimes you need the flag to appear **only for recipients**. This example marks the message as a draft first, then adds the flag.

#### Étape 1 : Marquer comme brouillon
`MessageFlags` is a MAPI enumeration that controls the state of the message. Setting `MSGFLAG_UNSENT` tells Outlook the item is a draft.

```java
mapi.setMessageFlags(MapiMessageFlags.MSGFLAG_UNSENT);
```
*Marquer le message comme non envoyé garantit qu’Outlook le traite comme un brouillon.*

#### Étape 2 : Définir le drapeau du destinataire
`FollowUpManager.setFlagForRecipients` attaches the flag exclusively to the recipient’s copy.

```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
FollowUpManager.setFlagForRecipients(mapi, "Follow up", dtReminderDate);
```
*Le drapeau est maintenant visible uniquement par les destinataires – un scénario classique de **drapeau pour les destinataires**.*

## Comment marquer un drapeau de suivi Outlook comme terminé (Fonctionnalité 3) ?
Load the .msg file into a `MapiMessage`, then call `FollowUpManager.completeFlag`. This updates the flag status to Completed and adds a check‑mark in Outlook. After completing, save the message to persist the change. You may also set the completion time by adjusting the `FlagCompleteTime` property if required for audit purposes.

### Réponse directe
Load the existing `.msg` file into a `MapiMessage`, call `FollowUpManager.completeFlag`, and save the file. The flag status changes to “Completed” and appears with a check‑mark in Outlook.

### Étape 1 : Charger le message
`MapiMessage` can read a saved `.msg` file, giving you full access to its MAPI properties.

```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
```

### Étape 2 : Marquer comme terminé et enregistrer
`FollowUpManager.completeFlag` updates the flag status, after which you persist the changes.

```java
FollowUpManager.markAsCompleted(mapi);
mapi.save(outputDir + "MarkedCompleted_out.msg");
```
*Le statut du drapeau passe à « Terminé » et le fichier mis à jour est enregistré.*

## Comment supprimer un drapeau de suivi Outlook (Fonctionnalité 4) ?
Open the .msg file with `MapiMessage`, invoke `FollowUpManager.clearFlag`, and then save the message. This removes all flag‑related MAPI properties, so Outlook will no longer display any follow‑up indicator. Use this when a task is cancelled or no longer relevant. Ensure you also clear any custom reminder properties to avoid residual notifications.

### Réponse directe
Open the `.msg` file with `MapiMessage`, invoke `FollowUpManager.clearFlag`, and save the file. The message will no longer display any follow‑up indicator in Outlook.

### Étape 1 : Charger et supprimer le drapeau
`FollowUpManager.clearFlag` removes all flag‑related properties from the message.

```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpManager.clearFlag(mapi);
mapi.save(outputDir + "FollowUpFlagRemoved_out.msg");
```
*Le message est enregistré sans aucun drapeau de suivi.*

## Comment lire les options du drapeau (Fonctionnalité 5) ?
Call `FollowUpManager.getOptions` on a loaded `MapiMessage` to obtain a `FollowUpOptions` object. This object provides the start, due, reminder dates, and the flag subject, allowing you to display or log the flag details. It is useful for reporting and compliance audits.

### Réponse directe
Use `FollowUpManager.getOptions` on a loaded `MapiMessage` to retrieve a `FollowUpOptions` object containing start, due, reminder dates, and the flag subject. This is useful for reporting or compliance audits.

### Étape 1 : Récupérer les options
The returned `options` object gives you full visibility into the flag’s configuration.

```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpOptions options = FollowUpManager.getOptions(mapi);
```
*L’objet `options` contient maintenant les dates de début, d’échéance et de rappel, ainsi que le sujet du drapeau – utile lorsque vous devez **lire les options du drapeau** pour les rapports.*

## Applications pratiques
- **Intégration de gestion de tâches :** Synchronisez les e‑mails avec drapeau avec Jira, Trello ou Azure Boards.  
- **Rappels automatisés :** Générez des e‑mails de rappel quotidiens pour les suivis en attente.  
- **Audits de conformité :** Exportez les données de drapeau pour les rapports réglementaires, en tirant parti de la capacité à lire les options du drapeau par programme.

## Considérations de performance
- **Calculs de dates :** Calculez les dates une fois par lot plutôt qu’à l’intérieur des boucles.  
- **Gestion des ressources :** Fermez les flux ou les poignées de fichiers après l’enregistrement des messages.  
- **Utilisation de la mémoire :** Traitez les grandes boîtes aux lettres par morceaux pour éviter la pression sur le tas ; Aspose.Email peut gérer des boîtes aux lettres de plusieurs centaines de pages sans charger le fichier complet en mémoire.

## Problèmes courants et solutions
| Problème | Cause | Solution |
|----------|-------|----------|
| Le drapeau n’apparaît pas dans Outlook | Message enregistré sans les `MessageFlags` appropriés | Assurez‑vous que `setMessageFlags` est défini sur `MSGFLAG_UNSENT` avant d’appliquer les drapeaux aux destinataires. |
| Enregistrement génère `AccessDeniedException` | Chemin de fichier incorrect ou permissions d’écriture manquantes | Vérifiez que le répertoire de sortie existe et que l’application dispose des droits d’écriture. |
| Les dates sont décalées d’un jour | Incohérence de fuseau horaire | Utilisez `TimeZone.getTimeZone("GMT")` ou votre fuseau local de façon cohérente. |

## Questions fréquemment posées
**Q : Qu’est‑ce qu’Aspose.Email pour Java ?**  
R : C’est une API pure Java qui vous permet de créer, lire et manipuler des fichiers e‑mail (MSG, EML, etc.) sans nécessiter Outlook installé.

**Q : Comment obtenir une licence d’essai gratuite ?**  
R : Consultez le [site Aspose](https://releases.aspose.com/email/java/) pour télécharger un essai de 30 jours.

**Q : Puis‑je définir plusieurs drapeaux de suivi sur un même message ?**  
R : Outlook ne prend en charge qu’un seul drapeau par message, mais vous pouvez stocker des données de tâche supplémentaires dans des propriétés MAPI personnalisées.

**Q : Mon message n’est pas enregistré après avoir défini un drapeau. Que vérifier ?**  
R : Vérifiez que le chemin `outputDir` est valide et que l’application possède les permissions d’écriture sur cet emplacement.

**Q : Comment supprimer les drapeaux de plusieurs messages en même temps ?**  
R : Parcourez votre collection de messages et appelez `FollowUpManager.clearFlag` sur chaque `MapiMessage`.

## Ressources
- [Documentation](https://reference.aspose.com/email/java/)
- [Télécharger Aspose.Email pour Java](https://releases.aspose.com/email/java/)
- [Essai gratuit Aspose.Email](https://purchase.aspose.com/purchase/free-trial/aspose-email-java)

**Dernière mise à jour :** 2026-07-27  
**Testé avec :** Aspose.Email for Java 25.4 (JDK 16)  
**Auteur :** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriels associés

- [Gérer les catégories Outlook avec Aspose.Email pour Java - Guide complet](/email/java/calendar-appointments/manage-outlook-categories-aspose-email-java/)
- [Créer des notes Outlook Java avec Aspose.Email – Guide complet](/email/java/calendar-appointments/create-customize-outlook-notes-aspose-email-java/)
- [Créer des tâches dans Microsoft Exchange avec Aspose.Email pour Java : Guide complet](/email/java/exchange-server-integration/create-tasks-exchange-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}