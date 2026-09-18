---
date: '2026-09-17'
description: Aprenda como exportar o Outlook calendar PST usando Aspose.Email para
  Java – crie MAPI calendar items, defina recurrence, adicione attendees e salve para
  PST.
keywords:
- export outlook calendar pst
- how to export pst
- how to add recurrence
- how to add attendees
- save calendar to pst
lastmod: '2026-09-17'
og_description: Exporte o Outlook calendar PST usando Aspose.Email para Java. Aprenda
  a criar MAPI calendar items, adicionar recurrence, attendees e salvar para PST em
  minutos.
og_image_alt: Guide to exporting Outlook calendar PST files with Aspose.Email for
  Java
og_title: Exportar Outlook calendar PST com Aspose.Email – Java
schemas:
- author: Aspose
  dateModified: '2026-09-17'
  description: Learn how to export Outlook calendar PST using Aspose.Email for Java
    – create MAPI calendar items, set recurrence, add attendees, and save to PST.
  headline: Export Outlook calendar PST with Aspose.Email – Java
  type: TechArticle
- description: Learn how to export Outlook calendar PST using Aspose.Email for Java
    – create MAPI calendar items, set recurrence, add attendees, and save to PST.
  name: Export Outlook calendar PST with Aspose.Email – Java
  steps:
  - name: '**Initialize date and recurrence pattern**'
    text: '**Initialize date and recurrence pattern**'
  - name: '**Set up recipients**'
    text: '**Set up recipients**'
  - name: '**Create the MAPI calendar item**'
    text: '**Create the MAPI calendar item**'
  - name: '**Save to PST file**'
    text: '**Save to PST file**'
  - name: '**Automated meeting scheduling** – Generate recurring meeting invites for
      project teams without manual effort.'
    text: '**Automated meeting scheduling** – Generate recurring meeting invites for
      project teams without manual effort.'
  - name: '**Event management platforms** – Export conference sessions as Outlook‑compatible
      calendar items.'
    text: '**Event management platforms** – Export conference sessions as Outlook‑compatible
      calendar items.'
  - name: '**CRM integration** – Sync customer appointments from a CRM system directly
      into Outlook via PST files.'
    text: '**CRM integration** – Sync customer appointments from a CRM system directly
      into Outlook via PST files.'
  type: HowTo
- questions:
  - answer: Aspose.Email for Java
    question: Which library?
  - answer: Export Outlook calendar PST and **save calendar to PST**
    question: Primary goal?
  - answer: Java 8+, Maven, Aspose.Email license
    question: Prerequisites?
  - answer: 10‑15 minutes for a basic event
    question: Typical implementation time?
  - answer: Yes – daily, weekly, monthly, etc.
    question: Can I add recurrence?
  type: FAQPage
tags:
- export outlook calendar pst
- Aspose.Email
- Java calendar automation
title: Exportar Outlook calendar PST com Aspose.Email – Java
url: /pt/java/calendar-appointments/create-save-mapi-calendar-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Exportar calendário Outlook PST com Aspose.Email – Java

## Introdução

Você está procurando simplificar a automação de calendário em suas aplicações Java e precisa **exportar arquivos PST de calendário do Outlook**? Com **Aspose.Email for Java**, você pode **criar itens de calendário MAPI Java**, definir padrões de recorrência, adicionar participantes e **salvar o calendário em PST** com apenas algumas linhas de código. Este tutorial orienta você em todo o processo — desde a configuração da biblioteca até a geração de uma entrada de calendário totalmente funcional pronta para distribuição.

### O que você aprenderá
- Como **criar eventos de calendário MAPI Java** usando Aspose.Email.  
- Configurar padrões de recorrência diários, semanais ou personalizados.  
- Adicionar destinatários (organizadores, participantes) aos seus convites de calendário.  
- Persistir o item de calendário **salvando o calendário em PST** para compatibilidade com Outlook.  
- Como **automatizar o agendamento de reuniões** com código reutilizável.

## Respostas rápidas
- **Qual biblioteca?** Aspose.Email for Java  
- **Objetivo principal?** Exportar calendário Outlook PST e **salvar o calendário em PST**  
- **Pré-requisitos?** Java 8+, Maven, licença Aspose.Email  
- **Tempo típico de implementação?** 10‑15 minutos para um evento básico  
- **Posso adicionar recorrência?** Sim – diária, semanal, mensal, etc.

## Exportar calendário Outlook PST

Nesta seção, focamos no fluxo de ponta a ponta que permite **exportar arquivos PST de calendário do Outlook**. Após criar o objeto de calendário MAPI, o passo final é armazená‑lo dentro de um arquivo PST que o Outlook pode ler diretamente.

## Por que usar Aspose.Email para automação de calendário?

Exportar calendário Outlook PST com Aspose.Email porque oferece uma maneira confiável e baseada em servidor de produzir itens compatíveis com Outlook sem interop COM. A biblioteca suporta **mais de 50 formatos de entrada e saída**, pode lidar com arquivos PST superiores a 2 GB e processa milhares de entradas de calendário por minuto em hardware de servidor típico. Seu mecanismo de recorrência embutido cobre padrões diários, semanais, mensais e personalizados, eliminando a necessidade de cálculos manuais de datas.

## Pré-requisitos

Antes de começarmos, certifique‑se de que você tem:

### Bibliotecas necessárias
- **Aspose.Email for Java**: Versão 25.4 ou posterior (suporta Java 8‑21).

### Requisitos de configuração do ambiente
- Uma IDE Java como IntelliJ IDEA ou Eclipse.  
- Maven instalado para gerenciar dependências.

### Pré-requisitos de conhecimento
- Habilidades básicas de programação Java.  
- Familiaridade com conceitos de programação orientada a objetos.

## Configurando Aspose.Email para Java

Adicione a dependência Maven do Aspose.Email ao seu `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Aquisição de licença

Aspose.Email oferece um teste gratuito, mas uma licença desbloqueia todos os recursos:

- **Teste gratuito**: Teste sem limitações por 30 dias.  
- **Licença temporária**: Solicite via [site da Aspose](https://purchase.aspose.com/temporary-license/) se precisar de tempo extra.  
- **Compra**: Adquira uma licença permanente na [página de compra](https://purchase.aspose.com/buy).

### Inicialização básica

Após adicionar a dependência, inicialize a biblioteca com seu arquivo de licença:

```java
com.aspose.email.License license = new com.aspose.email.License();
license.setLicense("path_to_your_license.lic");
```

## Guia de implementação

Agora que está configurado, vamos **criar calendário MAPI Java** e **salvar o calendário em PST**.

### Criar um calendário MAPI com recorrência

#### Visão geral

Construiremos um evento de calendário, aplicaremos uma recorrência diária, adicionaremos participantes e, finalmente, armazenaremos em um arquivo PST.

#### Implementação passo a passo

1. **Inicializar data e padrão de recorrência**  

   `MapiCalendarEventRecurrence` é a classe que armazena os detalhes de recorrência para um item de calendário.  
   `MapiCalendarDailyRecurrencePattern` define um agendamento simples de repetição diária.  

   Primeiro, defina a hora de início e configure uma recorrência diária:

   ```java
   import java.util.Date;

   // Add hours to current date to get the start time
   Date startDate = addHours(new Date(), 12);

   MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
   recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
   ```

2. **Configurar destinatários**  

   `MapiRecipientCollection` representa a lista de pessoas convidadas para a reunião.  
   `MAPI_TO` é a bandeira que marca um destinatário como participante principal.  

   Adicione as pessoas que devem receber o convite da reunião:

   ```java
   import com.aspose.email.MapiRecipientCollection;
   import com.aspose.email.MapiRecipientType;

   MapiRecipientCollection recColl = new MapiRecipientCollection();
   recColl.add("recipient@gmail.com", "Attendee Name", MapiRecipientType.MAPI_TO);
   ```

3. **Criar o item de calendário MAPI**  

   A classe `MapiMessage` (usada aqui como objeto de calendário) encapsula todas as propriedades do evento, como organizador, assunto, local, horários de início/fim, descrição, lista de destinatários e recorrência.  

   Construa o objeto de calendário com todos os detalhes necessários:

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

4. **Salvar em arquivo PST**  

   `PersonalStorage` é a API de nível superior do Aspose.Email para criar e manipular arquivos PST.  
   `addMapiMessageItem` insere uma mensagem MAPI (incluindo itens de calendário) em uma pasta especificada.  

   Finalmente, persista o calendário **salvando o calendário em PST**:

   ```java
   import com.aspose.email.PersonalStorage;
   import com.aspose.email.FolderInfo;
   import com.aspose.email.StandardIpmFolder;

   PersonalStorage pst = PersonalStorage.create("calendar.pst", 0);
   FolderInfo calendarFolder = pst.createPredefinedFolder("Calendar", StandardIpmFolder.CALendars);

   // Save the MAPI Calendar item
   calendarFolder.addMapiMessageItem(calendar);
   ```

### Dicas de solução de problemas
- Verifique o caminho da licença; uma licença inválida limitará a funcionalidade.  
- Certifique‑se de que os endereços de e‑mail dos destinatários estejam formatados corretamente para evitar falhas de convite.  
- Feche o PST (`pst.dispose()`) após as operações para liberar os manipuladores de arquivo.

## Aplicações práticas

Aqui estão cenários comuns onde **criar calendário MAPI Java** e **salvar o calendário em PST** se destacam:

1. **Agendamento automatizado de reuniões** – Gere convites de reunião recorrentes para equipes de projeto sem esforço manual.  
2. **Plataformas de gerenciamento de eventos** – Exporte sessões de conferência como itens de calendário compatíveis com Outlook.  
3. **Integração de CRM** – Sincronize compromissos de clientes de um sistema CRM diretamente para o Outlook via arquivos PST.

## Considerações de desempenho

- **Gerenciamento de recursos**: Libere objetos `PersonalStorage` após o uso para evitar bloqueios de arquivos.  
- **Processamento em lote**: Para grandes volumes, processe itens de calendário de forma assíncrona ou em blocos para manter o uso de memória baixo.  
- **Escalabilidade**: Aspose.Email pode gravar em arquivos PST maiores que 2 GB mantendo o consumo de memória abaixo de 200 MB.

## Conclusão

Agora você aprendeu como **exportar calendário Outlook PST** criando objetos de calendário MAPI Java, configurando recorrência, adicionando participantes e **salvando o calendário em PST** usando Aspose.Email. Essa abordagem capacita suas aplicações Java a automatizar fluxos de trabalho de agendamento sofisticados com compatibilidade Outlook.

Para uma exploração mais aprofundada, consulte a [documentação](https://reference.aspose.com/email/java/) oficial.

## Seção de Perguntas Frequentes

### Q: Posso criar padrões de recorrência semanal?
- **A**: Sim! Use `MapiCalendarWeeklyRecurrencePattern` para definir repetições semanais.

### Q: Como lidar com exceções na recorrência de eventos?
- **A**: Chame `setExceptions()` no objeto de recorrência para especificar datas que se desviam do padrão.

### Q: É possível atualizar um item de calendário existente?
- **A**: Absolutamente. Carregue o item do PST, modifique suas propriedades e salve‑o novamente.

### Q: Posso criptografar o arquivo PST?
- **A**: Sim, o Aspose.Email permite definir uma senha em `PersonalStorage` ao criar o PST.

### Q: E se eu precisar adicionar anexos ao evento de calendário?
- **A**: Use `calendar.getAttachments().addFileAttachment("path/to/file")` antes de salvar.

## Recursos

- [Documentação do Aspose.Email](https://reference.aspose.com/email/java/)
- [Baixar Aspose.Email para Java](https://releases.aspose.com/email/java/)
- [Comprar uma Licença](https://purchase.aspose.com/buy)
- [Versão de teste gratuita](https://releases.aspose.com/email/java/)
- [Solicitar uma Licença Temporária](https://purchase.aspose.com/temporary-license/)
- [Fórum de suporte da Aspose](https://forum.aspose.com/c/email/10)

**Última atualização:** 2026-09-17  
**Testado com:** Aspose.Email for Java 25.4 (JDK 16)  
**Autor:** Aspose

## Tutoriais Relacionados

- [Como Criar e Gerenciar Arquivos PST do Outlook Usando Aspose.Email para Java](/email/java/outlook-pst-ost-operations/aspose-email-java-manage-pst-files/)
- [Como Criar Arquivos PST com Aspose.Email para Java](/email/java/email-parsing-analysis/aspose-email-java-create-pst-guide/)
- [Como Criar Item de Calendário Java Usando Aspose.Email](/email/java/calendar-appointments/create-save-calendar-items-aspose-email-java/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}