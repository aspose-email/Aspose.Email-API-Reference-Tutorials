---
"date": "2025-05-29"
"description": "Apprenez à gérer efficacement plusieurs propriétés dans les messages MAPI avec Aspose.Email pour Java. Ce guide couvre la définition des types float, double, long et autres."
"title": "Définir plusieurs propriétés MAPI en Java avec Aspose.Email - Un guide complet"
"url": "/fr/java/mapi-operations/aspose-email-java-set-mapi-properties/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Définir plusieurs propriétés MAPI en Java avec Aspose.Email : guide complet

## Introduction

Gérer efficacement les propriétés des messages MAPI est essentiel pour optimiser vos applications Java. Avec Aspose.Email pour Java, vous pouvez définir facilement plusieurs propriétés, telles que float, double, long, short, boolean et des propriétés personnalisées. Ce guide vous présente différentes méthodes pour y parvenir.

**Ce que vous apprendrez :**
- Définition de plusieurs propriétés dans les messages MAPI à l'aide d'Aspose.Email Java
- Comprendre les différents types de propriétés et leurs utilisations
- Exemples de code pratiques pour la mise en œuvre

Commençons par aborder les prérequis.

## Prérequis

Pour suivre, assurez-vous d'avoir :
- **Kit de développement Java (JDK) :** JDK 8 ou version ultérieure installé.
- **Bibliothèque de courrier électronique Aspose :** La version 25.4 est recommandée.
- **Configuration Maven :** Maven doit être configuré dans votre IDE pour la gestion des dépendances.

### Bibliothèques requises

Incluez Aspose.Email comme dépendance dans votre `pom.xml`:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Acquisition de licence
- **Essai gratuit :** Commencez par un essai gratuit pour explorer les fonctionnalités.
- **Licence temporaire :** Obtenez des tests prolongés sans limitations.
- **Achat:** Envisagez de l’acheter si cela répond à vos besoins.

## Configuration d'Aspose.Email pour Java

Assurez-vous qu'Aspose.Email est correctement configuré dans votre environnement de développement :
1. **Dépendances d'importation :** Résoudre les dépendances Maven.
2. **Définir la licence :**
   - Téléchargez un fichier de licence à partir de [Aspose](https://purchase.aspose.com/buy).
   - Appliquez-le en utilisant :
     ```java
     com.aspose.email.License license = new com.aspose.email.License();
     license.setLicense("path/to/your/license.lic");
     ```

Une fois la configuration terminée, explorons comment définir diverses propriétés.

## Guide de mise en œuvre

### Définition de plusieurs propriétés flottantes

La définition des propriétés flottantes permet un stockage efficace des données numériques :

#### Aperçu
Cette fonctionnalité illustre l’ajout de plusieurs valeurs flottantes en tant que propriétés de message MAPI à l’aide d’Aspose.Email pour Java.

#### Mesures
1. **Créer et initialiser le message**
   ```java
   import java.util.ArrayList;
   import com.aspose.email.MapiMessage;
   import com.aspose.email.MapiProperty;
   import com.aspose.email.system.collections.IList;

   MapiMessage msg = new MapiMessage();
   ```
2. **Ajouter des valeurs flottantes à une liste**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((float) 1);
   values.addItem((float) 2);
   ```
3. **Définir la propriété avec un identifiant unique**
   ```java
   msg.setProperty(new MapiProperty(0x23901004, values));
   ```
*Explication:* L'étiquette de propriété `0x23901004` identifie cet ensemble de propriétés flottantes.

### Définition de plusieurs propriétés doubles

Les propriétés doubles stockent des nombres à virgule flottante de haute précision :

#### Aperçu
Cette section montre le stockage de plusieurs valeurs doubles en tant que propriétés de message MAPI.

#### Mesures
1. **Initialiser le message**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Remplir les valeurs doubles**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((double) 1);
   values.addItem((double) 2);
   ```
3. **Affecter à la balise de propriété**
   ```java
   msg.setProperty(new MapiProperty(0x23901005, values));
   ```

### Définition de plusieurs propriétés APPTIME

Les propriétés APPTIME stockent efficacement les durées :

#### Aperçu
Cette fonctionnalité illustre l’utilisation de nombres à double précision pour les représentations temporelles.

#### Mesures
1. **Créer un objet de message**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Ajouter des valeurs de temps**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem(30456.34);
   values.addItem(40655.45);
   ```
3. **Définir la propriété**
   ```java
   msg.setProperty(new MapiProperty(0x23901007, values));
   ```

### Définition de plusieurs propriétés longues

Les propriétés longues sont idéales pour les grands entiers :

#### Aperçu
Cette fonctionnalité se concentre sur la définition de plusieurs valeurs entières longues dans un message.

#### Mesures
1. **Initialiser le message MAPI**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Ajouter des valeurs longues**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((long) 30456);
   values.addItem((long) 40655);
   ```
3. **Définir la balise de propriété**
   ```java
   msg.setProperty(new MapiProperty(0x23901014, values));
   ```

### Définition de plusieurs propriétés courtes

Les propriétés courtes stockent efficacement les données de petits entiers :

#### Aperçu
Ce guide montre comment définir des entiers courts comme propriétés de message.

#### Mesures
1. **Initialiser le message**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Ajouter des valeurs courtes**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((short) 1);
   values.addItem((short) 2);
   ```
3. **Attribuer une balise de propriété**
   ```java
   msg.setProperty(new MapiProperty(0x23901002, values));
   ```

### Définition de plusieurs propriétés booléennes

Les propriétés booléennes stockent les états vrai/faux :

#### Aperçu
Découvrez comment définir plusieurs valeurs booléennes dans un message.

#### Mesures
1. **Créer un objet de message**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Ajouter des valeurs booléennes**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem(true);
   values.addItem(false);
   ```
3. **Définir la propriété avec l'identifiant**
   ```java
   msg.setProperty(new MapiProperty(0x2390100b, values));
   ```

### Définition d'une propriété nulle

Définir explicitement une propriété comme nulle peut être utile :

#### Aperçu
Cette section montre comment attribuer une valeur nulle à une propriété.

#### Mesures
1. **Initialiser le message**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Attribuer une propriété nulle**
   ```java
   msg.setProperty(new MapiProperty(0x67400001, new byte[1]));
   ```

### Définition d'une propriété longue nommée avec un ID et un UUID personnalisés

Pour les scénarios complexes, définissez des propriétés nommées :

#### Aperçu
Cette fonctionnalité illustre la définition d’une propriété longue avec un identifiant personnalisé et un UUID.

#### Mesures
1. **Initialiser le message**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Ajouter des valeurs longues**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((int) 4);
   UUID uuid = UUID.randomUUID();
   ```
3. **Créer et mapper une propriété**
   ```java
   MapiProperty property = new MapiProperty(msg.getNamedPropertyMapping().getNextAvailablePropertyId(com.aspose.email.MapiPropertyType.PT_MV_LONG), values);
   msg.getNamedPropertyMapping().addNamedPropertyMapping(property, (long) 0x00008028, uuid);
   msg.setProperty(property);
   ```

### Définition d'une propriété personnalisée avec un nom

Les propriétés personnalisées peuvent être nommées pour une identification plus facile :

#### Aperçu
Ce guide montre comment définir des propriétés nommées personnalisées.

#### Mesures
1. **Initialiser l'objet Message**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Définir une propriété personnalisée**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem("Custom Value");
   UUID uuid = UUID.randomUUID();
   
   MapiProperty property = new MapiProperty(msg.getNamedPropertyMapping().getNextAvailablePropertyId(com.aspose.email.MapiPropertyType.PT_STRING), values);
   msg.getNamedPropertyMapping().addNamedPropertyMapping(property, "CustomName", uuid);
   ```

### Définition et validation des propriétés

Il est essentiel de s’assurer que les propriétés sont correctement définies :

#### Aperçu
Cette section couvre la définition et la validation de plusieurs propriétés dans les messages MAPI.

#### Mesures
1. **Définir la propriété**
   Suivez les exemples précédents pour définir une propriété.
2. **Valider la propriété**
   ```java
   if (msg.getProperties().containsKey(0x23901004)) {
       System.out.println("Property is set correctly.");
   } else {
       System.err.println("Property setting failed.");
   }
   ```

## Conclusion

Ce guide propose une approche complète de la gestion de plusieurs propriétés dans les messages MAPI avec Aspose.Email pour Java. En suivant ces étapes, vous pourrez stocker et gérer efficacement différents types de données dans vos applications.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}