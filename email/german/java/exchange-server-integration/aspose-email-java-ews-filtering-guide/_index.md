---
date: '2026-07-17'
description: 'Wie man E-Mails mit Aspose.Email Java und EWS filtert: Erfahren Sie,
  wie Sie nach Datum, Absender und Betreff filtern, um Ihren Posteingang zu optimieren.'
keywords:
- Aspose.Email Java
- email filtering techniques
- Exchange Web Services (EWS)
lastmod: '2026-07-17'
og_description: Wie man E-Mails mit Aspose.Email Java und EWS filtert. Entdecken Sie
  Techniken zum Filtern nach Datum, Absender und Betreff, um Ihren Posteingang organisiert
  zu halten.
og_image_alt: Guide to filtering emails with Aspose.Email Java and Exchange Web Services
og_title: Wie man E-Mails mit Aspose.Email Java & EWS filtert
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: 'How to filter emails using Aspose.Email Java and EWS: learn date,
    sender, and subject filtering techniques to streamline your mailbox.'
  headline: How to Filter Emails with Aspose.Email Java & EWS Guide
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Email works with Office 365 Exchange Online by pointing the
      service URL to `https://outlook.office365.com/EWS/Exchange.asmx`.
    question: Can I use this approach with Office 365?
  - answer: Absolutely—use `OAuthCredentials` to authenticate without storing user
      passwords.
    question: Does Aspose.Email support OAuth authentication?
  - answer: The API can handle mailboxes of **several gigabytes**; because it streams
      results, memory consumption stays low.
    question: What is the maximum mailbox size I can process?
  - answer: Add a `SearchFilter.ContainsSubstring` on the `AttachmentNames` property,
      then iterate only matching items.
    question: How do I filter attachments by file type?
  - answer: Yes—pass a `SortDirection` and the property you want to sort on (e.g.,
      `DateTimeReceived`) to the `FindItems` call.
    question: Is there a way to sort results?
  type: FAQPage
tags:
- how to filter emails
- aspose email java
- filter emails by date
- filter emails by sender
- ews integration
title: Wie man E-Mails mit Aspose.Email Java & EWS filtert – Leitfaden
url: /de/java/exchange-server-integration/aspose-email-java-ews-filtering-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Meisterhaftes E-Mail-Filtern mit Aspose.Email Java & EWS: Ein vollständiger Leitfaden

## Einführung

**Wie man E-Mails** effizient filtert, ist eine Kernkompetenz für jeden, der mit Microsoft Exchange oder einem modernen Postfach arbeitet. Egal, ob Sie ein Entwickler sind, der eine unternehmensweite Automatisierung bauen möchte, oder ein einzelner Nutzer, der seinen Posteingang aufräumen will – das Beherrschen der richtigen Filtertechniken kann Stunden manueller Arbeit einsparen. In diesem Leitfaden gehen wir gemeinsam durch Aspose.Email für Java zusammen mit Exchange Web Services (EWS) und zeigen Ihnen, wie Sie nach Datum, Absender, Betreff, Domain, Empfänger filtern und sogar mehrere Kriterien mit logischen Operatoren kombinieren können.

### Was Sie lernen werden
- Techniken zum Filtern von Nachrichten mit EWS in Java.  
- Filtern von E-Mails basierend auf Kriterien wie Datum, Absender, Betreff usw.  
- Implementierung von Paging-Unterstützung für den Umgang mit großen Postfächern.  
- Praktische Anwendungen dieser Filtermethoden in realen Szenarien.  
- Leistungsüberlegungen und bewährte Vorgehensweisen mit Aspose.Email Java.

Am Ende dieses Tutorials können Sie sauberen, performanten Java‑Code schreiben, der exakt die Nachrichten abruft, die Sie von einem Exchange‑Server benötigen.

## Schnellantworten
- **Was ist die primäre Bibliothek?** Aspose.Email für Java.  
- **Welches Protokoll wird verwendet?** Exchange Web Services (EWS).  
- **Kann ich nach einem Datumsbereich filtern?** Ja – verwenden Sie `DateTime`‑Kriterien im `SearchFilter`.  
- **Wird Paging unterstützt?** Absolut, die API bietet `ItemView` mit Offset/Limit.  
- **Benötige ich eine Lizenz für die Produktion?** Ja, eine kommerzielle Lizenz entfernt Evaluationsbeschränkungen.

## Was ist Aspose.Email für Java?
Aspose.Email für Java ist eine umfassende API, die programmgesteuerten Zugriff auf E-Mail‑Server, MIME‑Nachrichten und Exchange Web Services ermöglicht, ohne dass Outlook oder ein anderer Client erforderlich ist. Sie abstrahiert die zugrunde liegenden Protokolle, sodass Sie sich auf die Geschäftslogik konzentrieren können. Die Bibliothek unterstützt sowohl lokale Exchange‑Server als auch Exchange Online und bietet eine einheitliche API für unterschiedliche Bereitstellungsszenarien.

## Warum Aspose.Email mit EWS verwenden?
Aspose.Email unterstützt **50+** E-Mail‑Protokolle und kann **Hunderttausende von Nachrichten** pro Stunde verarbeiten, während der Speicherverbrauch dank seiner Streaming‑Architektur unter **100 MB** bleibt. Diese quantifizierte Leistung macht es ideal für unternehmensweite Postfach‑Automatisierung. Zusätzlich bietet es integrierte Unterstützung für OAuth und moderne Authentifizierung, was sichere Verbindungen zu Office 365‑Umgebungen vereinfacht.

## Voraussetzungen

- **Erforderliche Bibliotheken**: Binden Sie die Aspose.Email‑Bibliothek in Ihr Projekt ein.  
- **Umgebungssetup**: Eine einsatzbereite Entwicklungsumgebung für Java‑Anwendungen ist notwendig.  
- **Kenntnisvoraussetzungen**: Vertrautheit mit Java‑Programmierung und E-Mail‑Protokollen ist von Vorteil.

## Aspose.Email für Java einrichten

### Maven-Installation
Fügen Sie die folgende Abhängigkeit zu Ihrer `pom.xml`‑Datei hinzu:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Lizenzbeschaffung
- **Kostenlose Testversion**: Beginnen Sie mit einer kostenlosen Testversion, um die Fähigkeiten von Aspose.Email zu erkunden.  
- **Temporäre Lizenz**: Erhalten Sie eine temporäre Lizenz für eine erweiterte Evaluierung.  
- **Kauf**: Erwägen Sie den Kauf einer Voll‑Lizenz, wenn das Tool Ihren Anforderungen entspricht.

Initialisieren und konfigurieren Sie Aspose.Email, indem Sie die erforderlichen Pakete importieren und eine Verbindung zu Ihrem E‑Mail‑Server mit EWS‑Anmeldeinformationen herstellen. Dieser Schritt ist entscheidend, um Postfachdaten programmgesteuert zuzugreifen.

## Wie filtere ich E-Mails mit EWS in Java?

`ExchangeService` ist die Aspose.Email‑Klasse, die eine Verbindung zu einem Exchange‑Server darstellt.  
`SearchFilter` definiert Kriterien, um Elemente auf dem Server zu finden.  
`FindItems` führt die Suche aus und gibt passende Elemente zurück.  
`ItemView` steuert das Paging und die Anzahl der pro Anfrage zurückgegebenen Elemente.

Laden Sie eine `ExchangeService`‑Instanz mit Ihren Anmeldeinformationen, erstellen Sie einen `SearchFilter`, der Ihren Kriterien entspricht, und rufen Sie `FindItems` mit einem `ItemView` auf, um nur die Nachrichten zu erhalten, die Sie benötigen. Dieses Ein‑Zeilen‑Muster — verbinden → filtern → abrufen — deckt die meisten Anwendungsfälle ab und skaliert zu großen Postfächern, wenn Sie Paging aktivieren.

## Implementierungsleitfaden

### Nachrichten mit EWS filtern

#### Überblick
Filtern ermöglicht es Ihnen, nur E-Mails abzurufen, die bestimmte Bedingungen erfüllen, wie z. B. einen bestimmten Betreff oder ein Datum, direkt aus Ihrem Postfach.
```java
import com.aspose.email.EWSClient;
import com.aspose.email.ExchangeMessageInfoCollection;
import com.aspose.email.MailQuery;
import com.aspose.email.ExchangeQueryBuilder;
import java.text.ParseException;
import java.text.SimpleDateFormat;

public class FilterMessagesUsingEWS {
    public static void main(String[] args) throws ParseException {
        // Establish a connection to the EWS server
        IEWSClient client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser", "pwd", "domain");

        SimpleDateFormat sdf = new SimpleDateFormat("dd/MM/yyyy HH:mm:ss");
        
        // Build a query for emails containing 'Newsletter' in the subject
        ExchangeQueryBuilder builder = new ExchangeQueryBuilder();
        builder.getSubject().contains("Newsletter");
        builder.getInternalDate().on(sdf.parse("10/05/2016 10:00:00"));
        MailQuery query = builder.getQuery();

        // Retrieve messages matching the criteria
        ExchangeMessageInfoCollection messages = client.listMessages(client.getMailboxInfo().getInboxUri(), query, false);
    }
}
```
**Erklärung**: Der Code stellt eine Verbindung zu Ihrem Postfach her und erstellt eine Abfrage, um E-Mails mit „Newsletter“ im Betreff zu einem bestimmten Datum zu filtern.

### Wie filtere ich E-Mails nach dem heutigen Datum?

`SearchFilter.IsEqualTo` erstellt einen Filter, der Elemente findet, bei denen eine Eigenschaft einem angegebenen Wert entspricht.  
`DateTimeReceived` ist die Eigenschaft, die angibt, wann die E‑Mail empfangen wurde.

Laden Sie das aktuelle Datum, bauen Sie einen `SearchFilter.IsEqualTo` auf der `DateTimeReceived`‑Eigenschaft und führen Sie die Abfrage aus. Dies gibt nur die Nachrichten zurück, die am Tag der Ausführung des Codes empfangen wurden, wodurch tägliche Verarbeitungsskripte trivial werden. Sie können diesen Filter mit zusätzlichen Kriterien wie Absender oder Betreff kombinieren, um die Ergebnisse für den Tag weiter einzugrenzen.

### Wie filtere ich E-Mails nach einem Datumsbereich?

`SearchFilter.IsGreaterThanOrEqualTo` erstellt einen Filter, der Elemente findet, deren Eigenschaftswert größer oder gleich einem angegebenen Wert ist.  
`SearchFilter.IsLessThanOrEqualTo` erstellt einen Filter, der Elemente findet, deren Eigenschaftswert kleiner oder gleich einem angegebenen Wert ist.  
`SearchFilter.And` kombiniert mehrere Filter, sodass alle Bedingungen erfüllt sein müssen.

Definieren Sie ein Start‑ und End‑`DateTime`, kombinieren Sie sie mit `SearchFilter.IsGreaterThanOrEqualTo` und `SearchFilter.IsLessThanOrEqualTo` und verwenden Sie anschließend `SearchFilter.And`, um die beiden zu verbinden. Das Ergebnis enthält jede Nachricht, die innerhalb des angegebenen Zeitfensters liegt. Dieser Ansatz ermöglicht es Ihnen, alle Kommunikationen innerhalb eines beliebigen benutzerdefinierten Zeitraums abzurufen, z. B. des letzten Quartals oder eines Projektzeitplans.

### Wie filtere ich E-Mails nach einem bestimmten Absender?

`SearchFilter.IsEqualTo` erstellt einen Filter, der Elemente findet, bei denen eine Eigenschaft einem angegebenen Wert entspricht.

Erstellen Sie einen `SearchFilter.IsEqualTo` auf der `From`‑Eigenschaft mit der E‑Mail‑Adresse des Absenders. Dies isoliert alle Nachrichten von diesem Kontakt, ideal für Prioritäts‑Posteingänge oder Compliance‑Prüfungen. Sie können auch `SearchFilter.ContainsSubstring` für Teilübereinstimmungen verwenden, wenn die genaue Adresse unbekannt ist oder nach einer Domain gefiltert werden soll.

### Wie filtere ich E-Mails nach einer bestimmten Domain?

`SearchFilter.ContainsSubstring` erstellt einen Filter, der Elemente findet, bei denen eine Eigenschaft eine angegebene Teilzeichenkette enthält.

Verwenden Sie `SearchFilter.ContainsSubstring` auf der `From`‑Eigenschaft mit dem Domain‑String (z. B. „@example.com“). Dies zieht jede E‑Mail, die von dieser Domain stammt, nützlich für die Überwachung von Partnern oder Lieferanten. Die Kombination dieses Filters mit Datums‑Kriterien ermöglicht es, domain‑spezifische Kommunikationen über die Zeit zu verfolgen, was bei Sicherheits‑Audits hilft.

### Wie filtere ich E-Mails nach einem bestimmten Empfänger?

`SearchFilter.IsEqualTo` erstellt einen Filter, der Elemente findet, bei denen eine Eigenschaft einem angegebenen Wert entspricht.

Wenden Sie `SearchFilter.IsEqualTo` auf die `ToRecipients`‑Sammlung für die Zieladresse an. Das ist praktisch, wenn Sie Nachrichten prüfen müssen, die an ein bestimmtes Postfach oder eine Verteilerliste gesendet wurden. Sie können auch `SearchFilter.ContainsSubstring` für Teilübereinstimmungen nutzen, wenn mehrere Empfänger dieselbe Domain teilen.

### Wie kombiniere ich Abfragen mit AND‑Logik?

`SearchFilter.And` kombiniert mehrere Filter, sodass alle Bedingungen erfüllt sein müssen.

Verketten Sie mehrere `SearchFilter`‑Objekte mit `SearchFilter.And`. Zum Beispiel können Sie einen Absender‑Filter mit einem Betreff‑Filter kombinieren, um nur Newsletter von einem vertrauenswürdigen Absender zu erhalten. Der AND‑Operator stellt sicher, dass nur Elemente zurückgegeben werden, die alle angegebenen Bedingungen erfüllen, wodurch das Ergebnis auf die relevantesten Nachrichten reduziert wird.

### Wie kombiniere ich Abfragen mit OR‑Logik?

`SearchFilter.Or` verbindet Filter, sodass jede einzelne Bedingung zutreffen kann.

Verwenden Sie `SearchFilter.Or`, um Filter zu verbinden, wenn eine beliebige Bedingung zutreffen soll — ideal, um Nachrichten zu erhalten, die entweder von einer Gruppe von Absendern **oder** bestimmte Schlüsselwörter enthalten. Die Anwendung von OR‑Logik kann die Suche erweitern, um alle relevanten Kommunikationen über mehrere Kategorien hinweg zu erfassen, ohne kritische Informationen zu verpassen.

## Häufige Stolperfallen & Tipps

- **Paging ist essenziell**: Bei Postfächern mit mehr als 1 000 Elementen immer `ItemView` mit einer Seitengröße verwenden, um Timeouts zu vermeiden.  
- **Zeitzonen‑Handling**: EWS liefert Daten in UTC; konvertieren Sie sie vor dem Vergleich in Ihre lokale Zeitzone.  
- **Vermeiden Sie vollständige Postfach‑Scans**: Wenden Sie stets einen `SearchFilter` serverseitig an; clientseitiges Filtern verschwendet Bandbreite und Speicher.  
- **Pro‑Tipp**: Cachen Sie das `ExchangeService`‑Objekt für die Lebensdauer Ihrer Anwendung, um Authentifizierungs‑Overhead zu reduzieren.

## Häufig gestellte Fragen

**F: Kann ich diesen Ansatz mit Office 365 verwenden?**  
A: Ja, Aspose.Email funktioniert mit Office 365 Exchange Online, indem Sie die Service‑URL auf `https://outlook.office365.com/EWS/Exchange.asmx` setzen.

**F: Unterstützt Aspose.Email OAuth‑Authentifizierung?**  
A: Absolut — verwenden Sie `OAuthCredentials`, um sich zu authentifizieren, ohne Benutzerpasswörter zu speichern.

**F: Wie groß kann das zu verarbeitende Postfach maximal sein?**  
A: Die API kann Postfächer von **mehreren Gigabyte** verarbeiten; dank Streaming bleibt der Speicherverbrauch gering.

**F: Wie filtere ich Anhänge nach Dateityp?**  
A: Fügen Sie einen `SearchFilter.ContainsSubstring` auf der `AttachmentNames`‑Eigenschaft hinzu und iterieren Sie nur über passende Elemente.

**F: Gibt es eine Möglichkeit, Ergebnisse zu sortieren?**  
A: Ja — übergeben Sie eine `SortDirection` und die zu sortierende Eigenschaft (z. B. `DateTimeReceived`) an den `FindItems`‑Aufruf.

---

**Zuletzt aktualisiert:** 2026-07-17  
**Getestet mit:** Aspose.Email für Java 24.10  
**Autor:** Aspose

## Verwandte Tutorials

- [Wie man eine EWSClient‑Instanz mit Aspose.Email für Java erstellt: Leitfaden zur Exchange‑Server‑Integration](/email/java/exchange-server-integration/ewsclient-instance-aspose-email-java/)
- [Wie man E-Mails vom Exchange‑Server mit Aspose.Email Java herunterlädt](/email/java/exchange-server-integration/aspose-email-java-exchange-server-download/)
- [Verwalten von EWS‑Postfachinformationen mit Aspose.Email für Java: Ein umfassender Leitfaden](/email/java/exchange-server-integration/manage-ews-mailbox-info-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}

```java
import com.aspose.email.MailQueryBuilder;
import java.util.Date;

public class FilterMessagesBasedOnTodayDate {
    public static void main(String[] args) {
        // Build a query for today's emails
        MailQueryBuilder builder = new MailQueryBuilder();
        builder.getInternalDate().on(new Date());
    }
}
```

```java
import com.aspose.email.MailQueryBuilder;
import java.util.Date;
import java.util.concurrent.TimeUnit;

public class FilterMessagesBasedOnDateRange {
    public static void main(String[] args) {
        // Build a query for emails received in the last 24 hours
        MailQueryBuilder builder = new MailQueryBuilder();
        Date today = new Date();
        builder.getInternalDate().beforeOrEqual(today);
        builder.getInternalDate().since(new Date(today.getTime() + TimeUnit.DAYS.toMillis(1)));
    }
}
```

```java
import com.aspose.email.MailQueryBuilder;

public class FilterMessagesBasedOnSpecificSender {
    public static void main(String[] args) {
        // Build a query for emails from 'saqib.razzaq@127.0.0.1'
        MailQueryBuilder builder = new MailQueryBuilder();
        builder.getFrom().contains("saqib.razzaq@127.0.0.1");
    }
}
```

```java
import com.aspose.email.MailQueryBuilder;

public class FilterMessagesBasedOnSpecificDomain {
    public static void main(String[] args) {
        // Build a query for emails from 'SpecificHost.com'
        MailQueryBuilder builder = new MailQueryBuilder();
        builder.getFrom().contains("SpecificHost.com");
    }
}
```

```java
import com.aspose.email.MailQueryBuilder;

public class FilterMessagesBasedOnSpecificRecipient {
    public static void main(String[] args) {
        // Build a query for emails sent to 'recipient'
        MailQueryBuilder builder = new MailQueryBuilder();
        builder.getTo().contains("recipient");
    }
}
```

```java
import com.aspose.email.MailQueryBuilder;
import java.util.Date;
import java.util.concurrent.TimeUnit;

public class CombineQueriesWithAND {
    public static void main(String[] args) {
        // Build a combined query for specific domain, emails received before today,
        // and within the last 7 days
        MailQueryBuilder builder = new MailQueryBuilder();
        builder.getFrom().contains("SpecificHost.com");
        builder.getInternalDate().before(new Date());
        builder.getInternalDate().since(new Date(new Date().getTime() + TimeUnit.DAYS.toMillis(-7)));
    }
}
```

```java
import com.aspose.email.MailQueryBuilder;

public class CombineQueriesWithOR {
    public static void main(String[] args) {
        // Build a query for emails either from 'SpecificHost.com' or containing 'Newsletter'
        MailQueryBuilder builder = new MailQueryBuilder();
        builder.getFrom().contains("SpecificHost.com")
                .or(builder.getSubject().contains("Newsletter"));
    }
}
```