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

Si vous avez besoin de **how toload msg** des fichiers, d'ajuster leurs horodatages, puis de **convert msg to mhtml**, vous êtes au bon endroit. Dans ce tutoriel, nous allons parcourir le chargement d’un courriel `.msg`, appliquer un décalage de fuseau horaire personnalisé, et enregistrer le résultat sous forme d’archive MHTML — le tout avec Aspose.Email pour Java. Que vous manipuliez un seul message ou un pipeline de **batch email Processing**, ces étapes vous fourniront une base solide.

**Ce que vous allez apprendre**
- Commenter charger un `MailMessage` à partir d'un fichier `.msg`.
- Comment définir un fuseau horaire personnalisé et la date actuelle.
- Comment enregistrer le message en MHTML avec un formatage précis.
- Astuces pour faire évoluer l’approche vers des scénarios de traitement par lots.

Prêt à optimiser votre flux de travail email ? Préparons d’abord l’environnement.

## Réponses rapides
- **Quelle est la bibliothèque principale ?** Aspose.Email pour Java.

- **Puis-je charger un fichier MSG et l’exporter en MHTML en une seule étape ?** Non, vous chargez, ajustez, puis enregistrez.

- **Ai-je besoin d’une licence pour la production ?** Oui, une licence Aspose.Email valide est requise.

- **La gestion des fuseaux horaires est-elle prise en charge ?** Oui, via `setTimeZoneOffset`.

- **Peut-on utiliser ceci en traitement par lots ?** Absolument : il suffit d’encapsuler les étapes dans une boucle.

## Prérequis

Avant de commencer, assurez-vous de disposer de ce qui suit :

### Bibliothèques et dépendances requises

- Bibliothèque **Aspose.Email pour Java** version 25.4 (classificateur jdk16)

- Connaissances de base en Java.

- Un IDE tel qu'IntelliJ IDEA ou Eclipse.

### Exigences de configuration de l'environnement
- JDK16ou une version plus récente installée.
- Maven pour la gestion des dépendances.

## Configuration d'Aspose.Email pour Java

Pour ajouter la bibliothèque à un projet Maven, incluez la dépendance suivante :

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Étapes d'acquisition de licence

Commencez avec un **essai gratuit** ou obtenez une **licence temporaire** afin d’évaluer les capacités complètes de la bibliothèque sans limitations. Pour une utilisation à long terme, envisagez d’acheter une licence :

- [Essai gratuit](https://releases.aspose.com/email/java/)
- [Licence temporaire](https://purchase.aspose.com/temporary-license/)
- [Acheter une licence](https://purchase.aspose.com/buy)

### Initialisation de base

Après avoir ajouté la dépendance, initialisez la licence dans votre code Java :

```java
import com.aspose.email.License;

License license = new License();
license.setLicense("path_to_your_license_file.lic");
```

## Guide d'implémentation

Nous allons décomposer l'implémentation en trois fonctionnalités distinctes.

### Fonctionnalité 1 : Chargement d'un MailMessage à partir d'un fichier

#### Aperçu
Le chargement d'un fichier `.msg` vous donne un accès complet par programmation au contenu, aux pièces jointes et aux métadonnées de l'e-mail.

#### Étape par étape

**Importer les classes requises**

```java
import com.aspose.email.MailMessage;
import com.aspose.email.MsgLoadOptions;
```

**Charger l'e-mail**

```java
String filename = "YOUR_DOCUMENT_DIRECTORY/MSG file with RTF Formatting.msg";
MailMessage msg = MailMessage.load(filename, new MsgLoadOptions());
```

`MsgLoadOptions` vous permet de contrôler l'interprétation du fichier MSG ; les paramètres par défaut conviennent à la plupart des cas.

### Fonctionnalité 2 : Définition de la date actuelle et d'un décalage horaire personnalisé

#### Aperçu
Des horodatages précis sont essentiels lorsque vous interagissez avec des utilisateurs situés dans différentes régions.

**Définir la date actuelle**

```java
import java.util.Date;

msg.setDate(new Date());
```

**Appliquer un décalage horaire personnalisé (par exemple, UTC+5)**

```java
msg.setTimeZoneOffset(5 * 60 * 60 * 1000); // 5 hours ahead of UTC in milliseconds.
```

Le décalage est exprimé en millisecondes ; vous pouvez donc également indiquer des valeurs négatives pour les fuseaux horaires situés à l'ouest de UTC.

### Fonctionnalité 3 : Enregistrer un message au format MHTML

#### Présentation
Le format MHTML regroupe le contenu HTML et les ressources intégrées dans un seul fichier, idéal pour l’archivage et le partage.

**Configurer les options d’enregistrement**

```java
import com.aspose.email.MhtSaveOptions;
import com.aspose.email.MhtFormatOptions;

MhtSaveOptions mhtOptions = new MhtSaveOptions();
mhtOptions.setMhtFormatOptions(MhtFormatOptions.WriteHeader);
```

**Enregistrer l’e-mail**

```java
msg.save("YOUR_OUTPUT_DIRECTORY/ExportToMHTWithCustomTimezone_out.mhtml", mhtOptions);
```

Le fichier `.mhtml` résultant conserve le formatage original, les images et les pièces jointes.

## Pourquoi convertir MSG en MHTML ?

Convertir les fichiers MSG en MHTML vous fournit une représentation web‑compatible, monofichier, qui peut être ouverte dans n’importe quel navigateur moderne. Cela est particulièrement utile pour :

- **Archivage légal** où une copie visuelle fidèle est requise.
- **Partage multiplateforme** sans besoin d'Outlook.
- **Embedding emails** dans des pages web ou de la documentation.

## Conseils pour le traitement des e-mails par lots

Si vous avez besoin de **batch email Processing**, encapsulez les étapes de chargement, d'ajustement du fuseau horaire et d'enregistrement dans une boucle qui parcourt un répertoire de fichiers `.msg`. N'oubliez pas de:

1. Réutilisez une seule instance `License` pour éviter les surcharges.
2. Libérer les ressources après chaque itération (`msg.dispose()` si applicable).
3. Consigner les échecs dans un fichier séparé pour une révision ultérieure.

## Applications pratiques

1. **Email Archiving** : Conservez les communications dans un format portable pour la conformité.
2. **Global Scheduling** : Ajustez les horaires à un fuseau horaire unifié avant d'envoyer des notifications.
3. **Intégration CRM** : Importez automatiquement les courriels archivés dans un système CRM sous forme de pièces jointes MHTML.

## Considérations sur les performances

- **Memory Management** : Traitez les gros lots par fragments afin de maintenir une faible consommation de mémoire.
- **Optimisation des E/S** : Utilisez des flux tamponnés si vous lisez/écrivez de nombreux fichiers.
- **Parallel Execution** : Envisagez le `ForkJoinPool` de Java pour le traitement parallèle, tout en garantissant la sécurité des objets Aspose.

## Conclusion

Vous savez maintenant **comment charger des msg** des fichiers, appliquer des décalages de fuseau horaire personnalisés, et **convertir msg en mhtml** avec Aspose.Email pour Java. Ces techniques peuvent être mises à l’échelle pour gérer les tâches de **batch email Processing**, vous offrant une solution robuste pour l’archivage, la migration et l’automatisation des courriels.

**Prochaines étapes**
Explorez d’autres fonctionnalités d’Aspose.Email telles que la gestion des pièces jointes, l’extraction d’éléments de calendrier ou l’envoi SMTP en visitant la [documentation](https://reference.aspose.com/email/java/) officielle.

## Questions fréquemment posées

**Q : Puis‑je charger des courriels à partir de formats autres que .msg?**
R : Oui, Aspose.Email prend en charge EML, MSG, MHT et plusieurs autres formats.

**Q : Comment gérer efficacement les fichiers de courriels très volumineux ?**
R : Utilisez les API de streaming fournies par Aspose.Email pour lire/écrire les données par fragments, notamment la pression sur la mémoire.

**Q : Est-il possible de modifier les pièces jointes d'un MailMessage ?**
R : Absolument. Vous pouvez ajouter, supprimer ou remplacer des pièces jointes via la collection `MailMessage.getAttachments()`.

**Q : Que faire si mon décalage de fuseau horaire est négatif (derrière l’UTC) ?**
R : Passez une valeur négative en millisecondes à `setTimeZoneOffset`, par ex. `-3 * 60 * 60 * 1000` pour UTC‑3.

**Q : Puis‑je utiliser Aspose.Email dans des projets commerciaux ?**
R : Oui, à condition de disposer d’une licence commerciale valide.

**Q : Comment traiter des milliers de fichiers MSG sans épuiser la mémoire ?**
R : Traitez les fichiers par lots, libérez chaque `MailMessage` après l'enregistrement, et envisagez d'utiliser le modèle `try‑with‑resources` de Java pour un nettoyage automatique.

## Ressources

- [Documentation](https://reference.aspose.com/email/java/)
- [Télécharger la bibliothèque](https://releases.aspose.com/email/java/)
- [Acheter une licence](https://purchase.aspose.com/buy)
- [Version d'essai gratuite](https://releases.aspose.com/email/java/)
- [Licence temporaire](https://purchase.aspose.com/temporary-license/)
- [Forum d'assistance](https://forum.aspose.com/c/email/10)

---

**Dernière mise à jour :** 27/02/2026
**Testé avec :** Aspose.Email pour Java 25.4 (classificateur JDK 16)
**Auteur :** Aspose 

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}