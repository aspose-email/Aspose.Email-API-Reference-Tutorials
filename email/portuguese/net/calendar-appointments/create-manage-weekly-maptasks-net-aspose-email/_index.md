---
"date": "2025-05-30"
"description": "Aprenda a configurar e gerenciar tarefas recorrentes semanais com o Aspose.Email para .NET. Este guia aborda a criação, configuração e otimização de suas soluções de agendamento."
"title": "Como criar MapiTasks recorrentes semanais no .NET usando Aspose.Email"
"url": "/pt/net/calendar-appointments/create-manage-weekly-maptasks-net-aspose-email/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Como criar MapiTasks recorrentes semanais no .NET usando Aspose.Email

## Introdução

Gerenciar tarefas recorrentes com eficiência é crucial para desenvolvedores que trabalham com aplicativos que envolvem funcionalidades de agendamento ou calendário. Seja desenvolvendo uma ferramenta interna para gerenciamento de tarefas ou integrando recursos de calendário a um aplicativo corporativo, criar e gerenciar tarefas recorrentes semanais pode aumentar significativamente a produtividade.

Neste tutorial, exploraremos como usar **Aspose.Email para .NET** para criar MapiTasks recorrentes semanais com término em uma data específica. Este recurso é inestimável para desenvolvedores que buscam automatizar o agendamento em seus aplicativos usando as funcionalidades robustas do Aspose.Email.

### O que você aprenderá:
- Configurando e configurando o Aspose.Email para .NET
- Criando uma MapiTask recorrente semanal com uma data de término especificada
- Implementando padrões de recorrência de vários dias
- Calculando contagens de ocorrências com base em regras de recorrência personalizadas

Pronto para começar a criar soluções de agendamento poderosas? Vamos começar!

## Pré-requisitos

Antes de começar, certifique-se de ter o seguinte:

- **Aspose.Email para .NET** biblioteca: Você pode instalá-la usando o NuGet ou outros gerenciadores de pacotes.
- **.NET Framework 4.6.1 ou posterior** ou **.NET Core/5+**: Certifique-se de que seu ambiente de desenvolvimento esteja configurado com uma versão .NET compatível.
- Conhecimento básico de C# e familiaridade com conceitos de programação orientada a objetos.

## Configurando o Aspose.Email para .NET

Para começar a usar o Aspose.Email para .NET, você precisa adicioná-lo ao seu projeto. Veja como:

**Usando o .NET CLI:**
```bash
dotnet add package Aspose.Email
```

**Usando o Console do Gerenciador de Pacotes:**
```powershell
Install-Package Aspose.Email
```

**Interface do Gerenciador de Pacotes NuGet:**
- Procure por "Aspose.Email" e instale a versão mais recente.

### Aquisição de Licença

Você pode adquirir uma licença através de:

- **Teste grátis**: Teste recursos sem limitações.
- **Licença Temporária**: Use isto para avaliar capacidades estendidas.
- **Comprar**: Para acesso total, adquira uma licença comercial.

Depois de ter seu arquivo de licença, inicialize o Aspose.Email aplicando a licença em seu código:
```csharp
Aspose.Email.License license = new Aspose.Email.License();
license.SetLicense("path_to_license_file.lic");
```

## Guia de Implementação

Dividiremos a implementação em dois recursos principais: criação de uma recorrência semanal de um único dia e configuração de recorrências de vários dias.

### Criando uma MapiTask recorrente semanal que termina após uma data específica

#### Visão geral
Este recurso permite criar tarefas recorrentes em um dia específico da semana até o término em uma data específica. É perfeito para agendar reuniões ou prazos recorrentes.

#### Etapas de implementação
**Etapa 1: Configurar o Padrão de Recorrência**
Aqui, configuraremos o padrão de recorrência usando `MapiCalendarWeeklyRecurrencePattern`.
```csharp
var rec = new MapiCalendarWeeklyRecurrencePattern
{
    EndType = MapiCalendarRecurrenceEndType.EndAfterDate,
    PatternType = MapiCalendarRecurrencePatternType.Week,
    Period = 1, // Recorrência semanal
    WeekStartDay = DayOfWeek.Sunday,
    DayOfWeek = MapiCalendarDayOfWeek.Friday, // Recorre às sextas-feiras
    EndDate = new DateTime(2015, 9, 1).Add(TimeZone.CurrentTimeZone.GetUtcOffset(DateTime.Now)),
    OccurrenceCount = GetOccurrenceCount(
        new DateTime(2015, 7, 16).Add(TimeZone.CurrentTimeZone.GetUtcOffset(DateTime.Now)),
        new DateTime(2015, 9, 1).Add(TimeZone.CurrentTimeZone.GetUtcOffset(DateTime.Now)), 
        "FREQ=WEEKLY;BYDAY=FR;INTERVAL=1")
};
```
**Etapa 2: Crie a MapiTask**
Agora que configuramos nosso padrão de recorrência, vamos criar uma tarefa e atribuir esse padrão a ela.
```csharp
MapiTask task = new MapiTask(
    "This is test task",
    "Sample Body",
    new DateTime(2015, 7, 16).Add(TimeZone.CurrentTimeZone.GetUtcOffset(DateTime.Now)),
    new DateTime(2015, 7, 16).Add(TimeZone.CurrentTimeZone.GetUtcOffset(DateTime.Now))
);
task.State = MapiTaskState.NotAssigned;

if (rec.OccurrenceCount == 0)
{
    rec.OccurrenceCount = 1; // Garantir pelo menos uma ocorrência
}

task.Recurrence = rec;
```
**Etapa 3: Salve a tarefa**
Por fim, salve sua tarefa em um arquivo .msg para persistência.
```csharp
string dataDir = "YOUR_DOCUMENT_DIRECTORY";
task.Save(dataDir + "/SetWeeklyEndAfterDateEveryDayRecurrence_out.msg", TaskSaveFormat.Msg);
```

### Criando uma MapiTask recorrente semanal em vários dias terminando após uma data específica

#### Visão geral
Este recurso estende a configuração anterior para permitir tarefas que se repetem em vários dias da semana, fornecendo flexibilidade para necessidades de agendamento mais complexas.

#### Etapas de implementação
**Etapa 1: Configurar o Padrão de Recorrência de Vários Dias**
Crie um padrão que inclua vários dias de recorrência por semana.
```csharp
var record = new MapiCalendarWeeklyRecurrencePattern
{
    EndType = MapiCalendarRecurrenceEndType.EndAfterDate,
    PatternType = MapiCalendarRecurrencePatternType.Week,
    Period = 2, // Ocorre a cada duas semanas
    WeekStartDay = DayOfWeek.Sunday,
    EndDate = new DateTime(2015, 9, 1).Add(TimeZone.CurrentTimeZone.GetUtcOffset(DateTime.Now)),
    DayOfWeek = MapiCalendarDayOfWeek.Friday | MapiCalendarDayOfWeek.Monday, // Recorre às sextas e segundas-feiras
    OccurrenceCount = GetOccurrenceCount(
        new DateTime(2015, 7, 16).Add(TimeZone.CurrentTimeZone.GetUtcOffset(DateTime.Now)), 
        new DateTime(2015, 9, 1).Add(TimeZone.CurrentTimeZone.GetUtcOffset(DateTime.Now)), 
        "FREQ=WEEKLY;BYDAY=FR,MO;INTERVAL=2")
};
```
**Etapa 2: Criar e atribuir a MapiTask**
Semelhante ao anterior, crie uma tarefa e atribua esse padrão de vários dias.
```csharp
MapiTask task = new MapiTask(
    "This is test task",
    "Sample Body",
    new DateTime(2015, 7, 16).Add(TimeZone.CurrentTimeZone.GetUtcOffset(DateTime.Now)),
    new DateTime(2015, 7, 16).Add(TimeZone.CurrentTimeZone.GetUtcOffset(DateTime.Now))
);
task.State = MapiTaskState.NotAssigned;
task.Recurrence = record;
```
**Etapa 3: Salve a tarefa de vários dias**
Salve sua tarefa da mesma forma para garantir que ela seja armazenada corretamente.
```csharp
string dataDir = "YOUR_DOCUMENT_DIRECTORY";
task.Save(dataDir + "/SetWeeklyEndAfterDateMultipleDaysRecurrence_out.msg", TaskSaveFormat.Msg);
```

## Aplicações práticas

Aqui estão algumas aplicações práticas desses recursos:

1. **Automatizando Reuniões Semanais**: Agende reuniões recorrentes da equipe em dias específicos, como sextas-feiras.
2. **Prazos de entrega das tarefas**: Defina prazos semanais para tarefas do projeto que se repetem toda segunda e sexta-feira.
3. **Planejamento de eventos**Gerencie cronogramas de planejamento de eventos que exigem acompanhamentos em vários dias da semana.

## Considerações de desempenho

- **Otimizar o uso da memória**: Certifique-se de descartar os objetos corretamente para evitar vazamentos de memória, especialmente ao lidar com grandes conjuntos de dados ou inúmeras tarefas recorrentes.
- **Cálculos de data eficientes**: Use algoritmos eficientes para cálculos de data dentro de suas regras de recorrência para minimizar o tempo de processamento.
- **Operações Assíncronas**: Ao salvar tarefas em disco ou locais de rede, considere métodos assíncronos para melhorar o desempenho.

## Conclusão

Neste tutorial, abordamos como criar e gerenciar MapiTasks recorrentes semanais usando o Aspose.Email para .NET. Seguindo os passos descritos acima, você pode implementar facilmente recursos sofisticados de agendamento em seus aplicativos.

Para explorar mais os recursos do Aspose.Email ou lidar com cenários mais complexos, considere revisar sua documentação oficial e os fóruns da comunidade.

## Perguntas frequentes

**P: Como instalo o Aspose.Email para .NET?**
R: Você pode instalá-lo através do Gerenciador de Pacotes NuGet usando o comando `Install-Package Aspose.Email`.

**P: O que é uma MapiTask?**
R: Uma MapiTask representa uma tarefa do Outlook com propriedades como assunto, data de vencimento e padrão de recorrência.

**P: Posso personalizar ainda mais os padrões de recorrência?**
R: Sim, você pode usar diferentes tipos de recorrência, como diária ou mensal, ajustando o `PatternType` propriedade de `MapiCalendarRecurrencePattern`.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}