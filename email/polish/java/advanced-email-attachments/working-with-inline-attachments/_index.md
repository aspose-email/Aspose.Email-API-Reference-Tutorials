---
date: 2026-04-28
description: Dowiedz się, jak osadzić obraz w wiadomości e‑mail HTML przy użyciu Aspose.Email
  for Java i wysłać e‑mail z osadzonym obrazem za pośrednictwem SMTP.
keywords:
- embed image in html email
- send email with embedded image
- how to embed image java
- create html email java
- send email via smtp java
linktitle: Praca z załącznikami wbudowanymi w Aspose.Email
second_title: Aspose.Email Java Email Management API
title: Jak osadzić obraz w wiadomości e‑mail HTML przy użyciu Aspose.Email dla Javy
url: /pl/java/advanced-email-attachments/working-with-inline-attachments/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Jak osadzić obraz w wiadomości e‑mail HTML przy użyciu Aspose.Email dla Javy

Osadzenie obrazu bezpośrednio w wiadomości e‑mail sprawia, że Twoje wiadomości wyglądają profesjonalnie i gwarantuje, że odbiorca zobaczy grafikę bez konieczności pobierania osobnych plików. W tym samouczku dowiesz się **jak osadzić obraz w wiadomości e‑mail HTML** przy użyciu Aspose.Email dla Javy, obejmując wszystko od konfiguracji biblioteki po tworzenie wiadomości HTML, dodawanie zasobów inline i ostateczne wysłanie wiadomości przez SMTP.

## Szybkie odpowiedzi
- **Jaka jest podstawowa klasa dla obrazów wbudowanych?** `LinkedResource`
- **Która metoda odwołuje się do obrazu w HTML?** Use `cid:yourContentId` in the `<img>` tag
- **Czy potrzebuję licencji do rozwoju?** A free trial works for testing; a license is required for production
- **Czy mogę wysłać e‑mail przez dowolny serwer SMTP?** Yes, just configure `SmtpClient` with your server details
- **Czy to podejście jest kompatybilne ze wszystkimi głównymi klientami poczty?** Most modern clients (Outlook, Gmail, Thunderbird) support CID‑embedded images

## Jak osadzić obraz w wiadomości e‑mail HTML przy użyciu Aspose.Email dla Javy

Kiedy **osadzasz obraz w wiadomości e‑mail HTML**, obraz staje się częścią ciała MIME, więc wyświetla się natychmiast w kliencie odbiorcy. Poniżej przeprowadzimy Cię przez cały proces, od prostej wiadomości HTML po w pełni funkcjonalny e‑mail z wbudowanym obrazem.

### Co to są załączniki wbudowane (obrazy osadzone)?

Załączniki wbudowane — czasami nazywane obrazami osadzonymi lub CID — to pliki, które znajdują się wewnątrz ciała MIME wiadomości e‑mail. Są odwoływane z części HTML wiadomości przy użyciu **Content‑ID** (CID). Ta technika pozwala **osadzać obrazy w e‑mailu**, tak aby pojawiały się dokładnie w miejscu, w którym umieścisz znacznik `<img>`, bez wyświetlania ich jako oddzielnych załączników do pobrania.

### Dlaczego używać osadzonych obrazów w wiadomościach e‑mail Java?

- **Profesjonalny wygląd:** Loga, banery i zdjęcia produktów wyświetlają się natychmiast.
- **Lepsze zaangażowanie:** Odbiorcy chętniej czytają e‑mail, który wygląda kompletnie.
- **Brak dodatkowych kliknięć:** Użytkownicy nie muszą pobierać załącznika, aby zobaczyć obraz.
- **Spójna identyfikacja wizualna:** Twoje zasoby marki pozostają w linii z treścią wiadomości.

### Wymagania wstępne

- Biblioteka Aspose.Email for Java (pobierz z oficjalnej [dokumentacji Aspose.Email for Java](https://reference.aspose.com/email/java/))
- Środowisko programistyczne Java 8+
- Dostęp do serwera SMTP do wysyłania poczty
- Plik obrazu, który chcesz osadzić (np. `logo.png`)

## Przewodnik krok po kroku

### Krok 1: Utwórz podstawową wiadomość e‑mail HTML

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

### Krok 2: Dodaj wbudowany obraz przy użyciu `LinkedResource`

Teraz osadzamy obraz. Klasa `LinkedResource` reprezentuje wbudowany załącznik. Przypisz unikalny **Content‑ID** i odwołaj się do niego w ciele HTML przy użyciu `cid:`.

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

> **Wskazówka:** Trzymaj `ContentId` prosty i unikalny w obrębie wiadomości, aby uniknąć konfliktów.

### Krok 3: Wyślij e‑mail za pomocą `SmtpClient`

Skonfiguruj ustawienia SMTP i wyślij wiadomość. Osadzony obraz podróżuje razem z e‑mailem, więc odbiorca zobaczy go od razu.

```java
import com.aspose.email.SmtpClient;

// Create an instance of SmtpClient
SmtpClient client = new SmtpClient("smtp.example.com", 587, "username", "password");

// Send the email
client.send(message);
```

### Krok 4: Odbierz i wyodrębnij wbudowane obrazy (opcjonalnie)

Jeśli musisz przetwarzać przychodzące wiadomości zawierające osadzone obrazy, możesz załadować plik `.eml` i uzyskać dostęp do jego `LinkedResources`.

```java
import com.aspose.email.MailMessage;
import com.aspose.email.LinkedResourceCollection;

// Load the received email message
MailMessage receivedMessage = MailMessage.load("path/to/received_email.eml");

// Access the inline attachments
LinkedResourceCollection inlineAttachments = receivedMessage.getLinkedResources();
```

## Typowe problemy i jak je naprawić

| Problem | Dlaczego się pojawia | Rozwiązanie |
|---------|----------------------|-------------|
| **Niezgodność Content‑ID** | Odwołanie `cid:` w HTML nie pasuje do `ContentId` ustawionego w `LinkedResource`. | Upewnij się, że ciągi są identyczne (`image001` vs `cid:image001`). |
| **Plik nie znaleziony** | Ścieżka do obrazu jest nieprawidłowa lub plik nie istnieje. | Zweryfikuj ścieżkę absolutną/względną i upewnij się, że plik istnieje na serwerze. |
| **Błąd uwierzytelniania SMTP** | Nieprawidłowe dane logowania lub ustawienia serwera. | Sprawdź ponownie host, port, nazwę użytkownika i hasło. Włącz TLS/SSL, jeśli jest wymagane. |
| **Obraz nie wyświetla się w niektórych klientach** | Niektóre klienty blokują zewnętrzne zasoby. | Używaj obrazów osadzonych CID (jak pokazano) zamiast zewnętrznych URL‑i. |

## Najczęściej zadawane pytania

**Q: Jak pobrać Aspose.Email dla Javy?**  
A: Możesz pobrać Aspose.Email dla Javy z [dokumentacji](https://reference.aspose.com/email/java/). Postępuj zgodnie z instrukcjami instalacji, aby skonfigurować ją w swoim projekcie.

**Q: Czy mogę używać Aspose.Email dla Javy z innymi bibliotekami Javy?**  
A: Tak, Aspose.Email integruje się płynnie z innymi bibliotekami Javy, umożliwiając łączenie przetwarzania e‑maili z generowaniem PDF, OCR lub dostępem do baz danych.

**Q: Jakie formaty plików są obsługiwane jako załączniki wbudowane?**  
A: Obsługiwane są typowe formaty obrazów, takie jak PNG, JPEG, GIF, a także inne typy dokumentów (np. SVG) jako zasoby inline.

**Q: Jak obsługiwać załączniki wbudowane w wiadomościach HTML?**  
A: Użyj klasy `LinkedResource`, aby przypisać `ContentId`, dodaj ją do `message.getLinkedResources()` i odwołaj się do niej w ciele HTML za pomocą `<img src='cid:yourContentId'>`.

**Q: Czy Aspose.Email dla Javy jest kompatybilny z różnymi serwerami pocztowymi?**  
A: Tak, działa z dowolnym serwerem SMTP/IMAP/POP3. Wystarczy podać prawidłowy adres serwera, port oraz dane uwierzytelniające.

## Podsumowanie

Masz teraz kompletny, gotowy do produkcji przepis na **osadzanie obrazu w wiadomości e‑mail HTML** przy użyciu Aspose.Email dla Javy. Tworząc `LinkedResource`, przypisując unikalny Content‑ID i odwołując się do niego za pomocą `cid:` w ciele HTML, zapewniasz, że loga, banery lub zdjęcia produktów pojawią się dokładnie tam, gdzie chcesz — bez dodatkowych pobrań czy zepsutych linków. Połącz to z solidną klasą `SmtpClient`, aby wysłać wiadomość przez dowolny serwer SMTP, i jesteś gotowy dostarczać eleganckie, spójne z marką e‑maile z aplikacji Java.

---

**Ostatnia aktualizacja:** 2026-04-28  
**Testowano z:** Aspose.Email for Java 24.12 (najnowsza w momencie pisania)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}