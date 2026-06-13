---
date: '2026-06-13'
description: Μάθετε πώς να διαβάζετε αρχεία MSG και να αναλύετε συνημμένα MSG χρησιμοποιώντας
  το Aspose.Email for Java, εξάγοντας αποδείξεις παράδοσης/ανάγνωσης και αποτελέσματα
  ψήφου αποδοτικά. Περιλαμβάνει εγκατάσταση, κώδικα και βέλτιστες πρακτικές.
keywords:
- how to read msg
- parse msg attachments
- Aspose.Email for Java
schemas:
- author: Aspose
  dateModified: '2026-06-13'
  description: Learn how to read MSG files and parse MSG attachments using Aspose.Email
    for Java, extracting delivery/read receipts and vote results efficiently. Includes
    setup, code, and best practices.
  headline: How to Read MSG Files with Aspose.Email for Java
  type: TechArticle
- description: Learn how to read MSG files and parse MSG attachments using Aspose.Email
    for Java, extracting delivery/read receipts and vote results efficiently. Includes
    setup, code, and best practices.
  name: How to Read MSG Files with Aspose.Email for Java
  steps:
  - name: Load the MSG File
    text: MapiMessage is the Aspose.Email class that represents an Outlook MSG message.
  - name: Iterate Over Recipients
    text: MapiRecipient represents a single recipient (To, CC, or BCC) in the MSG
      file.
  - name: Retrieve and Print Delivery Time
    text: DeliveryTime is a property of MapiRecipient that holds the timestamp when
      the message was delivered to the recipient’s server.
  - name: Retrieve and Print Read Time
    text: ReadTime is a property of MapiRecipient indicating when the recipient opened
      the message, if that information is available.
  - name: Load the MSG File
    text: MapiMessage is used again to access the voting information embedded in the
      MSG file.
  - name: Iterate Over Recipients
    text: MapiRecipient provides access to each participant’s voting choice and response
      time.
  - name: Retrieve and Print Response
    text: The `VotingResponse` property contains the actual vote (e.g., “Accept”,
      “Decline”, or custom options).
  - name: Retrieve and Print Response Time
    text: '`VotingResponseTime` records when the recipient submitted their vote, allowing
      chronological analysis of poll activity.'
  type: HowTo
- questions:
  - answer: Split the file into smaller segments or use the streaming API to read
      portions without full in‑memory loading.
    question: How do I handle MSG files larger than 500 MB?
  - answer: Yes, map the receipt and vote fields to your DB schema and use JDBC or
      an ORM to persist them.
    question: Can I store the extracted data directly into a database?
  - answer: Absolutely; Aspose.Email for Java is platform‑agnostic and runs on any
      OS with a supported JDK.
    question: Does the library work on Linux environments?
  - answer: Use `MailMessage.getAttachments()` after loading the MSG; the method returns
      a collection of all embedded files.
    question: Is there a way to extract attachments while reading receipts?
  - answer: Reach out via the official Aspose Email Forum for community help or open
      a support ticket with a valid license.
    question: What support options are available if I encounter bugs?
  type: FAQPage
title: Πώς να διαβάσετε αρχεία MSG με το Aspose.Email for Java
url: /el/java/email-parsing-analysis/aspose-email-java-msg-receipts-vote-results/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Πώς να Διαβάσετε Αρχεία MSG με το Aspose.Email για Java

## Εισαγωγή

Reading MSG files programmatically lets you pull valuable tracking data—delivery receipts, read confirmations, and voting results—from Outlook messages. In this guide we’ll show **how to read msg** files using Aspose.Email for Java, walk through the required setup, and demonstrate how to extract receipt and vote information efficiently.

## Γρήγορες Απαντήσεις
- **Ποια βιβλιοθήκη διαχειρίζεται την ανάλυση MSG;** Aspose.Email for Java.  
- **Μπορώ να εξάγω αποδείξεις ανάγνωσης;** Yes, the API returns delivery and read timestamps.  
- **Είναι προσβάσιμα τα δεδομένα ψήφου;** Absolutely; you can retrieve each recipient’s voting response.  
- **Χρειάζομαι άδεια;** A trial works for testing; a paid license removes evaluation limits.  
- **Ποια έκδοση Java απαιτείται;** Java 16 or later is recommended.

## Τι είναι το Aspose.Email για Java;

Το Aspose.Email για Java είναι μια αυτόνομη βιβλιοθήκη Java που επιτρέπει τη δημιουργία, τη διαχείριση και τη μετατροπή μορφών email χωρίς την ανάγκη του Microsoft Outlook. Παρέχει ένα πλούσιο μοντέλο αντικειμένων για MSG, EML, PST και πολλές άλλες μορφές, επιτρέποντας στους προγραμματιστές να εργάζονται με δεδομένα email απευθείας από κώδικα Java. (45 words)

## Γιατί να χρησιμοποιήσετε το Aspose.Email για Java για την ανάγνωση αρχείων MSG;

Το Aspose.Email για Java υποστηρίζει **30+ μορφές email** και μπορεί να επεξεργαστεί αρχεία MSG έως **500 MB** χωρίς να φορτώνει ολόκληρο το αρχείο στη μνήμη. Η υψηλής απόδοσης μηχανή ανάλυσης μειώνει την κατανάλωση CPU και μνήμης, καθιστώντας το ιδανικό για επεξεργασία μεγάλων αρχείων αλληλογραφίας και σενάρια ανάλυσης σε πραγματικό χρόνο. (48 words)

## Προαπαιτούμενα

- **Βιβλιοθήκες & Εξαρτήσεις:** Aspose.Email for Java version 25.4 or later and a JDK 16+ runtime.  
- **IDE:** IntelliJ IDEA, Eclipse, or any Java‑compatible IDE with Maven support.  
- **Βασικές Δεξιότητες:** Familiarity with Java syntax and object‑oriented concepts.

## Απόκτηση Άδειας

- **Δωρεάν Δοκιμή:** Start with the free trial version available on [Aspose's website](https://releases.aspose.com/email/java/).  
- **Προσωρινή Άδεια:** Request a temporary license from the [purchase page](https://purchase.aspose.com/temporary-license/).  
- **Αγορά:** If you’re satisfied with the evaluation, purchase a license for full access to all features via the [Buy Aspose Products](https://purchase.aspose.com/buy) page.  

## Πώς εξάγετε πληροφορίες αποδείξεων ανάγνωσης και παράδοσης από ένα αρχείο MSG;

Φορτώστε το αρχείο MSG, επαναλάβετε τους παραλήπτες του και διαβάστε τις ιδιότητες `DeliveryTime` και `ReadTime`. Αυτή η προσέγγιση επιστρέφει τις ακριβείς χρονικές σημάνσεις όταν ο διακομιστής αλληλογραφίας κάθε παραλήπτη παρέδωσε το μήνυμα και όταν ο παραλήπτης το άνοιξε, παρέχοντάς σας ακριβή δεδομένα παρακολούθησης για ανάλυση. (53 words)

### Βήμα 1: Φόρτωση του Αρχείου MSG
MapiMessage είναι η κλάση Aspose.Email που αντιπροσωπεύει ένα μήνυμα Outlook MSG.  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```  

### Βήμα 2: Επανάληψη στους Παραλήπτες
MapiRecipient αντιπροσωπεύει έναν μεμονωμένο παραλήπτη (Προς, CC ή BCC) στο αρχείο MSG.  
```java
import com.aspose.email.MapiMessage;
import com.aspose.email.MapiRecipient;
import com.aspose.email.MapiPropertyTag;

public class RetrieveReceipts {
    public static void main(String[] args) {
        String dataDir = "YOUR_DOCUMENT_DIRECTORY/outlook/";
        MapiMessage msg = MapiMessage.fromFile(dataDir + "message.msg");
```  

### Βήμα 3: Ανάκτηση και Εκτύπωση του Χρόνου Παράδοσης
DeliveryTime είναι μια ιδιότητα του MapiRecipient που περιέχει τη χρονική σήμανση όταν το μήνυμα παραδόθηκε στον διακομιστή του παραλήπτη.  
```java
        for (MapiRecipient recipient : msg.getRecipients()) {
            System.out.println("Recipient: " + recipient.getDisplayName());
```  

### Βήμα 4: Ανάκτηση και Εκτύπωση του Χρόνου Ανάγνωσης
ReadTime είναι μια ιδιότητα του MapiRecipient που υποδεικνύει πότε ο παραλήπτης άνοιξε το μήνυμα, εφόσον αυτή η πληροφορία είναι διαθέσιμη.  
```java
            System.out.println("Delivery time: " + 
                recipient.getProperties().get_Item(MapiPropertyTag.PR_RECIPIENT_TRACKSTATUS_TIME_DELIVERY).getDateTime());
```  

## Πώς διαβάζετε τα αποτελέσματα ψήφου από ένα αρχείο MSG;

Μετά τη φόρτωση του μηνύματος, το API αποκαλύπτει την ψήφο κάθε παραλήπτη και τη χρονική στιγμή που απάντησε, επιτρέποντάς σας να συγκεντρώσετε τα αποτελέσματα των δημοσκοπήσεων προγραμματιστικά. Αυτά τα δεδομένα μπορούν να χρησιμοποιηθούν για τη δημιουργία συνοπτικών αναφορών ή να τροφοδοτήσουν άμεσα πίνακες ελέγχου επιχειρηματικής νοημοσύνης για γρήγορη λήψη αποφάσεων. (53 words)

### Βήμα 1: Φόρτωση του Αρχείου MSG
MapiMessage χρησιμοποιείται ξανά για πρόσβαση στις πληροφορίες ψήφου που είναι ενσωματωμένες στο αρχείο MSG.  
```java
            System.out.println("Read time: " + 
                recipient.getProperties().get_Item(MapiPropertyTag.PR_RECIPIENT_TRACKSTATUS_TIME_READ).getDateTime());
        }
    }
}
```  

### Βήμα 2: Επανάληψη στους Παραλήπτες
MapiRecipient παρέχει πρόσβαση στην επιλογή ψήφου και τη χρονική στιγμή απόκρισης κάθε συμμετέχοντα.  
```java
import com.aspose.email.MapiMessage;
import com.aspose.email.MapiRecipient;
import com.aspose.email.MapiPropertyTag;

public class ReadVoteResults {
    public static void main(String[] args) {
        String dataDir = "YOUR_DOCUMENT_DIRECTORY/outlook/";
        MapiMessage msg = MapiMessage.fromFile(dataDir + "message.msg");
```  

### Βήμα 3: Ανάκτηση και Εκτύπωση της Απόκρισης
Η ιδιότητα `VotingResponse` περιέχει την πραγματική ψήφο (π.χ., “Accept”, “Decline”, ή προσαρμοσμένες επιλογές).  
```java
        for (MapiRecipient recipient : msg.getRecipients()) {
            System.out.println("Recipient: " + recipient.getDisplayName());
```  

### Βήμα 4: Ανάκτηση και Εκτύπωση του Χρόνου Απόκρισης
`VotingResponseTime` καταγράφει πότε ο παραλήπτης υπέβαλε την ψήφο του, επιτρέποντας χρονολογική ανάλυση της δραστηριότητας της δημοσκόπησης.  
```java
            System.out.println("Response: " + 
                recipient.getProperties().get_Item(MapiPropertyTag.PR_RECIPIENT_AUTORESPONSE_PROP_RESPONSE).getString());
```  

## Πρακτικές Εφαρμογές

1. **Παρακολούθηση Εκστρατειών Email:** Measure open rates and delivery success by analyzing receipt timestamps.  
2. **Ανάλυση Ερευνών:** Consolidate voting results from Outlook polls for quick decision‑making.  
3. **Διαχείριση Ανατροφοδότησης Πελατών:** Pull response data into CRM or analytics platforms for deeper insights.

Η ενσωμάτωση αυτών των εξαγωγών με βάσεις δεδομένων ή εργαλεία BI ενισχύει την αξία των ακατέργαστων δεδομένων email.

## Παρατηρήσεις Απόδοσης

- Process large MSG files in **chunks** to keep memory usage low.  
- Use **streaming APIs** when dealing with thousands of messages.  
- Store recipient data in lightweight collections such as `ArrayList` or `HashMap` for fast look‑ups.

## Κοινά Προβλήματα και Λύσεις

- **Null timestamps:** A missing `ReadTime` usually means the recipient hasn’t opened the message yet.  
- **Μεγάλα συνημμένα:** If an MSG contains huge attachments, enable `LoadOptions.setPreserveEmbeddedResources(false)` to skip loading them into memory.  
- **Προβλήματα κωδικοποίησης:** Ensure the correct code page is set via `MailMessage.setCharset(Charset.forName("UTF-8"))` when reading non‑ASCII content.

## Συχνές Ερωτήσεις

**Q: Πώς διαχειρίζομαι αρχεία MSG μεγαλύτερα από 500 MB;**  
A: Split the file into smaller segments or use the streaming API to read portions without full in‑memory loading.

**Q: Μπορώ να αποθηκεύσω τα εξαγόμενα δεδομένα απευθείας σε μια βάση δεδομένων;**  
A: Yes, map the receipt and vote fields to your DB schema and use JDBC or an ORM to persist them.

**Q: Λειτουργεί η βιβλιοθήκη σε περιβάλλοντα Linux;**  
A: Absolutely; Aspose.Email for Java is platform‑agnostic and runs on any OS with a supported JDK.

**Q: Υπάρχει τρόπος να εξάγω συνημμένα ενώ διαβάζω αποδείξεις;**  
A: Use `MailMessage.getAttachments()` after loading the MSG; the method returns a collection of all embedded files.

**Q: Ποιες επιλογές υποστήριξης είναι διαθέσιμες αν αντιμετωπίσω σφάλματα;**  
A: Reach out via the official Aspose Email Forum for community help or open a support ticket with a valid license.

## Πόροι
- **Τεκμηρίωση:** [Aspose Email Documentation](https://reference.aspose.com/email/java/)  
- **Τεκμηρίωση (duplicate):** [Aspose Email Documentation](https://reference.aspose.com/email/java/)  
- **Λήψη SDK:** [Aspose Email Downloads](https://releases.aspose.com/email/java/)  
- **Λήψη Section:** [Download Section](https://releases.aspose.com/email/java/)  
- **Αγορά Άδειας:** [Buy Aspose Products](https://purchase.aspose.com/buy)  
- **Δωρεάν Δοκιμή:** Ξεκινήστε με μια [Free Trial Version](https://releases.aspose.com/email/java/)  
- **Προσωρινή Άδεια:** [Request Temporary License](https://purchase.aspose.com/temporary-license/)  
- **Φόρουμ Υποστήριξης:** [Aspose Email Forum](https://forum.aspose.com/c/email/10)  
- **Φόρουμ Υποστήριξης (duplicate):** [Aspose Email Forum](https://forum.aspose.com/c/email/10)

---

**Τελευταία Ενημέρωση:** 2026-06-13  
**Δοκιμάστηκε Με:** Aspose.Email for Java 25.4  
**Συγγραφέας:** Aspose

```java
            System.out.println("Response time: " + 
                recipient.getProperties().get_Item(MapiPropertyTag.PR_RECIPIENT_TRACKSTATUS_TIME).getDateTime());
        }
    }
}
```

## Σχετικά Μαθήματα

- [Πώς να Φορτώσετε και να Αναλύσετε Αρχεία Outlook MSG Χρησιμοποιώντας το Aspose.Email για Java: Ένας Πλήρης Οδηγός](/email/java/mapi-operations/outlook-msg-aspose-email-java-guide/)
- [Μετατροπή MSG σε EML και Διαχείριση Συνημμένων με το Aspose.Email για Java](/email/java/attachments-handling/aspose-email-java-master-msg-attachments-parsing/)
- [Εξαγωγή Ενσωματωμένων Συνημμένων Java – Αρχεία MSG με το Aspose.Email](/email/java/attachments-handling/extract-inline-attachments-msg-files-java-aspose-email/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}