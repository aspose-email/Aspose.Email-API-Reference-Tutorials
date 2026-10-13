---
date: 2026-10-12
description: Découvrez comment intégrer des images dans les e‑mails HTML avec Aspose.Email
  for Java, envoyer des e‑mails HTML avec des images intégrées et réduire la taille
  des pièces jointes d’e‑mail.
keywords:
- reduce email attachment size
- create email with image
- optimize image for email
- send html email java
- embed cid image email
lastmod: 2026-10-12
linktitle: Comment joindre une image à un e‑mail avec Aspsoe.Email
og_description: Réduisez la taille des pièces jointes d’e‑mail et intégrez des images
  dans les e‑mails HTML avec Aspose.Email for Java. Suivez ce guide étape par étape
  pour envoyer des e‑mails HTML riches efficacement.
og_image_alt: 'Developer guide: embed images in HTML email while reducing attachment
  size with Aspose.Email for Java'
og_title: Réduire la taille des pièces jointes d'e‑mail avec Aspose.Email for Java
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: Learn how to embed images in HTML email using Aspose.Email for Java,
    send HTML email with embedded images, and reduce email attachment size.
  headline: Reduce email attachment size with Aspose.Email for Java
  type: TechArticle
- questions:
  - answer: Repeat the attachment and `LinkedResource` steps for each image, assigning
      a unique Content‑ID (e.g., `image2`, `image3`) and referencing them in the HTML.
    question: How can I embed multiple images in a single email?
  - answer: Plain‑text format does not support embedded images. You can only include
      URLs that recipients can click to view the image online.
    question: Can I embed images in plain‑text emails?
  - answer: JPEG, PNG, and GIF are widely supported. Use JPEG for photographs and
      PNG for graphics with transparency.
    question: What image formats are safe for email embedding?
  - answer: Yes—add `width`/`height` attributes to the `<img>` tag, e.g., `<img src='cid:image1'
      width='400' height='300'>`.
    question: Is there a way to control image dimensions in the email?
  - answer: While there’s no strict SMTP limit, most mail providers recommend keeping
      total email size under 5 MB. Optimizing image size helps stay well within this
      limit.
    question: Are there size limits for embedded images?
  type: FAQPage
second_title: Aspose.Email Java Email Management API
tags:
- email attachment size
- Aspose.Email
- Java email API
- embed images email
- HTML email
title: Réduire la taille des pièces jointes d'e‑mail avec Aspose.Email for Java
url: /fr/java/advanced-email-attachments/embedding-images-as-attachments/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Réduire la taille des pièces jointes d'email avec Aspose.Email pour Java

Embedding images directly into an HTML email not only makes the message look polished, it also **reduces email attachment size** because the image is part of the MIME body rather than a separate file. In this tutorial you’ll learn how to create email with image, embed the image using a CID reference, and apply best‑practice tips to **optimize image for email** so the final message stays lightweight. You’ll also see how to send HTML email Java‑style with Aspose.Email and keep the total payload well under typical mailbox limits.

## Réponses rapides
- **Quelle classe crée le message email ?** `MailMessage` – le conteneur principal pour l'objet, les destinataires et le corps.  
- **Quel objet vous permet d'intégrer une image dans le corps HTML ?** `LinkedResource` – il encapsule le flux d'image et attribue un Content‑ID.  
- **Ai-je besoin d'une licence pour une utilisation en production ?** Oui – une licence commerciale Aspose.Email est requise pour supprimer les limites d'évaluation.  
- **Comment réduire la taille de la pièce jointe ?** Optimisez l'image (redimensionnez à ≤600 px, compressez en dessous de 100 KB) avant de l'ajouter.  
- **Puis-je intégrer plusieurs images ?** Absolument – ajoutez un Content‑ID unique pour chaque image et référencez‑les avec les URI `cid:`.

## Qu'est-ce qu'un email HTML avec image intégrée ?
Intégrer une image signifie insérer la photo dans la structure MIME de l'email afin que le destinataire la voie en ligne. L'image est référencée par un **Content‑ID (CID)**, que la balise HTML `<img>` charge directement depuis le corps du message, éliminant les pièces jointes séparées et réduisant la taille globale.

## Pourquoi envoyer un email HTML avec image intégrée ?
Intégrer des images dans le HTML vous permet de créer des newsletters, annonces de produits ou tickets de support plus riches. Les destinataires voient le visuel immédiatement, sans devoir télécharger une pièce jointe, ce qui améliore les taux d'ouverture et l'engagement global. La plupart des clients de messagerie prennent en charge les images CID, et l'intégration évite les étapes de téléchargement supplémentaires, entraînant un rendu plus rapide et une consommation de bande passante moindre.

## Prérequis
- **Aspose.Email for Java** – téléchargez depuis le site officiel : [Aspose.Email Java download](https://releases.aspose.com/email/java/).  
- Accès à un serveur SMTP (Gmail, Outlook ou votre propre relais).  
- Un fichier image (JPEG, PNG ou GIF) que vous souhaitez intégrer.

> **Astuce pro :** *Optimisez la taille de l'image pour l'email* en la redimensionnant à une largeur ≤600 px et en la compressant à ≤100 KB. Cela réduit le temps de chargement et évite de dépasser les limites de taille de boîte aux lettres.

## Création d'un message email
`MailMessage` est l'objet de haut niveau d'Aspose.Email qui représente un seul email. Il contient l'objet, l'expéditeur, les destinataires et le corps (texte brut ou HTML).  

La classe `MailMessage` est le modèle central pour créer et envoyer des messages email avec Aspose.Email pour Java.

```java
// Import necessary libraries
import com.aspose.email.*;

// Create a new email message
MailMessage message = new MailMessage();
```

## Ajouter une image en tant que pièce jointe
`LinkedResource` représente une partie MIME qui peut être intégrée en ligne dans un email.  
Avant l'intégration, vous ajoutez le fichier image à la collection de pièces jointes du message. La pièce jointe devient un flux que `LinkedResource` pourra ensuite référencer.

```java
// Specify the path to the image file
String imagePath = "path/to/your/image.jpg";

// Attach the image to the email
Attachment attachment = new Attachment(imagePath);
message.getAttachments().add(attachment);
```

## Intégrer l'image jointe dans le HTML
`LinkedResource` est utilisé pour lier un flux d'image à un Content‑ID pour un affichage en ligne.  
Pour afficher l'image dans le corps HTML, créez un `LinkedResource` qui pointe vers l'image jointe et définissez son Content‑ID (par ex., `image1`). Ensuite, référencez cet ID dans le HTML en utilisant le schéma d'URI `cid:`.

```java
// Create a LinkedResource for the attached image
LinkedResource linkedImage = new LinkedResource(attachment.getContentStream(), "image/jpeg");
linkedImage.setContentId("image1");

// Create an HTML body with the embedded image
String htmlBody = "<html><body><h1>Check out this image:</h1><img src='cid:image1'></body></html>";
message.setHtmlBody(htmlBody);
message.getLinkedResources().addItem(linkedImage);
```

> **Pourquoi utiliser `LinkedResource` ?** Il indique au client que l'image fait partie du corps du message, ce qui est essentiel pour les scénarios **send html email java** nécessitant des graphiques en ligne.

## Envoi de l'email
`SmtpClient` est la classe qui gère la communication SMTP pour l'envoi des messages.  
`SmtpClient` assure la transmission réelle. Configurez‑le avec l'hôte, le port et les informations d'identification de votre serveur, puis appelez `send` pour expédier le `MailMessage`.  

`SmtpClient` est la classe de transport SMTP d'Aspose.Email qui envoie en toute sécurité le `MailMessage` composé au serveur de messagerie cible.

```java
// Initialize the SmtpClient
SmtpClient client = new SmtpClient("smtp.example.com", 587, "your_username", "your_password");

// Send the email
client.send(message);
```

Lorsque le destinataire ouvre l'email, le corps HTML rend l'image en ligne, offrant une expérience visuelle fluide tout en maintenant la charge globale petite.

## Comment intégrer plusieurs images dans un email
`LinkedResource` représente une partie MIME qui peut être intégrée en ligne dans un email.  
Ajoutez chaque image comme une pièce jointe distincte, créez un `LinkedResource` distinct pour chacune, et attribuez un Content‑ID unique tel que `image2`, `image3`, etc. Référencez‑les dans le HTML avec `src='cid:image2'`. Ce modèle s'adapte aux newsletters contenant des dizaines de graphiques sans gonfler la taille du message.

## Conseils pour réduire la taille des pièces jointes d'email
- **Redimensionner** l'image aux dimensions exactes requises (généralement ≤600 px de largeur).  
- **Compresser** à l'aide d'outils comme ImageMagick ou des compresseurs en ligne pour garder le fichier sous 100 KB.  
- **Choisir le bon format** : JPEG pour les photos, PNG pour les graphiques avec transparence.  
- **Supprimer les métadonnées EXIF** si elles ne sont pas nécessaires.  
- **Utiliser le JPEG progressif** pour un rendu progressif plus rapide dans les clients qui le supportent.

## Problèmes courants et dépannage
| Problème | Cause | Solution |
|----------|-------|----------|
| Image non affichée | Content‑ID incorrect ou `LinkedResource` manquant | Vérifiez que `linkedImage.setContentId("image1")` correspond au `src='cid:image1'` dans le HTML. |
| Taille d'email importante | Image non optimisée (haute résolution) | Redimensionnez/compressez l'image avant de l'attacher ; visez ≤100 KB. |
| Email signalé comme spam | En-têtes MIME appropriés manquants | Assurez‑vous que `SmtpClient` utilise TLS/STARTTLS et définissez une adresse `From` claire. |
| L'image en ligne apparaît comme pièce jointe | Le client ne prend pas en charge CID | Fournissez une URL de secours dans la balise `<img>` (`src='cid:image1' alt='Image'`). |

## Questions fréquemment posées

**Q : Comment puis‑je intégrer plusieurs images dans un seul email ?**  
R : Répétez les étapes d'ajout de pièce jointe et de `LinkedResource` pour chaque image, en attribuant un Content‑ID unique (par ex., `image2`, `image3`) et en les référencant dans le HTML.

**Q : Puis‑je intégrer des images dans des emails texte brut ?**  
R : Le format texte brut ne prend pas en charge les images intégrées. Vous ne pouvez inclure que des URL que les destinataires peuvent cliquer pour voir l'image en ligne.

**Q : Quels formats d'image sont sûrs pour l'intégration dans les emails ?**  
R : JPEG, PNG et GIF sont largement supportés. Utilisez JPEG pour les photographies et PNG pour les graphiques avec transparence.

**Q : Existe‑t‑il un moyen de contrôler les dimensions de l'image dans l'email ?**  
R : Oui — ajoutez les attributs `width`/`height` à la balise `<img>`, par ex., `<img src='cid:image1' width='400' height='300'>`.

**Q : Existe‑t‑il des limites de taille pour les images intégrées ?**  
R : Bien qu'il n'y ait pas de limite SMTP stricte, la plupart des fournisseurs de messagerie recommandent de garder la taille totale de l'email en dessous de 5 Mo. Optimiser la taille de l'image aide à rester bien en dessous de cette limite.

---

**Dernière mise à jour :** 2026-10-12  
**Testé avec :** Aspose.Email for Java 24.11 (latest at time of writing)  
**Auteur :** Aspose

## Tutoriels associés

- [Gestion de la limite de taille des pièces jointes d'email avec Aspose.Email](/email/java/advanced-email-attachments/managing-large-attachments/)
- [Construire l'envoi d'emails avec pièces jointes Aspose Email Java](/email/java/attachments-handling/build-send-emails-attachments-aspose-email-java/)
- [Comment extraire les pièces jointes des fichiers msg avec Aspose.Email pour Java](/email/java/advanced-email-attachments/extracting-attachments-from-email-messages/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}