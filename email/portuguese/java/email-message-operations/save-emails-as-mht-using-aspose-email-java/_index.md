---
date: '2026-09-22'
description: Aprenda como usar uma licença Aspose.Email com Maven para salvar e‑mails
  como arquivos MHT em Java. Inclui configuração, modelos personalizados e manipulação
  de eventos de calendário.
keywords:
- aspose email license
- how to save mht
- how to convert mht
- maven dependency aspose email
lastmod: '2026-09-22'
og_description: Aprenda como usar uma licença Aspose.Email com Maven para salvar e‑mails
  como arquivos MHT em Java. Inclui configuração, modelos personalizados e suporte
  a calendário.
og_image_alt: 'Tutorial: saving emails as MHT using Aspose.Email for Java with a license'
og_title: Como usar uma licença Aspose.Email para salvar e‑mails como MHT
schemas:
- author: Aspose
  dateModified: '2026-09-22'
  description: Learn how to use an Aspose.Email license with Maven to save emails
    as MHT files in Java. Includes setup, custom templates, and calendar event handling.
  headline: How to use an Aspose.Email license to save emails as MHT
  type: TechArticle
- description: Learn how to use an Aspose.Email license with Maven to save emails
    as MHT files in Java. Includes setup, custom templates, and calendar event handling.
  name: How to use an Aspose.Email license to save emails as MHT
  steps:
  - name: '**Free trial** – download from [Releases](https://releases.aspose.com/email/java/)
      and explore features without limitations.'
    text: '**Free trial** – download from [Releases](https://releases.aspose.com/email/java/)
      and explore features without limitations.'
  - name: '**Temporary license** – request a fully functional version via the [Temporary
      License Page](https://purchase.aspose.com/temporary-license/).'
    text: '**Temporary license** – request a fully functional version via the [Temporary
      License Page](https://purchase.aspose.com/temporary-license/).'
  - name: '**Purchase** – obtain a permanent license for long‑term projects.'
    text: '**Purchase** – obtain a permanent license for long‑term projects.'
  type: HowTo
- questions:
  - answer: Configure `MhtSaveOptions` to embed attachments; the library automatically
      includes them in the MHT package.
    question: How do I handle attachments when saving emails as MHT?
  - answer: Yes, use `MhtFormatOptions.WriteHeader` and provide custom template strings
      for each header field.
    question: Can I customize email headers in the output MHT file?
  - answer: A JDK 16 or higher is required. The library works with any IDE that supports
      Maven projects.
    question: What are the system requirements for using Aspose.Email Java?
  - answer: While MHT typically contains the full message, you can manipulate `MailMessage`
      properties to exclude unwanted sections before saving.
    question: Is it possible to save only specific parts of an email message?
  - answer: Verify file paths, ensure the license is correctly applied, and consult
      the Aspose.Email [support forum](https://forum.aspose.com/c/email/10) for detailed
      assistance.
    question: How can I troubleshoot issues with email loading or saving?
  type: FAQPage
tags:
- aspose email
- mht conversion
- java email processing
- maven
title: Como usar uma licença Aspose.Email para salvar e‑mails como MHT
url: /pt/java/email-message-operations/save-emails-as-mht-using-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como usar uma licença Aspose.Email para salvar e‑mails como MHT

## Introdução

Gerenciar dados de e‑mail de forma eficiente pode ser desafiador, especialmente quando se trata de compartilhamento e arquivamento. Neste guia, mostraremos **como salvar arquivos MHT usando Maven Aspose.Email para Java com uma licença Aspose.Email**, permitindo converter e‑mails para MHT com modelos personalizados e manter os eventos de calendário intactos. Você sairá com uma solução pronta‑para‑executar que funciona em qualquer ambiente Java 16+ e cumpre os requisitos de licenciamento para uso em produção.

## Respostas rápidas
- **Qual biblioteca eu preciso?** Maven Aspose.Email para Java (v25.4+).  
- **Qual formato é produzido?** Um arquivo MHT (MHTML) que agrupa HTML, imagens e dados de calendário.  
- **Posso personalizar o cabeçalho?** Sim – use `MhtFormatOptions` e strings de modelo.  
- **Preciso de uma licença?** Uma licença Aspose.Email é necessária para produção; um teste gratuito funciona para avaliação.  
- **Qual versão do Java é necessária?** JDK 16 ou posterior.  

## O que é Maven Aspose.Email para Java?

Maven Aspose.Email para Java é uma biblioteca que fornece uma API abrangente para criar, ler, converter e manipular mensagens de e‑mail diretamente a partir de código Java. Ela suporta mais de 30 formatos de e‑mail—including MSG, EML e MHT—permitindo lidar virtualmente com qualquer arquivo de e‑mail que você encontrar.

## Por que converter e‑mails para MHT?

Arquivos MHT incorporam todos os recursos (HTML, imagens, dados de calendário) em um único arquivo, tornando‑os visualizáveis instantaneamente em qualquer navegador moderno sem ativos externos. Esse formato preserva a aparência original, suporta eventos recorrentes de calendário e reduz o risco de anexos ausentes durante o compartilhamento.

## Pré‑requisitos
- **Aspose.Email for Java** (artefato Maven `com.aspose:aspose-email:25.4` com classificador `jdk16`).  
- **Maven** instalado e configurado na sua máquina.  
- **JDK 16+** (a biblioteca tem como alvo Java 16).  
- Um arquivo de licença **Aspose.Email** válido para uso em produção.  
- Conhecimento básico de Java (manipulação de arquivos, dependências Maven).

## Configurando Aspose.Email para Java

### Dependência Maven

Adicione a seguinte dependência ao seu arquivo `pom.xml`:

```xml
<dependency>
  <groupId>com.aspose</groupId>
  <artifactId>aspose-email</artifactId>
  <version>25.4</version>
  <classifier>jdk16</classifier>
</dependency>
```

### Aquisição de licença

Aspose oferece um teste gratuito para explorar suas capacidades, além de opções para comprar uma licença ou obter uma licença temporária.

1. **Teste gratuito** – baixe em [Releases](https://releases.aspose.com/email/java/) e explore os recursos sem limitações.  
2. **Licença temporária** – solicite uma versão totalmente funcional através da [Página de Licença Temporária](https://purchase.aspose.com/temporary-license/).  
3. **Compra** – obtenha uma licença permanente para projetos de longo prazo.

### Inicialização básica

Depois de instalado, inicialize a biblioteca em sua aplicação Java:

```java
import com.aspose.email.License;

License license = new License();
license.setLicense("path/to/your/license/file");
```

Com estas etapas concluídas, você está pronto para usar os recursos do Aspose.Email para manipulação eficiente de e‑mails.

## Guia de implementação

### Recurso 1: carregar MailMessage

#### Visão geral

`MailMessage` é o objeto central do Aspose.Email que representa um e‑mail, incluindo seus cabeçalhos, corpo, anexos e eventos de calendário.

#### Passo a passo

**Importar classes necessárias**

```java
import com.aspose.email.MailMessage;
```

**Carregar e‑mail a partir de arquivo**

```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY" + "/email/";
MailMessage msg = MailMessage.load(dataDir + "Meeting with Recurring Occurrences.msg");
```

Este trecho carrega uma mensagem de e‑mail localizada no diretório especificado.

### Recurso 2: configurar MhtSaveOptions

#### Visão geral

`MhtSaveOptions` configura como o Aspose.Email salva um `MailMessage` como um arquivo MHT, controlando flags de formato, modelos e incorporação de recursos. A configuração correta permite incorporar cabeçalhos, renderizar eventos de calendário e incorporar todas as imagens.

#### Passo a passo

**Importar classes necessárias**

```java
import com.aspose.email.MhtSaveOptions;
import com.aspose.email.MhtFormatOptions;
import com.aspose.email.MhtTemplateName;
```

**Definir opções de salvamento e modelos**

```java
MhtSaveOptions options = new MhtSaveOptions();
options.setMhtFormatOptions(MhtFormatOptions.WriteHeader | MhtFormatOptions.RenderCalendarEvent);

// Customize templates for email properties
for (Map.Entry<MhtTemplateName, String> entry : options.getFormatTemplates().entrySet()) {
    switch (entry.getKey()) {
        case START:
            options.getFormatTemplates().set_Item(MhtTemplateName.START,
                    "<span class='headerLineTitle'>Start:</span><span class='headerLineText'>{0}</span><br/>");
            break;
        // Add other cases similarly...
    }
}

// Ensure entries are added if absent
options.getFormatTemplates().addIfAbsent(MhtTemplateName.START,
            "<span class='headerLineTitle'>Start:</span><span class='headerLineText'>{0}</span><br/>");
```

Esta configuração define cabeçalhos e a renderização de eventos de calendário na saída MHT.

### Recurso 3: salvar MailMessage como MHT

#### Visão geral

Salvar o `MailMessage` configurado como um arquivo MHT grava um documento único e autocontido que pode ser aberto em navegadores ou clientes de e‑mail. O método `save` respeita as opções definidas anteriormente.

#### Passo a passo

**Importar classes necessárias**

```java
import com.aspose.email.MailMessage;
import com.aspose.email.MhtSaveOptions;
```

**Salvar mensagem de e‑mail**

```java
msg.save("YOUR_OUTPUT_DIRECTORY" + "Meeting with Recurring Occurrences_out.mhtml", options);
```

Este comando grava o e‑mail em um arquivo MHT, pronto para compartilhamento ou arquivamento.

## Aplicações práticas
- **Arquivamento de e‑mail** – Converta e armazene e‑mails importantes em um formato web‑amigável para retenção de longo prazo.  
- **Documentação legal** – Use arquivos MHT como parte de evidências legais onde a fidelidade do e‑mail é necessária.  
- **Compartilhamento multiplataforma** – Compartilhe e‑mails entre plataformas sem problemas de compatibilidade, pois o MHT agrupa tudo em um único arquivo.  

Integrar com outros sistemas—como CRM ou ferramentas de gerenciamento de projetos—pode melhorar a colaboração ao incorporar dados críticos de e‑mail diretamente nos fluxos de trabalho.

## Considerações de desempenho
Aspose.Email para Java pode processar arquivos de até 500 MB sem carregar todo o documento na memória, e normalmente converte um e‑mail de 100 páginas com imagens incorporadas em menos de 2 segundos em um servidor padrão. Para manter sua aplicação responsiva, gerencie o uso de memória cuidadosamente e agrupe operações de I/O sempre que possível.

## Problemas comuns e soluções
`MhtFormatOptions` é uma enumeração que controla quais elementos (cabeçalhos, recursos, eventos de calendário) são incluídos ao salvar uma mensagem como MHT.

| Problema | Causa | Correção |
|----------|-------|----------|
| **NullPointerException ao `msg.save`** | Caminho de saída incorreto | Verifique se `YOUR_OUTPUT_DIRECTORY` existe e tem permissão de gravação. |
| **Imagens ausentes no MHT** | `MhtFormatOptions` não configurado para incorporar recursos | Adicione `MhtFormatOptions.EmbedResources` à flag de opções. |
| **Eventos de calendário não renderizados** | Flag `RenderCalendarEvent` omitida | Garanta `options.setMhtFormatOptions(MhtFormatOptions.WriteHeader \| MhtFormatOptions.RenderCalendarEvent);` |

## Perguntas frequentes

**Q: Como lidar com anexos ao salvar e‑mails como MHT?**  
A: Configure `MhtSaveOptions` para incorporar anexos; a biblioteca inclui-os automaticamente no pacote MHT.

**Q: Posso personalizar os cabeçalhos de e‑mail no arquivo MHT de saída?**  
A: Sim, use `MhtFormatOptions.WriteHeader` e forneça strings de modelo personalizadas para cada campo de cabeçalho.

**Q: Quais são os requisitos de sistema para usar Aspose.Email Java?**  
A: É necessário JDK 16 ou superior. A biblioteca funciona com qualquer IDE que suporte projetos Maven.

**Q: É possível salvar apenas partes específicas de uma mensagem de e‑mail?**  
A: Embora o MHT normalmente contenha a mensagem completa, você pode manipular as propriedades de `MailMessage` para excluir seções indesejadas antes de salvar.

**Q: Como solucionar problemas de carregamento ou salvamento de e‑mail?**  
A: Verifique os caminhos dos arquivos, assegure que a licença foi aplicada corretamente e consulte o fórum de suporte do Aspose.Email [support forum](https://forum.aspose.com/c/email/10) para assistência detalhada.

**Q: A biblioteca suporta converter outros formatos (EML, MSG) para MHT?**  
A: Absolutamente. `MailMessage.load` pode ler EML, MSG e outros formatos suportados, após o que você pode salvá‑los como MHT usando as mesmas opções.

## Recursos
- **Documentação**: Para uma exploração mais profunda de todas as funcionalidades, visite a [Aspose Email Java Documentation](https://reference.aspose.com/email/java/).  
- **Download**: Comece seu teste gratuito baixando em [Releases](https://releases.aspose.com/email/java/).  
- **Compra**: Explore opções de compra na [Official Purchase Page](https://purchase.aspose.com/buy) para uso de longo prazo.  
- **Teste gratuito e licença temporária**: Acesse recursos abrangentes durante um teste gratuito ou obtenha uma licença temporária através destes links:  
  - [Free Trial](https://releases.aspose.com/email/java/)  
  - [Temporary License](https://purchase.aspose.com/temporary-license/)

Explore, implemente e transforme seu gerenciamento de e‑mails com Aspose.Email para Java hoje!

**Última atualização:** 2026-09-22  
**Testado com:** Aspose.Email para Java 25.4 (classificador jdk16)  
**Autor:** Aspose  

## Tutoriais relacionados

- [Dominando Aspose.Email para Java: Guia de Licença e Manipulação de E‑mail](/email/java/getting-started/mastering-aspose-email-java-license-email-handling/)
- [Como Converter MSG para MHT Usando Aspose.Email para Java – Guia Passo a Passo](/email/java/email-conversion-rendering/convert-mapi-messages-to-mht-aspose-email-java/)
- [Como Salvar E‑mails MSG com Aspose.Email para Java](/email/java/email-message-operations/aspose-email-java-create-save-emails/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}