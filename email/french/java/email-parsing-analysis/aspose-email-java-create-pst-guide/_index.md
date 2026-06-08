---
date: '2026-06-08'
description: Apprenez à créer des fichiers PST avec Aspose.Email for Java, y compris
  comment ajouter des structures de dossiers et comment rechercher efficacement le
  contenu d'un PST. Guide étape par étape.
keywords:
- how to create pst
- how to add folder
- how to search pst
schemas:
- author: Aspose
  dateModified: '2026-06-08'
  description: Learn how to create PST files with Aspose.Email for Java, including
    how to add folder structures and how to search PST content efficiently. Step‑by‑step
    guide.
  headline: How to Create PST Files with Aspose.Email for Java
  type: TechArticle
- description: Learn how to create PST files with Aspose.Email for Java, including
    how to add folder structures and how to search PST content efficiently. Step‑by‑step
    guide.
  name: How to Create PST Files with Aspose.Email for Java
  steps:
  - name: Add Maven Dependency
    text: Add the Aspose.Email Maven dependency to your `pom.xml`. This pulls in all
      required binaries automatically.
  - name: Acquire and Apply a License
    text: A free trial is available, but a permanent license removes evaluation limits
      and enables full‑speed processing.
  - name: Initialize PersonalStorage
    text: The `PersonalStorage` class is Aspose.Email's top‑level object that represents
      a single PST file in memory. After instantiation, all read and write operations
      flow through this object.
  - name: Define Directory Paths
    text: Set source and destination paths for your email files and the PST output
      location.
  - name: Create the PST File
    text: Use `PersonalStorage.create()` with `FileFormatVersion.Unicode` to produce
      a modern Unicode PST that supports large folders and Unicode characters.
  - name: Build Search Query
    text: Construct a query that looks for a keyword in the subject or body, ignoring
      case.
  - name: Execute Query and Retrieve Messages
    text: Run the query on the target folder and iterate over the resulting `MapiMessage`
      collection.
  - name: Initialize PersonalStorage Object
    text: Assume `PersonalStorage` object (`pst`) is already created as shown previously.
  - name: Add to PST Folder
    text: 'Convert `MailMessage` to `MapiMessage` and add it:'
  type: HowTo
- questions:
  - answer: JDK 16 or higher is recommended for full compatibility with Aspose.Email
      for Java.
    question: What is the minimum Java version required?
  - answer: Yes, a trial mode is available but limits PST size to **10 MB** and disables
      certain optimizations.
    question: Can I use Aspose.Email without a license?
  - answer: Process messages in batches, dispose of `MapiMessage` objects promptly,
      and enable lazy loading via `PersonalStorage.setUseUnicode(true)`.
    question: How do I handle large PST files efficiently?
  - answer: Absolutely. When converting `MailMessage` to `MapiMessage`, call `mapiMsg.getAttachments().add(attachment)`
      to embed files.
    question: Is it possible to add attachments to emails in PST files?
  - answer: Aspose offers a dedicated support forum, detailed documentation, and email
      support for licensed customers.
    question: What kind of support is available for troubleshooting issues?
  type: FAQPage
title: Comment créer des fichiers PST avec Aspose.Email for Java
url: /fr/java/email-parsing-analysis/aspose-email-java-create-pst-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Maîtriser la gestion des e‑mails avec Aspose.Email pour Java

Si vous avez besoin de **how to create pst** fichiers de manière programmatique, vous êtes au bon endroit. Dans ce tutoriel, nous passerons en revue chaque étape nécessaire pour générer un fichier PST Unicode, ajouter les dossiers Outlook standard, importer des messages et effectuer des recherches insensibles à la casse — le tout en utilisant Aspose.Email pour Java. À la fin, vous disposerez d’un modèle de code réutilisable qui passe de quelques e‑mails à des archives de plusieurs gigaoctets.

## Réponses rapides
- **Comment commencer ?** Ajoutez la dépendance Maven Aspose.Email, obtenez une licence et instanciez `PersonalStorage`.
- **Puis-je ajouter un dossier Boîte de réception ?** Oui – appelez `pst.getRootFolder().addSubFolder("Inbox")`.
- **La recherche insensible à la casse est‑elle prise en charge ?** Utilisez `PersonalStorageQueryBuilder` avec `StringComparison.OrdinalIgnoreCase`.
- **Quelle taille de fichier peut être gérée ?** Aspose.Email traite les fichiers PST jusqu’à 2 Go sans charger le fichier complet en mémoire.
- **Ai‑je besoin d’une licence payante pour la production ?** Une licence permanente supprime les limites d’évaluation et débloque toutes les fonctionnalités de performance.

## Qu’est‑ce que how to create pst ?
**how to create pst** désigne le processus programmatique de génération d’un fichier Outlook Personal Storage Table (PST) à l’aide de code plutôt que de l’interface Outlook. Aspose.Email pour Java fournit une API entièrement gérée qui crée des fichiers PST Unicode, ajoute des dossiers et stocke des objets `MapiMessage` sans nécessiter l’installation d’Outlook.

## Pourquoi utiliser Aspose.Email pour la création de PST ?
Aspose.Email prend en charge **plus de 50** formats liés aux e‑mails (MSG, EML, MBOX, PST, etc.) et peut traiter des fichiers PST d’une taille **jusqu’à 2 Go** tout en maintenant l’utilisation de la mémoire en dessous de **150 Mo** grâce à son architecture à chargement paresseux. Cette capacité quantifiée le rend idéal pour les scénarios d’archivage d’entreprise, de migration et de conformité.

## Prérequis
- **Java Development Kit (JDK)** – version 16 ou ultérieure.
- **Maven** – pour la gestion des dépendances.
- Familiarité de base avec la syntaxe Java ; aucune expérience préalable des fichiers PST n’est requise.

## Comment créer un fichier PST ?
La classe `PersonalStorage` représente un fichier PST et fournit des méthodes pour créer, ouvrir et manipuler son contenu. Pour créer un nouveau PST Unicode, appelez `PersonalStorage.create()` avec le chemin de fichier souhaité et la version du format. Cette opération génère un PST moderne qui prend en charge les dossiers volumineux, les caractères Unicode et le streaming efficace, le rendant adapté tant aux tâches d’archivage à petite échelle qu’aux besoins d’entreprise.

### Étape 1 : Ajouter la dépendance Maven
Ajoutez la dépendance Maven Aspose.Email à votre `pom.xml`. Cela récupère automatiquement tous les binaires requis.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Étape 2 : Obtenir et appliquer une licence
Une version d’essai gratuite est disponible, mais une licence permanente supprime les limites d’évaluation et permet un traitement à pleine vitesse.

```java
import com.aspose.email.*;

public class AsposeEmailSetup {
    public static void main(String[] args) {
        // Set up license if available
        License license = new License();
        try {
            license.setLicense("path/to/your/license.lic");
        } catch (Exception e) {
            System.out.println("License not found, proceeding with trial version.");
        }

        System.out.println("Aspose.Email for Java is ready to use!");
    }
}
```

## Comment ajouter un dossier à un PST ?
Créez la hiérarchie de dossiers souhaitée sous la racine du PST, puis référez‑vous à celle‑ci lors de l’insertion de messages. L’objet `FolderInfo` représente chaque dossier et peut être imbriqué de manière arbitraire, vous permettant de construire des structures telles que Boîte de réception, Éléments envoyés ou dossiers de projet personnalisés. L’ajout de dossiers est une opération légère qui ne charge pas le contenu des messages, préservant les performances même pour les PST volumineux.

### Étape 1 : Initialiser PersonalStorage
La classe `PersonalStorage` est l’objet de niveau supérieur d’Aspose.Email qui représente un seul fichier PST en mémoire. Après instanciation, toutes les opérations de lecture et d’écriture passent par cet objet.

```java
import com.aspose.email.FileFormatVersion;
import com.aspose.email.PersonalStorage;
```

### Étape 2 : Définir les chemins de répertoires
Définissez les chemins source et destination pour vos fichiers e‑mail et l’emplacement de sortie du PST.

```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY";
String outputDir = "YOUR_OUTPUT_DIRECTORY";
```

### Étape 3 : Créer le fichier PST
Utilisez `PersonalStorage.create()` avec `FileFormatVersion.Unicode` pour produire un PST Unicode moderne qui prend en charge les dossiers volumineux et les caractères Unicode.

```java
try {
    PersonalStorage pst = PersonalStorage.create(outputDir + "NewPSTFile_out.pst", FileFormatVersion.Unicode);

    // Perform operations here.
} finally {
    if (pst != null)
        pst.dispose();
}
```

## Comment rechercher dans un pst ?
`PersonalStorageQueryBuilder` est une classe de construction utilisée pour créer des requêtes de recherche dans le contenu d’un PST. En configurant le builder avec les critères souhaités et en spécifiant `StringComparison.OrdinalIgnoreCase`, vous pouvez effectuer des recherches rapides et insensibles à la casse sur les sujets, les corps et les propriétés personnalisées sans charger le PST complet en mémoire.

### Étape 1 : Construire la requête de recherche
Construisez une requête qui recherche un mot‑clé dans le sujet ou le corps, en ignorant la casse.

```java
import com.aspose.email.MailQueryBuilder;
import com.aspose.email.MailQuery;
import com.aspose.email.MessageInfoCollection;

MailQueryBuilder builder = new MailQueryBuilder();
builder.getFrom().contains("automated", true);
```

### Étape 2 : Exécuter la requête et récupérer les messages
Exécutez la requête sur le dossier cible et parcourez la collection `MapiMessage` résultante.

```java
try {
    MailQuery query = builder.getQuery();
    MessageInfoCollection coll = fi.getContents(query);

    // Process results as needed.
} finally {
    if (pst != null)
        pst.dispose();
}
```

## Création d’un dossier prédéfini dans le PST
L’ajout d’un dossier prédéfini tel que **Inbox** aide à organiser efficacement vos données e‑mail.

### Étape 1 : Initialiser l’objet PersonalStorage
Supposons que l’objet `PersonalStorage` (`pst`) soit déjà créé comme indiqué précédemment.

### Étape 2 : Créer le dossier 'Inbox'
```java
try {
    FolderInfo fi = pst.createPredefinedFolder("Inbox", StandardIpmFolder.Inbox);
} finally {
    if (pst != null)
        pst.dispose();
}
```

## Ajout de messages à un dossier PST
Remplissez votre dossier PST avec des messages e‑mail en les chargeant depuis des fichiers et en les convertissant.

### Étape 1 : Charger le message e‑mail
```java
import com.aspose.email.MailMessage;
import com.aspose.email.MapiMessage;

MailMessage mailMessage = MailMessage.load(dataDir + "message.msg");
```

### Étape 2 : Ajouter au dossier PST
Convertissez `MailMessage` en `MapiMessage` et ajoutez‑le :

```java
try {
    fi.addMessage(MapiMessage.fromMailMessage(mailMessage));
} finally {
    if (pst != null)
        pst.dispose();
}
```

## Applications pratiques
Aspose.Email pour Java n’est pas seulement destiné à créer des fichiers PST ; c’est un outil polyvalent avec de nombreuses applications :
- **Archivage d’e‑mail** : Automatisez l’archivage des e‑mails d’entreprise dans des fichiers PST, en prenant en charge les politiques de conservation jusqu’à 10 ans.
- **Outils de migration** : Migrez sans effort des magasins de messagerie hérités (p. ex., MBOX) vers Outlook PST avec un appel API unique par message.
- **Analyse de données** : Extrayez les métadonnées telles que l’expéditeur, le destinataire et les horodatages pour les pipelines d’intelligence d’affaires.
- **Solutions de sauvegarde** : Créez des utilitaires de sauvegarde robustes qui stockent les changements d’e‑mail incrémentiels sans retraiter l’ensemble de la boîte aux lettres.

## Considérations de performance
Pour garantir des performances optimales lors de l’utilisation d’Aspose.Email :
- **Gestion des ressources** : Appelez toujours `pst.dispose()` ou utilisez try‑with‑resources pour libérer rapidement les handles natifs.
- **Traitement par lots** : Traitez les e‑mails par lots de **500** éléments afin de garder une utilisation de la mémoire prévisible.
- **Gestion de la concurrence** : La bibliothèque est thread‑safe pour les opérations en lecture seule ; pour les écritures, synchronisez l’accès à l’instance `PersonalStorage`.

## Problèmes courants et solutions
| Issue | Cause | Solution |
|-------|-------|----------|
| **OutOfMemoryError** lors du traitement de gros PST | Chargement du PST complet en mémoire | Activez `PersonalStorage.setUseUnicode(true)` et traitez les messages en flux. |
| Erreur **Folder not found** | Casse du chemin du dossier incorrecte | Utilisez `StringComparison.OrdinalIgnoreCase` dans les requêtes ou normalisez les noms de dossiers. |
| **License not applied** | Fichier de licence non chargé avant le premier appel API | Chargez la licence au démarrage de l’application, avant de créer tout objet `PersonalStorage`. |

## Questions fréquemment posées
**Q : Quelle est la version minimale de Java requise ?**  
R : JDK 16 ou supérieur est recommandé pour une compatibilité complète avec Aspose.Email pour Java.

**Q : Puis‑je utiliser Aspose.Email sans licence ?**  
R : Oui, un mode d’essai est disponible mais limite la taille du PST à **10 Mo** et désactive certaines optimisations.

**Q : Comment gérer efficacement les gros fichiers PST ?**  
R : Traitez les messages par lots, libérez rapidement les objets `MapiMessage`, et activez le chargement paresseux via `PersonalStorage.setUseUnicode(true)`.

**Q : Est‑il possible d’ajouter des pièces jointes aux e‑mails dans les fichiers PST ?**  
R : Absolument. Lors de la conversion de `MailMessage` en `MapiMessage`, appelez `mapiMsg.getAttachments().add(attachment)` pour intégrer les fichiers.

**Q : Quel type de support est disponible pour résoudre les problèmes ?**  
R : Aspose propose un forum de support dédié, une documentation détaillée et un support par e‑mail pour les clients sous licence.

## Ressources
- [Documentation](https://reference.aspose.com/email/java/)
- [Téléchargement](https://releases.aspose.com/email/java/)
- [Achat](https://purchase.aspose.com/buy)
- [Essai gratuit](https://releases.aspose.com/email/java/)
- [Licence temporaire](https://purchase.aspose.com/temporary-license/)
- [Forum de support](https://forum.aspose.com/c/email/10)

---

**Dernière mise à jour :** 2026-06-08  
**Testé avec :** Aspose.Email for Java 24.10  
**Auteur :** Aspose

## Tutoriels associés
- [Comment créer et gérer des fichiers Outlook PST à l’aide d’Aspose.Email pour Java](/email/java/outlook-pst-ost-operations/aspose-email-java-manage-pst-files/)
- [Manipuler les fichiers PST avec Aspose.Email pour Java : guide complet](/email/java/outlook-pst-ost-operations/manipulate-pst-files-aspose-email-java/)
- [Extraire les pièces jointes d’e‑mail Java – Utiliser Aspose.Email pour les fichiers PST – Guide étape par étape](/email/java/attachments-handling/extract-email-attachments-pst-aspose-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}