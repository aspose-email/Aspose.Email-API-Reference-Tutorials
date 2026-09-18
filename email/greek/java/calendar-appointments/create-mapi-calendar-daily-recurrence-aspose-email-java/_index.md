---
date: '2026-09-17'
description: Μάθετε πώς να δημιουργήσετε Outlook calendar σε Java με καθημερινή επανάληψη
  και εξαιρέσεις, και να αποθηκεύσετε το ημερολόγιο σε αρχείο PST χρησιμοποιώντας
  το Aspose.Email για Java.
keywords:
- create outlook calendar
- outlook calendar daily recurrence
- java calendar exceptions
- Aspose.Email Java
- MAPI PST generation
lastmod: '2026-09-17'
og_description: Δημιουργήστε Outlook calendar σε Java χρησιμοποιώντας το Aspose.Email.
  Μάθετε για την καθημερινή επανάληψη, τη διαχείριση εξαιρέσεων και την αποθήκευση
  σε PST σε έναν οδηγό βήμα‑βήμα.
og_image_alt: Code example creating Outlook calendar with recurrence and PST export
  using Aspose.Email for Java
og_title: Δημιουργία Outlook calendar σε Java με καθημερινή επανάληψη και εξαιρέσεις
schemas:
- author: Aspose
  dateModified: '2026-09-17'
  description: Learn how to create outlook calendar java with daily recurrence and
    exceptions, and save calendar to PST using Aspose.Email for Java.
  headline: Create outlook calendar java with daily recurrence and exceptions
  type: TechArticle
- questions:
  - answer: Yes, you can set the `StartTimeZone` and `EndTimeZone` properties on `MapiCalendar`.
    question: Does the library support time‑zone aware appointments?
  - answer: Use the `DeletedInstanceDates` collection on the recurrence pattern to
      mark specific dates as removed.
    question: Can I programmatically delete a single occurrence from a recurring series?
  - answer: PST files follow the Unicode format limits (up to 2 GB by default), but
      you can configure larger sizes via `PersonalStorage` settings.
    question: Are there limits on the size of a PST file created with Aspose.Email?
  - answer: Create `MapiRecipient` objects, set their `RecipientType` to `MapiRecipientType.MAPI_TO`,
      and add them to the `Recipients` collection of the `MapiMessage`.
    question: How do I add attendees to a meeting request?
  - answer: Yes, Aspose.Email also provides `MapiTask` with similar recurrence capabilities.
    question: Is there support for recurring tasks (not just appointments)?
  type: FAQPage
tags:
- outlook calendar
- Aspose.Email
- Java scheduling
- PST file
title: Δημιουργία Outlook calendar σε Java με καθημερινή επανάληψη και εξαιρέσεις
url: /el/java/calendar-appointments/create-mapi-calendar-daily-recurrence-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Δημιουργία outlook calendar java με ημερήσια επανάληψη και εξαιρέσεις

Η διαχείριση επαναλαμβανόμενων συμβάντων μπορεί να είναι δύσκολη, ειδικά όταν χρειάζεστε ένα **outlook calendar java** που υποστηρίζει ημερήσια πρότυπα επανάληψης και περιστασιακές εξαιρέσεις. Σε αυτό το tutorial θα μάθετε πώς να δημιουργήσετε αντικείμενα Outlook calendar Java, να ρυθμίσετε ημερήσια επανάληψη, να προσθέσετε εξαιρέσεις και τελικά **να αποθηκεύσετε το ημερολόγιο σε PST** χρησιμοποιώντας Aspose.Email for Java. Στο τέλος θα έχετε ένα επαναχρησιμοποιήσιμο απόσπασμα κώδικα που μπορείτε να ενσωματώσετε σε οποιαδήποτε υπηρεσία προγραμματισμού βασισμένη σε Java.

## Γρήγορες απαντήσεις
- **Ποια βιβλιοθήκη;** Aspose.Email for Java  
- **Κύρια εργασία;** Δημιουργία outlook calendar java με ημερήσια επανάληψη και εξαιρέσεις  
- **Απαιτούμενο JDK;** Java 16 ή νεότερο  
- **Μπορώ να επισυνάψω αρχεία σε εξαιρέσεις;** Ναι, χρησιμοποιώντας `MapiCalendarExceptionInfo`  
- **Πού αποθηκεύεται το ημερολόγιο;** Σε αρχείο PST μέσω `PersonalStorage`  

## Τι είναι ένα Outlook calendar java;
Ένα Outlook calendar Java αντικείμενο είναι μια προγραμματιστική αναπαράσταση ενός ραντεβού Outlook, χτισμένη πάνω στην προδιαγραφή MAPI (Messaging Application Programming Interface), η οποία περιλαμβάνει ιδιότητες όπως θέμα, τοποθεσία, ώρες έναρξης/λήξης, κανόνες επανάληψης, συμμετέχοντες και συνημμένα. Αυτό το αντικείμενο μπορεί να τροποποιηθεί, να σειριοποιηθεί και να αποθηκευτεί σε αρχεία PST χωρίς να απαιτείται Outlook.

## Γιατί να χρησιμοποιήσετε Aspose.Email for Java;
Aspose.Email for Java σας επιτρέπει να εργάζεστε με αντικείμενα MAPI χωρίς να εγκαταστήσετε Outlook. Η βιβλιοθήκη υποστηρίζει **50+ ιδιότητες MAPI**, μπορεί να δημιουργήσει αρχεία Unicode PST έως **2 GB** σε λιγότερο από **2 δευτερόλεπτα** για τυπικά δεδομένα ραντεβού, και λειτουργεί σε οποιαδήποτε πλατφόρμα που υποστηρίζει Java 16+. Αυτή η καθαρά‑Java προσέγγιση επιτρέπει τη δημιουργία ημερολογίων από την πλευρά του διακομιστή, αυτοματοποιημένες σειρές συναντήσεων και πλήρη έλεγχο της λογικής επανάληψης.

## Προαπαιτούμενα

Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε την ακόλουθη διαμόρφωση:
- **Aspose.Email Library**: Έκδοση 25.4 (ή νεότερη) – διαθέσιμη μέσω Maven ή άμεσης λήψης.  
- **Java Development Kit (JDK)**: JDK 16 ή νεότερο.  
- **IDE**: IntelliJ IDEA, Eclipse, NetBeans ή οποιονδήποτε επεξεργαστή συμβατό με Java.

### Απαιτούμενες βιβλιοθήκες και εξαρτήσεις

Για να ενσωματώσετε το Aspose.Email στο έργο σας χρησιμοποιώντας Maven, προσθέστε την ακόλουθη εξάρτηση στο `pom.xml` σας:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Απόκτηση άδειας

Για να χρησιμοποιήσετε το Aspose.Email, θα χρειαστείτε άδεια:
- **Δωρεάν δοκιμή** – εξερευνήστε όλες τις δυνατότητες χωρίς κόστος.  
- **Προσωρινή άδεια** – ζητήστε για εκτεταμένη αξιολόγηση.  
- **Πλήρης άδεια** – αγορά για παραγωγικές εγκαταστάσεις.

## Ρύθμιση Aspose.Email για Java

Αρχικά, ρυθμίστε το περιβάλλον σας:

1. Επαληθεύστε ότι το JDK 16 είναι εγκατεστημένο και ότι το `JAVA_HOME` είναι ρυθμισμένο.  
2. Προσθέστε την εξάρτηση Maven (ή κατεβάστε το JAR) στο έργο σας.  

Ακολουθεί ένα μικρό απόσπασμα που δείχνει πώς να φορτώσετε ένα αρχείο άδειας:

```java
import com.aspose.email.*;

public class InitializeAspose {
    public static void main(String[] args) {
        // Set up a license if available
        License license = new License();
        try {
            license.setLicense("path/to/your/license.lic");
        } catch (Exception e) {
            System.out.println("License not found, using trial version.");
        }
    }
}
```

## Οδηγός υλοποίησης

### Δημιουργία outlook calendar java με ημερήσια επανάληψη και εξαιρέσεις

#### Επισκόπηση
Αυτή η δυνατότητα σας επιτρέπει να αυτοματοποιήσετε επαναλαμβανόμενα ραντεβού ενώ μπορείτε να παραλείψετε ή να τροποποιήσετε συγκεκριμένες εμφανίσεις.

#### Βήμα‑βήμα υλοποίηση

**1. Ορισμός ημερομηνίας έναρξης εκδήλωσης**  
Καθορίστε πότε πρέπει να αρχίσει η σειρά:

```java
Date startDate = addHours(newDate(2018, 7, 19), 12);
```

**2. Δημιουργία του αντικειμένου MAPI calendar**  
Η κλάση `MapiCalendar` είναι το αντικείμενο υψηλού επιπέδου που αντιπροσωπεύει ένα μοναδικό στοιχείο ημερολογίου στη μνήμη. Παρέχετε τοποθεσία, θέμα και περιγραφή:

```java
MapiCalendar calendar = new MapiCalendar("location1", "summary1", "description1", startDate, addHours(startDate, 1));
```

**3. Ορισμός προτύπου ημερήσιας επανάληψης**  
Η κλάση `MapiCalendarRecurrencePattern` αποθηκεύει τον κανόνα που επαναλαμβάνει το ραντεβού κάθε μέρα. Διαμορφώστε το συμβάν να επαναλαμβάνεται καθημερινά:

```java
MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
MapiCalendarRecurrencePattern pattern = recurrence.getRecurrencePattern();

pattern.setPatternType(MapiCalendarRecurrencePatternType.Day);
pattern.setPeriod(1); // Daily
pattern.setEndType(MapiCalendarRecurrenceEndType.NeverEnd);
```

**4. Προσθήκη εξαίρεσης στην επανάληψη**  
`MapiCalendarExceptionInfo` περιγράφει μια μεμονωμένη εμφάνιση που αποκλίνει από το πρότυπο — είτε αποκλείεται είτε τροποποιείται. Καθορίστε μια ημερομηνία που πρέπει να αποκλειστεί (ή να τροποποιηθεί):

```java
Date exceptionDate = addDays(startDate, 3);

MapiCalendarExceptionInfo exception = new MapiCalendarExceptionInfo();
exception.setLocation("exceptionLocation");
exception.setSubject("exceptionSubject");
exception.setBody("exceptionBody");

exception.setOriginalStartDate(exceptionDate);
exception.setStartDateTime(exceptionDate);
exception.setEndDateTime(addHours(exceptionDate, 5));

pattern.getExceptions().addItem(exception);
pattern.getModifiedInstanceDates().addItem(exceptionDate);
pattern.getDeletedInstanceDates().addItem(exceptionDate);

calendar.setRecurrence(recurrence);
```

### Επισύναψη αρχείων σε εξαιρέσεις ημερολογίου

#### Επισκόπηση
Μπορείτε να επισυνάψετε υποστηρικτικά έγγραφα (π.χ., ατζέντες) σε οποιαδήποτε εξαίρεση.

**1. Δημιουργία και επισύναψη αρχείου**

```java
MapiCalendarExceptionInfo exception = new MapiCalendarExceptionInfo();
exception.getAttachments().add("file.txt", "hello, world!".getBytes());
```

## Αποθήκευση outlook calendar java σε PST (αποθήκευση ημερολογίου σε pst)

#### Επισκόπηση
Διατηρήστε το ημερολόγιο σε αρχείο PST ώστε το Outlook ή άλλοι πελάτες να μπορούν να το διαβάσουν.

**1. Δημιουργία και αποθήκευση ημερολογίου σε PST**  
Η κλάση `PersonalStorage` παρέχει μεθόδους για δημιουργία νέου αρχείου PST και προσθήκη αντικειμένων MAPI σε αυτό.

```java
final PersonalStorage pst = PersonalStorage.create(new ByteArrayOutputStream(), FileFormatVersion.Unicode);
try {
    FolderInfo calendarFolder = pst.createPredefinedFolder("Calendar", StandardIpmFolder.Appointments);
    calendarFolder.addMapiMessageItem(calendar);
} finally {
    pst.dispose();
}
```

## Πρακτικές εφαρμογές
- **Εταιρικός προγραμματισμός** – αυτοματοποίηση σειρών συναντήσεων, παραλείποντας αυτόματα τις αργίες.  
- **Διαχείριση έργων** – παρακολούθηση επαναλαμβανόμενων ορόσημων με περιστασιακές μετατοπίσεις ημερομηνιών.  
- **Οργάνωση εκδηλώσεων** – διαχείριση πολυήμερων συνεδρίων όπου κάποιες συνεδρίες ακυρώνονται ή μεταπρογραμματίζονται.

### Δυνατότητες ενσωμάτωσης
Συνδυάστε το Aspose.Email με πλατφόρμες CRM, APIs διαχείρισης εργασιών ή προσαρμοσμένες μηχανές ροής εργασίας για πλήρη αυτοματοποίηση από άκρη σε άκρη.

## Παράγοντες απόδοσης
- **Αποδέσμευση πόρων** – πάντα καλέστε `dispose()` στο `PersonalStorage` για απελευθέρωση χειριστών αρχείων.  
- **Χρήση ροής** – προτιμήστε `ByteArrayOutputStream` ή ροές αρχείων για αποφυγή φόρτωσης ολόκληρων PST στη μνήμη.  
- **Ασύγχρονες λειτουργίες** – για μαζική δημιουργία ημερολογίων, εκτελέστε τη λογική δημιουργίας σε παρασκήνιο ώστε η διεπαφή χρήστη να παραμένει ανταποκρινόμενη.

## Συμπέρασμα
Ακολουθώντας αυτόν τον οδηγό, τώρα γνωρίζετε πώς να **δημιουργήσετε outlook calendar java** αντικείμενα με ημερήσια επανάληψη, να προσθέσετε εξαιρέσεις, να επισυνάψετε αρχεία και να **αποθηκεύσετε το ημερολόγιο σε PST**. Αυτές οι δυνατότητες σας επιτρέπουν να δημιουργήσετε ισχυρές λειτουργίες προγραμματισμού χωρίς να χρειάζεται ποτέ να αγγίξετε το Outlook άμεσα.

### Επόμενα βήματα
- Πειραματιστείτε με εβδομαδιαία ή μηνιαία πρότυπα επανάληψης.  
- Εξερευνήστε πρόσθετες ιδιότητες MAPI όπως συμμετέχοντες, υπενθυμίσεις και κατηγορίες.  
- Ανασκοπήστε την εκτενή τεκμηρίωση του Aspose.Email για πιο προχωρημένα σενάρια.

## Συχνές ερωτήσεις

**Ε: Υποστηρίζει η βιβλιοθήκη ραντεβού με προσαρμογή ζώνης ώρας;**  
Α: Ναι, μπορείτε να ορίσετε τις ιδιότητες `StartTimeZone` και `EndTimeZone` στο `MapiCalendar`.

**Ε: Μπορώ προγραμματιστικά να διαγράψω μια μεμονωμένη εμφάνιση από μια επαναλαμβανόμενη σειρά;**  
Α: Χρησιμοποιήστε τη συλλογή `DeletedInstanceDates` στο πρότυπο επανάληψης για να σημειώσετε συγκεκριμένες ημερομηνίες ως αφαιρεμένες.

**Ε: Υπάρχουν όρια στο μέγεθος ενός αρχείου PST που δημιουργείται με Aspose.Email;**  
Α: Τα αρχεία PST ακολουθούν τα όρια μορφής Unicode (μέχρι 2 GB εξ ορισμού), αλλά μπορείτε να ρυθμίσετε μεγαλύτερα μεγέθη μέσω των ρυθμίσεων του `PersonalStorage`.

**Ε: Πώς προσθέτω συμμετέχοντες σε αίτημα συνάντησης;**  
Α: Δημιουργήστε αντικείμενα `MapiRecipient`, ορίστε το `RecipientType` σε `MapiRecipientType.MAPI_TO` και προσθέστε τα στη συλλογή `Recipients` του `MapiMessage`.

**Ε: Υπάρχει υποστήριξη για επαναλαμβανόμενες εργασίες (όχι μόνο ραντεβού);**  
Α: Ναι, το Aspose.Email παρέχει επίσης `MapiTask` με παρόμοιες δυνατότητες επανάληψης.

**Ε: Μπορώ να χρησιμοποιήσω αυτόν τον οδηγό ως μέρος μιας σειράς μαθημάτων Aspose.Email Java;**  
Α: Απόλυτα – τα βήματα που παρουσιάζονται εδώ αποτελούν βασικό μέρος οποιουδήποτε μαθήματος Aspose.Email Java που ασχολείται με τη δημιουργία ημερολογίων.

## Πόροι
- [Τεκμηρίωση Aspose.Email για Java](https://reference.aspose.com/email/java/)
- [Λήψη Aspose.Email](https://releases.aspose.com/email/java/)
- [Αγορά άδειας](https://purchase.aspose.com/buy)
- [Δωρεάν έκδοση δοκιμής](https://releases.aspose.com/email/java/)
- [Αίτηση προσωρινής άδειας](https://purchase.aspose.com/temporary-license/)
- [Φόρουμ υποστήριξης Aspose](https://forum.aspose.com/c/email/10)

---

**Τελευταία ενημέρωση:** 2026-09-17  
**Δοκιμασμένο με:** Aspose.Email for Java 25.4 (JDK 16)  
**Συγγραφέας:** Aspose

## Σχετικά Μαθήματα

- [Εξαγωγή PST ημερολογίου Outlook με Aspose.Email – Java](/email/java/calendar-appointments/create-save-mapi-calendar-aspose-email-java/)
- [Πώς να δημιουργήσετε στοιχείο ημερολογίου Java χρησιμοποιώντας Aspose.Email](/email/java/calendar-appointments/create-save-calendar-items-aspose-email-java/)
- [Δημιουργία πρόσκλησης κοινής χρήσης ημερολογίου με Aspose.Email για Java](/email/java/calendar-appointments/create-send-calendar-invitations-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}