---
date: '2026-07-27'
description: Aprenda como definir a bandeira do Outlook Java usando Aspose.Email para
  Java, cobrindo criação de bandeiras, bandeiras de destinatários, conclusão, remoção
  e opções de leitura.
keywords:
- set outlook flag java
- outlook follow up flag java
- aspose email java
lastmod: '2026-07-27'
og_description: Defina a bandeira do Outlook Java com Aspose.Email para Java. Este
  guia mostra como criar, ler, concluir e remover bandeiras de acompanhamento do Outlook
  de forma eficiente.
og_image_alt: 'Developer guide: Set Outlook flag Java using Aspose.Email'
og_title: Definir Bandeira do Outlook Java – Guia Completo de Programação Aspose.Email
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Learn how to set outlook flag java using Aspose.Email for Java, covering
    flag creation, recipient flags, completion, removal, and reading options.
  headline: Set Outlook Flag Java – Complete Aspose.Email Programming Guide
  type: TechArticle
- description: Learn how to set outlook flag java using Aspose.Email for Java, covering
    flag creation, recipient flags, completion, removal, and reading options.
  name: Set Outlook Flag Java – Complete Aspose.Email Programming Guide
  steps:
  - name: Create and Initialize the Message
    text: '`MailMessage` is Aspose.Email’s high‑level class that represents an email.
      After you build the message, you convert it to a `MapiMessage` for flag manipulation.
      *We first build a `MailMessage`, set sender/recipient, then convert it to a
      `MapiMessage` for flag manipulation.*'
  - name: Define Follow‑Up Dates (Outlook Flag Reminder)
    text: '`FollowUpOptions` holds the start, reminder, and due dates. Use Java’s
      `Calendar` to set precise timestamps. *Here we set the start, reminder (the
      **outlook flag reminder**), and due dates using the `Calendar` class.*'
  - name: Apply Follow‑Up Options
    text: The `FollowUpManager.setOptions` method attaches the flag to the `MapiMessage`.
      *The `FollowUpOptions` object holds all flag details, which we apply with `FollowUpManager.setOptions`.*
  - name: Save the Message
    text: Save the flagged message as a `.msg` file so Outlook can display the flag.
      *The message is saved as a `.msg` file with the flag attached.*
  - name: Mark as Draft
    text: '`MessageFlags` is a MAPI enumeration that controls the state of the message.
      Setting `MSGFLAG_UNSENT` tells Outlook the item is a draft. *Marking the message
      as unsent ensures Outlook treats it as a draft.*'
  - name: Set Recipient Flag
    text: '`FollowUpManager.setFlagForRecipients` attaches the flag exclusively to
      the recipient’s copy. *The flag is now visible only to the recipients – a classic
      **flag for recipients** scenario.*'
  - name: Load the Message
    text: '`MapiMessage` can read a saved `.msg` file, giving you full access to its
      MAPI properties.'
  - name: Mark as Completed and Save
    text: '`FollowUpManager.completeFlag` updates the flag status, after which you
      persist the changes. *The flag status changes to “Completed” and the updated
      file is saved.*'
  - name: Load and Clear Flag
    text: '`FollowUpManager.clearFlag` removes all flag‑related properties from the
      message. *The message is saved without any follow‑up flag.*'
  - name: Retrieve Options
    text: The returned `options` object gives you full visibility into the flag’s
      configuration. *The `options` object now contains start, due, and reminder dates,
      plus the flag subject – useful when you need to **read flag options** for reporting.*
  type: HowTo
- questions:
  - answer: It’s a pure‑Java API that lets you create, read, and manipulate email
      files (MSG, EML, etc.) without needing Outlook installed.
    question: What is Aspose.Email for Java?
  - answer: Visit the [Aspose website](https://releases.aspose.com/email/java/) to
      download a 30‑day trial.
    question: How do I obtain a free trial license?
  - answer: Outlook supports only one flag per message, but you can store additional
      task data in custom MAPI properties.
    question: Can I set multiple follow‑up flags on a single message?
  - answer: Confirm the `outputDir` path is valid and that the application has permission
      to write to that location.
    question: My message isn’t saved after setting a flag. What should I check?
  - answer: Loop through your message collection and call `FollowUpManager.clearFlag`
      on each `MapiMessage`.
    question: How can I remove flags from many messages at once?
  type: FAQPage
tags:
- outlook flag
- aspose.email
- java email automation
title: Definir Bandeira do Outlook Java – Guia Completo de Programação Aspose.Email
url: /pt/java/calendar-appointments/aspose-email-java-outlook-follow-up-flags/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Definir Bandeira do Outlook em Java usando Aspose.Email para Java

## Introdução
Se você precisa **definir bandeira do outlook java** programaticamente, chegou ao lugar certo. A bandeira de follow‑up do Outlook transforma um e‑mail comum em uma tarefa rastreada, e o Aspose.Email para Java permite gerenciar essas bandeiras sem precisar do Outlook instalado. Neste tutorial vamos percorrer a criação, leitura, conclusão e, finalmente, remoção de bandeiras, além de como aplicar bandeiras para destinatários específicos. Ao final, você terá um trecho reutilizável em Java que automatiza o rastreamento de tarefas diretamente dos seus serviços de backend.

## Respostas Rápidas
- **O que significa “definir bandeira do outlook java”?** Adicionar uma bandeira com datas de início, lembrete e vencimento a um item do Outlook via código Java.  
- **Qual biblioteca é necessária?** Aspose.Email para Java (v25.4 ou mais recente).  
- **Preciso de licença?** Sim – um teste funciona para avaliação, mas uma licença adquirida é necessária para produção.  
- **Posso definir bandeiras apenas para destinatários?** Absolutamente – use `FollowUpManager.setFlagForRecipients`.  
- **É possível remover uma bandeira depois?** Sim – chame `FollowUpManager.clearFlag`.

## O que é uma Bandeira de Follow‑Up do Outlook?
A bandeira de follow‑up do Outlook é um marcador de tarefa interno que pode anexar uma data de início, um lembrete e uma data de vencimento a qualquer item de e‑mail. Ela transforma um e‑mail em um item de ação rastreado, ajudando você e sua equipe a manterem o controle das tarefas pendentes.

## Por que usar Aspose.Email para Java?
Aspose.Email para Java suporta **mais de 70 formatos de e‑mail** (incluindo MSG, EML, MHTML e TNEF) e pode processar **mais de 100.000 mensagens por minuto** em um servidor típico de 8 núcleos, tudo sem exigir Outlook na máquina host. Isso o torna ideal para automação de backend, relatórios de conformidade e integração com ferramentas de gerenciamento de projetos.

## Pré‑requisitos
- **Aspose.Email para Java** versão 25.4 ou posterior.  
- **JDK 16+** instalado.  
- IDE compatível com Maven (IntelliJ IDEA, Eclipse, etc.).  
- Conhecimento básico de Java e familiaridade com conceitos de e‑mail.

## Configurando Aspose.Email para Java
### Configuração do Maven
Adicione a seguinte dependência ao seu `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Aquisição de Licença
Aspose.Email requer uma licença para uso em produção:

- **Teste gratuito** – avaliação de 30 dias.  
- **Licença temporária** – teste estendido.  
- **Licença completa** – assinatura perpétua.

Inicialize a licença antes de qualquer operação de e‑mail:

```java
License license = new License();
license.setLicense("path/to/Aspose.Total.Java.lic");
```

## Definir Bandeira do Outlook Java (Recurso 1)
### Resposta direta
Carregue um `MailMessage`, converta‑o para um `MapiMessage`, configure `FollowUpOptions` e chame `FollowUpManager.setOptions`. Essa sequência cria um item do Outlook totalmente sinalizado em apenas algumas linhas de código Java.

### Etapa 1: Criar e Inicializar a Mensagem
`MailMessage` é a classe de alto nível do Aspose.Email que representa um e‑mail. Depois de construir a mensagem, você a converte para um `MapiMessage` para manipulação da bandeira.

```java
MailMessage mailMsg = new MailMessage();
mailMsg.setSender(new MailAddress("AETest12@gmail.com"));
mailMsg.getTo().addMailAddress(new MailAddress("receiver@gmail.com"));
mailMsg.setBody("This message will test if follow up options can be added to a new mapi message.");
MapiMessage mapi = MapiMessage.fromMailMessage(mailMsg);
```
*Primeiro criamos um `MailMessage`, definimos remetente/destinatário e, em seguida, convertemos para um `MapiMessage` para manipulação da bandeira.*

### Etapa 2: Definir Datas de Follow‑Up (Lembrete da Bandeira do Outlook)
`FollowUpOptions` contém as datas de início, lembrete e vencimento. Use o `Calendar` do Java para definir timestamps precisos.

```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 14, 40, 0);
Date dtStartDate = calendar.getTime();
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
calendar.add(Calendar.DATE, 1);
Date dtDueDate = calendar.getTime();
```
*Aqui definimos a data de início, o lembrete (o **lembrete da bandeira do outlook**) e as datas de vencimento usando a classe `Calendar`.*

### Etapa 3: Aplicar Opções de Follow‑Up
O método `FollowUpManager.setOptions` anexa a bandeira ao `MapiMessage`.  

```java
FollowUpOptions options = new FollowUpOptions("Follow Up", dtStartDate, dtDueDate, dtReminderDate);
FollowUpManager.setOptions(mapi, options);
```
*O objeto `FollowUpOptions` contém todos os detalhes da bandeira, que aplicamos com `FollowUpManager.setOptions`.*

### Etapa 4: Salvar a Mensagem
Salve a mensagem sinalizada como um arquivo `.msg` para que o Outlook possa exibir a bandeira.

```java
mapi.save(outputDir + "SetFollowUpflag_out.msg");
```
*A mensagem é salva como um arquivo `.msg` com a bandeira anexada.*

## Como Definir Bandeira para Destinatários (Recurso 2)?
Use `FollowUpManager.setFlagForRecipients` após marcar a mensagem como rascunho. Esse método adiciona a bandeira de follow‑up apenas à cópia do destinatário, deixando a visualização do remetente inalterada. É necessário definir `MessageFlags.MSGFLAG_UNSENT` antes de aplicar a bandeira. Você também pode personalizar as datas de início, lembrete e vencimento usando um objeto `FollowUpOptions` antes de chamar o método.

### Resposta direta
Marque a mensagem como rascunho usando `MessageFlags.MSGFLAG_UNSENT`, então chame `FollowUpManager.setFlagForRecipients`. O Outlook mostrará a bandeira apenas para os destinatários, não para o remetente.

### Visão geral
Às vezes você precisa que a bandeira apareça **apenas para os destinatários**. Este exemplo marca a mensagem como rascunho primeiro, depois adiciona a bandeira.

#### Etapa 1: Marcar como Rascunho
`MessageFlags` é uma enumeração MAPI que controla o estado da mensagem. Definir `MSGFLAG_UNSENT` indica ao Outlook que o item é um rascunho.

```java
mapi.setMessageFlags(MapiMessageFlags.MSGFLAG_UNSENT);
```
*Marcar a mensagem como não enviada garante que o Outlook a trate como um rascunho.*

#### Etapa 2: Definir Bandeira para Destinatário
`FollowUpManager.setFlagForRecipients` anexa a bandeira exclusivamente à cópia do destinatário.

```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
FollowUpManager.setFlagForRecipients(mapi, "Follow up", dtReminderDate);
```
*A bandeira agora está visível apenas para os destinatários – um cenário clássico de **bandeira para destinatários**.*

## Como Marcar uma Bandeira de Follow‑Up do Outlook como Concluída (Recurso 3)?
Carregue o arquivo `.msg` em um `MapiMessage`, então chame `FollowUpManager.completeFlag`. Isso atualiza o status da bandeira para Concluída e adiciona uma marca de verificação no Outlook. Após concluir, salve a mensagem para persistir a alteração. Você também pode definir o horário de conclusão ajustando a propriedade `FlagCompleteTime`, se necessário para fins de auditoria.

### Resposta direta
Carregue o arquivo `.msg` existente em um `MapiMessage`, chame `FollowUpManager.completeFlag` e salve o arquivo. O status da bandeira muda para “Concluída” e aparece com uma marca de verificação no Outlook.

### Etapa 1: Carregar a Mensagem
`MapiMessage` pode ler um arquivo `.msg` salvo, proporcionando acesso total às suas propriedades MAPI.

```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
```

### Etapa 2: Marcar como Concluída e Salvar
`FollowUpManager.completeFlag` atualiza o status da bandeira, após o que você persiste as alterações.

```java
FollowUpManager.markAsCompleted(mapi);
mapi.save(outputDir + "MarkedCompleted_out.msg");
```
*O status da bandeira muda para “Concluída” e o arquivo atualizado é salvo.*

## Como Remover uma Bandeira de Follow‑Up do Outlook (Recurso 4)?
Abra o arquivo `.msg` com `MapiMessage`, invoque `FollowUpManager.clearFlag` e, em seguida, salve a mensagem. Isso remove todas as propriedades MAPI relacionadas à bandeira, de modo que o Outlook não exibirá mais nenhum indicador de follow‑up. Use isso quando uma tarefa for cancelada ou não for mais relevante. Certifique‑se também de limpar quaisquer propriedades de lembrete personalizadas para evitar notificações residuais.

### Resposta direta
Abra o arquivo `.msg` com `MapiMessage`, invoque `FollowUpManager.clearFlag` e salve o arquivo. A mensagem não exibirá mais nenhum indicador de follow‑up no Outlook.

### Etapa 1: Carregar e Limpar a Bandeira
`FollowUpManager.clearFlag` remove todas as propriedades relacionadas à bandeira da mensagem.

```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpManager.clearFlag(mapi);
mapi.save(outputDir + "FollowUpFlagRemoved_out.msg");
```
*A mensagem é salva sem nenhuma bandeira de follow‑up.*

## Como Ler Opções de Bandeira (Recurso 5)?
Chame `FollowUpManager.getOptions` em um `MapiMessage` carregado para obter um objeto `FollowUpOptions`. Esse objeto fornece as datas de início, vencimento, lembrete e o assunto da bandeira, permitindo que você exiba ou registre os detalhes da bandeira. É útil para relatórios e auditorias de conformidade.

### Resposta direta
Use `FollowUpManager.getOptions` em um `MapiMessage` carregado para recuperar um objeto `FollowUpOptions` contendo datas de início, vencimento, lembrete e o assunto da bandeira. Isso é útil para relatórios ou auditorias de conformidade.

### Etapa 1: Recuperar Opções
O objeto `options` retornado fornece visibilidade total da configuração da bandeira.

```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpOptions options = FollowUpManager.getOptions(mapi);
```
*O objeto `options` agora contém datas de início, vencimento e lembrete, além do assunto da bandeira – útil quando você precisa **ler opções de bandeira** para relatórios.*

## Aplicações Práticas
- **Integração de Gerenciamento de Tarefas:** sincronizar e‑mails sinalizados com Jira, Trello ou Azure Boards.  
- **Lembretes Automatizados:** gerar e‑mails diários de lembrete para follow‑ups pendentes.  
- **Auditorias de Conformidade:** exportar dados de bandeiras para relatórios regulatórios, aproveitando a capacidade de ler opções de bandeira programaticamente.

## Considerações de Desempenho
- **Cálculos de Data:** compute datas uma vez por lote ao invés de dentro de loops.  
- **Gerenciamento de Recursos:** fechar quaisquer streams ou manipuladores de arquivos após salvar mensagens.  
- **Uso de Memória:** processar caixas de correio grandes em blocos para evitar pressão de heap; Aspose.Email pode lidar com caixas de correio de centenas de páginas sem carregar o arquivo inteiro na memória.

## Problemas Comuns e Soluções
| Problema | Causa | Correção |
|----------|-------|----------|
| Bandeira não aparece no Outlook | Mensagem salva sem `MessageFlags` adequados | Certifique‑se de que `setMessageFlags` está definido como `MSGFLAG_UNSENT` antes de aplicar bandeiras para destinatários. |
| Salvar gera `AccessDeniedException` | Caminho de arquivo incorreto ou permissões de gravação ausentes | Verifique se o diretório de saída existe e se a aplicação tem direitos de gravação. |
| Datas estão com um dia de diferença | Descompasso de fuso horário | Use `TimeZone.getTimeZone("GMT")` ou seu fuso local de forma consistente. |

## Perguntas Frequentes
**Q: O que é Aspose.Email para Java?**  
A: É uma API pura em Java que permite criar, ler e manipular arquivos de e‑mail (MSG, EML etc.) sem precisar do Outlook instalado.

**Q: Como obtenho uma licença de teste gratuita?**  
A: Visite o [site da Aspose](https://releases.aspose.com/email/java/) para baixar um teste de 30 dias.

**Q: Posso definir múltiplas bandeiras de follow‑up em uma única mensagem?**  
A: O Outlook suporta apenas uma bandeira por mensagem, mas você pode armazenar dados de tarefa adicionais em propriedades MAPI personalizadas.

**Q: Minha mensagem não é salva após definir uma bandeira. O que devo verificar?**  
A: Confirme se o caminho `outputDir` é válido e se a aplicação tem permissão para gravar nesse local.

**Q: Como remover bandeiras de muitas mensagens de uma só vez?**  
A: Percorra sua coleção de mensagens e chame `FollowUpManager.clearFlag` em cada `MapiMessage`.

## Recursos
- [Documentação](https://reference.aspose.com/email/java/)
- [Baixar Aspose.Email para Java](https://releases.aspose.com/email/java/)
- [Teste Gratuito do Aspose.Email](https://purchase.aspose.com/purchase/free-trial/aspose-email-java)

---

**Última Atualização:** 2026-07-27  
**Testado com:** Aspose.Email para Java 25.4 (JDK 16)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriais Relacionados
- [Gerenciar Categorias do Outlook com Aspose.Email para Java - Guia Abrangente](/email/java/calendar-appointments/manage-outlook-categories-aspose-email-java/)
- [Criar notas do Outlook em Java com Aspose.Email – Guia Completo](/email/java/calendar-appointments/create-customize-outlook-notes-aspose-email-java/)
- [Criar Tarefas no Microsoft Exchange Usando Aspose.Email para Java: Guia Completo](/email/java/exchange-server-integration/create-tasks-exchange-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}