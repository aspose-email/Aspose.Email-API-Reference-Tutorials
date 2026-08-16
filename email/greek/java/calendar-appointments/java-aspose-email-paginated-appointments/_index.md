---
date: '2026-08-16'
description: Μάθετε πώς να σελιδοποιήσετε τα ραντεβού σε Java χρησιμοποιώντας το Aspose.Email
  και να ανακτήσετε δεδομένα exchange calendar αποδοτικά, ακολουθώντας αποδεδειγμένες
  βέλτιστες πρακτικές pagination.
keywords:
- how to paginate appointments
- retrieve exchange calendar
- java pagination best practices
- Aspose.Email for Java
lastmod: '2026-08-16'
og_description: Μάθετε πώς να σελιδοποιήσετε τα ραντεβού σε Java χρησιμοποιώντας το
  Aspose.Email και να ανακτήσετε δεδομένα exchange calendar αποδοτικά. Ακολουθήστε
  step‑by‑step κώδικα και συμβουλές βέλτιστων πρακτικών.
og_image_alt: Developer guide showing paginated appointment retrieval from Exchange
  using Aspose.Email for Java
og_title: Πώς να σελιδοποιήσετε τα ραντεβού σε Java με Aspose.Email
schemas:
- author: Aspose
  dateModified: '2026-08-16'
  description: Learn how to paginate appointments in Java using Aspose.Email and retrieve
    exchange calendar data efficiently with proven pagination best practices.
  headline: How to paginate appointments in Java with Aspose.Email
  type: TechArticle
- description: Learn how to paginate appointments in Java using Aspose.Email and retrieve
    exchange calendar data efficiently with proven pagination best practices.
  name: How to paginate appointments in Java with Aspose.Email
  steps:
  - name: '**Reduce memory footprint** – only the current page lives in RAM.'
    text: '**Reduce memory footprint** – only the current page lives in RAM.'
  - name: '**Improve network efficiency** – each request transfers a predictable amount
      of data.'
    text: '**Improve network efficiency** – each request transfers a predictable amount
      of data.'
  - name: '**Enable responsive UI** – users can navigate page‑by‑page without waiting
      for a massive load.'
    text: '**Enable responsive UI** – users can navigate page‑by‑page without waiting
      for a massive load.'
  - name: '**Import pagination classes** – `PagingOptions`, `PagedResult`, and `Appointment`.'
    text: '**Import pagination classes** – `PagingOptions`, `PagedResult`, and `Appointment`.'
  - name: '**Define page size** – pick a value that matches your performance goals
      (50–200 is a common sweet spot).'
    text: '**Define page size** – pick a value that matches your performance goals
      (50–200 is a common sweet spot).'
  - name: '**Iterate through pages** – use a `while` loop that stops when the service
      reports no further pages.'
    text: '**Iterate through pages** – use a `while` loop that stops when the service
      reports no further pages.'
  - name: '**Process each appointment** – extract subject, start time, and any custom
      properties you need.'
    text: '**Process each appointment** – extract subject, start time, and any custom
      properties you need.'
  - name: '**Dispose the client** – ensure cleanup in a finally block.'
    text: '**Dispose the client** – ensure cleanup in a finally block.'
  - name: '**Corporate email management** – automate bulk calendar clean‑ups, generate
      compliance reports, or archive old meetings without overloading the server.'
    text: '**Corporate email management** – automate bulk calendar clean‑ups, generate
      compliance reports, or archive old meetings without overloading the server.'
  - name: '**Customer support systems** – pull support‑ticket appointments in a paged
      grid, allowing agents to scroll through large backlogs efficiently.'
    text: '**Customer support systems** – pull support‑ticket appointments in a paged
      grid, allowing agents to scroll through large backlogs efficiently.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Email supports Exchange 2007 through Exchange Online, provided
      the EWS endpoint is reachable and credentials are valid.
    question: Can I use Aspose.Email for Java with any Exchange server version?
  - answer: Pagination reduces memory consumption, lowers network latency, and simplifies
      UI pagination controls, making large calendar views feasible.
    question: What are the benefits of using paginated appointment retrieval?
  - answer: Start with 50–200 items per page; increase the number if your network
      latency is low and the server has ample RAM, or decrease it for mobile or high‑latency
      environments.
    question: How do I decide the right “items per page java” value?
  - answer: A permanent license removes evaluation limits and is required for commercial
      deployments; a free trial is sufficient for development and testing.
    question: Is a license required for production use?
  - answer: Yes, `Appointment` objects expose start and end times with full time‑zone
      information, and the SDK can convert them to the local time zone as needed.
    question: Does Aspose.Email handle time‑zone conversions automatically?
  type: FAQPage
tags:
- paginate appointments
- Aspose.Email
- Java EWS client
- exchange calendar
title: Πώς να σελιδοποιήσετε τα ραντεβού σε Java με Aspose.Email
url: /el/java/calendar-appointments/java-aspose-email-paginated-appointments/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Πώς να σελιδοποιήσετε ραντεβού σε Java με Aspose.Email

## Εισαγωγή

Σε αυτό το tutorial θα ανακαλύψετε **πώς να σελιδοποιήσετε ραντεβού** όταν εργάζεστε με έναν διακομιστή Exchange από μια εφαρμογή Java. Η σελιδοποίηση είναι μια βασική **java pagination best practice** που διατηρεί τη χρήση μνήμης χαμηλή, επιταχύνει τις κλήσεις δικτύου και κάνει την απόδοση του UI πιο ομαλή. Θα μάθετε να συνδέεστε στο Exchange χρησιμοποιώντας το `EWSClient`, να ανακτάτε στοιχεία ημερολογίου σελίδα‑με‑σελίδα και να εφαρμόζετε πρακτικές συμβουλές που αποτρέπουν κοινά προβλήματα.

**Τι θα μάθετε**
- Πώς να προσθέσετε το Aspose.Email for Java σε ένα έργο Maven.  
- Πώς να δημιουργήσετε και να επαναχρησιμοποιήσετε μια παρουσία `IEWSClient`.  
- Πώς να καλέσετε το `listAppointmentsByPage` με μια ρυθμιζόμενη τιμή **items per page java**.  
- Πώς να διαχειριστείτε σφάλματα, να απελευθερώσετε πόρους και να βελτιώσετε την απόδοση.  

Τώρα ας ελέγξουμε ότι έχετε όλα όσα χρειάζεστε πριν βυθιστείτε στον κώδικα.

## Γρήγορες απαντήσεις
- **Ποια βιβλιοθήκη χρησιμοποιείται;** Aspose.Email for Java.  
- **Ποια είναι η κύρια τεχνική;** Java pagination best practices with `listAppointmentsByPage`.  
- **Πόσα στοιχεία ανά σελίδα μπορώ να ορίσω;** Οποιοσδήποτε ακέραιος· τυπικές τιμές παραγωγής είναι 50–200, η επίδειξη χρησιμοποιεί 2 για σαφήνεια.  
- **Χρειάζομαι άδεια;** Μια δωρεάν δοκιμή λειτουργεί για δοκιμές· μια μόνιμη άδεια αφαιρεί τους περιορισμούς αξιολόγησης.  
- **Είναι συμβατό με JDK 16+;** Ναι, η βιβλιοθήκη υποστηρίζει JDK 16 και νεότερα.

## Τι είναι η σελιδοποίηση και γιατί είναι σημαντική;
Η σελιδοποίηση διαιρεί ένα μεγάλο σύνολο αποτελεσμάτων σε μικρότερες, διαδοχικές σελίδες. Η αίτηση ενός υποσυνόλου—π.χ., 100 ραντεβού—μειώνει την κατανάλωση μνήμης, περιορίζει το φορτίο δικτύου και παρέχει προβλέψιμη καθυστέρηση, κάτι που βελτιώνει την ανταπόκριση του UI και μειώνει το φορτίο του διακομιστή. Επίσης, απλοποιεί τη διαχείριση σφαλμάτων και επιτρέπει αποδοτική κύλιση σε εφαρμογές-πελάτες.

## Επισκόπηση βέλτιστων πρακτικών σελιδοποίησης Java

Όταν εργάζεστε με χιλιάδες στοιχεία ημερολογίου, η λήψη ολόκληρης της συλλογής σε μία κλήση μπορεί γρήγορα να εξαντλήσει τη μνήμη και να αυξήσει τους χρόνους απόκρισης. Διασπώντας το σύνολο αποτελεσμάτων σε μικρότερες, διαχειρίσιμες σελίδες, μπορείτε:

1. **Μείωση αποτυπώματος μνήμης** – μόνο η τρέχουσα σελίδα βρίσκεται στη RAM.  
2. **Βελτίωση αποδοτικότητας δικτύου** – κάθε αίτηση μεταφέρει μια προβλέψιμη ποσότητα δεδομένων.  
3. **Ενεργοποίηση ανταποκρινόμενου UI** – οι χρήστες μπορούν να περιηγηθούν σελίδα‑με‑σελίδα χωρίς να περιμένουν για μεγάλο φορτίο.  

Στη Java, το τυπικό μοτίβο είναι να καθορίσετε μια τιμή **items per page** που ισορροπεί την καθυστέρηση και τη μνήμη, και στη συνέχεια να επαναλαμβάνετε τις σελίδες μέχρι ο διακομιστής να υποδείξει την τελευταία σελίδα. Τα παραδείγματα κώδικα παρακάτω ακολουθούν ακριβώς αυτό το μοτίβο.

## Προαπαιτούμενα

Πριν προχωρήσετε σε αυτό το tutorial, βεβαιωθείτε ότι έχετε τα εξής:

### Απαιτούμενες βιβλιοθήκες και εκδόσεις
- Aspose.Email for Java ≥ 25.4 (η βιβλιοθήκη υποστηρίζει **50+** μορφές εισόδου και εξόδου, και μπορεί να επεξεργαστεί ημερολόγια με εκατοντάδες σελίδες χωρίς να φορτώνει ολόκληρο το αρχείο στη μνήμη).  
- Java Development Kit (JDK) 16 ή νεότερο.

### Ρύθμιση περιβάλλοντος
- Ένα IDE όπως IntelliJ IDEA ή Eclipse.  
- Εγκατεστημένο Maven για διαχείριση εξαρτήσεων.  

### Προαπαιτούμενες γνώσεις
- Εξοικείωση με τη βασική σύνταξη Java και Maven.  
- Προαιρετικό αλλά χρήσιμο: κατανόηση των εννοιών Exchange Web Services (EWS).

## Ρύθμιση Aspose.Email για Java

Το Aspose.Email είναι μια ισχυρή βιβλιοθήκη σχεδιασμένη για να απλοποιεί εργασίες ενσωμάτωσης email και ημερολογίου. Προσθέστε την στο Maven έργο σας με την ακόλουθη εξάρτηση:

**Maven dependency**

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Βήματα απόκτησης άδειας

Το Aspose.Email προσφέρει δωρεάν δοκιμή, προσωρινή άδεια 30 ημερών και πλήρη εμπορική άδεια. Η δοκιμή σας επιτρέπει να εξερευνήσετε όλες τις λειτουργίες, αλλά μια μόνιμη άδεια αφαιρεί τους περιορισμούς αξιολόγησης και απαιτείται για παραγωγικές εγκαταστάσεις.

### Βασική αρχικοποίηση

Για να ξεκινήσετε να χρησιμοποιείτε τη βιβλιοθήκη, τοποθετήστε το αρχείο άδειας (`Aspose.Email.lic`) στο classpath σας και φορτώστε το κατά την εκκίνηση της εφαρμογής:

```java
License license = new License();
license.setLicense("Aspose.Email.lic");
```

Με τη βιβλιοθήκη έτοιμη, μπορείτε τώρα να δημιουργήσετε έναν πελάτη που επικοινωνεί με το Exchange.

## Πώς να συνδεθείτε στο Exchange με Java
Δημιουργήστε ένα `IEWSClient` παρέχοντας το URL της υπηρεσίας Exchange, το όνομα χρήστη, τον κωδικό πρόσβασης και προαιρετικό domain. Επαναχρησιμοποιήστε αυτόν τον μοναδικό πελάτη για όλες τις κλήσεις σελιδοποίησης ώστε να αποφύγετε επαναλαμβανόμενα TLS handshake, και πάντα καλέστε `dispose()` σε ένα finally block για να απελευθερώσετε πόρους δικτύου και να αποτρέψετε διαρροές σύνδεσης.

```java
IEWSClient client = EWSClient.getEWSClient("https://mail.example.com/EWS/Exchange.asmx", "user", "pwd", "domain");
try {
    // pagination logic will go here
} finally {
    client.dispose();
}
```

## Πώς να καταγράψετε ραντεβού με υποστήριξη σελιδοποίησης
Χρησιμοποιήστε το `listAppointmentsByPage` στο `IEWSClient`, περνώντας ένα αντικείμενο `PagingOptions` που καθορίζει το επιθυμητό `itemsPerPage`. Η μέθοδος επιστρέφει ένα `PagedResult<Appointment>` που περιέχει το τρέχον τμήμα και μια σημαία που υποδεικνύει αν υπάρχουν περισσότερες σελίδες. Επαναλάβετε μέχρι το `hasMorePages` να είναι false, επεξεργαζόμενοι κάθε ραντεβού καθώς φτάνει.

**Πρόταση ορισμού:** `PagingOptions` ορίζει το μέγεθος σελίδας και την μετατόπιση για μια σελιδοποιημένη αίτηση. `PagedResult<T>` περιλαμβάνει μια σελίδα αντικειμένων τύπου T και υποδεικνύει αν υπάρχουν επιπλέον σελίδες. `Appointment` αντιπροσωπεύει ένα στοιχείο ημερολογίου με ιδιότητες όπως θέμα, ώρα έναρξης και τοποθεσία.

**Βήματα υλοποίησης**

1. **Εισαγωγή κλάσεων σελιδοποίησης** – `PagingOptions`, `PagedResult` και `Appointment`.  
2. **Ορισμός μεγέθους σελίδας** – επιλέξτε μια τιμή που ταιριάζει στους στόχους απόδοσής σας (50–200 είναι ένα κοινό sweet spot).  
3. **Επανάληψη μέσω σελίδων** – χρησιμοποιήστε ένα `while` loop που σταματά όταν η υπηρεσία αναφέρει ότι δεν υπάρχουν περαιτέρω σελίδες.  
4. **Επεξεργασία κάθε ραντεβού** – εξάγετε το θέμα, την ώρα έναρξης και τυχόν προσαρμοσμένες ιδιότητες που χρειάζεστε.  
5. **Απελευθέρωση του πελάτη** – εξασφαλίστε τον καθαρισμό σε ένα finally block.

```java
int itemsPerPage = 100; // adjust based on latency and memory constraints
PagingOptions paging = new PagingOptions(itemsPerPage);
PagedResult<Appointment> page = client.listAppointmentsByPage(paging);
while (page != null && page.getItems() != null) {
    for (Appointment appt : page.getItems()) {
        System.out.println("Subject: " + appt.getSubject());
        System.out.println("Start: " + appt.getStartTime());
    }
    if (!page.hasMorePages()) break;
    page = client.listAppointmentsByPage(paging);
}
```

**Κύριες επιλογές διαμόρφωσης**
- **Items per page** – ορίστε σε 50–200 για τις περισσότερες επιχειρησιακές περιπτώσεις· αυξήστε μόνο μετά τη μέτρηση της καθυστέρησης.  
- **Page offset** – διαχειρίζεται αυτόματα από το SDK· σπάνια χρειάζεται να το διαχειριστείτε χειροκίνητα.  

## Κοινά προβλήματα και συμβουλές

- **Επιλογή του σωστού μεγέθους σελίδας** – τιμές κάτω από 10 προκαλούν υπερβολικά round‑trips· τιμές πάνω από 500 μπορεί να αυξήσουν τη χρήση μνήμης. Ξεκινήστε με 100 και προσαρμόστε μετά το profiling.  
- **Ποτέ μην ξεχνάτε να απελευθερώσετε** – η παραμέληση του `dispose()` αφήνει ανοιχτές συνδέσεις HTTP, εξαντλώντας τελικά το pool συνδέσεων και προκαλώντας timeouts.  
- **Διαχείριση εξαιρέσεων με χάρη** – τυλίξτε τις κλήσεις `listAppointmentsByPage` σε try‑catch blocks για `IOException` ή `ServiceException`. Καταγράψτε το σφάλμα και προαιρετικά επαναλάβετε με εκθετική back‑off.  
- **Επαναχρησιμοποιήστε τον πελάτη** – η δημιουργία νέου `IEWSClient` για κάθε σελίδα προσθέτει περιττά TLS handshakes και μειώνει το throughput.  

## Πρακτικές εφαρμογές

Η υλοποίηση ανάκτησης ραντεβού με σελιδοποίηση είναι χρήσιμη σε πολλά πραγματικά σενάρια:

1. **Διαχείριση εταιρικού email** – αυτοματοποιήστε μαζικές εκκαθαρίσεις ημερολογίων, δημιουργήστε εκθέσεις συμμόρφωσης ή αρχειοθετήστε παλιά ραντεβού χωρίς να υπερφορτώνετε τον διακομιστή.  
2. **Συστήματα εξυπηρέτησης πελατών** – αντλήστε ραντεβού support‑ticket σε σελιδοποιημένο grid, επιτρέποντας στους πράκτορες να κυλούν μεγάλους backlog αποδοτικά.  
3. **Πλατφόρμες κράτησης πόρων** – εμφανίστε τη διαθεσιμότητα δωματίων ή εξοπλισμού σελίδα‑με‑σελίδα, διατηρώντας το front‑end ανταποκρινόμενο ακόμη και όταν υπάρχουν χιλιάδες κρατήσεις.  

## Παραμέτρους απόδοσης

Για να εξάγετε το μέγιστο από το Aspose.Email με Java:

- **Βελτιστοποίηση σελιδοποίησης** – δοκιμάστε διαφορετικές τιμές `itemsPerPage`; σε τυπικό LAN 1 Gbps, 150 στοιχεία ανά σελίδα δίνουν ~200 ms latency.  
- **Διαχείριση μνήμης** – καλέστε `dispose()` άμεσα και αποφύγετε το κράτημα μεγάλων συλλογών `Appointment` μετά την επεξεργασία.  
- **Διαχείριση συνδέσεων** – επαναχρησιμοποιήστε μια μοναδική παρουσία `IEWSClient` σε πολλαπλές λειτουργίες· το SDK εσωτερικά κάνει pooling των HTTP συνδέσεων για μέγιστο throughput.  

## Συμπέρασμα

Σε αυτό το tutorial μάθατε **πώς να σελιδοποιήσετε ραντεβού** όταν συνδέεστε σε διακομιστή Exchange με Aspose.Email for Java. Εφαρμόζοντας το παρουσιασμένο μοτίβο σελιδοποίησης, θα διατηρήσετε τη χρήση μνήμης προβλέψιμη, θα βελτιώσετε τους χρόνους απόκρισης και θα προσφέρετε μια πιο ομαλή εμπειρία χρήστη για οποιαδήποτε εφαρμογή με έντονη χρήση ημερολογίου.

### Επόμενα βήματα
- Εξερευνήστε επιπλέον δυνατότητες του Aspose.Email όπως αποστολή email, συγχρονισμό φακέλων και ανάλυση MIME.  
- Πειραματιστείτε με διαφορετικές ρυθμίσεις `itemsPerPage` σε περιβάλλον staging για να βρείτε την βέλτιστη ισορροπία για το δίκτυο και το υλικό σας.  
- Ενσωματώστε τη λογική σελιδοποίησης σε ένα REST endpoint ή σε grid UI Swing/JavaFX για χρήση από τελικούς χρήστες.  

Έτοιμοι να εφαρμόσετε τις νέες σας δεξιότητες; Υλοποιήστε τα αποσπάσματα στο Java έργο σας σήμερα και ζήστε από πρώτο χέρι τα οφέλη στην απόδοση.

## Συχνές ερωτήσεις

**Ε: Μπορώ να χρησιμοποιήσω το Aspose.Email for Java με οποιαδήποτε έκδοση διακομιστή Exchange;**  
Α: Ναι, το Aspose.Email υποστηρίζει Exchange 2007 έως Exchange Online, εφόσον το endpoint EWS είναι προσβάσιμο και τα διαπιστευτήρια είναι έγκυρα.

**Ε: Ποια είναι τα οφέλη της χρήσης σελιδοποιημένης ανάκτησης ραντεβού;**  
Α: Η σελιδοποίηση μειώνει την κατανάλωση μνήμης, μειώνει την καθυστέρηση δικτύου και απλοποιεί τα στοιχεία ελέγχου σελιδοποίησης UI, καθιστώντας εφικτές μεγάλες προβολές ημερολογίου.

**Ε: Πώς να αποφασίσω τη σωστή τιμή “items per page java”;**  
Α: Ξεκινήστε με 50–200 στοιχεία ανά σελίδα· αυξήστε τον αριθμό αν η καθυστέρηση δικτύου είναι χαμηλή και ο διακομιστής διαθέτει άφθονη RAM, ή μειώστε το για κινητές ή περιβάλλοντα υψηλής καθυστέρησης.

**Ε: Απαιτείται άδεια για παραγωγική χρήση;**  
Α: Μια μόνιμη άδεια αφαιρεί τους περιορισμούς αξιολόγησης και απαιτείται για εμπορικές εγκαταστάσεις· μια δωρεάν δοκιμή είναι επαρκής για ανάπτυξη και δοκιμές.

**Ε: Το Aspose.Email διαχειρίζεται αυτόματα τις μετατροπές ζώνης ώρας;**  
Α: Ναι, τα αντικείμενα `Appointment` εκθέτουν τις ώρες έναρξης και λήξης με πλήρη πληροφορία ζώνης ώρας, και το SDK μπορεί να τις μετατρέψει στη τοπική ζώνη ώρας όπως απαιτείται.

**Last Updated:** 2026-08-16  
**Tested With:** Aspose.Email for Java 25.4 (jdk16 classifier)  
**Author:** Aspose

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

```java
// Import necessary Aspose.Email packages
import com.aspose.email.EWSClient;
import com.aspose.email.IEWSClient;

public class EmailSetup {
    public static void main(String[] args) {
        // Initialize the EWS client with server credentials
        IEWSClient client = EWSClient.getEWSClient("exchange.domain.com", "username", "password");
        // Always remember to dispose of the client after use
        if (client != null) {
            ((com.aspose.email.system.IDisposable)client).dispose();
        }
    }
}
```

```java
import com.aspose.email.EWSClient;
import com.aspose.email.IEWSClient;
```

```java
// Replace with your actual domain, username, and password
IEWSClient client = EWSClient.getEWSClient("exchange.domain.com", "username", "password");
```

```java
if (client != null) {
    ((com.aspose.email.system.IDisposable)client).dispose();
}
```

```java
import com.aspose.email.AppointmentPageInfo;
import com.aspose.email.IEWSClient;
import com.aspose.email.system.collections.generic.List;
```

```java
IEWSClient client = EWSClient.getEWSClient("exchange.domain.com", "username", "password");
try {
    // Define total number of appointments per page – this is the “items per page java” setting
    int itemsPerPage = 2;
    List<AppointmentPageInfo> pages = new List<>();
```

```java
// Get the first page of appointments
AppointmentPageInfo pagedAppointmentCol = client.listAppointmentsByPage(itemsPerPage);
pages.addItem(pagedAppointmentCol);

// Loop through subsequent pages
while (!pagedAppointmentCol.getLastPage()) {
    pagedAppointmentCol = client.listAppointmentsByPage(
        itemsPerPage, pagedAppointmentCol.getPageOffset() + 1
    );
    pages.addItem(pagedAppointmentCol);
}
```

```java
} finally {
    if (client != null) 
        ((com.aspose.email.system.IDisposable)client).dispose();
}
```

## Σχετικά tutorials

- [Σελιδοποίηση υποφακέλων Exchange χρησιμοποιώντας Aspose.Email Java: Ένας αποδοτικός οδηγός](/email/java/exchange-server-integration/paginate-exchange-subfolders-aspose-email-java/)
- [Διαχείριση ραντεβού Exchange με Aspose.Email for Java: Ένας ολοκληρωμένος οδηγός](/email/java/exchange-server-integration/aspose-email-java-exchange-appointments-management/)
- [Δημιουργία ημερολογίου Exchange Java με Aspose.Email – Ένας πλήρης οδηγός](/email/java/calendar-appointments/mastering-exchange-calendar-management-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}