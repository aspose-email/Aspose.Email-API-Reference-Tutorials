---
title: Ustawianie tekstu alternatywnego dla obrazów — przewodnik po języku C#
linktitle: Ustawianie tekstu alternatywnego dla obrazów — przewodnik po języku C#
second_title: Aspose.Email .NET API do przetwarzania poczty e-mail
description: Dowiedz się, jak ustawić alternatywny tekst dla obrazów w wiadomościach e-mail za pomocą Aspose.Email dla .NET. Zapewnij dostępność dzięki wyraźnemu tekstowi alternatywnemu. W zestawie dokumentacja i kod.
weight: 15
url: /pl/net/email-composition-and-creation/setting-alternative-text-for-images-csharp-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ustawianie tekstu alternatywnego dla obrazów — przewodnik po języku C#


Ten przewodnik przeprowadzi Cię przez proces ustawiania alternatywnego tekstu dla obrazów w wiadomościach e-mail przy użyciu Aspose.Email dla .NET. Tekst alternatywny, znany również jako „tekst alternatywny”, służy do zapewnienia tekstowego opisu obrazu w przypadku, gdy obraz nie może zostać wyświetlony. Aspose.Email dla .NET to potężna biblioteka, która umożliwia pracę z wiadomościami e-mail i załącznikami w różnych formatach. W tym przewodniku skupimy się na ustawianiu tekstu alternatywnego dla obrazów w wiadomościach e-mail przy użyciu języka C#.

## Warunki wstępne

Zanim zaczniesz, upewnij się, że masz następujące wymagania wstępne:

1. Zainstalowano program Visual Studio lub dowolne kompatybilne środowisko programistyczne C#.
2. Aspose.Email dla biblioteki .NET. Możesz użyć Menedżera pakietów NuGet w programie Visual Studio.

## Krok 1: Utwórz nowy projekt

1. Uruchom program Visual Studio i utwórz nowy projekt aplikacji konsolowej C#.

## Krok 2: Zainstaluj Aspose.Email za pośrednictwem NuGet

1. Kliknij prawym przyciskiem myszy projekt w Eksploratorze rozwiązań i wybierz opcję „Zarządzaj pakietami NuGet”.
2. Wyszukaj „Aspose.Email” i zainstaluj najnowszą wersję pakietu.

## Krok 3: Dodaj instrukcje using

```csharp

using Aspose.Email.Mime;
```

## Krok 4: Załaduj i zmodyfikuj wiadomość e-mail

1.  Załaduj wiadomość e-mail za pomocą`MailMessage` klasa:

```csharp
MailMessage message = new MailMessage();
message.Subject = "Sample Email with Alternative Text";
message.From = new MailAddress("sender@example.com");
message.To.Add("recipient@example.com");
```

3. Załaduj treść HTML wiadomości e-mail:

```csharp
var htmlView = AlternateView.CreateAlternateViewFromString("<html><body><img src='cid:logo.jpg' alt='Company Logo'></body></html>", null, "text/html");
```

## Krok 5: Dodaj widok alternatywny dla tekstu alternatywnego do obrazów

Dodaj widok HTML dla tekstu alternatywnego do obrazu jako widok alternatywny do wiadomości. 
```csharp
message.AlternateViews.Add(htmlView);
```

## Krok 6: Zapisz i wyślij wiadomość e-mail

1. Zapisz zmodyfikowaną wiadomość do pliku lub wyślij ją wybraną metodą:

```csharp
message.Save("output.eml", SaveOptions.DefaultEml);
```

## Wniosek

W tym przewodniku dowiedziałeś się, jak ustawić alternatywny tekst dla obrazów w wiadomościach e-mail przy użyciu Aspose.Email dla .NET. Wykonując czynności opisane powyżej, możesz mieć pewność, że treść Twojej wiadomości e-mail pozostanie dostępna i zawierająca istotne informacje, nawet jeśli nie będzie można wyświetlić obrazów.

## Często zadawane pytania

## Jak mogę pobrać bibliotekę Aspose.Email?

Możesz pobrać bibliotekę Aspose.Email z wydań Aspose lub zainstalować ją za pomocą Menedżera pakietów NuGet w programie Visual Studio.

### Jak dodać obrazy jako połączone zasoby w wiadomości e-mail?

Aby dodać obrazy jako połączone zasoby w wiadomości e-mail, możesz użyć opcji`LinkedResource` klasa. Przypisz identyfikator treści do połączonego zasobu, a następnie odwołaj się do tego identyfikatora treści w treści HTML za pomocą`cid:` schemat. Szczegółowe informacje można znaleźć w[Dokumentacja LinkedResource](https://reference.aspose.com/email/net/aspose.email/linkedresource/).
### Gdzie mogę znaleźć więcej dokumentacji na temat Aspose.Email dla .NET?

 Bardziej szczegółową dokumentację, samouczki i przykłady dotyczące pracy z Aspose.Email dla .NET można znaleźć w pliku[Dokumentacja API](https://reference.aspose.com/email/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
