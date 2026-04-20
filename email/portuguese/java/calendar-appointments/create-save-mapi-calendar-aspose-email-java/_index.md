---
date: '2026-03-20'
description: Aprenda como exportar o PST do calendário do Outlook usando Aspose.Email
  para Java – crie itens de calendário MAPI, defina recorrência, adicione participantes
  e salve no PST.
keywords:
- Create MAPI Calendar Java
- Aspose.Email Java Calendar
- Java PST File Save
title: Exportar PST de calendário do Outlook com Aspose.Email – Java
url: /pt/java/calendar-appointments/create-save-mapi-calendar-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Exportar PST de calendário do Outlook com Aspose.Email – Java

## Introdução

Você está procurando simplificar a automação de calendários em suas aplicações Java e precisa **exportar arquivos PST de calendário do Outlook**? Com **Aspose.Email for Java**, você pode **criar itens de calendário MAPI Java**, definir padrões de recorrência, adicionar participantes e **salvar o calendário em PST** com apenas algumas linhas de código. Este tutorial orienta você por todo o processo — desde a configuração da biblioteca até a geração de uma entrada de calendário totalmente funcional pronta para distribuição.

### O que você aprenderá
- Como **criar eventos de calendário MAPI Java** usando Aspose.Email.  
- Configuração de padrões de recorrência diários, semanais ou personalizados.  
- Adição de destinatários (organizadores, participantes) aos convites de calendário.  
- Persistência do item de calendário ao **salvar o calendário em PST** para compatibilidade com Outlook.  
- Como **automatizar o agendamento de reuniões** com código reutilizável.

## Respostas rápidas
- **Qual biblioteca?** Aspose.Email for Java  
- **Objetivo principal?** Exportar PST de calendário do Outlook e **salvar o calendário em PST**  
- **Pré‑requisitos?** Java 8+, Maven, licença Aspose.Email  
- **Tempo típico de implementação?** 10‑15 minutos para um evento básico  
- **Posso adicionar recorrência?** Sim – diária, semanal, mensal etc.

## Exportar PST de calendário do Outlook

Nesta seção focamos no fluxo de ponta a ponta que permite **exportar arquivos PST de calendário do Outlook**. Após criar o objeto de calendário MAPI, a etapa final é armazená‑lo dentro de um arquivo PST que o Outlook pode ler diretamente.

## Por que usar Aspose.Email para automação de calendário?

- **Compatibilidade total com Outlook** – itens gerados funcionam no Outlook, OWA e clientes móveis.  
- **Suporte avançado a recorrência** – padrões diários, semanais, mensais e personalizados prontos para uso.  
- **Sem dependências externas** – biblioteca Java pura, sem necessidade de interop COM.  
- **Alto desempenho** – manipulação eficiente de arquivos PST grandes e operações em lote.  
- **Automatizar agendamento de reuniões** – incorpore essa lógica em jobs batch ou serviços web para criar centenas de convites automaticamente.

## Pré‑requisitos

Antes de começar, certifique‑se de que você tem:

### Bibliotecas necessárias
- **Aspose.Email for Java**: Versão 25.4 ou posterior.

### Requisitos de configuração do ambiente
- Uma IDE Java como IntelliJ IDEA ou Eclipse.  
- Maven instalado para gerenciar dependências.

### Pré‑requisitos de conhecimento
- Habilidades básicas de programação em Java.  
- Familiaridade com conceitos de orientação a objetos.

## Configurando Aspose.Email for Java

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

Aspose.Email oferece uma avaliação gratuita, mas uma licença desbloqueia todos os recursos:

- **Avaliação gratuita**: Teste sem limitações por 30 dias.  
- **Licença temporária**: Solicite via [site da Aspose](https://purchase.aspose.com/temporary-license/) se precisar de tempo extra.  
- **Compra**: Adquira uma licença permanente na [página de compra](https://purchase.aspose.com/buy).

### Inicialização básica

Após adicionar a dependência, inicialize a biblioteca com seu arquivo de licença:

```java
com.aspose.email.License license = new com.aspose.email.License();
license.setLicense("path_to_your_license.lic");
```

## Guia de implementação

Agora que tudo está configurado, vamos **criar calendário MAPI Java** e **salvar o calendário em PST**.

### Criar um calendário MAPI com recorrência

#### Visão geral

Construiremos um evento de calendário, aplicaremos uma recorrência diária, adicionaremos participantes e, finalmente, armazenaremos o item em um arquivo PST.

#### Implementação passo a passo

1. **Inicializar data e padrão de recorrência**  

   Primeiro, defina o horário de início e configure uma recorrência diária:

   ```java
   import java.util.Date;

   // Add hours to current date to get the start time
   Date startDate = addHours(new Date(), 12);

   MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
   recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
   ```

   *Explicação*: `MapiCalendarEventRecurrence` contém os detalhes da recorrência; escolhemos um padrão diário via `MapiCalendarDailyRecurrencePattern`.

2. **Configurar destinatários**  

   Adicione as pessoas que devem receber o convite da reunião:

   ```java
   import com.aspose.email.MapiRecipientCollection;
   import com.aspose.email.MapiRecipientType;

   MapiRecipientCollection recColl = new MapiRecipientCollection();
   recColl.add("recipient@gmail.com", "Attendee Name", MapiRecipientType.MAPI_TO);
   ```

   *Explicação*: `MapiRecipientCollection` armazena cada participante; `MAPI_TO` os marca como destinatários principais.

3. **Criar o item de calendário MAPI**  

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

   *Explicação*: O construtor recebe organizador, assunto, local, horários de início/fim, descrição, lista de destinatários e recorrência.

4. **Salvar em arquivo PST**  

   Por fim, persista o calendário ao **salvar o calendário em PST**:

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

### Dicas de solução de problemas
- Verifique o caminho da licença; uma licença inválida limitará a funcionalidade.  
- Certifique‑se de que os endereços de e‑mail dos destinatários estejam formatados corretamente para evitar falhas no convite.  
- Feche o PST (`pst.dispose()`) após as operações para liberar os manipuladores de arquivo.

## Aplicações práticas

Aqui estão cenários comuns onde **criar calendário MAPI Java** e **salvar o calendário em PST** se destaca:

1. **Agendamento automático de reuniões** – Gere convites recorrentes para equipes de projeto sem esforço manual.  
2. **Plataformas de gerenciamento de eventos** – Exporte sessões de conferência como itens de calendário compatíveis com Outlook.  
3. **Integração com CRM** – Sincronize compromissos de clientes de um sistema CRM diretamente para o Outlook via arquivos PST.

## Considerações de desempenho

- **Gerenciamento de recursos**: Libere objetos `PersonalStorage` após o uso para evitar bloqueios de arquivos.  
- **Processamento em lote**: Para volumes grandes, processe itens de calendário de forma assíncrona ou em blocos para manter o uso de memória baixo.  

## Conclusão

Agora você aprendeu como **exportar PST de calendário do Outlook** criando objetos de calendário MAPI Java, configurando recorrência, adicionando participantes e **salvando o calendário em PST** usando Aspose.Email. Essa abordagem capacita suas aplicações Java a automatizar fluxos de trabalho sofisticados de agendamento com compatibilidade Outlook.

Para aprofundar, consulte a [documentação oficial](https://reference.aspose.com/email/java/).

## Seção de Perguntas Frequentes

### Q: Posso criar padrões de recorrência semanais?
- **A**: Sim! Use `MapiCalendarWeeklyRecurrencePattern` para definir repetições semanais.

### Q: Como trato exceções na recorrência do evento?
- **A**: Chame `setExceptions()` no objeto de recorrência para especificar datas que divergem do padrão.

### Q: É possível atualizar um item de calendário existente?
- **A**: Absolutamente. Carregue o item do PST, modifique suas propriedades e salve novamente.

### Q: Posso criptografar o arquivo PST?
- **A**: Sim, Aspose.Email permite definir uma senha em `PersonalStorage` ao criar o PST.

### Q: E se eu precisar adicionar anexos ao evento de calendário?
- **A**: Use `calendar.getAttachments().addFileAttachment("path/to/file")` antes de salvar.

## Recursos

- [Documentação do Aspose.Email](https://reference.aspose.com/email/java/)
- [Download do Aspose.Email for Java](https://releases.aspose.com/email/java/)
- [Comprar uma licença](https://purchase.aspose.com/buy)
- [Versão de avaliação gratuita](https://releases.aspose.com/email/java/)
- [Solicitar licença temporária](https://purchase.aspose.com/temporary-license/)
- [Fórum de suporte da Aspose](https://forum.aspose.com/c/email/10)

---

**Última atualização:** 2026-03-20  
**Testado com:** Aspose.Email for Java 25.4 (JDK 16)  
**Autor:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}