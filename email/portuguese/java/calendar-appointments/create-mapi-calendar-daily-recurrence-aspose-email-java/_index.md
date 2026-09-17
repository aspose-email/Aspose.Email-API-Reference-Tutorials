---
date: '2026-09-17'
description: Aprenda como criar calendário Outlook em Java com recorrência diária
  e exceções, e salvar o calendário em PST usando Aspose.Email for Java.
keywords:
- create outlook calendar
- outlook calendar daily recurrence
- java calendar exceptions
- Aspose.Email Java
- MAPI PST generation
lastmod: '2026-09-17'
og_description: Crie calendário Outlook em Java usando Aspose.Email. Aprenda recorrência
  diária, tratamento de exceções e como salvar em PST em um guia passo a passo.
og_image_alt: Code example creating Outlook calendar with recurrence and PST export
  using Aspose.Email for Java
og_title: Criar calendário Outlook em Java com recorrência diária e exceções
schemas:
- author: Aspose
  dateModified: '2026-09-17'
  description: Learn how to create outlook calendar java with daily recurrence and
    exceptions, and save calendar to PST using Aspose.Email for Java.
  headline: Create outlook calendar java with daily recurrence and exceptions
  type: TechArticle
- questions:
  - answer: Yes, you can set the `StartTimeZone` and `EndTimeZone` properties on `MapiCalendar`.
    question: Does the library support time‑zone aware appointments?
  - answer: Use the `DeletedInstanceDates` collection on the recurrence pattern to
      mark specific dates as removed.
    question: Can I programmatically delete a single occurrence from a recurring series?
  - answer: PST files follow the Unicode format limits (up to 2 GB by default), but
      you can configure larger sizes via `PersonalStorage` settings.
    question: Are there limits on the size of a PST file created with Aspose.Email?
  - answer: Create `MapiRecipient` objects, set their `RecipientType` to `MapiRecipientType.MAPI_TO`,
      and add them to the `Recipients` collection of the `MapiMessage`.
    question: How do I add attendees to a meeting request?
  - answer: Yes, Aspose.Email also provides `MapiTask` with similar recurrence capabilities.
    question: Is there support for recurring tasks (not just appointments)?
  type: FAQPage
tags:
- outlook calendar
- Aspose.Email
- Java scheduling
- PST file
title: Criar calendário Outlook em Java com recorrência diária e exceções
url: /pt/java/calendar-appointments/create-mapi-calendar-daily-recurrence-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar calendário Outlook java com recorrência diária e exceções

Gerenciar eventos recorrentes de forma eficiente pode ser desafiador, especialmente quando você precisa de um **outlook calendar java** que suporte padrões de recorrência diária e exceções ocasionais. Neste tutorial você aprenderá como criar objetos Outlook calendar Java, configurar recorrência diária, adicionar instâncias de exceção e, finalmente, **save calendar to PST** usando Aspose.Email for Java. Ao final, você terá um trecho de código reutilizável que pode ser inserido em qualquer serviço de agendamento baseado em Java.

## Respostas rápidas
- **Qual biblioteca?** Aspose.Email for Java  
- **Tarefa principal?** Criar um Outlook calendar Java com recorrência diária e exceções  
- **JDK pré-requisito?** Java 16 ou superior  
- **Posso anexar arquivos às exceções?** Sim, usando `MapiCalendarExceptionInfo`  
- **Onde o calendário é armazenado?** Em um arquivo PST via `PersonalStorage`  

## O que é um Outlook calendar java?
Um objeto Outlook calendar Java é uma representação programática de um compromisso do Outlook, construído sobre a especificação MAPI (Messaging Application Programming Interface), que inclui propriedades como assunto, local, horários de início/fim, regras de recorrência, participantes e anexos. Esse objeto pode ser manipulado, serializado e armazenado em arquivos PST sem a necessidade do Outlook.

## Por que usar Aspose.Email for Java?
Aspose.Email for Java permite trabalhar com objetos MAPI sem instalar o Outlook. A biblioteca suporta **50+ MAPI properties**, pode gerar arquivos PST Unicode de até **2 GB** em menos de **2 seconds** para dados típicos de compromissos, e funciona em qualquer plataforma que suporte Java 16+. Essa abordagem pure‑Java possibilita a criação de calendários no lado do servidor, séries de reuniões automatizadas e controle total sobre a lógica de recorrência.

## Pré-requisitos

Antes de começarmos, certifique-se de que você tem a seguinte configuração:

- **Aspose.Email Library**: Versão 25.4 (ou posterior) – disponível via Maven ou download direto.  
- **Java Development Kit (JDK)**: JDK 16 ou mais recente.  
- **IDE**: IntelliJ IDEA, Eclipse, NetBeans ou qualquer editor compatível com Java.

### Bibliotecas e dependências necessárias

Para integrar Aspose.Email ao seu projeto usando Maven, adicione a seguinte dependência ao seu `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Aquisição de licença

Para usar Aspose.Email, você precisará de uma licença:

- **Free trial** – explore todos os recursos sem custo.  
- **Temporary license** – solicite para avaliação estendida.  
- **Full license** – compre para implantações em produção.

## Configurando Aspose.Email para Java

Primeiro, configure seu ambiente:

1. Verifique se o JDK 16 está instalado e se `JAVA_HOME` está configurado.  
2. Adicione a dependência Maven (ou faça o download do JAR) ao seu projeto.  

Aqui está um pequeno trecho que mostra como carregar um arquivo de licença:

```java
import com.aspose.email.*;

public class InitializeAspose {
    public static void main(String[] args) {
        // Set up a license if available
        License license = new License();
        try {
            license.setLicense("path/to/your/license.lic");
        } catch (Exception e) {
            System.out.println("License not found, using trial version.");
        }
    }
}
```

## Guia de implementação

### Criando outlook calendar java com recorrência diária e exceções

#### Visão geral
Este recurso permite automatizar compromissos recorrentes enquanto ainda é possível pular ou modificar instâncias específicas.

#### Implementação passo a passo

**1. Defina a data de início do evento**  
Determine quando a série deve começar:

```java
Date startDate = addHours(newDate(2018, 7, 19), 12);
```

**2. Crie o objeto de calendário MAPI**  
A classe `MapiCalendar` é o objeto de nível superior que representa um único item de calendário na memória. Forneça local, assunto e descrição:

```java
MapiCalendar calendar = new MapiCalendar("location1", "summary1", "description1", startDate, addHours(startDate, 1));
```

**3. Defina um padrão de recorrência diária**  
A classe `MapiCalendarRecurrencePattern` armazena a regra que repete o compromisso todos os dias. Configure o evento para repetir diariamente:

```java
MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
MapiCalendarRecurrencePattern pattern = recurrence.getRecurrencePattern();

pattern.setPatternType(MapiCalendarRecurrencePatternType.Day);
pattern.setPeriod(1); // Daily
pattern.setEndType(MapiCalendarRecurrenceEndType.NeverEnd);
```

**4. Adicione uma exceção à recorrência**  
`MapiCalendarExceptionInfo` descreve uma única ocorrência que se desvia do padrão — seja excluída ou alterada. Especifique uma data que deve ser excluída (ou alterada):

```java
Date exceptionDate = addDays(startDate, 3);

MapiCalendarExceptionInfo exception = new MapiCalendarExceptionInfo();
exception.setLocation("exceptionLocation");
exception.setSubject("exceptionSubject");
exception.setBody("exceptionBody");

exception.setOriginalStartDate(exceptionDate);
exception.setStartDateTime(exceptionDate);
exception.setEndDateTime(addHours(exceptionDate, 5));

pattern.getExceptions().addItem(exception);
pattern.getModifiedInstanceDates().addItem(exceptionDate);
pattern.getDeletedInstanceDates().addItem(exceptionDate);

calendar.setRecurrence(recurrence);
```

### Anexando arquivos a exceções de calendário

#### Visão geral
Você pode anexar documentos de apoio (por exemplo, agendas) a qualquer instância de exceção.

**1. Crie e anexe um arquivo**

```java
MapiCalendarExceptionInfo exception = new MapiCalendarExceptionInfo();
exception.getAttachments().add("file.txt", "hello, world!".getBytes());
```

## Salvando outlook calendar java para PST (save calendar to pst)

#### Visão geral
Persista o calendário em um arquivo PST para que o Outlook ou outros clientes possam lê-lo.

**1. Crie e salve o calendário para PST**  
A classe `PersonalStorage` fornece métodos para criar um novo arquivo PST e adicionar itens MAPI a ele.

```java
final PersonalStorage pst = PersonalStorage.create(new ByteArrayOutputStream(), FileFormatVersion.Unicode);
try {
    FolderInfo calendarFolder = pst.createPredefinedFolder("Calendar", StandardIpmFolder.Appointments);
    calendarFolder.addMapiMessageItem(calendar);
} finally {
    pst.dispose();
}
```

## Aplicações práticas
- **Corporate scheduling** – automatize séries de reuniões, pulando feriados automaticamente.  
- **Project management** – acompanhe marcos recorrentes com alterações de data ocasionais.  
- **Event planning** – gerencie conferências de vários dias onde algumas sessões são canceladas ou reprogramadas.

### Possibilidades de integração
Combine Aspose.Email com plataformas CRM, APIs de gerenciamento de tarefas ou motores de fluxo de trabalho personalizados para impulsionar a automação de ponta a ponta.

## Considerações de desempenho
- **Dispose resources** – sempre chame `dispose()` em `PersonalStorage` para liberar manipuladores de arquivos.  
- **Stream usage** – prefira `ByteArrayOutputStream` ou streams de arquivo para evitar carregar PSTs inteiros na memória.  
- **Async operations** – para geração em massa de calendários, execute a lógica de criação em uma thread em segundo plano para manter a UI responsiva.

## Conclusão
Seguindo este guia, você agora sabe como **create outlook calendar java** objetos com recorrência diária, adicionar exceções, anexar arquivos e **save calendar to PST**. Essas capacidades permitem que você construa recursos de agendamento robustos sem nunca tocar diretamente no Outlook.

### Próximos passos
- Experimente padrões de recorrência semanais ou mensais.  
- Explore propriedades MAPI adicionais, como participantes, lembretes e categorias.  
- Revise a documentação completa da API do Aspose.Email para cenários mais avançados.

## Perguntas frequentes

**Q: A biblioteca suporta compromissos com consciência de fuso horário?**  
A: Sim, você pode definir as propriedades `StartTimeZone` e `EndTimeZone` em `MapiCalendar`.

**Q: Posso excluir programaticamente uma única ocorrência de uma série recorrente?**  
A: Use a coleção `DeletedInstanceDates` no padrão de recorrência para marcar datas específicas como removidas.

**Q: Existem limites no tamanho de um arquivo PST criado com Aspose.Email?**  
A: Arquivos PST seguem os limites do formato Unicode (até 2 GB por padrão), mas você pode configurar tamanhos maiores via configurações `PersonalStorage`.

**Q: Como adiciono participantes a uma solicitação de reunião?**  
A: Crie objetos `MapiRecipient`, defina seu `RecipientType` como `MapiRecipientType.MAPI_TO` e adicione-os à coleção `Recipients` do `MapiMessage`.

**Q: Há suporte para tarefas recorrentes (não apenas compromissos)?**  
A: Sim, Aspose.Email também fornece `MapiTask` com capacidades de recorrência semelhantes.

**Q: Posso usar este guia como parte de uma série de tutoriais Aspose.Email Java?**  
A: Absolutamente – os passos mostrados aqui são parte central de qualquer tutorial Aspose.Email Java que trate da criação de calendários.

## Recursos
- [Aspose.Email for Java Documentation](https://reference.aspose.com/email/java/)
- [Download Aspose.Email](https://releases.aspose.com/email/java/)
- [Purchase a License](https://purchase.aspose.com/buy)
- [Free Trial Version](https://releases.aspose.com/email/java/)
- [Request Temporary License](https://purchase.aspose.com/temporary-license/)
- [Aspose Support Forum](https://forum.aspose.com/c/email/10)

---

**Última atualização:** 2026-09-17  
**Testado com:** Aspose.Email for Java 25.4 (JDK 16)  
**Autor:** Aspose

## Tutoriais Relacionados

- [Export Outlook calendar PST with Aspose.Email – Java](/email/java/calendar-appointments/create-save-mapi-calendar-aspose-email-java/)
- [How to Create Calendar Item Java Using Aspose.Email](/email/java/calendar-appointments/create-save-calendar-items-aspose-email-java/)
- [Create Calendar Sharing Invitation with Aspose.Email for Java](/email/java/calendar-appointments/create-send-calendar-invitations-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}