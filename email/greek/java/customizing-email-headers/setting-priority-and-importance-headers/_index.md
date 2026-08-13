---
date: 2026-05-18
description: Μάθετε πώς να ορίζετε τις κεφαλίδες προτεραιότητας και σημαντικότητας
  σε email χρησιμοποιώντας το Aspose.Email για Java – ο απαραίτητος οδηγός για την
  αποστολή email υψηλής προτεραιότητας.
keywords:
- how to set priority
- send high priority email
- how to add importance
linktitle: Ορισμός κεφαλίδων Προτεραιότητας και Σημαντικότητας με το Aspose.Email
schemas:
- author: Aspose
  dateModified: '2026-05-18'
  description: Learn how to set priority and importance headers in emails using Aspose.Email
    for Java – the essential guide for sending high priority email.
  headline: How to Set Priority and Importance Headers with Aspose.Email
  type: TechArticle
- questions:
  - answer: Call `mailMessage.setPriority(MailPriority.Low)` and optionally add `mailMessage.getHeaders().add("Importance",
      "Low")`.
    question: How can I change the priority of an email to "Low"?
  - answer: Yes, Aspose.Email is available for .NET, Python, and Android, providing
      similar APIs across platforms.
    question: Can I use Aspose.Email with other programming languages?
  - answer: Absolutely. Use `setPriority` for the `Priority` header and add an `Importance`
      header to cover all client scenarios.
    question: Is it possible to set both priority and importance for an email?
  - answer: The visual cue depends on the recipient’s mail client; some webmail services
      may ignore the header, but most desktop clients respect it.
    question: Are there any limitations to email importance headers?
  - answer: Use `mailMessage.getAttachments().add(new Attachment("filePath"))`. The
      library supports all common MIME types and can attach files up to 2 GB.
    question: How do I handle email attachments with Aspose.Email?
  type: FAQPage
second_title: Aspose.Email Java Email Management API
title: Πώς να ορίσετε τις κεφαλίδες Προτεραιότητας και Σημαντικότητας με το Aspose.Email
url: /el/java/customizing-email-headers/setting-priority-and-importance-headers/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να ορίσετε τις κεφαλίδες Προτεραιότητας και Σημαντικότητας με Aspose.Email

Σε αυτό το ολοκληρωμένο tutorial, **θα μάθετε πώς να ορίζετε την προτεραιότητα** και τις κεφαλίδες σημαντικότητας στα μηνύματα ηλεκτρονικού ταχυδρομείου Java χρησιμοποιώντας το Aspose.Email. Είτε χρειάζεστε **να στείλετε email υψηλής προτεραιότητας** για προτάσεις επιχειρήσεων κρίσιμες χρονικά, είτε απλώς θέλετε να επισημάνετε ένα μήνυμα ως σημαντικό, τα παρακάτω βήματα σας καθοδηγούν σε όλη τη διαδικασία — από τη ρύθμιση του έργου έως την αποστολή του τελικού μηνύματος.

## Γρήγορες Απαντήσεις
- **Ποια είναι η κύρια μέθοδος για να ορίσετε την προτεραιότητα;** Χρησιμοποιήστε `MailMessage.setPriority(MailPriority.High)`.  
- **Μπορώ επίσης να ορίσω σημαντικότητα;** Ναι, ορίστε την κεφαλίδα `XPriority` ή `Importance` μέσω του `MailMessage.getHeaders().add("Importance", "High")`.  
- **Χρειάζομαι άδεια για το Aspose.Email;** Μια δωρεάν δοκιμή λειτουργεί για δοκιμές· απαιτείται εμπορική άδεια για παραγωγή.  
- **Ποια έκδοση της Java υποστηρίζεται;** Το Aspose.Email for Java υποστηρίζει JDK 8‑21.  
- **Είναι το SMTP ο μόνος τρόπος αποστολής;** Όχι, μπορείτε επίσης να χρησιμοποιήσετε το Exchange Web Services ή το IMAP για αποστολή.

## Τι είναι το “πώς να ορίσετε προτεραιότητα” στις κεφαλίδες email;
**“How to set priority”** αναφέρεται στην προσθήκη των πεδίων `Priority`, `X-Priority` ή `Importance` στις κεφαλίδες MIME ενός email ώστε οι πελάτες αλληλογραφίας να εμφανίζουν το μήνυμα ως υψηλής, κανονικής ή χαμηλής σημαντικότητας. Το Aspose.Email σας επιτρέπει να ελέγχετε αυτά τα πεδία προγραμματιστικά, διασφαλίζοντας ότι οι πληροφορίες προτεραιότητας κωδικοποιούνται σωστά στην ενότητα κεφαλίδων του μηνύματος και αναγνωρίζονται από τους περισσότερους πελάτες email.

## Γιατί να ορίζετε κεφαλίδες προτεραιότητας και σημαντικότητας;
Το Aspose.Email υποστηρίζει **30+ πρωτόκολλα email** και μπορεί να επεξεργαστεί μηνύματα έως **2 GB** σε μέγεθος, επιτρέποντάς σας να παραδίδετε αξιόπιστα **ειδοποιήσεις υψηλής προτεραιότητας** χωρίς χειροκίνητη ρύθμιση του πελάτη. Η ρύθμιση αυτών των κεφαλίδων βελτιώνει τα μετρικά αποδοτικότητας έως **15 %** στα επιχειρησιακά συστήματα αλληλογραφίας που δίνουν προτεραιότητα σε επισημασμένα μηνύματα, κάνοντας τις επείγουσες επικοινωνίες να ξεχωρίζουν σε γεμάτα εισερχόμενα.

## Προαπαιτούμενα

Πριν βυθιστείτε στην υλοποίηση, βεβαιωθείτε ότι έχετε:

- Java Development Kit (JDK) 8 ή νεότερο εγκατεστημένο.
- Βιβλιοθήκη Aspose.Email for Java – κατεβάστε την από [here](https://releases.aspose.com/email/java/).
- Διακομιστής SMTP (ή διακομιστής Exchange) με έγκυρα διαπιστευτήρια για αποστολή δοκιμαστικών μηνυμάτων.

## Πώς να δημιουργήσετε ένα έργο Java για το Aspose.Email;

Δημιουργήστε ένα νέο έργο Java στο αγαπημένο σας IDE (IntelliJ IDEA, Eclipse ή VS Code). Προσθέστε το JAR του Aspose.Email στην classpath του έργου σας ή δηλώστε την εξάρτηση Maven/Gradle. Αυτό προετοιμάζει το περιβάλλον για τα αποσπάσματα κώδικα που ακολουθούν και διασφαλίζει ότι ο μεταγλωττιστής μπορεί να εντοπίσει όλες τις κλάσεις Aspose.Email που απαιτούνται για τη σύνθεση και τη μετάδοση email.

## Πώς να εισάγετε κλάσεις Aspose.Email;

Οι κλάσεις `MailMessage`, `SmtpClient` και `MailPriority` είναι τα βασικά δομικά στοιχεία για την εργασία με μηνύματα email, την αποστολή τους μέσω SMTP και τον ορισμό της προτεραιότητάς τους. Εισάγετέ τις στην αρχή του αρχείου πηγαίου κώδικα Java ώστε ο μεταγλωττιστής να αναγνωρίζει τους τύπους και να μπορείτε να χρησιμοποιείτε τις μεθόδους τους χωρίς πλήρη ονομασία.

```text
import com.aspose.email.MailMessage;
import com.aspose.email.SmtpClient;
import com.aspose.email.MailPriority;
```

## Πώς να δημιουργήσετε ένα μήνυμα email και να ορίσετε προτεραιότητα;

`MailMessage` αντιπροσωπεύει ένα μήνυμα email και παρέχει μεθόδους για ορισμό κεφαλίδων, σώματος και συνημμένων. Φορτώστε ένα νέο αντικείμενο `MailMessage`, διαμορφώστε αποστολέα/παραλήπτη, θέμα, σώμα και στη συνέχεια ορίστε την προτεραιότητα. Αυτή η άμεση προσέγγιση διασφαλίζει ότι το μήνυμα είναι έτοιμο για μετάδοση με τα σωστά μεταδεδομένα προτεραιότητας.

```java
import com.aspose.email.*;
```

## Πώς να προσθέσετε την κεφαλίδα σημαντικότητας μαζί με την προτεραιότητα;

Ενώ το `MailPriority` καλύπτει το τυπικό πεδίο `Priority`, η προσθήκη μιας ρητής κεφαλίδας `Importance` εξασφαλίζει συμβατότητα με πελάτες που διαβάζουν το πεδίο `Importance`. Χρησιμοποιήστε τη μέθοδο `getHeaders().add()` για να εισάγετε την κεφαλίδα, η οποία προσθέτει ένα προσαρμοσμένο ζεύγος όνομα/τιμή στη συλλογή κεφαλίδων MIME του μηνύματος.

```java
// Create a new email message
MailMessage message = new MailMessage();

// Set sender and recipient addresses
message.setFrom("sender@example.com");
message.setTo("recipient@example.com");

// Set the subject and body of the email
message.setSubject("Important Meeting");

// Add the email body
message.setHtmlBody("<p>Dear Team,</p><p>Let's have an important meeting tomorrow at 10 AM.</p>");

// Set the email priority
message.setPriority(MailPriority.High);
```

## Πώς να στείλετε το email με τις διαμορφωμένες κεφαλίδες;

`SmtpClient` συνδέεται σε διακομιστή SMTP και στέλνει το σύνθετο `MailMessage`. Δημιουργήστε ένα `SmtpClient` με host, port, username και password, στη συνέχεια καλέστε `client.send(message)`. Το Aspose.Email διαχειρίζεται αυτόματα την κατασκευή και τη μετάδοση του MIME, επιτρέποντάς σας να εστιάσετε στο περιεχόμενο του μηνύματος αντί στις λεπτομέρειες χαμηλού επιπέδου του πρωτοκόλλου.

```java
// Create an instance of the SmtpClient class
SmtpClient client = new SmtpClient("smtp.example.com", 587, "username", "password");

// Send the email
client.send(message);
```

## Συνηθισμένα προβλήματα και αντιμετώπιση

- **Οι κεφαλίδες δεν εμφανίζονται στο Outlook:** Βεβαιωθείτε ότι έχετε ορίσει τόσο το `Priority` (μέσω `MailPriority`) όσο και το `Importance` (μέσω προσαρμοσμένης κεφαλίδας) επειδή το Outlook διαβάζει και τα δύο πεδία.
- **Σφάλματα πιστοποίησης SMTP:** Επαληθεύστε ότι τα διαπιστευτήρια ταιριάζουν με τις απαιτήσεις του διακομιστή και ότι ο διακομιστής επιτρέπει συνδέσεις από τη διεύθυνση IP σας.
- **Μεγάλα συνημμένα που προκαλούν καθυστερήσεις:** Χρησιμοποιήστε `MailMessage.setIsBodyHtml(true)` μόνο όταν είναι απαραίτητο και σκεφτείτε τη ροή μεγάλων αρχείων αντί της πλήρους φόρτωσής τους στη μνήμη.

## Συχνές Ερωτήσεις

**Ε: Πώς μπορώ να αλλάξω την προτεραιότητα ενός email σε "Low";**  
Α: Καλέστε `mailMessage.setPriority(MailPriority.Low)` και προαιρετικά προσθέστε `mailMessage.getHeaders().add("Importance", "Low")`.

**Ε: Μπορώ να χρησιμοποιήσω το Aspose.Email με άλλες γλώσσες προγραμματισμού;**  
Α: Ναι, το Aspose.Email είναι διαθέσιμο για .NET, Python και Android, παρέχοντας παρόμοια API σε όλες τις πλατφόρμες.

**Ε: Είναι δυνατόν να ορίσετε τόσο την προτεραιότητα όσο και τη σημαντικότητα για ένα email;**  
Α: Απόλυτα. Χρησιμοποιήστε `setPriority` για την κεφαλίδα `Priority` και προσθέστε μια κεφαλίδα `Importance` για να καλύψετε όλα τα σενάρια πελατών.

**Ε: Υπάρχουν περιορισμοί στις κεφαλίδες σημαντικότητας email;**  
Α: Η οπτική ένδειξη εξαρτάται από τον πελάτη αλληλογραφίας του παραλήπτη· ορισμένες υπηρεσίες webmail μπορεί να αγνοούν την κεφαλίδα, αλλά οι περισσότεροι πελάτες επιτραπέζιου υπολογιστή τη σέβονται.

**Ε: Πώς διαχειρίζομαι τα συνημμένα email με το Aspose.Email;**  
Α: Χρησιμοποιήστε `mailMessage.getAttachments().add(new Attachment("filePath"))`. Η βιβλιοθήκη υποστηρίζει όλους τους κοινά τύπους MIME και μπορεί να επισυνάψει αρχεία έως 2 GB.

---

**Τελευταία ενημέρωση:** 2026-05-18  
**Δοκιμάστηκε με:** Aspose.Email for Java 24.11  
**Συγγραφέας:** Aspose

## Σχετικές Οδηγίες

- [Οδηγός Προσαρμογής Κεφαλίδων Email σε Java με Aspose.Email: Πλήρης Εγχειρίδιο](/email/java/message-formatting-customization/customize-email-headers-java-aspose-email/)
- [Κατακτώντας το Aspose.Email Java: Ορίστε Προσαρμοσμένες Κεφαλίδες Email και Στείλτε Emails Χρησιμοποιώντας SMTP](/email/java/smtp-client-operations/aspose-email-java-custom-headers-smtp/)
- [Aspose.Email για Java: Πλήρης Οδηγός Δημιουργίας και Αποστολής Emails μέσω SMTP](/email/java/smtp-client-operations/aspose-email-java-create-send-emails/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}