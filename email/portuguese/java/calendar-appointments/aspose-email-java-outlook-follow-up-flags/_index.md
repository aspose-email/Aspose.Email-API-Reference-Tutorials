---
date: '2025-12-19'
description: Aprenda como definir sinalizadores de acompanhamento no Outlook usando
  Aspose.Email para Java, incluindo como definir o sinalizador de acompanhamento do
  Outlook e remover o sinalizador de acompanhamento do Outlook de forma eficiente.
keywords:
- Manage Outlook follow-up flags
- Set follow-up flags in Outlook with Aspose.Email for Java
- Integrate email task management with Aspose.Email
title: Como definir sinalizadores de acompanhamento no Outlook usando Aspose.Email
  para Java
url: /pt/java/calendar-appointments/aspose-email-java-outlook-follow-up-flags/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Como Definir Bandeiras de Acompanhamento no Outlook usando Aspose.Email para Java

## Introdução
Se você já teve dificuldade em acompanhar e‑mails importantes, sabe o quão valiosas podem ser as bandeiras de acompanhamento do Outlook. Neste guia, mostraremos **como definir bandeiras de acompanhamento** programaticamente com Aspose.Email para Java, além de abordar como **definir bandeira de acompanhamento do Outlook** para destinatários e como **remover bandeira de acompanhamento do Outlook** quando uma tarefa for concluída. Ao final, você poderá automatizar o rastreamento de tarefas, lembretes e trilhas de auditoria diretamente do seu código Java.

**O que você aprenderá**
- Criar e aplicar uma bandeira de acompanhamento em uma mensagem do Outlook.  
- Definir bandeiras de acompanhamento para destinatários específicos.  
- Marcar uma bandeira como concluída e, posteriormente, removê‑la.  
- Ler opções de bandeira para relatórios ou conformidade.  

Vamos preparar o ambiente antes de mergulhar no código.

## Respostas Rápidas
- **O que significa “como definir acompanhamento”?** Adicionar uma bandeira com datas de início, lembrete e vencimento a um item do Outlook.  
- **Qual biblioteca é necessária?** Aspose.Email para Java (v25.4 ou mais recente).  
- **Preciso de licença?** Sim, é necessária uma licença de avaliação ou comprada para funcionalidade completa.  
- **Posso definir bandeiras apenas para destinatários?** Absolutamente – use `FollowUpManager.setFlagForRecipients`.  
- **É possível remover uma bandeira depois?** Sim, chame `FollowUpManager.clearFlag`.

## O que é uma Bandeira de Acompanhamento?
Uma bandeira de acompanhamento é um recurso do Outlook que marca um e‑mail como uma tarefa, opcionalmente anexando datas de início, lembrete e vencimento. Ela ajuda você e sua equipe a manterem‑se em dia com ações pendentes.

## Por que usar Aspose.Email para Java?
Aspose.Email fornece uma API pura em Java que funciona sem a necessidade do Outlook instalado, permitindo manipular arquivos .msg, definir bandeiras e gerenciar tarefas em qualquer plataforma—perfeito para serviços de backend, fluxos de trabalho automatizados ou integração com ferramentas de gerenciamento de projetos.

## Pré‑requisitos
- **Aspose.Email para Java** versão 25.4 ou posterior.  
- **JDK 16+** instalado.  
- IDE compatível com Maven (IntelliJ IDEA, Eclipse, etc.).  
- Conhecimento básico de Java e familiaridade com conceitos de e‑mail.

## Configurando Aspose.Email para Java
### Configuração do Maven
Adicione a dependência a seguir ao seu `pom.xml`:

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
- **Licença temporária** – testes estendidos.  
- **Licença completa** – assinatura perpétua.

Inicialize a licença antes de qualquer operação de e‑mail:

```java
License license = new License();
license.setLicense("path/to/Aspose.Total.Java.lic");
```

## Guia de Implementação

### Como Definir Bandeiras de Acompanhamento (Recurso 1)
#### Visão Geral
Esta seção orienta na criação de uma mensagem do Outlook, definição de datas de início/lembrete/vencimento e aplicação de uma bandeira de acompanhamento.

#### Etapa 1: Criar e Inicializar a Mensagem
```java
MailMessage mailMsg = new MailMessage();
mailMsg.setSender(new MailAddress("AETest12@gmail.com"));
mailMsg.getTo().addMailAddress(new MailAddress("receiver@gmail.com"));
mailMsg.setBody("This message will test if follow up options can be added to a new mapi message.");
MapiMessage mapi = MapiMessage.fromMailMessage(mailMsg);
```
*Primeiro criamos um `MailMessage`, definimos remetente/destinatário e, em seguida, o convertemos para um `MapiMessage` para manipular a bandeira.*

#### Etapa 2: Definir Datas de Acompanhamento
```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 14, 40, 0);
Date dtStartDate = calendar.getTime();
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
calendar.add(Calendar.DATE, 1);
Date dtDueDate = calendar.getTime();
```
*Aqui definimos as datas de início, lembrete e vencimento usando a classe `Calendar`.*

#### Etapa 3: Aplicar Opções de Acompanhamento
```java
FollowUpOptions options = new FollowUpOptions("Follow Up", dtStartDate, dtDueDate, dtReminderDate);
FollowUpManager.setOptions(mapi, options);
```
*O objeto `FollowUpOptions` contém todos os detalhes da bandeira, que aplicamos com `FollowUpManager.setOptions`.*

#### Etapa 4: Salvar a Mensagem
```java
mapi.save(outputDir + "SetFollowUpflag_out.msg");
```
*A mensagem é salva como um arquivo `.msg` com a bandeira anexada.*

### Como Definir Bandeira de Acompanhamento do Outlook para Destinatários (Recurso 2)
#### Visão Geral
Às vezes, você precisa marcar uma mensagem apenas para os destinatários. Este exemplo marca a mensagem como rascunho primeiro e, depois, adiciona a bandeira.

#### Etapa 1: Marcar como Rascunho
```java
mapi.setMessageFlags(MapiMessageFlags.MSGFLAG_UNSENT);
```
*Marcar a mensagem como não enviada garante que o Outlook a trate como rascunho.*

#### Etapa 2: Definir Bandeira para Destinatário
```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
FollowUpManager.setFlagForRecipients(mapi, "Follow up", dtReminderDate);
```
*A bandeira agora fica visível apenas para os destinatários.*

### Como Marcar uma Bandeira de Acompanhamento do Outlook como Concluída (Recurso 3)
#### Visão Geral
Quando uma tarefa é concluída, você pode marcar programaticamente a bandeira como concluída.

#### Etapa 1: Carregar a Mensagem
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
```

#### Etapa 2: Marcar como Concluída e Salvar
```java
FollowUpManager.markAsCompleted(mapi);
mapi.save(outputDir + "MarkedCompleted_out.msg");
```
*O status da bandeira muda para “Completed” e o arquivo atualizado é salvo.*

### Como Remover a Bandeira de Acompanhamento do Outlook (Recurso 4)
#### Visão Geral
Se uma bandeira não for mais necessária, você pode limpá‑la completamente.

#### Etapa 1: Carregar e Limpar a Bandeira
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpManager.clearFlag(mapi);
mapi.save(outputDir + "FollowUpFlagRemoved_out.msg");
```
*A mensagem é salva sem nenhuma bandeira de acompanhamento.*

### Como Ler Opções de Bandeira de Acompanhamento (Recurso 5)
#### Visão Geral
Para auditoria ou relatórios, pode ser necessário ler as configurações de bandeira existentes.

#### Etapa 1: Recuperar Opções
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpOptions options = FollowUpManager.getOptions(mapi);
```
*O objeto `options` agora contém datas de início, vencimento e lembrete, além do assunto da bandeira.*

## Aplicações Práticas
- **Integração de Gerenciamento de Tarefas:** Sincronize e‑mails marcados com Jira, Trello ou Azure Boards.  
- **Lembretes Automatizados:** Gere e‑mails diários de lembrete para acompanhamentos pendentes.  
- **Auditorias de Conformidade:** Exporte dados de bandeiras para relatórios regulatórios.

## Considerações de Desempenho
- **Cálculo de Datas:** Compute as datas uma única vez por lote, em vez de dentro de loops.  
- **Gerenciamento de Recursos:** Feche quaisquer streams ou manipuladores de arquivos após salvar as mensagens.  
- **Uso de Memória:** Processe caixas de correio grandes em blocos para evitar pressão no heap.

## Problemas Comuns e Soluções
| Problema | Causa | Solução |
|----------|-------|---------|
| Bandeira não aparece no Outlook | Mensagem salva sem `MessageFlags` adequados | Certifique‑se de que `setMessageFlags` esteja definido como `MSGFLAG_UNSENT` antes de aplicar bandeiras para destinatários. |
| Salvar lança `AccessDeniedException` | Caminho de arquivo incorreto ou permissões de gravação ausentes | Verifique se o diretório de saída existe e se a aplicação tem direitos de escrita. |
| Datas com um dia de diferença | Descompasso de fuso horário | Use `TimeZone.getTimeZone("GMT")` ou seu fuso local de forma consistente. |

## Perguntas Frequentes
**P: O que é Aspose.Email para Java?**  
R: É uma API pura em Java que permite criar, ler e manipular arquivos de e‑mail (MSG, EML, etc.) sem precisar do Outlook instalado.

**P: Como obtenho uma licença de teste gratuita?**  
R: Visite o [site da Aspose](https://releases.aspose.com/email/java/) para baixar a avaliação de 30 dias.

**P: Posso definir múltiplas bandeiras de acompanhamento em uma única mensagem?**  
R: O Outlook suporta apenas uma bandeira por mensagem, mas você pode armazenar dados de tarefa adicionais em propriedades MAPI personalizadas.

**P: Minha mensagem não é salva após definir a bandeira. O que devo verificar?**  
R: Confirme se o caminho `outputDir` é válido e se a aplicação tem permissão para gravar nesse local.

**P: Como remover bandeiras de muitas mensagens de uma vez?**  
R: Percorra sua coleção de mensagens e chame `FollowUpManager.clearFlag` em cada `MapiMessage`.

## Recursos
- [Documentação](https://reference.aspose.com/email/java/)
- [Download Aspose.Email para Java](https://releases.aspose.com/email/java/)
- [Teste Gratuito Aspose.Email](https://purchase.aspose.com/purchase/free-trial/aspose-email-java)

---

**Última Atualização:** 2025-12-19  
**Testado Com:** Aspose.Email para Java 25.4 (jdk16)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}