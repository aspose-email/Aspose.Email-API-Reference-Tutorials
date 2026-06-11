---
date: '2026-02-27'
description: Aprenda a carregar arquivos MSG e convertê-los para MHTML com Aspose.Email
  para Java, incluindo configurações de fuso horário personalizadas e dicas de processamento
  em lote de e‑mails.
keywords:
- Aspose.Email for Java
- load emails in MHTML format
- custom timezone settings
title: Como Carregar MSG e Salvar como MHTML Usando Aspose.Email para Java
url: /pt/java/email-message-operations/load-save-emails-mhtml-aspose-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Como Carregar MSG e Salvar como MHTML Usando Aspose.Email para Java

## Introdução

Se você precisa **como carregar msg** arquivos, ajustar seus timestamps e então **converter msg para mhtml**, está no lugar certo. Neste tutorial vamos percorrer o carregamento de um e‑mail `.msg`, aplicar um deslocamento de fuso horário personalizado e salvar o resultado como um arquivo MHTML — tudo com Aspose.Email para Java. Seja lidando com uma única mensagem ou um pipeline de **processamento em lote de e‑mail**, estas etapas lhe darão uma base sólida.

**O que você aprenderá**
- Como carregar um `MailMessage` a partir de um arquivo `.msg`.
- Como definir um fuso horário personalizado e a data atual.
- Como salvar a mensagem como MHTML com formatação precisa.
- Dicas para escalar a abordagem para cenários em lote.

Pronto para melhorar seu fluxo de trabalho de e‑mail? Vamos preparar o ambiente primeiro.

## Respostas Rápidas
- **Qual é a biblioteca principal?** Aspose.Email para Java.
- **Posso carregar MSG e exportar para MHTML em um único passo?** Não, você carrega, ajusta e então salva.
- **Preciso de licença para produção?** Sim, é necessária uma licença válida do Aspose.Email.
- **O tratamento de fuso horário é suportado?** Sim, via `setTimeZoneOffset`.
- **Isso pode ser usado em processamento em lote?** Absolutamente – envolva as etapas em um loop.

## Pré-requisitos

Antes de começarmos, certifique-se de que você tem o seguinte:

### Bibliotecas e Dependências Necessárias
- **Aspose.Email for Java** versão 25.4 (classificador jdk16)
- Conhecimento básico de Java.
- Uma IDE como IntelliJ IDEA ou Eclipse.

### Requisitos de Configuração do Ambiente
- JDK 16 ou mais recente instalado.
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

### Etapas de Aquisição de Licença

Comece com um **teste gratuito** ou obtenha uma **licença temporária** para avaliar todas as capacidades da biblioteca sem limitações. Para uso a longo prazo, considere comprar uma licença:

- [Free Trial](https://releases.aspose.com/email/java/)
- [Temporary License](https://purchase.aspose.com/temporary-license/)
- [Purchase License](https://purchase.aspose.com/buy)

### Inicialização Básica

Depois de adicionar a dependência, inicialize a licença no seu código Java:

```java
import com.aspose.email.License;

License license = new License();
license.setLicense("path_to_your_license_file.lic");
```

## Guia de Implementação

Dividiremos a implementação em três recursos claros.

### Recurso 1: Carregando um MailMessage a partir de um Arquivo

#### Visão Geral
Carregar um arquivo `.msg` fornece acesso programático completo ao conteúdo do e‑mail, anexos e metadados.

#### Passo a Passo

**Importe as classes necessárias**

```java
import com.aspose.email.MailMessage;
import com.aspose.email.MsgLoadOptions;
```

**Carregue o e‑mail**

```java
String filename = "YOUR_DOCUMENT_DIRECTORY/MSG file with RTF Formatting.msg";
MailMessage msg = MailMessage.load(filename, new MsgLoadOptions());
```

`MsgLoadOptions` permite controlar como o arquivo MSG é interpretado; as configurações padrão funcionam na maioria dos cenários.

### Recurso 2: Definindo a Data Atual e Deslocamento de Fuso Horário Personalizado

#### Visão Geral
Timestamps precisos são essenciais quando você lida com usuários em diferentes regiões.

**Defina a data atual**

```java
import java.util.Date;

msg.setDate(new Date());
```

**Aplique um deslocamento de fuso horário personalizado (ex.: UTC+5)**

```java
msg.setTimeZoneOffset(5 * 60 * 60 * 1000); // 5 hours ahead of UTC in milliseconds.
```

O deslocamento é expresso em milissegundos, portanto você também pode passar valores negativos para zonas a oeste do UTC.

### Recurso 3: Salvando um MailMessage como Arquivo MHTML

#### Visão Geral
MHTML agrupa conteúdo HTML e recursos incorporados em um único arquivo, perfeito para arquivamento ou compartilhamento.

**Configure as opções de salvamento**

```java
import com.aspose.email.MhtSaveOptions;
import com.aspose.email.MhtFormatOptions;

MhtSaveOptions mhtOptions = new MhtSaveOptions();
mhtOptions.setMhtFormatOptions(MhtFormatOptions.WriteHeader);
```

**Salve o e‑mail**

```java
msg.save("YOUR_OUTPUT_DIRECTORY/ExportToMHTWithCustomTimezone_out.mhtml", mhtOptions);
```

O arquivo `.mhtml` resultante mantém a formatação original, imagens e anexos.

## Por que Converter MSG para MHTML?

Converter arquivos MSG para MHTML fornece uma representação amigável à web, em um único arquivo, que pode ser aberto em qualquer navegador moderno. Isso é especialmente útil para:

- **Arquivamento legal** onde uma cópia visual fiel é necessária.
- **Compartilhamento multiplataforma** sem necessidade do Outlook.
- **Incorporação de e‑mails** em páginas web ou documentação.

## Dicas para Processamento de E‑mail em Lote

Se você precisar de **processamento de e‑mail em lote**, envolva as etapas de carregamento, ajuste de fuso horário e salvamento dentro de um loop que itere sobre um diretório de arquivos `.msg`. Lembre‑se de:

1. Reutilizar uma única instância de `License` para evitar sobrecarga.
2. Liberar recursos após cada iteração (`msg.dispose()` se aplicável).
3. Registrar quaisquer falhas em um arquivo separado para revisão posterior.

## Aplicações Práticas

1. **Arquivamento de E‑mail:** Preserve comunicações em um formato portátil para conformidade.
2. **Agendamento Global:** Ajuste timestamps para um fuso horário unificado antes de enviar notificações.
3. **Integração com CRM:** Importe automaticamente e‑mails arquivados para um sistema CRM como anexos MHTML.

## Considerações de Performance

- **Gerenciamento de Memória:** Processar grandes lotes em blocos para manter o uso de memória baixo.
- **Otimização de I/O:** Use streams bufferizados se estiver lendo/escrevendo muitos arquivos.
- **Execução Paralela:** Considere o `ForkJoinPool` do Java para processamento paralelo, mas garanta a segurança de threads dos objetos Aspose.

## Conclusão

Agora você sabe **como carregar arquivos msg**, aplicar deslocamentos de fuso horário personalizados e **converter msg para mhtml** usando Aspose.Email para Java. Essas técnicas podem ser escaladas para lidar com tarefas de **processamento de e‑mail em lote**, oferecendo uma solução robusta para arquivamento, migração e automação de e‑mails.

**Próximos Passos**  
Explore recursos adicionais do Aspose.Email, como manipulação de anexos, extração de itens de calendário ou envio SMTP, visitando a [documentação](https://reference.aspose.com/email/java/) oficial.

## Perguntas Frequentes

**P: Posso carregar e‑mails de formatos diferentes de .msg?**  
R: Sim, Aspose.Email suporta EML, MSG, MHT e vários outros formatos.

**P: Como posso lidar com arquivos de e‑mail muito grandes de forma eficiente?**  
R: Use as APIs de streaming fornecidas pelo Aspose.Email para ler/escrever dados em blocos, reduzindo a pressão de memória.

**P: É possível modificar anexos dentro de um MailMessage?**  
R: Absolutamente. Você pode adicionar, remover ou substituir anexos via a coleção `MailMessage.getAttachments()`.

**P: E se o meu deslocamento de fuso horário for negativo (atrás do UTC)?**  
R: Passe um valor negativo em milissegundos para `setTimeZoneOffset`, por exemplo, `-3 * 60 * 60 * 1000` para UTC‑3.

**P: Posso usar Aspose.Email em projetos comerciais?**  
R: Sim, desde que você possua uma licença comercial válida.

**P: Como processar milhares de arquivos MSG sem ficar sem memória?**  
R: Processar arquivos em lotes, liberar cada `MailMessage` após a gravação e considerar usar o padrão `try‑with‑resources` do Java para limpeza automática.

## Recursos
- [Documentation](https://reference.aspose.com/email/java/)
- [Download Library](https://releases.aspose.com/email/java/)
- [Purchase License](https://purchase.aspose.com/buy)
- [Free Trial](https://releases.aspose.com/email/java/)
- [Temporary License](https://purchase.aspose.com/temporary-license/)
- [Support Forum](https://forum.aspose.com/c/email/10)

---

**Last Updated:** 2026-02-27  
**Tested With:** Aspose.Email for Java 25.4 (jdk16 classifier)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}