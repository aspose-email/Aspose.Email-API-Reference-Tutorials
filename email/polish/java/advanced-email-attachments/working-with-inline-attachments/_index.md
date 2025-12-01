---
date: 2025-12-01
description: Dowiedz się, jak wysyłać e‑mail z osadzonym obrazem przy użyciu Aspose.Email
  dla Javy. Ten przewodnik pokazuje, jak osadzać obrazy w e‑mailu i tworzyć e‑mail
  w formacie HTML w Javie z załącznikami inline.
language: pl
linktitle: Working with Inline Attachments in Aspose.Email
second_title: Aspose.Email Java Email Management API
title: Jak wysłać e‑mail z osadzonym obrazem przy użyciu Aspose.Email dla Javy
url: /java/advanced-email-attachments/working-with-inline-attachments/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Jak wysłać e‑mail z osadzonym obrazem przy użyciu Aspose.Email dla Javy

Osadzanie obrazów bezpośrednio w treści e‑maila sprawia, że wiadomości wyglądają profesjonalnie i zapewnia, że odbiorca zobaczy grafikę bez konieczności pobierania oddzielnych plików. W tym samouczku nauczysz się **jak wysłać e‑mail z osadzonym obrazem** przy użyciu Aspose.Email dla Javy, obejmując wszystko od konfiguracji biblioteki, przez tworzenie wiadomości HTML, dodawanie zasobów inline, aż po wysłanie wiadomości.

## Szybkie odpowiedzi
- **Jaka jest podstawowa klasa dla obrazów inline?** `LinkedResource`
- **Która metoda odwołuje się do obrazu w HTML?** Użyj `cid:yourContentId` w znaczniku `<img>`
- **Czy potrzebna jest licencja do rozwoju?** Darmowa wersja próbna wystarczy do testów; licencja jest wymagana w produkcji
- **Czy mogę wysłać e‑mail przez dowolny serwer SMTP?** Tak, wystarczy skonfigurować `SmtpClient` z danymi serwera
- **Czy to rozwiązanie jest kompatybilne ze wszystkimi głównymi klientami poczty?** Większość nowoczesnych klientów (Outlook, Gmail, Thunderbird) obsługuje obrazy osadzone metodą CID

## Czym są załączniki inline (osadzone obrazy)?

Załączniki inline — czasami nazywane osadzonymi lub obrazami CID — to pliki znajdujące się wewnątrz ciała MIME wiadomości e‑mail. Są odwoływane z części HTML wiadomości przy użyciu **Content‑ID** (CID). Ta technika pozwala **osadzić obrazy w e‑mailu**, tak aby pojawiały się dokładnie w miejscu, w którym umieścisz znacznik `<img>`, bez wyświetlania ich jako oddzielne, pobieralne załączniki.

## Dlaczego używać osadzonych obrazów w e‑mailach Java?

- **Profesjonalny wygląd:** Loga, banery i zdjęcia produktów wyświetlają się natychmiast.
- **Lepsze zaangażowanie:** Odbiorcy chętniej czytają e‑mail, który wygląda kompletnie.
- **Brak dodatkowych kliknięć:** Użytkownicy nie muszą pobierać załącznika, aby zobaczyć obraz.
- **Spójna identyfikacja wizualna:** Twoje materiały brandingowe pozostają w linii z treścią wiadomości.

## Wymagania wstępne

- Biblioteka Aspose.Email dla Javy (pobierz z oficjalnej [dokumentacji Aspose.Email dla Javy](https://reference.aspose.com/email/java/))
- Środowisko programistyczne Java 8+
- Dostęp do serwera SMTP do wysyłania poczty
- Plik obrazu, który chcesz osadzić (np. `logo.png`)

## Przewodnik krok po kroku

### Krok 1: Utwórz podstawową wiadomość e‑mail w formacie HTML

Najpierw skonfiguruj prosty `MailMessage` z ciałem HTML. To będzie płótno, na którym później osadzimy obraz.

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

### Krok 2: Dodaj obraz inline przy użyciu `LinkedResource`

Teraz osadzamy obraz. Klasa `LinkedResource` reprezentuje załącznik inline. Przypisz unikalny **Content‑ID** i odwołaj się do niego w ciele HTML przy pomocy `cid:`.

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

> **Pro tip:** Trzymaj `ContentId` prosty i unikalny w obrębie wiadomości, aby uniknąć konfliktów.

### Krok 3: Wyślij e‑mail za pomocą `SmtpClient`

Skonfiguruj ustawienia SMTP i wyślij wiadomość. Osadzony obraz podróżuje razem z e‑mailem, więc odbiorca zobaczy go od razu.

```java
import com.aspose.email.SmtpClient;

// Create an instance of SmtpClient
SmtpClient client = new SmtpClient("smtp.example.com", 587, "username", "password");

// Send the email
client.send(message);
```

### Krok 4: Odbierz i wyodrębnij obrazy inline (opcjonalnie)

Jeśli potrzebujesz przetwarzać przychodzące wiadomości zawierające osadzone obrazy, możesz wczytać plik `.eml` i uzyskać dostęp do jego `LinkedResources`.

```java
import com.aspose.email.MailMessage;
import com.aspose.email.LinkedResourceCollection;

// Load the received email message
MailMessage receivedMessage = MailMessage.load("path/to/received_email.eml");

// Access the inline attachments
LinkedResourceCollection inlineAttachments = receivedMessage.getLinkedResources();
```

## Typowe problemy i jak je rozwiązać

| Problem | Dlaczego się pojawia | Rozwiązanie |
|---------|----------------------|-------------|
| **Content‑ID mismatch** | Odwołanie `cid:` w HTML nie zgadza się z `ContentId` ustawionym w `LinkedResource`. | Upewnij się, że ciągi znaków są identyczne (`image001` vs `cid:image001`). |
| **File not found** | Ścieżka do obrazu jest niepoprawna lub plik nie istnieje. | Zweryfikuj ścieżkę absolutną/względną i upewnij się, że plik znajduje się na serwerze. |
| **SMTP authentication failure** | Nieprawidłowe dane logowania lub ustawienia serwera. | Sprawdź ponownie host, port, nazwę użytkownika i hasło. W razie potrzeby włącz TLS/SSL. |
| **Image not displayed in some clients** | Niektóre klienty blokują zewnętrzne zasoby. | Używaj obrazów osadzonych metodą CID (tak jak pokazano), a nie zewnętrznych URL‑i. |

## Najczęściej zadawane pytania

**Q: Jak pobrać Aspose.Email dla Javy?**  
A: Możesz pobrać Aspose.Email dla Javy z [dokumentacji](https://reference.aspose.com/email/java/). Postępuj zgodnie z instrukcjami instalacji, aby dodać ją do swojego projektu.

**Q: Czy mogę używać Aspose.Email dla Javy z innymi bibliotekami Java?**  
A: Tak, Aspose.Email integruje się płynnie z innymi bibliotekami Java, umożliwiając łączenie przetwarzania e‑maili z generowaniem PDF, OCR lub dostępem do baz danych.

**Q: Jakie formaty plików są obsługiwane jako załączniki inline?**  
A: Obsługiwane są popularne formaty obrazów, takie jak PNG, JPEG, GIF, a także inne typy dokumentów (np. SVG) jako zasoby inline.

**Q: Jak obsługiwać załączniki inline w e‑mailach HTML?**  
A: Użyj klasy `LinkedResource`, aby przypisać `ContentId`, dodaj ją do `message.getLinkedResources()`, i odwołaj się do niej w ciele HTML za pomocą `<img src='cid:yourContentId'>`.

**Q: Czy Aspose.Email dla Javy jest kompatybilny z różnymi serwerami poczty?**  
A: Tak, działa z dowolnym serwerem SMTP/IMAP/POP3. Wystarczy podać prawidłowy adres serwera, port oraz dane uwierzytelniające.

**Ostatnia aktualizacja:** 2025-12-01  
**Testowano z:** Aspose.Email dla Javy 24.12 (najnowsza w momencie pisania)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}