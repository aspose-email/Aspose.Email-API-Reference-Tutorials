---
"date": "2025-05-29"
"description": "Erfahren Sie, wie Sie mit der AMP-Technologie von Aspose.Email für .NET interaktive und ansprechende E-Mails erstellen. Optimieren Sie Ihre E-Mail-Marketingstrategie mit dynamischen Inhalten wie Animationen, Karussells und Formularen."
"title": "Erstellen Sie interaktive E-Mails mit Aspose.Email .NET AMP – Ein umfassender Leitfaden"
"url": "/de/net/message-formatting-customization/create-interactive-emails-aspose-email-net-amp/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Erstellen Sie interaktive E-Mails mit Aspose.Email .NET AMP: Ein umfassender Leitfaden

## Einführung

Möchten Sie Ihre E-Mail-Marketingstrategie durch interaktive und ansprechende E-Mails verbessern? Herkömmliche HTML-E-Mails bieten oft nicht genügend Interaktivität. Accelerated Mobile Pages (AMP) für E-Mails bieten jedoch eine überzeugende Lösung. Durch die Integration von Aspose.Email für .NET in Ihren Workflow können Sie AMP-E-Mails erstellen, die Ihre Zielgruppe mit dynamischen Inhalten wie Animationen, Bildern, Karussells und Formularen fesseln.

In diesem Tutorial führen wir Sie durch den Prozess der Erstellung verschiedener Komponenten in AMP-E-Mails mit Aspose.Email für .NET. Egal, ob Sie ein erfahrener Entwickler sind oder gerade erst anfangen, Sie erhalten wertvolle Einblicke in die Gestaltung überzeugender E-Mail-Erlebnisse.

**Was Sie lernen werden:**
- So erstellen Sie grundlegende AMP-E-Mail-Strukturen
- Hinzufügen interaktiver Elemente wie Animationen und Bilder
- Implementierung von Karussells, passendem Text, Akkordeons, Formularen und Zeitkomponenten
- Optimieren Sie Ihre E-Mails für eine bessere Leistung

Bereit zum Einstieg? Lassen Sie uns zunächst die Voraussetzungen klären, bevor wir mit der Erstellung dynamischer E-Mails beginnen.

## Voraussetzungen

Bevor Sie mit dem Erstellen von AMP-E-Mails mit Aspose.Email für .NET beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:
- **Aspose.Email für .NET-Bibliothek:** Sie benötigen diese Bibliothek, die über verschiedene Paketmanager installiert werden kann.
- **Entwicklungsumgebung:** Eine geeignete IDE wie Visual Studio wird empfohlen.
- **Grundkenntnisse in C# und E-Mail-Protokollen:** Kenntnisse in der Programmierung in C# und im Verständnis von E-Mail-Formaten sind von Vorteil.

## Einrichten von Aspose.Email für .NET

Um Aspose.Email für .NET verwenden zu können, müssen Sie die Bibliothek installieren. Sie können dies mit einer der folgenden Methoden tun:

**.NET-CLI**
```bash
dotnet add package Aspose.Email
```

**Paket-Manager-Konsole**
```powershell
Install-Package Aspose.Email
```

**NuGet-Paket-Manager-Benutzeroberfläche**
Suchen Sie nach „Aspose.Email“ und installieren Sie die neueste Version direkt von Ihrer IDE.

### Lizenzerwerb

Um Aspose.Email auszuprobieren, können Sie eine [kostenlose Testversion](https://releases.aspose.com/email/net/) oder erwerben Sie eine temporäre Lizenz. Wenn Sie es nützlich finden, können Sie eine Volllizenz erwerben, um alle Funktionen freizuschalten.

**Grundlegende Initialisierung**
Initialisieren Sie die Bibliothek nach der Installation in Ihrem Projekt:
```csharp
using Aspose.Email;

// Grundlegender Setup-Code zum Initialisieren von Aspose.Email
```

## Implementierungshandbuch

### Erstellen Sie eine AMP-E-Mail mit Grundstruktur

#### Überblick
Die Erstellung einer Grundstruktur ist die Grundlage jeder AMP-E-Mail. Dieser Abschnitt zeigt, wie Sie einen ersten HTML-Text erstellen.

**1. AmpMessage initialisieren**
Beginnen Sie mit der Erstellung einer Instanz von `AmpMessage`.
```csharp
using Aspose.Email.Amp;

string dataDir = "YOUR_DOCUMENT_DIRECTORY";
AmpMessage msg = new AmpMessage();
```

**2. Legen Sie den HTML-Text fest**
Weisen Sie einen einfachen HTML-Inhalt zu `HtmlBody`.
```csharp
msg.HtmlBody = "<html><body> Hello AMP </body></html>";
msg.Save(dataDir + "BasicAmpEmail.eml");
```

#### Schlüsselkonfiguration
Stellen Sie sicher, dass Ihr Verzeichnispfad richtig eingerichtet ist, um Dateien erfolgreich zu speichern.

### AMP-Animationskomponente hinzufügen

#### Überblick
Verbessern Sie Ihre E-Mail mit einer Animationskomponente für mehr Engagement.

**1. AmpMessage einrichten**
Initialisieren Sie den `AmpMessage` und definieren Sie grundlegende HTML-Inhalte.
```csharp
using Aspose.Email.Amp;

string dataDir = "YOUR_DOCUMENT_DIRECTORY";
AmpMessage msgWithAnim = new AmpMessage();
msgWithAnim.HtmlBody = "<html><body> Hello AMP with Animation </body></html>";
```

**2. AmpAnim erstellen und hinzufügen**
Konfigurieren Sie die `AmpAnim` Komponente.
```csharp
// AmpAnim-Komponente hinzufügen
AmpAnim anim = new AmpAnim(800, 400);
anim.Src = "https://placekitten.com/800/400";
anim.Alt = "Test alt";
anim.Attribution = "The Go gopher was designed by Reneee French";
anim.Attributes.Layout = LayoutType.Responsive;
anim.Fallback = "offline";

msgWithAnim.AddAmpComponent(anim);
msgWithAnim.Save(dataDir + "AmpEmailWithAnim.eml");
```

#### Fehlerbehebung
- Stellen Sie sicher, dass die Bild-URL zugänglich ist und die Reaktionsattribute richtig eingestellt sind.

### AMP-Bildkomponente hinzufügen

#### Überblick
Integrieren Sie Bilder, um Ihre E-Mails optisch ansprechend zu gestalten.

**1. AmpMessage initialisieren**
Einrichten eines neuen `AmpMessage`.
```csharp
using Aspose.Email.Amp;

string dataDir = "YOUR_DOCUMENT_DIRECTORY";
AmpMessage msgWithImage = new AmpMessage();
msgWithImage.HtmlBody = "<html><body> Hello AMP with Image </body></html>";
```

**2. AmpImage hinzufügen**
Konfigurieren und hinzufügen eines `AmpImage`.
```csharp
// AmpImage-Komponente hinzufügen
AmpImage img = new AmpImage(800, 400);
img.Src = "https://placekitten.com/800/400";
img.Alt = "Test alt";
img.Attributes.Layout = LayoutType.Responsive;

msgWithImage.AddAmpComponent(img);
msgWithImage.Save(dataDir + "AmpEmailWithImage.eml");
```

### AMP-Karussellkomponente hinzufügen

#### Überblick
Erstellen Sie ein Karussell, um mehrere Bilder in einer einzigen E-Mail anzuzeigen.

**1. AmpMessage einrichten**
Initialisieren `AmpMessage` mit einfachem HTML-Inhalt.
```csharp
using Aspose.Email.Amp;

string dataDir = "YOUR_DOCUMENT_DIRECTORY";
AmpMessage msgWithCarousel = new AmpMessage();
msgWithCarousel.HtmlBody = "<html><body> Hello AMP with Carousel </body></html>";
```

**2. AmpCarousel konfigurieren und hinzufügen**
Fügen Sie dem Karussell Bilder hinzu.
```csharp
// AmpCarousel-Komponente hinzufügen
AmpCarousel car = new AmpCarousel(800, 400);

AmpImage carouselImg1 = new AmpImage(800, 400) { Src = "https://amp.dev/static/img/docs/tutorials/firstemail/photo_by_caleb_woods.jpg", Alt = "Test 2 alt", Attribute = { Layout = LayoutType.Fixed } };
car.Images.Add(carouselImg1);

AmpImage carouselImg2 = new AmpImage(800, 400) { Src = "https://placekitten.com/800/400", Alt = "Test alt", Attribute = { Layout = LayoutType.Responsive } };
car.Images.Add(carouselImg2);

AmpImage carouselImg3 = new AmpImage(800, 400) { Src = "https://amp.dev/static/img/docs/tutorials/firstemail/photo_by_craig_mclaclan.jpg", Alt = "Test 3 alt", Attribute = { Layout = LayoutType.Fill } };
car.Images.Add(carouselImg3);

msgWithCarousel.AddAmpComponent(car);
msgWithCarousel.Save(dataDir + "AmpEmailWithCarousel.eml");
```

### AMP FitText-Komponente hinzufügen

#### Überblick
Verwenden Sie die Komponente „Text anpassen“, um die Textgröße dynamisch anzupassen.

**1. AmpMessage initialisieren**
Beginnen Sie mit einem neuen `AmpMessage`.
```csharp
using Aspose.Email.Amp;

string dataDir = "YOUR_DOCUMENT_DIRECTORY";
AmpMessage msgWithFitText = new AmpMessage();
msgWithFitText.HtmlBody = "<html><body> Hello AMP with Fit Text </body></html>";
```

**2. AmpFitText hinzufügen**
Konfigurieren und hinzufügen eines `AmpFitText` Komponente.
```csharp
// AmpFitText-Komponente hinzufügen
AmpFitText fitText = new AmpFitText(800, 400);
fitText.Text = "This is a dynamic text that fits the container.";
fitText.Attributes.Layout = LayoutType.Responsive;

msgWithFitText.AddAmpComponent(fitText);
msgWithFitText.Save(dataDir + "AmpEmailWithFitText.eml");
```

### AMP-Akkordeonkomponente hinzufügen

#### Überblick
Integrieren Sie ein Akkordeon, mit dem Benutzer Inhaltsabschnitte erweitern und reduzieren können.

**1. AmpMessage initialisieren**
Einrichten eines neuen `AmpMessage`.
```csharp
using Aspose.Email.Amp;

string dataDir = "YOUR_DOCUMENT_DIRECTORY";
AmpMessage msgWithAccordion = new AmpMessage();
msgWithAccordion.HtmlBody = "<html><body> Hello AMP with Accordion </body></html>";
```

**2. AmpAccordion hinzufügen**
Konfigurieren und hinzufügen eines `AmpAccordion` Komponente.
```csharp
// AmpAccordion-Komponente hinzufügen
AmpAccordion accordion = new AmpAccordion();
accordion.AddSection("Introduction", "This is the introduction section.");
accordion.AddSection("Details", "Here are more details.");
accordion.AddSection("Conclusion", "This is the conclusion.");

msgWithAccordion.AddAmpComponent(accordion);
msgWithAccordion.Save(dataDir + "AmpEmailWithAccordion.eml");
```

### AMP-Formularkomponente hinzufügen

#### Überblick
Erweitern Sie Ihre E-Mail mit einem Formular, um Benutzerantworten direkt in der E-Mail zu sammeln.

**1. AmpMessage initialisieren**
Erstellen Sie ein neues `AmpMessage` Beispiel.
```csharp
using Aspose.Email.Amp;

string dataDir = "YOUR_DOCUMENT_DIRECTORY";
AmpMessage msgWithForm = new AmpMessage();
msgWithForm.HtmlBody = "<html><body> Hello AMP with Form </body></html>";
```

**2. AmpForm hinzufügen**
Konfigurieren und hinzufügen eines `AmpForm` Komponente.
```csharp
// AmpForm-Komponente hinzufügen
AmpForm form = new AmpForm();
form.AddInput("name", "text", "Your Name");
form.AddInput("email", "email", "Your Email");
form.SetAction("https://your-server.com/submit-form"); // Legen Sie die Endpunkt-URL für die Formularübermittlung fest

msgWithForm.AddAmpComponent(form);
msgWithForm.Save(dataDir + "AmpEmailWithForm.eml");
```

### AMP-Timer-Komponente hinzufügen

#### Überblick
Integrieren Sie einen Timer, um Countdowns oder die verstrichene Zeit in Ihrer E-Mail anzuzeigen.

**1. AmpMessage initialisieren**
Einrichten eines neuen `AmpMessage` Beispiel.
```csharp
using Aspose.Email.Amp;

string dataDir = "YOUR_DOCUMENT_DIRECTORY";
AmpMessage msgWithTimer = new AmpMessage();
msgWithTimer.HtmlBody = "<html><body> Hello AMP with Timer </body></html>";
```

**2. AmpTimer hinzufügen**
Konfigurieren und hinzufügen eines `AmpTimer` Komponente.
```csharp
// AmpTimer-Komponente hinzufügen
AmpTimer timer = new AmpTimer();
timer.SetDuration(3600); // Dauer in Sekunden einstellen (zB 1 Stunde)

msgWithTimer.AddAmpComponent(timer);
msgWithTimer.Save(dataDir + "AmpEmailWithTimer.eml");
```

### Abschluss

Mit dieser Anleitung erstellen Sie interaktive und ansprechende AMP-E-Mails mit Aspose.Email für .NET. Diese dynamischen Komponenten verbessern Ihre E-Mail-Marketingstrategie und sorgen für ein interaktiveres Benutzererlebnis.

**Nächste Schritte:**
- Experimentieren Sie mit verschiedenen AMP-Komponenten, um die beste Lösung für Ihre Kampagnen zu finden.
- Testen Sie Ihre E-Mails auf verschiedenen Geräten und E-Mail-Clients, um die Kompatibilität sicherzustellen.
- Überwachen Sie Engagement-Metriken, um die Wirkung Ihrer interaktiven E-Mails zu messen.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}