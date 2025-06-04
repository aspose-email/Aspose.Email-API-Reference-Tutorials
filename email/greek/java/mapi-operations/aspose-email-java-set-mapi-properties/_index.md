---
"date": "2025-05-29"
"description": "Μάθετε πώς να διαχειρίζεστε αποτελεσματικά πολλαπλές ιδιότητες σε μηνύματα MAPI χρησιμοποιώντας το Aspose.Email για Java. Αυτός ο οδηγός καλύπτει τη ρύθμιση τύπων float, double, long και άλλων."
"title": "Ορισμός πολλαπλών ιδιοτήτων MAPI σε Java με το Aspose.Email® Ένας πλήρης οδηγός"
"url": "/el/java/mapi-operations/aspose-email-java-set-mapi-properties/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Ορισμός πολλαπλών ιδιοτήτων MAPI σε Java με το Aspose.Email: Ένας πλήρης οδηγός

## Εισαγωγή

Η αποτελεσματική διαχείριση των ιδιοτήτων μηνυμάτων MAPI είναι ζωτικής σημασίας για τη βελτίωση των εφαρμογών Java σας. Με το Aspose.Email για Java, μπορείτε να ορίσετε πολλές ιδιότητες όπως float, double, long, short, boolean και προσαρμοσμένες ιδιότητες απρόσκοπτα. Αυτός ο οδηγός θα σας καθοδηγήσει σε διάφορες μεθόδους για να το πετύχετε αυτό.

**Τι θα μάθετε:**
- Ορισμός πολλαπλών ιδιοτήτων σε μηνύματα MAPI χρησιμοποιώντας το Aspose.Email Java
- Κατανόηση διαφορετικών τύπων ακινήτων και των χρήσεών τους
- Πρακτικά παραδείγματα κώδικα για υλοποίηση

Ας ξεκινήσουμε καλύπτοντας τις προαπαιτούμενες προϋποθέσεις.

## Προαπαιτούμενα

Για να παρακολουθήσετε, βεβαιωθείτε ότι έχετε:
- **Κιτ ανάπτυξης Java (JDK):** Εγκατεστημένο JDK 8 ή νεότερη έκδοση.
- **Βιβλιοθήκη Aspose.Email:** Συνιστάται η έκδοση 25.4.
- **Ρύθμιση Maven:** Το Maven θα πρέπει να ρυθμιστεί στο IDE σας για διαχείριση εξαρτήσεων.

### Απαιτούμενες βιβλιοθήκες

Συμπεριλάβετε το Aspose.Email ως εξάρτηση στο `pom.xml`:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Απόκτηση Άδειας
- **Δωρεάν δοκιμή:** Ξεκινήστε με μια δωρεάν δοκιμή για να εξερευνήσετε τις λειτουργίες.
- **Προσωρινή Άδεια:** Λάβετε εκτεταμένες δοκιμές χωρίς περιορισμούς.
- **Αγορά:** Σκεφτείτε να το αγοράσετε αν ταιριάζει στις ανάγκες σας.

## Ρύθμιση του Aspose.Email για Java

Βεβαιωθείτε ότι το Aspose.Email έχει ρυθμιστεί σωστά στο περιβάλλον ανάπτυξής σας:
1. **Εξαρτήσεις εισαγωγής:** Επίλυση εξαρτήσεων Maven.
2. **Ορισμός άδειας χρήσης:**
   - Λήψη αρχείου άδειας χρήσης από [Άσποζε](https://purchase.aspose.com/buy).
   - Εφαρμόστε το χρησιμοποιώντας:
     ```java
     com.aspose.email.License license = new com.aspose.email.License();
     license.setLicense("path/to/your/license.lic");
     ```

Αφού ολοκληρώσουμε τη ρύθμιση, ας εξερευνήσουμε πώς να ορίσουμε διάφορες ιδιότητες.

## Οδηγός Εφαρμογής

### Ορισμός πολλαπλών ιδιοτήτων κινητής υποδιαστολής

Ο ορισμός των ιδιοτήτων float επιτρέπει την αποτελεσματική αποθήκευση αριθμητικών δεδομένων:

#### Επισκόπηση
Αυτή η λειτουργία επιδεικνύει την προσθήκη πολλαπλών τιμών κινητής υποδιαστολής ως ιδιότητες μηνύματος MAPI χρησιμοποιώντας το Aspose.Email για Java.

#### Βήματα
1. **Δημιουργία και αρχικοποίηση του μηνύματος**
   ```java
   import java.util.ArrayList;
   import com.aspose.email.MapiMessage;
   import com.aspose.email.MapiProperty;
   import com.aspose.email.system.collections.IList;

   MapiMessage msg = new MapiMessage();
   ```
2. **Προσθήκη τιμών κινητής υποδιαστολής σε μια λίστα**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((float) 1);
   values.addItem((float) 2);
   ```
3. **Ορισμός της ιδιότητας με ένα μοναδικό αναγνωριστικό**
   ```java
   msg.setProperty(new MapiProperty(0x23901004, values));
   ```
*Εξήγηση:* Η ετικέτα ιδιότητας `0x23901004` προσδιορίζει αυτό το σύνολο ιδιοτήτων κινητής υποδιαστολής.

### Ορισμός πολλαπλών διπλών ιδιοτήτων

Οι διπλές ιδιότητες αποθηκεύουν αριθμούς κινητής υποδιαστολής υψηλής ακρίβειας:

#### Επισκόπηση
Αυτή η ενότητα δείχνει την αποθήκευση πολλαπλών διπλών τιμών ως ιδιότητες μηνύματος MAPI.

#### Βήματα
1. **Αρχικοποίηση του μηνύματος**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Συμπλήρωση διπλών τιμών**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((double) 1);
   values.addItem((double) 2);
   ```
3. **Ανάθεση σε ετικέτα ιδιότητας**
   ```java
   msg.setProperty(new MapiProperty(0x23901005, values));
   ```

### Ορισμός πολλαπλών ιδιοτήτων APPTIME

Οι ιδιότητες APPTIME αποθηκεύουν αποτελεσματικά τις χρονικές διάρκειες:

#### Επισκόπηση
Αυτό το χαρακτηριστικό απεικονίζει τη χρήση αριθμών διπλής ακρίβειας για χρονικές αναπαραστάσεις.

#### Βήματα
1. **Δημιουργία αντικειμένου μηνύματος**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Προσθήκη τιμών χρόνου**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem(30456.34);
   values.addItem(40655.45);
   ```
3. **Ορισμός της ιδιότητας**
   ```java
   msg.setProperty(new MapiProperty(0x23901007, values));
   ```

### Ορισμός πολλαπλών ιδιοτήτων μεγάλου μήκους

Οι ιδιότητες Long είναι ιδανικές για μεγάλους ακέραιους αριθμούς:

#### Επισκόπηση
Αυτή η λειτουργία εστιάζει στον ορισμό πολλαπλών μεγάλων ακέραιων τιμών σε ένα μήνυμα.

#### Βήματα
1. **Αρχικοποίηση μηνύματος MAPI**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Προσθήκη μεγάλων τιμών**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((long) 30456);
   values.addItem((long) 40655);
   ```
3. **Ορισμός ετικέτας ιδιότητας**
   ```java
   msg.setProperty(new MapiProperty(0x23901014, values));
   ```

### Ορισμός πολλαπλών ιδιοτήτων Short

Οι ιδιότητες Short αποθηκεύουν αποτελεσματικά μικρά ακέραια δεδομένα:

#### Επισκόπηση
Αυτός ο οδηγός δείχνει τον ορισμό μικρών ακεραίων ως ιδιοτήτων μηνύματος.

#### Βήματα
1. **Αρχικοποίηση του μηνύματος**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Προσθήκη σύντομων τιμών**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((short) 1);
   values.addItem((short) 2);
   ```
3. **Αντιστοίχιση ετικέτας ιδιότητας**
   ```java
   msg.setProperty(new MapiProperty(0x23901002, values));
   ```

### Ορισμός πολλαπλών λογικών ιδιοτήτων

Οι λογικές ιδιότητες αποθηκεύουν καταστάσεις true/false:

#### Επισκόπηση
Μάθετε πώς να ορίζετε πολλαπλές λογικές τιμές σε ένα μήνυμα.

#### Βήματα
1. **Δημιουργία αντικειμένου μηνύματος**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Προσθήκη λογικών τιμών**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem(true);
   values.addItem(false);
   ```
3. **Ορισμός ιδιότητας με αναγνωριστικό**
   ```java
   msg.setProperty(new MapiProperty(0x2390100b, values));
   ```

### Ορισμός ιδιότητας Null

Ο ρητός ορισμός μιας ιδιότητας ως null μπορεί να είναι χρήσιμος:

#### Επισκόπηση
Αυτή η ενότητα παρουσιάζει την ανάθεση μιας τιμής null σε μια ιδιότητα.

#### Βήματα
1. **Αρχικοποίηση του μηνύματος**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Ανάθεση ιδιότητας Null**
   ```java
   msg.setProperty(new MapiProperty(0x67400001, new byte[1]));
   ```

### Ρύθμιση ιδιότητας Named Long με προσαρμοσμένο αναγνωριστικό και UUID

Για σύνθετα σενάρια, ορίστε τις ιδιότητες με όνομα:

#### Επισκόπηση
Αυτή η λειτουργία δείχνει τον ορισμό μιας ιδιότητας long με ένα προσαρμοσμένο αναγνωριστικό και UUID.

#### Βήματα
1. **Αρχικοποίηση του μηνύματος**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Προσθήκη μεγάλων τιμών**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((int) 4);
   UUID uuid = UUID.randomUUID();
   ```
3. **Δημιουργία και αντιστοίχιση ιδιότητας**
   ```java
   MapiProperty property = new MapiProperty(msg.getNamedPropertyMapping().getNextAvailablePropertyId(com.aspose.email.MapiPropertyType.PT_MV_LONG), values);
   msg.getNamedPropertyMapping().addNamedPropertyMapping(property, (long) 0x00008028, uuid);
   msg.setProperty(property);
   ```

### Ορισμός προσαρμοσμένης ιδιότητας με όνομα

Οι προσαρμοσμένες ιδιότητες μπορούν να ονομαστούν για ευκολότερη αναγνώριση:

#### Επισκόπηση
Αυτός ο οδηγός δείχνει τον ορισμό ιδιοτήτων με προσαρμοσμένα ονόματα.

#### Βήματα
1. **Αρχικοποίηση αντικειμένου μηνύματος**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Ορισμός προσαρμοσμένης ιδιότητας**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem("Custom Value");
   UUID uuid = UUID.randomUUID();
   
   MapiProperty property = new MapiProperty(msg.getNamedPropertyMapping().getNextAvailablePropertyId(com.aspose.email.MapiPropertyType.PT_STRING), values);
   msg.getNamedPropertyMapping().addNamedPropertyMapping(property, "CustomName", uuid);
   ```

### Ορισμός και επικύρωση ιδιοτήτων

Είναι σημαντικό να διασφαλίσετε ότι οι ιδιότητες έχουν οριστεί σωστά:

#### Επισκόπηση
Αυτή η ενότητα καλύπτει τον ορισμό και την επικύρωση πολλαπλών ιδιοτήτων σε μηνύματα MAPI.

#### Βήματα
1. **Ορισμός ιδιότητας**
   Ακολουθήστε τα προηγούμενα παραδείγματα για να ορίσετε μια ιδιότητα.
2. **Επικύρωση ιδιότητας**
   ```java
   if (msg.getProperties().containsKey(0x23901004)) {
       System.out.println("Property is set correctly.");
   } else {
       System.err.println("Property setting failed.");
   }
   ```

## Σύναψη

Αυτός ο οδηγός παρείχε μια ολοκληρωμένη προσέγγιση για τη διαχείριση πολλαπλών ιδιοτήτων σε μηνύματα MAPI χρησιμοποιώντας το Aspose.Email για Java. Ακολουθώντας αυτά τα βήματα, μπορείτε να αποθηκεύετε και να διαχειρίζεστε αποτελεσματικά διάφορους τύπους δεδομένων στις εφαρμογές σας.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}