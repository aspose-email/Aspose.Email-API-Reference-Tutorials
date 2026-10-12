---
date: 2026-10-12
description: Dowiedz się, jak osadzać obrazy w wiadomościach HTML przy użyciu Aspose.Email
  for Java, wysyłać e‑mail w formacie HTML z osadzonymi obrazami oraz zmniejszyć rozmiar
  załączników e‑mail.
keywords:
- reduce email attachment size
- create email with image
- optimize image for email
- send html email java
- embed cid image email
lastmod: 2026-10-12
linktitle: Jak dołączyć obraz do e‑maila przy użyciu Aspsoe.Email
og_description: Zmniejsz rozmiar załączników e‑mail i osadzaj obrazy w wiadomościach
  HTML przy użyciu Aspose.Email for Java. Postępuj zgodnie z tym przewodnikiem krok
  po kroku, aby efektywnie wysyłać bogate wiadomości HTML.
og_image_alt: 'Developer guide: embed images in HTML email while reducing attachment
  size with Aspose.Email for Java'
og_title: Zmniejsz rozmiar załączników e‑mail przy użyciu Aspose.Email for Java
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: Learn how to embed images in HTML email using Aspose.Email for Java,
    send HTML email with embedded images, and reduce email attachment size.
  headline: Reduce email attachment size with Aspose.Email for Java
  type: TechArticle
- questions:
  - answer: Repeat the attachment and `LinkedResource` steps for each image, assigning
      a unique Content‑ID (e.g., `image2`, `image3`) and referencing them in the HTML.
    question: How can I embed multiple images in a single email?
  - answer: Plain‑text format does not support embedded images. You can only include
      URLs that recipients can click to view the image online.
    question: Can I embed images in plain‑text emails?
  - answer: JPEG, PNG, and GIF are widely supported. Use JPEG for photographs and
      PNG for graphics with transparency.
    question: What image formats are safe for email embedding?
  - answer: Yes—add `width`/`height` attributes to the `<img>` tag, e.g., `<img src='cid:image1'
      width='400' height='300'>`.
    question: Is there a way to control image dimensions in the email?
  - answer: While there’s no strict SMTP limit, most mail providers recommend keeping
      total email size under 5 MB. Optimizing image size helps stay well within this
      limit.
    question: Are there size limits for embedded images?
  type: FAQPage
second_title: Aspose.Email Java Email Management API
tags:
- email attachment size
- Aspose.Email
- Java email API
- embed images email
- HTML email
title: Zmniejsz rozmiar załączników e‑mail przy użyciu Aspose.Email for Java
url: /pl/java/advanced-email-attachments/embedding-images-as-attachments/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zmniejsz rozmiar załącznika e‑mail przy użyciu Aspose.Email dla Javy

Osadzanie obrazów bezpośrednio w wiadomości e‑mail HTML nie tylko sprawia, że wiadomość wygląda elegancko, ale także **zmniejsza rozmiar załącznika e‑mail**, ponieważ obraz jest częścią ciała MIME, a nie osobnym plikiem. W tym samouczku dowiesz się, jak utworzyć e‑mail z obrazem, osadzić obraz przy użyciu odwołania CID oraz zastosować wskazówki najlepszych praktyk, aby **optymalizować obraz pod e‑mail**, tak aby końcowa wiadomość była lekka. Zobaczysz również, jak wysłać e‑mail HTML w stylu Javy przy użyciu Aspose.Email i utrzymać całkowitą wielkość danych znacznie poniżej typowych limitów skrzynki pocztowej.

## Szybkie odpowiedzi
- **Jaka klasa tworzy wiadomość e‑mail?** `MailMessage` – podstawowy kontener dla tematu, odbiorców i treści.  
- **Który obiekt pozwala osadzić obraz w treści HTML?** `LinkedResource` – otacza strumień obrazu i przypisuje Content‑ID.  
- **Czy potrzebna jest licencja do użytku produkcyjnego?** Tak – wymagana jest komercyjna licencja Aspose.Email, aby usunąć ograniczenia wersji próbnej.  
- **Jak mogę zmniejszyć rozmiar załącznika?** Optymalizuj obraz (zmień rozmiar do ≤600 px, skompresuj poniżej 100 KB) przed dodaniem.  
- **Czy mogę osadzić kilka obrazów?** Oczywiście – dodaj unikalny Content‑ID dla każdego obrazu i odwołuj się do nich przy użyciu URI `cid:`.

## Co to jest osadzony obraz w e‑mailu HTML?
Osadzenie obrazu oznacza wstawienie go do struktury MIME wiadomości e‑mail, tak aby odbiorca widział go w treści. Obraz jest odwoływany za pomocą **Content‑ID (CID)**, które znacznik HTML `<img>` ładuje bezpośrednio z ciała wiadomości, eliminując osobne załączniki i zmniejszając ogólny rozmiar.

## Dlaczego wysyłać e‑mail HTML z osadzonym obrazem?
Osadzanie obrazów w HTML pozwala tworzyć bardziej atrakcyjne newslettery, ogłoszenia produktów lub zgłoszenia wsparcia. Odbiorcy widzą grafikę od razu, bez konieczności pobierania załącznika, co zwiększa wskaźniki otwarć i ogólne zaangażowanie. Większość klientów e‑mail obsługuje obrazy CID, a osadzanie eliminuje dodatkowe kroki pobierania, co prowadzi do szybszego renderowania i mniejszego zużycia pasma.

## Wymagania wstępne
- **Aspose.Email for Java** – pobierz ze strony oficjalnej: [Aspose.Email Java download](https://releases.aspose.com/email/java/).  
- Dostęp do serwera SMTP (Gmail, Outlook lub własny serwer przekaźnikowy).  
- Plik obrazu (JPEG, PNG lub GIF), który chcesz osadzić.

> **Pro tip:** *Optymalizuj rozmiar obrazu pod e‑mail*, zmniejszając szerokość do ≤600 px i kompresując do ≤100 KB. To skraca czas ładowania i zapobiega przekroczeniu limitów rozmiaru skrzynki pocztowej.

## Tworzenie wiadomości e‑mail
`MailMessage` jest obiektem najwyższego poziomu w Aspose.Email, który reprezentuje pojedynczy e‑mail. Przechowuje temat, nadawcę, odbiorców oraz treść (tekstową lub HTML).  
Klasa `MailMessage` jest centralnym modelem do budowania i wysyłania wiadomości e‑mail w Aspose.Email dla Javy.

```java
// Import necessary libraries
import com.aspose.email.*;

// Create a new email message
MailMessage message = new MailMessage();
```

## Dodawanie obrazu jako załącznika
`LinkedResource` reprezentuje część MIME, którą można osadzić w treści e‑maila.  
Przed osadzeniem dodajesz plik obrazu do kolekcji załączników wiadomości. Załącznik staje się strumieniem, do którego `LinkedResource` może później odwołać się.

```java
// Specify the path to the image file
String imagePath = "path/to/your/image.jpg";

// Attach the image to the email
Attachment attachment = new Attachment(imagePath);
message.getAttachments().add(attachment);
```

## Osadzanie załączonego obrazu w HTML
`LinkedResource` służy do powiązania strumienia obrazu z Content‑ID w celu wyświetlenia go w treści.  
Aby wyświetlić obraz w treści HTML, utwórz `LinkedResource`, który wskazuje na załączony obraz i ustaw jego Content‑ID (np. `image1`). Następnie odwołaj się do tego ID w HTML, używając schematu URI `cid:`.

```java
// Create a LinkedResource for the attached image
LinkedResource linkedImage = new LinkedResource(attachment.getContentStream(), "image/jpeg");
linkedImage.setContentId("image1");

// Create an HTML body with the embedded image
String htmlBody = "<html><body><h1>Check out this image:</h1><img src='cid:image1'></body></html>";
message.setHtmlBody(htmlBody);
message.getLinkedResources().addItem(linkedImage);
```

> **Dlaczego używać `LinkedResource`?** Sygnał dla klienta, że obraz jest częścią ciała wiadomości, co jest niezbędne w scenariuszach **send html email java**, które wymagają grafik w treści.

## Wysyłanie wiadomości e‑mail
`SmtpClient` jest klasą obsługującą komunikację SMTP w celu wysyłania wiadomości.  
`SmtpClient` zajmuje się rzeczywistym przesyłaniem. Skonfiguruj go z hostem serwera, portem i danymi uwierzytelniającymi, a następnie wywołaj `send`, aby wysłać `MailMessage`.  
`SmtpClient` to klasa transportowa SMTP w Aspose.Email, która bezpiecznie wysyła skonstruowany `MailMessage` do docelowego serwera pocztowego.

```java
// Initialize the SmtpClient
SmtpClient client = new SmtpClient("smtp.example.com", 587, "your_username", "your_password");

// Send the email
client.send(message);
```

Kiedy odbiorca otwiera e‑mail, treść HTML wyświetla obraz w linii, zapewniając płynne wrażenia wizualne przy jednoczesnym utrzymaniu małej wielkości ładunku.

## Jak osadzić wiele obrazów w e‑mailu
`LinkedResource` reprezentuje część MIME, którą można osadzić w treści e‑maila.  
Dodaj każdy obraz jako osobny załącznik, utwórz odrębny `LinkedResource` dla każdego i przypisz unikalny Content‑ID, np. `image2`, `image3` itd. Odwołuj się do nich w HTML za pomocą `src='cid:image2'`. Ten wzorzec skaluje się do newsletterów z dziesiątkami grafik bez zwiększania rozmiaru wiadomości.

## Wskazówki, jak zmniejszyć rozmiar załącznika e‑mail
- **Zmień rozmiar** obrazu do dokładnych potrzebnych wymiarów (zazwyczaj ≤600 px szerokości).  
- **Kompresuj** przy użyciu narzędzi takich jak ImageMagick lub kompresorów online, aby plik był poniżej 100 KB.  
- **Wybierz odpowiedni format**: JPEG dla zdjęć, PNG dla grafik z przezroczystością.  
- **Usuń metadane EXIF**, jeśli nie są potrzebne.  
- **Używaj progresywnego JPEG**, aby przyspieszyć renderowanie progresywne w obsługiwanych klientach.

## Typowe problemy i rozwiązywanie
| Issue | Cause | Solution |
|-------|-------|----------|
| Obraz nie wyświetla się | Nieprawidłowy Content‑ID lub brak `LinkedResource` | Sprawdź, czy `linkedImage.setContentId("image1")` odpowiada `src='cid:image1'` w HTML. |
| Duży rozmiar e‑maila | Niezoptymalizowany obraz (wysoka rozdzielczość) | Zmień rozmiar/skompresuj obraz przed dołączeniem; celuj w ≤100 KB. |
| E‑mail oznaczony jako spam | Brak odpowiednich nagłówków MIME | Upewnij się, że `SmtpClient` używa TLS/STARTTLS i ustaw wyraźny adres `From`. |
| Obraz w treści pojawia się jako załącznik | Klient nie obsługuje CID | Podaj alternatywny URL w znaczniku `<img>` (`src='cid:image1' alt='Image'`). |

## Najczęściej zadawane pytania

**Q: Jak mogę osadzić wiele obrazów w jednej wiadomości e‑mail?**  
A: Powtórz kroki dodawania załącznika i `LinkedResource` dla każdego obrazu, przypisując unikalny Content‑ID (np. `image2`, `image3`) i odwołując się do nich w HTML.

**Q: Czy mogę osadzać obrazy w e‑mailach w formacie tekstowym?**  
A: Format tekstowy nie obsługuje osadzonych obrazów. Można jedynie umieścić URL, które odbiorcy mogą kliknąć, aby zobaczyć obraz online.

**Q: Jakie formaty obrazów są bezpieczne do osadzania w e‑mailu?**  
A: JPEG, PNG i GIF są szeroko wspierane. Używaj JPEG dla fotografii i PNG dla grafik z przezroczystością.

**Q: Czy istnieje sposób kontrolowania wymiarów obrazu w e‑mailu?**  
A: Tak — dodaj atrybuty `width`/`height` do znacznika `<img>`, np. `<img src='cid:image1' width='400' height='300'>`.

**Q: Czy istnieją limity rozmiaru dla osadzonych obrazów?**  
A: Chociaż nie ma ścisłego limitu SMTP, większość dostawców poczty zaleca utrzymanie całkowitego rozmiaru e‑maila poniżej 5 MB. Optymalizacja rozmiaru obrazu pomaga pozostać w granicach tego limitu.

---

**Ostatnia aktualizacja:** 2026-10-12  
**Testowano z:** Aspose.Email for Java 24.11 (najnowsza w momencie pisania)  
**Autor:** Aspose

## Powiązane samouczki

- [Zarządzanie limitem rozmiaru załącznika e‑mail przy użyciu Aspose.Email](/email/java/advanced-email-attachments/managing-large-attachments/)
- [Tworzenie i wysyłanie załączników e‑mail Aspose Email Java](/email/java/attachments-handling/build-send-emails-attachments-aspose-email-java/)
- [Jak wyodrębnić załączniki z plików msg przy użyciu Aspose.Email dla Javy](/email/java/advanced-email-attachments/extracting-attachments-from-email-messages/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}