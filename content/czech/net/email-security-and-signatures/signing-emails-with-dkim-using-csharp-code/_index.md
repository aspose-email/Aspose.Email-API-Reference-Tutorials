---
title: Podepisování e-mailů pomocí DKIM pomocí kódu C#
linktitle: Podepisování e-mailů pomocí DKIM pomocí kódu C#
second_title: Aspose.Email .NET Email Processing API
description: Naučte se zabezpečit e-maily pomocí DKIM pomocí C# & Aspose.Email pro .NET. Průvodce krok za krokem se zdrojovým kódem. Zvyšte důvěryhodnost a autenticitu e-mailů.
type: docs
weight: 11
url: /cs/net/email-security-and-signatures/signing-emails-with-dkim-using-csharp-code/
---

V dnešním digitálním světě má prvořadý význam zajištění autenticity a integrity e-mailové komunikace. Jedním ze způsobů, jak toho dosáhnout, je použití podpisů DomainKeys Identified Mail (DKIM). V tomto podrobném průvodci prozkoumáme, jak podepisovat e-maily pomocí DKIM pomocí C# a výkonné knihovny Aspose.Email for .NET.

## Úvod do DKIM

### Co je DKIM?
DKIM je zkratka pro DomainKeys Identified Mail. Je to metoda ověřování e-mailu, která umožňuje odesílateli digitálně podepsat e-mail a poskytnout kryptografický podpis, který ověřuje pravost e-mailu.

### Proč je DKIM důležitý?
DKIM pomáhá předcházet e-mailovému spoofingu a phishingovým útokům tím, že zajišťuje, že příchozí e-maily pocházejí z legitimních zdrojů a během přenosu s nimi nebylo manipulováno.

## Předpoklady

Než začneme, ujistěte se, že máte splněny následující předpoklady:

1.  Aspose.Email for .NET: Ujistěte se, že máte ve svém projektu nainstalovanou knihovnu Aspose.Email for .NET. Můžete si jej stáhnout z[tady](https://releases.aspose.com/email/net/).

2. Soukromý klíč DKIM: K podepisování e-mailů budete potřebovat soukromý klíč DKIM. Ujistěte se, že ji máte připravenou. 

## Krok 1: Inicializujte parametry DKIM

```csharp
string privateKeyFile = Path.Combine(RunExamples.GetDataDir_SMTP().Replace("_Send", string.Empty), RunExamples.GetDataDir_SMTP() + "key2.pem");

RSACryptoServiceProvider rsa = PemReader.GetPrivateKey(privateKeyFile);
DKIMSignatureInfo signInfo = new DKIMSignatureInfo("test", "yandex.ru");
signInfo.Headers.Add("From");
signInfo.Headers.Add("Subject");
```

V tomto kroku inicializujeme parametry DKIM. Načteme soukromý klíč ze souboru, určíme selektor a doménu a vypíšeme hlavičky, které by měly být součástí podpisu DKIM.

## Krok 2: Vytvořte a připravte e-mail

```csharp
MailMessage mailMessage = new MailMessage("useremail@gmail.com", "test@gmail.com");
mailMessage.Subject = "Signed DKIM message text body";
mailMessage.Body = "This is a text body signed DKIM message";
```

Zde vytvoříme instanci`MailMessage` třídy a nastavte odesílatele, příjemce, předmět a tělo e-mailu.

## Krok 3: Podepište e-mail

```csharp
MailMessage signedMsg = mailMessage.DKIMSign(rsa, signInfo);
```

Nyní podepíšeme e-mail pomocí parametrů DKIM a soukromého klíče, které jsme inicializovali dříve.

## Krok 4: Odešlete podepsaný e-mail

```csharp
try
{
    SmtpClient client = new SmtpClient("smtp.gmail.com", 587, "your.email@gmail.com", "your.password");
    client.Send(signedMsg);                
}
finally
{
    // Čisticí kód, pokud existuje
}
```
 V tomto kroku odešleme podepsaný email pomocí SMTP klienta. Ujistěte se, že vyměníte`"your.email@gmail.com"` a`"your.password"` s vašimi přihlašovacími údaji k Gmailu.

## Kompletní zdrojový kód
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

## Závěr

Podepisování e-mailů pomocí DKIM je zásadním krokem k zajištění bezpečnosti a pravosti vaší e-mailové komunikace. S pomocí Aspose.Email pro .NET a C# můžete snadno implementovat podpisy DKIM do procesu odesílání e-mailů.

---

## Často kladené otázky

### Q1: Co je DKIM a proč je důležitý pro zabezpečení e-mailu?

DKIM je zkratka pro DomainKeys Identified Mail a je důležitý pro zabezpečení e-mailu, protože ověřuje pravost e-mailových zpráv a zabraňuje spoofingu a phishingu.

### Q2: Jak získám soukromý klíč DKIM?

Soukromý klíč DKIM můžete získat prostřednictvím poskytovatele e-mailových služeb nebo jeho vygenerováním pomocí kryptografických nástrojů.

### Otázka 3: Mohu používat Aspose.Email pro .NET s jinými poskytovateli e-mailu kromě Gmailu?

Ano, Aspose.Email pro .NET lze používat s různými poskytovateli e-mailu, nejen s Gmailem.

### Q4: Jaké hlavičky bych měl zahrnout do podpisu DKIM?

Běžná záhlaví, která se mají zahrnout do podpisu DKIM, jsou „Od“, „Předmět“ a jakákoli další záhlaví, která jsou důležitá pro ověřování e-mailů.

### Otázka 5: Je DKIM jedinou metodou pro ověřování e-mailů?

Ne, existují další metody jako SPF a DMARC, které se používají ve spojení s DKIM pro lepší zabezpečení e-mailu.