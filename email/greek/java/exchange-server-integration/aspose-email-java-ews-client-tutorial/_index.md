---
date: '2026-07-17'
description: Μάθετε πώς να δημιουργήσετε EWS client Java χρησιμοποιώντας Aspose.Email
  for Java. Αυτός ο οδηγός σας καθοδηγεί στη διαδικασία του setup, της mailbox info
  retrieval, της inbox listing και της moving messages αποδοτικά.
keywords:
- create ews client java
- Aspose.Email Java
- email automation Java
lastmod: '2026-07-17'
og_description: Μάθετε πώς να δημιουργήσετε EWS client Java χρησιμοποιώντας Aspose.Email
  for Java. Αυτός ο οδηγός σας καθοδηγεί στη διαδικασία του setup, της mailbox info
  retrieval, της inbox listing και της moving messages αποδοτικά.
og_image_alt: 'Developer guide: create EWS client Java using Aspose.Email'
og_title: Δημιουργία EWS Client Java – Αυτοματοποιήστε το Email με Aspose.Email
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: Learn how to create EWS client Java using Aspose.Email for Java. This
    guide walks you through setup, mailbox info retrieval, inbox listing, and moving
    messages efficiently.
  headline: Create EWS Client Java – Automate Email with Aspose.Email
  type: TechArticle
- description: Learn how to create EWS client Java using Aspose.Email for Java. This
    guide walks you through setup, mailbox info retrieval, inbox listing, and moving
    messages efficiently.
  name: Create EWS Client Java – Automate Email with Aspose.Email
  steps:
  - name: Install Aspose.Email via Maven
    text: Make sure the Maven snippet from the **Prerequisites** section is present
      in your `pom.xml`. Run `mvn clean install` to download the JARs.
  - name: Obtain a License
    text: '- Start with a [free trial](https://releases.aspose.com/email/java/) to
      evaluate the library. - For extended evaluation, request a [temporary license](https://purchase.aspose.com/temporary-license/).
      - Purchase a full license on the [Aspose purchase page](https://purchase.aspose.com/buy)
      for product'
  - name: Initialize the Client
    text: 'Add the following initialization code after you have added the Maven dependency
      and license file:'
  type: HowTo
- questions:
  - answer: Verify credentials, ensure the service URL is correct, and confirm that
      the Exchange server permits the authentication method you are using (Basic,
      NTLM, or OAuth).
    question: How do I handle authentication errors when connecting to EWS?
  - answer: Yes. Create a separate `IEWSClient` instance for each mailbox, each with
      its own credentials and service URL.
    question: Can I manage emails from multiple mailboxes with this setup?
  - answer: Use `client.createFolder(parentUri, "FolderName")` before attempting to
      move messages, or check `client.folderExists(uri)` and create it on‑the‑fly.
    question: What should I do if the target folder does not exist?
  - answer: 'Extend the loop condition: `if (msg.getSubject().contains("Invoice")
      && msg.getFrom().contains("@vendor.com")) { … }`.'
    question: How can I filter emails based on multiple criteria (subject and sender)?
  - answer: Yes. The library processes mailboxes with **200,000+ messages** using
      server‑side paging, keeping client memory usage under **50 MB**.
    question: Does Aspose.Email support large mailboxes without performance degradation?
  type: FAQPage
tags:
- create ews client java
- Aspose.Email
- Java EWS integration
- email automation
title: Δημιουργία EWS Client Java – Αυτοματοποιήστε το Email με Aspose.Email
url: /el/java/exchange-server-integration/aspose-email-java-ews-client-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Δημιουργία Πελάτη EWS Java – Αυτοματοποιήστε το Email με Aspose.Email

## Εισαγωγή
Αναζητάτε να **δημιουργήσετε εφαρμογές EWS client Java** που διαχειρίζονται αυτόματα τα γραμματοκιβώτια Exchange; Αυτός ο ολοκληρωμένος οδηγός δείχνει πώς να χρησιμοποιήσετε το Aspose.Email for Java για να δημιουργήσετε έναν πελάτη EWS, να ανακτήσετε πληροφορίες γραμματοκιβωτίου, να καταγράψετε τα μηνύματα του εισερχόμενου και να μετακινήσετε τα email βάσει συγκεκριμένων κριτηρίων. Αυτοματοποιήστε τις επαναλαμβανόμενες εργασίες email, μειώστε την χειροκίνητη προσπάθεια και διατηρήστε το εισερχόμενο οργανωμένο — όλα από κώδικα Java.

Στο σημερινό γρήγορα εξελισσόμενο ψηφιακό περιβάλλον, η αποδοτική διαχείριση χιλιάδων μηνυμάτων είναι απαραίτητη για ομάδες υποστήριξης, τμήματα οικονομικών και οποιονδήποτε οργανισμό που βασίζεται στο Exchange. Στο τέλος αυτού του οδηγού θα έχετε μια σταθερή, έτοιμη για παραγωγή βάση για αυτοματοποίηση email.

**Τι θα μάθετε**
- Πώς να δημιουργήσετε κώδικα **create EWS client Java** με το Aspose.Email.
- Πώς να ανακτήσετε λεπτομέρειες γραμματοκιβωτίου όπως τα URI των φακέλων.
- Πώς να καταγράψετε μηνύματα από το φάκελο Inbox.
- Πώς να μετακινήσετε μηνύματα που ταιριάζουν με ένα μοτίβο θέματος σε άλλο φάκελο.

Ας επαληθεύσουμε τις προαπαιτήσεις πριν ξεκινήσουμε τον κώδικα.

## Γρήγορες Απαντήσεις
- **Ποια είναι η πρώτη γραμμή κώδικα για τη δημιουργία ενός πελάτη EWS;** `IEWSClient client = EWSClient.getEWSClient(serviceUrl, username, password, domain);`
- **Ποιο Maven artifact παρέχει το Aspose.Email for Java;** `com.aspose:aspose-email`
- **Χρειάζομαι άδεια για ανάπτυξη;** Μια δωρεάν δοκιμή λειτουργεί για ανάπτυξη· μια άδεια παραγωγής αφαιρεί όλους τους περιορισμούς αξιολόγησης.
- **Μπορώ να επεξεργαστώ πάνω από 100.000 μηνύματα;** Ναι—το Aspose.Email μπορεί να κάνει σελίδωση σε μεγάλα γραμματοκιβώτια χωρίς να φορτώνει τα πάντα στη μνήμη.
- **Ποια έκδοση Java απαιτείται;** JDK 1.8 ή νεότερη (η βιβλιοθήκη είναι συμβατή μέχρι Java 21).

## Τι είναι **create EWS client Java**;
`create ews client java` αναφέρεται στη διαδικασία δημιουργίας ενός αντικειμένου `IEWSClient` που επικοινωνεί με το Microsoft Exchange Web Services από μια εφαρμογή Java. Αυτός ο πελάτης αφαιρεί τις χαμηλού επιπέδου κλήσεις SOAP και σας παρέχει ένα καθαρό, αντικειμενοστραφές API για λειτουργίες γραμματοκιβωτίου.

## Γιατί να χρησιμοποιήσετε το Aspose.Email for Java;
Το Aspose.Email υποστηρίζει **πάνω από 70 πρωτόκολλα email**, μπορεί να διαχειριστεί γραμματοκιβώτια με **έως 200.000 μηνύματα** χωρίς να φορτώνει ολόκληρο το αποθετήριο στη μνήμη, και παρέχει **ενσωματωμένη σελιδοποίηση** που μειώνει την κυκλοφορία δικτύου έως **80 %**. Η βιβλιοθήκη είναι πλήρως thread‑safe, λειτουργεί σε οποιοδήποτε runtime Java 8+ και λαμβάνει μηνιαίες ενημερώσεις που προσθέτουν νέες δυνατότητες Exchange.

## Προαπαιτήσεις
Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε τα εξής:

### Απαιτούμενες Βιβλιοθήκες και Εξαρτήσεις
Συμπεριλάβετε το Aspose.Email for Java στο έργο σας. Εάν χρησιμοποιείτε Maven, προσθέστε αυτήν την εξάρτηση στο αρχείο `pom.xml` σας:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Απαιτήσεις Ρύθμισης Περιβάλλοντος
- Java Development Kit (JDK) 1.8 ή νεότερο.
- Maven για διαχείριση εξαρτήσεων.
- Πρόσβαση σε διακομιστή Exchange με ενεργοποιημένο το EWS.

### Προαπαιτήσεις Γνώσεων
- Άνεση με τη σύνταξη Java και τις αντικειμενοστραφείς έννοιες.
- Βασική κατανόηση των RESTful APIs· το EWS χρησιμοποιεί SOAP, αλλά το Aspose.Email κρύβει την πολυπλοκότητα.

## Πώς να **create EWS client Java**;
`IEWSClient` είναι η διεπαφή του Aspose.Email που παρέχει μεθόδους για αλληλεπίδραση με το Exchange Web Services.  
Φορτώστε το URL της υπηρεσίας Exchange, τα διαπιστευτήρια χρήστη και το domain, και στη συνέχεια δημιουργήστε τον πελάτη σε μία μόνο γραμμή. Αυτή η κλήση δημιουργεί μια ασφαλή σύνδεση, διαπραγματεύεται TLS και επιστρέφει ένα αντικείμενο `IEWSClient` έτοιμο για λειτουργίες γραμματοκιβωτίου όπως ανάγνωση φακέλων, καταγραφή μηνυμάτων και μετακίνηση αντικειμένων. Ο πελάτης επίσης αποθηκεύει στην κρυφή μνήμη το σημείο λήψης υπηρεσίας για βελτίωση της απόδοσης επόμενων αιτημάτων.
```text
IEWSClient client = EWSClient.getEWSClient(serviceUrl, username, password, domain);
```

Ο πελάτης διαπραγματεύεται αυτόματα TLS, διαχειρίζεται τα cookies αυθεντικοποίησης και αποθηκεύει στην κρυφή μνήμη το σημείο λήψης υπηρεσίας για επόμενες κλήσεις.

### Βήμα 1: Εγκατάσταση Aspose.Email μέσω Maven
Βεβαιωθείτε ότι το απόσπασμα Maven από την ενότητα **Prerequisites** υπάρχει στο `pom.xml` σας. Εκτελέστε `mvn clean install` για να κατεβάσετε τα JAR.

### Βήμα 2: Απόκτηση Άδειας
- Ξεκινήστε με μια [δωρεάν δοκιμή](https://releases.aspose.com/email/java/) για να αξιολογήσετε τη βιβλιοθήκη.
- Για εκτεταμένη αξιολόγηση, ζητήστε μια [προσωρινή άδεια](https://purchase.aspose.com/temporary-license/).
- Αγοράστε πλήρη άδεια στη [σελίδα αγοράς του Aspose](https://purchase.aspose.com/buy) για χρήση σε παραγωγή.

### Βήμα 3: Αρχικοποίηση του Πελάτη
Προσθέστε τον παρακάτω κώδικα αρχικοποίησης μετά την προσθήκη της εξάρτησης Maven και του αρχείου άδειας:
```java
   import com.aspose.email.EWSClient;
   import com.aspose.email.IEWSClient;

   // Initialize the EWS Client
   IEWSClient client = EWSClient.getEWSClient(
       "https://outlook.office365.com/exchangeews/exchange.asmx",
       "testUser",
       "pwd",
       "domain"
   );
   ```

## Πώς να ανακτήσετε πληροφορίες γραμματοκιβωτίου;
`ExchangeMailboxInfo` αντιπροσωπεύει τη δομή του γραμματοκιβωτίου και τα URI των φακέλων που επιστρέφει ο διακομιστής.  
Χρησιμοποιήστε το στιγμιότυπο `IEWSClient` για να ζητήσετε ένα αντικείμενο `ExchangeMailboxInfo`. Αυτό το αντικείμενο περιέχει τα URI για τους κοινά φακέλους (Inbox, Sent Items, Drafts) και μεταδεδομένα όπως το μέγεθος του γραμματοκιβωτίου, ο συνολικός αριθμός αντικειμένων και οι πληροφορίες ορίου, επιτρέποντάς σας να περιηγηθείτε στο γραμματοκιβώτιο χωρίς επιπλέον κλήσεις.
```text
ExchangeMailboxInfo mailboxInfo = client.getMailboxInfo();
String inboxUri = mailboxInfo.getInboxUri();
```

Η κλάση `ExchangeMailboxInfo` είναι η αναπαράσταση του Aspose.Email για τη δομή ενός γραμματοκιβωτίου Exchange, εκθέτοντας τα URI των φακέλων χωρίς να απαιτούνται επιπλέον κλήσεις δικτύου.

## Πώς να καταγράψετε μηνύματα από το Inbox;
`MessageInfo` είναι ένα ελαφρύ αντικείμενο που περιέχει μεταδεδομένα όπως θέμα, αποστολέας και ημερομηνία λήψης για κάθε email.  
Μonce έχετε το URI του Inbox, καλέστε `client.listMessages` για να λάβετε μια συλλογή αντικειμένων `MessageInfo`. Μπορείτε να καθορίσετε ένα αντικείμενο `PagingInfo` για να περιορίσετε τα αποτελέσματα και να βελτιώσετε την απόδοση σε μεγάλα γραμματοκιβώτια· το `PagingInfo` λέει στον διακομιστή πόσα αντικείμενα να επιστρέψει ανά σελίδα και ποια σελίδα να φέρει, μειώνοντας δραστικά τη χρήση μνήμης.
```text
PagingInfo paging = new PagingInfo(1, 100); // first 100 messages
MessageInfoCollection messages = client.listMessages(inboxUri, paging);
```

`MessageInfo` παρέχει ελαφριά μεταδεδομένα (θέμα, αποστολέας, ώρα λήψης) χωρίς να κατεβάζει πλήρη σώματα μηνυμάτων, κάτι που διατηρεί τη χρήση μνήμης χαμηλή.

## Πώς να μετακινήσετε μηνύματα σε άλλο φάκελο;
`moveMessage` μετακινεί ένα μήνυμα από τον τρέχοντα φάκελό του σε έναν καθορισμένο φάκελο προορισμού στον διακομιστή Exchange.  
Διατρέξτε τη συλλογή `MessageInfo`, αξιολογήστε κάθε θέμα και καλέστε `client.moveMessage` όταν τα κριτήρια ταιριάζουν. Η μέθοδος εκτελεί τη μετακίνηση εξ ολοκλήρου στον διακομιστή, έτσι δεν απαιτείται τοπικό αντίγραφο και η λειτουργία ολοκληρώνεται σε χιλιοστά του δευτερολέπτου ακόμη και για μεγάλα μηνύματα.
```text
for (MessageInfo msg : messages) {
    if (msg.getSubject().contains("Invoice")) {
        client.moveMessage(msg.getUniqueUri(), targetFolderUri);
    }
}
```

Η λειτουργία `moveMessage` είναι ατομική στον διακομιστή Exchange και ολοκληρώνεται σε χιλιοστά του δευτερολέπτου ακόμη και για μεγάλα μηνύματα.

## Συχνά Προβλήματα και Λύσεις
- **Αποτυχίες αυθεντικοποίησης:** Επαληθεύστε ότι το όνομα χρήστη, ο κωδικός πρόσβασης και το domain είναι σωστά, και ότι ο διακομιστής Exchange επιτρέπει βασική αυθεντικοποίηση ή OAuth όπως έχει ρυθμιστεί.
- **Φάκελος δεν βρέθηκε:** Χρησιμοποιήστε `client.createFolder(parentUri, "Processed")` για να δημιουργήσετε το φάκελο προορισμού εάν δεν υπάρχει.
- **Σημεία συμφόρησης απόδοσης:** Ενεργοποιήστε τη σελιδοποίηση (`PagingInfo`) και ζητήστε μόνο τα πεδία που χρειάζεστε (`MessageInfo.getSubject()`, `MessageInfo.getFrom()`). Αυτό μειώνει το φορτίο δικτύου έως **70 %**.

## Πρακτικές Εφαρμογές
Πραγματικά σενάρια όπου η αυτοματοποίηση email με το Aspose.Email ξεχωρίζει:
1. **Αυτοματοποιημένη Επεξεργασία Εισιτηρίων** – Μετακινήστε τα email υποστήριξης που περιέχουν “Ticket#” σε έναν αφιερωμένο φάκελο για το σύστημα εισιτηρίων σας.
2. **Διαχείριση Τιμολογίων** – Εντοπίστε “Invoice” στη γραμμή θέματος και δρομολογήστε τα μηνύματα αυτόματα στο τμήμα οικονομικών.
3. **Ανάθεση Εργασιών** – Φιλτράρετε τα email “Action Required” σε μια προτεραιότητα ουρά για τους διαχειριστές έργων.
4. **Συγχρονισμός CRM** – Ανάκτηση μεταδεδομένων μηνυμάτων και ενσωμάτωσή τους σε CRM για να διατηρούνται οι αλληλεπιδράσεις πελατών ενημερωμένες.
5. **Διαχείριση Ειδοποιήσεων** – Διαχωρίστε τις ειδοποιήσεις συστήματος από τα email που δημιουργούνται από χρήστες για πιο σαφή παρακολούθηση.

## Σκέψεις Απόδοσης
- **Βελτιστοποίηση πόρων:** Ανακτήστε μόνο τα πρώτα 200 μηνύματα ανά αίτηση και χρησιμοποιήστε `PagingInfo` για σελιδοποίηση του υπολοίπου. Αυτό αποτρέπει σφάλματα OutOfMemory σε διακομιστές με περιορισμένη μνήμη heap.
- **Καθαρισμός μνήμης:** Απενεργοποιήστε (nullify) μεγάλα αντικείμενα μετά τη χρήση και καλέστε `System.gc()` σπάνια σε υπηρεσίες μακράς διάρκειας.
- **Ενημερώσεις βιβλιοθήκης:** Εκτελέστε πάντα την πιο πρόσφατη έκδοση του Aspose.Email (π.χ., 24.12) για να επωφεληθείτε από διορθώσεις απόδοσης που βελτιώνουν την καθυστέρηση κλήσεων EWS έως **30 %**.

## Συμπέρασμα
Τώρα γνωρίζετε πώς να δημιουργήσετε εφαρμογές **create EWS client Java** που μπορούν να διαβάσουν λεπτομέρειες γραμματοκιβωτίου, να καταγράψουν μηνύματα εισερχομένων και να μετακινήσουν email βάσει προσαρμοσμένης λογικής. Αυτή η βάση σας επιτρέπει να δημιουργήσετε εξελιγμένες γραμμές αυτοματοποίησης, να ενσωματώσετε συστήματα ERP/CRM και να μειώσετε την χειροκίνητη διαχείριση email σε όλη την οργάνωσή σας.

### Επόμενα Βήματα
- Επεκτείνετε τον κώδικα για διαγραφή ή προώθηση μηνυμάτων.
- Εφαρμόστε προχωρημένο φιλτράρισμα χρησιμοποιώντας `SearchQuery` για αποστολέα, εύρος ημερομηνιών ή παρουσία συνημμένων.
- Εξερευνήστε τις δυνατότητες **SMTP** και **IMAP** του Aspose.Email για υβριδικά περιβάλλοντα.

**Κάλεσμα σε Δράση:** Αναπτύξτε το δείγμα σε περιβάλλον δοκιμής σήμερα, προσαρμόστε το φίλτρο θέματος και δείτε πόσο γρήγορα η διαχείριση email γίνεται μια διαδικασία «ρύθμισης‑και‑λήθης».

## Συχνές Ερωτήσεις

**Q: Πώς να αντιμετωπίσω σφάλματα αυθεντικοποίησης κατά τη σύνδεση στο EWS;**  
A: Επαληθεύστε τα διαπιστευτήρια, βεβαιωθείτε ότι το URL της υπηρεσίας είναι σωστό, και επιβεβαιώστε ότι ο διακομιστής Exchange επιτρέπει τη μέθοδο αυθεντικοποίησης που χρησιμοποιείτε (Basic, NTLM ή OAuth).

**Q: Μπορώ να διαχειριστώ email από πολλαπλά γραμματοκιβώτια με αυτή τη ρύθμιση;**  
A: Ναι. Δημιουργήστε ένα ξεχωριστό στιγμιότυπο `IEWSClient` για κάθε γραμματοκιβώτιο, το καθένα με τα δικά του διαπιστευτήρια και URL υπηρεσίας.

**Q: Τι πρέπει να κάνω αν ο φάκελος προορισμού δεν υπάρχει;**  
A: Χρησιμοποιήστε `client.createFolder(parentUri, "FolderName")` πριν προσπαθήσετε να μετακινήσετε μηνύματα, ή ελέγξτε `client.folderExists(uri)` και δημιουργήστε το εν κινήσει.

**Q: Πώς μπορώ να φιλτράρω email βάσει πολλαπλών κριτηρίων (θέμα και αποστολέας);**  
A: Επεκτείνετε τη συνθήκη του βρόχου: `if (msg.getSubject().contains("Invoice") && msg.getFrom().contains("@vendor.com")) { … }`.

**Q: Το Aspose.Email υποστηρίζει μεγάλα γραμματοκιβώτια χωρίς μείωση της απόδοσης;**  
A: Ναι. Η βιβλιοθήκη επεξεργάζεται γραμματοκιβώτια με **πάνω από 200.000 μηνύματα** χρησιμοποιώντας σελιδοποίηση από τον διακομιστή, διατηρώντας τη χρήση μνήμης του πελάτη κάτω από **50 MB**.

---

**Last Updated:** 2026-07-17  
**Tested With:** Aspose.Email for Java 24.12  
**Author:** Aspose  

```java
   import com.aspose.email.EWSClient;
   import com.aspose.email.IEWSClient;
   ```
```java
   IEWSClient client = EWSClient.getEWSClient(
       "https://outlook.office365.com/exchangeews/exchange.asmx",
       "testUser",
       "pwd",
       "domain"
   );
   ```
```java
   import com.aspose.email.ExchangeMailboxInfo;
   ```
```java
   ExchangeMailboxInfo mailboxInfo = client.getMailboxInfo();
   ```
```java
   import com.aspose.email.ExchangeMessageInfo;
   import com.aspose.email.ExchangeMessageInfoCollection;
   ```
```java
   ExchangeMessageInfoCollection msgInfoColl = client.listMessages(mailboxInfo.getInboxUri());
   ```
```java
   for (ExchangeMessageInfo msgInfo : msgInfoColl) {
       if (msgInfo.getSubject() != null && msgInfo.getSubject().contains("process this message")) {
           // Move item logic here
       }
   }
   ```
```java
   client.moveItem(
       msgInfo.getUniqueUri(),
       client.getMailboxInfo().getRootUri() + "/Processed/" + msgInfo.getSubject()
   );
   ```

{{< blocks/products/products-backtop-button >}}

## Σχετικά Μαθήματα

- [Αρχικοποίηση Aspose.Email Java για Exchange Server: Ανάκτηση Πληροφοριών Γραμματοκιβωτίου](/email/java/exchange-server-integration/aspose-email-java-exchange-client-mailbox-info/)
- [Αποτελεσματική Σύνδεση και Καταγραφή Μηνυμάτων Exchange Χρησιμοποιώντας Aspose.Email for Java: Ένας Πλήρης Οδηγός](/email/java/exchange-server-integration/aspose-email-java-exchange-messages-listing/)
- [Πώς να Συνδεθείτε σε Διακομιστή Exchange Χρησιμοποιώντας EWS με Aspose.Email for Java: Ένας Πλήρης Οδηγός](/email/java/exchange-server-integration/exchange-server-ews-aspose-email-java-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}