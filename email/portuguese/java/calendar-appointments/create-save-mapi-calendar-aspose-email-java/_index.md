---
date: '2026-01-01'
description: Aprenda a criar calendário MAPI em Java e salvar o calendário em PST
  usando Aspose.Email para Java. Guia passo a passo com código, recorrência e destinatários.
keywords:
- Create MAPI Calendar Java
- Aspose.Email Java Calendar
- Java PST File Save
title: Como criar calendário MAPI em Java com Aspose.Email – Salvar calendário em
  PST
url: /pt/java/calendar-appointments/create-save-mapi-calendar-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Como criar MAPI calendar java com Aspose.Email – Salvar calendário em PST

## Introdução

Você está procurando simplificar a automação de calendários em suas aplicações Java? Com **Aspose.Email for Java**, você pode **create MAPI calendar java** itens, definir padrões de recorrência, adicionar participantes e **save calendar to PST** arquivos com apenas algumas linhas de código. Este tutorial guia você por todo o processo — desde a configuração da biblioteca até a geração de uma entrada de calendário totalmente funcional pronta para distribuição.

### O que você aprenderá
- Como **create MAPI calendar java** eventos usando Aspose.Email.  
- Configurar padrões de recorrência diários, semanais ou personalizados.  
- Adicionar destinatários (organizadores, participantes) aos seus convites de calendário.  
- Persistir o item de calendário usando **saving calendar to PST** para compatibilidade com Outlook.

Vamos mergulhar e preparar seu ambiente de desenvolvimento.

## Respostas Rápidas
- **Qual biblioteca?** Aspose.Email for Java  
- **Objetivo principal?** Create MAPI calendar java e **save calendar to PST**  
- **Pré-requisitos?** Java 8+, Maven, licença Aspose.Email  
- **Tempo típico de implementação?** 10‑15 minutos para um evento básico  
- **Posso adicionar recorrência?** Sim – diário, semanal, mensal, etc.

## O que é um MAPI Calendar em Java?
Um objeto de calendário MAPI (Messaging Application Programming Interface) representa uma reunião ou compromisso compatível com Outlook. Usando Aspose.Email, você pode construir esses objetos programaticamente, permitindo integração perfeita com Exchange, Outlook ou qualquer cliente que consuma arquivos PST.

## Por que usar Aspose.Email para automação de calendário?
- **Compatibilidade total com Outlook** – itens gerados funcionam no Outlook, OWA e clientes móveis.- **Suporte avançado a recorrência** – padrões diários, semanais, mensais e personalizados prontos para uso.  
- **Sem dependências externas** – biblioteca pura Java, sem necessidade de interop COM.  
- **Alto desempenho** – manipulação eficiente de arquivos PST grandes e operações em lote.

## Pré-requisitos

Antes de começarmos, certifique-se de que você tem:

### Bibliotecas Necessárias
- **Aspose.Email for Java**: Versão 25.4 ou posterior.

### Requisitos de Configuração do Ambiente
- Uma IDE Java como IntelliJ IDEA ou Eclipse.  
- Maven instalado para gerenciar dependências.

### Pré-requisitos de Conhecimento
- Conhecimentos básicos de programação Java.  
- Familiaridade com conceitos orientados a objetos.

## Configurando Aspose.Email para Java

Add the Aspose.Email Maven dependency to your `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Aquisição de Licença

Aspose.Email offers a free trial, but a license unlocks all features:

- **Teste Gratuito**: Teste sem limitações por 30 dias.  
- **Licença Temporária**: Solicite via [site da Aspose](https://purchase.aspose.com/temporary-license/) se precisar de tempo extra.  
- **Compra**: Adquira uma licença permanente na [página de compra](https://purchase.aspose.com/buy).

### Inicialização Básica

After adding the dependency, initialize the library with your license file:

```java
com.aspose.email.License license = new com.aspose.email.License();
license.setLicense("path_to_your_license.lic");
```

## Guia de Implementação

Now that you’re set up, let’s **create MAPI calendar java** and **save calendar to PST**.

### Criar um MAPI Calendar com Recorrência

#### Visão Geral

Vamos criar um evento de calendário, aplicar uma recorrência diária, adicionar participantes e, finalmente, armazená-lo em um arquivo PST.

#### Implementação Passo a Passo

1. **Initialize Date and Recurrence Pattern**  

   First, define the start time and set a daily recurrence:

   ```java
   import java.util.Date;

   // Add hours to current date to get the start time
   Date startDate = addHours(new Date(), 12);

   MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
   recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
   ```

   *Explicação*: `MapiCalendarEventRecurrence` contém detalhes da recorrência; escolhemos um padrão diário via `MapiCalendarDailyRecurrencePattern`.

2. **Set Up Recipients**  

   Add the people who should receive the meeting invitation:

   ```java
   import com.aspose.email.MapiRecipientCollection;
   import com.aspose.email.MapiRecipientType;

   MapiRecipientCollection recColl = new MapiRecipientCollection();
   recColl.add("recipient@gmail.com", "Attendee Name", MapiRecipientType.MAPI_TO);
   ```

   *Explicação*: `MapiRecipientCollection` armazena cada participante; `MAPI_TO` os marca como destinatários principais.

3. **Create the MAPI Calendar Item**  

   Build the calendar object with all required details:

   ```java
   import com.aspose.email.MapiCalendar;

   MapiCalendar calendar = new MapiCalendar(
       "Organizer Name", 
       "Meeting Subject", 
       "Meeting Location", 
       startDate, 
       addHours(startDate, 1), // End time is one hour after start
       "Event Description",
       recColl,
       recurrence
   );
   ```

   *Explicação*: O construtor espera organizador, assunto, local, horários de início/fim, descrição, lista de destinatários e recorrência.

4. **Save to PST File**  

   Finally, persist the calendar by **saving calendar to PST**:

   ```java
   import com.aspose.email.PersonalStorage;
   import com.aspose.email.FolderInfo;
   import com.aspose.email.StandardIpmFolder;

   PersonalStorage pst = PersonalStorage.create("calendar.pst", 0);
   FolderInfo calendarFolder = pst.createPredefinedFolder("Calendar", StandardIpmFolder.CALendars);

   // Save the MAPI Calendar item
   calendarFolder.addMapiMessageItem(calendar);
   ```

   *Explicação*: `PersonalStorage.create` gera um novo arquivo PST, e `addMapiMessageItem` insere a entrada de calendário na pasta "Calendar".

### Dicas de Solução de Problemas
- Verifique o caminho da licença; uma licença inválida limitará a funcionalidade.  
- Certifique-se de que os endereços de e‑mail dos destinatários estejam formatados corretamente para evitar falhas no convite.  
- Feche o PST (`pst.dispose()`) após as operações para liberar os manipuladores de arquivo.

## Aplicações Práticas

Here are common scenarios where **creating MAPI calendar java** and **saving calendar to PST** shines:

1. **Automated Meeting Scheduling** – Generate recurring meeting invites for project teams without manual effort. -> **Agendamento Automatizado de Reuniões** – Gere convites recorrentes para equipes de projeto sem esforço manual.  
2. **Event Management Platforms** – Export conference sessions as Outlook‑compatible calendar items. -> **Plataformas de Gerenciamento de Eventos** – Exporte sessões de conferência como itens de calendário compatíveis com Outlook.  
3. **CRM Integration** – Sync customer appointments from a CRM system directly into Outlook via PST files. -> **Integração com CRM** – Sincronize compromissos de clientes de um sistema CRM diretamente para o Outlook via arquivos PST.

## Considerações de Desempenho

- **Gerenciamento de Recursos**: Libere objetos `PersonalStorage` após o uso para evitar bloqueios de arquivos.  
- **Processamento em Lote**: Para grandes volumes, processe itens de calendário de forma assíncrona ou em blocos para manter o uso de memória baixo.

## Conclusão

You’ve now learned how to **create MAPI calendar java** objects, configure recurrence, add attendees, and **save calendar to PST** using Aspose.Email. This approach empowers your Java applications to automate sophisticated scheduling workflows with Outlook compatibility.

For deeper exploration, check the official [documentation](https://reference.aspose.com/email/java/).

## Seção de Perguntas Frequentes

### P: Posso criar padrões de recorrência semanais?
- **R**: Sim! Use `MapiCalendarWeeklyRecurrencePattern` para definir repetições semanais.

### P: Como lidar com exceções na recorrência de eventos?
- **R**: Chame `setExceptions()` no objeto de recorrência para especificar datas que se desviam do padrão.

### P: É possível atualizar um item de calendário existente?
- **R**: Absolutamente. Carregue o item do PST, modifique suas propriedades e salve novamente.

### P: Posso criptografar o arquivo PST?
- **R**: Sim, Aspose.Email permite definir uma senha em `PersonalStorage` ao criar o PST.

### P: E se eu precisar adicionar anexos ao evento de calendário?
- **R**: Use `calendar.getAttachments().addFileAttachment("path/to/file")` antes de salvar.

## Recursos

- [Aspose.Email Documentation](https://reference.aspose.com/email/java/)
- [Download Aspose.Email for Java](https://releases.aspose.com/email/java/)
- [Purchase a License](https://purchase.aspose.com/buy)
- [Free Trial Version](https://releases.aspose.com/email/java/)
- [Request a Temporary License](https://purchase.aspose.com/temporary-license/)
- [Aspose Support Forum](https://forum.aspose.com/c/email/10)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-01  
**Tested With:** Aspose.Email for Java 25.4 (JDK 16)  
**Author:** Aspose