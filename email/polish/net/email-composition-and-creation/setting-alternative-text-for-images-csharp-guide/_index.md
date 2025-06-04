---
"description": "Naucz się ustawiać alternatywny tekst dla obrazów w wiadomościach e-mail za pomocą Aspose.Email dla .NET. Zapewnij dostępność dzięki wyraźnemu tekstowi alt. Dołączono dokumentację i kod."
"linktitle": "Ustawianie alternatywnego tekstu dla obrazów - przewodnik C#"
"second_title": "Aspose.Email .NET API przetwarzania poczty e-mail"
"title": "Ustawianie alternatywnego tekstu dla obrazów - przewodnik C#"
"url": "/pl/net/email-composition-and-creation/setting-alternative-text-for-images-csharp-guide/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Ustawianie alternatywnego tekstu dla obrazów - przewodnik C#


Ten przewodnik przeprowadzi Cię przez proces ustawiania tekstu alternatywnego dla obrazów w wiadomościach e-mail przy użyciu Aspose.Email dla .NET. Tekst alternatywny, znany również jako „alt text”, jest używany do zapewnienia tekstowego opisu obrazu w przypadku, gdy obraz nie może zostać wyświetlony. Aspose.Email dla .NET to potężna biblioteka, która umożliwia pracę z wiadomościami e-mail i załącznikami w różnych formatach. W tym przewodniku skupimy się na ustawianiu tekstu alternatywnego dla obrazów w wiadomościach e-mail przy użyciu języka C#.

## Wymagania wstępne

Zanim zaczniesz, upewnij się, że spełniasz następujące wymagania wstępne:

1. Zainstalowany program Visual Studio lub dowolne zgodne środowisko programistyczne C#.
2. Biblioteka Aspose.Email dla .NET. Możesz użyć NuGet Package Manager w Visual Studio.

## Krok 1: Utwórz nowy projekt

1. Uruchom program Visual Studio i utwórz nowy projekt aplikacji konsolowej w języku C#.

## Krok 2: Zainstaluj Aspose.Email za pomocą NuGet

1. Kliknij prawym przyciskiem myszy swój projekt w Eksploratorze rozwiązań i wybierz opcję „Zarządzaj pakietami NuGet”.
2. Wyszukaj „Aspose.Email” i zainstaluj najnowszą wersję pakietu.

## Krok 3: Dodaj instrukcje Using

```csharp

using Aspose.Email.Mime;
```

## Krok 4: Załaduj i zmodyfikuj wiadomość e-mail

1. Załaduj wiadomość e-mail za pomocą `MailMessage` klasa:

```csharp
MailMessage message = new MailMessage();
message.Subject = "Sample Email with Alternative Text";
message.From = new MailAddress("sender@example.com");
message.To.Add("recipient@example.com");
```

3. Załaduj zawartość HTML wiadomości e-mail:

```csharp
var htmlView = AlternateView.CreateAlternateViewFromString("<html><body><img src='cid:logo.jpg' alt='Company Logo'></body></html>", null, "text/html");
```

## Krok 5: Dodaj AlternativeView dla alternatywnego tekstu do obrazów

Dodaj do wiadomości widok htmlview dla tekstu alternatywnego do obrazu jako AlternateView. 
```csharp
message.AlternateViews.Add(htmlView);
```

## Krok 6: Zapisz i wyślij wiadomość e-mail

1. Zapisz zmodyfikowaną wiadomość do pliku lub wyślij ją wybraną metodą:

```csharp
message.Save("output.eml", SaveOptions.DefaultEml);
```

## Wniosek

W tym przewodniku dowiedziałeś się, jak ustawić tekst alternatywny dla obrazów w wiadomościach e-mail przy użyciu Aspose.Email dla .NET. Postępując zgodnie z powyższymi krokami, możesz zapewnić, że treść wiadomości e-mail pozostanie dostępna i informacyjna, nawet gdy obrazy nie mogą zostać wyświetlone.

## Często zadawane pytania

## Jak mogę pobrać bibliotekę Aspose.Email?

Bibliotekę Aspose.Email można pobrać ze strony Aspose Releases lub zainstalować ją za pomocą Menedżera pakietów NuGet w programie Visual Studio.

### Jak dodać obrazy jako powiązane zasoby w wiadomości e-mail?

Aby dodać obrazy jako powiązane zasoby w wiadomości e-mail, możesz użyć `LinkedResource` Klasa. Przypisz identyfikator zawartości do powiązanego zasobu, a następnie odwołaj się do tego identyfikatora zawartości w treści HTML za pomocą `cid:` schemat. Szczegółowe informacje można znaleźć w [Dokumentacja LinkedResource](https://reference.aspose.com/email/net/aspose.email/linkedresource/).
### Gdzie mogę znaleźć więcej dokumentacji na temat Aspose.Email dla .NET?

Bardziej szczegółową dokumentację, samouczki i przykłady dotyczące pracy z Aspose.Email dla .NET można znaleźć w [Odniesienie do API](https://reference.aspose.com/email/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}