---
date: '2026-08-27'
description: Μάθετε πώς να φορτώνετε αρχεία MSG και να τα μετατρέπετε σε MHTML με
  το Aspose.Email for Java, συμπεριλαμβανομένων των προσαρμοσμένων ρυθμίσεων timezone
  και συμβουλές batch email processing.
keywords:
- how to load msg
- Aspose.Email Java
- convert MSG to MHTML
- email timezone offset
lastmod: '2026-08-27'
og_description: Μάθετε πώς να φορτώνετε αρχεία MSG και να τα εξάγετε ως MHTML χρησιμοποιώντας
  το Aspose.Email for Java. Περιλαμβάνει διαχείριση timezone και συμβουλές batch email
  processing.
og_image_alt: Guide to loading MSG files and saving as MHTML with Aspose.Email for
  Java
og_title: Πώς να φορτώσετε αρχεία MSG και να τα αποθηκεύσετε ως MHTML με το Aspose.Email
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
title: Πώς να φορτώσετε αρχεία MSG και να τα αποθηκεύσετε ως MHTML χρησιμοποιώντας
  το Aspose.Email for Java
url: /el/java/email-message-operations/load-save-emails-mhtml-aspose-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να φορτώσετε msg και να αποθηκεύσετε ως MHTML χρησιμοποιώντας το Aspose.Email για Java

## Εισαγωγή

Αν χρειάζεστε να **φορτώσετε msg** αρχεία, να προσαρμόσετε τις χρονικές σφραγίδες τους και στη συνέχεια να **μετατρέψετε msg σε mhtml**, βρίσκεστε στο σωστό μέρος. Σε αυτό το tutorial θα περάσουμε από τη φόρτωση ενός email `.msg`, την εφαρμογή μιας προσαρμοσμένης μετατόπισης ζώνης ώρας και την αποθήκευση του αποτελέσματος ως αρχείο MHTML — όλα με το Aspose.Email για Java. Είτε διαχειρίζεστε ένα μόνο μήνυμα είτε μια **δυναμική επεξεργασία email** pipeline, αυτά τα βήματα θα σας προσφέρουν μια σταθερή βάση για αξιόπιστη αρχειοθέτηση και μετεγκατάσταση.

**Τι θα μάθετε**
- Πώς να φορτώσετε ένα `MailMessage` από ένα αρχείο `.msg`.
- Πώς να ορίσετε μια προσαρμοσμένη ζώνη ώρας και την τρέχουσα ημερομηνία.
- Πώς να αποθηκεύσετε το μήνυμα ως MHTML με ακριβή μορφοποίηση.
- Συμβουλές για κλιμάκωση της προσέγγισης σε σενάρια batch.

Έτοιμοι να ενισχύσετε τη ροή εργασίας των email σας; Ας ετοιμάσουμε πρώτα το περιβάλλον.

## Γρήγορες απαντήσεις
- **Ποια είναι η κύρια βιβλιοθήκη;** Aspose.Email for Java.
- **Μπορώ να φορτώσω MSG και να εξάγω σε MHTML σε ένα βήμα;** Όχι, φορτώνετε, προσαρμόζετε, μετά αποθηκεύετε.
- **Χρειάζομαι άδεια για παραγωγή;** Ναι, απαιτείται έγκυρη άδεια Aspose.Email.
- **Υποστηρίζεται η διαχείριση ζώνης ώρας;** Ναι, μέσω του `setTimeZoneOffset`.
- **Μπορεί να χρησιμοποιηθεί σε επεξεργασία batch;** Απόλυτα – τυλίξτε τα βήματα σε έναν βρόχο.

## Τι είναι το Aspose.Email για Java;

Το Aspose.Email για Java είναι ένα ολοκληρωμένο API που σας επιτρέπει να δημιουργείτε, διαβάζετε, μετατρέπετε και να χειρίζεστε μηνύματα email χωρίς να απαιτείται το Microsoft Outlook. Υποστηρίζει περισσότερα από 30 μορφές email και μπορεί να επεξεργαστεί μηνύματα πολλών εκατοντάδων σελίδων διατηρώντας χαμηλή χρήση μνήμης.

## Γιατί να μετατρέψετε MSG σε MHTML;

Η μετατροπή αρχείων MSG σε MHTML σας παρέχει μια φιλική προς το web, μονοαρχική αναπαράσταση που μπορεί να ανοιχθεί σε οποιονδήποτε σύγχρονο περιηγητή. Αυτή η μορφή διατηρεί το αρχικό στυλ, τις ενσωματωμένες εικόνες και τα συνημμένα, καθιστώντας την ιδανική για **νομική αρχειοθέτηση**, **διαπλατφορμική κοινή χρήση** και **ενσωμάτωση email σε ιστοσελίδες ή τεκμηρίωση**.

## Προαπαιτούμενα

Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τα εξής:

### Απαιτούμενες βιβλιοθήκες και εξαρτήσεις
- Βιβλιοθήκη **Aspose.Email for Java** έκδοση 25.4 (classifier jdk16) – η βιβλιοθήκη υποστηρίζει **50+** μορφές εισόδου και εξόδου email.
- Βασικές γνώσεις Java.
- Ένα IDE όπως το IntelliJ IDEA ή το Eclipse.

### Απαιτήσεις ρύθμισης περιβάλλοντος
- Εγκατεστημένο JDK 16 ή νεότερο.
- Maven για διαχείριση εξαρτήσεων.

## Ρύθμιση του Aspose.Email για Java

Για να προσθέσετε τη βιβλιοθήκη σε ένα έργο Maven, συμπεριλάβετε την ακόλουθη εξάρτηση:

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

### Βήματα απόκτησης άδειας

Ξεκινήστε με μια **δωρεάν δοκιμή** ή αποκτήστε μια **προσωρινή άδεια** για να αξιολογήσετε τις πλήρεις δυνατότητες της βιβλιοθήκης χωρίς περιορισμούς. Για μακροπρόθεσμη χρήση, σκεφτείτε την αγορά άδειας:

- [Δωρεάν Δοκιμή](https://releases.aspose.com/email/java/)
- [Προσωρινή Άδεια](https://purchase.aspose.com/temporary-license/)
- [Αγορά Άδειας](https://purchase.aspose.com/buy)

### Βασική αρχικοποίηση

Η κλάση `License` καταχωρεί την άδεια Aspose.Email για να ξεκλειδώσει όλες τις δυνατότητες.  
Μετά την προσθήκη της εξάρτησης, αρχικοποιήστε την άδεια στον κώδικα Java:

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

## Πώς να φορτώσετε msg και να αποθηκεύσετε ως MHTML;

Φορτώστε το αρχείο MSG, προσαρμόστε τη χρονική σφραγίδα και αποθηκεύστε το ως MHTML σε τρία απλά βήματα. Πρώτα, δημιουργήστε ένα `MailMessage` από το αρχείο MSG χρησιμοποιώντας το `MsgLoadOptions`. Στη συνέχεια, ορίστε την επιθυμητή μετατόπιση ζώνης ώρας με το `setTimeZoneOffset`. Τέλος, διαμορφώστε το `MhtSaveOptions` και καλέστε το `save` για να παραγάγετε το αρχείο MHTML.

### Δυνατότητα 1: φόρτωση ενός MailMessage από αρχείο

Η κλάση `MailMessage` αντιπροσωπεύει ένα μήνυμα email με κεφαλίδες, σώμα και συνημμένα.

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

`MsgLoadOptions` σας επιτρέπει να ελέγξετε πώς θα αναλυθεί το αρχείο MSG· οι προεπιλεγμένες ρυθμίσεις λειτουργούν για τις περισσότερες περιπτώσεις.

### Δυνατότητα 2: ορισμός τρέχουσας ημερομηνίας και προσαρμοσμένης μετατόπισης ζώνης ώρας

Το αντικείμενο `Date` περιέχει τη χρονική σφραγίδα που θα γραφτεί στην κεφαλίδα **Date** του email.

```java
java.util.Date now = new java.util.Date();
msg.setDate(now);
```
```java
import java.util.Date;

msg.setDate(new Date());
```

Η μετατόπιση εκφράζεται σε χιλιοστά του δευτερολέπτου· για UTC+5 περνάτε `5 * 60 * 60 * 1000`.

```java
int utcPlusFive = 5 * 60 * 60 * 1000;
msg.setTimeZoneOffset(utcPlusFive);
```
```java
msg.setTimeZoneOffset(5 * 60 * 60 * 1000); // 5 hours ahead of UTC in milliseconds.
```

### Δυνατότητα 3: αποθήκευση ενός MailMessage ως αρχείο MHTML

`MhtSaveOptions` ορίζει πώς το email θα συσκευαστεί σε αρχείο MHTML, διατηρώντας τις ενσωματωμένες εικόνες και τα συνημμένα.

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

Το προκύπτον αρχείο `.mhtml` διατηρεί την αρχική μορφοποίηση, τις εικόνες και τα συνημμένα, καθιστώντας το μια πιστή οπτική αντίγραφο του αρχικού MSG.

## Πώς να ορίσετε προσαρμοσμένη μετατόπιση ζώνης ώρας;

Μπορείτε να τροποποιήσετε τη ζώνη ώρας καλώντας το `setTimeZoneOffset` στο αντικείμενο `MailMessage`. Η μέθοδος αναμένει μια μετατόπιση σε χιλιοστά του δευτερολέπτου, επιτρέποντας τόσο θετικές (ανατολικά του UTC) όσο και αρνητικές (δυτικά του UTC) τιμές. Για παράδειγμα, UTC‑3 είναι `-3 * 60 * 60 * 1000`.

## Πώς να επεξεργαστείτε αρχεία MSG σε batch;

Τυλίξτε τη ροή τριών βημάτων μέσα σε έναν βρόχο που διατρέχει έναν φάκελο με αρχεία `.msg`. Επαναχρησιμοποιήστε ένα μόνο αντικείμενο `License` για να αποφύγετε επαναλαμβανόμενες εισόδους/εξόδους και απελευθερώστε κάθε `MailMessage` μετά την αποθήκευση για να διατηρήσετε τη χρήση μνήμης χαμηλή.

```java
File folder = new File("msg_folder");
for (File file : folder.listFiles((dir, name) -> name.toLowerCase().endsWith(".msg"))) {
    MailMessage msg = MailMessage.load(file.getAbsolutePath(), new MsgLoadOptions());
    // set date & timezone as shown earlier
    msg.save(file.getName().replace(".msg", ".mhtml"), new MhtSaveOptions());
    msg.dispose(); // releases native resources
}
```

### Συμβουλές επεξεργασίας batch
1. **Επαναχρησιμοποίηση της άδειας** – καλέστε `new License().setLicense(...)` μία φορά κατά την εκκίνηση της εφαρμογής.
2. **Χρησιμοποιήστε try‑with‑resources** για αυτόματη εκκαθάριση των ροών.
3. **Καταγράψτε αποτυχίες** σε ξεχωριστό αρχείο ώστε να μπορείτε να επαναπροσπαθήσετε τα προβληματικά μηνύματα αργότερα.
4. **Σκεφτείτε παράλληλη εκτέλεση** με `ForkJoinPool` για μεγάλα batch, αλλά βεβαιωθείτε ότι κάθε νήμα χρησιμοποιεί το δικό του αντικείμενο `MailMessage`.

## Κοινά προβλήματα και λύσεις

- **Αιχμές μνήμης με τεράστια αρχεία MSG** – ενεργοποιήστε τη ροή δεδομένων χρησιμοποιώντας `MailMessage.load(InputStream, MsgLoadOptions)` και επεξεργαστείτε τη ροή σε τμήματα.
- **Λανθασμένες χρονικές σφραγίδες** – βεβαιωθείτε ότι το σύστημα ώρας είναι ρυθμισμένο σε UTC πριν την εφαρμογή των μετατοπίσεων, ή περάστε ρητά ένα αντικείμενο `java.util.Calendar`.
- **Απουσία συνημμένων στο MHTML** – βεβαιωθείτε ότι το `MhtSaveOptions.setWriteHeader(true)` είναι ενεργό· αυτό ενσωματώνει τα συνημμένα ως πόρους `cid:`.

## Συχνές ερωτήσεις

**Ε: Μπορώ να φορτώσω email από μορφές εκτός του .msg;**  
Α: Ναι, το Aspose.Email υποστηρίζει EML, MHT, EMLX και πολλές άλλες μορφές, συνολικά πάνω από 30 τύπους εισόδου.

**Ε: Πώς μπορώ να διαχειριστώ πολύ μεγάλα αρχεία email αποδοτικά;**  
Α: Χρησιμοποιήστε τα streaming APIs (`MailMessage.load(InputStream, ...)`) για ανάγνωση και εγγραφή δεδομένων σε τμήματα, κάτι που διατηρεί τη χρήση μνήμης κάτω από 50 MB ακόμη και για μηνύματα 500 σελίδων.

**Ε: Είναι δυνατόν να τροποποιήσετε τα συνημμένα μέσα σε ένα MailMessage;**  
Α: Απόλυτα. Μπορείτε να προσθέσετε, να αφαιρέσετε ή να αντικαταστήσετε συνημμένα μέσω της συλλογής `msg.getAttachments()`, και στη συνέχεια να καλέσετε `save` για να αποθηκεύσετε τις αλλαγές.

**Ε: Τι γίνεται αν η μετατόπιση της ζώνης ώρας είναι αρνητική (πίσω από το UTC);**  
Α: Περνάτε μια αρνητική τιμή χιλιοστών του δευτερολέπτου στο `setTimeZoneOffset`, π.χ., `-3 * 60 * 60 * 1000` για UTC‑3.

**Ε: Μπορώ να χρησιμοποιήσω το Aspose.Email σε εμπορικά έργα;**  
Α: Ναι, εφόσον διαθέτετε έγκυρη εμπορική άδεια. Η δωρεάν δοκιμή περιορίζεται στα 20 MB ανά έγγραφο.

**Ε: Πώς μπορώ να επεξεργαστώ χιλιάδες αρχεία MSG χωρίς να εξαντλήσω τη μνήμη;**  
Α: Επεξεργαστείτε τα αρχεία σε παρτίδες, απελευθερώστε κάθε `MailMessage` μετά την αποθήκευση και χρησιμοποιήστε το πρότυπο `try‑with‑resources` της Java για αυτόματη εκκαθάριση.

## Πόροι
- [τεκμηρίωση](https://reference.aspose.com/email/java/)
- [Τεκμηρίωση](https://reference.aspose.com/email/java/)
- [Λήψη Βιβλιοθήκης](https://releases.aspose.com/email/java/)
- [Αγορά Άδειας](https://purchase.aspose.com/buy)
- [Δωρεάν Δοκιμή](https://releases.aspose.com/email/java/)
- [Προσωρινή Άδεια](https://purchase.aspose.com/temporary-license/)
- [Φόρουμ Υποστήριξης](https://forum.aspose.com/c/email/10)

---

**Τελευταία ενημέρωση:** 2026-08-27  
**Δοκιμή με:** Aspose.Email for Java 25.4 (jdk16 classifier)  
**Συγγραφέας:** Aspose

## Σχετικές οδηγίες

- [Πώς να φορτώσετε και να αναλύσετε αρχεία Outlook MSG χρησιμοποιώντας το Aspose.Email για Java: Ένας ολοκληρωμένος οδηγός](/email/java/mapi-operations/outlook-msg-aspose-email-java-guide/)
- [Maven Aspose.Email για Java: Αποθήκευση email ως αρχεία MHT](/email/java/email-message-operations/save-emails-as-mht-using-aspose-email-java/)
- [Πώς να εξάγετε συνημμένα από αρχεία msg χρησιμοποιώντας το Aspose.Email για Java](/email/java/advanced-email-attachments/extracting-attachments-from-email-messages/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}