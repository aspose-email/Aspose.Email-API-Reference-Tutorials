---
date: '2026-02-22'
description: Aprenda a definir um sinalizador de acompanhamento no Outlook usando
  Aspose.Email para Java, incluindo a definição, leitura e remoção de sinalizadores
  para os destinatários.
keywords:
- Manage Outlook follow-up flags
- Set follow-up flags in Outlook with Aspose.Email for Java
- Integrate email task management with Aspose.Email
title: Como definir a bandeira de acompanhamento do Outlook usando Aspose.Email para
  Java
url: /pt/java/calendar-appointments/aspose-email-java-outlook-follow-up-flags/
weight: 1
---

 craft translation.

Be careful with markdown formatting.

Proceed.{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Como Definir a Outlook Follow Up Flag usando Aspose.Email para Java

## Introdução
Se você já teve dificuldade em acompanhar e‑mails importantes, sabe o quão valiosa pode ser a **outlook follow up flag** do Outlook. Neste guia, mostraremos **como definir uma outlook follow up flag** programaticamente com Aspose.Email para Java, além de abordar como **definir outlook follow up flag para destinatários** e como **remover uma outlook follow up flag** quando uma tarefa é concluída. Ao final, você será capaz de automatizar o rastreamento de tarefas, lembretes e trilhas de auditoria diretamente do seu código Java.

**O que você aprenderá**
- Criar e aplicar uma bandeira de follow‑up em uma mensagem do Outlook.  
- Definir bandeiras de follow‑up para destinatários específicos.  
- Marcar uma bandeira como concluída e removê‑la posteriormente.  
- Ler as opções da bandeira para relatórios ou conformidade.  

Vamos preparar o ambiente antes de mergulhar no código.

## Respostas Rápidas
- **O que significa “como definir follow‑up”?** Adicionar uma bandeira com datas de início, lembrete e vencimento a um item do Outlook.  
- **Qual biblioteca é necessária?** Aspose.Email para Java (v25.4 ou mais recente).  
- **Preciso de licença?** Sim, uma licença de avaliação ou comprada é necessária para funcionalidade completa.  
- **Posso definir bandeiras apenas para destinatários?** Absolutamente – use `FollowUpManager.setFlagForRecipients`.  
- **É possível remover a bandeira depois?** Sim, chame `FollowUpManager.clearFlag`.

## O que é uma Outlook Follow Up Flag?
Uma Outlook Follow Up Flag é um marcador de tarefa integrado que pode associar uma data de início, um lembrete e uma data de vencimento a qualquer item de e‑mail. Ela transforma um e‑mail comum em um item de ação rastreável, ajudando você e sua equipe a manterem o controle das tarefas pendentes.

## Por que usar Aspose.Email para Java?
Aspose.Email oferece uma API pura em Java que funciona sem a necessidade do Outlook instalado, permitindo manipular arquivos .msg, definir bandeiras e gerenciar tarefas em qualquer plataforma—perfeito para **automate outlook tasks**, serviços de backend ou integração com ferramentas de gerenciamento de projetos.

## Pré‑requisitos
- **Aspose.Email para Java** versão 25.4 ou posterior (também conhecido como **aspose email java**).  
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
- **Licença temporária** – teste estendido.  
- **Licença completa** – assinatura perpétua.

Inicialize a licença antes de qualquer operação de e‑mail:

```java
License license = new License();
license.setLicense("path/to/Aspose.Total.Java.lic");
```

## Definir Outlook Follow Up Flag (Recurso 1)
### Etapa 1: Criar e Inicializar a Mensagem
```java
MailMessage mailMsg = new MailMessage();
mailMsg.setSender(new MailAddress("AETest12@gmail.com"));
mailMsg.getTo().addMailAddress(new MailAddress("receiver@gmail.com"));
mailMsg.setBody("This message will test if follow up options can be added to a new mapi message.");
MapiMessage mapi = MapiMessage.fromMailMessage(mailMsg);
```
*Primeiro criamos um `MailMessage`, definimos remetente/destinatário e, em seguida, o convertemos para um `MapiMessage` para manipular a bandeira.*

### Etapa 2: Definir Datas de Follow‑Up (Lembrete da Bandeira do Outlook)
```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 14, 40, 0);
Date dtStartDate = calendar.getTime();
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
calendar.add(Calendar.DATE, 1);
Date dtDueDate = calendar.getTime();
```
*Aqui definimos as datas de início, lembrete (o **outlook flag reminder**) e vencimento usando a classe `Calendar`.*

### Etapa 3: Aplicar Opções de Follow‑Up
```java
FollowUpOptions options = new FollowUpOptions("Follow Up", dtStartDate, dtDueDate, dtReminderDate);
FollowUpManager.setOptions(mapi, options);
```
*O objeto `FollowUpOptions` contém todos os detalhes da bandeira, que aplicamos com `FollowUpManager.setOptions`.*

### Etapa 4: Salvar a Mensagem
```java
mapi.save(outputDir + "SetFollowUpflag_out.msg");
```
*A mensagem é salva como um arquivo `.msg` com a bandeira anexada.*

## Como Definir Bandeira para Destinatários (Recurso 2)
### Visão Geral
Às vezes, você precisa que a bandeira apareça **apenas para destinatários**. Este exemplo marca a mensagem como rascunho primeiro, depois adiciona a bandeira.

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
*A bandeira agora fica visível apenas para os destinatários – um cenário clássico de **flag for recipients**.*

## Como Marcar uma Outlook Follow Up Flag como Concluída (Recurso 3)
### Etapa 1: Carregar a Mensagem
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
```

### Etapa 2: Marcar como Concluída e Salvar
```java
FollowUpManager.markAsCompleted(mapi);
mapi.save(outputDir + "MarkedCompleted_out.msg");
```
*O status da bandeira muda para “Completed” e o arquivo atualizado é salvo.*

## Como Remover uma Outlook Follow Up Flag (Recurso 4)
### Etapa 1: Carregar e Limpar a Bandeira
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpManager.clearFlag(mapi);
mapi.save(outputDir + "FollowUpFlagRemoved_out.msg");
```
*A mensagem é salva sem nenhuma bandeira de follow‑up.*

## Como Ler Opções da Bandeira (Recurso 5)
### Etapa 1: Recuperar Opções
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpOptions options = FollowUpManager.getOptions(mapi);
```
*O objeto `options` agora contém datas de início, vencimento e lembrete, além do assunto da bandeira – útil quando você precisa **read flag options** para relatórios.*

## Aplicações Práticas
- **Integração de Gerenciamento de Tarefas:** Sincronize e‑mails marcados com Jira, Trello ou Azure Boards.  
- **Lembretes Automatizados:** Gere e‑mails de lembrete diários para follow‑ups pendentes.  
- **Auditorias de Conformidade:** Exporte dados de bandeiras para relatórios regulatórios.

## Considerações de Desempenho
- **Cálculos de Data:** Calcule datas uma única vez por lote, em vez de dentro de loops.  
- **Gerenciamento de Recursos:** Feche quaisquer streams ou manipuladores de arquivos após salvar as mensagens.  
- **Uso de Memória:** Procese caixas de correio grandes em blocos para evitar pressão no heap.

## Problemas Comuns e Soluções
| Problema | Causa | Solução |
|----------|-------|---------|
| Bandeira não aparece no Outlook | Mensagem salva sem `MessageFlags` corretos | Certifique‑se de que `setMessageFlags` esteja definido como `MSGFLAG_UNSENT` antes de aplicar bandeiras para destinatários. |
| Salvamento gera `AccessDeniedException` | Caminho de arquivo incorreto ou falta de permissão de gravação | Verifique se o diretório de saída existe e se a aplicação tem direitos de escrita. |
| Datas estão adiantadas em um dia | Descompasso de fuso horário | Use `TimeZone.getTimeZone("GMT")` ou seu fuso local de forma consistente. |

## Perguntas Frequentes
**Q: O que é Aspose.Email para Java?**  
A: É uma API pura em Java que permite criar, ler e manipular arquivos de e‑mail (MSG, EML, etc.) sem precisar do Outlook instalado.

**Q: Como obtenho uma licença de avaliação gratuita?**  
A: Visite o [site da Aspose](https://releases.aspose.com/email/java/) para baixar a avaliação de 30 dias.

**Q: Posso definir múltiplas bandeiras de follow‑up em uma única mensagem?**  
A: O Outlook suporta apenas uma bandeira por mensagem, mas você pode armazenar dados de tarefa adicionais em propriedades MAPI personalizadas.

**Q: Minha mensagem não é salva após definir a bandeira. O que devo verificar?**  
A: Confirme se o caminho `outputDir` é válido e se a aplicação tem permissão para gravar nesse local.

**Q: Como remover bandeiras de muitas mensagens de uma vez?**  
A: Percorra sua coleção de mensagens e chame `FollowUpManager.clearFlag` em cada `MapiMessage`.

## Recursos
- [Documentation](https://reference.aspose.com/email/java/)
- [Download Aspose.Email para Java](https://releases.aspose.com/email/java/)
- [Aspose.Email Free Trial](https://purchase.aspose.com/purchase/free-trial/aspose-email-java)

---

**Última atualização:** 2026-02-22  
**Testado com:** Aspose.Email para Java 25.4 (jdk16)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}