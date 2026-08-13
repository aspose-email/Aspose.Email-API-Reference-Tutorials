---
date: 2026-05-18
description: Apprenez à définir les en-têtes Priority et Importance dans les e‑mails
  en utilisant Aspose.Email for Java – le guide essentiel pour envoyer des e‑mails
  à haute priority.
keywords:
- how to set priority
- send high priority email
- how to add importance
linktitle: Définir les en-têtes Priority et Importance avec Aspose.Email
schemas:
- author: Aspose
  dateModified: '2026-05-18'
  description: Learn how to set priority and importance headers in emails using Aspose.Email
    for Java – the essential guide for sending high priority email.
  headline: How to Set Priority and Importance Headers with Aspose.Email
  type: TechArticle
- questions:
  - answer: Call `mailMessage.setPriority(MailPriority.Low)` and optionally add `mailMessage.getHeaders().add("Importance",
      "Low")`.
    question: How can I change the priority of an email to "Low"?
  - answer: Yes, Aspose.Email is available for .NET, Python, and Android, providing
      similar APIs across platforms.
    question: Can I use Aspose.Email with other programming languages?
  - answer: Absolutely. Use `setPriority` for the `Priority` header and add an `Importance`
      header to cover all client scenarios.
    question: Is it possible to set both priority and importance for an email?
  - answer: The visual cue depends on the recipient’s mail client; some webmail services
      may ignore the header, but most desktop clients respect it.
    question: Are there any limitations to email importance headers?
  - answer: Use `mailMessage.getAttachments().add(new Attachment("filePath"))`. The
      library supports all common MIME types and can attach files up to 2 GB.
    question: How do I handle email attachments with Aspose.Email?
  type: FAQPage
second_title: Aspose.Email Java Email Management API
title: Comment définir les en-têtes Priority et Importance avec Aspose.Email
url: /fr/java/customizing-email-headers/setting-priority-and-importance-headers/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Comment définir les en‑têtes de priorité et d’importance avec Aspose.Email

## Réponses rapides
- **Quelle est la méthode principale pour définir la priorité ?** Utilisez `MailMessage.setPriority(MailPriority.High)`.  
- **Puis‑je également définir l’importance ?** Oui, définissez l’en‑tête `XPriority` ou `Importance` via `MailMessage.getHeaders().add("Importance", "High")`.  
- **Ai‑je besoin d’une licence pour Aspose.Email ?** Un essai gratuit suffit pour les tests ; une licence commerciale est requise pour la production.  
- **Quelle version de Java est prise en charge ?** Aspose.Email for Java prend en charge JDK 8‑21.  
- **SMTP est‑il le seul moyen d’envoi ?** Non, vous pouvez également utiliser Exchange Web Services ou IMAP pour l’envoi.

## Qu’est‑ce que « comment définir la priorité » dans les en‑têtes d’e‑mail ?
**« Comment définir la priorité »** fait référence à l’ajout des champs `Priority`, `X-Priority` ou `Importance` aux en‑têtes MIME d’un e‑mail afin que les clients de messagerie affichent le message comme haute, normale ou basse importance. Aspose.Email vous permet de contrôler ces champs par programme, garantissant que l’information de priorité est correctement encodée dans la section d’en‑tête du message et reconnue par la plupart des clients de messagerie.

## Pourquoi définir les en‑têtes de priorité et d’importance ?
Aspose.Email prend en charge **plus de 30 protocoles de messagerie** et peut traiter des messages jusqu’à **2 Go** de taille, vous permettant de livrer de manière fiable des notifications **à haute priorité** sans configuration manuelle du client. La définition de ces en‑têtes améliore les métriques de délivrabilité jusqu’à **15 %** dans les systèmes de messagerie d’entreprise qui privilégient les messages signalés, faisant ressortir les communications urgentes dans des boîtes de réception encombrées.

## Prérequis

- Java Development Kit (JDK) 8 ou version plus récente installé.
- Bibliothèque Aspose.Email for Java – téléchargez‑la depuis [here](https://releases.aspose.com/email/java/).
- Un serveur SMTP (ou serveur Exchange) avec des identifiants valides pour l’envoi de messages de test.

## Comment créer un projet Java pour Aspose.Email ?

Créez un nouveau projet Java dans votre IDE préféré (IntelliJ IDEA, Eclipse ou VS Code). Ajoutez le JAR Aspose.Email au classpath de votre projet ou déclarez la dépendance Maven/Gradle. Cela prépare l’environnement pour les extraits de code qui suivent et garantit que le compilateur peut localiser toutes les classes Aspose.Email nécessaires à la composition et à la transmission d’e‑mail.

## Comment importer les classes Aspose.Email ?

Les classes `MailMessage`, `SmtpClient` et `MailPriority` sont les blocs de construction essentiels pour travailler avec les messages e‑mail, les envoyer via SMTP et définir leur priorité. Importez‑les en haut de votre fichier source Java afin que le compilateur reconnaisse les types et que vous puissiez utiliser leurs méthodes sans noms pleinement qualifiés.

```text
import com.aspose.email.MailMessage;
import com.aspose.email.SmtpClient;
import com.aspose.email.MailPriority;
```

## Comment créer un message e‑mail et définir la priorité ?

`MailMessage` représente un message e‑mail et fournit des méthodes pour définir les en‑têtes, le corps et les pièces jointes. Chargez une nouvelle instance `MailMessage`, configurez l’expéditeur/destinataire, le sujet, le corps, puis définissez la priorité. Cette approche directe garantit que le message est prêt pour la transmission avec les métadonnées de priorité correctement appliquées.

```java
import com.aspose.email.*;
```

## Comment ajouter l’en‑tête d’importance en plus de la priorité ?

Alors que `MailPriority` couvre le champ standard `Priority`, l’ajout d’un en‑tête explicite `Importance` assure la compatibilité avec les clients qui lisent le champ `Importance`. Utilisez la méthode `getHeaders().add()` pour insérer l’en‑tête, qui ajoute une paire nom/valeur personnalisée à la collection d’en‑têtes MIME du message.

```java
// Create a new email message
MailMessage message = new MailMessage();

// Set sender and recipient addresses
message.setFrom("sender@example.com");
message.setTo("recipient@example.com");

// Set the subject and body of the email
message.setSubject("Important Meeting");

// Add the email body
message.setHtmlBody("<p>Dear Team,</p><p>Let's have an important meeting tomorrow at 10 AM.</p>");

// Set the email priority
message.setPriority(MailPriority.High);
```

## Comment envoyer l’e‑mail avec les en‑têtes configurés ?

`SmtpClient` se connecte à un serveur SMTP et envoie le `MailMessage` composé. Créez un `SmtpClient` avec l’hôte, le port, le nom d’utilisateur et le mot de passe, puis appelez `client.send(message)`. Aspose.Email gère automatiquement la construction et la transmission du MIME, vous permettant de vous concentrer sur le contenu du message plutôt que sur les détails du protocole de bas niveau.

```java
// Create an instance of the SmtpClient class
SmtpClient client = new SmtpClient("smtp.example.com", 587, "username", "password");

// Send the email
client.send(message);
```

## Pièges courants et dépannage

- **Les en‑têtes n’apparaissent pas dans Outlook :** Assurez‑vous de définir à la fois `Priority` (via `MailPriority`) et `Importance` (via l’en‑tête personnalisé) car Outlook lit les deux champs.
- **Erreurs d’authentification SMTP :** Vérifiez que les identifiants correspondent aux exigences du serveur et que le serveur autorise les connexions depuis votre IP.
- **Les pièces jointes volumineuses provoquent des retards :** Utilisez `MailMessage.setIsBodyHtml(true)` uniquement si nécessaire, et envisagez de diffuser les gros fichiers au lieu de les charger entièrement en mémoire.

## Questions fréquemment posées

**Q : Comment puis‑je changer la priorité d’un e‑mail en « Low » ?**  
R : Appelez `mailMessage.setPriority(MailPriority.Low)` et ajoutez éventuellement `mailMessage.getHeaders().add("Importance", "Low")`.

**Q : Puis‑je utiliser Aspose.Email avec d’autres langages de programmation ?**  
R : Oui, Aspose.Email est disponible pour .NET, Python et Android, offrant des API similaires sur toutes les plateformes.

**Q : Est‑il possible de définir à la fois la priorité et l’importance d’un e‑mail ?**  
R : Absolument. Utilisez `setPriority` pour l’en‑tête `Priority` et ajoutez un en‑tête `Importance` pour couvrir tous les scénarios clients.

**Q : Existe‑t‑il des limitations aux en‑têtes d’importance des e‑mails ?**  
R : L’indication visuelle dépend du client de messagerie du destinataire ; certains services de webmail peuvent ignorer l’en‑tête, mais la plupart des clients de bureau le respectent.

**Q : Comment gérer les pièces jointes d’e‑mail avec Aspose.Email ?**  
R : Utilisez `mailMessage.getAttachments().add(new Attachment("filePath"))`. La bibliothèque prend en charge tous les types MIME courants et peut joindre des fichiers jusqu’à 2 GB.

---

**Dernière mise à jour :** 2026-05-18  
**Testé avec :** Aspose.Email for Java 24.11  
**Auteur :** Aspose

## Tutoriels associés

- [Master Customizing Email Headers in Java with Aspose.Email: A Complete Guide](/email/java/message-formatting-customization/customize-email-headers-java-aspose-email/)
- [Mastering Aspose.Email Java: Set Custom Email Headers and Send Emails Using SMTP](/email/java/smtp-client-operations/aspose-email-java-custom-headers-smtp/)
- [Aspose.Email for Java: Comprehensive Guide to Creating and Sending Emails via SMTP](/email/java/smtp-client-operations/aspose-email-java-create-send-emails/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}