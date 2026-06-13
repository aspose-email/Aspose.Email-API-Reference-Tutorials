---
title: "How to Read MSG Files with Aspose.Email for Java"
description: "Learn how to read MSG files and parse MSG attachments using Aspose.Email for Java, extracting delivery/read receipts and vote results efficiently. Includes setup, code, and best practices."
date: "2026-06-13"
weight: 1
url: "/java/email-parsing-analysis/aspose-email-java-msg-receipts-vote-results/"
keywords:
- how to read msg
- parse msg attachments
- Aspose.Email for Java
schemas:
- type: TechArticle
  headline: How to Read MSG Files with Aspose.Email for Java
  description: Learn how to read MSG files and parse MSG attachments using Aspose.Email
    for Java, extracting delivery/read receipts and vote results efficiently. Includes
    setup, code, and best practices.
  dateModified: '2026-06-13'
  author: Aspose
- type: HowTo
  name: How to Read MSG Files with Aspose.Email for Java
  description: Learn how to read MSG files and parse MSG attachments using Aspose.Email
    for Java, extracting delivery/read receipts and vote results efficiently. Includes
    setup, code, and best practices.
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
- type: FAQPage
  questions:
  - question: How do I handle MSG files larger than 500 MB?
    answer: Split the file into smaller segments or use the streaming API to read
      portions without full in‑memory loading.
  - question: Can I store the extracted data directly into a database?
    answer: Yes, map the receipt and vote fields to your DB schema and use JDBC or
      an ORM to persist them.
  - question: Does the library work on Linux environments?
    answer: Absolutely; Aspose.Email for Java is platform‑agnostic and runs on any
      OS with a supported JDK.
  - question: Is there a way to extract attachments while reading receipts?
    answer: Use `MailMessage.getAttachments()` after loading the MSG; the method returns
      a collection of all embedded files.
  - question: What support options are available if I encounter bugs?
    answer: Reach out via the official Aspose Email Forum for community help or open
      a support ticket with a valid license.
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# How to Read MSG Files with Aspose.Email for Java

## Introduction

Reading MSG files programmatically lets you pull valuable tracking data—delivery receipts, read confirmations, and voting results—from Outlook messages. In this guide we’ll show **how to read msg** files using Aspose.Email for Java, walk through the required setup, and demonstrate how to extract receipt and vote information efficiently.

## Quick Answers
- **What library handles MSG parsing?** Aspose.Email for Java.  
- **Can I extract read receipts?** Yes, the API returns delivery and read timestamps.  
- **Is vote data accessible?** Absolutely; you can retrieve each recipient’s voting response.  
- **Do I need a license?** A trial works for testing; a paid license removes evaluation limits.  
- **Which Java version is required?** Java 16 or later is recommended.

## What is Aspose.Email for Java?

Aspose.Email for Java is a standalone Java library that enables creation, manipulation, and conversion of email formats without requiring Microsoft Outlook. It provides a rich object model for MSG, EML, PST, and many other formats, allowing developers to work with email data directly from Java code. (45 words)

## Why use Aspose.Email for Java to read MSG files?

Aspose.Email for Java supports **30+ email formats** and can process MSG files up to **500 MB** without loading the entire file into memory. Its high‑performance parsing engine reduces CPU and memory consumption, making it ideal for large‑scale mail‑archive processing and real‑time analytics scenarios. (48 words)

## Prerequisites

- **Libraries & Dependencies:** Aspose.Email for Java version 25.4 or later and a JDK 16+ runtime.  
- **IDE:** IntelliJ IDEA, Eclipse, or any Java‑compatible IDE with Maven support.  
- **Basic Skills:** Familiarity with Java syntax and object‑oriented concepts.

## License Acquisition

To use Aspose.Email for Java, you need a license:

- **Free Trial:** Start with the free trial version available on [Aspose's website](https://releases.aspose.com/email/java/).  
- **Temporary License:** Request a temporary license from the [purchase page](https://purchase.aspose.com/temporary-license/).  
- **Purchase:** If you’re satisfied with the evaluation, purchase a license for full access to all features via the [Buy Aspose Products](https://purchase.aspose.com/buy) page.  

## How do you extract read and delivery receipt information from an MSG file?

Load the MSG file, iterate through its recipients, and read the `DeliveryTime` and `ReadTime` properties. This approach returns the exact timestamps when each recipient’s mail server delivered the message and when the recipient opened it, giving you precise tracking data for analysis. (53 words)

### Step 1: Load the MSG File
MapiMessage is the Aspose.Email class that represents an Outlook MSG message.  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```  

### Step 2: Iterate Over Recipients
MapiRecipient represents a single recipient (To, CC, or BCC) in the MSG file.  
```java
import com.aspose.email.MapiMessage;
import com.aspose.email.MapiRecipient;
import com.aspose.email.MapiPropertyTag;

public class RetrieveReceipts {
    public static void main(String[] args) {
        String dataDir = "YOUR_DOCUMENT_DIRECTORY/outlook/";
        MapiMessage msg = MapiMessage.fromFile(dataDir + "message.msg");
```  

### Step 3: Retrieve and Print Delivery Time
DeliveryTime is a property of MapiRecipient that holds the timestamp when the message was delivered to the recipient’s server.  
```java
        for (MapiRecipient recipient : msg.getRecipients()) {
            System.out.println("Recipient: " + recipient.getDisplayName());
```  

### Step 4: Retrieve and Print Read Time
ReadTime is a property of MapiRecipient indicating when the recipient opened the message, if that information is available.  
```java
            System.out.println("Delivery time: " + 
                recipient.getProperties().get_Item(MapiPropertyTag.PR_RECIPIENT_TRACKSTATUS_TIME_DELIVERY).getDateTime());
```  

## How do you read vote results from an MSG file?

After loading the message, the API exposes each recipient’s voting response and the time they responded, enabling you to aggregate poll outcomes programmatically. This data can be used to generate summary reports or feed directly into business intelligence dashboards for quick decision‑making. (53 words)

### Step 1: Load the MSG File
MapiMessage is used again to access the voting information embedded in the MSG file.  
```java
            System.out.println("Read time: " + 
                recipient.getProperties().get_Item(MapiPropertyTag.PR_RECIPIENT_TRACKSTATUS_TIME_READ).getDateTime());
        }
    }
}
```  

### Step 2: Iterate Over Recipients
MapiRecipient provides access to each participant’s voting choice and response time.  
```java
import com.aspose.email.MapiMessage;
import com.aspose.email.MapiRecipient;
import com.aspose.email.MapiPropertyTag;

public class ReadVoteResults {
    public static void main(String[] args) {
        String dataDir = "YOUR_DOCUMENT_DIRECTORY/outlook/";
        MapiMessage msg = MapiMessage.fromFile(dataDir + "message.msg");
```  

### Step 3: Retrieve and Print Response
The `VotingResponse` property contains the actual vote (e.g., “Accept”, “Decline”, or custom options).  
```java
        for (MapiRecipient recipient : msg.getRecipients()) {
            System.out.println("Recipient: " + recipient.getDisplayName());
```  

### Step 4: Retrieve and Print Response Time
`VotingResponseTime` records when the recipient submitted their vote, allowing chronological analysis of poll activity.  
```java
            System.out.println("Response: " + 
                recipient.getProperties().get_Item(MapiPropertyTag.PR_RECIPIENT_AUTORESPONSE_PROP_RESPONSE).getString());
```  

## Practical Applications

1. **Email Campaign Tracking:** Measure open rates and delivery success by analyzing receipt timestamps.  
2. **Survey Analysis:** Consolidate voting results from Outlook polls for quick decision‑making.  
3. **Customer Feedback Management:** Pull response data into CRM or analytics platforms for deeper insights.

Integrating these extracts with databases or BI tools amplifies the value of the raw email data.

## Performance Considerations

- Process large MSG files in **chunks** to keep memory usage low.  
- Use **streaming APIs** when dealing with thousands of messages.  
- Store recipient data in lightweight collections such as `ArrayList` or `HashMap` for fast look‑ups.

## Common Issues and Solutions

- **Null timestamps:** A missing `ReadTime` usually means the recipient hasn’t opened the message yet.  
- **Large attachments:** If an MSG contains huge attachments, enable `LoadOptions.setPreserveEmbeddedResources(false)` to skip loading them into memory.  
- **Encoding problems:** Ensure the correct code page is set via `MailMessage.setCharset(Charset.forName("UTF-8"))` when reading non‑ASCII content.

## Frequently Asked Questions

**Q: How do I handle MSG files larger than 500 MB?**  
A: Split the file into smaller segments or use the streaming API to read portions without full in‑memory loading.

**Q: Can I store the extracted data directly into a database?**  
A: Yes, map the receipt and vote fields to your DB schema and use JDBC or an ORM to persist them.

**Q: Does the library work on Linux environments?**  
A: Absolutely; Aspose.Email for Java is platform‑agnostic and runs on any OS with a supported JDK.

**Q: Is there a way to extract attachments while reading receipts?**  
A: Use `MailMessage.getAttachments()` after loading the MSG; the method returns a collection of all embedded files.

**Q: What support options are available if I encounter bugs?**  
A: Reach out via the official Aspose Email Forum for community help or open a support ticket with a valid license.

## Resources
- **Documentation:** [Aspose Email Documentation](https://reference.aspose.com/email/java/)  
- **Documentation (duplicate):** [Aspose Email Documentation](https://reference.aspose.com/email/java/)  
- **Download SDK:** [Aspose Email Downloads](https://releases.aspose.com/email/java/)  
- **Download Section:** [Download Section](https://releases.aspose.com/email/java/)  
- **Purchase License:** [Buy Aspose Products](https://purchase.aspose.com/buy)  
- **Free Trial:** Start with a [Free Trial Version](https://releases.aspose.com/email/java/)  
- **Temporary License:** [Request Temporary License](https://purchase.aspose.com/temporary-license/)  
- **Support Forum:** [Aspose Email Forum](https://forum.aspose.com/c/email/10)  
- **Support Forum (duplicate):** [Aspose Email Forum](https://forum.aspose.com/c/email/10)

---

**Last Updated:** 2026-06-13  
**Tested With:** Aspose.Email for Java 25.4  
**Author:** Aspose

```java
            System.out.println("Response time: " + 
                recipient.getProperties().get_Item(MapiPropertyTag.PR_RECIPIENT_TRACKSTATUS_TIME).getDateTime());
        }
    }
}
```

## Related Tutorials

- [How to Load and Parse Outlook MSG Files Using Aspose.Email for Java: A Comprehensive Guide](/email/java/mapi-operations/outlook-msg-aspose-email-java-guide/)
- [Convert MSG to EML and Manage Attachments with Aspose.Email for Java](/email/java/attachments-handling/aspose-email-java-master-msg-attachments-parsing/)
- [Extract Inline Attachments Java – MSG Files with Aspose.Email](/email/java/attachments-handling/extract-inline-attachments-msg-files-java-aspose-email/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
