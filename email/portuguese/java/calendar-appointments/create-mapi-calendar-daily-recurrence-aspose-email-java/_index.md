---
date: '2026-03-20'
description: Aprenda como criar um calendário do Outlook em Java com recorrência diária
  e exceções e salvar o calendário em PST usando Aspose.Email para Java.
keywords:
- MAPI Calendar creation
- daily recurrence events
- Java calendar exceptions
title: Criar calendário Outlook em Java com recorrência diária e exceções
url: /pt/java/calendar-appointments/create-mapi-calendar-daily-recurrence-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Como criar outlook calendar java com recorrência diária e exceções

Gerenciar eventos recorrentes de forma eficiente pode ser desafiador, especialmente quando você precisa de um **outlook calendar java** que suporte padrões de recorrência diária e exceções ocasionais. Neste tutorial você aprenderá como criar objetos Outlook calendar Java, configurar recorrência diária, adicionar instâncias de exceção e, finalmente, **salvar calendário em PST** usando Aspose.Email for Java. Ao final, você terá um trecho de código reutilizável que pode ser inserido em qualquer serviço de agendamento baseado em Java.

## Respostas Rápidas
- **Qual biblioteca?** Aspose.Email for Java  
- **Tarefa principal?** Criar um Outlook calendar Java com recorrência diária e exceções  
- **JDK pré-requisito?** Java 16 ou superior  
- **Posso anexar arquivos às exceções?** Sim, usando `MapiCalendarExceptionInfo`  
- **Onde o calendário é armazenado?** Em um arquivo PST via `PersonalStorage`

## O que é um Outlook calendar java?
Um objeto Outlook calendar Java (implementado como um calendário MAPI) segue os mesmos padrões das compromissos do Microsoft Outlook. Ele armazena regras de recorrência avançadas, tratamento de exceções, participantes e anexos, tornando‑o perfeito para agendamento de nível empresarial.

## Por que usar Aspose.Email for Java?
Aspose.Email fornece uma API pura em Java que permite trabalhar com objetos MAPI sem precisar do Outlook instalado. Esta abordagem **aspose email tutorial java** permite a geração de arquivos PST no lado do servidor, séries de reuniões automatizadas e controle total sobre a lógica de recorrência.

## Pré-requisitos

Antes de começarmos, certifique‑se de que você tem a seguinte configuração:
- **Biblioteca Aspose.Email**: Versão 25.4 (ou posterior) – disponível via Maven ou download direto.  
- **Java Development Kit (JDK)**: JDK 16 ou mais recente.  
- **IDE**: IntelliJ IDEA, Eclipse, NetBeans ou qualquer editor compatível com Java.

### Bibliotecas e Dependências Necessárias

Para integrar Aspose.Email ao seu projeto usando Maven, adicione a seguinte dependência ao seu `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Aquisição de Licença

Para usar Aspose.Email, você precisará de uma licença:
- **Teste Gratuito** – explore todos os recursos sem custo.  
- **Licença Temporária** – solicite para avaliação estendida.  
- **Licença Completa** – compre para implantações em produção.

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

## Guia de Implementação

### Criando Outlook calendar java com Recorrência Diária e Exceções

#### Visão Geral
Este recurso permite automatizar compromissos recorrentes enquanto ainda é possível pular ou modificar instâncias específicas.

#### Implementação Passo a Passo

**1. Definir Data de Início do Evento**  
Determine quando a série deve começar:

```java
Date startDate = addHours(newDate(2018, 7, 19), 12);
```

**2. Criar o Objeto MAPI Calendar**  
Forneça local, assunto e descrição:

```java
MapiCalendar calendar = new MapiCalendar("location1", "summary1", "description1", startDate, addHours(startDate, 1));
```

**3. Definir um Padrão de Recorrência Diária**  
Configure o evento para repetir todos os dias:

```java
MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
MapiCalendarRecurrencePattern pattern = recurrence.getRecurrencePattern();

pattern.setPatternType(MapiCalendarRecurrencePatternType.Day);
pattern.setPeriod(1); // Daily
pattern.setEndType(MapiCalendarRecurrenceEndType.NeverEnd);
```

**4. Adicionar uma Exceção à Recorrência**  
Especifique uma data que deve ser excluída (ou alterada):

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

### Anexando Arquivos às Exceções do Calendário

#### Visão Geral
Você pode anexar documentos de suporte (por exemplo, agendas) a qualquer instância de exceção.

**1. Criar e Anexar um Arquivo**

```java
MapiCalendarExceptionInfo exception = new MapiCalendarExceptionInfo();
exception.getAttachments().add("file.txt", "hello, world!".getBytes());
```

### Salvando Outlook calendar java em PST (salvar calendário em pst)

#### Visão Geral
Persista o calendário em um arquivo PST para que o Outlook ou outros clientes possam lê‑lo.

**1. Criar e Salvar o Calendário em PST**

```java
final PersonalStorage pst = PersonalStorage.create(new ByteArrayOutputStream(), FileFormatVersion.Unicode);
try {
    FolderInfo calendarFolder = pst.createPredefinedFolder("Calendar", StandardIpmFolder.Appointments);
    calendarFolder.addMapiMessageItem(calendar);
} finally {
    pst.dispose();
}
```

## Aplicações Práticas
- **Agendamento Corporativo** – automatize séries de reuniões, pulando feriados automaticamente.  
- **Gerenciamento de Projetos** – acompanhe marcos recorrentes com alterações ocasionais de datas.  
- **Planejamento de Eventos** – gerencie conferências de vários dias onde algumas sessões são canceladas ou remarcadas.

### Possibilidades de Integração
Combine Aspose.Email com plataformas CRM, APIs de gerenciamento de tarefas ou motores de fluxo de trabalho personalizados para conduzir automação de ponta a ponta.

## Considerações de Desempenho
- **Liberar Recursos** – sempre chame `dispose()` em `PersonalStorage` para liberar manipuladores de arquivos.  
- **Uso de Streams** – prefira `ByteArrayOutputStream` ou streams de arquivo para evitar carregar PSTs inteiros na memória.  
- **Operações Assíncronas** – para geração em massa de calendários, execute a lógica de criação em uma thread em segundo plano para manter a UI responsiva.

## Conclusão
Seguindo este guia, você agora sabe como **criar outlook calendar java** objetos com recorrência diária, adicionar exceções, anexar arquivos e **salvar calendário em PST**. Essas capacidades permitem construir recursos de agendamento robustos sem jamais precisar tocar diretamente no Outlook.

### Próximos Passos
- Experimente padrões de recorrência semanal ou mensal.  
- Explore propriedades MAPI adicionais, como participantes, lembretes e categorias.  
- Revise a documentação completa da API do Aspose.Email para cenários mais avançados.

## Perguntas Frequentes

**Q: A biblioteca suporta compromissos com consciência de fuso horário?**  
A: Sim, você pode definir as propriedades `StartTimeZone` e `EndTimeZone` em `MapiCalendar`.

**Q: Posso excluir programaticamente uma única ocorrência de uma série recorrente?**  
A: Use a coleção `DeletedInstanceDates` no padrão de recorrência para marcar datas específicas como removidas.

**Q: Existem limites para o tamanho de um arquivo PST criado com Aspose.Email?**  
A: Arquivos PST seguem os limites do formato Unicode (até 2 GB por padrão), mas você pode configurar tamanhos maiores via configurações de `PersonalStorage`.

**Q: Como adiciono participantes a uma solicitação de reunião?**  
A: Crie objetos `MapiRecipient`, defina seu `RecipientType` como `MapiRecipientType.MAPI_TO` e adicione-os à coleção `Recipients` do `MapiMessage`.

**Q: Há suporte para tarefas recorrentes (não apenas compromissos)?**  
A: Sim, Aspose.Email também fornece `MapiTask` com capacidades de recorrência semelhantes.

**Q: Posso usar este guia como parte de uma série de tutorial aspose email java?**  
A: Absolutamente – os passos mostrados aqui são parte central de qualquer tutorial Aspose.Email Java que trate da criação de calendários.

## Recursos
- [Documentação do Aspose.Email para Java](https://reference.aspose.com/email/java/)
- [Download do Aspose.Email](https://releases.aspose.com/email/java/)
- [Comprar uma Licença](https://purchase.aspose.com/buy)
- [Versão de Avaliação Gratuita](https://releases.aspose.com/email/java/)
- [Solicitar Licença Temporária](https://purchase.aspose.com/temporary-license/)
- [Fórum de Suporte Aspose](https://forum.aspose.com/c/email/10)

---

**Última Atualização:** 2026-03-20  
**Testado com:** Aspose.Email for Java 25.4 (JDK 16)  
**Autor:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}