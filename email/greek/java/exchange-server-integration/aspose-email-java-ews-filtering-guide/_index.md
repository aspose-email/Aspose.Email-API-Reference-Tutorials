---
date: '2026-07-17'
description: 'Πώς να φιλτράρετε emails χρησιμοποιώντας Aspose.Email Java και EWS:
  μάθετε τεχνικές φιλτραρίσματος κατά ημερομηνία, αποστολέα και θέμα για να βελτιώσετε
  τη διαχείριση του γραμματοκιβωτίου σας.'
keywords:
- Aspose.Email Java
- email filtering techniques
- Exchange Web Services (EWS)
lastmod: '2026-07-17'
og_description: Πώς να φιλτράρετε emails χρησιμοποιώντας Aspose.Email Java και EWS.
  Ανακαλύψτε τεχνικές φιλτραρίσματος κατά ημερομηνία, αποστολέα και θέμα για να διατηρήσετε
  το γραμματοκιβώτιό σας οργανωμένο.
og_image_alt: Guide to filtering emails with Aspose.Email Java and Exchange Web Services
og_title: Πώς να Φιλτράρετε Emails με Aspose.Email Java & EWS
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: 'How to filter emails using Aspose.Email Java and EWS: learn date,
    sender, and subject filtering techniques to streamline your mailbox.'
  headline: How to Filter Emails with Aspose.Email Java & EWS Guide
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Email works with Office 365 Exchange Online by pointing the
      service URL to `https://outlook.office365.com/EWS/Exchange.asmx`.
    question: Can I use this approach with Office 365?
  - answer: Absolutely—use `OAuthCredentials` to authenticate without storing user
      passwords.
    question: Does Aspose.Email support OAuth authentication?
  - answer: The API can handle mailboxes of **several gigabytes**; because it streams
      results, memory consumption stays low.
    question: What is the maximum mailbox size I can process?
  - answer: Add a `SearchFilter.ContainsSubstring` on the `AttachmentNames` property,
      then iterate only matching items.
    question: How do I filter attachments by file type?
  - answer: Yes—pass a `SortDirection` and the property you want to sort on (e.g.,
      `DateTimeReceived`) to the `FindItems` call.
    question: Is there a way to sort results?
  type: FAQPage
tags:
- how to filter emails
- aspose email java
- filter emails by date
- filter emails by sender
- ews integration
title: Πώς να Φιλτράρετε Emails με Aspose.Email Java & EWS Οδηγός
url: /el/java/exchange-server-integration/aspose-email-java-ews-filtering-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Αποκτώντας τον έλεγχο του φιλτραρίσματος email με Aspose.Email Java & EWS: Ένας πλήρης οδηγός

## Εισαγωγή

**Πώς να φιλτράρετε email** αποδοτικά είναι μια βασική δεξιότητα για όποιον εργάζεται με Microsoft Exchange ή οποιοδήποτε σύγχρονο γραμματοκιβώτιο. Είτε είστε προγραμματιστής που δημιουργεί αυτοματοποίηση σε εταιρικό επίπεδο είτε άτομο που θέλει να διατηρήσει τακτικό το inbox του, η κατάκτηση των σωστών τεχνικών φιλτραρίσματος μπορεί να εξοικονομήσει ώρες χειροκίνητης εργασίας. Σε αυτόν τον οδηγό θα περάσουμε από το Aspose.Email για Java μαζί με το Exchange Web Services (EWS) για να σας δείξουμε πώς να φιλτράρετε κατά ημερομηνία, αποστολέα, θέμα, domain, παραλήπτη, και ακόμη να συνδυάσετε πολλαπλά κριτήρια με λογικούς τελεστές.

### Τι θα μάθετε
- Τεχνικές φιλτραρίσματος μηνυμάτων χρησιμοποιώντας EWS σε Java.  
- Φιλτράρισμα email βάσει κριτηρίων όπως ημερομηνία, αποστολέας, θέμα κ.λπ.  
- Υλοποίηση υποστήριξης σελιδοποίησης για διαχείριση μεγάλων γραμματοκιβωτίων.  
- Πρακτικές εφαρμογές αυτών των μεθόδων φιλτραρίσματος σε πραγματικά σενάρια.  
- Παράγοντες απόδοσης και βέλτιστες πρακτικές με Aspose.Email Java.

Στο τέλος αυτού του tutorial θα μπορείτε να γράψετε καθαρό, αποδοτικό κώδικα Java που θα αντλεί ακριβώς τα μηνύματα που χρειάζεστε από έναν Exchange server.

## Γρήγορες Απαντήσεις
- **Ποια είναι η κύρια βιβλιοθήκη;** Aspose.Email for Java.  
- **Ποιο πρωτόκολλο χρησιμοποιεί;** Exchange Web Services (EWS).  
- **Μπορώ να φιλτράρω κατά εύρος ημερομηνιών;** Ναι – χρησιμοποιήστε κριτήρια `DateTime` στο `SearchFilter`.  
- **Υποστηρίζεται η σελιδοποίηση;** Απόλυτα, το API προσφέρει `ItemView` με offset/limit.  
- **Χρειάζομαι άδεια για παραγωγή;** Ναι, μια εμπορική άδεια αφαιρεί τα όρια αξιολόγησης.

## Τι είναι το Aspose.Email για Java;
Το Aspose.Email για Java είναι ένα ολοκληρωμένο API που επιτρέπει προγραμματισμένη πρόσβαση σε διακομιστές email, μηνύματα MIME και Exchange Web Services χωρίς την ανάγκη Outlook ή οποιουδήποτε άλλου πελάτη. Απομονώνει τα υποκείμενα πρωτόκολλα, επιτρέποντάς σας να εστιάσετε στη λογική της επιχείρησης. Η βιβλιοθήκη υποστηρίζει τόσο τοπικούς διακομιστές Exchange όσο και το Exchange Online, παρέχοντας ένα ενοποιημένο API για διάφορα σενάρια ανάπτυξης.

## Γιατί να χρησιμοποιήσετε το Aspose.Email με EWS;
Το Aspose.Email υποστηρίζει **50+** πρωτόκολλα email και μπορεί να επεξεργαστεί **εκατοντάδες χιλιάδες μηνύματα** ανά ώρα διατηρώντας τη χρήση μνήμης κάτω από **100 MB** χάρη στην αρχιτεκτονική ροής του. Αυτή η μετρήσιμη απόδοση το καθιστά ιδανικό για αυτοματοποίηση γραμματοκιβωτίων σε επιχειρησιακό επίπεδο. Επιπλέον, προσφέρει ενσωματωμένη υποστήριξη για OAuth και σύγχρονη πιστοποίηση, απλοποιώντας ασφαλείς συνδέσεις σε περιβάλλοντα Office 365.

## Προαπαιτούμενα
- **Απαιτούμενες βιβλιοθήκες**: Συμπεριλάβετε τη βιβλιοθήκη Aspose.Email στο έργο σας.  
- **Ρύθμιση περιβάλλοντος**: Απαιτείται ένα έτοιμο περιβάλλον ανάπτυξης για εφαρμογές Java.  
- **Προαπαιτούμενες γνώσεις**: Η εξοικείωση με προγραμματισμό Java και πρωτόκολλα email θα είναι επωφελής.

## Ρύθμιση του Aspose.Email για Java

### Εγκατάσταση μέσω Maven
Add the following dependency to your `pom.xml` file:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Απόκτηση Άδειας
- **Δωρεάν δοκιμή**: Ξεκινήστε με μια δωρεάν δοκιμή για να εξερευνήσετε τις δυνατότητες του Aspose.Email.  
- **Προσωρινή άδεια**: Αποκτήστε μια προσωρινή άδεια για εκτεταμένη αξιολόγηση.  
- **Αγορά**: Σκεφτείτε την αγορά πλήρους άδειας εάν το εργαλείο καλύπτει τις ανάγκες σας.

Initialize and set up Aspose.Email by importing necessary packages and establishing a connection to your email server using EWS credentials. This step is crucial for accessing mailbox data programmatically.

## Πώς να φιλτράρετε email χρησιμοποιώντας EWS σε Java;

ExchangeService είναι η κλάση Aspose.Email που αντιπροσωπεύει μια σύνδεση σε διακομιστή Exchange.  
SearchFilter ορίζει κριτήρια για τον εντοπισμό αντικειμένων στον διακομιστή.  
FindItems εκτελεί την αναζήτηση και επιστρέφει τα αντικείμενα που ταιριάζουν.  
ItemView ελέγχει τη σελιδοποίηση και τον αριθμό των αντικειμένων που επιστρέφονται ανά αίτηση.

Φορτώστε μια παρουσία `ExchangeService` με τα διαπιστευτήριά σας, δημιουργήστε ένα `SearchFilter` που ταιριάζει στα κριτήριά σας, και καλέστε το `FindItems` με ένα `ItemView` για να ανακτήσετε μόνο τα μηνύματα που χρειάζεστε. Αυτό το μοτίβο μιας γραμμής—σύνδεση → φιλτράρισμα → λήψη—καλύπτει τις περισσότερες περιπτώσεις χρήσης και κλιμακώνεται σε μεγάλα γραμματοκιβώτια όταν ενεργοποιήσετε τη σελιδοποίηση.

## Οδηγός Υλοποίησης

### Φιλτράρισμα μηνυμάτων χρησιμοποιώντας EWS

#### Επισκόπηση
Filtering allows you to retrieve only emails that meet certain conditions, such as a specific subject or date, directly from your mailbox.
```java
import com.aspose.email.EWSClient;
import com.aspose.email.ExchangeMessageInfoCollection;
import com.aspose.email.MailQuery;
import com.aspose.email.ExchangeQueryBuilder;
import java.text.ParseException;
import java.text.SimpleDateFormat;

public class FilterMessagesUsingEWS {
    public static void main(String[] args) throws ParseException {
        // Establish a connection to the EWS server
        IEWSClient client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser", "pwd", "domain");

        SimpleDateFormat sdf = new SimpleDateFormat("dd/MM/yyyy HH:mm:ss");
        
        // Build a query for emails containing 'Newsletter' in the subject
        ExchangeQueryBuilder builder = new ExchangeQueryBuilder();
        builder.getSubject().contains("Newsletter");
        builder.getInternalDate().on(sdf.parse("10/05/2016 10:00:00"));
        MailQuery query = builder.getQuery();

        // Retrieve messages matching the criteria
        ExchangeMessageInfoCollection messages = client.listMessages(client.getMailboxInfo().getInboxUri(), query, false);
    }
}
```
**Επεξήγηση**: Ο κώδικας δημιουργεί σύνδεση στο γραμματοκιβώτιό σας και δημιουργεί ένα ερώτημα για φιλτράρισμα email με 'Newsletter' στη γραμμή θέματος σε συγκεκριμένη ημερομηνία.

### Πώς να φιλτράρετε email με βάση την σημερινή ημερομηνία;

SearchFilter.IsEqualTo δημιουργεί ένα φίλτρο που ταιριάζει σε αντικείμενα όπου μια ιδιότητα ισούται με μια δεδομένη τιμή.  
DateTimeReceived είναι η ιδιότητα που υποδεικνύει πότε ελήφθη το email.

Φορτώστε την τρέχουσα ημερομηνία, δημιουργήστε ένα `SearchFilter.IsEqualTo` στην ιδιότητα `DateTimeReceived` και εκτελέστε το ερώτημα. Αυτό επιστρέφει μόνο τα μηνύματα που ελήφθησαν την ημέρα που εκτελείτε τον κώδικα, καθιστώντας τα καθημερινά σενάρια επεξεργασίας απλά. Μπορείτε να συνδυάσετε αυτό το φίλτρο με πρόσθετα κριτήρια όπως αποστολέας ή θέμα για περαιτέρω περιορισμό των αποτελεσμάτων της ημέρας.

### Πώς να φιλτράρετε email με βάση το εύρος ημερομηνιών;

SearchFilter.IsGreaterThanOrEqualTo δημιουργεί ένα φίλτρο που ταιριάζει σε αντικείμενα με τιμή ιδιότητας μεγαλύτερη ή ίση με μια καθορισμένη τιμή.  
SearchFilter.IsLessThanOrEqualTo δημιουργεί ένα φίλτρο που ταιριάζει σε αντικείμενα με τιμή ιδιότητας μικρότερη ή ίση με μια καθορισμένη τιμή.  
SearchFilter.And συνδυάζει πολλαπλά φίλτρα έτσι ώστε όλες οι συνθήκες να πρέπει να ικανοποιηθούν.

Ορίστε ένα αρχικό και ένα τελικό `DateTime`, συνδυάστε τα με `SearchFilter.IsGreaterThanOrEqualTo` και `SearchFilter.IsLessThanOrEqualTo`, στη συνέχεια χρησιμοποιήστε `SearchFilter.And` για να τα ενώσετε. Το σύνολο αποτελεσμάτων περιέχει κάθε μήνυμα που εμπίπτει στο καθορισμένο παράθυρο. Αυτή η προσέγγιση σας επιτρέπει να ανακτήσετε όλες τις επικοινωνίες εντός οποιασδήποτε προσαρμοσμένης περιόδου, όπως το τελευταίο τρίμηνο ή μια συγκεκριμένη χρονοδιάγραμμα έργου.

### Πώς να φιλτράρετε email με βάση συγκεκριμένο αποστολέα;

SearchFilter.IsEqualTo δημιουργεί ένα φίλτρο που ταιριάζει σε αντικείμενα όπου μια ιδιότητα ισούται με μια δεδομένη τιμή.

Δημιουργήστε ένα `SearchFilter.IsEqualTo` στην ιδιότητα `From` με τη διεύθυνση email του αποστολέα. Αυτό απομονώνει όλα τα μηνύματα από αυτή την επαφή, ιδανικό για προτεραιότητα inbox ή ελέγχους συμμόρφωσης. Μπορείτε επίσης να χρησιμοποιήσετε `SearchFilter.ContainsSubstring` για μερικές αντιστοιχίες όταν η ακριβής διεύθυνση είναι άγνωστη ή όταν φιλτράρετε κατά domain.

### Πώς να φιλτράρετε email με βάση συγκεκριμένο domain;

SearchFilter.ContainsSubstring δημιουργεί ένα φίλτρο που ταιριάζει σε αντικείμενα όπου μια ιδιότητα περιέχει ένα καθορισμένο υποσυμβολοσειρά.

Χρησιμοποιήστε `SearchFilter.ContainsSubstring` στην ιδιότητα `From` με τη συμβολοσειρά του domain (π.χ., “@example.com”). Αυτό αντλεί κάθε email που προέρχεται από αυτό το domain, χρήσιμο για παρακολούθηση συνεργατών ή προμηθευτών. Συνδυάζοντας αυτό το φίλτρο με κριτήρια ημερομηνίας μπορείτε να παρακολουθείτε επικοινωνίες ειδικές για το domain με την πάροδο του χρόνου, βοηθώντας σε ελέγχους ασφαλείας.

### Πώς να φιλτράρετε email με βάση συγκεκριμένο παραλήπτη;

SearchFilter.IsEqualTo δημιουργεί ένα φίλτρο που ταιριάζει σε αντικείμενα όπου μια ιδιότητα ισούται με μια δεδομένη τιμή.

Εφαρμόστε `SearchFilter.IsEqualTo` στη συλλογή `ToRecipients` για τη στοχευμένη διεύθυνση. Αυτό είναι χρήσιμο όταν χρειάζεται να ελέγξετε μηνύματα που αποστέλλονται σε συγκεκριμένο γραμματοκιβώτιο ή λίστα διανομής. Μπορείτε επίσης να χρησιμοποιήσετε `SearchFilter.ContainsSubstring` για μερικές αντιστοιχίες όταν αντιμετωπίζετε πολλούς παραλήπτες που μοιράζονται ένα κοινό domain.

### Πώς να συνδυάσετε ερωτήματα με λογική AND;

SearchFilter.And συνδυάζει πολλαπλά φίλτρα έτσι ώστε όλες οι συνθήκες να πρέπει να ικανοποιηθούν.

Συνδέστε πολλαπλά αντικείμενα `SearchFilter` χρησιμοποιώντας `SearchFilter.And`. Για παράδειγμα, συνδυάστε ένα φίλτρο αποστολέα με ένα φίλτρο θέματος για να ανακτήσετε μόνο newsletters από έναν αξιόπιστο αποστολέα. Ο τελεστής AND διασφαλίζει ότι επιστρέφονται μόνο τα αντικείμενα που ικανοποιούν όλες τις καθορισμένες συνθήκες, μειώνοντας το σύνολο αποτελεσμάτων στα πιο σχετικά μηνύματα.

### Πώς να συνδυάσετε ερωτήματα με λογική OR;

SearchFilter.Or συγχωνεύει φίλτρα ώστε οποιαδήποτε μία συνθήκη μπορεί να ταιριάζει.

Χρησιμοποιήστε `SearchFilter.Or` για να συγχωνεύσετε φίλτρα όταν οποιαδήποτε μία συνθήκη πρέπει να ταιριάζει—ιδανικό για την ανάκτηση μηνυμάτων που είτε προέρχονται από ένα σύνολο αποστολέων **ή** περιέχουν συγκεκριμένες λέξεις-κλειδιά. Η εφαρμογή λογικής OR μπορεί να επεκτείνει τις αναζητήσεις ώστε να καταγράψετε όλες τις σχετικές επικοινωνίες σε πολλαπλές κατηγορίες χωρίς να λείπουν κρίσιμες πληροφορίες.

## Συνηθισμένα Πιθανά Σφάλματα & Συμβουλές
- **Η σελιδοποίηση είναι απαραίτητη**: Όταν διαχειρίζεστε γραμματοκιβώτια μεγαλύτερα από 1.000 αντικείμενα, χρησιμοποιείτε πάντα `ItemView` με μέγεθος σελίδας για να αποφύγετε χρονικά όρια.  
- **Διαχείριση ζώνης ώρας**: Το EWS επιστρέφει ημερομηνίες σε UTC· μετατρέψτε τις στη δική σας τοπική ζώνη πριν τη σύγκριση.  
- **Αποφύγετε πλήρεις σαρώσεις γραμματοκιβωτίου**: Εφαρμόζετε πάντα ένα `SearchFilter` στην πλευρά του διακομιστή· το φιλτράρισμα στην πλευρά του πελάτη σπαταλά εύρος ζώνης και μνήμη.  
- **Συμβουλή**: Κρατήστε στην cache το αντικείμενο `ExchangeService` για τη διάρκεια ζωής της εφαρμογής σας ώστε να μειώσετε το κόστος πιστοποίησης.

## Συχνές Ερωτήσεις

**Ε: Μπορώ να χρησιμοποιήσω αυτήν την προσέγγιση με Office 365;**  
Α: Ναι, το Aspose.Email λειτουργεί με το Office 365 Exchange Online δείχνοντας το URL υπηρεσίας στο `https://outlook.office365.com/EWS/Exchange.asmx`.

**Ε: Υποστηρίζει το Aspose.Email την πιστοποίηση OAuth;**  
Α: Απόλυτα—χρησιμοποιήστε `OAuthCredentials` για πιστοποίηση χωρίς αποθήκευση κωδικών χρηστών.

**Ε: Ποιο είναι το μέγιστο μέγεθος γραμματοκιβωτίου που μπορώ να επεξεργαστώ;**  
Α: Το API μπορεί να διαχειριστεί γραμματοκιβώτια **πολλών gigabytes**· επειδή ρέει τα αποτελέσματα, η κατανάλωση μνήμης παραμένει χαμηλή.

**Ε: Πώς φιλτράρω συνημμένα κατά τύπο αρχείου;**  
Α: Προσθέστε ένα `SearchFilter.ContainsSubstring` στην ιδιότητα `AttachmentNames`, στη συνέχεια επαναλάβετε μόνο τα αντικείμενα που ταιριάζουν.

**Ε: Υπάρχει τρόπος να ταξινομήσω τα αποτελέσματα;**  
Α: Ναι—περάστε ένα `SortDirection` και την ιδιότητα με την οποία θέλετε να ταξινομήσετε (π.χ., `DateTimeReceived`) στην κλήση `FindItems`.

---

**Τελευταία ενημέρωση:** 2026-07-17  
**Δοκιμάστηκε με:** Aspose.Email for Java 24.10  
**Συγγραφέας:** Aspose

## Σχετικά Μαθήματα

- [Πώς να δημιουργήσετε μια παρουσία EWSClient χρησιμοποιώντας Aspose.Email για Java: Οδηγός ενσωμάτωσης Exchange Server](/email/java/exchange-server-integration/ewsclient-instance-aspose-email-java/)
- [Πώς να κατεβάσετε email από Exchange Server χρησιμοποιώντας Aspose.Email Java](/email/java/exchange-server-integration/aspose-email-java-exchange-server-download/)
- [Διαχείριση πληροφοριών γραμματοκιβωτίου EWS χρησιμοποιώντας Aspose.Email για Java: Ένας ολοκληρωμένος οδηγός](/email/java/exchange-server-integration/manage-ews-mailbox-info-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}

```java
import com.aspose.email.MailQueryBuilder;
import java.util.Date;

public class FilterMessagesBasedOnTodayDate {
    public static void main(String[] args) {
        // Build a query for today's emails
        MailQueryBuilder builder = new MailQueryBuilder();
        builder.getInternalDate().on(new Date());
    }
}
```

```java
import com.aspose.email.MailQueryBuilder;
import java.util.Date;
import java.util.concurrent.TimeUnit;

public class FilterMessagesBasedOnDateRange {
    public static void main(String[] args) {
        // Build a query for emails received in the last 24 hours
        MailQueryBuilder builder = new MailQueryBuilder();
        Date today = new Date();
        builder.getInternalDate().beforeOrEqual(today);
        builder.getInternalDate().since(new Date(today.getTime() + TimeUnit.DAYS.toMillis(1)));
    }
}
```

```java
import com.aspose.email.MailQueryBuilder;

public class FilterMessagesBasedOnSpecificSender {
    public static void main(String[] args) {
        // Build a query for emails from 'saqib.razzaq@127.0.0.1'
        MailQueryBuilder builder = new MailQueryBuilder();
        builder.getFrom().contains("saqib.razzaq@127.0.0.1");
    }
}
```

```java
import com.aspose.email.MailQueryBuilder;

public class FilterMessagesBasedOnSpecificDomain {
    public static void main(String[] args) {
        // Build a query for emails from 'SpecificHost.com'
        MailQueryBuilder builder = new MailQueryBuilder();
        builder.getFrom().contains("SpecificHost.com");
    }
}
```

```java
import com.aspose.email.MailQueryBuilder;

public class FilterMessagesBasedOnSpecificRecipient {
    public static void main(String[] args) {
        // Build a query for emails sent to 'recipient'
        MailQueryBuilder builder = new MailQueryBuilder();
        builder.getTo().contains("recipient");
    }
}
```

```java
import com.aspose.email.MailQueryBuilder;
import java.util.Date;
import java.util.concurrent.TimeUnit;

public class CombineQueriesWithAND {
    public static void main(String[] args) {
        // Build a combined query for specific domain, emails received before today,
        // and within the last 7 days
        MailQueryBuilder builder = new MailQueryBuilder();
        builder.getFrom().contains("SpecificHost.com");
        builder.getInternalDate().before(new Date());
        builder.getInternalDate().since(new Date(new Date().getTime() + TimeUnit.DAYS.toMillis(-7)));
    }
}
```

```java
import com.aspose.email.MailQueryBuilder;

public class CombineQueriesWithOR {
    public static void main(String[] args) {
        // Build a query for emails either from 'SpecificHost.com' or containing 'Newsletter'
        MailQueryBuilder builder = new MailQueryBuilder();
        builder.getFrom().contains("SpecificHost.com")
                .or(builder.getSubject().contains("Newsletter"));
    }
}
```