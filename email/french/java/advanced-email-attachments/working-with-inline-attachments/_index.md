---
date: 2026-10-23
description: Apprenez à intégrer une image dans un e‑mail HTML en utilisant Aspose.Email
  for Java et à envoyer l’e‑mail avec l’image intégrée via SMTP.
keywords:
- how to embed image
- embed image html email
- html email image cid
- send email embedded image
- send email smtp java
lastmod: 2026-10-23
linktitle: Travailler avec les pièces jointes inline dans Aspose.Email
og_description: Comment intégrer une image dans un e‑mail HTML en utilisant Aspose.Email
  for Java. Suivez le guide étape par étape pour ajouter des images inline, configurer
  SMTP et envoyer des messages soignés.
og_image_alt: Screenshot of Java code embedding an image in an HTML email using Aspose.Email
og_title: Comment intégrer une image dans un e‑mail HTML avec Aspose.Email for Java
schemas:
- author: Aspose
  dateModified: '2026-10-23'
  description: Learn how to embed image in html email using Aspose.Email for Java
    and send email with embedded image via SMTP.
  headline: How to embed image in html email with Aspose.Email for Java
  type: TechArticle
- questions:
  - answer: You can download Aspose.Email for Java from the [Aspose.Email for Java
      documentation](https://reference.aspose.com/email/java/). Follow the installation
      instructions to set it up in your project.
    question: How do I download Aspose.Email for Java?
  - answer: Yes, Aspose.Email integrates smoothly with PDF generation, OCR, or database
      libraries, allowing you to build end‑to‑end communication workflows.
    question: Can I use Aspose.Email for Java with other Java libraries?
  - answer: PNG, JPEG, GIF, BMP, and SVG are all supported. Each can be embedded without
      conversion.
    question: What image formats are supported as inline attachments?
  - answer: Use the `LinkedResource` class to assign a `ContentId`, add it to `message.getLinkedResources()`,
      and reference it in the HTML body with `<img src='cid:yourContentId'>`.
    question: How do I handle inline attachments in HTML emails?
  - answer: Yes, it works with any SMTP, IMAP, or POP3 server. Just provide the correct
      server address, port, and authentication details.
    question: Is Aspose.Email for Java compatible with different email servers?
  type: FAQPage
second_title: Aspose.Email Java Email Management API
tags:
- embed image
- Aspose.Email
- Java email
- inline attachments
title: Comment intégrer une image dans un e‑mail HTML avec Aspose.Email for Java
url: /fr/java/advanced-email-attachments/working-with-inline-attachments/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment intégrer une image dans un e‑mail HTML avec Aspose.Email pour Java

Intégrer une image directement dans un e‑mail rend vos messages plus soignés et garantit que le destinataire voit les graphiques sans avoir à télécharger de fichiers séparés. **Comment intégrer une image** dans un e‑mail HTML est une exigence courante pour le branding, le marketing et les communications transactionnelles. Dans ce tutoriel, vous apprendrez comment intégrer une image dans un e‑mail HTML en utilisant Aspose.Email pour Java, en couvrant tout, de la configuration de la bibliothèque à la création d’un e‑mail HTML, l’ajout de ressources en ligne, et enfin l’envoi du message via SMTP.

## Réponses rapides
- **Quelle classe représente une image en ligne ?** `LinkedResource` stocke les données de l'image et son Content‑ID.  
- **Comment référencer l'image dans le corps HTML ?** Utilisez `<img src="cid:yourContentId">` où `yourContentId` correspond au `ContentId` du `LinkedResource`.  
- **Une licence est‑elle requise pour une utilisation en production ?** Oui – un essai gratuit fonctionne pour les tests, mais une licence achetée supprime les limites d’évaluation.  
- **Tout serveur SMTP peut‑il être utilisé ?** Absolument ; il suffit de configurer `SmtpClient` avec l’hôte, le port et les informations d’identification.  
- **Les principaux clients supportent‑ils les images CID intégrées ?** Plus de 95 % des clients Outlook, Gmail et Thunderbird affichent correctement les images CID.

## Qu’est‑ce que les pièces jointes en ligne (images intégrées) ?

Les pièces jointes en ligne – parfois appelées images intégrées ou images CID – sont des fichiers qui résident à l’intérieur du corps MIME d’un e‑mail. Elles sont référencées depuis la partie HTML du message avec un **Content‑ID** (CID). Cette technique vous permet d’intégrer des images afin qu’elles apparaissent exactement à l’endroit où vous placez la balise `<img>`, sans apparaître comme des pièces jointes téléchargeables séparées.

## Pourquoi utiliser des images intégrées dans vos e‑mails Java ?

Intégrer des images augmente le taux d’ouverture d’environ 30 % en moyenne, car les destinataires voient immédiatement un message complet et brandé. Cela élimine également le problème « image manquante » qui survient lorsque les URL externes sont bloquées. Aspose.Email peut intégrer jusqu’à **50 ressources en ligne par message** tout en maintenant la taille totale du MIME sous **10 Mo** – bien dans les limites de la plupart des serveurs SMTP.

## Prérequis

- Bibliothèque Aspose.Email pour Java (téléchargez depuis la [documentation Aspose.Email pour Java](https://reference.aspose.com/email/java/))
- Environnement de développement Java 8+
- Accès à un serveur SMTP pour l’envoi du courrier
- Fichier image que vous souhaitez intégrer (par ex., `logo.png`)

## Comment intégrer une image dans un e‑mail HTML avec Aspose.Email pour Java

Voici un flux de travail complet, prêt pour la production. Chaque étape est expliquée en termes simples afin que vous puissiez l’adapter à votre propre projet.

### Quelle est la classe principale pour créer un message e‑mail ?

`MailMessage` est l’objet de haut niveau d’Aspose.Email qui représente un seul e‑mail, incluant le sujet, l’expéditeur, les destinataires et le contenu du corps. Toutes les opérations telles que l’ajout de HTML, de pièces jointes ou de ressources en ligne passent par cette classe.

### Quelle est la classe principale pour les images en ligne ?

`LinkedResource` représente une pièce jointe en ligne telle qu’une image, fournissant les données, le type MIME et un Content‑ID. Elle contient les données binaires, le type MIME et un Content‑ID unique que le corps HTML peut référencer. Vous pouvez définir la propriété `ContentId`, spécifier le type média, et ajouter la ressource à la collection de ressources liées du `MailMessage`, garantissant que l’image est envoyée avec le corps MIME.

### Comment intégrer l’image ?

Chargez le fichier image dans un `LinkedResource`, attribuez‑lui un Content‑ID unique (par exemple, `image001`), et ajoutez la ressource à la collection de ressources liées du `MailMessage`. Référencez‑la ensuite dans le corps HTML avec `<img src="cid:image001">`. Ce modèle en une ligne assure que l’image est transmise dans le corps MIME et affichée automatiquement par le client.

### Comment envoyer l’e‑mail via SMTP ?

`SmtpClient` est la classe qui se connecte à un serveur SMTP et envoie des objets `MailMessage`. Configurez un `SmtpClient` avec l’hôte, le port, le nom d’utilisateur et le mot de passe. Appelez `client.send(message)` et la bibliothèque se charge de l’encodage des parties MIME, y compris l’image en ligne. Le message complet, incluant l’image intégrée, est envoyé en un seul aller‑retour réseau.

### Option : Comment recevoir et extraire les images en ligne d’un message entrant ?

Si vous devez traiter le courrier entrant, chargez le fichier `.eml` dans un `MailMessage`, puis parcourez `message.getLinkedResources()` pour récupérer chaque `LinkedResource`. Ceci est utile pour l’archivage ou l’analyse antivirus du contenu intégré. Vous pouvez également enregistrer chaque ressource sur disque ou la stocker dans une base de données pour une analyse ultérieure.

## Problèmes courants & comment les résoudre

| Problème | Pourquoi cela se produit | Solution |
|----------|--------------------------|----------|
| **Incohérence de Content‑ID** | La référence `cid:` dans le HTML ne correspond pas au `ContentId` défini sur le `LinkedResource`. | Assurez‑vous que les chaînes sont identiques (`image001` vs `cid:image001`). |
| **Fichier non trouvé** | Le chemin de l’image est incorrect ou le fichier est absent sur le serveur. | Vérifiez le chemin absolu/relatif et que le fichier existe. |
| **Échec d’authentification SMTP** | Identifiants ou paramètres du serveur incorrects. | Revérifiez l’hôte, le port, le nom d’utilisateur et le mot de passe. Activez TLS/SSL si nécessaire. |
| **Image non affichée dans certains clients** | Certains clients bloquent les ressources externes. | Utilisez des images CID intégrées (comme montré) plutôt que des URL externes. |
| **Taille du message dépasse la limite du serveur** | L’intégration d’images volumineuses peut pousser la taille MIME au‑delà de 10 Mo. | Redimensionnez ou compressez les images avant l’intégration ; Aspose.Email prend en charge le redimensionnement automatique des images. |

## Questions fréquemment posées

**Q : Comment télécharger Aspose.Email pour Java ?**  
R : Vous pouvez télécharger Aspose.Email pour Java depuis la [documentation Aspose.Email pour Java](https://reference.aspose.com/email/java/). Suivez les instructions d’installation pour l’intégrer à votre projet.

**Q : Puis‑je utiliser Aspose.Email pour Java avec d’autres bibliothèques Java ?**  
R : Oui, Aspose.Email s’intègre facilement avec des bibliothèques de génération PDF, OCR ou bases de données, vous permettant de créer des flux de travail de communication de bout en bout.

**Q : Quels formats d’image sont pris en charge comme pièces jointes en ligne ?**  
R : PNG, JPEG, GIF, BMP et SVG sont tous pris en charge. Chacun peut être intégré sans conversion.

**Q : Comment gérer les pièces jointes en ligne dans les e‑mails HTML ?**  
R : Utilisez la classe `LinkedResource` pour attribuer un `ContentId`, ajoutez‑la à `message.getLinkedResources()`, et référencez‑la dans le corps HTML avec `<img src='cid:yourContentId'>`.

**Q : Aspose.Email pour Java est‑il compatible avec différents serveurs de messagerie ?**  
R : Oui, il fonctionne avec n’importe quel serveur SMTP, IMAP ou POP3. Il suffit de fournir l’adresse du serveur, le port et les détails d’authentification corrects.

## Conclusion

Vous disposez maintenant d’une recette complète, prête pour la production, pour **comment intégrer une image** dans un e‑mail HTML avec Aspose.Email pour Java. En créant un `LinkedResource`, en attribuant un Content‑ID unique et en le référencant avec `cid:` dans votre corps HTML, vous garantissez que les logos, bannières ou photos de produit apparaissent exactement où vous le souhaitez—sans téléchargements supplémentaires ni liens brisés. Combinez cela avec la classe robuste `SmtpClient` pour envoyer le message via n’importe quel serveur SMTP, et vous êtes prêt à délivrer des e‑mails soignés et cohérents avec votre marque depuis vos applications Java.

---

**Dernière mise à jour :** 2026-10-23  
**Testé avec :** Aspose.Email pour Java 24.12 (dernière version au moment de la rédaction)  
**Auteur :** Aspose  









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

```java
import com.aspose.email.SmtpClient;

// Create an instance of SmtpClient
SmtpClient client = new SmtpClient("smtp.example.com", 587, "username", "password");

// Send the email
client.send(message);
```

```java
import com.aspose.email.MailMessage;
import com.aspose.email.LinkedResourceCollection;

// Load the received email message
MailMessage receivedMessage = MailMessage.load("path/to/received_email.eml");

// Access the inline attachments
LinkedResourceCollection inlineAttachments = receivedMessage.getLinkedResources();
```

## Tutoriels associés

- [Extraire les pièces jointes en ligne des fichiers Msg Java Aspose Email](/email/java/attachments-handling/extract-inline-attachments-msg-files-java-aspose-email/)
- [Comment envoyer un e‑mail Java avec pièces jointes en utilisant Aspose.Email](/email/java/advanced-email-attachments/using-aspose-email-for-document-attachments/)
- [Comment envoyer des e‑mails avec Aspose.Email en Java : guide complet des opérations du client SMTP](/email/java/smtp-client-operations/send-emails-aspose-email-java-tutorial/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}