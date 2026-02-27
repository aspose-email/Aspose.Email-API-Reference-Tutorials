---
date: '2026-02-27'
description: Apprenez à charger des fichiers MSG et à les convertir en MHTML avec
  Aspose.Email pour Java, y compris les paramètres de fuseau horaire personnalisés
  et les conseils de traitement d'e-mails par lots.
keywords:
- Aspose.Email for Java
- load emails in MHTML format
- custom timezone settings
title: Comment charger un fichier MSG et l’enregistrer au format MHTML avec Aspose.Email
  pour Java
url: /fr/java/email-message-operations/load-save-emails-mhtml-aspose-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Comment charger un MSG et l’enregistrer en MHTML avec Aspose.Email pour Java

## Introduction

Si vous avez besoin de **how to load msg** des fichiers, d’ajuster leurs horodatages, puis de **convert msg to mhtml**, vous êtes au bon endroit. Dans ce tutoriel, nous allons parcourir le chargement d’un courriel `.msg`, appliquer un décalage de fuseau horaire personnalisé, et enregistrer le résultat sous forme d’archive MHTML — le tout avec Aspose.Email pour Java. Que vous manipuliez un seul message ou un pipeline de **batch email processing**, ces étapes vous fourniront une base solide.

**Ce que vous allez apprendre**
- Comment charger un `MailMessage` à partir d’un fichier `.msg`.
- Comment définir un fuseau horaire personnalisé et la date actuelle.
- Comment enregistrer le message en MHTML avec un formatage précis.
- Astuces pour faire évoluer l’approche vers des scénarios de traitement par lots.

Prêt à optimiser votre flux de travail email ? Préparons d’abord l’environnement.

## Quick Answers
- **What is the primary library?** Aspose.Email for Java.
- **Can I load MSG and export to MHTML in one step?** No, you load, adjust, then save.
- **Do I need a license for production?** Yes, a valid Aspose.Email license is required.
- **Is timezone handling supported?** Yes, via `setTimeZoneOffset`.
- **Can this be used in batch processing?** Absolutely – wrap the steps in a loop.

## Prerequisites

Avant de commencer, assurez-vous de disposer de ce qui suit :

### Required Libraries and Dependencies
- Bibliothèque **Aspose.Email for Java** version 25.4 (classifier jdk16)
- Connaissances de base en Java.
- Un IDE tel qu’IntelliJ IDEA ou Eclipse.

### Environment Setup Requirements
- JDK 16 ou une version plus récente installée.
- Maven pour la gestion des dépendances.

## Setting Up Aspose.Email for Java

Pour ajouter la bibliothèque à un projet Maven, incluez la dépendance suivante :

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### License Acquisition Steps

Commencez avec un **free trial** ou obtenez une **temporary license** afin d’évaluer les capacités complètes de la bibliothèque sans limitations. Pour une utilisation à long terme, envisagez d’acheter une licence :

- [Free Trial](https://releases.aspose.com/email/java/)
- [Temporary License](https://purchase.aspose.com/temporary-license/)
- [Purchase License](https://purchase.aspose.com/buy)

### Basic Initialization

Après avoir ajouté la dépendance, initialisez la licence dans votre code Java :

```java
import com.aspose.email.License;

License license = new License();
license.setLicense("path_to_your_license_file.lic");
```

## Implementation Guide

Nous allons diviser l’implémentation en trois fonctionnalités claires.

### Feature 1: Loading a MailMessage from a File

#### Overview
Charger un fichier `.msg` vous donne un accès programmatique complet au contenu du courriel, aux pièces jointes et aux métadonnées.

#### Step‑by‑Step

**Import the required classes**

```java
import com.aspose.email.MailMessage;
import com.aspose.email.MsgLoadOptions;
```

**Load the email**

```java
String filename = "YOUR_DOCUMENT_DIRECTORY/MSG file with RTF Formatting.msg";
MailMessage msg = MailMessage.load(filename, new MsgLoadOptions());
```

`MsgLoadOptions` vous permet de contrôler la façon dont le fichier MSG est interprété ; les paramètres par défaut conviennent à la plupart des scénarios.

### Feature 2: Setting the Current Date and Custom Timezone Offset

#### Overview
Des horodatages précis sont essentiels lorsque vous traitez des utilisateurs situés dans différentes régions.

**Set the current date**

```java
import java.util.Date;

msg.setDate(new Date());
```

**Apply a custom timezone offset (e.g., UTC+5)**

```java
msg.setTimeZoneOffset(5 * 60 * 60 * 1000); // 5 hours ahead of UTC in milliseconds.
```

Le décalage est exprimé en millisecondes, vous pouvez donc également fournir des valeurs négatives pour les zones à l’ouest de l’UTC.

### Feature 3: Saving a MailMessage as an MHTML File

#### Overview
MHTML regroupe le contenu HTML et les ressources intégrées dans un seul fichier, idéal pour l’archivage ou le partage.

**Configure save options**

```java
import com.aspose.email.MhtSaveOptions;
import com.aspose.email.MhtFormatOptions;

MhtSaveOptions mhtOptions = new MhtSaveOptions();
mhtOptions.setMhtFormatOptions(MhtFormatOptions.WriteHeader);
```

**Save the email**

```java
msg.save("YOUR_OUTPUT_DIRECTORY/ExportToMHTWithCustomTimezone_out.mhtml", mhtOptions);
```

Le fichier `.mhtml` résultant conserve le formatage original, les images et les pièces jointes.

## Why Convert MSG to MHTML?

Convertir les fichiers MSG en MHTML vous fournit une représentation web‑compatible, monofichier, qui peut être ouverte dans n’importe quel navigateur moderne. Cela est particulièrement utile pour :

- **Legal archiving** où une copie visuelle fidèle est requise.
- **Cross‑platform sharing** sans besoin d’Outlook.
- **Embedding emails** dans des pages web ou de la documentation.

## Batch Email Processing Tips

Si vous avez besoin de **batch email processing**, encapsulez les étapes de chargement, d’ajustement du fuseau horaire et d’enregistrement dans une boucle qui parcourt un répertoire de fichiers `.msg`. N’oubliez pas de :

1. Réutiliser une seule instance `License` pour éviter les surcharges.
2. Libérer les ressources après chaque itération (`msg.dispose()` si applicable).
3. Consigner les échecs dans un fichier séparé pour une révision ultérieure.

## Practical Applications

1. **Email Archiving** : Conservez les communications dans un format portable pour la conformité.
2. **Global Scheduling** : Ajustez les horodatages à un fuseau horaire unifié avant d’envoyer des notifications.
3. **CRM Integration** : Importez automatiquement les courriels archivés dans un système CRM sous forme de pièces jointes MHTML.

## Performance Considerations

- **Memory Management** : Traitez les gros lots par fragments afin de maintenir une faible consommation de mémoire.
- **I/O Optimization** : Utilisez des flux tamponnés si vous lisez/écrivez de nombreux fichiers.
- **Parallel Execution** : Envisagez le `ForkJoinPool` de Java pour le traitement parallèle, tout en garantissant la sécurité des objets Aspose.

## Conclusion

Vous savez maintenant **how to load msg** des fichiers, appliquer des décalages de fuseau horaire personnalisés, et **convert msg to mhtml** avec Aspose.Email pour Java. Ces techniques peuvent être mises à l’échelle pour gérer des tâches de **batch email processing**, vous offrant une solution robuste pour l’archivage, la migration et l’automatisation des courriels.

**Next Steps**  
Explorez d’autres fonctionnalités d’Aspose.Email telles que la gestion des pièces jointes, l’extraction d’éléments de calendrier ou l’envoi SMTP en visitant la [documentation](https://reference.aspose.com/email/java/) officielle.

## Frequently Asked Questions

**Q : Puis‑je charger des courriels à partir de formats autres que .msg ?**  
R : Oui, Aspose.Email prend en charge EML, MSG, MHT et plusieurs autres formats.

**Q : Comment gérer efficacement des fichiers de courriel très volumineux ?**  
R : Utilisez les API de streaming fournies par Aspose.Email pour lire/écrire les données par fragments, réduisant ainsi la pression sur la mémoire.

**Q : Est‑il possible de modifier les pièces jointes d’un MailMessage ?**  
R : Absolument. Vous pouvez ajouter, supprimer ou remplacer des pièces jointes via la collection `MailMessage.getAttachments()`.

**Q : Que faire si mon décalage de fuseau horaire est négatif (derrière l’UTC) ?**  
R : Passez une valeur négative en millisecondes à `setTimeZoneOffset`, par ex. `-3 * 60 * 60 * 1000` pour UTC‑3.

**Q : Puis‑je utiliser Aspose.Email dans des projets commerciaux ?**  
R : Oui, à condition de disposer d’une licence commerciale valide.

**Q : Comment traiter des milliers de fichiers MSG sans épuiser la mémoire ?**  
R : Traitez les fichiers par lots, libérez chaque `MailMessage` après l’enregistrement, et envisagez d’utiliser le modèle `try‑with‑resources` de Java pour un nettoyage automatique.

---

**Last Updated:** 2026-02-27  
**Tested With:** Aspose.Email for Java 25.4 (jdk16 classifier)  
**Author:** Aspose  

## Resources
- [Documentation](https://reference.aspose.com/email/java/)
- [Download Library](https://releases.aspose.com/email/java/)
- [Purchase License](https://purchase.aspose.com/buy)
- [Free Trial](https://releases.aspose.com/email/java/)
- [Temporary License](https://purchase.aspose.com/temporary-license/)
- [Support Forum](https://forum.aspose.com/c/email/10)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}