---
title: Podpisywanie wiadomości e-mail za pomocą DKIM przy użyciu kodu C#
linktitle: Podpisywanie wiadomości e-mail za pomocą DKIM przy użyciu kodu C#
second_title: Aspose.Email .NET API do przetwarzania poczty e-mail
description: Naucz się zabezpieczać wiadomości e-mail za pomocą DKIM przy użyciu C# i Aspose.Email dla .NET. Przewodnik krok po kroku z kodem źródłowym. Zwiększ zaufanie i autentyczność poczty e-mail.
type: docs
weight: 11
url: /pl/net/email-security-and-signatures/signing-emails-with-dkim-using-csharp-code/
---

W dzisiejszym cyfrowym świecie zapewnienie autentyczności i integralności komunikacji e-mailowej ma ogromne znaczenie. Jednym ze sposobów osiągnięcia tego jest użycie podpisów DomainKeys Identified Mail (DKIM). W tym przewodniku krok po kroku odkryjemy, jak podpisywać wiadomości e-mail za pomocą DKIM przy użyciu języka C# i potężnej biblioteki Aspose.Email dla .NET.

## Wprowadzenie do DKIM

### Co to jest DKIM?
DKIM oznacza pocztę identyfikowaną przez DomainKeys. Jest to metoda uwierzytelniania wiadomości e-mail, która umożliwia nadawcy cyfrowe podpisanie wiadomości e-mail, dostarczając podpis kryptograficzny weryfikujący autentyczność wiadomości e-mail.

### Dlaczego DKIM jest ważny?
DKIM pomaga zapobiegać fałszowaniu wiadomości e-mail i atakom typu phishing, zapewniając, że przychodzące wiadomości e-mail pochodzą z legalnych źródeł i nie zostały zmienione podczas przesyłania.

## Warunki wstępne

Zanim zaczniemy, upewnij się, że spełnione są następujące wymagania wstępne:

1.  Aspose.Email dla .NET: Upewnij się, że masz zainstalowaną bibliotekę Aspose.Email dla .NET w swoim projekcie. Można go pobrać z[Tutaj](https://releases.aspose.com/email/net/).

2. Klucz prywatny DKIM: Do podpisywania e-maili będziesz potrzebować klucza prywatnego DKIM. Upewnij się, że masz to gotowe. 

## Krok 1: Zainicjuj parametry DKIM

```csharp
string privateKeyFile = Path.Combine(RunExamples.GetDataDir_SMTP().Replace("_Send", string.Empty), RunExamples.GetDataDir_SMTP() + "key2.pem");

RSACryptoServiceProvider rsa = PemReader.GetPrivateKey(privateKeyFile);
DKIMSignatureInfo signInfo = new DKIMSignatureInfo("test", "yandex.ru");
signInfo.Headers.Add("From");
signInfo.Headers.Add("Subject");
```

W tym kroku inicjujemy parametry DKIM. Ładujemy klucz prywatny z pliku, określamy selektor i domenę oraz wymieniamy nagłówki, które powinny znaleźć się w podpisie DKIM.

## Krok 2: Utwórz i przygotuj wiadomość e-mail

```csharp
MailMessage mailMessage = new MailMessage("useremail@gmail.com", "test@gmail.com");
mailMessage.Subject = "Signed DKIM message text body";
mailMessage.Body = "This is a text body signed DKIM message";
```

Tutaj tworzymy instancję`MailMessage` class i ustaw nadawcę, odbiorcę, temat i treść wiadomości e-mail.

## Krok 3: Podpisz e-mail

```csharp
MailMessage signedMsg = mailMessage.DKIMSign(rsa, signInfo);
```

Teraz podpisujemy wiadomość e-mail za pomocą zainicjowanych wcześniej parametrów DKIM i klucza prywatnego.

## Krok 4: Wyślij podpisany e-mail

```csharp
try
{
    SmtpClient client = new SmtpClient("smtp.gmail.com", 587, "your.email@gmail.com", "your.password");
    client.Send(signedMsg);                
}
finally
{
    // Kod czyszczący, jeśli istnieje
}
```
 Na tym etapie wysyłamy podpisaną wiadomość e-mail za pomocą klienta SMTP. Upewnij się, że wymieniłeś`"your.email@gmail.com"` I`"your.password"` za pomocą danych logowania do Gmaila.

## Uzupełnij kod źródłowy
```csharp

string privateKeyFile = Path.Combine(RunExamples.GetDataDir_SMTP().Replace("_Send", string.Empty), RunExamples.GetDataDir_SMTP()+ "key2.pem");

RSACryptoServiceProvider rsa = PemReader.GetPrivateKey(privateKeyFile);
DKIMSignatureInfo signInfo = new DKIMSignatureInfo("test", "yandex.ru");
signInfo.Headers.Add("From");
signInfo.Headers.Add("Subject");

MailMessage mailMessage = new MailMessage("useremail@gmail.com", "test@gmail.com");
mailMessage.Subject = "Signed DKIM message text body";
mailMessage.Body = "This is a text body signed DKIM message";
MailMessage signedMsg = mailMessage.DKIMSign(rsa, signInfo);

try
{
	SmtpClient client = new SmtpClient("smtp.gmail.com", 587, "your.email@gmail.com", "your.password");
	client.Send(signedMsg);                
}
finally
{}
```

## Wniosek

Podpisywanie wiadomości e-mail za pomocą DKIM to kluczowy krok zapewniający bezpieczeństwo i autentyczność Twojej komunikacji e-mailowej. Za pomocą Aspose.Email dla .NET i C# możesz łatwo wdrożyć podpisy DKIM w procesie wysyłania wiadomości e-mail.

---

## Często Zadawane Pytania

### P1: Co to jest DKIM i dlaczego jest ważny dla bezpieczeństwa poczty e-mail?

DKIM oznacza DomainKeys Identified Mail i jest ważny dla bezpieczeństwa poczty e-mail, ponieważ weryfikuje autentyczność wiadomości e-mail, zapobiegając fałszowaniu i phishingowi.

### P2: Jak uzyskać klucz prywatny DKIM?

Klucz prywatny DKIM możesz uzyskać za pośrednictwem swojego dostawcy usług e-mail lub generując go za pomocą narzędzi kryptograficznych.

### P3: Czy mogę używać Aspose.Email dla .NET z innymi dostawcami poczty e-mail poza Gmailem?

Tak, Aspose.Email dla .NET może być używany z różnymi dostawcami poczty e-mail, nie ograniczając się do Gmaila.

### P4: Jakie nagłówki powinienem uwzględnić w podpisie DKIM?

Typowe nagłówki, które należy uwzględnić w podpisie DKIM, to „Od”, „Temat” i inne nagłówki ważne dla uwierzytelniania wiadomości e-mail.

### P5: Czy DKIM to jedyna metoda uwierzytelniania poczty e-mail?

Nie, istnieją inne metody, takie jak SPF i DMARC, które są używane w połączeniu z DKIM w celu zwiększenia bezpieczeństwa poczty e-mail.