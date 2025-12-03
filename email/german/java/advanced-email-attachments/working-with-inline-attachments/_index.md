---
date: 2025-12-01
description: Erfahren Sie, wie Sie E-Mails mit eingebettetem Bild mit Aspose.Email
  für Java senden. Dieser Leitfaden zeigt, wie man Bilder in E-Mails einbettet und
  HTML‑E-Mails in Java mit Inline‑Anhängen erstellt.
language: de
linktitle: Working with Inline Attachments in Aspose.Email
second_title: Aspose.Email Java Email Management API
title: Wie man E-Mails mit eingebettetem Bild mit Aspose.Email für Java sendet
url: /java/advanced-email-attachments/working-with-inline-attachments/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Wie man E-Mails mit eingebettetem Bild mit Aspose.Email für Java sendet

Bilder direkt in eine E‑Mail einzubetten lässt Ihre Nachrichten professionell aussehen und stellt sicher, dass der Empfänger die Grafiken sieht, ohne separate Dateien herunterladen zu müssen. In diesem Tutorial lernen Sie **wie man E‑Mails mit eingebettetem Bild sendet** mit Aspose.Email für Java, wobei alles von der Einrichtung der Bibliothek über das Erstellen einer HTML‑E‑Mail, das Hinzufügen von Inline‑Ressourcen bis hin zum Senden der Nachricht abgedeckt wird.

## Schnelle Antworten
- **Was ist die primäre Klasse für Inline‑Bilder?** `LinkedResource`
- **Welche Methode referenziert das Bild in HTML?** Use `cid:yourContentId` in the `<img>` tag
- **Benötige ich eine Lizenz für die Entwicklung?** Eine kostenlose Testversion funktioniert für Tests; für die Produktion ist eine Lizenz erforderlich
- **Kann ich die E‑Mail über jeden SMTP‑Server senden?** Ja, konfigurieren Sie einfach `SmtpClient` mit Ihren Serverdetails
- **Ist dieser Ansatz mit allen gängigen E‑Mail‑Clients kompatibel?** Die meisten modernen Clients (Outlook, Gmail, Thunderbird) unterstützen CID‑eingebettete Bilder

## Was sind Inline‑Anhänge (eingebettete Bilder)?

Inline‑Anhänge – manchmal auch eingebettete oder CID‑Bilder genannt – sind Dateien, die im MIME‑Body einer E‑Mail leben. Sie werden aus dem HTML‑Teil der Nachricht mit einer **Content‑ID** (CID) referenziert. Diese Technik ermöglicht es Ihnen, **Bilder in E‑Mails einzubetten**, sodass sie genau dort erscheinen, wo Sie das `<img>`‑Tag platzieren, ohne als separate herunterladbare Anhänge zu erscheinen.

## Warum eingebettete Bilder in Ihren Java‑E‑Mails verwenden?

- **Professionelles Aussehen:** Logos, Banner und Produktbilder werden sofort dargestellt.
- **Bessere Interaktion:** Empfänger lesen eher eine E‑Mail, die vollständig aussieht.
- **Keine zusätzlichen Klicks:** Benutzer müssen keinen Anhang herunterladen, um das Bild zu sehen.
- **Konsistentes Branding:** Ihre Marken‑Assets bleiben im Einklang mit dem Nachrichteninhalt.

## Voraussetzungen

- Aspose.Email for Java Bibliothek (Download von der offiziellen [Aspose.Email for Java documentation](https://reference.aspose.com/email/java/))
- Java 8+ Entwicklungsumgebung
- Zugriff auf einen SMTP‑Server zum Senden von E‑Mails
- Bilddatei, die Sie einbetten möchten (z. B. `logo.png`)

## Schritt‑für‑Schritt‑Anleitung

### Schritt 1: Erstellen einer einfachen HTML‑E‑Mail‑Nachricht

Zuerst richten Sie eine einfache `MailMessage` mit einem HTML‑Body ein. Dies wird die Leinwand sein, auf der wir später das Bild einbetten.

```java
// Import necessary classes
import com.aspose.email.MailAddress;
import com.aspose.email.MailMessage;

// Create a new email message
MailMessage message = new MailMessage();
message.setSubject("Hello, World!");
message.setFrom(new MailAddress("sender@example.com"));
message.setTo(new MailAddress("recipient@example.com"));
message.setHtmlBody("<html><body>This is a sample email with inline attachments.</body></html>");
```

### Schritt 2: Hinzufügen eines Inline‑Bildes mit `LinkedResource`

Jetzt betten wir ein Bild ein. Die Klasse `LinkedResource` repräsentiert den Inline‑Anhang. Weisen Sie eine eindeutige **Content‑ID** zu und referenzieren Sie sie im HTML‑Body mit `cid:`.

```java
import com.aspose.email.LinkedResource;

// Create a LinkedResource for the image
LinkedResource linkedResource = new LinkedResource("path/to/your/image.png");
linkedResource.setContentId("image001"); // Unique ID for the inline image

// Add the LinkedResource to the HTML body
message.getLinkedResources().add(linkedResource);

// Reference the inline image in the HTML body
message.setHtmlBody("<html><body>This is an inline image: <img src='cid:image001'></body></html>");
```

> **Pro‑Tipp:** Halten Sie die `ContentId` einfach und eindeutig innerhalb der Nachricht, um Konflikte zu vermeiden.

### Schritt 3: Senden der E‑Mail über `SmtpClient`

Konfigurieren Sie Ihre SMTP‑Einstellungen und senden Sie die Nachricht. Das eingebettete Bild wird zusammen mit der E‑Mail übertragen, sodass der Empfänger es sofort sieht.

```java
import com.aspose.email.SmtpClient;

// Create an instance of SmtpClient
SmtpClient client = new SmtpClient("smtp.example.com", 587, "username", "password");

// Send the email
client.send(message);
```

### Schritt 4: Empfangen und Extrahieren von Inline‑Bildern (optional)

Wenn Sie eingehende Nachrichten verarbeiten müssen, die eingebettete Bilder enthalten, können Sie die `.eml`‑Datei laden und auf deren `LinkedResources` zugreifen.

```java
import com.aspose.email.MailMessage;
import com.aspose.email.LinkedResourceCollection;

// Load the received email message
MailMessage receivedMessage = MailMessage.load("path/to/received_email.eml");

// Access the inline attachments
LinkedResourceCollection inlineAttachments = receivedMessage.getLinkedResources();
```

## Häufige Probleme & deren Behebung

| Issue | Why It Happens | Fix |
|-------|----------------|-----|
| **Content‑ID‑Mismatch** | Der `cid:`‑Verweis im HTML stimmt nicht mit der auf `LinkedResource` gesetzten `ContentId` überein. | Stellen Sie sicher, dass die Zeichenketten identisch sind (`image001` vs `cid:image001`). |
| **Datei nicht gefunden** | Der Pfad zum Bild ist falsch oder die Datei fehlt. | Überprüfen Sie den absoluten/relativen Pfad und dass die Datei auf dem Server existiert. |
| **SMTP‑Authentifizierungsfehler** | Falsche Anmeldedaten oder Servereinstellungen. | Überprüfen Sie Host, Port, Benutzername und Passwort. Aktivieren Sie TLS/SSL falls erforderlich. |
| **Bild wird in einigen Clients nicht angezeigt** | Einige Clients blockieren externe Ressourcen. | Verwenden Sie CID‑eingebettete Bilder (wie gezeigt) anstelle externer URLs. |

## Häufig gestellte Fragen

**Q: Wie lade ich Aspose.Email für Java herunter?**  
A: Sie können Aspose.Email für Java von der [Dokumentation](https://reference.aspose.com/email/java/) herunterladen. Befolgen Sie die Installationsanweisungen, um es in Ihrem Projekt einzurichten.

**Q: Kann ich Aspose.Email für Java mit anderen Java‑Bibliotheken verwenden?**  
A: Ja, Aspose.Email lässt sich nahtlos in andere Java‑Bibliotheken integrieren, sodass Sie die E‑Mail‑Verarbeitung mit PDF‑Erstellung, OCR oder Datenbankzugriff kombinieren können.

**Q: Welche Dateiformate werden für Inline‑Anhänge unterstützt?**  
A: Gängige Bildformate wie PNG, JPEG, GIF sowie andere Dokumenttypen (z. B. SVG) werden als Inline‑Ressourcen unterstützt.

**Q: Wie gehe ich mit Inline‑Anhängen in HTML‑E‑Mails um?**  
A: Verwenden Sie die Klasse `LinkedResource`, um eine `ContentId` zuzuweisen, fügen Sie sie zu `message.getLinkedResources()` hinzu und referenzieren Sie sie im HTML‑Body mit `<img src='cid:yourContentId'>`.

**Q: Ist Aspose.Email für Java mit verschiedenen E‑Mail‑Servern kompatibel?**  
A: Ja, es funktioniert mit jedem SMTP/IMAP/POP3‑Server. Geben Sie einfach die korrekte Serveradresse, den Port und die Authentifizierungsdetails an.

---

**Zuletzt aktualisiert:** 2025-12-01  
**Getestet mit:** Aspose.Email for Java 24.12 (neueste Version zum Zeitpunkt der Erstellung)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}