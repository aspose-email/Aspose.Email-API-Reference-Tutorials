---
date: '2026-08-27'
description: Apprenez à charger des fichiers MSG et à les convertir en MHTML avec
  Aspose.Email for Java, y compris les paramètres de fuseau horaire personnalisés
  et des conseils de traitement d'e-mails par lots.
keywords:
- how to load msg
- Aspose.Email Java
- convert MSG to MHTML
- email timezone offset
lastmod: '2026-08-27'
og_description: Apprenez à charger des fichiers msg et à les exporter au format MHTML
  avec Aspose.Email for Java. Comprend la gestion des fuseaux horaires et des conseils
  de traitement par lots.
og_image_alt: Guide to loading MSG files and saving as MHTML with Aspose.Email for
  Java
og_title: Comment charger un msg et l'enregistrer au format MHTML avec Aspose.Email
  for Java
schemas:
- author: Aspose
  dateModified: '2026-08-27'
  description: Learn how to load MSG files and convert them to MHTML with Aspose.Email
    for Java, including custom timezone settings and batch email processing tips.
  headline: How to load msg and save as MHTML using Aspose.Email for Java
  type: TechArticle
- description: Learn how to load MSG files and convert them to MHTML with Aspose.Email
    for Java, including custom timezone settings and batch email processing tips.
  name: How to load msg and save as MHTML using Aspose.Email for Java
  steps:
  - name: '**Reuse the license** – call `new License().setLicense(...)` once at application
      startup.'
    text: '**Reuse the license** – call `new License().setLicense(...)` once at application
      startup.'
  - name: '**Use try‑with‑resources** for automatic cleanup of streams.'
    text: '**Use try‑with‑resources** for automatic cleanup of streams.'
  - name: '**Log failures** to a separate file so you can retry problematic messages
      later.'
    text: '**Log failures** to a separate file so you can retry problematic messages
      later.'
  - name: '**Consider parallelism** with `ForkJoinPool` for large batches, but ensure
      each thread uses its own `MailMessage` instance.'
    text: '**Consider parallelism** with `ForkJoinPool` for large batches, but ensure
      each thread uses its own `MailMessage` instance.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Email supports EML, MHT, EMLX, and several other formats,
      totaling over 30 input types.
    question: Can I load emails from formats other than .msg?
  - answer: Use the streaming APIs (`MailMessage.load(InputStream, ...)`) to read
      and write data in chunks, which keeps memory consumption under 50 MB even for
      500‑page messages.
    question: How can I handle very large email files efficiently?
  - answer: Absolutely. You can add, remove, or replace attachments via the `msg.getAttachments()`
      collection, then call `save` to persist changes.
    question: Is it possible to modify attachments within a MailMessage?
  - answer: Pass a negative millisecond value to `setTimeZoneOffset`, e.g., `-3 *
      60 * 60 * 1000` for UTC‑3.
    question: What if my timezone offset is negative (behind UTC)?
  - answer: Yes, provided you have a valid commercial license. The free trial is limited
      to 20 MB per document.
    question: Can I use Aspose.Email in commercial projects?
  type: FAQPage
tags:
- email processing
- Aspose.Email
- Java email conversion
title: Comment charger un fichier msg et l'enregistrer au format MHTML avec Aspose.Email
  for Java
url: /fr/java/email-message-operations/load-save-emails-mhtml-aspose-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment charger un msg et l’enregistrer en MHTML avec Aspose.Email pour Java

## Introduction

Si vous devez **how to load msg** des fichiers, ajuster leurs horodatages, puis **convert msg to mhtml**, vous êtes au bon endroit. Dans ce tutoriel, nous parcourrons le chargement d’un courriel `.msg`, l’application d’un décalage de fuseau horaire personnalisé, et l’enregistrement du résultat sous forme d’archive MHTML — le tout avec Aspose.Email pour Java. Que vous traitiez un seul message ou un pipeline de **batch email processing**, ces étapes vous fourniront une base solide pour une archivage fiable et une migration.

**Ce que vous apprendrez**
- Comment charger un `MailMessage` à partir d’un fichier `.msg`.
- Comment définir un fuseau horaire personnalisé et la date actuelle.
- Comment enregistrer le message en MHTML avec un formatage précis.
- Conseils pour faire évoluer l’approche vers des scénarios de traitement par lots.

Prêt à améliorer votre flux de travail d’e‑mail ? Préparons d’abord l’environnement.

## Réponses rapides
- **Quelle est la bibliothèque principale ?** Aspose.Email for Java.
- **Puis‑je charger un MSG et l’exporter en MHTML en une seule étape ?** Non, vous chargez, ajustez, puis enregistrez.
- **Ai‑je besoin d’une licence pour la production ?** Oui, une licence valide d’Aspose.Email est requise.
- **La gestion des fuseaux horaires est‑elle prise en charge ?** Oui, via `setTimeZoneOffset`.
- **Cette méthode peut‑elle être utilisée en traitement par lots ?** Absolument – encapsulez les étapes dans une boucle.

## Qu’est‑ce qu’Aspose.Email pour Java ?
Aspose.Email pour Java est une API complète qui vous permet de créer, lire, convertir et manipuler des messages électroniques sans nécessiter Microsoft Outlook. Elle prend en charge plus de 30 formats d’e‑mail et peut traiter des messages de plusieurs centaines de pages tout en maintenant une faible consommation de mémoire.

## Pourquoi convertir MSG en MHTML ?
Convertir des fichiers MSG en MHTML vous fournit une représentation web‑compatible, sous forme d’un seul fichier, qui peut être ouverte dans n’importe quel navigateur moderne. Ce format préserve le style original, les images intégrées et les pièces jointes, ce qui le rend idéal pour **legal archiving**, **cross‑platform sharing**, et **embedding emails into web pages or documentation**.

## Prérequis
Avant de commencer, assurez-vous de disposer de ce qui suit :

### Bibliothèques et dépendances requises
- Bibliothèque **Aspose.Email for Java** version 25.4 (classificateur jdk16) – la bibliothèque prend en charge **50+** formats d’e‑mail en entrée et sortie.
- Connaissances de base en Java.
- Un IDE tel qu’IntelliJ IDEA ou Eclipse.

### Exigences de configuration de l’environnement
- JDK 16 ou version ultérieure installé.
- Maven pour la gestion des dépendances.

## Configuration d’Aspose.Email pour Java
Pour ajouter la bibliothèque à un projet Maven, incluez la dépendance suivante :

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Étapes d’obtention de licence
Commencez avec un **free trial** ou obtenez une **temporary license** pour évaluer les capacités complètes de la bibliothèque sans limitations. Pour une utilisation à long terme, envisagez d’acheter une licence :

- [Essai gratuit](https://releases.aspose.com/email/java/)
- [Licence temporaire](https://purchase.aspose.com/temporary-license/)
- [Acheter une licence](https://purchase.aspose.com/buy)

### Initialisation de base
La classe `License` enregistre votre licence Aspose.Email pour débloquer toutes les fonctionnalités.  
Après avoir ajouté la dépendance, initialisez la licence dans votre code Java :

```java
import com.aspose.email.License;

License license = new License();
license.setLicense("Aspose.Email.lic");
```
```java
import com.aspose.email.License;

License license = new License();
license.setLicense("path_to_your_license_file.lic");
```

## Comment charger un msg et l’enregistrer en MHTML ?
Chargez le fichier MSG, ajustez l’horodatage, et enregistrez‑le en MHTML en trois étapes simples. Tout d’abord, créez une instance de `MailMessage` à partir du fichier MSG en utilisant `MsgLoadOptions`. Ensuite, définissez le décalage de fuseau horaire souhaité avec `setTimeZoneOffset`. Enfin, configurez `MhtSaveOptions` et appelez `save` pour produire l’archive MHTML.

### Fonctionnalité 1 : charger un MailMessage depuis un fichier
La classe `MailMessage` représente un message électronique avec en‑têtes, corps et pièces jointes.

```java
import com.aspose.email.MailMessage;
import com.aspose.email.MsgLoadOptions;
```
```java
import com.aspose.email.MailMessage;
import com.aspose.email.MsgLoadOptions;
```

```java
MsgLoadOptions loadOptions = new MsgLoadOptions();
MailMessage msg = MailMessage.load("sample.msg", loadOptions);
```
```java
String filename = "YOUR_DOCUMENT_DIRECTORY/MSG file with RTF Formatting.msg";
MailMessage msg = MailMessage.load(filename, new MsgLoadOptions());
```

`MsgLoadOptions` vous permet de contrôler la façon dont le fichier MSG est analysé ; les paramètres par défaut fonctionnent dans la plupart des scénarios.

### Fonctionnalité 2 : définir la date actuelle et le décalage de fuseau horaire personnalisé
L’objet `Date` contient l’horodatage qui sera écrit dans l’en‑tête **Date** du courriel.

```java
java.util.Date now = new java.util.Date();
msg.setDate(now);
```
```java
import java.util.Date;

msg.setDate(new Date());
```

Le décalage est exprimé en millisecondes ; pour UTC+5 vous passez `5 * 60 * 60 * 1000`.

```java
int utcPlusFive = 5 * 60 * 60 * 1000;
msg.setTimeZoneOffset(utcPlusFive);
```
```java
msg.setTimeZoneOffset(5 * 60 * 60 * 1000); // 5 hours ahead of UTC in milliseconds.
```

### Fonctionnalité 3 : enregistrer un MailMessage en fichier MHTML
`MhtSaveOptions` définit comment le courriel est empaqueté dans une archive MHTML, en préservant les images en ligne et les pièces jointes.

```java
import com.aspose.email.MhtSaveOptions;
MhtSaveOptions saveOptions = new MhtSaveOptions();
saveOptions.setWriteHeader(true);
```
```java
import com.aspose.email.MhtSaveOptions;
import com.aspose.email.MhtFormatOptions;

MhtSaveOptions mhtOptions = new MhtSaveOptions();
mhtOptions.setMhtFormatOptions(MhtFormatOptions.WriteHeader);
```

```java
msg.save("output.mhtml", saveOptions);
```
```java
msg.save("YOUR_OUTPUT_DIRECTORY/ExportToMHTWithCustomTimezone_out.mhtml", mhtOptions);
```

Le fichier `.mhtml` résultant conserve le formatage original, les images et les pièces jointes, ce qui en fait une copie visuelle fidèle du MSG d’origine.

## Comment définir un décalage de fuseau horaire personnalisé ?
Vous pouvez modifier le fuseau horaire en appelant `setTimeZoneOffset` sur l’instance `MailMessage`. La méthode attend un décalage en millisecondes, permettant des valeurs positives (est de l’UTC) et négatives (ouest de l’UTC). Par exemple, UTC‑3 correspond à `-3 * 60 * 60 * 1000`.

## Comment traiter des fichiers MSG par lots ?
Encapsulez le flux de travail en trois étapes dans une boucle qui parcourt un répertoire de fichiers `.msg`. Réutilisez une seule instance `License` pour éviter les I/O répétés, et libérez chaque `MailMessage` après l’enregistrement afin de maintenir une faible consommation de mémoire.

```java
File folder = new File("msg_folder");
for (File file : folder.listFiles((dir, name) -> name.toLowerCase().endsWith(".msg"))) {
    MailMessage msg = MailMessage.load(file.getAbsolutePath(), new MsgLoadOptions());
    // set date & timezone as shown earlier
    msg.save(file.getName().replace(".msg", ".mhtml"), new MhtSaveOptions());
    msg.dispose(); // releases native resources
}
```

### Conseils pour le traitement par lots
1. **Réutiliser la licence** – appelez `new License().setLicense(...)` une fois au démarrage de l’application.
2. **Utiliser try‑with‑resources** pour le nettoyage automatique des flux.
3. **Consigner les échecs** dans un fichier séparé afin de pouvoir retenter les messages problématiques plus tard.
4. **Envisager le parallélisme** avec `ForkJoinPool` pour les gros lots, mais assurez‑vous que chaque thread utilise sa propre instance `MailMessage`.

## Problèmes courants et solutions
- **Pics de mémoire avec des fichiers MSG volumineux** – activez le streaming en utilisant `MailMessage.load(InputStream, MsgLoadOptions)` et traitez le flux par morceaux.
- **Horodatages incorrects** – vérifiez que l’horloge du système est réglée sur UTC avant d’appliquer les décalages, ou passez explicitement une instance `java.util.Calendar`.
- **Pièces jointes manquantes dans le MHTML** – assurez‑vous que `MhtSaveOptions.setWriteHeader(true)` est activé ; cela intègre les pièces jointes comme ressources `cid:`.

## Questions fréquemment posées
**Q : Puis‑je charger des e‑mails à partir de formats autres que .msg ?**  
R : Oui, Aspose.Email prend en charge EML, MHT, EMLX, et plusieurs autres formats, totalisant plus de 30 types d’entrée.

**Q : Comment gérer efficacement des fichiers e‑mail très volumineux ?**  
R : Utilisez les API de streaming (`MailMessage.load(InputStream, ...)`) pour lire et écrire les données par morceaux, ce qui maintient la consommation de mémoire sous 50 Mo même pour des messages de 500 pages.

**Q : Est‑il possible de modifier les pièces jointes d’un MailMessage ?**  
R : Absolument. Vous pouvez ajouter, supprimer ou remplacer des pièces jointes via la collection `msg.getAttachments()`, puis appeler `save` pour enregistrer les modifications.

**Q : Que faire si mon décalage de fuseau horaire est négatif (en retard par rapport à UTC) ?**  
R : Passez une valeur négative en millisecondes à `setTimeZoneOffset`, par exemple `-3 * 60 * 60 * 1000` pour UTC‑3.

**Q : Puis‑je utiliser Aspose.Email dans des projets commerciaux ?**  
R : Oui, à condition de disposer d’une licence commerciale valide. L’essai gratuit est limité à 20 Mo par document.

**Q : Comment traiter des milliers de fichiers MSG sans épuiser la mémoire ?**  
R : Traitez les fichiers par lots, libérez chaque `MailMessage` après l’enregistrement, et utilisez le modèle `try‑with‑resources` de Java pour le nettoyage automatique.

## Ressources
- [documentation](https://reference.aspose.com/email/java/)
- [Documentation](https://reference.aspose.com/email/java/)
- [Télécharger la bibliothèque](https://releases.aspose.com/email/java/)
- [Acheter une licence](https://purchase.aspose.com/buy)
- [Essai gratuit](https://releases.aspose.com/email/java/)
- [Licence temporaire](https://purchase.aspose.com/temporary-license/)
- [Forum d’assistance](https://forum.aspose.com/c/email/10)

---

**Dernière mise à jour :** 2026-08-27  
**Testé avec :** Aspose.Email for Java 25.4 (classificateur jdk16)  
**Auteur :** Aspose

## Tutoriels associés

- [Comment charger et analyser les fichiers Outlook MSG avec Aspose.Email pour Java : guide complet](/email/java/mapi-operations/outlook-msg-aspose-email-java-guide/)
- [Maven Aspose.Email pour Java : enregistrer les e‑mails en fichiers MHT](/email/java/email-message-operations/save-emails-as-mht-using-aspose-email-java/)
- [Comment extraire les pièces jointes des fichiers msg avec Aspose.Email pour Java](/email/java/advanced-email-attachments/extracting-attachments-from-email-messages/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}