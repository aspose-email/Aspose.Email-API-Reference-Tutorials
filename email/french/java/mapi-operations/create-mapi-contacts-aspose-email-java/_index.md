---
"date": "2025-05-29"
"description": "Apprenez à créer et gérer efficacement vos contacts MAPI avec Aspose.Email pour Java. Ce guide couvre tous les aspects, de la création de contacts de base à la gestion détaillée, en passant par l'ajout d'informations professionnelles."
"title": "Créer des contacts MAPI en Java à l'aide d'Aspose.Email &#58; un guide étape par étape"
"url": "/fr/java/mapi-operations/create-mapi-contacts-aspose-email-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Comment créer des contacts MAPI en Java avec Aspose.Email : guide étape par étape

## Introduction

La gestion des contacts est essentielle pour les applications nécessitant une intégration robuste des e-mails et du carnet d'adresses. Ce guide complet explique comment créer des contacts MAPI (Messaging Application Programming Interface) à l'aide de la puissante bibliothèque Aspose.Email en Java. En suivant ce tutoriel, vous automatiserez la création de contacts, améliorerez l'organisation des données et intégrerez facilement la gestion des contacts à vos applications Java.

**Ce que vous apprendrez :**
- Créer des contacts MAPI de base et détaillés
- Gérez vos informations professionnelles, vos adresses et vos e-mails avec Aspose.Email pour Java
- Configurer un fichier PST (Personal Storage Table) pour stocker efficacement les contacts

## Prérequis

Avant de vous lancer dans la création de contacts, assurez-vous de disposer des éléments suivants :

### Bibliothèques requises :
- Bibliothèque Aspose.Email pour Java (version 25.4 ou ultérieure)

### Configuration requise pour l'environnement :
- JDK version 16 ou supérieure
- Un IDE de votre choix (IntelliJ IDEA, Eclipse, etc.)

### Prérequis en matière de connaissances :
Une compréhension de base de la programmation Java et une familiarité avec la gestion des bibliothèques tierces.

## Configuration d'Aspose.Email pour Java

Pour commencer, incluez la bibliothèque Aspose.Email dans votre projet. Si vous utilisez Maven, ajoutez la dépendance suivante à votre `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Étapes d'acquisition de la licence :
- **Essai gratuit :** Téléchargez une version d'essai à partir du [Site Web d'Aspose](https://releases.aspose.com/email/java/) pour explorer ses fonctionnalités.
- **Licence temporaire :** Demandez un permis temporaire via le [page d'achat](https://purchase.aspose.com/temporary-license/).
- **Achat:** Envisagez d'acheter une licence complète auprès de leur [page d'achat](https://purchase.aspose.com/buy) si Aspose.Email répond à vos besoins.

### Initialisation de base :
Une fois installé, initialisez Aspose.Email dans votre application Java pour commencer à créer et à gérer les contacts MAPI.

## Guide de mise en œuvre

Nous aborderons trois fonctionnalités principales : la création de contacts de base, l'inclusion d'informations professionnelles et la gestion complète des détails.

### Création d'un contact MAPI de base

#### Aperçu
Cette fonctionnalité vous permet de créer des contacts simples avec uniquement le prénom, le nom et l'adresse e-mail, adaptés aux applications nécessitant un minimum de données.

#### Étapes de mise en œuvre

##### Étape 1 : Importer les classes requises
```java
import com.aspose.email.MapiContact;
```

##### Étape 2 : Créer le contact MAPI
Voici comment créer un contact MAPI de base :
```java
public static MapiContact createBasicMapiContact(String firstName, String lastName, String emailAddress) {
    return new MapiContact(firstName + " " + lastName, emailAddress);
}
```
**Explication:** Cette méthode initialise un `MapiContact` Objet utilisant le nom et l'adresse e-mail fournis. Le contact est stocké avec un minimum d'informations.

### Création d'un contact MAPI avec des informations professionnelles

#### Aperçu
Améliorez vos contacts en ajoutant des détails professionnels tels que le nom de l'entreprise, le titre du poste et les numéros de téléphone.

#### Étapes de mise en œuvre

##### Étape 1 : Importer des classes supplémentaires
```java
import com.aspose.email.MapiContactNamePropertySet;
import com.aspose.email.MapiContactProfessionalPropertySet;
import com.aspose.email.MapiContactTelephonePropertySet;
```

##### Étape 2 : Créer le contact MAPI avec les informations professionnelles
Voici comment inclure des informations professionnelles :
```java
public static MapiContact createProfessionalMapiContact(String firstName, String middleName, String lastName,
        String company, String jobTitle, String businessPhone, String mobilePhone) {
    MapiContact contact = new MapiContact();
    contact.setNameInfo(new MapiContactNamePropertySet(firstName, middleName, lastName));
    contact.setProfessionalInfo(new MapiContactProfessionalPropertySet(company, jobTitle));
    contact.getTelephones().setBusinessTelephoneNumber(businessPhone);
    contact.getTelephones().setMobileTelephoneNumber(mobilePhone);
    return contact;
}
```
**Explication:** Cette méthode initialise un `MapiContact` Objet avec des détails étendus, notamment le nom de l'entreprise et l'intitulé du poste. Il définit également les numéros de téléphone professionnels.

### Création d'un contact MAPI avec des informations détaillées

#### Aperçu
Créez des contacts complets en ajoutant des adresses physiques, des informations de courrier électronique et des attributs de genre pour une gestion détaillée.

#### Étapes de mise en œuvre

##### Étape 1 : Importer des classes supplémentaires
```java
import com.aspose.email.MapiContactNamePropertySet;
import com.aspose.email.MapiContactProfessionalPropertySet;
import com.aspose.email.MapiContactTelephonePropertySet;
import com.aspose.email.MapiContactElectronicAddress;
import com.aspose.email.MapiContactGender;
```

##### Étape 2 : Créer un contact MAPI détaillé
Voici comment créer un contact détaillé :
```java
public static MapiContact createDetailedMapiContact(String firstName, String middleName, String lastName,
        MapiContactGender gender, String company, String jobTitle, String email, String workAddress) {
    MapiContact contact = new MapiContact();
    contact.setNameInfo(new MapiContactNamePropertySet(firstName, middleName, lastName));
    contact.getPersonalInfo().setGender(gender);
    contact.setProfessionalInfo(new MapiContactProfessionalPropertySet(company, jobTitle));
    contact.getPhysicalAddresses().getWorkAddress().setAddress(workAddress);
    contact.getElectronicAddresses().setEmail1(new MapiContactElectronicAddress(email));
    return contact;
}
```
**Explication:** Cette méthode initialise un `MapiContact` avec des informations détaillées, notamment le sexe et l'adresse physique. Cela garantit que toutes les données pertinentes sont saisies.

### Création d'un fichier PST et ajout de contacts

#### Aperçu
Stockez plusieurs contacts dans un fichier de table de stockage personnel (PST) pour une gestion centralisée.

#### Étapes de mise en œuvre

##### Étape 1 : Importer les classes requises
```java
import com.aspose.email.FileFormatVersion;
import com.aspose.email.FolderInfo;
import com.aspose.email.MapiContact;
import com.aspose.email.PersonalStorage;
import com.aspose.email.StandardIpmFolder;
```

##### Étape 2 : Créer un fichier PST et ajouter des contacts
Voici comment vous pouvez créer un fichier PST et ajouter des contacts :
```java
public static void createPstAndAddContacts(MapiContact[] contacts) {
    String pstPath = "YOUR_OUTPUT_DIRECTORY/MapiContactToPST_out.pst";
    PersonalStorage pst = PersonalStorage.create(pstPath, FileFormatVersion.Unicode);
    FolderInfo contactFolder = pst.createPredefinedFolder("Contacts", StandardIpmFolder.Contacts);
    for (MapiContact contact : contacts) {
        contactFolder.addMapiMessageItem(contact);
    }
}
```
**Explication:** Cette méthode crée un fichier PST et ajoute plusieurs `MapiContact` objets dedans, en les organisant sous un dossier « Contacts ».

## Applications pratiques

1. **Systèmes CRM :** Automatisez la création de contacts dans un logiciel de gestion de la relation client.
2. **Clients de messagerie :** Améliorez les clients de messagerie en intégrant des fonctionnalités robustes de gestion des contacts.
3. **Synchronisation du carnet d'adresses :** Utilisez cette fonctionnalité pour synchroniser les contacts sur différentes plates-formes et appareils.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}