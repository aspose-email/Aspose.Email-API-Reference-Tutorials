---
"date": "2025-05-29"
"description": "Scopri come creare e gestire contatti MAPI in modo efficiente con Aspose.Email per Java. Questa guida copre tutto, dalla creazione di base dei contatti alla gestione dettagliata, inclusa l'aggiunta di informazioni professionali."
"title": "Creare contatti MAPI in Java utilizzando Aspose.Email&#58; una guida passo passo"
"url": "/it/java/mapi-operations/create-mapi-contacts-aspose-email-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Come creare contatti MAPI in Java utilizzando Aspose.Email: una guida passo passo

## Introduzione

La gestione dei contatti è essenziale per le applicazioni che richiedono una solida integrazione di email e rubrica. Questa guida completa illustra come creare contatti MAPI (Messaging Application Programming Interface) utilizzando la potente libreria Aspose.Email in Java. Seguendo questo tutorial, automatizzerai la creazione dei contatti, migliorerai l'organizzazione dei dati e integrerai perfettamente la gestione dei contatti nelle tue applicazioni Java.

**Cosa imparerai:**
- Crea contatti MAPI di base e dettagliati
- Gestisci informazioni professionali, indirizzi ed e-mail con Aspose.Email per Java
- Imposta un file Personal Storage Table (PST) per archiviare in modo efficiente i contatti

## Prerequisiti

Prima di iniziare a creare i contatti, assicurati di avere quanto segue:

### Librerie richieste:
- Libreria Aspose.Email per Java (versione 25.4 o successiva)

### Requisiti di configurazione dell'ambiente:
- JDK versione 16 o superiore
- Un IDE a tua scelta (IntelliJ IDEA, Eclipse, ecc.)

### Prerequisiti di conoscenza:
Una conoscenza di base della programmazione Java e familiarità con la gestione di librerie di terze parti.

## Impostazione di Aspose.Email per Java

Per iniziare, includi la libreria Aspose.Email nel tuo progetto. Se utilizzi Maven, aggiungi la seguente dipendenza al tuo `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Fasi di acquisizione della licenza:
- **Prova gratuita:** Scarica una versione di prova da [Sito web di Aspose](https://releases.aspose.com/email/java/) per esplorarne le caratteristiche.
- **Licenza temporanea:** Richiedi una licenza temporanea tramite il [pagina di acquisto](https://purchase.aspose.com/temporary-license/).
- **Acquistare:** Considera l'acquisto di una licenza completa da loro [pagina di acquisto](https://purchase.aspose.com/buy) se Aspose.Email soddisfa le tue esigenze.

### Inizializzazione di base:
Una volta installato, inizializza Aspose.Email nella tua applicazione Java per iniziare a creare e gestire i contatti MAPI.

## Guida all'implementazione

Parleremo di tre funzionalità principali: creazione di contatti di base, inclusione di informazioni professionali e gestione completa dei dettagli.

### Creazione di un contatto MAPI di base

#### Panoramica
Questa funzionalità consente di creare contatti semplici contenenti solo nome, cognome e indirizzo e-mail, adatti ad applicazioni che richiedono dati minimi.

#### Fasi di implementazione

##### Passaggio 1: importare le classi richieste
```java
import com.aspose.email.MapiContact;
```

##### Passaggio 2: creare il contatto MAPI
Ecco come creare un contatto MAPI di base:
```java
public static MapiContact createBasicMapiContact(String firstName, String lastName, String emailAddress) {
    return new MapiContact(firstName + " " + lastName, emailAddress);
}
```
**Spiegazione:** Questo metodo inizializza un `MapiContact` oggetto utilizzando il nome e l'indirizzo email forniti. Il contatto viene memorizzato con informazioni minime.

### Creazione di un contatto MAPI con informazioni professionali

#### Panoramica
Arricchisci i tuoi contatti aggiungendo dettagli professionali come il nome dell'azienda, la qualifica professionale e i numeri di telefono.

#### Fasi di implementazione

##### Passaggio 1: importare classi aggiuntive
```java
import com.aspose.email.MapiContactNamePropertySet;
import com.aspose.email.MapiContactProfessionalPropertySet;
import com.aspose.email.MapiContactTelephonePropertySet;
```

##### Passaggio 2: creare il contatto MAPI con i dettagli professionali
Ecco come includere informazioni professionali:
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
**Spiegazione:** Questo metodo inizializza un `MapiContact` Oggetto con dettagli estesi, inclusi nome dell'azienda e qualifica professionale. Imposta anche numeri di telefono aziendali.

### Creazione di un contatto MAPI con informazioni dettagliate

#### Panoramica
Crea contatti completi aggiungendo indirizzi fisici, informazioni e-mail e attributi di genere per una gestione dettagliata.

#### Fasi di implementazione

##### Passaggio 1: importare classi aggiuntive
```java
import com.aspose.email.MapiContactNamePropertySet;
import com.aspose.email.MapiContactProfessionalPropertySet;
import com.aspose.email.MapiContactTelephonePropertySet;
import com.aspose.email.MapiContactElectronicAddress;
import com.aspose.email.MapiContactGender;
```

##### Passaggio 2: creare un contatto MAPI dettagliato
Ecco come creare un contatto dettagliato:
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
**Spiegazione:** Questo metodo inizializza un `MapiContact` Con informazioni dettagliate, inclusi sesso e indirizzo fisico. Garantisce l'acquisizione di tutti i dati rilevanti.

### Creazione di un file PST e aggiunta di contatti

#### Panoramica
Memorizza più contatti in un file PST (Personal Storage Table) per una gestione centralizzata.

#### Fasi di implementazione

##### Passaggio 1: importare le classi richieste
```java
import com.aspose.email.FileFormatVersion;
import com.aspose.email.FolderInfo;
import com.aspose.email.MapiContact;
import com.aspose.email.PersonalStorage;
import com.aspose.email.StandardIpmFolder;
```

##### Passaggio 2: creare PST e aggiungere contatti
Ecco come creare un file PST e aggiungere contatti:
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
**Spiegazione:** Questo metodo crea un file PST e aggiunge più `MapiContact` oggetti al suo interno, organizzandoli in una cartella "Contatti".

## Applicazioni pratiche

1. **Sistemi CRM:** Automatizza la creazione dei contatti nel software di gestione delle relazioni con i clienti.
2. **Client di posta elettronica:** Migliora i client di posta elettronica integrando potenti funzionalità di gestione dei contatti.
3. **Sincronizzazione della rubrica:** Utilizza questa funzionalità per sincronizzare i contatti su diverse piattaforme e dispositivi.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}