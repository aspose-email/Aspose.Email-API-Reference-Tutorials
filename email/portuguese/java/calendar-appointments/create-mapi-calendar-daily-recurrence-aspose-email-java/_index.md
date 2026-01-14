---
date: '2025-12-20'
description: Aprenda a criar calendário MAPI em Java, gerenciar padrões de recorrência
  diária e lidar com exceções usando Aspose.Email para Java.
keywords:
- MAPI Calendar creation
- daily recurrence events
- Java calendar exceptions
title: Criar calendário MAPI em Java com recorrência diária e exceções
url: /pt/java/calendar-appointments/create-mapi-calendar-daily-recurrence-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Como criar um calendário MAPI Java com recorrência diária e exceções

Gerenciar eventos recorrentes de forma eficiente pode ser desafiador, especialmente quando são necessárias exceções ou alterações. Neste tutorial você **criará objetos mapi calendar java**, configurará padrões de recorrência diária e adicionará exceções usando Aspose.Email para Java. Você aprenderá a automatizar tarefas de agendamento perfeitamente dentro de suas aplicações.

## Respostas rápidas
- **Qual biblioteca?** Aspose.Email para Java  
- **Tarefa principal?** Criar um calendário MAPI com recorrência diária e exceções  
- **JDK pré‑requisito?** Java 16 ou superior  
- **Posso anexar arquivos às exceções?** Sim, usando `MapiCalendarExceptionInfo`  
- **Onde o calendário é armazenado?** Em um arquivo PST via `PersonalStorage`

### O que é um calendário MAPI?
Um calendário MAPI (Messaging Application Programming Interface) é um formato padrão usado pelo Microsoft Outlook e outros clientes de e‑mail para armazenar dados de compromissos. Ele suporta regras de recorrência avançadas, exceções e anexos, tornando‑o ideal para agendamento corporativo.

### Por que usar Aspose.Email para Java?
Aspose.Email fornece uma API pura em Java que permite criar, modificar e salvar objetos MAPI sem depender do Outlook. Isso significa que você pode construir recursos de agendamento no lado do servidor, gerar arquivos PST e lidar programaticamente com cenários complexos de recorrência.

## Pré‑requisitos

Antes de começar, certifique‑se de que você tem o seguinte configurado:
- **Biblioteca Aspose.Email**: Versão 25.4 (ou posterior) – disponível via Maven ou download direto.  
- **Kit de Desenvolvimento Java (JDK)**: JDK 16 ou mais recente.  
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
- **Teste gratuito** – explore todos os recursos sem custo.  
- **Licença temporária** – solicite para avaliação prolongada.  
- **Licença completa** – adquira para implantações em produção.

## Configurando Aspose.Email para Java

Primeiro, configure seu ambiente:

1. Verifique se o JDK 16 está instalado e se a variável `JAVA_HOME` está configurada.  
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

### Criando um calendário MAPI com recorrência diária e exceções

#### Visão geral
Este recurso permite automatizar compromissos recorrentes enquanto ainda é possível pular ou modificar instâncias específicas.

#### Implementação passo a passo

**1. Definir a data de início do evento**  
Determine quando a série deve começar:

```java
Date startDate = addHours(newDate(2018, 7, 19), 12);
```

**2. Criar o objeto MAPI Calendar**  
Forneça local, assunto e descrição:

```java
MapiCalendar calendar = new MapiCalendar("location1", "summary1", "description1", startDate, addHours(startDate, 1));
```

**3. Definir um padrão de recorrência diária**  
Configure o evento para repetir a cada dia:

```java
MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
MapiCalendarRecurrencePattern pattern = recurrence.getRecurrencePattern();

pattern.setPatternType(MapiCalendarRecurrencePatternType.Day);
pattern.setPeriod(1); // Daily
pattern.setEndType(MapiCalendarRecurrenceEndType.NeverEnd);
```

**4. Adicionar uma exceção à recorrência**  
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

### Anexando arquivos a exceções de calendário

#### Visão geral
Você pode anexar documentos de apoio (por exemplo, agendas) a qualquer instância de exceção.

**1. Criar e anexar um arquivo**

```java
MapiCalendarExceptionInfo exception = new MapiCalendarExceptionInfo();
exception.getAttachments().add("file.txt", "hello, world!".getBytes());
```

### Salvando o calendário MAPI em arquivos PST

#### Visão geral
Persista o calendário em um arquivo PST para que o Outlook ou outros clientes possam lê‑lo.

**1. Criar e salvar o calendário no PST**

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
- **Agendamento corporativo** – automatize séries de reuniões, pulando automaticamente feriados.  
- **Gestão de projetos** – acompanhe marcos recorrentes com alterações ocasionais de datas.  
- **Planejamento de eventos** – gerencie conferências de vários dias onde algumas sessões são canceladas ou remarcadas.

### Possibilidades de integração
Combine Aspose.Email com plataformas CRM, APIs de gerenciamento de tarefas ou motores de fluxo de trabalho personalizados para conduzir automação de ponta a ponta.

## Considerações de desempenho
- **Liberar recursos** – sempre chame `dispose()` em `PersonalStorage` para liberar manipuladores de arquivo.  
- **Uso de streams** – prefira `ByteArrayOutputStream` ou streams de arquivo para evitar carregar PSTs inteiros na memória.  
- **Operações assíncronas** – para geração em massa de calendários, execute a lógica de criação em uma thread em segundo plano para manter a UI responsiva.

## Conclusão
Seguindo este guia, você agora sabe como **criar mapi calendar java** com recorrência diária, adicionar exceções, anexar arquivos e armazenar tudo em um arquivo PST. Essas capacidades permitem construir recursos robustos de agendamento sem nunca tocar no Outlook diretamente.

### Próximos passos
- Experimente padrões de recorrência semanal ou mensal.  
- Explore propriedades MAPI adicionais, como participantes, lembretes e categorias.  
- Revise a documentação completa da API Aspose.Email para cenários mais avançados.

## Perguntas Frequentes

**Q: A biblioteca suporta compromissos com fuso horário?**  
A: Sim, você pode definir as propriedades `StartTimeZone` e `EndTimeZone` em `MapiCalendar`.

**Q: Posso excluir programaticamente uma única ocorrência de uma série recorrente?**  
A: Use a coleção `DeletedInstanceDates` no padrão de recorrência para marcar datas específicas como removidas.

**Q: Existem limites para o tamanho de um arquivo PST criado com Aspose.Email?**  
A: Arquivos PST seguem os limites do formato Unicode (até 2 GB por padrão), mas você pode configurar tamanhos maiores via configurações de `PersonalStorage`.

**Q: Como adiciono participantes a um convite de reunião?**  
A: Crie objetos `MapiRecipient`, defina seu `RecipientType` como `MapiRecipientType.MAPI_TO` e adicione‑os à coleção `Recipients` de `MapiMessage`.

**Q: Há suporte para tarefas recorrentes (não apenas compromissos)?**  
A: Sim, Aspose.Email também fornece `MapiTask` com capacidades de recorrência semelhantes.

## Recursos
- [Documentação Aspose.Email para Java](https://reference.aspose.com/email/java/)
- [Download Aspose.Email](https://releases.aspose.com/email/java/)
- [Comprar Licença](https://purchase.aspose.com/buy)
- [Versão de Teste Gratuita](https://releases.aspose.com/email/java/)
- [Solicitar Licença Temporária](https://purchase.aspose.com/temporary-license/)
- [Fórum de Suporte Aspose](https://forum.aspose.com/c/email/10)

---

**Última atualização:** 2025-12-20  
**Testado com:** Aspose.Email para Java 25.4 (JDK 16)  
**Autor:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
