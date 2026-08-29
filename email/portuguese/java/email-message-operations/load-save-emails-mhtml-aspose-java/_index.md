---
date: '2026-08-27'
description: Aprenda a carregar arquivos MSG e convertê-los para MHTML com Aspose.Email
  para Java, incluindo configurações personalizadas de fuso horário e dicas de processamento
  em lote de e‑mail.
keywords:
- how to load msg
- Aspose.Email Java
- convert MSG to MHTML
- email timezone offset
lastmod: '2026-08-27'
og_description: Aprenda a carregar arquivos msg e exportá‑los como MHTML usando Aspose.Email
  para Java. Inclui tratamento de fuso horário e dicas de processamento em lote.
og_image_alt: Guide to loading MSG files and saving as MHTML with Aspose.Email for
  Java
og_title: Como carregar msg e salvar como MHTML com Aspose.Email para Java
schemas:
- author: Aspose
  dateModified: '2026-08-27'
  description: Learn how to load MSG files and convert them to MHTML with Aspose.Email
    for Java, including custom timezone settings and batch email processing tips.
  headline: How to load msg and save as MHTML using Aspose.Email for Java
  type: TechArticle
- description: Learn how to load MSG files and convert them to MHTML with Aspose.Email
    for Java, including custom timezone settings and batch email processing tips.
  name: How to load msg and save as MHTML using Aspose.Email for Java
  steps:
  - name: '**Reuse the license** – call `new License().setLicense(...)` once at application
      startup.'
    text: '**Reuse the license** – call `new License().setLicense(...)` once at application
      startup.'
  - name: '**Use try‑with‑resources** for automatic cleanup of streams.'
    text: '**Use try‑with‑resources** for automatic cleanup of streams.'
  - name: '**Log failures** to a separate file so you can retry problematic messages
      later.'
    text: '**Log failures** to a separate file so you can retry problematic messages
      later.'
  - name: '**Consider parallelism** with `ForkJoinPool` for large batches, but ensure
      each thread uses its own `MailMessage` instance.'
    text: '**Consider parallelism** with `ForkJoinPool` for large batches, but ensure
      each thread uses its own `MailMessage` instance.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Email supports EML, MHT, EMLX, and several other formats,
      totaling over 30 input types.
    question: Can I load emails from formats other than .msg?
  - answer: Use the streaming APIs (`MailMessage.load(InputStream, ...)`) to read
      and write data in chunks, which keeps memory consumption under 50 MB even for
      500‑page messages.
    question: How can I handle very large email files efficiently?
  - answer: Absolutely. You can add, remove, or replace attachments via the `msg.getAttachments()`
      collection, then call `save` to persist changes.
    question: Is it possible to modify attachments within a MailMessage?
  - answer: Pass a negative millisecond value to `setTimeZoneOffset`, e.g., `-3 *
      60 * 60 * 1000` for UTC‑3.
    question: What if my timezone offset is negative (behind UTC)?
  - answer: Yes, provided you have a valid commercial license. The free trial is limited
      to 20 MB per document.
    question: Can I use Aspose.Email in commercial projects?
  type: FAQPage
tags:
- email processing
- Aspose.Email
- Java email conversion
title: Como carregar arquivos msg e salvar como MHTML usando Aspose.Email para Java
url: /pt/java/email-message-operations/load-save-emails-mhtml-aspose-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como carregar msg e salvar como MHTML usando Aspose.Email para Java

## Introdução

Se você precisa **carregar arquivos msg**, ajustar seus carimbos de data/hora e então **converter msg para mhtml**, está no lugar certo. Neste tutorial vamos percorrer o carregamento de um `.msg` e‑mail, aplicar um deslocamento de fuso horário personalizado e salvar o resultado como um arquivo MHTML — tudo com Aspose.Email para Java. Seja lidando com uma única mensagem ou um pipeline de **processamento de e‑mail em lote**, estas etapas lhe darão uma base sólida para arquivamento e migração confiáveis.

**O que você aprenderá**
- Como carregar um `MailMessage` a partir de um arquivo `.msg`.
- Como definir um fuso horário personalizado e a data atual.
- Como salvar a mensagem como MHTML com formatação precisa.
- Dicas para escalar a abordagem para cenários em lote.

Pronto para melhorar seu fluxo de trabalho de e‑mail? Vamos preparar o ambiente primeiro.

## Respostas rápidas
- **Qual é a biblioteca principal?** Aspose.Email para Java.
- **Posso carregar MSG e exportar para MHTML em um único passo?** Não, você carrega, ajusta e então salva.
- **Preciso de uma licença para produção?** Sim, é necessária uma licença válida do Aspose.Email.
- **O tratamento de fuso horário é suportado?** Sim, via `setTimeZoneOffset`.
- **Isso pode ser usado em processamento em lote?** Absolutamente — envolva as etapas em um loop.

## O que é Aspose.Email para Java?

Aspose.Email para Java é uma API abrangente que permite criar, ler, converter e manipular mensagens de e‑mail sem a necessidade do Microsoft Outlook. Ela suporta mais de 30 formatos de e‑mail e pode processar mensagens com centenas de páginas mantendo o uso de memória baixo.

## Por que converter MSG para MHTML?

Converter arquivos MSG para MHTML fornece uma representação amigável para a web, em um único arquivo, que pode ser aberta em qualquer navegador moderno. Esse formato preserva o estilo original, imagens incorporadas e anexos, tornando‑o ideal para **arquivamento legal**, **compartilhamento multiplataforma** e **incorporação de e‑mails em páginas web ou documentação**.

## Pré-requisitos

Antes de começarmos, certifique‑se de que você tem o seguinte:

### Bibliotecas e dependências necessárias
- **Aspose.Email para Java** versão 25.4 (classificador jdk16) – a biblioteca suporta **mais de 50** formatos de e‑mail de entrada e saída.
- Conhecimento básico de Java.
- Uma IDE como IntelliJ IDEA ou Eclipse.

### Requisitos de configuração do ambiente
- JDK 16 ou superior instalado.
- Maven para gerenciamento de dependências.

## Configurando Aspose.Email para Java

Para adicionar a biblioteca a um projeto Maven, inclua a seguinte dependência:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Etapas de aquisição de licença

Comece com um **teste gratuito** ou obtenha uma **licença temporária** para avaliar todas as capacidades da biblioteca sem limitações. Para uso a longo prazo, considere adquirir uma licença:

- [Free Trial](https://releases.aspose.com/email/java/)
- [Temporary License](https://purchase.aspose.com/temporary-license/)
- [Purchase License](https://purchase.aspose.com/buy)

### Inicialização básica

A classe `License` registra sua licença Aspose.Email para desbloquear todos os recursos.  
Depois de adicionar a dependência, inicialize a licença no seu código Java:

```java
import com.aspose.email.License;

License license = new License();
license.setLicense("Aspose.Email.lic");
```
```java
import com.aspose.email.License;

License license = new License();
license.setLicense("path_to_your_license_file.lic");
```

## Como carregar msg e salvar como MHTML?

Carregue o arquivo MSG, ajuste o carimbo de data/hora e salve‑o como MHTML em três etapas simples. Primeiro, instancie um `MailMessage` a partir do arquivo MSG usando `MsgLoadOptions`. Em seguida, defina o deslocamento de fuso horário desejado com `setTimeZoneOffset`. Por fim, configure `MhtSaveOptions` e chame `save` para gerar o arquivo MHTML.

### Recurso 1: carregando um MailMessage a partir de um arquivo

A classe `MailMessage` representa uma mensagem de e‑mail com cabeçalhos, corpo e anexos.

```java
import com.aspose.email.MailMessage;
import com.aspose.email.MsgLoadOptions;
```
```java
import com.aspose.email.MailMessage;
import com.aspose.email.MsgLoadOptions;
```

```java
MsgLoadOptions loadOptions = new MsgLoadOptions();
MailMessage msg = MailMessage.load("sample.msg", loadOptions);
```
```java
String filename = "YOUR_DOCUMENT_DIRECTORY/MSG file with RTF Formatting.msg";
MailMessage msg = MailMessage.load(filename, new MsgLoadOptions());
```

`MsgLoadOptions` permite controlar como o arquivo MSG é analisado; as configurações padrão funcionam na maioria dos cenários.

### Recurso 2: definindo a data atual e o deslocamento de fuso horário personalizado

O objeto `Date` contém o carimbo de data/hora que será escrito no cabeçalho **Date** do e‑mail.

```java
java.util.Date now = new java.util.Date();
msg.setDate(now);
```
```java
import java.util.Date;

msg.setDate(new Date());
```

O deslocamento é expresso em milissegundos; para UTC+5 você passa `5 * 60 * 60 * 1000`.

```java
int utcPlusFive = 5 * 60 * 60 * 1000;
msg.setTimeZoneOffset(utcPlusFive);
```
```java
msg.setTimeZoneOffset(5 * 60 * 60 * 1000); // 5 hours ahead of UTC in milliseconds.
```

### Recurso 3: salvando um MailMessage como um arquivo MHTML

`MhtSaveOptions` define como o e‑mail é empacotado em um arquivo MHTML, preservando imagens embutidas e anexos.

```java
import com.aspose.email.MhtSaveOptions;
MhtSaveOptions saveOptions = new MhtSaveOptions();
saveOptions.setWriteHeader(true);
```
```java
import com.aspose.email.MhtSaveOptions;
import com.aspose.email.MhtFormatOptions;

MhtSaveOptions mhtOptions = new MhtSaveOptions();
mhtOptions.setMhtFormatOptions(MhtFormatOptions.WriteHeader);
```

```java
msg.save("output.mhtml", saveOptions);
```
```java
msg.save("YOUR_OUTPUT_DIRECTORY/ExportToMHTWithCustomTimezone_out.mhtml", mhtOptions);
```

O arquivo `.mhtml` resultante mantém a formatação original, imagens e anexos, tornando‑o uma cópia visual fiel do MSG original.

## Como definir um deslocamento de fuso horário personalizado?

Você pode modificar o fuso horário chamando `setTimeZoneOffset` na instância `MailMessage`. O método espera um deslocamento em milissegundos, permitindo valores positivos (leste do UTC) e negativos (oeste do UTC). Por exemplo, UTC‑3 é `-3 * 60 * 60 * 1000`.

## Como processar arquivos MSG em lote?

Envolva o fluxo de trabalho de três etapas dentro de um loop que itere sobre um diretório de arquivos `.msg`. Reutilize uma única instância `License` para evitar I/O repetido e descarte cada `MailMessage` após a gravação para manter o uso de memória baixo.

```java
File folder = new File("msg_folder");
for (File file : folder.listFiles((dir, name) -> name.toLowerCase().endsWith(".msg"))) {
    MailMessage msg = MailMessage.load(file.getAbsolutePath(), new MsgLoadOptions());
    // set date & timezone as shown earlier
    msg.save(file.getName().replace(".msg", ".mhtml"), new MhtSaveOptions());
    msg.dispose(); // releases native resources
}
```

### Dicas para processamento em lote
1. **Reutilize a licença** – chame `new License().setLicense(...)` uma vez na inicialização da aplicação.
2. **Use try‑with‑resources** para limpeza automática de streams.
3. **Registre falhas** em um arquivo separado para que você possa reprocessar mensagens problemáticas posteriormente.
4. **Considere paralelismo** com `ForkJoinPool` para lotes grandes, mas garanta que cada thread use sua própria instância `MailMessage`.

## Problemas comuns e soluções

- **Picos de memória com arquivos MSG enormes** – habilite streaming usando `MailMessage.load(InputStream, MsgLoadOptions)` e processe o stream em blocos.
- **Carimbos de data/hora incorretos** – verifique se o relógio do sistema está configurado para UTC antes de aplicar os deslocamentos, ou passe explicitamente uma instância `java.util.Calendar`.
- **Anexos ausentes no MHTML** – assegure que `MhtSaveOptions.setWriteHeader(true)` esteja definido; isso incorpora os anexos como recursos `cid:`.

## Perguntas frequentes

**Q: Posso carregar e‑mails de formatos diferentes de .msg?**  
A: Sim, Aspose.Email suporta EML, MHT, EMLX e vários outros formatos, totalizando mais de 30 tipos de entrada.

**Q: Como posso lidar com arquivos de e‑mail muito grandes de forma eficiente?**  
A: Use as APIs de streaming (`MailMessage.load(InputStream, ...)`) para ler e gravar dados em blocos, mantendo o consumo de memória abaixo de 50 MB mesmo para mensagens de 500 páginas.

**Q: É possível modificar anexos dentro de um MailMessage?**  
A: Absolutamente. Você pode adicionar, remover ou substituir anexos via a coleção `msg.getAttachments()`, e então chamar `save` para persistir as alterações.

**Q: E se o meu deslocamento de fuso horário for negativo (atrás do UTC)?**  
A: Passe um valor negativo em milissegundos para `setTimeZoneOffset`, por exemplo, `-3 * 60 * 60 * 1000` para UTC‑3.

**Q: Posso usar Aspose.Email em projetos comerciais?**  
A: Sim, desde que você possua uma licença comercial válida. O teste gratuito é limitado a 20 MB por documento.

**Q: Como processar milhares de arquivos MSG sem ficar sem memória?**  
A: Processe os arquivos em lotes, libere cada `MailMessage` após a gravação e utilize o padrão `try‑with‑resources` do Java para limpeza automática.

## Recursos
- [documentação](https://reference.aspose.com/email/java/)
- [Documentação](https://reference.aspose.com/email/java/)
- [Baixar Biblioteca](https://releases.aspose.com/email/java/)
- [Comprar Licença](https://purchase.aspose.com/buy)
- [Teste Gratuito](https://releases.aspose.com/email/java/)
- [Licença Temporária](https://purchase.aspose.com/temporary-license/)
- [Fórum de Suporte](https://forum.aspose.com/c/email/10)

---

**Última atualização:** 2026-08-27  
**Testado com:** Aspose.Email para Java 25.4 (classificador jdk16)  
**Autor:** Aspose

## Tutoriais Relacionados

- [Como carregar e analisar arquivos Outlook MSG usando Aspose.Email para Java: Um guia abrangente](/email/java/mapi-operations/outlook-msg-aspose-email-java-guide/)
- [Maven Aspose.Email para Java: Salvar e‑mails como arquivos MHT](/email/java/email-message-operations/save-emails-as-mht-using-aspose-email-java/)
- [Como extrair anexos de arquivos msg usando Aspose.Email para Java](/email/java/advanced-email-attachments/extracting-attachments-from-email-messages/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}