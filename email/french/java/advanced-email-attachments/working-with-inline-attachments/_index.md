---
date: 2026-04-28
description: Apprenez comment intégrer une image dans un e‑mail HTML en utilisant
  Aspose.Email pour Java et envoyer un e‑mail avec l’image intégrée via SMTP.
keywords:
- embed image in html email
- send email with embedded image
- how to embed image java
- create html email java
- send email via smtp java
linktitle: Travailler avec les pièces jointes intégrées dans Aspose.Email
second_title: Aspose.Email Java Email Management API
title: Comment intégrer une image dans un e‑mail HTML avec Aspose.Email pour Java
url: /fr/java/advanced-email-attachments/working-with-inline-attachments/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Comment intégrer une image dans un e‑mail HTML avec Aspose.Email pour Java

Intégrer une image directement dans un e‑mail rend vos messages plus professionnels et garantit que le destinataire voit les graphiques sans avoir à télécharger des fichiers séparés. Dans ce tutoriel, vous apprendrez **comment intégrer une image dans un e‑mail HTML** en utilisant Aspose.Email pour Java, couvrant tout, de la configuration de la bibliothèque à la création d’un e‑mail HTML, l’ajout de ressources en ligne, et enfin l’envoi du message via SMTP.

## Réponses rapides
- **Quelle est la classe principale pour les images en ligne ?** `LinkedResource`
- **Quelle méthode référence l’image dans le HTML ?** Utilisez `cid:yourContentId` dans la balise `<img>`
- **Ai‑je besoin d’une licence pour le développement ?** Un essai gratuit suffit pour les tests ; une licence est requise pour la production
- **Puis‑je envoyer l’e‑mail via n’importe quel serveur SMTP ?** Oui, configurez simplement `SmtpClient` avec les détails de votre serveur
- **Cette approche est‑elle compatible avec tous les principaux clients de messagerie ?** La plupart des clients modernes (Outlook, Gmail, Thunderbird) prennent en charge les images intégrées par CID

## Comment intégrer une image dans un e‑mail HTML en utilisant Aspose.Email pour Java

Lorsque vous **intégrez une image dans un e‑mail HTML**, l’image devient partie du corps MIME, de sorte qu’elle s’affiche immédiatement dans le client du destinataire. Ci‑dessous, nous parcourons le processus complet, d’un simple message HTML à un e‑mail complet avec une image en ligne.

### Qu’est‑ce que les pièces jointes en ligne (images intégrées) ?

Les pièces jointes en ligne—parfois appelées images intégrées ou images CID—sont des fichiers qui résident à l’intérieur du corps MIME d’un e‑mail. Elles sont référencées depuis la partie HTML du message avec un **Content‑ID** (CID). Cette technique vous permet **d’intégrer des images dans les e‑mails** afin qu’elles apparaissent exactement où vous placez la balise `<img>`, sans apparaître comme des pièces jointes téléchargeables séparées.

### Pourquoi utiliser des images intégrées dans vos e‑mails Java ?

- **Aspect professionnel :** Logos, bannières et photos de produits s’affichent instantanément.
- **Meilleur engagement :** Les destinataires sont plus enclins à lire un e‑mail qui semble complet.
- **Pas de clics supplémentaires :** Les utilisateurs n’ont pas besoin de télécharger une pièce jointe pour voir l’image.
- **Cohérence de la marque :** Vos éléments de marque restent intégrés au contenu du message.

### Prérequis

- Bibliothèque Aspose.Email pour Java (téléchargez depuis la documentation officielle [Aspose.Email for Java documentation](https://reference.aspose.com/email/java/))
- Environnement de développement Java 8+
- Accès à un serveur SMTP pour l’envoi du courrier
- Fichier image à intégrer (par ex., `logo.png`)

## Guide étape par étape

### Étape 1 : Créer un message e‑mail HTML de base

Tout d’abord, configurez un simple `MailMessage` avec un corps HTML. Ce sera la toile sur laquelle nous intégrerons l’image plus tard.

```java
// Import necessary classes
import com.aspose.email.MailAddress;
import com.aspose.email.MailMessage;

// Create a new email message
MailMessage message = new MailMessage();
message.setSubject("Hello, World!");
message.setFrom(new MailAddress("sender@example.com"));
message.setTo(new MailAddress("recipient@example.com"));
message.setHtmlBody("<html><body>This is a sample email with inline attachments.</body></html>");
```

### Étape 2 : Ajouter une image en ligne avec `LinkedResource`

Nous intégrons maintenant une image. La classe `LinkedResource` représente la pièce jointe en ligne. Assignez un **Content‑ID** unique et référencez‑le dans le corps HTML avec `cid:`.

```java
import com.aspose.email.LinkedResource;

// Create a LinkedResource for the image
LinkedResource linkedResource = new LinkedResource("path/to/your/image.png");
linkedResource.setContentId("image001"); // Unique ID for the inline image

// Add the LinkedResource to the HTML body
message.getLinkedResources().add(linkedResource);

// Reference the inline image in the HTML body
message.setHtmlBody("<html><body>This is an inline image: <img src='cid:image001'></body></html>");
```

> **Astuce :** Gardez le `ContentId` simple et unique dans le message pour éviter les conflits.

### Étape 3 : Envoyer l’e‑mail via `SmtpClient`

Configurez vos paramètres SMTP et envoyez le message. L’image intégrée voyage avec l’e‑mail, de sorte que le destinataire la voit immédiatement.

```java
import com.aspose.email.SmtpClient;

// Create an instance of SmtpClient
SmtpClient client = new SmtpClient("smtp.example.com", 587, "username", "password");

// Send the email
client.send(message);
```

### Étape 4 : Recevoir et extraire les images en ligne (optionnel)

Si vous devez traiter les messages entrants contenant des images intégrées, vous pouvez charger le fichier `.eml` et accéder à ses `LinkedResources`.

```java
import com.aspose.email.MailMessage;
import com.aspose.email.LinkedResourceCollection;

// Load the received email message
MailMessage receivedMessage = MailMessage.load("path/to/received_email.eml");

// Access the inline attachments
LinkedResourceCollection inlineAttachments = receivedMessage.getLinkedResources();
```

## Problèmes courants & solutions

| Problème | Pourquoi cela se produit | Solution |
|----------|--------------------------|----------|
| **Incohérence de Content‑ID** | La référence `cid:` dans le HTML ne correspond pas au `ContentId` défini sur `LinkedResource`. | Assurez‑vous que les chaînes sont identiques (`image001` vs `cid:image001`). |
| **Fichier introuvable** | Le chemin vers l’image est incorrect ou le fichier est manquant. | Vérifiez le chemin absolu/relatif et assurez‑vous que le fichier existe sur le serveur. |
| **Échec d’authentification SMTP** | Identifiants ou paramètres du serveur incorrects. | Revérifiez l’hôte, le port, le nom d’utilisateur et le mot de passe. Activez TLS/SSL si nécessaire. |
| **Image non affichée dans certains clients** | Certains clients bloquent les ressources externes. | Utilisez des images intégrées par CID (comme montré) plutôt que des URLs externes. |

## Questions fréquemment posées

**Q : Comment télécharger Aspose.Email pour Java ?**  
R : Vous pouvez télécharger Aspose.Email pour Java depuis la [documentation](https://reference.aspose.com/email/java/). Suivez les instructions d’installation pour l’intégrer à votre projet.

**Q : Puis‑je utiliser Aspose.Email pour Java avec d’autres bibliothèques Java ?**  
R : Oui, Aspose.Email s’intègre parfaitement avec d’autres bibliothèques Java, vous permettant de combiner le traitement des e‑mails avec la génération de PDF, l’OCR ou l’accès à une base de données.

**Q : Quels formats de fichiers sont pris en charge pour les pièces jointes en ligne ?**  
R : Les formats d’image courants tels que PNG, JPEG, GIF, ainsi que d’autres types de documents (par ex., SVG) sont pris en charge comme ressources en ligne.

**Q : Comment gérer les pièces jointes en ligne dans les e‑mails HTML ?**  
R : Utilisez la classe `LinkedResource` pour attribuer un `ContentId`, ajoutez‑le à `message.getLinkedResources()`, et référencez‑le dans le corps HTML avec `<img src='cid:yourContentId'>`.

**Q : Aspose.Email pour Java est‑il compatible avec différents serveurs de messagerie ?**  
R : Oui, il fonctionne avec n’importe quel serveur SMTP/IMAP/POP3. Fournissez simplement l’adresse du serveur, le port et les détails d’authentification corrects.

## Conclusion

Vous disposez maintenant d’une recette complète, prête pour la production, pour **intégrer une image dans un e‑mail HTML** avec Aspose.Email pour Java. En créant un `LinkedResource`, en assignant un Content‑ID unique et en le référencant avec `cid:` dans votre corps HTML, vous garantissez que les logos, bannières ou photos de produits apparaissent exactement où vous le souhaitez—sans téléchargements supplémentaires ni liens brisés. Combinez cela avec la robuste classe `SmtpClient` pour envoyer le message via n’importe quel serveur SMTP, et vous êtes prêt à délivrer des e‑mails soignés et cohérents avec votre marque depuis vos applications Java.

---

**Dernière mise à jour :** 2026-04-28  
**Testé avec :** Aspose.Email pour Java 24.12 (dernière version au moment de la rédaction)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}