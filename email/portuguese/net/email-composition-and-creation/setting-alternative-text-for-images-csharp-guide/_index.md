---
title: Configurando texto alternativo para imagens – Guia C#
linktitle: Configurando texto alternativo para imagens – Guia C#
second_title: API de processamento de e-mail Aspose.Email .NET
description: Aprenda a definir texto alternativo para imagens em e-mails usando Aspose.Email for .NET. Garanta a acessibilidade com texto alternativo claro. Documentação e código incluídos.
weight: 15
url: /pt/net/email-composition-and-creation/setting-alternative-text-for-images-csharp-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Configurando texto alternativo para imagens – Guia C#


Este guia orientará você no processo de configuração de texto alternativo para imagens em e-mails usando Aspose.Email for .NET. O texto alternativo, também conhecido como “texto alternativo”, é usado para fornecer uma descrição textual de uma imagem caso ela não possa ser exibida. Aspose.Email for .NET é uma biblioteca poderosa que permite trabalhar com e-mails e anexos em vários formatos. Neste guia, focaremos na configuração de texto alternativo para imagens em mensagens de e-mail usando C#.

## Pré-requisitos

Antes de começar, certifique-se de ter os seguintes pré-requisitos:

1. Visual Studio ou qualquer ambiente de desenvolvimento C# compatível instalado.
2. Biblioteca Aspose.Email para .NET. Você pode usar o Gerenciador de Pacotes NuGet no Visual Studio.

## Etapa 1: crie um novo projeto

1. Inicie o Visual Studio e crie um novo projeto de aplicativo de console C#.

## Etapa 2: Instale Aspose.Email via NuGet

1. Clique com o botão direito em seu projeto no Solution Explorer e selecione “Gerenciar pacotes NuGet”.
2. Procure por “Aspose.Email” e instale a versão mais recente do pacote.

## Etapa 3: adicionar instruções usando

```csharp

using Aspose.Email.Mime;
```

## Etapa 4: carregar e modificar a mensagem de e-mail

1.  Carregue a mensagem de e-mail usando o`MailMessage` aula:

```csharp
MailMessage message = new MailMessage();
message.Subject = "Sample Email with Alternative Text";
message.From = new MailAddress("sender@example.com");
message.To.Add("recipient@example.com");
```

3. Carregue o conteúdo HTML da mensagem de e-mail:

```csharp
var htmlView = AlternateView.CreateAlternateViewFromString("<html><body><img src='cid:logo.jpg' alt='Company Logo'></body></html>", null, "text/html");
```

## Etapa 5: adicionar AlternativeView para texto alternativo às imagens

Adicione htmlview para texto alternativo à imagem como AlternateView na mensagem. 
```csharp
message.AlternateViews.Add(htmlView);
```

## Etapa 6: salve e envie o e-mail

1. Salve a mensagem modificada em um arquivo ou envie-a usando o método desejado:

```csharp
message.Save("output.eml", SaveOptions.DefaultEml);
```

## Conclusão

Neste guia, você aprendeu como definir texto alternativo para imagens em mensagens de e-mail usando Aspose.Email for .NET. Seguindo as etapas descritas acima, você pode garantir que o conteúdo do seu e-mail permaneça acessível e informativo mesmo quando as imagens não puderem ser exibidas.

## Perguntas frequentes

## Como posso baixar a biblioteca Aspose.Email?

Você pode baixar a biblioteca Aspose.Email das versões Aspose ou instalá-la por meio do NuGet Package Manager no Visual Studio.

### Como adiciono imagens como recursos vinculados em um email?

Para adicionar imagens como recursos vinculados em um e-mail, você pode usar o`LinkedResource` aula. Atribua um ID de conteúdo ao recurso vinculado e faça referência a esse ID de conteúdo no corpo HTML usando o comando`cid:` esquema. Para informações detalhadas, consulte o[Documentação do LinkedResource](https://reference.aspose.com/email/net/aspose.email/linkedresource/).
### Onde posso encontrar mais documentação sobre Aspose.Email for .NET?

 Você pode encontrar documentação mais detalhada, tutoriais e exemplos sobre como trabalhar com Aspose.Email for .NET no[Referência de API](https://reference.aspose.com/email/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
