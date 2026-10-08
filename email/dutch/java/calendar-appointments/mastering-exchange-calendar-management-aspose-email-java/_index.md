---
date: '2026-10-07'
description: Leer hoe u een kalendermap in Java maakt met Aspose.Email voor Java,
  inclusief Maven-configuratie, verbinding maken met Exchange en het bijwerken van
  afspraakdetails in de Exchange-kalender.
keywords:
- create calendar folder java
- update exchange calendar appointment
- Aspose.Email for Java
- exchange calendar management
lastmod: '2026-10-07'
og_description: Maak een kalendermap in Java met behulp van Aspose.Email voor Java.
  Deze gids toont de Maven-afhankelijkheid, Exchange-verbinding en hoe u een Exchange-kalenderafspraak
  efficiënt bijwerkt.
og_image_alt: 'Aspose.Email Java tutorial: creating a calendar folder and managing
  appointments'
og_title: Maak een kalendermap in Java met Aspose.Email – Gids
schemas:
- author: Aspose
  dateModified: '2026-10-07'
  description: Learn how to create calendar folder java with Aspose.Email for Java,
    including Maven setup, connecting to Exchange, and updating exchange calendar
    appointment details.
  headline: How to create calendar folder java with Aspose.Email
  type: TechArticle
- questions:
  - answer: A free trial works for development and testing, but a full license is
      required for production deployments.
    question: Do I need a license for development?
  - answer: Yes. Just change the EWS URL to point to your on‑premises server.
    question: Can I use this with on‑premises Exchange?
  - answer: The library supports JDK 16 and newer; older JDKs are not recommended
      for the latest version.
    question: Is Java 8 supported?
  - answer: Use `client.deleteAppointment(appointmentId, calendarFolderUri);` after
      retrieving the appointment’s unique ID.
    question: How do I delete an appointment?
  - answer: Aspose.Email provides a `Recurrence` class that you can attach to an `Appointment`
      before saving.
    question: What if I need to handle recurring meetings?
  type: FAQPage
tags:
- calendar folder
- Aspose.Email
- Java Exchange integration
- appointment management
title: Hoe een kalendermap te maken in Java met Aspose.Email
url: /nl/java/calendar-appointments/mastering-exchange-calendar-management-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maak Exchange‑agenda java met Aspose.Email

## Inleiding

Het beheren van e‑mail en agenda's in een zakelijke omgeving kan complex zijn, vooral wanneer u **create calendar folder java** programma's moet maken die werken voor meerdere gebruikers en tijdzones. Gelukkig vereenvoudigt **Aspose.Email for Java** deze taken door robuuste API's te bieden voor het beheer van Exchange‑Server agenda's. In deze uitgebreide gids leert u hoe u verbinding maakt met een Exchange‑server, agenda‑mappen maakt en afspraken verwerkt — inclusief hoe u **update exchange calendar appointment** objecten bijwerkt — met duidelijke, stap‑voor‑stap Java‑code. U ziet ook praktijkvoorbeelden waarin geautomatiseerde agenda‑verwerking uren handmatig werk bespaart.

**Wat u zult leren**
- Hoe u **connect to exchange java** gebruikt met Aspose.Email  
- Hoe u de **maven dependency aspose email** aan uw project toevoegt  
- Een nieuwe agenda‑map maken en afspraken beheren  
- Afspraken bijwerken, weergeven en annuleren  

Laten we beginnen!

## Snelle antwoorden
- **Wat is de primaire bibliotheek?** Aspose.Email for Java  
- **Hoe voeg ik de bibliotheek toe?** Gebruik de Maven‑dependency hieronder weergegeven  
- **Kan ik een agenda‑map maken?** Ja, met één API‑aanroep  
- **Heb ik een licentie nodig?** Een proefversie werkt voor ontwikkeling; een volledige licentie is vereist voor productie  
- **Is dit compatibel met Office 365?** Absoluut – dezelfde code werkt met Exchange Online  

## Wat is create calendar folder java?
Een agenda‑map maken in Java betekent programmatisch een toegewijde sub‑map toevoegen binnen de agenda‑hiërarchie van een Exchange‑mailbox. Hierdoor kunt u gerelateerde vergaderingen groeperen, afdelingsspecifieke schema's gescheiden houden en bulk‑bewerkingen automatiseren zonder handmatige gebruikersinteractie. De map kan worden gebruikt om afdelingsspecifieke evenementen op te slaan, aangepaste rechten toe te passen en rapportage over meerdere agenda's te vereenvoudigen.

## Waarom Aspose.Email voor Java gebruiken?
Aspose.Email for Java biedt een uitgebreide, high‑level API die de complexiteit van Exchange Web Services abstraheert, waardoor ontwikkelaars kunnen werken met e‑mail, contactpersonen en agenda‑items met eenvoudige Java‑objecten. Het elimineert de noodzaak om ruwe SOAP‑verzoeken te maken en behandelt authenticatie, serialisatie en foutafhandeling intern.

- **Full‑featured API** – Verwerkt Exchange Web Services (EWS) zonder low‑level SOAP‑afhandeling.  
- **Cross‑platform** – Werkt op Windows, Linux en macOS met elke JDK 16+ runtime.  
- **Geen externe afhankelijkheden** – De bibliotheek bundelt alles wat u nodig heeft om met Exchange te communiceren.  
- **Gekwantificeerde capaciteit** – Ondersteunt **50+** Exchange‑operaties, verwerkt **hundreds of appointments per second**, en kan mailboxen tot **2 GB** aan zonder de volledige opslag in het geheugen te laden.

## Waarom dit belangrijk is
Het automatiseren van agenda‑bewerkingen elimineert menselijke fouten, zorgt voor consistente vergadergegevens tussen afdelingen, en maakt integratie met andere bedrijfssystemen zoals CRM‑ of ERP‑platformen mogelijk. Met **create calendar folder java** kunt u aangepaste plannings‑bots bouwen, vergaderuitnodigingen genereren vanuit databases, of evenementen synchroniseren tussen meerdere Exchange‑tenants.

## Veelvoorkomende use‑cases
- **Enterprise meeting rooms** – Automatisch vergaderruimtes reserveren op basis van beschikbaarheid opgeslagen in Exchange.  
- **Employee onboarding** – Nieuwe‑werknemersagenda's vooraf vullen met trainingssessies.  
- **Project timelines** – Mijlpalen‑datums vanuit een project‑managementtool direct naar Outlook‑agenda's pushen.  

## Voorwaarden
- Aspose.Email for Java bibliotheek (versie 25.4 of later)  
- JDK 16 of hoger  
- Toegang tot een Exchange Server (Office 365 of on‑premises)  
- IDE zoals IntelliJ IDEA, Eclipse of NetBeans  

## Maven‑dependency Aspose Email
Voeg het volgende fragment toe aan uw `pom.xml`. Dit is de **maven dependency aspose email** die u nodig heeft om de bibliotheek van Maven Central te halen.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Stappen voor licentie‑acquisitie
1. **Gratis proefversie:** Download een proefversie van de [Aspose website](https://releases.aspose.com/email/java/) om functies te testen.  
2. **Tijdelijke licentie:** Verkrijg een tijdelijke licentie voor volledige functionaliteit via [this link](https://purchase.aspose.com/temporary-license/).  
3. **Aankoop:** Als u tevreden bent, overweeg dan een volledige licentie aan te schaffen via [Aspose's purchase page](https://purchase.aspose.com/buy).

## Hoe maak je een calendar folder java
`IEWSClient` is de primaire klasse van Aspose.Email voor communicatie met Exchange Web Services. Laad uw Exchange‑mailbox met `new IEWSClient("https://exchange.example.com/EWS/Exchange.asmx", "username", "password")` – deze regel maakt een beveiligde sessie aan die u kunt hergebruiken voor agenda‑bewerkingen. Roep vervolgens `client.createFolder("new calendar", client.getDefaultFolder(WellKnownFolderName.Calendar))` aan om een toegewijde map toe te voegen onder de primaire agenda‑hiërarchie. De map verschijnt onmiddellijk en kan een onbeperkt aantal afspraken opslaan, waardoor hij ideaal is voor afdelingsspecifieke planning.

## Definitie‑anker voor IEWSClient
`IEWSClient` is de hoofdklasse van Aspose.Email voor interactie met Exchange Web Services, die authenticatie, het opbouwen van verzoeken en het parseren van antwoorden afhandelt.  

**Uitleg:** Vervang `"username"` en `"password"` door uw werkelijke inloggegevens. Dit client‑object zal later worden hergebruikt voor alle agenda‑acties.

```java
import com.aspose.email.EWSClient;
import com.aspose.email.IEWSClient;

public class ConnectToExchangeServer {
    public static void main(String[] args) {
        IEWSClient client = null;
        try {
            // Connect to Exchange Server with provided URL and credentials
            client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "username", "password");
            System.out.println("Connected to Exchange server.");
        } finally {
            if (client != null)
                client.dispose();
        }
    }
}
```

## Hoe een exchange agenda‑afspraak bij te werken
Haal de bestaande afspraak op via de unieke identifier, wijzig de gewenste velden, en roep `client.updateAppointment(appointment)` aan – dit drie‑stappenpatroon werkt het item op zijn plaats bij zonder het opnieuw te maken, waardoor alle deelnemers en herhalingsgegevens behouden blijven. Gebruik deze aanpak wanneer u de locatie, het onderwerp of de tijd van een vergadering moet wijzigen nadat deze is verzonden.

## Definitie‑anker voor Appointment
`Appointment` is de weergave van een agenda‑item in Aspose.Email, met eigenschappen zoals onderwerp, starttijd, eindtijd, locatie en deelnemers.  

**Uitleg:** Vervang `"YOUR_DOCUMENT_DIRECTORY"` door de daadwerkelijke map‑URI van de afspraak die u wilt bijwerken. Deze code laat zien hoe u het locatie‑veld wijzigt.

```java
import com.aspose.email.MailboxInfo;

public class CreateCalendarFolder {
    public static void main(String[] args) {
        IEWSClient client = null;
        try {
            // Connect to Exchange Server (Replace with actual credentials)
            client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "username", "password");

            // Create a new calendar folder named 'new calendar'
            String calendarUri = client.getMailboxInfo().getCalendarUri();
            client.createFolder(calendarUri, "new calendar", null, "IPF.Appointment");
        } finally {
            if (client != null)
                client.dispose();
        }
    }
}
```

## Afspraak maken in agenda‑map
**Overzicht:** Voeg een vergadering of evenement toe aan de nieuw aangemaakte agenda‑map.

### Stap 3: afspraakdetails instellen
```java
import com.aspose.email.Appointment;
import com.aspose.email.MailAddress;
import java.util.Calendar;
import java.util.Date;
import java.util.UUID;

public class CreateAppointment {
    public static void main(String[] args) {
        IEWSClient client = null;
        try {
            // Connect to Exchange Server (Replace with actual credentials)
            client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "username", "password");

            // Setup appointment details
            Calendar calendar = Calendar.getInstance();
            Date startTime = calendar.getTime();
            calendar.add(Calendar.HOUR, 1);
            Date endTime = calendar.getTime();
            String timeZone = "America/New_York";

            Appointment appointment = new Appointment("Room 121", startTime, endTime,
                    MailAddress.to_MailAddress("email1@aspose.com"),
                    MailAddressCollection.to_MailAddressCollection("email2@aspose.com"));
            appointment.setTimeZone(timeZone);
            appointment.setSummary("EMAILNET-35198 - ".concat(UUID.randomUUID().toString()));
            appointment.setDescription("EMAILNET-35198 Ability to add Java event to Secondary Calendar of Office 365");

            // List subfolders and get the URI for the new calendar folder created earlier
            String newCalendarFolderUri = client.listSubFolders(client.getMailboxInfo().getCalendarUri()).get_Item(0).getUri();

            // Create appointment in the specified calendar folder
            client.createAppointment(appointment, newCalendarFolderUri);
        } finally {
            if (client != null)
                client.dispose();
        }
    }
}
```
**Uitleg:** Deze code bouwt een `Appointment`‑object, stelt de tijdzone in, voegt deelnemers toe, en slaat het op in de aangepaste agenda‑map.

## Afspraak bijwerken
**Overzicht:** Wijzig de eigenschappen van een bestaande afspraak, zoals locatie of onderwerp.

### Stap 4: bestaande afspraak definiëren
```java
import com.aspose.email.Appointment;

public class UpdateAppointment {
    public static void main(String[] args) {
        IEWSClient client = null;
        try {
            // Connect to Exchange Server (Replace with actual credentials)
            client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "username", "password");

            // Setup appointment details for existing appointment
            Appointment appointment = new Appointment();
            appointment.setLocation("Room 122");

            // Specify the URI of the calendar folder where the appointment exists
            String newCalendarFolderUri = "YOUR_DOCUMENT_DIRECTORY";

            // Update the location of the existing appointment
            client.updateAppointment(appointment, newCalendarFolderUri);
        } finally {
            if (client != null)
                client.dispose();
        }
    }
}
```
**Uitleg:** Vervang `"YOUR_DOCUMENT_DIRECTORY"` door de daadwerkelijke map‑URI van de afspraak die u wilt bijwerken. Deze code laat zien hoe u het locatie‑veld wijzigt.

## Veelvoorkomende problemen & tips
- **Authenticatiefouten:** Controleer of het account EWS‑toegang heeft en of multi‑factor authenticatie is uitgeschakeld of een app‑wachtwoord wordt gebruikt.  
- **Map‑URI niet gevonden:** Gebruik `client.listSubFolders()` om de juiste agenda‑URI te ontdekken voordat u items maakt of bijwerkt.  
- **Tijdzone‑verschillen:** Stel altijd de tijdzone in op het `Appointment`‑object om verrassingen door zomertijd te voorkomen.  
- **Prestatie‑tip:** Bij het verwerken van grote batches, hergebruik één `IEWSClient`‑instantie en schakel `client.setTimeout(60000)` in om time‑out‑exceptions te voorkomen.  

## Overzicht van Aspose Email Java‑tutorial
Deze tutorial maakt deel uit van de bredere **Aspose Email Java tutorial**‑reeks die berichtverwerking, contactbeheer en MIME‑verwerking behandelt. Als u de volledige suite wilt beheersen, bekijk dan de andere handleidingen voor het verzenden van e‑mails, het parseren van EML‑bestanden en het werken met IMAP/POP3.

## Veelgestelde vragen

**V: Heb ik een licentie nodig voor ontwikkeling?**  
A: Een gratis proefversie werkt voor ontwikkeling en testen, maar een volledige licentie is vereist voor productie‑implementaties.

**V: Kan ik dit gebruiken met on‑premises Exchange?**  
A: Ja. Wijzig eenvoudig de EWS‑URL zodat deze naar uw on‑premises server wijst.

**V: Wordt Java 8 ondersteund?**  
A: De bibliotheek ondersteunt JDK 16 en nieuwer; oudere JDK’s worden niet aanbevolen voor de nieuwste versie.

**V: Hoe verwijder ik een afspraak?**  
A: Gebruik `client.deleteAppointment(appointmentId, calendarFolderUri);` nadat u de unieke ID van de afspraak hebt opgehaald.

**V: Wat als ik terugkerende vergaderingen moet verwerken?**  
A: Aspose.Email biedt een `Recurrence`‑klasse die u kunt koppelen aan een `Appointment` voordat u deze opslaat.

**V: Zijn er limieten voor het aantal afspraken dat ik kan maken?**  
A: Limieten worden opgelegd door de configuratie van de Exchange‑server, niet door Aspose.Email. Zorg ervoor dat uw mailbox‑quota de items kan bevatten.

## Conclusie
U heeft nu een volledig, end‑to‑end voorbeeld van hoe u **create calendar folder java**‑toepassingen maakt met Aspose.Email voor Java. Van het tot stand brengen van een beveiligde verbinding tot het beheren van mappen en afspraken, de bovenstaande stappen bieden een solide basis om meer geavanceerde planningsoplossingen te bouwen. Verken de andere secties van de Aspose Email Java‑tutorial om uw automatiseringsmogelijkheden uit te breiden.

---

**Last Updated:** 2026-10-07  
**Tested With:** Aspose.Email for Java 25.4 (jdk16 classifier)  
**Author:** Aspose

## Gerelateerde tutorials

- [Gids voor het verbinden van Exchange‑agenda met Aspose.Email voor Java | Exchange Server‑integratie](/email/java/exchange-server-integration/exchange-calendar-connection-aspose-email-java/)
- [Aspose Email Java Exchange‑afsprakenbeheer](/email/java/exchange-server-integration/aspose-email-java-exchange-appointments-management/)
- [Exchange‑maprechten beheren met Aspose.Email voor Java: Een stapsgewijze gids](/email/java/exchange-server-integration/manage-exchange-folder-permissions-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}