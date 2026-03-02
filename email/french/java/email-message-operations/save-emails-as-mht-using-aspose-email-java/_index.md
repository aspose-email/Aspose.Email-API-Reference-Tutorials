---
date: '2026-03-02'
description: Apprenez à utiliser Maven Aspose.Email pour Java afin d’enregistrer les
  e‑mails au format MHT. Ce guide étape par étape couvre l’installation, les modèles
  personnalisés et la conversion d’e‑mail en MHT.
keywords:
- save emails as MHT files
- Aspose.Email for Java
- convert emails to MHTML
title: 'Maven Aspose.Email pour Java : Enregistrer les e‑mails au format MHT'
url: /fr/java/email-message-operations/save-emails-as-mht-using-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Maven Aspose.Email for Java : comment enregistrer les e‑mails au format MHT

## Introduction

Gérer efficacement les données d’e‑mail peut être difficile, surtout lorsqu’il s’agit de partage et d’archivage. Dans ce guide, nous vous montrons **comment enregistrer des fichiers MHT** en utilisant **Maven Aspose.Email for Java**, afin de convertir les e‑mails en MHT avec des modèles personnalisés et de conserver les événements du calendrier intacts. Vous repartirez avec une solution prête à l’emploi qui fonctionne dans n’importe quel environnement Java 16+.

## Quick Answers
- **Quelle bibliothèque faut‑il ?** Maven Aspose.Email for Java (v25.4+).  
- **Quel format est produit ?** Un fichier MHT (MHTML) qui regroupe HTML, images et données de calendrier.  
- **Puis‑je personnaliser l’en‑tête ?** Oui – utilisez `MhtFormatOptions` et des chaînes de modèle.  
- **Ai‑je besoin d’une licence ?** Un essai gratuit suffit pour l’évaluation ; une licence permanente est requise pour la production.  
- **Quelle version de Java est requise ?** JDK 16 ou ultérieure.

## What is Maven Aspose.Email for Java?
Maven Aspose.Email for Java est une API puissante qui vous permet de créer, lire, convertir et manipuler des messages e‑mail directement depuis du code Java. Elle prend en charge de nombreux formats — notamment MSG, EML et MHT — ce qui la rend idéale pour les tâches de **java email conversion**.

## Why Convert Emails to MHT?
- **Compatible Web** : les fichiers MHT s’affichent dans les navigateurs sans ressources externes.  
- **Stabilité d’archivage** : toutes les ressources sont intégrées, préservant l’apparence originale.  
- **Support du calendrier** : vous pouvez rendre les événements récurrents avec des modèles personnalisés.  

## Prerequisites
- **Aspose.Email for Java** (artefact Maven `com.aspose:aspose-email:25.4` avec le classificateur `jdk16`).  
- **Maven** installé et configuré sur votre machine.  
- **JDK 16+** (la bibliothèque cible Java 16).  
- Connaissances de base en Java (gestion de fichiers, dépendances Maven).

## Setting Up Aspose.Email for Java

### Maven Dependency

Ajoutez la dépendance suivante à votre fichier `pom.xml` :

```xml
<dependency>
  <groupId>com.aspose</groupId>
  <artifactId>aspose-email</artifactId>
  <version>25.4</version>
  <classifier>jdk16</classifier>
</dependency>
```

### License Acquisition

Aspose propose un essai gratuit pour explorer ses capacités, ainsi que des options d’achat de licence ou d’obtention d’une licence temporaire.

1. **Essai gratuit** : téléchargez depuis [Releases](https://releases.aspose.com/email/java/) et explorez les fonctionnalités sans limitation.  
2. **Licence temporaire** : accédez à une version pleinement fonctionnelle en la demandant via la [Temporary License Page](https://purchase.aspose.com/temporary-license/).  
3. **Achat** : envisagez l’achat si Aspose.Email répond à vos besoins à long terme.

### Basic Initialization

Une fois installée, initialisez la bibliothèque dans votre application Java :

```java
import com.aspose.email.License;

License license = new License();
license.setLicense("path/to/your/license/file");
```

Avec ces étapes terminées, vous êtes prêt à exploiter les fonctionnalités d’Aspose.Email pour une gestion efficace des e‑mails.

## Implementation Guide

### Feature 1: Load MailMessage

#### Overview
Le chargement d’un message e‑mail est la première étape du traitement et de l’enregistrement au format MHT. Ici, nous montrons comment charger un fichier `.msg` avec `MailMessage`.

#### Step‑by‑Step

**Import Required Classes**

```java
import com.aspose.email.MailMessage;
```

**Load Email from File**

```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY" + "/email/";
MailMessage msg = MailMessage.load(dataDir + "Meeting with Recurring Occurrences.msg");
```

Cet extrait charge un message e‑mail situé dans le répertoire que vous avez spécifié.

### Feature 2: Configure MhtSaveOptions

#### Overview
Configurer `MhtSaveOptions` est essentiel pour définir comment votre e‑mail sera enregistré en MHT, y compris le formatage personnalisé des événements du calendrier.

#### Step‑by‑Step

**Import Required Classes**

```java
import com.aspose.email.MhtSaveOptions;
import com.aspose.email.MhtFormatOptions;
import com.aspose.email.MhtTemplateName;
```

**Set Save Options and Templates**

```java
MhtSaveOptions options = new MhtSaveOptions();
options.setMhtFormatOptions(MhtFormatOptions.WriteHeader | MhtFormatOptions.RenderCalendarEvent);

// Customize templates for email properties
for (Map.Entry<MhtTemplateName, String> entry : options.getFormatTemplates().entrySet()) {
    switch (entry.getKey()) {
        case START:
            options.getFormatTemplates().set_Item(MhtTemplateName.START,
                    "<span class='headerLineTitle'>Start:</span><span class='headerLineText'>{0}</span><br/>");
            break;
        // Add other cases similarly...
    }
}

// Ensure entries are added if absent
options.getFormatTemplates().addIfAbsent(MhtTemplateName.START,
            "<span class='headerLineTitle'>Start:</span><span class='headerLineText'>{0}</span><br/>");
```

Cette configuration définit les en‑têtes et le rendu des événements du calendrier dans la sortie MHT.

### Feature 3: Save MailMessage as MHT

#### Overview
L’étape finale consiste à enregistrer votre `MailMessage` configuré en fichier MHT en utilisant les options spécifiées.

#### Step‑by‑Step

**Import Required Classes**

```java
import com.aspose.email.MailMessage;
import com.aspose.email.MhtSaveOptions;
```

**Save Email Message**

```java
msg.save("YOUR_OUTPUT_DIRECTORY" + "Meeting with Recurring Occurrences_out.mhtml", options);
```

Cette commande écrit l’e‑mail dans un fichier MHT, prêt à être partagé ou archivé.

## Practical Applications
- **Archivage d’e‑mail** : convertissez et stockez les e‑mails importants dans un format compatible Web.  
- **Documentation juridique** : utilisez les fichiers MHT comme preuve légale où les détails de l’e‑mail doivent être préservés.  
- **Partage multiplateforme** : partagez les e‑mails entre plateformes sans problèmes de compatibilité.  

L’intégration avec d’autres systèmes, tels que les CRM ou les outils de gestion de projet, peut améliorer la collaboration en intégrant directement les données essentielles des e‑mails dans les flux de travail.

## Performance Considerations
Pour garantir des performances optimales :
- Gérez efficacement l’utilisation de la mémoire lors du traitement de gros lots d’e‑mails.  
- Optimisez les opérations d’E/S de fichiers afin d’éviter les goulets d’étranglement pendant le processus d’enregistrement.  

Suivre les meilleures pratiques de gestion de la mémoire en Java maintiendra votre application réactive.

## Common Issues and Solutions
| Problème | Cause | Solution |
|----------|-------|----------|
| **NullPointerException sur `msg.save`** | Chemin de sortie incorrect | Vérifiez que `YOUR_OUTPUT_DIRECTORY` existe et est accessible en écriture. |
| **Images manquantes dans le MHT** | `MhtFormatOptions` non configuré pour intégrer les ressources | Ajoutez `MhtFormatOptions.EmbedResources` au drapeau des options. |
| **Événements du calendrier non rendus** | Drapeau `RenderCalendarEvent` omis | Assurez‑vous d’appeler `options.setMhtFormatOptions(MhtFormatOptions.WriteHeader \| MhtFormatOptions.RenderCalendarEvent);` |

## Frequently Asked Questions

**Q : Comment gérer les pièces jointes lors de l’enregistrement d’e‑mails au format MHT ?**  
R : Assurez‑vous que `MhtSaveOptions` est configuré pour inclure la logique de traitement des pièces jointes. La bibliothèque prend en charge l’intégration des pièces jointes dans le fichier MHT.

**Q : Puis‑je personnaliser les en‑têtes d’e‑mail dans le fichier MHT de sortie ?**  
R : Oui, utilisez `MhtFormatOptions.WriteHeader` et définissez des modèles personnalisés pour les différents champs d’en‑tête comme illustré dans le tutoriel.

**Q : Quelles sont les exigences système pour utiliser Aspose.Email Java ?**  
R : Un JDK 16 ou supérieur est requis. La bibliothèque fonctionne sans problème avec la plupart des IDE modernes supportant les projets Maven.

**Q : Est‑il possible d’enregistrer uniquement certaines parties d’un message e‑mail ?**  
R : Bien que le format MHT inclue généralement le message complet, vous pouvez utiliser les propriétés de `MailMessage` pour sélectionner et inclure uniquement le contenu souhaité.

**Q : Comment dépanner les problèmes de chargement ou d’enregistrement d’e‑mail ?**  
R : Vérifiez la justesse des chemins de fichiers, assurez‑vous d’une configuration correcte de la bibliothèque dans votre projet, et consultez le [forum de support Aspose.Email](https://forum.aspose.com/c/email/10) pour obtenir de l’aide.

**Q : La bibliothèque prend‑elle en charge la conversion d’autres formats (EML, MSG) vers MHT ?**  
R : Absolument. `MailMessage.load` peut lire les formats EML, MSG et d’autres, puis vous pouvez les enregistrer en MHT avec les mêmes options.

## Resources
- **Documentation** : pour explorer en profondeur toutes les fonctionnalités, rendez‑vous sur la [Aspose Email Java Documentation](https://reference.aspose.com/email/java/).  
- **Download** : commencez avec votre essai gratuit en téléchargeant depuis [Releases](https://releases.aspose.com/email/java/).  
- **Purchase** : découvrez les options d’achat sur la [Official Purchase Page](https://purchase.aspose.com/buy) pour une utilisation à long terme.  
- **Essai gratuit et licence temporaire** : accédez à l’ensemble des fonctionnalités pendant un essai gratuit ou obtenez une licence temporaire via ces liens :  
  - [Free Trial](https://releases.aspose.com/email/java/)  
  - [Temporary License](https://purchase.aspose.com/temporary-license/)

Explorez, implémentez et transformez votre gestion d’e‑mail avec Aspose.Email for Java dès aujourd’hui !

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Dernière mise à jour** : 2026-03-02  
**Testé avec** : Aspose.Email for Java 25.4 (jdk16 classifier)  
**Auteur** : Aspose  

---