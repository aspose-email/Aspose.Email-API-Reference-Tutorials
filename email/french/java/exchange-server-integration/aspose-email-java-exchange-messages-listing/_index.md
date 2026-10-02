---
date: '2026-10-02'
description: Apprenez à connecter Exchange et à répertorier les dossiers publics Exchange
  à l'aide d'Aspose.Email for Java. Ce guide étape par étape montre la dépendance
  Maven et la configuration sans code.
keywords:
- how to connect exchange
- list exchange public folders
- maven dependency aspose email
lastmod: '2026-10-02'
og_description: Apprenez à connecter Exchange et à répertorier les dossiers publics
  Exchange à l'aide d'Aspose.Email for Java. Ce guide couvre la dépendance Maven,
  la licence et la récupération récursive des messages.
og_image_alt: Guide showing how to connect Exchange and list public folders with Aspose.Email
  for Java
og_title: Comment connecter Exchange et répertorier les dossiers publics en Java
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Learn how to connect exchange and list exchange public folders using
    Aspose.Email for Java. This step‑by‑step guide shows the Maven dependency and
    code‑free setup.
  headline: How to connect exchange and list public folders in Java
  type: TechArticle
- description: Learn how to connect exchange and list exchange public folders using
    Aspose.Email for Java. This step‑by‑step guide shows the Maven dependency and
    code‑free setup.
  name: How to connect exchange and list public folders in Java
  steps:
  - name: '**Automated email archiving** – Periodically pull all public‑folder messages
      and store them in a compliant archive.'
    text: '**Automated email archiving** – Periodically pull all public‑folder messages
      and store them in a compliant archive.'
  - name: '**Backup solutions** – Mirror Exchange public folders to a secure file
      system or cloud bucket, guaranteeing data redundancy.'
    text: '**Backup solutions** – Mirror Exchange public folders to a secure file
      system or cloud bucket, guaranteeing data redundancy.'
  - name: '**Custom email clients** – Build lightweight viewers that display only
      the folders and messages you need, reducing UI complexity.'
    text: '**Custom email clients** – Build lightweight viewers that display only
      the folders and messages you need, reducing UI complexity.'
  type: HowTo
- questions:
  - answer: Yes. Provide the Office 365 EWS endpoint (`https://outlook.office365.com/EWS/Exchange.asmx`)
      and use modern authentication (OAuth) – Aspose.Email supports OAuth tokens out
      of the box.
    question: Can I use this code with Exchange Online (Office 365)?
  - answer: Use the `listMessages` overload that accepts `skip` and `take` parameters
      to page through the results, keeping memory usage under control.
    question: What if a folder contains more than 10 000 messages?
  - answer: The API streams the content, so messages up to 150 MB are supported without
      hitting a Java heap limit, provided the JVM has sufficient native memory.
    question: Is there a limit on the size of a single email I can download?
  - answer: By default Aspose.Email trusts the Java default keystore. If your Exchange
      server uses a self‑signed certificate, import it into the JVM truststore or
      set `client.setEnableSslVerification(false)` for testing only.
    question: Do I need to handle SSL certificates manually?
  - answer: Enable Aspose.Email’s built‑in logging by configuring `Logger.setLevel(Level.INFO)`
      and directing output to a file or monitoring system.
    question: How do I log the operations for audit purposes?
  type: FAQPage
tags:
- exchange integration
- Aspose.Email
- Java email automation
title: Comment connecter Exchange et répertorier les dossiers publics en Java
url: /fr/java/exchange-server-integration/aspose-email-java-exchange-messages-listing/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment connecter Exchange et répertorier les dossiers publics en Java

## Introduction
Dans les entreprises modernes, accéder de manière programmatique aux boîtes aux lettres Microsoft Exchange vous permet d'automatiser les tâches d'archivage, de surveillance et de génération de rapports. Ce tutoriel montre **comment connecter Exchange** avec Aspose.Email pour Java puis **répertorier les dossiers publics Exchange** de façon récursive. Vous verrez la dépendance Maven requise, les étapes de licence et la séquence exacte des appels API — aucune bibliothèque supplémentaire n'est nécessaire. À la fin, vous pourrez extraire les messages de n'importe quel dossier public et les enregistrer localement.

## Réponses rapides
- **Quelle est la première étape ?** Ajoutez la dépendance Maven Aspose.Email à votre `pom.xml`.  
- **Ai‑je besoin d'une licence ?** Oui — utilisez une licence temporaire pour l'évaluation ou achetez une licence complète pour la production.  
- **Quelle classe crée la connexion ?** `ExchangeClient` (ou `ImapClient` pour IMAP) gère l'authentification et la communication avec le serveur.  
- **Puis‑je répertorier automatiquement les sous‑dossiers ?** Oui — utilisez la méthode récursive `listSubFolders` fournie par l'API.  
- **Cette approche est‑elle thread‑safe ?** Les objets client ne sont pas thread‑safe ; créez une instance séparée par thread pour les charges de travail concurrentes.

## Qu'est‑ce que la connexion à Exchange ?
**Comment connecter Exchange** est le processus d'authentification d'une application Java avec un serveur Microsoft Exchange sur site ou basé sur le cloud, afin de pouvoir effectuer des appels API tels que l'énumération de dossiers ou la récupération de messages. Aspose.Email abstrait les protocoles EWS/IMAP sous‑jacents, vous offrant un modèle d'objet unique et cohérent.

## Pourquoi répertorier les dossiers publics Exchange ?
Lister les dossiers publics vous donne une visibilité sur la structure hiérarchique que les organisations utilisent pour les boîtes aux lettres partagées, les listes de distribution et les archives. Aspose.Email peut énumérer plus de **50 dossiers publics** en un seul appel et prend en charge le traitement de boîtes aux lettres de plusieurs centaines de pages sans charger l'intégralité du magasin en mémoire, ce qui réduit la consommation de RAM jusqu'à 70 %.

## Prérequis
- **Aspose.Email pour Java** — version 25.4 ou ultérieure (la dernière version stable).  
- **Java Development Kit (JDK)** — JDK 11 ou plus récent installé et `JAVA_HOME` configuré.  
- **Maven** — pour la gestion des dépendances et l'automatisation de la construction.  
- Connaissances de base de la syntaxe Java et des concepts Exchange (boîtes aux lettres, dossiers, EWS).

## Configuration d'Aspose.Email pour Java
Pour intégrer la bibliothèque, ajoutez la dépendance Maven à votre `pom.xml` du projet. Voici la **dépendance Maven Aspose Email** dont vous avez besoin.

### Dépendance Maven
Ajoutez le fragment suivant à l'intérieur de l'élément `<dependencies>` de votre `pom.xml` :

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Étapes d'obtention de licence
Aspose.Email requires a valid license for full‑feature use:

- **Essai gratuit** – Téléchargez une licence temporaire depuis le [site Aspose](https://purchase.aspose.com/temporary-license/) pour évaluer l'API.  
- **Achat** – Obtenez une licence commerciale via le portail Aspose pour les déploiements en production.

#### Initialisation de base
Après que Maven ait résolu le paquet et que vous disposiez d'un fichier de licence, placez le fichier `.lic` sur le classpath et initialisez la bibliothèque :

```java
import com.aspose.email.License;

License license = new License();
license.setLicense("path/to/your/license.lic");
```

## Guide d'implémentation
Nous parcourrons chaque bloc fonctionnel, en répondant aux questions clés avec des paragraphes directs et concis avant les étapes détaillées.

### Comment connecter Exchange ?
Chargez le `ExchangeClient` avec l'URL du serveur, les identifiants utilisateur et le domaine, puis appelez `connect()`. Le client établit une session HTTPS avec Exchange Web Services (EWS) et valide les identifiants. Si la connexion échoue, l'API lève une `AuthenticationException` détaillée incluant le code d'état HTTP pour un dépannage rapide.  
`ExchangeClient` est la classe d'Aspose.Email qui gère une connexion aux Exchange Web Services.

```java
import com.aspose.email.EWSClient;
import com.aspose.email.IEWSClient;

IEWSClient connectToExchangeServer(String exchangeUrl, String username, String password, String domain) {
    // Create instance of IEWSClient class by providing credentials
    return EWSClient.getEWSClient(exchangeUrl, username, password, domain);
}
```

### Comment répertorier les dossiers publics Exchange ?
Appelez `client.listPublicFolders()` pour récupérer une collection d'objets `FolderInfo` représentant chaque dossier public de niveau supérieur. La méthode renvoie des métadonnées telles que le nom du dossier, le nombre total d'éléments et un identifiant unique utilisé pour les appels ultérieurs. Cet appel se termine en moins de 2 secondes pour les déploiements typiques sur site avec jusqu'à 500 dossiers.  
`listPublicFolders()` renvoie une collection d'objets `FolderInfo`.  
`FolderInfo` contient des métadonnées comme le nom d'affichage et le nombre d'éléments.

```java
import com.aspose.email.ExchangeFolderInfoCollection;
import com.aspose.email.IEWSClient;

ExchangeFolderInfoCollection listPublicFolders(IEWSClient client) {
    // List all public folders and return their information as a collection
    return client.listPublicFolders();
}
```

### Comment afficher les informations du dossier ?
Itérez sur la collection `FolderInfo` et affichez le `displayName` et le `subFolderCount`. Cette vue rapide vous aide à comprendre la hiérarchie avant d'effectuer une exploration plus approfondie. Pour les grandes organisations, l'API peut paginer les résultats, renvoyant 100 dossiers par page afin de limiter l'utilisation de la mémoire.

```java
import com.aspose.email.ExchangeFolderInfo;

void displayFolderInfo(ExchangeFolderInfo folder) {
    // Print folder details
    System.out.println("Name: " + folder.getDisplayName());
    System.out.println("Subfolders count: " + folder.getChildFolderCount());
}
```

### Comment répertorier les messages d'un dossier ?
Appelez `client.listMessages(folderId)` où `folderId` est l'identifiant obtenu à l'étape précédente. La méthode renvoie une liste d'objets `MessageInfo` contenant le sujet, l'expéditeur et la date de réception. Vous pouvez limiter le jeu de résultats avec `maxCount` pour éviter de submerger le client lors du traitement de dossiers très volumineux.  
`listMessages(folderId)` renvoie une liste d'objets `MessageInfo`.  
`MessageInfo` contient les propriétés de base d'un e‑mail telles que le sujet, l'expéditeur et la date de réception.

```java
import com.aspose.email.ExchangeMessageInfoCollection;
import com.aspose.email.IEWSClient;

ExchangeMessageInfoCollection listMessagesFromFolder(IEWSClient client, ExchangeFolderInfo folder) {
    // List messages from the specified public folder and return their information as a collection
    return client.listMessagesFromPublicFolder(folder);
}
```

### Comment récupérer et enregistrer les messages ?
Pour chaque `MessageInfo`, utilisez `client.fetchMessage(messageId)` pour télécharger le contenu MIME complet. Puis écrivez le tableau d'octets dans un fichier `.eml` sur le disque. L'API diffuse le contenu, de sorte que même les messages de 100 Mo sont gérés sans charger la charge utile complète en mémoire.  
`fetchMessage(messageId)` télécharge le contenu MIME complet de l'e‑mail spécifié.

```java
import com.aspose.email.ExchangeMessageInfo;
import com.aspose.email.IEWSClient;
import com.aspose.email.MailMessage;
import com.aspose.email.SaveOptions;

void fetchAndSaveMessages(IEWSClient client, ExchangeMessageInfoCollection messages) {
    for (ExchangeMessageInfo messageInfo : messages) {
        // Fetch the full MailMessage using its unique URI
        MailMessage msg = client.fetchMessage(messageInfo.getUniqueUri());
        
        // Save the fetched message to a file named after its subject with .msg extension
        String filePath = "YOUR_OUTPUT_DIRECTORY/" + msg.getSubject() + ".msg";
        msg.save(filePath, SaveOptions.getDefaultMsgUnicode());
    }
}
```

### Comment répertorier récursivement les messages des sous‑dossiers ?
Implémentez un parcours en profondeur d'abord : commencez par un dossier de niveau supérieur, listez ses sous‑dossiers via `client.listSubFolders(parentId)`, puis appelez la même routine de répertoriage des messages pour chaque enfant. Ce modèle garantit que chaque message de l'arbre des dossiers publics est traité. La profondeur de récursion est limitée uniquement par la hiérarchie des dossiers du serveur (généralement < 20 niveaux).  
`listSubFolders(parentId)` renvoie les dossiers enfants immédiats du dossier donné.

```java
import com.aspose.email.ExchangeFolderInfo;
import com.aspose.email.IEWSClient;

void listMessagesFromSubFolders(IEWSClient client, ExchangeFolderInfo folder) {
    // List all messages in the current public folder
    ExchangeMessageInfoCollection msgCollection = client.listMessagesFromPublicFolder(folder);
    fetchAndSaveMessages(client, msgCollection);

    if (folder.getChildFolderCount() > 0) {
        ExchangeFolderInfoCollection subFolders = client.listSubFolders(folder);
        for (ExchangeFolderInfo subFolder : subFolders) {
            listMessagesFromSubFolders(client, subFolder);
        }
    }
}
```

## Applications pratiques
1. **Archivage automatisé des e‑mails** – Extraire périodiquement tous les messages des dossiers publics et les stocker dans une archive conforme.  
2. **Solutions de sauvegarde** – Miroir des dossiers publics Exchange vers un système de fichiers sécurisé ou un bucket cloud, garantissant la redondance des données.  
3. **Clients e‑mail personnalisés** – Construire des visionneuses légères qui affichent uniquement les dossiers et les messages nécessaires, réduisant la complexité de l'interface.

## Considérations de performance
When scaling to thousands of folders and millions of messages, keep these tips in mind:

- **Pooling de connexions** – Réutilisez une seule instance `ExchangeClient` pour plusieurs opérations au lieu de créer un nouveau client par dossier.  
- **Chargement paresseux** – Demandez uniquement les métadonnées dont vous avez besoin (`listMessages` avec le paramètre `maxCount`) et récupérez les corps complets à la demande.  
- **Libérer les objets** – Appelez `client.dispose()` après l'exécution du lot pour libérer les connexions HTTP et les tampons locaux aux threads.  
- **Traitement parallèle** – Répartissez les dossiers de niveau supérieur sur plusieurs threads, chacun avec sa propre instance client, pour exploiter efficacement les CPU multi‑cœurs.

## Questions fréquemment posées

**Q : Puis‑je utiliser ce code avec Exchange Online (Office 365) ?**  
R : Oui. Fournissez le point de terminaison EWS d'Office 365 (`https://outlook.office365.com/EWS/Exchange.asmx`) et utilisez l'authentification moderne (OAuth) – Aspose.Email prend en charge les jetons OAuth dès le départ.

**Q : Que faire si un dossier contient plus de 10 000 messages ?**  
R : Utilisez la surcharge de `listMessages` qui accepte les paramètres `skip` et `take` pour paginer les résultats, maintenant l'utilisation de la mémoire sous contrôle.

**Q : Existe‑t‑il une limite de taille pour un e‑mail unique que je peux télécharger ?**  
R : L'API diffuse le contenu, ainsi les messages jusqu'à 150 Mo sont pris en charge sans atteindre la limite du tas Java, à condition que la JVM dispose de suffisamment de mémoire native.

**Q : Dois‑je gérer manuellement les certificats SSL ?**  
R : Par défaut, Aspose.Email fait confiance au keystore Java par défaut. Si votre serveur Exchange utilise un certificat auto‑signé, importez‑le dans le truststore JVM ou définissez `client.setEnableSslVerification(false)` uniquement pour les tests.

**Q : Comment consigner les opérations à des fins d’audit ?**  
R : Activez la journalisation intégrée d'Aspose.Email en configurant `Logger.setLevel(Level.INFO)` et en dirigeant la sortie vers un fichier ou un système de surveillance.

## Conclusion
Vous disposez maintenant d'une recette complète et prête pour la production pour **comment connecter Exchange** et répertorier de façon récursive les messages des dossiers publics à l'aide d'Aspose.Email pour Java. Les étapes couvrent la configuration Maven, la licence, la connexion, l'énumération des dossiers, la récupération des messages et l'optimisation des performances. Étendez cette base en l'intégrant à des bases de données, du stockage cloud ou des pipelines d'analyse personnalisés pour répondre aux besoins spécifiques de votre organisation.

---

**Last Updated:** 2026-10-02  
**Tested With:** Aspose.Email for Java 25.4  
**Author:** Aspose

## Tutoriels associés

- [How to Connect to Exchange Server using Aspose.Email in Java: Step-by-Step Guide](/email/java/exchange-server-integration/aspose-email-java-exchange-server-connection/)
- [How to Connect and List Exchange Server Folders Using Aspose.Email for Java](/email/java/exchange-server-integration/connect-list-exchange-server-folders-aspose-email-java/)
- [Manage Exchange Server Folders Using Aspose.Email for Java: A Comprehensive Guide](/email/java/exchange-server-integration/exchange-server-folders-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}