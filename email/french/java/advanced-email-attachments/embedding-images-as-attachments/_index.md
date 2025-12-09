---
date: 2025-11-30
description: Apprenez à joindre une image à un e‑mail avec Aspose.Email pour Java,
  à envoyer un e‑mail HTML avec image intégrée et à optimiser la taille de l’image
  pour l’e‑mail.
linktitle: How to Attach Image to Email with Aspsoe.Email
second_title: Aspose.Email Java Email Management API
title: Comment joindre une image à un e‑mail avec Aspose.Email pour Java
url: /fr/java/advanced-email-attachments/embedding-images-as-attachments/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Comment joindre une image à un e‑mail avec Aspose.Email pour Java

Dans la communication moderne par e‑mail, **comment joindre une image à un e‑mail** est plus important que jamais — les visuels augmentent l’engagement et permettent de transmettre votre message instantanément. Ce tutoriel vous guide à travers le processus complet de jointure d’une image, de son insertion dans le corps HTML, et de la garantie d’un rendu optimal sur les différents clients de messagerie. Nous aborderons également les meilleures pratiques pour envoyer un e‑mail HTML avec image intégrée et optimiser la taille de l’image pour les e‑mails.

## Réponses rapides
- **Quelle est la classe principale pour créer un e‑mail ?** `MailMessage`
- **Quelle classe permet d’intégrer une image dans le corps HTML ?** `LinkedResource`
- **Ai‑je besoin d’une licence pour envoyer des e‑mails en production ?** Oui, une licence commerciale Aspose.Email est requise.
- **Comment réduire la taille de la pièce jointe ?** Optimisez l’image avant de l’ajouter (par ex., redimensionner/comprimer).
- **Puis‑je envoyer plusieurs images ?** Absolument — il suffit d’ajouter un Content‑ID unique pour chaque image.

## Qu’est‑ce que la jointure d’une image à un e‑mail ?
Joindre une image signifie ajouter le fichier à la structure MIME de l’e‑mail afin que le destinataire puisse le visualiser. Lorsque vous intégrez l’image à l’aide d’un Content‑ID (CID), l’image apparaît directement dans le corps HTML au lieu d’une pièce jointe séparée, donnant l’impression d’une image en ligne.

## Pourquoi envoyer un e‑mail HTML avec image intégrée ?
Incorporer des images dans le HTML vous permet de créer des newsletters, annonces de produits ou tickets de support plus riches. Les destinataires voient le visuel immédiatement, sans devoir télécharger une pièce jointe, ce qui améliore les taux d’ouverture et l’engagement global.

## Prérequis
- **Aspose.Email for Java** – téléchargez depuis le site officiel : [Aspose.Email Java download](https://releases.aspose.com/email/java/).
- Un **serveur SMTP** valide (par ex., Gmail, Outlook, ou votre propre relais de messagerie).
- Un fichier image que vous souhaitez intégrer (JPEG, PNG, GIF, etc.).

> **Astuce :** *Optimisez la taille de l’image pour les e‑mails* en redimensionnant à une largeur ≤600 px et en compressant à ≤100 KB. Cela réduit le temps de chargement et évite de dépasser les limites de taille de boîte aux lettres.

## Création d’un message e‑mail
Tout d’abord, importez les espaces de noms requis et créez une instance de `MailMessage`. Cet objet contiendra le sujet, les destinataires et le corps de votre e‑mail.

```java
// Import necessary libraries
import com.aspose.email.*;

// Create a new email message
MailMessage message = new MailMessage();
```

## Ajout de l’image en tant que pièce jointe
Ensuite, indiquez le chemin du fichier image sur le disque et ajoutez‑le à la collection de pièces jointes du message. La pièce jointe sera ensuite référencée par un Content‑ID.

```java
// Specify the path to the image file
String imagePath = "path/to/your/image.jpg";

// Attach the image to the email
Attachment attachment = new Attachment(imagePath);
message.getAttachments().add(attachment);
```

## Intégration de l’image jointe dans le HTML
Pour afficher l’image dans le corps de l’e‑mail, créez un `LinkedResource` qui encapsule le flux de la pièce jointe. Assignez un Content‑ID unique (par ex., `image1`) et faites‑y référence dans le HTML en utilisant le schéma d’URI `cid:`.

```java
// Create a LinkedResource for the attached image
LinkedResource linkedImage = new LinkedResource(attachment.getContentStream(), "image/jpeg");
linkedImage.setContentId("image1");

// Create an HTML body with the embedded image
String htmlBody = "<html><body><h1>Check out this image:</h1><img src='cid:image1'></body></html>";
message.setHtmlBody(htmlBody);
message.getLinkedResources().addItem(linkedImage);
```

> **Pourquoi utiliser `LinkedResource` ?** Il indique au client de messagerie que l’image fait partie du corps du message, et non d’un téléchargement séparé, ce qui est essentiel pour les scénarios de **envoi d’e‑mail HTML avec image intégrée**.

## Envoi de l’e‑mail
Enfin, configurez `SmtpClient` avec les détails de votre serveur et envoyez le message. Assurez‑vous que les identifiants SMTP ont l’autorisation d’envoyer au nom de l’adresse de l’expéditeur.

```java
// Initialize the SmtpClient
SmtpClient client = new SmtpClient("smtp.example.com", 587, "your_username", "your_password");

// Send the email
client.send(message);
```

Lorsque le destinataire ouvre l’e‑mail, le corps HTML affichera l’image en ligne, offrant une expérience visuelle fluide.

## Problèmes courants & dépannage
| Problème | Cause | Solution |
|----------|-------|----------|
| Image non affichée | Content‑ID incorrect ou `LinkedResource` manquant | Vérifiez que `linkedImage.setContentId("image1")` correspond au `src='cid:image1'` dans le HTML. |
| Taille d’e‑mail importante | Image non optimisée (haute résolution) | Redimensionnez/comprimez l’image avant de la joindre ; visez ≤100 KB. |
| E‑mail signalé comme spam | En‑têtes MIME manquants ou incorrects | Assurez‑vous que `SmtpClient` utilise TLS/STARTTLS et définissez une adresse `From` claire. |
| L’image en ligne apparaît comme pièce jointe | Le client ne supporte pas le CID | Fournissez une URL de secours dans la balise `<img>` (`src='cid:image1' alt='Image'`). |

## Questions fréquentes

**Q : Comment puis‑je intégrer plusieurs images dans un même e‑mail ?**  
R : Répétez les étapes d’ajout de pièce jointe et de `LinkedResource` pour chaque image, en assignant un Content‑ID unique (par ex., `image2`, `image3`) et en les référencant dans le HTML.

**Q : Puis‑je intégrer des images dans des e‑mails en texte brut ?**  
R : Le format texte brut ne prend pas en charge les images intégrées. Vous ne pouvez inclure que des URL que les destinataires peuvent cliquer pour voir l’image en ligne.

**Q : Quels formats d’image sont sûrs pour l’intégration dans les e‑mails ?**  
R : JPEG, PNG et GIF sont largement supportés. Utilisez JPEG pour les photographies et PNG pour les graphiques avec transparence.

**Q : Existe‑t‑il un moyen de contrôler les dimensions de l’image dans l’e‑mail ?**  
R : Oui—ajoutez les attributs width/height à la balise `<img>`, par ex., `<img src='cid:image1' width='400' height='300'>`.

**Q : Existe‑t‑il des limites de taille pour les images intégrées ?**  
R : Bien qu’il n’y ait pas de limite SMTP stricte, la plupart des fournisseurs de messagerie recommandent de garder la taille totale de l’e‑mail inférieure à 5 Mo. Optimiser la taille des images aide à rester largement en dessous de cette limite.

## Conclusion
Vous savez maintenant **comment joindre une image à un e‑mail** avec Aspose.Email pour Java, l’intégrer dans un corps HTML, et appliquer les meilleures pratiques comme **l’optimisation de la taille de l’image pour les e‑mails**. Cette technique vous permet de créer des messages visuellement attrayants qui engagent les destinataires et ont un aspect professionnel sur tous les clients de messagerie.

---

**Dernière mise à jour :** 2025-11-30  
**Testé avec :** Aspose.Email for Java 24.11 (dernière version au moment de la rédaction)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}