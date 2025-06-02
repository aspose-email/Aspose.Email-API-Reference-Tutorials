---
title: "Create MAPI Contacts in Java Using Aspose.Email&#58; A Step-by-Step Guide"
description: "Learn how to create and manage MAPI contacts efficiently with Aspose.Email for Java. This guide covers everything from basic contact creation to detailed management, including adding professional information."
date: "2025-05-29"
weight: 1
url: "/java/mapi-operations/create-mapi-contacts-aspose-email-java/"
keywords:
- Create MAPI Contacts Java
- Aspose.Email for Java
- Manage Contacts in Java

---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}
# How to Create MAPI Contacts in Java Using Aspose.Email: A Step-by-Step Guide

## Introduction

Managing contacts is essential for applications that require robust email and address book integration. This comprehensive guide demonstrates how to create MAPI (Messaging Application Programming Interface) contacts using the powerful Aspose.Email library in Java. By following this tutorial, you'll automate contact creation, enhance data organization, and seamlessly integrate contact management into your Java applications.

**What You'll Learn:**
- Create basic and detailed MAPI contacts
- Manage professional information, addresses, and emails with Aspose.Email for Java
- Set up a Personal Storage Table (PST) file to efficiently store contacts

## Prerequisites

Before diving into contact creation, ensure you have the following:

### Required Libraries:
- Aspose.Email for Java library (Version 25.4 or later)

### Environment Setup Requirements:
- JDK version 16 or higher
- An IDE of your choice (IntelliJ IDEA, Eclipse, etc.)

### Knowledge Prerequisites:
A basic understanding of Java programming and familiarity with handling third-party libraries.

## Setting Up Aspose.Email for Java

To begin, include the Aspose.Email library in your project. If you're using Maven, add the following dependency to your `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### License Acquisition Steps:
- **Free Trial:** Download a trial version from the [Aspose website](https://releases.aspose.com/email/java/) to explore its features.
- **Temporary License:** Apply for a temporary license via the [purchase page](https://purchase.aspose.com/temporary-license/).
- **Purchase:** Consider purchasing a full license from their [buy page](https://purchase.aspose.com/buy) if Aspose.Email meets your needs.

### Basic Initialization:
Once installed, initialize Aspose.Email in your Java application to start creating and managing MAPI contacts.

## Implementation Guide

We'll cover three main features: basic contact creation, professional information inclusion, and comprehensive detail management.

### Creating a Basic MAPI Contact

#### Overview
This feature allows you to create simple contacts with just first name, last name, and email address, suitable for applications requiring minimal data.

#### Implementation Steps

##### Step 1: Import Required Classes
```java
import com.aspose.email.MapiContact;
```

##### Step 2: Create the MAPI Contact
Here's how to create a basic MAPI contact:
```java
public static MapiContact createBasicMapiContact(String firstName, String lastName, String emailAddress) {
    return new MapiContact(firstName + " " + lastName, emailAddress);
}
```
**Explanation:** This method initializes a `MapiContact` object using the provided name and email address. The contact is stored with minimal information.

### Creating a MAPI Contact with Professional Information

#### Overview
Enhance your contacts by adding professional details such as company name, job title, and phone numbers.

#### Implementation Steps

##### Step 1: Import Additional Classes
```java
import com.aspose.email.MapiContactNamePropertySet;
import com.aspose.email.MapiContactProfessionalPropertySet;
import com.aspose.email.MapiContactTelephonePropertySet;
```

##### Step 2: Create the MAPI Contact with Professional Details
Here's how to include professional information:
```java
public static MapiContact createProfessionalMapiContact(String firstName, String middleName, String lastName,
        String company, String jobTitle, String businessPhone, String mobilePhone) {
    MapiContact contact = new MapiContact();
    contact.setNameInfo(new MapiContactNamePropertySet(firstName, middleName, lastName));
    contact.setProfessionalInfo(new MapiContactProfessionalPropertySet(company, jobTitle));
    contact.getTelephones().setBusinessTelephoneNumber(businessPhone);
    contact.getTelephones().setMobileTelephoneNumber(mobilePhone);
    return contact;
}
```
**Explanation:** This method initializes a `MapiContact` object with extended details, including company name and job title. It also sets business-related phone numbers.

### Creating a MAPI Contact with Detailed Information

#### Overview
Create comprehensive contacts by adding physical addresses, email information, and gender attributes for detailed management.

#### Implementation Steps

##### Step 1: Import Additional Classes
```java
import com.aspose.email.MapiContactNamePropertySet;
import com.aspose.email.MapiContactProfessionalPropertySet;
import com.aspose.email.MapiContactTelephonePropertySet;
import com.aspose.email.MapiContactElectronicAddress;
import com.aspose.email.MapiContactGender;
```

##### Step 2: Create a Detailed MAPI Contact
Here's how to create a detailed contact:
```java
public static MapiContact createDetailedMapiContact(String firstName, String middleName, String lastName,
        MapiContactGender gender, String company, String jobTitle, String email, String workAddress) {
    MapiContact contact = new MapiContact();
    contact.setNameInfo(new MapiContactNamePropertySet(firstName, middleName, lastName));
    contact.getPersonalInfo().setGender(gender);
    contact.setProfessionalInfo(new MapiContactProfessionalPropertySet(company, jobTitle));
    contact.getPhysicalAddresses().getWorkAddress().setAddress(workAddress);
    contact.getElectronicAddresses().setEmail1(new MapiContactElectronicAddress(email));
    return contact;
}
```
**Explanation:** This method initializes a `MapiContact` with detailed information, including gender and physical addresses. It ensures all relevant data is captured.

### Creating a PST File and Adding Contacts

#### Overview
Store multiple contacts in a Personal Storage Table (PST) file for centralized management.

#### Implementation Steps

##### Step 1: Import Required Classes
```java
import com.aspose.email.FileFormatVersion;
import com.aspose.email.FolderInfo;
import com.aspose.email.MapiContact;
import com.aspose.email.PersonalStorage;
import com.aspose.email.StandardIpmFolder;
```

##### Step 2: Create PST and Add Contacts
Here's how you can create a PST file and add contacts:
```java
public static void createPstAndAddContacts(MapiContact[] contacts) {
    String pstPath = "YOUR_OUTPUT_DIRECTORY/MapiContactToPST_out.pst";
    PersonalStorage pst = PersonalStorage.create(pstPath, FileFormatVersion.Unicode);
    FolderInfo contactFolder = pst.createPredefinedFolder("Contacts", StandardIpmFolder.Contacts);
    for (MapiContact contact : contacts) {
        contactFolder.addMapiMessageItem(contact);
    }
}
```
**Explanation:** This method creates a PST file and adds multiple `MapiContact` objects into it, organizing them under a "Contacts" folder.

## Practical Applications

1. **CRM Systems:** Automate contact creation in customer relationship management software.
2. **Email Clients:** Enhance email clients by integrating robust contact management features.
3. **Address Book Synchronization:** Use this functionality to synchronize contacts across different platforms and devices.
{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}