---
date: '2026-07-27'
description: Μάθετε πώς να ορίσετε outlook flag java χρησιμοποιώντας Aspose.Email
  for Java, καλύπτοντας τη δημιουργία flag, τις flags παραλήπτη, την ολοκλήρωση, την
  αφαίρεση και τις επιλογές ανάγνωσης.
keywords:
- set outlook flag java
- outlook follow up flag java
- aspose email java
lastmod: '2026-07-27'
og_description: Ορίστε outlook flag java με Aspose.Email for Java. Αυτός ο οδηγός
  δείχνει πώς να δημιουργήσετε, να διαβάσετε, να ολοκληρώσετε και να αφαιρέσετε Outlook
  follow‑up flags αποδοτικά.
og_image_alt: 'Developer guide: Set Outlook flag Java using Aspose.Email'
og_title: Ορισμός Outlook Flag Java – Πλήρης Οδηγός Προγραμματισμού Aspose.Email
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Learn how to set outlook flag java using Aspose.Email for Java, covering
    flag creation, recipient flags, completion, removal, and reading options.
  headline: Set Outlook Flag Java – Complete Aspose.Email Programming Guide
  type: TechArticle
- description: Learn how to set outlook flag java using Aspose.Email for Java, covering
    flag creation, recipient flags, completion, removal, and reading options.
  name: Set Outlook Flag Java – Complete Aspose.Email Programming Guide
  steps:
  - name: Create and Initialize the Message
    text: '`MailMessage` is Aspose.Email’s high‑level class that represents an email.
      After you build the message, you convert it to a `MapiMessage` for flag manipulation.
      *We first build a `MailMessage`, set sender/recipient, then convert it to a
      `MapiMessage` for flag manipulation.*'
  - name: Define Follow‑Up Dates (Outlook Flag Reminder)
    text: '`FollowUpOptions` holds the start, reminder, and due dates. Use Java’s
      `Calendar` to set precise timestamps. *Here we set the start, reminder (the
      **outlook flag reminder**), and due dates using the `Calendar` class.*'
  - name: Apply Follow‑Up Options
    text: The `FollowUpManager.setOptions` method attaches the flag to the `MapiMessage`.
      *The `FollowUpOptions` object holds all flag details, which we apply with `FollowUpManager.setOptions`.*
  - name: Save the Message
    text: Save the flagged message as a `.msg` file so Outlook can display the flag.
      *The message is saved as a `.msg` file with the flag attached.*
  - name: Mark as Draft
    text: '`MessageFlags` is a MAPI enumeration that controls the state of the message.
      Setting `MSGFLAG_UNSENT` tells Outlook the item is a draft. *Marking the message
      as unsent ensures Outlook treats it as a draft.*'
  - name: Set Recipient Flag
    text: '`FollowUpManager.setFlagForRecipients` attaches the flag exclusively to
      the recipient’s copy. *The flag is now visible only to the recipients – a classic
      **flag for recipients** scenario.*'
  - name: Load the Message
    text: '`MapiMessage` can read a saved `.msg` file, giving you full access to its
      MAPI properties.'
  - name: Mark as Completed and Save
    text: '`FollowUpManager.completeFlag` updates the flag status, after which you
      persist the changes. *The flag status changes to “Completed” and the updated
      file is saved.*'
  - name: Load and Clear Flag
    text: '`FollowUpManager.clearFlag` removes all flag‑related properties from the
      message. *The message is saved without any follow‑up flag.*'
  - name: Retrieve Options
    text: The returned `options` object gives you full visibility into the flag’s
      configuration. *The `options` object now contains start, due, and reminder dates,
      plus the flag subject – useful when you need to **read flag options** for reporting.*
  type: HowTo
- questions:
  - answer: It’s a pure‑Java API that lets you create, read, and manipulate email
      files (MSG, EML, etc.) without needing Outlook installed.
    question: What is Aspose.Email for Java?
  - answer: Visit the [Aspose website](https://releases.aspose.com/email/java/) to
      download a 30‑day trial.
    question: How do I obtain a free trial license?
  - answer: Outlook supports only one flag per message, but you can store additional
      task data in custom MAPI properties.
    question: Can I set multiple follow‑up flags on a single message?
  - answer: Confirm the `outputDir` path is valid and that the application has permission
      to write to that location.
    question: My message isn’t saved after setting a flag. What should I check?
  - answer: Loop through your message collection and call `FollowUpManager.clearFlag`
      on each `MapiMessage`.
    question: How can I remove flags from many messages at once?
  type: FAQPage
tags:
- outlook flag
- aspose.email
- java email automation
title: Ορισμός Outlook Flag Java – Πλήρης Οδηγός Προγραμματισμού Aspose.Email
url: /el/java/calendar-appointments/aspose-email-java-outlook-follow-up-flags/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Ορισμός Σημαίας Outlook Java με Aspose.Email για Java

## Εισαγωγή
Αν χρειάζεστε να **set outlook flag java** προγραμματιστικά, βρίσκεστε στο σωστό μέρος. Η σημαία παρακολούθησης του Outlook μετατρέπει ένα κανονικό email σε μια παρακολουθούμενη εργασία, και το Aspose.Email for Java σας επιτρέπει να διαχειρίζεστε αυτές τις σημαίες χωρίς να έχετε εγκατεστημένο το Outlook. Σε αυτό το tutorial θα περάσουμε από τη δημιουργία, ανάγνωση, ολοκλήρωση και τελικά την αφαίρεση των σημαίων, καθώς και πώς να εφαρμόζετε σημαίες για συγκεκριμένους παραλήπτες. Στο τέλος θα έχετε ένα επαναχρησιμοποιήσιμο απόσπασμα Java που αυτοματοποιεί την παρακολούθηση εργασιών απευθείας από τις υπηρεσίες backend σας.

## Γρήγορες Απαντήσεις
- **Τι σημαίνει “set outlook flag java”;** Προσθήκη μιας σημαίας με ημερομηνίες έναρξης, υπενθύμισης και λήξης σε ένα στοιχείο Outlook μέσω κώδικα Java.  
- **Ποια βιβλιοθήκη απαιτείται;** Aspose.Email for Java (v25.4 ή νεότερη).  
- **Χρειάζομαι άδεια;** Ναι – μια δοκιμαστική έκδοση λειτουργεί για αξιολόγηση, αλλά απαιτείται αγορασμένη άδεια για παραγωγή.  
- **Μπορώ να ορίσω σημαίες μόνο για παραλήπτες;** Απόλυτα – χρησιμοποιήστε `FollowUpManager.setFlagForRecipients`.  
- **Μπορεί να αφαιρεθεί μια σημαία αργότερα;** Ναι – καλέστε `FollowUpManager.clearFlag`.

## Τι είναι η Σημαία Παρακολούθησης Outlook;
Η σημαία παρακολούθησης του Outlook είναι ένας ενσωματωμένος δείκτης εργασίας που μπορεί να συνδέσει μια ημερομηνία έναρξης, μια υπενθύμιση και μια ημερομηνία λήξης σε οποιοδήποτε στοιχείο αλληλογραφίας. Μετατρέπει ένα email σε μια παρακολουθούμενη ενέργεια, βοηθώντας εσάς και την ομάδα σας να παραμένετε ενημερωμένοι για τις εκκρεμείς εργασίες.

## Γιατί να Χρησιμοποιήσετε το Aspose.Email για Java;
Το Aspose.Email για Java υποστηρίζει **πάνω από 70 μορφές email** (συμπεριλαμβανομένων των MSG, EML, MHTML και TNEF) και μπορεί να επεξεργαστεί **πάνω από 100.000 μηνύματα ανά λεπτό** σε έναν τυπικό διακομιστή 8‑πυρήνων, όλα χωρίς να απαιτείται το Outlook στον κεντρικό υπολογιστή. Αυτό το καθιστά ιδανικό για αυτοματοποίηση backend, αναφορές συμμόρφωσης και ενσωμάτωση με εργαλεία διαχείρισης έργων.

## Προαπαιτούμενα
- **Aspose.Email for Java** έκδοση 25.4 ή νεότερη.  
- **JDK 16+** εγκατεστημένο.  
- IDE συμβατό με Maven (IntelliJ IDEA, Eclipse κ.λπ.).  
- Βασικές γνώσεις Java και εξοικείωση με έννοιες email.

## Ρύθμιση του Aspose.Email για Java
### Διαμόρφωση Maven
Προσθέστε την ακόλουθη εξάρτηση στο `pom.xml` σας:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Απόκτηση Άδειας
Το Aspose.Email απαιτεί άδεια για χρήση σε παραγωγή:
- **Δωρεάν δοκιμή** – αξιολόγηση 30 ημερών.  
- **Προσωρινή άδεια** – εκτεταμένη δοκιμή.  
- **Πλήρης άδεια** – διαρκής συνδρομή.

Αρχικοποιήστε την άδεια πριν από οποιαδήποτε λειτουργία email:

```java
License license = new License();
license.setLicense("path/to/Aspose.Total.Java.lic");
```

## Ορισμός Σημαίας Outlook Java (Δυνατότητα 1)
### Άμεση απάντηση
Φορτώστε ένα `MailMessage`, μετατρέψτε το σε `MapiMessage`, διαμορφώστε το `FollowUpOptions` και καλέστε το `FollowUpManager.setOptions`. Αυτή η ακολουθία δημιουργεί ένα πλήρως σηματοδοτημένο στοιχείο Outlook με λίγες μόνο γραμμές κώδικα Java.

### Βήμα 1: Δημιουργία και Αρχικοποίηση του Μηνύματος
`MailMessage` είναι η υψηλού επιπέδου κλάση του Aspose.Email που αντιπροσωπεύει ένα email. Αφού δημιουργήσετε το μήνυμα, το μετατρέπετε σε `MapiMessage` για διαχείριση σημαίας.

```java
MailMessage mailMsg = new MailMessage();
mailMsg.setSender(new MailAddress("AETest12@gmail.com"));
mailMsg.getTo().addMailAddress(new MailAddress("receiver@gmail.com"));
mailMsg.setBody("This message will test if follow up options can be added to a new mapi message.");
MapiMessage mapi = MapiMessage.fromMailMessage(mailMsg);
```
*Αρχικά δημιουργούμε ένα `MailMessage`, ορίζουμε αποστολέα/παραλήπτη, και στη συνέχεια το μετατρέπουμε σε `MapiMessage` για διαχείριση σημαίας.*

### Βήμα 2: Ορισμός Ημερομηνιών Παρακολούθησης (Υπενθύμιση Σημαίας Outlook)
`FollowUpOptions` περιέχει τις ημερομηνίες έναρξης, υπενθύμισης και λήξης. Χρησιμοποιήστε το `Calendar` της Java για να ορίσετε ακριβείς χρονικές σήμανσεις.

```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 14, 40, 0);
Date dtStartDate = calendar.getTime();
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
calendar.add(Calendar.DATE, 1);
Date dtDueDate = calendar.getTime();
```
*Εδώ ορίζουμε τις ημερομηνίες έναρξης, υπενθύμισης (η **outlook flag reminder**) και λήξης χρησιμοποιώντας την κλάση `Calendar`.*

### Βήμα 3: Εφαρμογή Επιλογών Παρακολούθησης
Η μέθοδος `FollowUpManager.setOptions` προσθέτει τη σημαία στο `MapiMessage`.

```java
FollowUpOptions options = new FollowUpOptions("Follow Up", dtStartDate, dtDueDate, dtReminderDate);
FollowUpManager.setOptions(mapi, options);
```
*Το αντικείμενο `FollowUpOptions` περιέχει όλες τις λεπτομέρειες της σημαίας, τις οποίες εφαρμόζουμε με το `FollowUpManager.setOptions`.*

### Βήμα 4: Αποθήκευση του Μηνύματος
Αποθηκεύστε το σηματοδοτημένο μήνυμα ως αρχείο `.msg` ώστε το Outlook να μπορεί να εμφανίσει τη σημαία.

```java
mapi.save(outputDir + "SetFollowUpflag_out.msg");
```
*Το μήνυμα αποθηκεύεται ως αρχείο `.msg` με τη σημαία επισυναπτόμενη.*

## Πώς να Ορίσετε Σημαία για Παραλήπτες (Δυνατότητα 2);
Χρησιμοποιήστε το `FollowUpManager.setFlagForRecipients` μετά το σήμανση του μηνύματος ως πρόχειρο. Αυτή η μέθοδος προσθέτει τη σημαία παρακολούθησης μόνο στο αντίγραφο του παραλήπτη, αφήνοντας την προβολή του αποστολέα αμετάβλητη. Απαιτεί τον ορισμό του `MessageFlags.MSGFLAG_UNSENT` πριν την εφαρμογή της σημαίας. Μπορείτε επίσης να προσαρμόσετε τις ημερομηνίες έναρξης, υπενθύμισης και λήξης χρησιμοποιώντας ένα αντικείμενο `FollowUpOptions` πριν καλέσετε τη μέθοδο.

### Άμεση απάντηση
Σημειώστε το μήνυμα ως πρόχειρο χρησιμοποιώντας το `MessageFlags.MSGFLAG_UNSENT`, στη συνέχεια καλέστε το `FollowUpManager.setFlagForRecipients`. Το Outlook θα εμφανίσει τη σημαία μόνο στους παραλήπτες, όχι στον αποστολέα.

### Επισκόπηση
Μερικές φορές χρειάζεται η σημαία να εμφανίζεται **μόνο για τους παραλήπτες**. Αυτό το παράδειγμα σηματοδοτεί πρώτα το μήνυμα ως πρόχειρο, και στη συνέχεια προσθέτει τη σημαία.

#### Βήμα 1: Σήμανση ως Πρόχειρο
`MessageFlags` είναι μια απαρίθμηση MAPI που ελέγχει την κατάσταση του μηνύματος. Ο ορισμός του `MSGFLAG_UNSENT` λέει στο Outlook ότι το στοιχείο είναι πρόχειρο.

```java
mapi.setMessageFlags(MapiMessageFlags.MSGFLAG_UNSENT);
```
*Η σήμανση του μηνύματος ως μη απεσταλμένου εξασφαλίζει ότι το Outlook το θεωρεί ως πρόχειρο.*

#### Βήμα 2: Ορισμός Σημαίας Παραλήπτη
`FollowUpManager.setFlagForRecipients` προσθέτει τη σημαία αποκλειστικά στο αντίγραφο του παραλήπτη.

```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
FollowUpManager.setFlagForRecipients(mapi, "Follow up", dtReminderDate);
```
*Η σημαία είναι τώρα ορατή μόνο στους παραλήπτες – ένα κλασικό σενάριο **flag for recipients**.*

## Πώς να Σημειώσετε μια Σημαία Παρακολούθησης Outlook ως Ολοκληρωμένη (Δυνατότητα 3);
Φορτώστε το αρχείο .msg σε ένα `MapiMessage`, στη συνέχεια καλέστε το `FollowUpManager.completeFlag`. Αυτό ενημερώνει την κατάσταση της σημαίας σε Ολοκληρωμένη και προσθέτει ένα σημάδι ελέγχου στο Outlook. Μετά την ολοκλήρωση, αποθηκεύστε το μήνυμα για να διατηρηθεί η αλλαγή. Μπορείτε επίσης να ορίσετε τον χρόνο ολοκλήρωσης προσαρμόζοντας την ιδιότητα `FlagCompleteTime` εάν απαιτείται για σκοπούς ελέγχου.

### Άμεση απάντηση
Φορτώστε το υπάρχον αρχείο `.msg` σε ένα `MapiMessage`, καλέστε το `FollowUpManager.completeFlag` και αποθηκεύστε το αρχείο. Η κατάσταση της σημαίας αλλάζει σε “Completed” και εμφανίζεται με σημάδι ελέγχου στο Outlook.

### Βήμα 1: Φόρτωση του Μηνύματος
`MapiMessage` μπορεί να διαβάσει ένα αποθηκευμένο αρχείο `.msg`, παρέχοντάς σας πλήρη πρόσβαση στις ιδιότητες MAPI του.

```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
```

### Βήμα 2: Σήμανση ως Ολοκληρωμένο και Αποθήκευση
`FollowUpManager.completeFlag` ενημερώνει την κατάσταση της σημαίας, μετά από αυτό διατηρείτε τις αλλαγές.

```java
FollowUpManager.markAsCompleted(mapi);
mapi.save(outputDir + "MarkedCompleted_out.msg");
```
*Η κατάσταση της σημαίας αλλάζει σε “Completed” και το ενημερωμένο αρχείο αποθηκεύεται.*

## Πώς να Αφαιρέσετε μια Σημαία Παρακολούθησης Outlook (Δυνατότητα 4);
Ανοίξτε το αρχείο .msg με το `MapiMessage`, καλέστε το `FollowUpManager.clearFlag`, και στη συνέχεια αποθηκεύστε το μήνυμα. Αυτό αφαιρεί όλες τις ιδιότητες MAPI σχετικές με τη σημαία, ώστε το Outlook να μην εμφανίζει πλέον κανένα δείκτη παρακολούθησης. Χρησιμοποιήστε το όταν μια εργασία ακυρώνεται ή δεν είναι πλέον σχετική. Βεβαιωθείτε ότι καθαρίζετε επίσης τυχόν προσαρμοσμένες ιδιότητες υπενθύμισης για να αποφύγετε υπολειπόμενες ειδοποιήσεις.

### Άμεση απάντηση
Ανοίξτε το αρχείο `.msg` με το `MapiMessage`, καλέστε το `FollowUpManager.clearFlag` και αποθηκεύστε το αρχείο. Το μήνυμα δεν θα εμφανίζει πλέον κανένα δείκτη παρακολούθησης στο Outlook.

### Βήμα 1: Φόρτωση και Καθαρισμός Σημαίας
`FollowUpManager.clearFlag` αφαιρεί όλες τις ιδιότητες σχετικές με τη σημαία από το μήνυμα.

```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpManager.clearFlag(mapi);
mapi.save(outputDir + "FollowUpFlagRemoved_out.msg");
```
*Το μήνυμα αποθηκεύεται χωρίς καμία σημαία παρακολούθησης.*

## Πώς να Διαβάσετε τις Επιλογές Σημαίας (Δυνατότητα 5);
Καλέστε το `FollowUpManager.getOptions` σε ένα φορτωμένο `MapiMessage` για να λάβετε ένα αντικείμενο `FollowUpOptions`. Αυτό το αντικείμενο παρέχει τις ημερομηνίες έναρξης, λήξης, υπενθύμισης και το θέμα της σημαίας, επιτρέποντάς σας να εμφανίσετε ή να καταγράψετε τις λεπτομέρειες της σημαίας. Είναι χρήσιμο για αναφορές και ελέγχους συμμόρφωσης.

### Άμεση απάντηση
Χρησιμοποιήστε το `FollowUpManager.getOptions` σε ένα φορτωμένο `MapiMessage` για να ανακτήσετε ένα αντικείμενο `FollowUpOptions` που περιέχει τις ημερομηνίες έναρξης, λήξης, υπενθύμισης και το θέμα της σημαίας. Αυτό είναι χρήσιμο για αναφορές ή ελέγχους συμμόρφωσης.

### Βήμα 1: Ανάκτηση Επιλογών
Το επιστρεφόμενο αντικείμενο `options` σας δίνει πλήρη ορατότητα στη διαμόρφωση της σημαίας.

```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpOptions options = FollowUpManager.getOptions(mapi);
```
*Το αντικείμενο `options` περιέχει τώρα τις ημερομηνίες έναρξης, λήξης και υπενθύμισης, καθώς και το θέμα της σημαίας – χρήσιμο όταν χρειάζεται να **read flag options** για αναφορά.*

## Πρακτικές Εφαρμογές
- **Ενσωμάτωση Διαχείρισης Εργασιών:** Συγχρονίστε τα σηματοδοτημένα email με Jira, Trello ή Azure Boards.  
- **Αυτοματοποιημένες Υπενθυμίσεις:** Δημιουργήστε καθημερινά email υπενθύμισης για εκκρεμείς παρακολουθήσεις.  
- **Έλεγχοι Συμμόρφωσης:** Εξάγετε τα δεδομένα σημαίας για ρυθμιστικές αναφορές, αξιοποιώντας τη δυνατότητα προγραμματιστικής ανάγνωσης των επιλογών σημαίας.

## Σκέψεις Απόδοσης
- **Υπολογισμοί Ημερομηνιών:** Υπολογίστε τις ημερομηνίες μία φορά ανά παρτίδα αντί μέσα σε βρόχους.  
- **Διαχείριση Πόρων:** Κλείστε τυχόν ροές ή χειριστές αρχείων μετά την αποθήκευση των μηνυμάτων.  
- **Χρήση Μνήμης:** Επεξεργαστείτε μεγάλες θυρίδες αλληλογραφίας σε τμήματα για να αποφύγετε πίεση στη μνήμη heap· το Aspose.Email μπορεί να διαχειριστεί θυρίδες πολλαπλών εκατοντάδων σελίδων χωρίς να φορτώνει ολόκληρο το αρχείο στη μνήμη.

## Συνηθισμένα Προβλήματα και Λύσεις
| Πρόβλημα | Αιτία | Διόρθωση |
|----------|-------|----------|
| Η σημαία δεν εμφανίζεται στο Outlook | Το μήνυμα αποθηκεύτηκε χωρίς τα σωστά `MessageFlags` | Βεβαιωθείτε ότι το `setMessageFlags` είναι ορισμένο σε `MSGFLAG_UNSENT` πριν την εφαρμογή σημαίας σε παραλήπτες. |
| Η αποθήκευση προκαλεί `AccessDeniedException` | Λανθασμένη διαδρομή αρχείου ή έλλειψη δικαιωμάτων εγγραφής | Επαληθεύστε ότι ο φάκελος εξόδου υπάρχει και η εφαρμογή έχει δικαιώματα εγγραφής. |
| Οι ημερομηνίες είναι εκτός μιας ημέρας | Ασυμφωνία ζώνης ώρας | Χρησιμοποιήστε `TimeZone.getTimeZone("GMT")` ή τη δική σας τοπική ζώνη σταθερά. |

## Συχνές Ερωτήσεις
**Ε: Τι είναι το Aspose.Email για Java;**  
Είναι ένα καθαρό API Java που σας επιτρέπει να δημιουργείτε, διαβάζετε και να διαχειρίζεστε αρχεία email (MSG, EML κ.λπ.) χωρίς να χρειάζεται εγκατεστημένο Outlook.

**Ε: Πώς μπορώ να αποκτήσω δωρεάν άδεια δοκιμής;**  
Επισκεφθείτε τον [ιστότοπο Aspose](https://releases.aspose.com/email/java/) για να κατεβάσετε μια δοκιμαστική έκδοση 30 ημερών.

**Ε: Μπορώ να ορίσω πολλαπλές σημαίες παρακολούθησης σε ένα μόνο μήνυμα;**  
Το Outlook υποστηρίζει μόνο μία σημαία ανά μήνυμα, αλλά μπορείτε να αποθηκεύσετε πρόσθετα δεδομένα εργασίας σε προσαρμοσμένες ιδιότητες MAPI.

**Ε: Το μήνυμά μου δεν αποθηκεύεται μετά τον ορισμό μιας σημαίας. Τι πρέπει να ελέγξω;**  
Επιβεβαιώστε ότι η διαδρομή `outputDir` είναι έγκυρη και ότι η εφαρμογή έχει δικαίωμα εγγραφής σε αυτήν την τοποθεσία.

**Ε: Πώς μπορώ να αφαιρέσω σημαίες από πολλά μηνύματα ταυτόχρονα;**  
Διασχίστε τη συλλογή των μηνυμάτων σας και καλέστε το `FollowUpManager.clearFlag` σε κάθε `MapiMessage`.

## Πόροι
- [Τεκμηρίωση](https://reference.aspose.com/email/java/)
- [Λήψη Aspose.Email για Java](https://releases.aspose.com/email/java/)
- [Δωρεάν Δοκιμή Aspose.Email](https://purchase.aspose.com/purchase/free-trial/aspose-email-java)

---
**Τελευταία Ενημέρωση:** 2026-07-27  
**Δοκιμάστηκε Με:** Aspose.Email for Java 25.4 (JDK 16)  
**Συγγραφέας:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Σχετικές Οδηγίες

- [Διαχείριση Κατηγοριών Outlook με Aspose.Email για Java - Αναλυτικός Οδηγός](/email/java/calendar-appointments/manage-outlook-categories-aspose-email-java/)
- [Δημιουργία σημειώσεων Outlook Java με Aspose.Email – Πλήρης Οδηγός](/email/java/calendar-appointments/create-customize-outlook-notes-aspose-email-java/)
- [Δημιουργία Εργασιών στο Microsoft Exchange με Aspose.Email για Java: Πλήρης Οδηγός](/email/java/exchange-server-integration/create-tasks-exchange-aspose-email-java/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}