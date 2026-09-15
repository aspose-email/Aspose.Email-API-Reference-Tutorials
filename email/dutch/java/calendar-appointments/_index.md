---
date: 2026-09-12
description: Leer hoe u een ics file java kunt genereren met Aspose.Email, een calendar
  event java kunt maken en iCalendar‑afspraken kunt exporteren met volledige codevoorbeelden.
keywords:
- generate ics file java
- create calendar event java
- Aspose.Email Java
- iCalendar generation Java
lastmod: 2026-09-12
og_description: Genereer ics file java met Aspose.Email. Deze tutorial laat zien hoe
  u een calendar event java maakt, recurrence definieert en iCalendar‑bestanden exporteert
  die werken met Outlook, Google Calendar en Apple Calendar.
og_image_alt: 'Aspose.Email Java tutorial: generate ics file and calendar event'
og_title: Genereer ics file java met Aspose.Email – stapsgewijze handleiding
schemas:
- author: Aspose
  dateModified: '2026-09-12'
  description: Learn how to generate ics file java using Aspose.Email, create calendar
    event java, and export iCalendar appointments with full code examples.
  headline: Generate ics file java – email calendar and appointments with Aspose.Email
  type: TechArticle
- description: Learn how to generate ics file java using Aspose.Email, create calendar
    event java, and export iCalendar appointments with full code examples.
  name: Generate ics file java – email calendar and appointments with Aspose.Email
  steps:
  - name: Set up the project and add the Aspose.Email JAR
    text: Create a Maven or Gradle project and include the Aspose.Email dependency.
      This gives you access to the `MailMessage`, `MapiMessage`, and `Appointment`
      classes needed for calendar handling.
  - name: Create a new `Appointment` object
    text: '`Appointment` is Aspose.Email''s core class that represents a calendar
      event and holds all event properties such as subject, location, and attendees.
      Instantiate `Appointment` and fill in the essential fields such as subject,
      location, start/end times, and attendees. This object represents the calend'
  - name: Define recurrence or exceptions (optional)
    text: '`RecurrencePattern` defines how an appointment repeats over time, supporting
      daily, weekly, monthly, and custom patterns. If the meeting repeats, use the
      `RecurrencePattern` class to specify daily, weekly, or custom patterns. You
      can also add exception dates to skip specific occurrences.'
  - name: Save the appointment as an .ics file
    text: Call `appointment.save("MyMeeting.ics", AppointmentSaveFormat.Ics)` to write
      the iCalendar data to disk. The file can now be attached to an email or uploaded
      to a server.
  - name: (optional) Send the invitation via email
    text: '`MailMessage` represents an email message that can contain attachments,
      body, and recipients. `SmtpClient` is the class used to send email messages
      through an SMTP server. Wrap the saved .ics file in a `MailMessage` and use
      `SmtpClient` to deliver it to recipients. This step demonstrates the full wo'
  type: HowTo
- questions:
  - answer: Yes. Aspose.Email creates iCalendar files locally, so no server connection
      is required.
    question: Can I generate an .ics file without an Exchange server?
  - answer: Use `appointment.getReminder().setMinutesBeforeStart(15);` to set a 15‑minute
      reminder.
    question: How do I add a reminder to the event?
  - answer: Absolutely. Call `appointment.getCustomFields().add("X‑MyProperty", "MyValue");`
      to add non‑standard iCal fields.
    question: Is it possible to embed custom properties?
  - answer: Any recent version that supports `AppointmentSaveFormat.Ics`; we tested
      with the latest release.
    question: What version of Aspose.Email is required?
  - answer: Yes. Load the Outlook item with `MapiMessage.fromFile("appointment.msg")`
      and then call `appointment.save(..., AppointmentSaveFormat.Ics)`.
    question: Can I convert existing Outlook appointments to .ics?
  type: FAQPage
tags:
- generate ics
- Aspose.Email
- Java calendar events
- iCalendar
title: Genereer ics file java – e‑mailagenda en afspraken met Aspose.Email
url: /nl/java/calendar-appointments/
weight: 5
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Genereer ics-bestand java – e‑mailkalender en afspraken met Aspose.Email

In deze tutorial ontdek je hoe je **generate ics file java** programma's kunt maken met Aspose.Email. Of je nu een vergaderplanner bouwt, integreert met Microsoft Exchange, of gewoon kalendergegevens moet exporteren, we lopen je stap voor stap door het volledige proces — van het maken van het gebeurtenisobject tot het opslaan van een standaarden‑conform .ics‑bestand. Je ziet ook hoe je **create calendar event java** kunt maken die kan worden verzonden, opgeslagen of geïmporteerd in elke kalenderclient.

## Snelle antwoorden
- **Welke bibliotheek is nodig?** Aspose.Email for Java
- **Kan ik een .ics‑bestand genereren zonder licentie?** Een tijdelijke licentie werkt voor testen; een volledige licentie is vereist voor productie.
- **Welk formaat geeft de API terug?** Standaard iCalendar (.ics)-bestanden compatibel met Outlook, Google Calendar, enz.
- **Heb ik een Exchange‑server nodig?** Nee, de API kan bestanden lokaal genereren zonder verbinding met een server.
- **Wordt herhaling ondersteund?** Ja, je kunt dagelijkse, wekelijkse of aangepaste herhalingspatronen definiëren.

## Wat is “generate ics file java”?
Een .ics‑bestand genereren in Java betekent programmatically een iCalendar‑representatie van een vergadering of afspraak opbouwen, inclusief details zoals onderwerp, locatie, tijd, deelnemers en herinneringen. Het bestand voldoet aan de RFC 5545‑specificatie, waardoor elke kalenderapplicatie — Outlook, Google Calendar, Apple Calendar of andere — het evenement correct kan lezen, weergeven en verwerken.

## Waarom iCalendar‑bestanden genereren met Aspose.Email?
Je moet iCalendar‑bestanden genereren met Aspose.Email omdat de bibliotheek de volledige RFC 5545‑specificatie afhandelt, meer dan **50 kalender‑gerelateerde eigenschappen** ondersteunt en werkt op elk Java‑platform zonder externe afhankelijkheden. Het garandeert dat de .ics‑bestanden correct openen in Outlook, Google Calendar, Apple Calendar en andere clients, terwijl je fijne controle krijgt over deelnemers, herinneringen en herhaling.

## Vereisten
- Java 8 of hoger  
- Aspose.Email for Java (download van de officiële site)  
- Een geldige tijdelijke of volledige licentie voor Aspose.Email  

## Hoe maak je een calendar event java met Aspose.Email?
Laad je Java‑project, instantieer een `Appointment`, configureer de details en sla het op als een .ics‑bestand — allemaal in een paar eenvoudige regels. De `Appointment`‑klasse omvat alle gebeurtenisinformatie zoals onderwerp, locatie, start‑/eindtijden, deelnemers en herhaling. Nadat je de gewenste eigenschappen hebt ingesteld, roep je `save` aan met `AppointmentSaveFormat.Ics` om een standaarden‑conform bestand te produceren dat elke kalenderclient kan importeren.

## Stapsgewijze handleiding

### Stap 1: Het project opzetten en de Aspose.Email‑JAR toevoegen
Maak een Maven‑ of Gradle‑project en voeg de Aspose.Email‑dependency toe. Hiermee krijg je toegang tot de `MailMessage`, `MapiMessage` en `Appointment`‑klassen die nodig zijn voor kalenderverwerking.

### Stap 2: Maak een nieuw `Appointment`‑object
`Appointment` is de kernklasse van Aspose.Email die een kalendergebeurtenis vertegenwoordigt en alle gebeurteniseigenschappen bevat, zoals onderwerp, locatie en deelnemers.  
Instantieer `Appointment` en vul de essentiële velden in, zoals onderwerp, locatie, start‑/eindtijden en deelnemers. Dit object vertegenwoordigt de kalendergebeurtenis die je wilt exporteren.

### Stap 3: Definieer herhaling of uitzonderingen (optioneel)
`RecurrencePattern` definieert hoe een afspraak zich in de tijd herhaalt, met ondersteuning voor dagelijkse, wekelijkse, maandelijkse en aangepaste patronen.  
Als de vergadering zich herhaalt, gebruik dan de `RecurrencePattern`‑klasse om dagelijkse, wekelijkse of aangepaste patronen op te geven. Je kunt ook uitzonderingsdatums toevoegen om specifieke voorkomens over te slaan.

### Stap 4: Sla de afspraak op als een .ics‑bestand
Roep `appointment.save("MyMeeting.ics", AppointmentSaveFormat.Ics)` aan om de iCalendar‑gegevens naar schijf te schrijven. Het bestand kan nu als bijlage aan een e‑mail worden toegevoegd of naar een server worden geüpload.

### Stap 5: (optioneel) Verstuur de uitnodiging via e‑mail
`MailMessage` vertegenwoordigt een e‑mailbericht dat bijlagen, een body en ontvangers kan bevatten. `SmtpClient` is de klasse die wordt gebruikt om e‑mailberichten via een SMTP‑server te verzenden.  
Wikkel het opgeslagen .ics‑bestand in een `MailMessage` en gebruik `SmtpClient` om het naar de ontvangers te leveren. Deze stap toont de volledige workflow van het maken van een gebeurtenis tot distributie.

## Veelvoorkomende problemen en oplossingen
- **Tijdzone‑verschillen** – Zorg ervoor dat de `TimeZoneInfo` van de afspraak overeenkomt met de beoogde zone; anders zien ontvangers mogelijk verkeerde tijden.  
- **Ontbrekende deelnemers** – Voeg elke deelnemer toe met `appointment.getAttendees().add(new MailAddress("user@example.com"));`.  
- **Bestand opent niet in Outlook** – Controleer of de bestandsextensie `.ics` is en of de inhoud voldoet aan RFC 5545 (Aspose.Email handelt dit automatisch af).

## Veelgestelde vragen

**Q: Kan ik een .ics‑bestand genereren zonder Exchange‑server?**  
A: Ja. Aspose.Email maakt iCalendar‑bestanden lokaal, dus er is geen serververbinding nodig.

**Q: Hoe voeg ik een herinnering toe aan het evenement?**  
A: Gebruik `appointment.getReminder().setMinutesBeforeStart(15);` om een herinnering van 15 minuten in te stellen.

**Q: Is het mogelijk om aangepaste eigenschappen in te sluiten?**  
A: Absoluut. Roep `appointment.getCustomFields().add("X‑MyProperty", "MyValue");` aan om niet‑standaard iCal‑velden toe te voegen.

**Q: Welke versie van Aspose.Email is vereist?**  
A: Elke recente versie die `AppointmentSaveFormat.Ics` ondersteunt; we hebben getest met de laatste release.

**Q: Kan ik bestaande Outlook‑afspraken converteren naar .ics?**  
A: Ja. Laad het Outlook‑item met `MapiMessage.fromFile("appointment.msg")` en roep vervolgens `appointment.save(..., AppointmentSaveFormat.Ics)` aan.

## Aanvullende bronnen
- [Maak & Verstuur Kalenderuitnodigingen met Aspose.Email voor Java&#58; Een stapsgewijze gids](./create-send-calendar-invitations-aspose-email-java/)
- [Maak en Sla MAPI‑Kalenders op in Java met Aspose.Email&#58; Een uitgebreide gids](./create-save-mapi-calendar-aspose-email-java/)
- [Hoe Outlook‑kalenderitems te converteren naar ICS met Aspose.Email voor Java](./extract-outlook-calendar-to-ics-aspose-email-java/)
- [Hoe concept‑e‑mailafspraken te maken in Java met Aspose.Email](./create-draft-email-appointment-java-aspose/)
- [Hoe een MAPI‑kalender te maken met dagelijkse herhaling en uitzonderingen met Aspose.Email voor Java](./create-mapi-calendar-daily-recurrence-aspose-email-java/)
- [Hoe Outlook‑notities te maken en aan te passen met Aspose.Email voor Java&#58; Een uitgebreide gids](./create-customize-outlook-notes-aspose-email-java/)
- [Hoe Exchange‑serverafspraken te filteren op datum met Aspose.Email Java](./aspose-email-java-filter-exchange-appointments-by-date/)
- [Hoe gepagineerde afspraken te implementeren in Java met Aspose.Email voor Exchange‑servers](./java-aspose-email-paginated-appointments/)
- [Hoe meerdere ICS‑evenementen te lezen met Aspose.Email in Java&#58; Een uitgebreide gids](./read-multiple-ics-events-aspose-email-java/)
- [Beheer Outlook‑categorieën met Aspose.Email voor Java&#58; Een uitgebreide gids](./manage-outlook-categories-aspose-email-java/)
- [Beheer Outlook‑follow‑up‑vlaggen met Aspose.Email voor Java&#58; Een ontwikkelaarsgids](./aspose-email-java-outlook-follow-up-flags/)
- [Beheer taken efficiënt met Aspose.Email voor Java&#58; Kalender‑ & afspraken‑gids](./aspose-email-java-task-management/)
- [Beheer afspraken meesterlijk met Aspose.Email Java&#58; Een uitgebreide gids voor EWS‑API‑integratie](./master-appointment-management-aspose-email-java/)
- [Beheer Aspose.Email Java&#58; Maak en beheer kalendergebeurtenissen efficiënt](./master-aspose-email-java-calendar-events/)
- [Beheer Aspose.Email Java&#58; Stel deelnemerstatus in & schrijf ICS‑bestanden efficiënt](./aspose-email-java-set-participant-status-write-ics/)
- [Beheer het maken en opslaan van kalenderitems met Aspose.Email voor Java](./create-save-calendar-items-aspose-email-java/)
- [Beheer Exchange‑kalender met Aspose.Email voor Java&#58; Een uitgebreide gids](./mastering-exchange-calendar-management-aspose-email-java/)
- [Beheer Outlook‑sjablonen met Aspose.Email voor Java](./master-outlook-template-management-aspose-email-java/)
- [Aspose.Email for Java Documentation](https://docs.aspose.com/email/java/)
- [Aspose.Email for Java API Reference](https://reference.aspose.com/email/java/)
- [Download Aspose.Email for Java](https://releases.aspose.com/email/java/)
- [Aspose.Email Forum](https://forum.aspose.com/c/email)
- [Free Support](https://forum.aspose.com/)
- [Temporary License](https://purchase.aspose.com/temporary-license/)

---

**Laatst bijgewerkt:** 2026-09-12  
**Getest met:** Aspose.Email for Java (latest release)  
**Auteur:** Aspose

## Gerelateerde tutorials

- [Parse ics file java – Lees kalendergebeurtenissen met Aspose.Email](/email/java/calendar-appointments/read-multiple-ics-events-aspose-email-java/)
- [Hoe ICS te exporteren – Status instellen – Aspose.Email Java](/email/java/calendar-appointments/aspose-email-java-set-participant-status-write-ics/)
- [Hoe een kalenderitem te maken in Java met Aspose.Email](/email/java/calendar-appointments/create-save-calendar-items-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}