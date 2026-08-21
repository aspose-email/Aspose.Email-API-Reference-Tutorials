---
date: '2026-06-13'
description: Apprenez à lire les fichiers MSG et à analyser les pièces jointes MSG
  à l'aide d'Aspose.Email for Java, en extrayant efficacement les delivery/read receipts
  et les vote results. Comprend la configuration, le code et les meilleures pratiques.
keywords:
- how to read msg
- parse msg attachments
- Aspose.Email for Java
schemas:
- author: Aspose
  dateModified: '2026-06-13'
  description: Learn how to read MSG files and parse MSG attachments using Aspose.Email
    for Java, extracting delivery/read receipts and vote results efficiently. Includes
    setup, code, and best practices.
  headline: How to Read MSG Files with Aspose.Email for Java
  type: TechArticle
- description: Learn how to read MSG files and parse MSG attachments using Aspose.Email
    for Java, extracting delivery/read receipts and vote results efficiently. Includes
    setup, code, and best practices.
  name: How to Read MSG Files with Aspose.Email for Java
  steps:
  - name: Load the MSG File
    text: MapiMessage is the Aspose.Email class that represents an Outlook MSG message.
  - name: Iterate Over Recipients
    text: MapiRecipient represents a single recipient (To, CC, or BCC) in the MSG
      file.
  - name: Retrieve and Print Delivery Time
    text: DeliveryTime is a property of MapiRecipient that holds the timestamp when
      the message was delivered to the recipient’s server.
  - name: Retrieve and Print Read Time
    text: ReadTime is a property of MapiRecipient indicating when the recipient opened
      the message, if that information is available.
  - name: Load the MSG File
    text: MapiMessage is used again to access the voting information embedded in the
      MSG file.
  - name: Iterate Over Recipients
    text: MapiRecipient provides access to each participant’s voting choice and response
      time.
  - name: Retrieve and Print Response
    text: The `VotingResponse` property contains the actual vote (e.g., “Accept”,
      “Decline”, or custom options).
  - name: Retrieve and Print Response Time
    text: '`VotingResponseTime` records when the recipient submitted their vote, allowing
      chronological analysis of poll activity.'
  type: HowTo
- questions:
  - answer: Split the file into smaller segments or use the streaming API to read
      portions without full in‑memory loading.
    question: How do I handle MSG files larger than 500 MB?
  - answer: Yes, map the receipt and vote fields to your DB schema and use JDBC or
      an ORM to persist them.
    question: Can I store the extracted data directly into a database?
  - answer: Absolutely; Aspose.Email for Java is platform‑agnostic and runs on any
      OS with a supported JDK.
    question: Does the library work on Linux environments?
  - answer: Use `MailMessage.getAttachments()` after loading the MSG; the method returns
      a collection of all embedded files.
    question: Is there a way to extract attachments while reading receipts?
  - answer: Reach out via the official Aspose Email Forum for community help or open
      a support ticket with a valid license.
    question: What support options are available if I encounter bugs?
  type: FAQPage
title: Comment lire les fichiers MSG avec Aspose.Email for Java
url: /fr/java/email-parsing-analysis/aspose-email-java-msg-receipts-vote-results/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Comment lire les fichiers MSG avec Aspose.Email pour Java

## Introduction

Lire les fichiers MSG de manière programmatique vous permet d'extraire des données de suivi précieuses — reçus de livraison, confirmations de lecture et résultats de vote — à partir des messages Outlook. Dans ce guide, nous montrerons **comment lire les fichiers msg** avec Aspose.Email pour Java, parcourrons la configuration requise et démontrerons comment extraire efficacement les informations de reçu et de vote.

## Réponses rapides
- **Quelle bibliothèque gère l'analyse des MSG ?** Aspose.Email pour Java.  
- **Puis-je extraire les reçus de lecture ?** Oui, l'API renvoie les horodatages de livraison et de lecture.  
- **Les données de vote sont‑elles accessibles ?** Absolument ; vous pouvez récupérer la réponse de vote de chaque destinataire.  
- **Ai‑je besoin d'une licence ?** Une version d'essai fonctionne pour les tests ; une licence payante supprime les limites d'évaluation.  
- **Quelle version de Java est requise ?** Java 16 ou ultérieure est recommandée.

## Qu'est‑ce qu'Aspose.Email pour Java ?

Aspose.Email pour Java est une bibliothèque Java autonome qui permet la création, la manipulation et la conversion de formats d'e‑mail sans nécessiter Microsoft Outlook. Elle fournit un modèle d'objets riche pour MSG, EML, PST et de nombreux autres formats, permettant aux développeurs de travailler directement avec les données d'e‑mail depuis le code Java. (45 mots)

## Pourquoi utiliser Aspose.Email pour Java pour lire les fichiers MSG ?

Aspose.Email pour Java prend en charge **plus de 30 formats d'e‑mail** et peut traiter des fichiers MSG jusqu'à **500 Mo** sans charger le fichier complet en mémoire. Son moteur d'analyse haute performance réduit la consommation CPU et mémoire, ce qui le rend idéal pour le traitement d'archives de messagerie à grande échelle et les scénarios d'analytique en temps réel. (48 mots)

## Prérequis

- **Bibliothèques et dépendances :** Aspose.Email pour Java version 25.4 ou ultérieure et un runtime JDK 16+.  
- **IDE :** IntelliJ IDEA, Eclipse ou tout IDE compatible Java avec support Maven.  
- **Compétences de base :** Familiarité avec la syntaxe Java et les concepts orientés objet.

## Acquisition de licence

Pour utiliser Aspose.Email pour Java, vous avez besoin d'une licence :

- **Essai gratuit :** Commencez avec la version d'essai gratuite disponible sur le [site Web d'Aspose](https://releases.aspose.com/email/java/).  
- **Licence temporaire :** Demandez une licence temporaire depuis la [page d'achat](https://purchase.aspose.com/temporary-license/).  
- **Achat :** Si vous êtes satisfait de l'évaluation, achetez une licence pour un accès complet à toutes les fonctionnalités via la page [Buy Aspose Products](https://purchase.aspose.com/buy).

## Comment extraire les informations de reçu de lecture et de livraison d'un fichier MSG ?

Chargez le fichier MSG, parcourez ses destinataires et lisez les propriétés `DeliveryTime` et `ReadTime`. Cette approche renvoie les horodatages exacts lorsque le serveur de messagerie de chaque destinataire a livré le message et quand le destinataire l'a ouvert, vous fournissant des données de suivi précises pour l'analyse. (53 mots)

### Étape 1 : Charger le fichier MSG
MapiMessage est la classe Aspose.Email qui représente un message Outlook MSG.  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```  

### Étape 2 : Parcourir les destinataires
MapiRecipient représente un seul destinataire (À, CC ou CCI) dans le fichier MSG.  
```java
import com.aspose.email.MapiMessage;
import com.aspose.email.MapiRecipient;
import com.aspose.email.MapiPropertyTag;

public class RetrieveReceipts {
    public static void main(String[] args) {
        String dataDir = "YOUR_DOCUMENT_DIRECTORY/outlook/";
        MapiMessage msg = MapiMessage.fromFile(dataDir + "message.msg");
```  

### Étape 3 : Récupérer et afficher l'heure de livraison
DeliveryTime est une propriété de MapiRecipient qui contient l'horodatage du moment où le message a été livré au serveur du destinataire.  
```java
        for (MapiRecipient recipient : msg.getRecipients()) {
            System.out.println("Recipient: " + recipient.getDisplayName());
```  

### Étape 4 : Récupérer et afficher l'heure de lecture
ReadTime est une propriété de MapiRecipient indiquant quand le destinataire a ouvert le message, si cette information est disponible.  
```java
            System.out.println("Delivery time: " + 
                recipient.getProperties().get_Item(MapiPropertyTag.PR_RECIPIENT_TRACKSTATUS_TIME_DELIVERY).getDateTime());
```  

## Comment lire les résultats de vote d'un fichier MSG ?

Après avoir chargé le message, l'API expose la réponse de vote de chaque destinataire ainsi que le moment où il a répondu, vous permettant d'agréger les résultats du sondage de manière programmatique. Ces données peuvent être utilisées pour générer des rapports récapitulatifs ou alimenter directement les tableaux de bord de business intelligence pour une prise de décision rapide. (53 mots)

### Étape 1 : Charger le fichier MSG
MapiMessage est à nouveau utilisé pour accéder aux informations de vote intégrées dans le fichier MSG.  
```java
            System.out.println("Read time: " + 
                recipient.getProperties().get_Item(MapiPropertyTag.PR_RECIPIENT_TRACKSTATUS_TIME_READ).getDateTime());
        }
    }
}
```  

### Étape 2 : Parcourir les destinataires
MapiRecipient fournit l'accès au choix de vote et à l'heure de réponse de chaque participant.  
```java
import com.aspose.email.MapiMessage;
import com.aspose.email.MapiRecipient;
import com.aspose.email.MapiPropertyTag;

public class ReadVoteResults {
    public static void main(String[] args) {
        String dataDir = "YOUR_DOCUMENT_DIRECTORY/outlook/";
        MapiMessage msg = MapiMessage.fromFile(dataDir + "message.msg");
```  

### Étape 3 : Récupérer et afficher la réponse
La propriété `VotingResponse` contient le vote réel (par ex., « Accept », « Decline » ou des options personnalisées).  
```java
        for (MapiRecipient recipient : msg.getRecipients()) {
            System.out.println("Recipient: " + recipient.getDisplayName());
```  

### Étape 4 : Récupérer et afficher l'heure de réponse
`VotingResponseTime` enregistre le moment où le destinataire a soumis son vote, permettant une analyse chronologique de l'activité du sondage.  
```java
            System.out.println("Response: " + 
                recipient.getProperties().get_Item(MapiPropertyTag.PR_RECIPIENT_AUTORESPONSE_PROP_RESPONSE).getString());
```  

## Applications pratiques

1. **Suivi des campagnes e‑mail :** Mesurez les taux d'ouverture et le succès de la livraison en analysant les horodatages des reçus.  
2. **Analyse d'enquête :** Consolidez les résultats de vote des sondages Outlook pour une prise de décision rapide.  
3. **Gestion des retours clients :** Récupérez les données de réponse dans les CRM ou plateformes d'analytique pour des insights plus approfondis.

Intégrer ces extractions avec des bases de données ou des outils BI augmente la valeur des données e‑mail brutes.

## Considérations de performance

- Traitez les gros fichiers MSG par **morceaux** pour maintenir une faible utilisation de la mémoire.  
- Utilisez les **API de streaming** lorsqu'il s'agit de milliers de messages.  
- Stockez les données des destinataires dans des collections légères comme `ArrayList` ou `HashMap` pour des recherches rapides.

## Problèmes courants et solutions

- **Horodatages nuls :** Un `ReadTime` manquant signifie généralement que le destinataire n'a pas encore ouvert le message.  
- **Pièces jointes volumineuses :** Si un MSG contient des pièces jointes énormes, activez `LoadOptions.setPreserveEmbeddedResources(false)` pour éviter de les charger en mémoire.  
- **Problèmes d'encodage :** Assurez‑vous que la bonne page de code est définie via `MailMessage.setCharset(Charset.forName("UTF-8"))` lors de la lecture de contenu non‑ASCII.

## Questions fréquemment posées

**Q : Comment gérer les fichiers MSG supérieurs à 500 Mo ?**  
R : Divisez le fichier en segments plus petits ou utilisez l'API de streaming pour lire des portions sans chargement complet en mémoire.

**Q : Puis‑je stocker les données extraites directement dans une base de données ?**  
R : Oui, mappez les champs de reçu et de vote à votre schéma de base de données et utilisez JDBC ou un ORM pour les persister.

**Q : La bibliothèque fonctionne‑t‑elle sous Linux ?**  
R : Absolument ; Aspose.Email pour Java est indépendante de la plateforme et fonctionne sur tout OS avec un JDK supporté.

**Q : Existe‑t‑il un moyen d'extraire les pièces jointes lors de la lecture des reçus ?**  
R : Utilisez `MailMessage.getAttachments()` après avoir chargé le MSG ; la méthode renvoie une collection de tous les fichiers intégrés.

**Q : Quelles options de support sont disponibles en cas de bugs ?**  
R : Contactez le forum officiel Aspose Email pour obtenir de l'aide communautaire ou ouvrez un ticket de support avec une licence valide.

## Ressources
- **Documentation :** [Aspose Email Documentation](https://reference.aspose.com/email/java/)  
- **Documentation (duplicate) :** [Aspose Email Documentation](https://reference.aspose.com/email/java/)  
- **Télécharger le SDK :** [Aspose Email Downloads](https://releases.aspose.com/email/java/)  
- **Section de téléchargement :** [Download Section](https://releases.aspose.com/email/java/)  
- **Acheter une licence :** [Buy Aspose Products](https://purchase.aspose.com/buy)  
- **Essai gratuit :** Commencez avec une [Free Trial Version](https://releases.aspose.com/email/java/)  
- **Licence temporaire :** [Request Temporary License](https://purchase.aspose.com/temporary-license/)  
- **Forum de support :** [Aspose Email Forum](https://forum.aspose.com/c/email/10)  
- **Forum de support (duplicate) :** [Aspose Email Forum](https://forum.aspose.com/c/email/10)

---

**Dernière mise à jour :** 2026-06-13  
**Testé avec :** Aspose.Email pour Java 25.4  
**Auteur :** Aspose

```java
            System.out.println("Response time: " + 
                recipient.getProperties().get_Item(MapiPropertyTag.PR_RECIPIENT_TRACKSTATUS_TIME).getDateTime());
        }
    }
}
```

## Tutoriels associés

- [Comment charger et analyser les fichiers Outlook MSG avec Aspose.Email pour Java : guide complet](/email/java/mapi-operations/outlook-msg-aspose-email-java-guide/)
- [Convertir MSG en EML et gérer les pièces jointes avec Aspose.Email pour Java](/email/java/attachments-handling/aspose-email-java-master-msg-attachments-parsing/)
- [Extraire les pièces jointes en ligne Java – fichiers MSG avec Aspose.Email](/email/java/attachments-handling/extract-inline-attachments-msg-files-java-aspose-email/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}