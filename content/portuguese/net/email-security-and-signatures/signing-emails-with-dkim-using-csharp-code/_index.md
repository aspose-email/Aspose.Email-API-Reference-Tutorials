---
title: Assinando e-mails com DKIM usando código C#
linktitle: Assinando e-mails com DKIM usando código C#
second_title: API de processamento de e-mail Aspose.Email .NET
description: Aprenda a proteger e-mails com DKIM usando C# e Aspose.Email para .NET. Guia passo a passo com código-fonte. Aumente a confiança e a autenticidade do e-mail.
type: docs
weight: 11
url: /pt/net/email-security-and-signatures/signing-emails-with-dkim-using-csharp-code/
---

No mundo digital de hoje, garantir a autenticidade e a integridade das comunicações por email é de suma importância. Uma maneira de conseguir isso é usando assinaturas DomainKeys Identified Mail (DKIM). Neste guia passo a passo, exploraremos como assinar e-mails com DKIM usando C# e a poderosa biblioteca Aspose.Email for .NET.

## Introdução ao DKIM

### O que é DKIM?
DKIM significa Correio identificado por DomainKeys. É um método de autenticação de email que permite ao remetente assinar digitalmente um email, fornecendo uma assinatura criptográfica que verifica a autenticidade do email.

### Por que o DKIM é importante?
O DKIM ajuda a prevenir ataques de falsificação e phishing de e-mail, garantindo que os e-mails recebidos sejam de fontes legítimas e não tenham sido adulterados durante o trânsito.

## Pré-requisitos

Antes de começarmos, certifique-se de ter os seguintes pré-requisitos em vigor:

1.  Aspose.Email for .NET: Certifique-se de ter a biblioteca Aspose.Email for .NET instalada em seu projeto. Você pode baixá-lo em[aqui](https://releases.aspose.com/email/net/).

2. Chave privada DKIM: você precisará de uma chave privada DKIM para assinar seus e-mails. Certifique-se de tê-lo pronto. 

## Etapa 1: inicializar os parâmetros DKIM

```csharp
string privateKeyFile = Path.Combine(RunExamples.GetDataDir_SMTP().Replace("_Send", string.Empty), RunExamples.GetDataDir_SMTP() + "key2.pem");

RSACryptoServiceProvider rsa = PemReader.GetPrivateKey(privateKeyFile);
DKIMSignatureInfo signInfo = new DKIMSignatureInfo("test", "yandex.ru");
signInfo.Headers.Add("From");
signInfo.Headers.Add("Subject");
```

Nesta etapa, inicializamos os parâmetros DKIM. Carregamos a chave privada do arquivo, especificamos o seletor e o domínio e listamos os cabeçalhos que devem ser incluídos na assinatura DKIM.

## Etapa 2: criar e preparar o e-mail

```csharp
MailMessage mailMessage = new MailMessage("useremail@gmail.com", "test@gmail.com");
mailMessage.Subject = "Signed DKIM message text body";
mailMessage.Body = "This is a text body signed DKIM message";
```

Aqui, criamos uma instância do`MailMessage` class e defina o remetente, o destinatário, o assunto e o corpo do e-mail.

## Etapa 3: assine o e-mail

```csharp
MailMessage signedMsg = mailMessage.DKIMSign(rsa, signInfo);
```

Agora, assinamos o e-mail usando os parâmetros DKIM e a chave privada que inicializamos anteriormente.

## Etapa 4: envie o e-mail assinado

```csharp
try
{
    SmtpClient client = new SmtpClient("smtp.gmail.com", 587, "your.email@gmail.com", "your.password");
    client.Send(signedMsg);                
}
finally
{
    // Código de limpeza, se houver
}
```
 Nesta etapa, enviamos o email assinado através de um cliente SMTP. Certifique-se de substituir`"your.email@gmail.com"` e`"your.password"` com suas credenciais do Gmail.

## Completar código-fonte
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

## Conclusão

Assinar emails com DKIM é uma etapa crucial para garantir a segurança e autenticidade de suas comunicações por email. Com a ajuda do Aspose.Email para .NET e C#, você pode implementar facilmente assinaturas DKIM em seu processo de envio de e-mail.

---

## perguntas frequentes

### P1: O que é DKIM e por que ele é importante para a segurança do e-mail?

DKIM significa DomainKeys Identified Mail e é importante para a segurança do e-mail porque verifica a autenticidade das mensagens de e-mail, evitando falsificação e phishing.

### P2: Como obtenho uma chave privada DKIM?

Você pode obter uma chave privada DKIM através do seu provedor de serviços de e-mail ou gerando uma usando ferramentas criptográficas.

### Q3: Posso usar o Aspose.Email for .NET com outros provedores de e-mail além do Gmail?

Sim, o Aspose.Email for .NET pode ser usado com vários provedores de e-mail, não se limitando ao Gmail.

### P4: Quais cabeçalhos devo incluir na assinatura DKIM?

Os cabeçalhos comuns a serem incluídos na assinatura DKIM são “De”, “Assunto” e quaisquer outros cabeçalhos que sejam importantes para autenticação de e-mail.

### P5: O DKIM é o único método para autenticação de e-mail?

Não, existem outros métodos como SPF e DMARC que são usados em conjunto com DKIM para aumentar a segurança de e-mail.