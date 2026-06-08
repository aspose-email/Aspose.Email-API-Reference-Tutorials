---
date: '2026-06-08'
description: Μάθετε πώς να δημιουργήσετε αρχεία PST με το Aspose.Email for Java, συμπεριλαμβανομένου
  του πώς να προσθέσετε δομές φακέλων και του πώς να αναζητήσετε το περιεχόμενο του
  PST αποδοτικά. Οδηγός βήμα-βήμα.
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
title: Πώς να δημιουργήσετε αρχεία PST με το Aspose.Email for Java
url: /el/java/email-parsing-analysis/aspose-email-java-create-pst-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Κατάκτηση της Διαχείρισης Email με το Aspose.Email για Java

Αν χρειάζεστε να **how to create pst** αρχεία προγραμματιστικά, βρίσκεστε στο σωστό μέρος. Σε αυτό το tutorial θα περάσουμε από κάθε βήμα που απαιτείται για τη δημιουργία ενός Unicode PST αρχείου, την προσθήκη τυπικών φακέλων Outlook, την εισαγωγή μηνυμάτων και την εκτέλεση αναζητήσεων χωρίς διάκριση πεζών‑κεφαλαίων — όλα χρησιμοποιώντας το Aspose.Email για Java. Στο τέλος, θα έχετε ένα επαναχρησιμοποιήσιμο πρότυπο κώδικα που κλιμακώνεται από λίγα email έως αρχεία πολλαπλών gigabyte.

## Γρήγορες Απαντήσεις
- **Πώς ξεκινάω;** Προσθέστε την εξάρτηση Aspose.Email Maven, αποκτήστε άδεια και δημιουργήστε ένα αντικείμενο `PersonalStorage`.
- **Μπορώ να προσθέσω φάκελο Inbox;** Ναι – καλέστε `pst.getRootFolder().addSubFolder("Inbox")`.
- **Υποστηρίζεται η αναζήτηση χωρίς διάκριση πεζών‑κεφαλαίων;** Χρησιμοποιήστε `PersonalStorageQueryBuilder` με `StringComparison.OrdinalIgnoreCase`.
- **Ποιο μέγεθος αρχείου μπορεί να διαχειριστεί;** Το Aspose.Email επεξεργάζεται αρχεία PST έως 2 GB χωρίς να φορτώνει ολόκληρο το αρχείο στη μνήμη.
- **Χρειάζομαι πληρωμένη άδεια για παραγωγή;** Μια μόνιμη άδεια αφαιρεί τους περιορισμούς της δοκιμής και ξεκλειδώνει όλες τις δυνατότητες απόδοσης.

## Τι είναι το how to create pst;
**how to create pst** αναφέρεται στη διαδικασία προγραμματιστικής δημιουργίας ενός αρχείου Outlook Personal Storage Table (PST) χρησιμοποιώντας κώδικα αντί για το UI του Outlook. Το Aspose.Email για Java παρέχει ένα πλήρως διαχειριζόμενο API που δημιουργεί αρχεία Unicode PST, προσθέτει φακέλους και αποθηκεύει αντικείμενα `MapiMessage` χωρίς να απαιτείται εγκατάσταση του Outlook.

## Γιατί να χρησιμοποιήσετε το Aspose.Email για δημιουργία PST;
Το Aspose.Email υποστηρίζει **50+** μορφές σχετικές με email (MSG, EML, MBOX, PST κ.λπ.) και μπορεί να επεξεργαστεί αρχεία PST με **μέγεθος έως 2 GB** διατηρώντας τη χρήση μνήμης κάτω από **150 MB** χάρη στην αρχιτεκτονική lazy‑loading. Αυτή η ποσοτικοποιημένη δυνατότητα το καθιστά ιδανικό για επιχειρησιακή αρχειοθέτηση, μετανάστευση και σενάρια συμμόρφωσης.

## Προαπαιτούμενα

- **Java Development Kit (JDK)** – έκδοση 16 ή νεότερη.
- **Maven** – για διαχείριση εξαρτήσεων.
- Βασική εξοικείωση με τη σύνταξη της Java· δεν απαιτείται προηγούμενη εμπειρία με αρχεία PST.

## Πώς να δημιουργήσετε αρχείο PST;

Η κλάση `PersonalStorage` αντιπροσωπεύει ένα αρχείο PST και παρέχει μεθόδους για δημιουργία, άνοιγμα και διαχείριση του περιεχομένου του. Για να δημιουργήσετε ένα νέο Unicode PST, καλέστε `PersonalStorage.create()` με τη ζητούμενη διαδρομή αρχείου και την έκδοση μορφής. Αυτή η λειτουργία δημιουργεί ένα σύγχρονο PST που υποστηρίζει μεγάλους φακέλους, χαρακτήρες Unicode και αποδοτική ροή δεδομένων, καθιστώντας το κατάλληλο για μικρής κλίμακας καθώς και επιχειρησιακής κλίμακας αρχειοθέτηση.

### Βήμα 1: Προσθήκη εξάρτησης Maven

Προσθέστε την εξάρτηση Aspose.Email Maven στο `pom.xml` σας. Αυτό θα φέρει αυτόματα όλα τα απαιτούμενα binaries.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Βήμα 2: Απόκτηση και εφαρμογή άδειας

Διατίθεται δωρεάν δοκιμή, αλλά μια μόνιμη άδεια αφαιρεί τους περιορισμούς αξιολόγησης και ενεργοποιεί επεξεργασία πλήρους ταχύτητας.

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

## Πώς να προσθέσετε φάκελο σε PST;

Δημιουργήστε την επιθυμητή ιεραρχία φακέλων κάτω από τη ρίζα του PST, και στη συνέχεια αναφερθείτε σε αυτήν όταν εισάγετε μηνύματα. Το αντικείμενο `FolderInfo` αντιπροσωπεύει κάθε φάκελο και μπορεί να ενσωματώνεται αυθαίρετα, επιτρέποντάς σας να δημιουργήσετε δομές όπως Inbox, Sent Items ή προσαρμοσμένους φακέλους έργου. Η προσθήκη φακέλων είναι μια ελαφριά λειτουργία που δεν φορτώνει το περιεχόμενο των μηνυμάτων, διατηρώντας την απόδοση ακόμη και για μεγάλα PST.

### Βήμα 1: Αρχικοποίηση PersonalStorage

Η κλάση `PersonalStorage` είναι το αντικείμενο υψηλότερου επιπέδου του Aspose.Email που αντιπροσωπεύει ένα μοναδικό αρχείο PST στη μνήμη. Μετά την δημιουργία, όλες οι λειτουργίες ανάγνωσης και εγγραφής περνούν μέσω αυτού του αντικειμένου.

```java
import com.aspose.email.FileFormatVersion;
import com.aspose.email.PersonalStorage;
```

### Βήμα 2: Ορισμός διαδρομών καταλόγων

Ορίστε τις διαδρομές πηγής και προορισμού για τα αρχεία email σας και τη θέση εξόδου του PST.

```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY";
String outputDir = "YOUR_OUTPUT_DIRECTORY";
```

### Βήμα 3: Δημιουργία του αρχείου PST

Χρησιμοποιήστε `PersonalStorage.create()` με `FileFormatVersion.Unicode` για να δημιουργήσετε ένα σύγχρονο Unicode PST που υποστηρίζει μεγάλους φακέλους και χαρακτήρες Unicode.

```java
try {
    PersonalStorage pst = PersonalStorage.create(outputDir + "NewPSTFile_out.pst", FileFormatVersion.Unicode);

    // Perform operations here.
} finally {
    if (pst != null)
        pst.dispose();
}
```

## Πώς να αναζητήσετε pst;

`PersonalStorageQueryBuilder` είναι μια κλάση builder που χρησιμοποιείται για τη δημιουργία ερωτημάτων αναζήτησης για το περιεχόμενο του PST. Με τη διαμόρφωση του builder με τα επιθυμητά κριτήρια και τον καθορισμό του `StringComparison.OrdinalIgnoreCase`, μπορείτε να εκτελέσετε γρήγορες, αναζητήσεις χωρίς διάκριση πεζών‑κεφαλαίων σε θέματα, σώματα και προσαρμοσμένες ιδιότητες χωρίς να φορτώνετε ολόκληρο το PST στη μνήμη.

### Βήμα 1: Δημιουργία ερωτήματος αναζήτησης

Δημιουργήστε ένα ερώτημα που αναζητά μια λέξη-κλειδί στο θέμα ή στο σώμα, αγνοώντας τη διάκριση πεζών‑κεφαλαίων.

```java
import com.aspose.email.MailQueryBuilder;
import com.aspose.email.MailQuery;
import com.aspose.email.MessageInfoCollection;

MailQueryBuilder builder = new MailQueryBuilder();
builder.getFrom().contains("automated", true);
```

### Βήμα 2: Εκτέλεση ερωτήματος και ανάκτηση μηνυμάτων

Εκτελέστε το ερώτημα στον στόχο φάκελο και επαναλάβετε τη συλλογή `MapiMessage` που προκύπτει.

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

## Δημιουργία προεπιλεγμένου φακέλου σε PST

Η προσθήκη ενός προεπιλεγμένου φακέλου όπως το **Inbox** βοηθά στην αποτελεσματική οργάνωση των δεδομένων email σας.

### Βήμα 1: Αρχικοποίηση αντικειμένου PersonalStorage

Υποθέτουμε ότι το αντικείμενο `PersonalStorage` (`pst`) έχει ήδη δημιουργηθεί όπως φαίνεται προηγουμένως.

### Βήμα 2: Δημιουργία φακέλου 'Inbox'

```java
try {
    FolderInfo fi = pst.createPredefinedFolder("Inbox", StandardIpmFolder.Inbox);
} finally {
    if (pst != null)
        pst.dispose();
}
```

## Προσθήκη μηνυμάτων σε φάκελο PST

Συμπληρώστε το φάκελο PST με μηνύματα email φορτώνοντάς τα από αρχεία και μετατρέποντάς τα.

### Βήμα 1: Φόρτωση μηνύματος email

```java
import com.aspose.email.MailMessage;
import com.aspose.email.MapiMessage;

MailMessage mailMessage = MailMessage.load(dataDir + "message.msg");
```

### Βήμα 2: Προσθήκη σε φάκελο PST

Μετατρέψτε το `MailMessage` σε `MapiMessage` και προσθέστε το:

```java
try {
    fi.addMessage(MapiMessage.fromMailMessage(mailMessage));
} finally {
    if (pst != null)
        pst.dispose();
}
```

## Πρακτικές Εφαρμογές

Το Aspose.Email για Java δεν αφορά μόνο τη δημιουργία αρχείων PST· είναι ένα ευέλικτο εργαλείο με πολλές εφαρμογές:
- **Email Archiving**: Αυτοματοποιήστε την αρχειοθέτηση εταιρικών email σε αρχεία PST, υποστηρίζοντας πολιτικές διατήρησης έως 10 ετών.
- **Migration Tools**: Μεταφέρετε αβίαστα από παλαιά αποθήκες αλληλογραφίας (π.χ., MBOX) σε Outlook PST με μία κλήση API ανά μήνυμα.
- **Data Analysis**: Εξάγετε μεταδεδομένα όπως αποστολέας, παραλήπτης και χρονικές σφραγίδες για pipelines επιχειρησιακής ευφυΐας.
- **Backup Solutions**: Δημιουργήστε αξιόπιστες λύσεις backup που αποθηκεύουν διαδοχικές αλλαγές email χωρίς επεξεργασία ολόκληρου του γραμματοκιβωτίου.

## Παράγοντες Απόδοσης

Για να εξασφαλίσετε βέλτιστη απόδοση κατά τη χρήση του Aspose.Email:
- **Resource Management**: Πάντα καλέστε `pst.dispose()` ή χρησιμοποιήστε try‑with‑resources για άμεση απελευθέρωση των εγγενών χειριστών.
- **Batch Processing**: Επεξεργαστείτε email σε παρτίδες των **500** στοιχείων για προβλέψιμη χρήση μνήμης.
- **Concurrency Handling**: Η βιβλιοθήκη είναι thread‑safe για λειτουργίες μόνο ανάγνωσης· για εγγραφές, συγχρονίστε την πρόσβαση στο αντικείμενο `PersonalStorage`.

## Κοινά Προβλήματα και Λύσεις

| Πρόβλημα | Αιτία | Λύση |
|----------|-------|------|
| **OutOfMemoryError** κατά τη διαχείριση μεγάλων PST | Φόρτωση ολόκληρου του PST στη μνήμη | Ενεργοποιήστε `PersonalStorage.setUseUnicode(true)` και επεξεργαστείτε τα μηνύματα σε ροές. |
| **Folder not found** error | Λανθασμένη περίπτωση διαδρομής φακέλου | Χρησιμοποιήστε `StringComparison.OrdinalIgnoreCase` στα ερωτήματα ή κανονικοποιήστε τα ονόματα φακέλων. |
| **License not applied** | Το αρχείο άδειας δεν φορτώθηκε πριν την πρώτη κλήση API | Φορτώστε την άδεια κατά την εκκίνηση της εφαρμογής, πριν δημιουργήσετε οποιαδήποτε αντικείμενα `PersonalStorage`. |

## Συχνές Ερωτήσεις

**Q: Ποια είναι η ελάχιστη έκδοση Java που απαιτείται;**  
A: Συνιστάται το JDK 16 ή νεότερο για πλήρη συμβατότητα με το Aspose.Email για Java.

**Q: Μπορώ να χρησιμοποιήσω το Aspose.Email χωρίς άδεια;**  
A: Ναι, υπάρχει λειτουργία δοκιμής, αλλά περιορίζει το μέγεθος του PST στα **10 MB** και απενεργοποιεί ορισμένες βελτιστοποιήσεις.

**Q: Πώς να διαχειριστώ μεγάλα αρχεία PST αποδοτικά;**  
A: Επεξεργαστείτε τα μηνύματα σε παρτίδες, απελευθερώστε άμεσα τα αντικείμενα `MapiMessage` και ενεργοποιήστε τη lazy loading μέσω `PersonalStorage.setUseUnicode(true)`.

**Q: Είναι δυνατόν να προσθέσετε συνημμένα σε email σε αρχεία PST;**  
A: Απόλυτα. Κατά τη μετατροπή του `MailMessage` σε `MapiMessage`, καλέστε `mapiMsg.getAttachments().add(attachment)` για να ενσωματώσετε τα αρχεία.

**Q: Τι είδους υποστήριξη είναι διαθέσιμη για την αντιμετώπιση προβλημάτων;**  
A: Η Aspose προσφέρει αφιερωμένο φόρουμ υποστήριξης, λεπτομερή τεκμηρίωση και υποστήριξη μέσω email για πελάτες με άδεια.

## Πόροι
- [Τεκμηρίωση](https://reference.aspose.com/email/java/)
- [Λήψη](https://releases.aspose.com/email/java/)
- [Αγορά](https://purchase.aspose.com/buy)
- [Δωρεάν Δοκιμή](https://releases.aspose.com/email/java/)
- [Προσωρινή Άδεια](https://purchase.aspose.com/temporary-license/)
- [Φόρουμ Υποστήριξης](https://forum.aspose.com/c/email/10)

---

**Τελευταία Ενημέρωση:** 2026-06-08  
**Δοκιμάστηκε Με:** Aspose.Email for Java 24.10  
**Συγγραφέας:** Aspose

## Σχετικά Μαθήματα

- [Πώς να δημιουργήσετε και να διαχειριστείτε αρχεία Outlook PST χρησιμοποιώντας το Aspose.Email για Java](/email/java/outlook-pst-ost-operations/aspose-email-java-manage-pst-files/)
- [Διαχείριση αρχείων PST με το Aspose.Email για Java: Ένας ολοκληρωμένος οδηγός](/email/java/outlook-pst-ost-operations/manipulate-pst-files-aspose-email-java/)
- [Εξαγωγή Συνημμένων Email Java - Χρήση Aspose.Email για αρχεία PST – Οδηγός βήμα προς βήμα](/email/java/attachments-handling/extract-email-attachments-pst-aspose-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}