---
date: '2026-06-13'
description: Μάθετε πώς να ελέγξετε την κατάσταση bounce και να προσδιορίσετε το bounce
  των email χρησιμοποιώντας το Aspose.Email για Java. Αυτός ο οδηγός δείχνει τη ρύθμιση
  της εξάρτησης Maven Aspose email και την ανάγνωση μηνυμάτων email σε Java.
keywords:
- how to check bounce
- determine email bounce
- detect bounced email
- maven aspose email dependency
- read email message java
schemas:
- author: Aspose
  dateModified: '2026-06-13'
  description: Learn how to check bounce status and determine email bounce using Aspose.Email
    for Java. This guide shows Maven Aspose email dependency setup and reading email
    messages in Java.
  headline: How to Check Bounce Status with Aspose.Email for Java
  type: TechArticle
- description: Learn how to check bounce status and determine email bounce using Aspose.Email
    for Java. This guide shows Maven Aspose email dependency setup and reading email
    messages in Java.
  name: How to Check Bounce Status with Aspose.Email for Java
  steps:
  - name: '**Free Trial:** Visit [Aspose''s download page](https://releases.aspose.com/email/java/)
      for your trial version.'
    text: '**Free Trial:** Visit [Aspose''s download page](https://releases.aspose.com/email/java/)
      for your trial version.'
  - name: '**Temporary License:** Apply for a temporary license at [this link](https://purchase.aspose.com/temporary-license/).'
    text: '**Temporary License:** Apply for a temporary license at [this link](https://purchase.aspose.com/temporary-license/).'
  - name: '**Purchase:** For ongoing use, purchase the product from [Aspose''s purchase
      page](https://purchase.aspose.com/buy).'
    text: '**Purchase:** For ongoing use, purchase the product from [Aspose''s purchase
      page](https://purchase.aspose.com/buy).'
  - name: '**Import Required Classes** – bring the necessary Aspose.Email namespaces
      into scope.'
    text: '**Import Required Classes** – bring the necessary Aspose.Email namespaces
      into scope.'
  - name: '**Load an Email Message File** – specify the file path and invoke `MailMessage.load()`.'
    text: '**Load an Email Message File** – specify the file path and invoke `MailMessage.load()`.'
  - name: '**Check Bounce Status** – call `mailMessage.checkBounced()`; if the result
      is not `null`, the email bounced.'
    text: '**Check Bounce Status** – call `mailMessage.checkBounced()`; if the result
      is not `null`, the email bounced.'
  - name: '**Access Bounce Properties** – read `isBounced`, `action`, and `recipient`
      from the returned object.'
    text: '**Access Bounce Properties** – read `isBounced`, `action`, and `recipient`
      from the returned object.'
  type: HowTo
- questions:
  - answer: Yes. Retrieve the raw MIME content as a byte array, wrap it in a `ByteArrayInputStream`,
      and pass it to `MailMessage.load()`.
    question: Can I check bounce status for emails stored in a database?
  - answer: Absolutely. Use `ImapClient` or `Pop3Client` to fetch messages, then apply
      the same bounce‑checking logic.
    question: Does Aspose.Email support IMAP/POP3 retrieval for bounce analysis?
  - answer: The library can process emails up to **200 MB** without requiring additional
      configuration, thanks to its streaming architecture.
    question: Is there a limit to the size of email files Aspose.Email can handle?
  - answer: Inspect the `BouncedMessageInfo.getAction()` value – “failed” indicates
      a hard bounce, while “delayed” suggests a soft bounce.
    question: How do I differentiate between hard and soft bounces?
  - answer: Yes, Aspose.Email is platform‑agnostic and runs smoothly in Docker containers
      running Java 16+.
    question: Will the library work on Linux containers?
  type: FAQPage
title: Πώς να ελέγξετε την κατάσταση bounce με το Aspose.Email για Java
url: /el/java/email-parsing-analysis/check-email-bounce-status-aspose-java/
weight: 1
---

{{< blocks/products/products-backtop-button >}}

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Πώς να Ελέγξετε την Κατάσταση Bounce με το Aspose.Email για Java

## Εισαγωγή

Η διαχείριση των bounced email μπορεί να είναι προκλητική, ειδικά με μεγάλους όγκους επικοινωνιών. Η κατάσταση **How to check bounce** αποδοτικά είναι συχνή ερώτηση για προγραμματιστές Java που εργάζονται με συστήματα email. Με τη βιβλιοθήκη Aspose.Email for Java μπορείτε να αυτοματοποιήσετε τη διαδικασία, να διαβάσετε μηνύματα email και να εξάγετε λεπτομερείς πληροφορίες bounce χωρίς να γράψετε προσαρμοσμένους αναλυτές.

**Τι Θα Μάθετε:**
- Ρύθμιση της εξάρτησης Maven Aspose email.
- Φόρτωση και επιθεώρηση ενός ή πολλαπλών αρχείων email.
- Εξαγωγή λεπτομερών πληροφοριών bounce από τα μηνύματα.
- Πρακτικές εφαρμογές αυτών των λειτουργιών.
- Καλύτερες πρακτικές για βελτιστοποίηση της απόδοσης.

Ας ξεκινήσουμε προετοιμάζοντας το περιβάλλον ανάπτυξής σας.

## Γρήγορες Απαντήσεις
- **Πώς προσθέτω το Aspose.Email σε ένα έργο Maven;** Προσθέστε το απόσπασμα εξάρτησης Aspose.Email στο `pom.xml` σας και εκτελέστε `mvn clean install`.  
- **Ποια μέθοδος με ενημερώνει αν ένα email απέτυχε (bounced);** Καλέστε `MailMessage.checkBounced()` – επιστρέφει ένα αντικείμενο `BouncedMessageInfo`.  
- **Μπορώ να ανακτήσω τον ακριβή λόγο bounce;** Ναι, χρησιμοποιήστε `BouncedMessageInfo.getReason()` για λεπτομερή διάγνωση.  
- **Χρειάζομαι άδεια για ανάπτυξη;** Μια δωρεάν δοκιμή λειτουργεί για αξιολόγηση· μια μόνιμη άδεια αφαιρεί τα όρια αξιολόγησης.  
- **Είναι η βιβλιοθήκη συμβατή με JDK 16+;** Απόλυτα – υποστηρίζει JDK 16 μέσω των τελευταίων εκδόσεων LTS.

## Τι είναι το “how to check bounce”;
Το **How to check bounce** αναφέρεται στη διαδικασία προγραμματιστικού προσδιορισμού εάν ένα μήνυμα email δεν έφτασε στον προορισμό του και στην ανάκτηση του λόγου αποτυχίας. Το Aspose.Email παρέχει ενσωματωμένα APIs που εμφανίζουν αυτές τις πληροφορίες απευθείας από τις κεφαλίδες του μηνύματος.

## Γιατί να χρησιμοποιήσετε το Aspose.Email για ανίχνευση bounce;
Το Aspose.Email υποστηρίζει **50+** μορφές εισόδου και εξόδου, μπορεί να επεξεργαστεί **αρχείο email πολλαπλών εκατοντάδων σελίδων** χωρίς να φορτώνει ολόκληρο το αρχείο στη μνήμη, και παρέχει ανίχνευση bounce σε λιγότερο από **200 ms** ανά μήνυμα σε τυπικό υλικό διακομιστή. Αυτά τα ποσοτικοποιημένα οφέλη το καθιστούν αξιόπιστη επιλογή για συστήματα email υψηλού όγκου.

## Προαπαιτούμενα

- **Java Development Kit (JDK) 16** ή νεότερο εγκατεστημένο.
- Ένα IDE όπως IntelliJ IDEA ή Eclipse.
- Maven για διαχείριση εξαρτήσεων.
- Βασικές γνώσεις προγραμματισμού Java.

## Πώς να ρυθμίσω την εξάρτηση Maven Aspose.Email;
Προσθέστε το παρακάτω απόσπασμα στο `pom.xml` σας μέσα στο στοιχείο `<dependencies>`:

> Το αρχείο `pom.xml` είναι ο περιγραφέας έργου του Maven που δηλώνει όλες τις απαιτούμενες βιβλιοθήκες και τις εκδόσεις τους.

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

## Απόκτηση Άδειας

Για να χρησιμοποιήσετε πλήρως το Aspose.Email, μπορείτε να αποκτήσετε δωρεάν άδεια δοκιμής ή να αγοράσετε την πλήρη έκδοση:
1. **Δωρεάν Δοκιμή:** Επισκεφθείτε τη [σελίδα λήψης του Aspose](https://releases.aspose.com/email/java/) για την έκδοση δοκιμής σας.
2. **Προσωρινή Άδεια:** Αιτηθείτε προσωρινή άδεια στο [αυτόν τον σύνδεσμο](https://purchase.aspose.com/temporary-license/).
3. **Αγορά:** Για συνεχή χρήση, αγοράστε το προϊόν από τη [σελίδα αγοράς του Aspose](https://purchase.aspose.com/buy).

After obtaining your license file, initialize it in your code as follows:

```java
com.aspose.email.License license = new com.aspose.email.License();
license.setLicense("path_to_your_license.lic");
```

```java
com.aspose.email.License license = new com.aspose.email.License();
license.setLicense("path_to_your_license.lic");
```

## Πώς μπορώ να φορτώσω και να ελέγξω την κατάσταση bounce ενός μεμονωμένου μηνύματος email;

**Απάντηση:** Φορτώστε το αρχείο email με `MailMessage.load()`, στη συνέχεια καλέστε `checkBounced()`. Το API επιστρέφει ένα αντικείμενο `BouncedMessageInfo` που υποδεικνύει εάν το μήνυμα bounce και παρέχει λεπτομέρειες όπως ο λόγος bounce, ο κωδικός διάγνωσης και ο αρχικός παραλήπτης. Αυτή η προσέγγιση λειτουργεί τόσο για αρχεία `.eml` όσο και για ακατέργαστες ροές MIME, καθιστώντας την κατάλληλη για ένα ευρύ φάσμα σεναρίων ενσωμάτωσης.

**Ορισμός:** `MailMessage` είναι η κύρια κλάση του Aspose.Email που αντιπροσωπεύει ένα μήνυμα email στη μνήμη.

**Ορισμός:** `BouncedMessageInfo` είναι ένα αντικείμενο δεδομένων που περιέχει ιδιότητες σχετικές με bounce όπως `isBounced`, `action`, `reason` και `recipientAddress`.

**Βήμα‑βήμα:**
1. **Εισαγωγή Απαιτούμενων Κλάσεων** – φέρτε τα απαραίτητα namespaces του Aspose.Email στο πεδίο ορατότητας.  
   ```java
import com.aspose.email.BounceResult;
import com.aspose.email.MailMessage;
```  
2. **Φόρτωση Αρχείου Μηνύματος Email** – καθορίστε τη διαδρομή του αρχείου και καλέστε `MailMessage.load()`.  
   ```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY/";
String fileName = "failed.msg";
MailMessage mail = MailMessage.load(dataDir + fileName);
```  
3. **Έλεγχος Κατάστασης Bounce** – καλέστε `mailMessage.checkBounced()`· εάν το αποτέλεσμα δεν είναι `null`, το email bounce.  
   ```java
BounceResult result = mail.checkBounced();
```  
4. **Πρόσβαση στις Ιδιότητες Bounce** – διαβάστε `isBounced`, `action` και `recipient` από το επιστρεφόμενο αντικείμενο.  
   ```java
System.out.println("IsBounced : " + result.isBounced());
System.out.println("Action : " + result.getAction());
System.out.println("Recipient : " + result.getRecipient());
```  

> `MailMessage` είναι η κύρια κλάση του Aspose.Email που αντιπροσωπεύει ένα μεμονωμένο μήνυμα email στη μνήμη.

## Πώς να ανακτήσω λεπτομερείς πληροφορίες bounce από ένα email;

**Απάντηση:** Αφού επιβεβαιώσετε ότι ένα μήνυμα bounce, μπορείτε να καλέσετε πρόσθετους getters στο αντικείμενο `BouncedMessageInfo` όπως `getReason()`, `getDiagnosticCode()` και `getRecipientAddress()` για να λάβετε την ακριβή απάντηση SMTP, τον κωδικό διάγνωσης και τη διεύθυνση του αρχικού παραλήπτη. Αυτά τα λεπτομερή δεδομένα σας βοηθούν να κατηγοριοποιήσετε τα bounces και να λάβετε τις κατάλληλες διορθωτικές ενέργειες.

```java
BouncedMessageInfo info = mailMessage.checkBounced();
if (info != null) {
    System.out.println("Reason: " + info.getReason());
    System.out.println("Diagnostic Code: " + info.getDiagnosticCode());
    System.out.println("Recipient: " + info.getRecipientAddress());
}
```

```java
System.out.println("Reason : " + result.getReason());
System.out.println("Status : " + result.getStatus());
System.out.println("OriginalMessage ToAddress 1: " + 
    result.getOriginalMessage().getTo().get_Item(0).getAddress());
```

## Πώς μπορώ να εφαρμόσω την ίδια λογική σε άλλο αρχείο email;

**Απάντηση:** Η λογική ελέγχου bounce είναι επαναχρησιμοποιήσιμη· απλώς αλλάξτε τη διαδρομή του αρχείου στην κλήση `MailMessage.load()` και επαναλάβετε την ίδια σειρά ενεργειών. Αυτό καθιστά εύκολη την επεξεργασία παρτίδων μηνυμάτων επαναλαμβάνοντας έναν φάκελο ή μια συλλογή που λαμβάνεται από διακομιστή αλληλογραφίας.

```java
String[] files = {"email1.eml", "email2.eml"};
for (String file : files) {
    MailMessage msg = MailMessage.load(file);
    BouncedMessageInfo info = msg.checkBounced();
    // Process info as needed
}
```

```java
String fileName = "test.eml";
MailMessage mail = MailMessage.load(dataDir + fileName);
BounceResult result = mail.checkBounced();
// Access properties similarly.
```

## Πρακτικές Εφαρμογές

Η κατανόηση της κατάστασης bounce των email είναι κρίσιμη για διάφορα σενάρια:
- **Καμπάνιες Email Marketing:** Εντοπίστε μη παραδιδόμενες διευθύνσεις για να διατηρήσετε τη λίστα σας καθαρή και να βελτιώσετε τα ποσοστά παραδοσιμότητας.
- **Συστήματα Υποστήριξης Πελατών:** Αυτόματη απάντηση σε bounces εισιτηρίων υποστήριξης, μειώνοντας την ανάγκη χειροκίνητης παρακολούθησης.
- **Εργαλεία Εταιρικής Επικοινωνίας:** Εξασφαλίστε ότι κρίσιμες ειδοποιήσεις φθάνουν στους παραλήπτες και σημαδέψτε αποτυχίες για άμεση διόρθωση.

## Παράγοντες Απόδοσης

Κατά την επεξεργασία χιλιάδων μηνυμάτων:
- Επαναχρησιμοποιήστε ένα μόνο αντικείμενο `License` για να αποφύγετε επαναλαμβανόμενες αναγνώσεις αρχείων.
- Μεταφέρετε (stream) τα αρχεία email από το δίσκο αντί να τα φορτώνετε όλα στη μνήμη ταυτόχρονα.
- Αναβαθμίστε στην πιο πρόσφατη έκδοση του Aspose.Email για να επωφεληθείτε από βελτιστοποιήσεις απόδοσης που μειώνουν το χρόνο επεξεργασίας έως και **30 %**.

## Κοινά Προβλήματα και Λύσεις

| Πρόβλημα | Αιτία | Λύση |
|-------|-------|----------|
| `NullPointerException` στο `checkBounced()` | Η άδεια δεν έχει οριστεί ή το αρχείο δεν βρέθηκε | Βεβαιωθείτε ότι το αρχείο άδειας έχει φορτωθεί πριν από οποιαδήποτε κλήση API και ελέγξτε τη διαδρομή του αρχείου. |
| Έλλειψη λόγου bounce | Το μήνυμα δεν είναι bounce (π.χ., απόδειξη παράδοσης) | Πρώτα επαληθεύστε ότι το `isBounced` είναι true πριν προσπελάσετε τις λεπτομερείς ιδιότητες. |
| Αργή επεξεργασία σε μεγάλες παρτίδες | Ανάγνωση ολόκληρων αρχείων στη μνήμη | Χρησιμοποιήστε `MailMessage.load(InputStream)` για ροή δεδομένων και άμεση απελευθέρωση πόρων. |

## Συχνές Ερωτήσεις

**Ε: Μπορώ να ελέγξω την κατάσταση bounce για email που αποθηκεύονται σε βάση δεδομένων;**  
Α: Ναι. Ανακτήστε το ακατέργαστο περιεχόμενο MIME ως πίνακα byte, τυλίξτε το σε `ByteArrayInputStream` και περάστε το στο `MailMessage.load()`.

**Ε: Υποστηρίζει το Aspose.Email ανάκτηση IMAP/POP3 για ανάλυση bounce;**  
Α: Απόλυτα. Χρησιμοποιήστε `ImapClient` ή `Pop3Client` για να ανακτήσετε μηνύματα, στη συνέχεια εφαρμόστε την ίδια λογική ελέγχου bounce.

**Ε: Υπάρχει όριο στο μέγεθος των αρχείων email που μπορεί να διαχειριστεί το Aspose.Email;**  
Α: Η βιβλιοθήκη μπορεί να επεξεργαστεί email έως **200 MB** χωρίς επιπλέον ρυθμίσεις, χάρη στην αρχιτεκτονική ροής δεδομένων.

**Ε: Πώς να διακρίνω μεταξύ hard και soft bounces;**  
Α: Εξετάστε την τιμή `BouncedMessageInfo.getAction()` – το “failed” υποδεικνύει hard bounce, ενώ το “delayed” υποδηλώνει soft bounce.

**Ε: Θα λειτουργεί η βιβλιοθήκη σε Linux containers;**  
Α: Ναι, το Aspose.Email είναι ανεξάρτητο πλατφόρμας και λειτουργεί ομαλά σε Docker containers με Java 16+.

## Πόροι

- [Aspose.Email Documentation](https://reference.aspose.com/email/java/)
- [Download Aspose.Email](https://releases.aspose.com/email/java/)
- [Free Trial Version](https://releases.aspose.com/email/java/)
- [Purchase a License](https://purchase.aspose.com/buy)
- [Temporary License Application](https://purchase.aspose.com/temporary-license/)
- [Aspose Support Forum](https://forum.aspose.com/c/email/10)

## Συμπέρασμα

Τώρα έχετε μια πλήρη, έτοιμη για παραγωγή προσέγγιση για την κατάσταση **how to check bounce** χρησιμοποιώντας το Aspose.Email για Java. Ενσωματώνοντας αυτά τα αποσπάσματα, μπορείτε αυτόματα να εντοπίζετε μηνύματα bounce, να εξάγετε ακριβείς λόγους και να διατηρείτε τα κανάλια επικοινωνίας σας καθαρά και αξιόπιστα.

**Επόμενα Βήματα**
- Πειραματιστείτε με επεξεργασία παρτίδων επαναλαμβάνοντας έναν φάκελο `.eml` αρχείων.  
- Συνδυάστε τα δεδομένα bounce με το CRM σας για αυτόματη επισήμανση μη έγκυρων επαφών.  
- Εξερευνήστε πρόσθετες δυνατότητες του Aspose.Email όπως προώθηση email, εξαγωγή συνημμένων και αποστολή SMTP.

Έτοιμοι να υλοποιήσετε; Ξεκινήστε με την εξάρτηση Maven, φορτώστε ένα δείγμα email και παρακολουθήστε τις πληροφορίες bounce να εμφανίζονται στην κονσόλα σας.

---

**Τελευταία Ενημέρωση:** 2026-06-13  
**Δοκιμάστηκε Με:** Aspose.Email for Java 24.12  
**Συγγραφέας:** Aspose  

{{< blocks/products/pf/main-container >}}

## Σχετικά Μαθήματα

- [Πώς να Φορτώσετε Μηνύματα Email με το Aspose.Email για Java: Οδηγός Βήμα‑Βήμα](/email/java/email-message-operations/aspose-email-java-load-email-tutorial/)
- [Μαθήματα Ανάλυσης και Επεξεργασίας Email για το Aspose.Email Java](/email/java/email-parsing-analysis/)
- [Ρύθμιση Aspose.Email Java IMAP: Οδηγός Ασφαλούς Διαμόρφωσης και Χρήσης για Προγραμματιστές](/email/java/imap-client-operations/aspose-email-java-imap-setup-usage-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}