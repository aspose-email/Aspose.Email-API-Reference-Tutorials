---
date: '2026-09-17'
description: Comment créer une invitation de calendrier avec Aspose.Email for Java
  vous permet de partager des calendriers, de définir des autorisations de délégué
  et d'envoyer des e‑mails de partage de manière programmatique.
keywords:
- how to create calendar invitation
- calendar sharing invitation
- Aspose.Email Java
- delegate calendar permissions
lastmod: '2026-09-17'
og_description: Comment créer une invitation de calendrier avec Aspose.Email for Java
  vous permet de partager des calendriers, de définir des autorisations de délégué
  et d'envoyer des e‑mails de partage via Exchange Web Services, améliorant la collaboration
  d'équipe.
og_image_alt: Guide showing how to create calendar invitation with Aspose.Email for
  Java
og_title: Comment créer une invitation de calendrier avec Aspose.Email for Java
schemas:
- author: Aspose
  dateModified: '2026-09-17'
  description: How to create calendar invitation with Aspose.Email for Java lets you
    share calendars, set delegate permissions, and send sharing emails programmatically.
  headline: How to create calendar invitation with Aspose.Email for Java
  type: TechArticle
- description: How to create calendar invitation with Aspose.Email for Java lets you
    share calendars, set delegate permissions, and send sharing emails programmatically.
  name: How to create calendar invitation with Aspose.Email for Java
  steps:
  - name: Install JDK if you haven't already. You can download it from [Oracle's official
      site](https://www.oracle.com/java/technologies/javase-downloads.html).
    text: Install JDK if you haven't already. You can download it from [Oracle's official
      site](https://www.oracle.com/java/technologies/javase-downloads.html).
  - name: Ensure Maven is installed and configured on your machine.
    text: Ensure Maven is installed and configured on your machine.
  - name: Choose an IDE such as IntelliJ IDEA or Eclipse for easier development.
    text: Choose an IDE such as IntelliJ IDEA or Eclipse for easier development.
  - name: '**Corporate meetings** – Let team members view meeting schedules without
      giving full mailbox rights.'
    text: '**Corporate meetings** – Let team members view meeting schedules without
      giving full mailbox rights.'
  - name: '**Project management** – Project leads can monitor timelines while developers
      retain control of their own calendars.'
    text: '**Project management** – Project leads can monitor timelines while developers
      retain control of their own calendars.'
  - name: '**Event planning** – Vendors receive a **calendar sharing email** to coordinate
      logistics without exposing internal details.'
    text: '**Event planning** – Vendors receive a **calendar sharing email** to coordinate
      logistics without exposing internal details.'
  type: HowTo
- questions:
  - answer: It’s a comprehensive library for handling emails, calendars, and contacts
      in Java applications, supporting Outlook, Exchange, and other protocols.
    question: What is Aspose.Email for Java used for?
  - answer: Install JDK 16+, Maven, add the Aspose.Email dependency to `pom.xml`,
      and obtain a license (trial or full).
    question: How do I set up my environment for using Aspose.Email?
  - answer: Yes, but verify the service URL and permission levels match your server’s
      configuration.
    question: Can I use this code with other versions of Exchange Online?
  - answer: Check network connectivity, credentials, and that the delegate user has
      valid permissions. Review exception details for clues.
    question: What should I do if the calendar sharing invitation fails to send?
  - answer: Absolutely – replace `ExchangeDelegateFolderPermissionLevel.Reviewer`
      with `Editor`, `Author`, or `Owner` as needed.
    question: Is it possible to add additional permissions like editing or full access?
  type: FAQPage
tags:
- calendar sharing
- Aspose.Email
- Java email API
- delegate permissions
- EWS client
title: Comment créer une invitation de calendrier avec Aspose.Email for Java
url: /fr/java/calendar-appointments/create-send-calendar-invitations-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gérer le partage de calendrier : guide Aspose.Email pour Java

## Introduction à la gestion du partage de calendrier
La gestion des invitations de partage de calendrier peut être une tâche complexe, surtout lorsqu'il s'agit de plusieurs utilisateurs sur différentes plateformes. Dans ce tutoriel, vous allez **créer une invitation de partage de calendrier** avec Aspose.Email pour Java, couvrant tout, de la création d'un accès délégué à l'envoi d'e‑mails de partage de calendrier. À la fin, vous pourrez définir les autorisations de délégué, **configurer les autorisations du calendrier**, et rationaliser la collaboration au sein de votre organisation.

**Ce que vous apprendrez**
- Comment initialiser le client EWS avec Aspose.Email pour Java  
- Créer un utilisateur délégué et **définir les autorisations du délégué**  
- **Créer un accès délégué** et configurer les autorisations du calendrier  
- Envoyer un **e‑mail de partage de calendrier** (invitation) de manière programmatique  
- Scénarios réels où ces fonctionnalités ajoutent de la valeur  

Avant de commencer, assurons-nous que vous avez tout ce dont vous avez besoin.

## Réponses rapides
- **Quel est le but principal de ce guide ?** Montrer comment **créer une invitation de partage de calendrier** en utilisant Aspose.Email pour Java.  
- **Quelle version de la bibliothèque est requise ?** Aspose.Email pour Java 25.4 (classificateur JDK 16).  
- **Ai‑je besoin d’une licence ?** Oui – une licence d’essai ou complète est requise pour une utilisation en production.  
- **Quel environnement est nécessaire ?** JDK 16+, Maven et un compte Exchange Online.  
- **Puis‑je l’utiliser avec d’autres serveurs Exchange ?** Oui, mais il peut être nécessaire d’ajuster l’URL du service et les niveaux d’autorisation.  

## Qu’est‑ce qu’une invitation de partage de calendrier ?
Une invitation de partage de calendrier est un message e‑mail qui accorde à un autre utilisateur l’accès pour consulter (ou modifier) votre calendrier sans lui donner les droits complets de la boîte aux lettres. Elle permet aux membres de l’équipe de voir votre agenda, de proposer des réunions ou de gérer des événements tout en maintenant la sécurité de votre boîte aux lettres.

## Pourquoi configurer les autorisations du calendrier ?
Configurer les autorisations du calendrier vous permet de contrôler exactement ce qu’un délégué peut faire — s’il ne peut que lire les événements, en proposer de nouveaux ou modifier les entrées existantes. Des paramètres d’autorisation appropriés protègent les informations sensibles tout en permettant une collaboration efficace. Par exemple, accorder un accès en lecture seule empêche les modifications accidentelles, tandis que les droits d’édition permettent au délégué de planifier ou de modifier des réunions en votre nom.

## Prérequis
- **Java Development Kit (JDK) :** Version 16 ou ultérieure.  
- **Maven :** Pour la gestion des dépendances et la construction du projet.  
- **Bibliothèque Aspose.Email pour Java :** Version 25.4 avec prise en charge du JDK 16.  

### Exigences de configuration de l’environnement
1. Installez le JDK si ce n’est pas déjà fait. Vous pouvez le télécharger depuis le [site officiel d’Oracle](https://www.oracle.com/java/technologies/javase-downloads.html).  
2. Assurez‑vous que Maven est installé et configuré sur votre machine.  
3. Choisissez un IDE tel qu’IntelliJ IDEA ou Eclipse pour faciliter le développement.

### Prérequis de connaissances
- Compétences de base en programmation Java  
- Familiarité avec les dépendances Maven  
- Optionnel : Expérience avec Exchange Web Services (EWS)

## Configuration d’Aspose.Email pour Java
### Configuration Maven
Ajoutez la dépendance suivante à votre fichier `pom.xml` :

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Acquisition de licence
Aspose.Email pour Java nécessite une licence pour la pleine fonctionnalité. Vous pouvez :
- **Essai gratuit :** Télécharger depuis la [page de diffusion d’Aspose](https://releases.aspose.com/email/java/).  
- **Licence temporaire :** Demander une clé temporaire sur le site d’Aspose.  
- **Achat :** Obtenir une licence permanente pour les déploiements en production.

### Initialisation et configuration de base
Une fois que Maven a résolu la dépendance, initialisez le client EWS :

`ExchangeService` est la classe principale utilisée pour communiquer avec Exchange Web Services.  

```java
IEWSClient client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser", "pwd", "domain");
```

## Comment créer une invitation de partage de calendrier
Pour créer une invitation de partage de calendrier, vous vous connectez d’abord à Exchange en utilisant le client `ExchangeService`, puis vous définissez un délégué avec le niveau d’autorisation souhaité, et enfin vous composez un `MailMessage` qui inclut la demande de partage. Les étapes suivantes démontrent ce flux de travail en Java.

Ci‑dessous, nous couvrons deux fonctionnalités principales : créer et envoyer une invitation de partage de calendrier, et **définir les autorisations du délégué** pour l’accès au calendrier.

### Fonctionnalité 1 : créer et envoyer une invitation de partage de calendrier
#### Vue d’ensemble
Cette fonctionnalité vous guide à travers l’initialisation du client, **créer un accès délégué**, et l’envoi de l’e‑mail d’invitation.

#### Implémentation étape par étape
##### 1️⃣ Initialiser le client EWS
`ExchangeService` représente la connexion à un serveur Exchange et est utilisé pour envoyer et recevoir des messages.`  

```java
IEWSClient client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser", "pwd", "domain");
```  
Cela connecte votre application Java à Exchange Online.

##### 2️⃣ Créer un utilisateur délégué
`DelegateUser` définit l’adresse e‑mail du délégué et le niveau d’autorisation à accorder.`  

```java
ExchangeDelegateUser delegateUser = new ExchangeDelegateUser("sharingfrom@domain.com", ExchangeDelegateFolderPermissionLevel.NotSpecified);
delegateUser.getFolderPermissions().setCalendarFolderPermissionLevel(ExchangeDelegateFolderPermissionLevel.Reviewer);
client.delegateAccess(delegateUser, "sharingfrom@domain.com");
```  
Ici, nous **créons un accès délégué** et assignons le niveau `Reviewer`, qui permet au délégué de voir les éléments du calendrier.

##### 3️⃣ Envoyer une invitation de partage de calendrier
`MailMessage` construit l’e‑mail qui transporte l’invitation de partage de calendrier.`  

```java
MapiMessage mapiMessage = client.createCalendarSharingInvitationMessage("sharingfrom@domain.com");

MailConversionOptions options = new MailConversionOptions();
options.setConvertAsTnef(true);

MailMessage mail = mapiMessage.toMailMessage(options);
client.send(mail);
```  
Le code crée un **e‑mail de partage de calendrier** (invitation) et l’envoie via le client EWS.

### Fonctionnalité 2 : autorisation d’accès au calendrier du délégué
#### Vue d’ensemble
Cette section montre comment **configurer les autorisations du calendrier** et s’assurer que le délégué possède les droits appropriés.

#### Étapes d’implémentation
##### 1️⃣ Initialiser le client EWS (réutilisation)
`ExchangeService` peut être réutilisé pour plusieurs opérations après la configuration initiale.`  

```java
IEWSClient client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser", "pwd", "domain");
```  

##### 2️⃣ Créer et définir les autorisations du délégué
`ExchangeDelegateFolderPermissionLevel` énumère les niveaux d’accès qu’un délégué peut avoir à un dossier de calendrier.`  

```java
ExchangeDelegateUser delegateUser = new ExchangeDelegateUser("sharingfrom@domain.com", ExchangeDelegateFolderPermissionLevel.NotSpecified);
delegateUser.getFolderPermissions().setCalendarFolderPermissionLevel(ExchangeDelegateFolderPermissionLevel.Reviewer);

client.delegateAccess(delegateUser, "sharingfrom@domain.com");
```  
Cet extrait **définit les autorisations du délégué** afin que l’utilisateur puisse voir les entrées du calendrier sans accès complet à la boîte aux lettres.

## Comment configurer les autorisations du calendrier pour les délégués
Lorsqu’un délégué a besoin de plus qu’un accès en lecture seule, vous pouvez ajuster le `ExchangeDelegateFolderPermissionLevel` pour accorder des droits d’édition, d’auteur ou de propriétaire. Choisissez le niveau minimal qui satisfait le besoin métier afin de maintenir la sécurité tout en fournissant la fonctionnalité nécessaire. Par exemple, attribuer le niveau Editor permet au délégué de créer, modifier et supprimer des événements, tandis que le niveau Reviewer ne permet que la visualisation.

- `Reviewer` – accès en lecture seule.  
- `Editor` – accès lecture/écriture.  
- `Author` – créer et lire, mais ne peut pas supprimer.  
- `Owner` – contrôle total, y compris les modifications d’autorisations.  

**Astuce :** Utilisez le niveau de privilège le plus bas qui satisfait le besoin métier pour garder vos données de calendrier sécurisées.

## Applications pratiques
Scénarios réels où **gérer le partage de calendrier** brille :
1. **Réunions d’entreprise** – Permettre aux membres de l’équipe de voir les plannings de réunions sans donner les droits complets de la boîte aux lettres.  
2. **Gestion de projet** – Les chefs de projet peuvent surveiller les échéances tandis que les développeurs conservent le contrôle de leurs propres calendriers.  
3. **Planification d’événements** – Les fournisseurs reçoivent un **e‑mail de partage de calendrier** pour coordonner la logistique sans exposer les détails internes.

## Considérations de performance
- **Gestion de la mémoire :** Libérez rapidement les gros objets `MailMessage` dans les applications à fort volume.  
- **Gestion des exceptions :** Enveloppez les appels réseau dans des blocs try‑catch pour gérer les problèmes de connectivité de manière élégante.  
- **Mises à jour de la bibliothèque :** Aspose.Email pour Java prend en charge plus de 50 protocoles et peut traiter des calendriers contenant jusqu’à 10 000 éléments sans charger le fichier complet en mémoire, il faut donc maintenir la bibliothèque à jour pour profiter des améliorations de performance et des corrections de bugs.

## Problèmes courants et solutions
| Problème | Cause probable | Solution |
|----------|----------------|----------|
| Invitation non reçue | Filtres anti‑spam ou adresse e‑mail incorrecte | Vérifiez l’adresse du destinataire et ajoutez le domaine d’envoi à la liste des expéditeurs sûrs |
| Autorisation non appliquée | Utilisation d’un mauvais `ExchangeDelegateFolderPermissionLevel` | Vérifiez que le niveau d’autorisation correspond à l’accès requis |
| Exception d’exécution sur `createCalendarSharingInvitationMessage` | Licence manquante ou bibliothèque obsolète | Assurez‑vous qu’une licence valide est chargée et que vous utilisez la dernière version d’Aspose.Email |

## Questions fréquemment posées
**Q : À quoi sert Aspose.Email pour Java ?**  
R : C’est une bibliothèque complète pour gérer les e‑mails, les calendriers et les contacts dans les applications Java, prenant en charge Outlook, Exchange et d’autres protocoles.

**Q : Comment configurer mon environnement pour utiliser Aspose.Email ?**  
R : Installez JDK 16+, Maven, ajoutez la dépendance Aspose.Email à `pom.xml`, et obtenez une licence (essai ou complète).

**Q : Puis‑je utiliser ce code avec d’autres versions d’Exchange Online ?**  
R : Oui, mais vérifiez que l’URL du service et les niveaux d’autorisation correspondent à la configuration de votre serveur.

**Q : Que faire si l’invitation de partage de calendrier n’est pas envoyée ?**  
R : Vérifiez la connectivité réseau, les informations d’identification, et que l’utilisateur délégué possède des autorisations valides. Examinez les détails de l’exception pour obtenir des indices.

**Q : Est‑il possible d’ajouter des autorisations supplémentaires comme la modification ou l’accès complet ?**  
R : Absolument – remplacez `ExchangeDelegateFolderPermissionLevel.Reviewer` par `Editor`, `Author` ou `Owner` selon les besoins.

## Conclusion
Vous disposez maintenant d’une solution complète, de bout en bout, pour **créer une invitation de partage de calendrier** avec Aspose.Email pour Java. En initialisant le client EWS, **créant un accès délégué**, **définissant les autorisations du délégué**, et en envoyant un **e‑mail de partage de calendrier**, vous pouvez automatiser la collaboration au sein de votre organisation.

**Prochaines étapes**
- Expérimentez d’autres niveaux d’autorisation (Editor, Owner).  
- Intégrez cette logique dans vos systèmes de planification ou RH existants.  
- Explorez d’autres fonctionnalités d’Aspose.Email comme les événements récurrents ou les demandes de réunion.

---

**Dernière mise à jour :** 2026-09-17  
**Testé avec :** Aspose.Email pour Java 25.4 (classificateur JDK 16)  
**Auteur :** Aspose

## Tutoriels associés

- [Comment créer un élément de calendrier Java avec Aspose.Email](/email/java/calendar-appointments/create-save-calendar-items-aspose-email-java/)
- [Filtrer les rendez-vous Exchange par date avec Aspose Email Java](/email/java/calendar-appointments/aspose-email-java-filter-exchange-appointments-by-date/)
- [Créer un calendrier Exchange Java avec Aspose.Email – Guide complet](/email/java/calendar-appointments/mastering-exchange-calendar-management-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}