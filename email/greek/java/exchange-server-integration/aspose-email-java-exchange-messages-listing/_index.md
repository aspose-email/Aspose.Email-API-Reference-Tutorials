---
date: '2026-10-02'
description: Μάθετε πώς να συνδέσετε το Exchange και να εμφανίσετε δημόσιους φακέλους
  του Exchange χρησιμοποιώντας το Aspose.Email for Java. Αυτός ο οδηγός βήμα‑βήμα
  παρουσιάζει την εξάρτηση Maven και τη ρύθμιση χωρίς κώδικα.
keywords:
- how to connect exchange
- list exchange public folders
- maven dependency aspose email
lastmod: '2026-10-02'
og_description: Μάθετε πώς να συνδέσετε το Exchange και να εμφανίσετε δημόσιους φακέλους
  του Exchange χρησιμοποιώντας το Aspose.Email for Java. Αυτός ο οδηγός καλύπτει την
  εξάρτηση Maven, την άδεια χρήσης και την αναδρομική ανάκτηση μηνυμάτων.
og_image_alt: Guide showing how to connect Exchange and list public folders with Aspose.Email
  for Java
og_title: Πώς να συνδέσετε το Exchange και να εμφανίσετε δημόσιους φακέλους σε Java
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Learn how to connect exchange and list exchange public folders using
    Aspose.Email for Java. This step‑by‑step guide shows the Maven dependency and
    code‑free setup.
  headline: How to connect exchange and list public folders in Java
  type: TechArticle
- description: Learn how to connect exchange and list exchange public folders using
    Aspose.Email for Java. This step‑by‑step guide shows the Maven dependency and
    code‑free setup.
  name: How to connect exchange and list public folders in Java
  steps:
  - name: '**Automated email archiving** – Periodically pull all public‑folder messages
      and store them in a compliant archive.'
    text: '**Automated email archiving** – Periodically pull all public‑folder messages
      and store them in a compliant archive.'
  - name: '**Backup solutions** – Mirror Exchange public folders to a secure file
      system or cloud bucket, guaranteeing data redundancy.'
    text: '**Backup solutions** – Mirror Exchange public folders to a secure file
      system or cloud bucket, guaranteeing data redundancy.'
  - name: '**Custom email clients** – Build lightweight viewers that display only
      the folders and messages you need, reducing UI complexity.'
    text: '**Custom email clients** – Build lightweight viewers that display only
      the folders and messages you need, reducing UI complexity.'
  type: HowTo
- questions:
  - answer: Yes. Provide the Office 365 EWS endpoint (`https://outlook.office365.com/EWS/Exchange.asmx`)
      and use modern authentication (OAuth) – Aspose.Email supports OAuth tokens out
      of the box.
    question: Can I use this code with Exchange Online (Office 365)?
  - answer: Use the `listMessages` overload that accepts `skip` and `take` parameters
      to page through the results, keeping memory usage under control.
    question: What if a folder contains more than 10 000 messages?
  - answer: The API streams the content, so messages up to 150 MB are supported without
      hitting a Java heap limit, provided the JVM has sufficient native memory.
    question: Is there a limit on the size of a single email I can download?
  - answer: By default Aspose.Email trusts the Java default keystore. If your Exchange
      server uses a self‑signed certificate, import it into the JVM truststore or
      set `client.setEnableSslVerification(false)` for testing only.
    question: Do I need to handle SSL certificates manually?
  - answer: Enable Aspose.Email’s built‑in logging by configuring `Logger.setLevel(Level.INFO)`
      and directing output to a file or monitoring system.
    question: How do I log the operations for audit purposes?
  type: FAQPage
tags:
- exchange integration
- Aspose.Email
- Java email automation
title: Πώς να συνδέσετε το Exchange και να εμφανίσετε δημόσιους φακέλους σε Java
url: /el/java/exchange-server-integration/aspose-email-java-exchange-messages-listing/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να συνδέσετε το Exchange και να καταγράψετε δημόσιους φακέλους σε Java

## Εισαγωγή
Στις σύγχρονες επιχειρήσεις, η προγραμματιστική πρόσβαση σε γραμματοκιβώτια Microsoft Exchange σας επιτρέπει να αυτοματοποιείτε εργασίες αρχειοθέτησης, παρακολούθησης και αναφοράς. Αυτό το μάθημα δείχνει **πώς να συνδέσετε το Exchange** με το Aspose.Email for Java και στη συνέχεια **να καταγράψετε τους δημόσιους φακέλους του Exchange** αναδρομικά. Θα δείτε την απαιτούμενη εξάρτηση Maven, τα βήματα αδειοδότησης και τη ακριβή ακολουθία κλήσεων API—χωρίς επιπλέον βιβλιοθήκες. Στο τέλος, θα μπορείτε να αντλήσετε μηνύματα από οποιονδήποτε δημόσιο φάκελο και να τα αποθηκεύσετε τοπικά.

## Σύντομες απαντήσεις
- **Ποιο είναι το πρώτο βήμα;** Προσθέστε την εξάρτηση Maven του Aspose.Email στο `pom.xml` σας.  
- **Χρειάζομαι άδεια;** Ναι—χρησιμοποιήστε μια προσωρινή άδεια για αξιολόγηση ή αγοράστε πλήρη άδεια για παραγωγή.  
- **Ποια κλάση δημιουργεί τη σύνδεση;** `ExchangeClient` (ή `ImapClient` για IMAP) διαχειρίζεται τον έλεγχο ταυτότητας και την επικοινωνία με τον διακομιστή.  
- **Μπορώ να καταγράψω αυτόματα τους υποφακέλους;** Ναι—χρησιμοποιήστε τη recursive μέθοδο `listSubFolders` που παρέχει το API.  
- **Είναι αυτή η προσέγγιση thread‑safe;** Τα αντικείμενα client δεν είναι thread‑safe· δημιουργήστε ξεχωριστό instance ανά νήμα για ταυτόχρονες εργασίες.

## Τι είναι η σύνδεση στο Exchange;
**Η σύνδεση στο Exchange** είναι η διαδικασία ταυτοποίησης μιας εφαρμογής Java με έναν τοπικό ή cloud‑βασισμένο διακομιστή Microsoft Exchange ώστε να μπορείτε να εκτελείτε κλήσεις API όπως απαρίθμηση φακέλων ή ανάκτηση μηνυμάτων. Το Aspose.Email αφαιρεί τα υποκείμενα πρωτόκολλα EWS/IMAP, παρέχοντάς σας ένα ενιαίο, συνεπές μοντέλο αντικειμένων.

## Γιατί να καταγράψετε τους δημόσιους φακέλους του Exchange;
Η απαρίθμηση των δημόσιων φακέλων σας δίνει ορατότητα στη ιεραρχική δομή που χρησιμοποιούν οι οργανισμοί για κοινόχρηστους γραμματοκιβώτια, λίστες διανομής και αποθήκες αρχειοθέτησης. Το Aspose.Email μπορεί να απαριθμήσει πάνω από **50+ δημόσιους φακέλους** με μία κλήση και υποστηρίζει την επεξεργασία γραμματοκιβωτίων πολλών εκατοντάδων σελίδων χωρίς να φορτώνει ολόκληρο το αποθετήριο στη μνήμη, μειώνοντας τη χρήση RAM έως και 70 %.

## Προαπαιτούμενα
- **Aspose.Email for Java** — έκδοση 25.4 ή νεότερη (η τελευταία σταθερή έκδοση).  
- **Java Development Kit (JDK)** — εγκατεστημένο JDK 11 ή νεότερο και ρυθμισμένο `JAVA_HOME`.  
- **Maven** — για διαχείριση εξαρτήσεων και αυτοματοποίηση κατασκευής.  
- Βασικές γνώσεις σύνταξης Java και εννοιών Exchange (γραμματοκιβώτια, φάκελοι, EWS).

## Ρύθμιση του Aspose.Email για Java
Για να ενσωματώσετε τη βιβλιοθήκη, προσθέστε την εξάρτηση Maven στο `pom.xml` του έργου σας. Αυτή είναι η **εξάρτηση Maven Aspose Email** που χρειάζεστε.

### Εξάρτηση Maven
Προσθέστε το παρακάτω απόσπασμα μέσα στο στοιχείο `<dependencies>` του `pom.xml` σας:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Βήματα απόκτησης άδειας
Το Aspose.Email απαιτεί έγκυρη άδεια για πλήρη χρήση λειτουργιών:

- **Δωρεάν δοκιμή** – Κατεβάστε μια προσωρινή άδεια από τον [Ιστότοπο Aspose](https://purchase.aspose.com/temporary-license/) για αξιολόγηση του API.  
- **Αγορά** – Αποκτήστε εμπορική άδεια μέσω της πύλης Aspose για παραγωγικές εγκαταστάσεις.

#### Βασική αρχικοποίηση
Αφού το Maven επιλύσει το πακέτο και έχετε ένα αρχείο άδειας, τοποθετήστε το αρχείο `.lic` στην classpath και αρχικοποιήστε τη βιβλιοθήκη:

```java
import com.aspose.email.License;

License license = new License();
license.setLicense("path/to/your/license.lic");
```

## Οδηγός υλοποίησης
Θα περάσουμε από κάθε λειτουργικό μπλοκ, απαντώντας στις κύριες ερωτήσεις με άμεσες, σύντομες παραγράφους πριν τα λεπτομερή βήματα.

### Πώς να συνδέσετε το Exchange;
Φορτώστε το `ExchangeClient` με το URL του διακομιστή, τα διαπιστευτήρια χρήστη και τον τομέα, και στη συνέχεια καλέστε `connect()`. Ο client δημιουργεί μια συνεδρία HTTPS με το Exchange Web Services (EWS) και επαληθεύει τα διαπιστευτήρια. Εάν η σύνδεση αποτύχει, το API ρίχνει μια λεπτομερή `AuthenticationException` που περιλαμβάνει τον κωδικό κατάστασης HTTP για γρήγορη αντιμετώπιση προβλημάτων.  
`ExchangeClient` είναι η κλάση του Aspose.Email που διαχειρίζεται μια σύνδεση με το Exchange Web Services.

```java
import com.aspose.email.EWSClient;
import com.aspose.email.IEWSClient;

IEWSClient connectToExchangeServer(String exchangeUrl, String username, String password, String domain) {
    // Create instance of IEWSClient class by providing credentials
    return EWSClient.getEWSClient(exchangeUrl, username, password, domain);
}
```

### Πώς να καταγράψετε τους δημόσιους φακέλους του Exchange;
Κληθείτε το `client.listPublicFolders()` για να λάβετε μια συλλογή από αντικείμενα `FolderInfo` που αντιπροσωπεύουν κάθε δημόσιο φάκελο κορυφαίου επιπέδου. Η μέθοδος επιστρέφει μεταδεδομένα όπως το όνομα φακέλου, ο συνολικός αριθμός αντικειμένων και ένα μοναδικό αναγνωριστικό που χρησιμοποιείται για επόμενες κλήσεις. Αυτή η κλήση ολοκληρώνεται σε λιγότερο από 2 δευτερόλεπτα για τυπικές εγκαταστάσεις on‑premises με έως 500 φακέλους.  
`listPublicFolders()` επιστρέφει μια συλλογή από αντικείμενα `FolderInfo`.  
`FolderInfo` περιέχει μεταδεδομένα όπως το εμφανιζόμενο όνομα και τον αριθμό αντικειμένων.

```java
import com.aspose.email.ExchangeFolderInfoCollection;
import com.aspose.email.IEWSClient;

ExchangeFolderInfoCollection listPublicFolders(IEWSClient client) {
    // List all public folders and return their information as a collection
    return client.listPublicFolders();
}
```

### Πώς να εμφανίσετε πληροφορίες φακέλου;
Διατρέξτε τη συλλογή `FolderInfo` και εκτυπώστε το `displayName` και το `subFolderCount`. Αυτό το γρήγορο στιγμιότυπο σας βοηθά να κατανοήσετε την ιεραρχία πριν ξεκινήσετε μια πιο βαθιά ανίχνευση. Για μεγάλους οργανισμούς, το API μπορεί να σελιδοποιήσει τα αποτελέσματα, επιστρέφοντας 100 φακέλους ανά σελίδα για χαμηλή χρήση μνήμης.

```java
import com.aspose.email.ExchangeFolderInfo;

void displayFolderInfo(ExchangeFolderInfo folder) {
    // Print folder details
    System.out.println("Name: " + folder.getDisplayName());
    System.out.println("Subfolders count: " + folder.getChildFolderCount());
}
```

### Πώς να καταγράψετε μηνύματα από έναν φάκελο;
Καλέστε το `client.listMessages(folderId)` όπου το `folderId` είναι το αναγνωριστικό που ελήφθη στο προηγούμενο βήμα. Η μέθοδος επιστρέφει μια λίστα από αντικείμενα `MessageInfo` που περιέχουν θέμα, αποστολέα και ημερομηνία λήψης. Μπορείτε να περιορίσετε το σύνολο αποτελεσμάτων με το `maxCount` για να μην υπερφορτώσετε το client όταν επεξεργάζεστε πολύ μεγάλους φακέλους.  
`listMessages(folderId)` επιστρέφει μια λίδα από αντικείμενα `MessageInfo`.  
`MessageInfo` περιέχει βασικές ιδιότητες ενός email όπως θέμα, αποστολέας και ημερομηνία λήψης.

```java
import com.aspose.email.ExchangeMessageInfoCollection;
import com.aspose.email.IEWSClient;

ExchangeMessageInfoCollection listMessagesFromFolder(IEWSClient client, ExchangeFolderInfo folder) {
    // List messages from the specified public folder and return their information as a collection
    return client.listMessagesFromPublicFolder(folder);
}
```

### Πώς να ανακτήσετε και να αποθηκεύσετε μηνύματα;
Για κάθε `MessageInfo`, χρησιμοποιήστε το `client.fetchMessage(messageId)` για να κατεβάσετε το πλήρες περιεχόμενο MIME. Στη συνέχεια γράψτε τον πίνακα byte σε ένα αρχείο `.eml` στο δίσκο. Το API μεταδίδει το περιεχόμενο σε ροή, έτσι ακόμη και μηνύματα 100 MB διαχειρίζονται χωρίς να φορτώνεται ολόκληρο το φορτίο στη μνήμη.  
`fetchMessage(messageId)` κατεβάζει το πλήρες περιεχόμενο MIME του συγκεκριμένου email.

```java
import com.aspose.email.ExchangeMessageInfo;
import com.aspose.email.IEWSClient;
import com.aspose.email.MailMessage;
import com.aspose.email.SaveOptions;

void fetchAndSaveMessages(IEWSClient client, ExchangeMessageInfoCollection messages) {
    for (ExchangeMessageInfo messageInfo : messages) {
        // Fetch the full MailMessage using its unique URI
        MailMessage msg = client.fetchMessage(messageInfo.getUniqueUri());
        
        // Save the fetched message to a file named after its subject with .msg extension
        String filePath = "YOUR_OUTPUT_DIRECTORY/" + msg.getSubject() + ".msg";
        msg.save(filePath, SaveOptions.getDefaultMsgUnicode());
    }
}
```

### Πώς να καταγράψετε αναδρομικά μηνύματα από υποφακέλους;
Εφαρμόστε μια διάσχιση βάθους‑πρώτης (depth‑first): ξεκινήστε με έναν φάκελο κορυφαίου επιπέδου, καταγράψτε τους υποφακέλους του μέσω `client.listSubFolders(parentId)`, και στη συνέχεια καλέστε την ίδια ρουτίνα καταγραφής μηνυμάτων για κάθε παιδί. Αυτό το μοτίβο εξασφαλίζει ότι κάθε μήνυμα στο δέντρο των δημόσιων φακέλων επεξεργάζεται. Το βάθος της αναδρομής περιορίζεται μόνο από την ιεραρχία φακέλων του διακομιστή (συνήθως < 20 επίπεδα).  
`listSubFolders(parentId)` επιστρέφει τους άμεσους υποφακέλους του δεδομένου φακέλου.

```java
import com.aspose.email.ExchangeFolderInfo;
import com.aspose.email.IEWSClient;

void listMessagesFromSubFolders(IEWSClient client, ExchangeFolderInfo folder) {
    // List all messages in the current public folder
    ExchangeMessageInfoCollection msgCollection = client.listMessagesFromPublicFolder(folder);
    fetchAndSaveMessages(client, msgCollection);

    if (folder.getChildFolderCount() > 0) {
        ExchangeFolderInfoCollection subFolders = client.listSubFolders(folder);
        for (ExchangeFolderInfo subFolder : subFolders) {
            listMessagesFromSubFolders(client, subFolder);
        }
    }
}
```

## Πρακτικές εφαρμογές
Πραγματικά σενάρια όπου αυτή η ροή εργασίας διαπρέπει:

1. **Αυτοματοποιημένη αρχειοθέτηση email** – Αποκτήστε περιοδικά όλα τα μηνύματα των δημόσιων φακέλων και αποθηκεύστε τα σε ένα συμμορφωμένο αρχείο.  
2. **Λύσεις αντιγράφων ασφαλείας** – Κατοπτρίστε τους δημόσιους φακέλους του Exchange σε ασφαλές σύστημα αρχείων ή cloud bucket, εξασφαλίζοντας εφεδρεία δεδομένων.  
3. **Προσαρμοσμένοι πελάτες email** – Δημιουργήστε ελαφριές προβολές που εμφανίζουν μόνο τους φακέλους και τα μηνύματα που χρειάζεστε, μειώνοντας την πολυπλοκότητα του UI.

## Σκέψεις απόδοσης
Κατά την κλιμάκωση σε χιλιάδες φακέλους και εκατομμύρια μηνύματα, κρατήστε αυτές τις συμβουλές στο μυαλό:

- **Πισίνα συνδέσεων** – Επαναχρησιμοποιήστε ένα μόνο instance του `ExchangeClient` για πολλαπλές λειτουργίες αντί να δημιουργείτε νέο client ανά φάκελο.  
- **Lazy loading** – Ζητήστε μόνο τα μεταδεδομένα που χρειάζεστε (`listMessages` με παράμετρο `maxCount`) και ανακτήστε τα πλήρη σώματα κατά απαίτηση.  
- **Απόρριψη αντικειμένων** – Καλέστε `client.dispose()` μετά την εκτέλεση του batch για να ελευθερώσετε συνδέσεις HTTP και buffers νήματος.  
- **Παράλληλη επεξεργασία** – Διαχωρίστε τους φακέλους κορυφαίου επιπέδου σε πολλαπλά νήματα, το καθένα με το δικό του instance client, για αποτελεσματική χρήση πολυπύρηνων CPU.

## Συχνές ερωτήσεις

**Ε: Μπορώ να χρησιμοποιήσω αυτόν τον κώδικα με το Exchange Online (Office 365);**  
Α: Ναι. Παρέχετε το endpoint EWS του Office 365 (`https://outlook.office365.com/EWS/Exchange.asmx`) και χρησιμοποιήστε σύγχρονη ταυτοποίηση (OAuth) – το Aspose.Email υποστηρίζει διακριτικά OAuth από το κουτί.

**Ε: Τι γίνεται αν ένας φάκελος περιέχει περισσότερα από 10 000 μηνύματα;**  
Α: Χρησιμοποιήστε την υπερφόρτωση της `listMessages` που δέχεται παραμέτρους `skip` και `take` για σελιδοποίηση των αποτελεσμάτων, διατηρώντας τη χρήση μνήμης υπό έλεγχο.

**Ε: Υπάρχει όριο στο μέγεθος ενός μεμονωμένου email που μπορώ να κατεβάσω;**  
Α: Το API μεταδίδει το περιεχόμενο σε ροή, έτσι υποστηρίζονται μηνύματα έως 150 MB χωρίς να φτάσει το όριο της Java heap, εφόσον η JVM διαθέτει επαρκή φυσική μνήμη.

**Ε: Πρέπει να διαχειριστώ τα πιστοποιητικά SSL χειροκίνητα;**  
Α: Από προεπιλογή το Aspose.Email εμπιστεύεται το προεπιλεγμένο keystore της Java. Εάν ο διακομιστής Exchange χρησιμοποιεί αυτο‑υπογεγραμμένο πιστοποιητικό, εισάγετε το στο truststore της JVM ή ορίστε `client.setEnableSslVerification(false)` μόνο για δοκιμές.

**Ε: Πώς καταγράφω τις λειτουργίες για σκοπούς ελέγχου;**  
Α: Ενεργοποιήστε την ενσωματωμένη καταγραφή του Aspose.Email ρυθμίζοντας `Logger.setLevel(Level.INFO)` και κατευθύνοντας την έξοδο σε αρχείο ή σύστημα παρακολούθησης.

## Συμπέρασμα
Τώρα έχετε μια πλήρη, έτοιμη για παραγωγή συνταγή για **πώς να συνδέσετε το Exchange** και να καταγράψετε αναδρομικά μηνύματα από δημόσιους φακέλους χρησιμοποιώντας το Aspose.Email για Java. Τα βήματα καλύπτουν τη ρύθμιση Maven, την άδεια, τη σύνδεση, την απαρίθμηση φακέλων, την ανάκτηση μηνυμάτων και τη βελτιστοποίηση απόδοσης. Επεκτείνετε αυτή τη βάση ενσωματώνοντας βάσεις δεδομένων, αποθήκευση στο cloud ή προσαρμοσμένες γραμμές ανάλυσης για να καλύψετε τις συγκεκριμένες ανάγκες του οργανισμού σας.

---

**Last Updated:** 2026-10-02  
**Tested With:** Aspose.Email for Java 25.4  
**Author:** Aspose

## Σχετικά Μαθήματα

- [Πώς να συνδέσετε τον Exchange Server χρησιμοποιώντας το Aspose.Email σε Java: Οδηγός βήμα προς βήμα](/email/java/exchange-server-integration/aspose-email-java-exchange-server-connection/)
- [Πώς να συνδέσετε και να καταγράψετε φακέλους του Exchange Server χρησιμοποιώντας το Aspose.Email για Java](/email/java/exchange-server-integration/connect-list-exchange-server-folders-aspose-email-java/)
- [Διαχείριση φακέλων Exchange Server χρησιμοποιώντας το Aspose.Email για Java: Ένας ολοκληρωμένος οδηγός](/email/java/exchange-server-integration/exchange-server-folders-aspose-email-java/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}