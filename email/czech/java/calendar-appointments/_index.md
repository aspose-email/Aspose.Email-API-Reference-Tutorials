---
date: 2026-09-12
description: Naučte se, jak generovat soubor ics v jazyce Java pomocí Aspose.Email,
  vytvořit událost kalendáře v Java a exportovat iCalendar schůzky s úplnými ukázkami
  kódu.
keywords:
- generate ics file java
- create calendar event java
- Aspose.Email Java
- iCalendar generation Java
lastmod: 2026-09-12
og_description: Generování souboru ics v Java s Aspose.Email. Tento tutoriál vám ukáže,
  jak vytvořit událost kalendáře v Java, definovat opakování a exportovat iCalendar
  soubory, které fungují s Outlook, Google Calendar a Apple Calendar.
og_image_alt: 'Aspose.Email Java tutorial: generate ics file and calendar event'
og_title: Generování souboru ics v Java s Aspose.Email – průvodce krok za krokem
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
title: Generování souboru ics v jazyce Java – e‑mailový kalendář a schůzky s Aspose.Email
url: /cs/java/calendar-appointments/
weight: 5
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generování souboru ics java – e‑mailový kalendář a schůzky s Aspose.Email

V tomto tutoriálu se dozvíte, jak **generovat soubor ics java** pomocí Aspose.Email. Ať už vytváříte plánovač schůzek, integrujete se s Microsoft Exchange, nebo jen potřebujete exportovat kalendářová data, provedeme vás kompletním procesem – od vytvoření objektu události až po uložení standardně kompatibilního .ics souboru. Také uvidíte, jak **vytvořit kalendářovou událost java**, kterou lze odeslat, uložit nebo importovat do libovolného kalendářového klienta.

## Rychlé odpovědi
- **Jaká knihovna je potřeba?** Aspose.Email for Java
- **Mohu vygenerovat soubor .ics bez licence?** Dočasná licence funguje pro testování; pro produkční nasazení je vyžadována plná licence.
- **Jaký formát API vrací?** Standardní iCalendar (.ics) soubory kompatibilní s Outlook, Google Calendar atd.
- **Potřebuji server Exchange?** Ne, API může generovat soubory lokálně bez připojení k serveru.
- **Je podporována opakování?** Ano, můžete definovat denní, týdenní nebo vlastní vzory opakování.

## Co je „generovat soubor ics java“?
Generování .ics souboru v Javě znamená programově vytvořit iCalendar reprezentaci schůzky nebo události, včetně podrobností jako předmět, místo, čas, účastníci a připomenutí. Soubor splňuje specifikaci RFC 5545, což umožňuje jakékoli kalendářové aplikaci – Outlook, Google Calendar, Apple Calendar nebo jiné – přečíst, zobrazit a správně zpracovat událost.

## Proč generovat iCalendar soubory s Aspose.Email?
Měli byste generovat iCalendar soubory s Aspose.Email, protože knihovna zpracovává kompletní specifikaci RFC 5545, podporuje více než **50 kalendářových vlastností** a funguje na jakékoli platformě Java bez externích závislostí. Zaručuje, že .ics soubory se otevřou správně v Outlook, Google Calendar, Apple Calendar a dalších klientech, přičemž vám poskytuje detailní kontrolu nad účastníky, připomenutími a opakováním.

## Požadavky
- Java 8 nebo vyšší  
- Aspose.Email for Java (stáhnout z oficiálního webu)  
- Platná dočasná nebo plná licence pro Aspose.Email  

## Jak vytvořit kalendářovou událost java s Aspose.Email?

Načtěte svůj Java projekt, vytvořte instanci `Appointment`, nastavte její podrobnosti a uložte ji jako .ics soubor – vše během několika jednoduchých řádků. Třída `Appointment` zapouzdřuje všechny informace o události, jako jsou předmět, místo, časy začátku/konce, účastníci a opakování. Po nastavení požadovaných vlastností zavolejte `save` s `AppointmentSaveFormat.Ics` a získáte standardně kompatibilní soubor, který může importovat jakýkoli kalendářový klient.

## Průvodce krok za krokem

### Krok 1: Nastavte projekt a přidejte Aspose.Email JAR
Vytvořte Maven nebo Gradle projekt a zahrňte závislost Aspose.Email. Tím získáte přístup ke třídám `MailMessage`, `MapiMessage` a `Appointment`, které jsou potřebné pro práci s kalendářem.

### Krok 2: Vytvořte nový objekt `Appointment`
`Appointment` je hlavní třída Aspose.Email, která představuje kalendářovou událost a obsahuje všechny její vlastnosti, jako jsou předmět, místo a účastníci.  
Instanciujte `Appointment` a vyplňte základní pole – předmět, místo, časy začátku/konce a účastníky. Tento objekt představuje kalendářovou událost, kterou chcete exportovat.

### Krok 3: Definujte opakování nebo výjimky (volitelné)
`RecurrencePattern` určuje, jak se schůzka opakuje v čase, a podporuje denní, týdenní, měsíční i vlastní vzory.  
Pokud se schůzka opakuje, použijte třídu `RecurrencePattern` k určení denního, týdenního nebo vlastního vzoru. Můžete také přidat data výjimek, aby se vynechaly konkrétní výskyty.

### Krok 4: Uložte schůzku jako .ics soubor
Zavolejte `appointment.save("MyMeeting.ics", AppointmentSaveFormat.Ics)` a zapíšete data iCalendar na disk. Soubor lze nyní připojit k e‑mailu nebo nahrát na server.

### Krok 5: (volitelné) Odeslat pozvánku e‑mailem
`MailMessage` představuje e‑mailovou zprávu, která může obsahovat přílohy, tělo a příjemce. `SmtpClient` je třída používaná k odesílání e‑mailových zpráv přes SMTP server.  
Zabalte uložený .ics soubor do `MailMessage` a použijte `SmtpClient` k doručení příjemcům. Tento krok ukazuje kompletní workflow od vytvoření události po distribuci.

## Časté problémy a řešení
- **Neshody časových pásem** – Ujistěte se, že `TimeZoneInfo` schůzky odpovídá zamýšlenému pásmu; jinak mohou příjemci vidět nesprávné časy.  
- **Chybějící účastníci** – Přidejte každého účastníka pomocí `appointment.getAttendees().add(new MailAddress("user@example.com"));`.  
- **Soubor se neotevírá v Outlooku** – Ověřte, že přípona souboru je `.ics` a že obsah odpovídá RFC 5545 (Aspose.Email to automaticky řeší).  

## Často kladené otázky

**Q: Mohu vygenerovat soubor .ics bez serveru Exchange?**  
A: Ano. Aspose.Email vytváří iCalendar soubory lokálně, takže není vyžadováno žádné připojení k serveru.

**Q: Jak přidám připomenutí k události?**  
A: Použijte `appointment.getReminder().setMinutesBeforeStart(15);` pro nastavení 15‑minutového připomenutí.

**Q: Je možné vložit vlastní vlastnosti?**  
A: Rozhodně. Zavolejte `appointment.getCustomFields().add("X‑MyProperty", "MyValue");` a přidejte nestandardní iCal pole.

**Q: Jaká verze Aspose.Email je vyžadována?**  
A: Jakákoli aktuální verze, která podporuje `AppointmentSaveFormat.Ics`; testovali jsme s nejnovějším vydáním.

**Q: Mohu převést existující Outlook schůzky na .ics?**  
A: Ano. Načtěte Outlook položku pomocí `MapiMessage.fromFile("appointment.msg")` a poté zavolejte `appointment.save(..., AppointmentSaveFormat.Ics)`.

## Další zdroje
- [Vytvoření a odeslání kalendářových pozvánek s Aspose.Email pro Java: Průvodce krok za krokem](./create-send-calendar-invitations-aspose-email-java/)
- [Vytvoření a uložení MAPI kalendářů v Javě s Aspose.Email: Komplexní průvodce](./create-save-mapi-calendar-aspose-email-java/)
- [Jak převést položky kalendáře Outlook na ICS pomocí Aspose.Email pro Java](./extract-outlook-calendar-to-ics-aspose-email-java/)
- [Jak vytvořit koncept e‑mailových schůzek v Javě pomocí Aspose.Email](./create-draft-email-appointment-java-aspose/)
- [Jak vytvořit MAPI kalendář s denním opakováním a výjimkami pomocí Aspose.Email pro Java](./create-mapi-calendar-daily-recurrence-aspose-email-java/)
- [Jak vytvořit a přizpůsobit Outlook poznámky s Aspose.Email pro Java: Komplexní průvodce](./create-customize-outlook-notes-aspose-email-java/)
- [Jak filtrovat schůzky Exchange Serveru podle data pomocí Aspose.Email Java](./aspose-email-java-filter-exchange-appointments-by-date/)
- [Jak implementovat stránkované schůzky v Javě pomocí Aspose.Email pro Exchange servery](./java-aspose-email-paginated-appointments/)
- [Jak číst více ICS událostí pomocí Aspose.Email v Javě: Komplexní průvodce](./read-multiple-ics-events-aspose-email-java/)
- [Správa Outlook kategorií s Aspose.Email pro Java: Komplexní průvodce](./manage-outlook-categories-aspose-email-java/)
- [Správa Outlook Follow‑Up vlajek s Aspose.Email pro Java: Průvodce pro vývojáře](./aspose-email-java-outlook-follow-up-flags/)
- [Efektivní správa úkolů s Aspose.Email pro Java: Kalendář a schůzky](./aspose-email-java-task-management/)
- [Mistrovská správa schůzek s Aspose.Email Java: Komplexní průvodce integrací EWS API](./master-appointment-management-aspose-email-java/)
- [Mistrovská práce s Aspose.Email Java: Vytváření a správa kalendářových událostí efektivně](./master-aspose-email-java-calendar-events/)
- [Mistrovská práce s Aspose.Email Java: Nastavení stavu účastníka a zápis ICS souborů efektivně](./aspose-email-java-set-participant-status-write-ics/)
- [Mistrovské vytváření a ukládání kalendářových položek s Aspose.Email pro Java](./create-save-calendar-items-aspose-email-java/)
- [Mistrovská správa Exchange kalendářů s Aspose.Email pro Java: Komplexní průvodce](./mastering-exchange-calendar-management-aspose-email-java/)
- [Mistrovská správa Outlook šablon pomocí Aspose.Email pro Java](./master-outlook-template-management-aspose-email-java/)
- [Aspose.Email pro Java Dokumentace](https://docs.aspose.com/email/java/)
- [Aspose.Email pro Java API Reference](https://reference.aspose.com/email/java/)
- [Stáhnout Aspose.Email pro Java](https://releases.aspose.com/email/java/)
- [Aspose.Email Fórum](https://forum.aspose.com/c/email)
- [Bezplatná podpora](https://forum.aspose.com/)
- [Dočasná licence](https://purchase.aspose.com/temporary-license/)

---

**Poslední aktualizace:** 2026-09-12  
**Testováno s:** Aspose.Email for Java (nejnovější vydání)  
**Autor:** Aspose

## Související tutoriály

- [Analyzovat soubor ics java – Číst kalendářové události s Aspose.Email](/email/java/calendar-appointments/read-multiple-ics-events-aspose-email-java/)
- [Jak exportovat ICS – Nastavit stav – Aspose.Email Java](/email/java/calendar-appointments/aspose-email-java-set-participant-status-write-ics/)
- [Jak vytvořit kalendářovou položku Java pomocí Aspose.Email](/email/java/calendar-appointments/create-save-calendar-items-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}