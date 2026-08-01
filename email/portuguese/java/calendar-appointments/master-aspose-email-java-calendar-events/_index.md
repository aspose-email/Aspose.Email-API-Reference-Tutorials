---
date: '2026-08-01'
description: Aprenda como exportar calendário para PST com Aspose.Email for Java,
  incluindo como adicionar participantes, definir datas de início e término e gerenciar
  compromissos de forma eficiente.
keywords:
- export calendar to pst
- export recurring appointments
- Aspose.Email Java Calendar Events
lastmod: '2026-08-01'
og_description: Exportar calendário para PST usando Aspose.Email for Java. Aprenda
  passo a passo como criar compromissos, adicionar participantes e gerar arquivos
  PST do Outlook.
og_image_alt: 'Developer guide: Export calendar to PST using Aspose.Email for Java'
og_title: Exportar calendário para PST – Guia completo com Aspose.Email for Java
schemas:
- author: Aspose
  dateModified: '2026-08-01'
  description: Learn how to export calendar to PST with Aspose.Email for Java, including
    how to add attendees, set start and end dates, and manage appointments efficiently.
  headline: Export calendar to PST with Aspose.Email for Java
  type: TechArticle
- description: Learn how to export calendar to PST with Aspose.Email for Java, including
    how to add attendees, set start and end dates, and manage appointments efficiently.
  name: Export calendar to PST with Aspose.Email for Java
  steps:
  - name: '**Free Trial**: Visit the [Aspose download page](https://releases.aspose.com/email/java/)
      for a temporary license.'
    text: '**Free Trial**: Visit the [Aspose download page](https://releases.aspose.com/email/java/)
      for a temporary license.'
  - name: '**Temporary License**: Apply via the [purchase page](https://purchase.aspose.com/temporary-license/).'
    text: '**Temporary License**: Apply via the [purchase page](https://purchase.aspose.com/temporary-license/).'
  - name: '**Purchase License**: Consider purchasing from [Aspose''s purchase portal](https://purchase.aspose.com/buy)
      for long‑term use.'
    text: '**Purchase License**: Consider purchasing from [Aspose''s purchase portal](https://purchase.aspose.com/buy)
      for long‑term use.'
  - name: '**Business Scheduling** – Automate internal meeting creation and distribution.'
    text: '**Business Scheduling** – Automate internal meeting creation and distribution.'
  - name: '**Event Management** – Track conferences, workshops, and participant lists.'
    text: '**Event Management** – Track conferences, workshops, and participant lists.'
  - name: '**CRM Integration** – Sync appointments with customer relationship tools.'
    text: '**CRM Integration** – Sync appointments with customer relationship tools.'
  - name: '**Project Planning** – Store project milestones as calendar items.'
    text: '**Project Planning** – Store project milestones as calendar items.'
  - name: '**Remote Team Collaboration** – Generate PST files for offline sharing.'
    text: '**Remote Team Collaboration** – Generate PST files for offline sharing.'
  type: HowTo
- questions:
  - answer: Add the Maven dependency shown above, obtain a license, and follow the
      steps in this guide to create and export calendar events.
    question: How do I get started with Aspose.Email for Java?
  - answer: Yes, change the `pstFilePath` variable in `createPSTWithCalendarEvents()`
      to any valid path on your system.
    question: Can I customize the PST file name and location?
  - answer: Absolutely – `MapiCalendar` exposes a `RecurrencePattern` property that
      you can configure before saving.
    question: Is it possible to add recurrence patterns to appointments?
  - answer: Yes, you can export to iCalendar (`.ics`) and other formats using the
      appropriate API methods.
    question: Does Aspose.Email support other calendar formats besides PST?
  - answer: With the Unicode format (`FileFormatVersion.Unicode`), PST files can grow
      up to 2 TB, limited only by available disk space.
    question: What is the maximum size of a PST file I can create?
  type: FAQPage
tags:
- export calendar to pst
- Aspose.Email
- Java calendar appointments
title: Exportar calendário para PST com Aspose.Email for Java
url: /pt/java/calendar-appointments/master-aspose-email-java-calendar-events/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Exportar calendário para PST com Aspose.Email para Java

Se você está desenvolvendo uma aplicação Java que precisa compartilhar dados de agendamento com o Outlook, frequentemente precisará **exportar calendário para PST**. Neste tutorial, percorreremos tudo o que você precisa — desde criar um compromisso simples até adicionar participantes e, finalmente, gravar os eventos em um arquivo PST, tudo com Aspose.Email para Java. Ao final, você terá uma solução pronta para produção que funciona no Windows, Linux e macOS.

## Respostas Rápidas
- **Qual é o objetivo principal?** Exportar eventos de calendário para um arquivo PST.  
- **Qual biblioteca é necessária?** Aspose.Email for Java (v25.4+).  
- **Preciso de uma licença?** Sim, uma licença válida do Aspose.Email remove as limitações de avaliação.  
- **Posso adicionar participantes?** Absolutamente – use `MapiRecipientCollection`.  
- **Qual versão do Java é suportada?** JDK 16 ou superior.

## O que é **exportar calendário para pst**?
`MapiCalendar` é a classe do Aspose.Email que modela um item de calendário do Outlook, incluindo assunto, local e detalhes de horário.

Exportar um calendário para PST significa converter objetos `MapiCalendar` em memória em uma Microsoft Outlook Personal Storage Table (PST). O arquivo PST gerado pode ser aberto diretamente no Outlook, compartilhado com colegas ou importado para qualquer sistema que compreenda o formato PST, preservando todos os detalhes do evento, como participantes, recorrência e lembretes.

## Por que usar Aspose.Email para Java para exportar calendário para PST?
Você pode gerar um arquivo PST totalmente compatível sem instalar o Outlook. Aspose.Email fornece **suporte total ao MAPI**, funciona em **todos os principais sistemas operacionais** e pode lidar com **até 2 TB** de dados no formato PST Unicode — suficiente para arquivos de escala empresarial. A API também permite gerenciar participantes, padrões de recorrência, lembretes e propriedades personalizadas com apenas algumas chamadas de método, reduzindo drasticamente o esforço de desenvolvimento.

## Pré-requisitos
- **Bibliotecas e Dependências**: Aspose.Email for Java versão 25.4 ou posterior.  
- **Ambiente**: JDK 16 ou superior, Maven para gerenciamento de dependências.  
- **Conhecimento**: Programação Java básica e familiaridade com Maven.

## Como configurar Aspose.Email para Java
Adicione a dependência Aspose.Email ao seu `pom.xml` e atualize seu projeto Maven. Esta única etapa torna toda a API MAPI disponível no seu classpath.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

```xml
<dependency>
  <groupId>com.aspose</groupId>
  <artifactId>aspose-email</artifactId>
  <version>25.4</version>
  <classifier>jdk16</classifier>
</dependency>
```

### Aquisição de Licença
Desbloqueie a funcionalidade completa do Aspose.Email sem limitações de avaliação adquirindo uma licença:

1. **Teste Gratuito**: Visite a [página de download da Aspose](https://releases.aspose.com/email/java/) para uma licença temporária.  
2. **Licença Temporária**: Solicite através da [página de compra](https://purchase.aspose.com/temporary-license/).  
3. **Compra de Licença**: Considere comprar no [portal de compras da Aspose](https://purchase.aspose.com/buy) para uso a longo prazo.

Depois de obter sua licença, inicialize-a em sua aplicação para habilitar todos os recursos.

## Como **criar compromisso** (Criar Evento de Calendário Java)
Carregue um objeto `MapiCalendar`, defina suas propriedades principais e retorne-o pronto para processamento adicional. Este método cria uma entrada de calendário com assunto, local, descrição e a **data de início do calendário java** / **data de término do calendário java** que você definiu.

```java
public static MapiCalendar createAppointment(String subject, String location,
                                             String description, Calendar start, Calendar end) {
    MapiCalendar appointment = new MapiCalendar();
    appointment.setSubject(subject);
    appointment.setLocation(location);
    appointment.setBody(description);
    appointment.setStartDate(start);
    appointment.setEndDate(end);
    return appointment;
}
```

```java
import com.aspose.email.MapiCalendar;
import java.util.Calendar;
import java.util.Date;

public MapiCalendar createAppointment() {
    Calendar cal = Calendar.getInstance();
    
    // Setting the start date
    cal.set(Calendar.YEAR, 2023);
    cal.set(Calendar.MONTH, Calendar.OCTOBER);
    cal.set(Calendar.DAY_OF_MONTH, 1);
    Date startDate = cal.getTime();
    
    // Setting the end date
    cal.set(Calendar.HOUR_OF_DAY, 10);
    Date endDate = cal.getTime();
    
    return new MapiCalendar("Conference Room", "Important Meeting",
        "Discuss project milestones and updates.", startDate, endDate);
}
```

*Explicação*: A classe `MapiCalendar` é a representação do Aspose.Email de um item de calendário do Outlook. Após definir os campos básicos, você também pode configurar recorrência, lembretes e categorias antes de salvar.

## Como **adicionar participantes** (java adicionar participantes da reunião)
Crie um `MapiRecipientCollection`, preencha-o com cada participante e anexe-o à reunião. Isso garante que cada participante receba um convite adequado quando o PST for aberto.

`MapiRecipientCollection` é uma classe de coleção que contém objetos `MapiRecipient` representando participantes da reunião. `MapiRecipient` representa um participante individual com propriedades como endereço de e‑mail e tipo de destinatário.

```java
public static MapiRecipientCollection buildAttendees(List<String> emails) {
    MapiRecipientCollection attendees = new MapiRecipientCollection();
    for (String email : emails) {
        MapiRecipient recipient = new MapiRecipient(email, email, MapiRecipientType.MAPI_TO);
        attendees.add(recipient);
    }
    return attendees;
}
```

```java
import com.aspose.email.MapiCalendar;
import com.aspose.email.MapiRecipientCollection;
import com.aspose.email.MapiRecipientType;
import java.util.Date;

public MapiCalendar createMeetingWithAttendees(Date startDate, Date endDate) {
    MapiRecipientCollection attendees = new MapiRecipientCollection();
    
    // Adding primary recipients
    attendees.add("attendee1@example.com", "John Doe", MapiRecipientType.MAPI_TO);
    attendees.add("attendee2@example.com", "Jane Smith", MapiRecipientType.MAPI_TO);
    
    return new MapiCalendar(
        "Main Office Boardroom",
        "Team Meeting",
        "Discuss quarterly goals.",
        startDate,
        endDate,
        "organizer@example.com",
        attendees
    );
}
```

*Explicação*: `MapiRecipient` define um único participante da reunião. Definir o tipo como `MAPI_TO` marca o endereço como participante principal, enquanto `MAPI_CC` ou `MAPI_BCC` podem ser usados para participantes opcionais.

## Como **exportar calendário para pst** (Criar PST com eventos de calendário)
Crie um arquivo PST Unicode, adicione uma pasta "Calendário" e insira os objetos `MapiCalendar` construídos anteriormente. O PST pode então ser aberto no Outlook ou distribuído aos usuários finais.

`PersonalStorage` é a classe do Aspose.Email usada para criar, abrir e manipular arquivos PST.

```java
public static void createPSTWithCalendarEvents(String pstFilePath,
                                                List<MapiCalendar> events) throws Exception {
    // Create a new Unicode PST (supports up to 2 TB)
    PersonalStorage pst = PersonalStorage.create(pstFilePath, FileFormatVersion.Unicode);
    // Add the default Calendar folder
    FolderInfo calendarFolder = pst.getRootFolder().addSubFolder("Calendar", 
                                   StandardIpmFolder.Calendar);
    // Insert each event
    for (MapiCalendar event : events) {
        calendarFolder.addMapiMessageItem(event);
    }
}
```

```java
import com.aspose.email.FileFormatVersion;
import com.aspose.email.FolderInfo;
import com.aspose.email.PersonalStorage;
import com.aspose.email.StandardIpmFolder;

public void createPSTWithCalendarEvents() {
    String pstFilePath = "/path/to/output/MapiCalendarToPST_out.pst";
    
    PersonalStorage pst = PersonalStorage.create(pstFilePath, FileFormatVersion.Unicode);
    FolderInfo calendarFolder = pst.createPredefinedFolder("Calendar", StandardIpmFolder.Appointments);

    MapiCalendar appointment = createAppointment();
    calendarFolder.addMapiMessageItem(appointment);
    
    Date startDate = new Date(); // Use actual dates from your event
    Date endDate = new Date();
    MapiCalendar meeting = createMeetingWithAttendees(startDate, endDate);
    calendarFolder.addMapiMessageItem(meeting);
}
```

*Explicação*: `PersonalStorage` é o ponto de entrada para manipulação de PST. Ao usar o formato Unicode, você evita o limite de 2 GB das versões mais antigas de PST e se beneficia de I/O mais rápido em grandes arquivos.

## Aplicações Práticas
1. **Agendamento Empresarial** – Automatizar a criação e distribuição de reuniões internas.  
2. **Gestão de Eventos** – Rastrear conferências, workshops e listas de participantes.  
3. **Integração CRM** – Sincronizar compromissos com ferramentas de relacionamento com o cliente.  
4. **Planejamento de Projetos** – Armazenar marcos do projeto como itens de calendário.  
5. **Colaboração de Equipes Remotas** – Gerar arquivos PST para compartilhamento offline.

## Considerações de Desempenho
- **Descartar objetos** que você não precisa mais para liberar memória prontamente.  
- **Usar coleções eficientes** (por exemplo, `ArrayList` para listas de participantes) ao lidar com milhares de participantes.  
- **Cachear eventos acessados com frequência** se você consultar o PST repetidamente, reduzindo I/O de disco.

## Problemas Comuns e Soluções
| Problema | Solução |
|----------|----------|
| **Arquivo PST não criado** | Verifique as permissões de gravação no diretório de destino e assegure que o caminho da pasta exista. |
| **Participantes não recebem convites** | Confirme que cada `MapiRecipient` usa `MapiRecipientType.MAPI_TO` e que o e‑mail do organizador é válido. |
| **Incompatibilidade de datas** | Use `Calendar` consistentemente para datas de início/fim; evite misturar `java.util.Date` com outras bibliotecas de data sem conversão. |

## Perguntas Frequentes

**Q: Como começar a usar o Aspose.Email para Java?**  
A: Adicione a dependência Maven mostrada acima, obtenha uma licença e siga os passos deste guia para criar e exportar eventos de calendário.

**Q: Posso personalizar o nome e o local do arquivo PST?**  
A: Sim, altere a variável `pstFilePath` em `createPSTWithCalendarEvents()` para qualquer caminho válido no seu sistema.

**Q: É possível adicionar padrões de recorrência aos compromissos?**  
A: Absolutamente – `MapiCalendar` expõe a propriedade `RecurrencePattern` que você pode configurar antes de salvar.

**Q: O Aspose.Email suporta outros formatos de calendário além de PST?**  
A: Sim, você pode exportar para iCalendar (`.ics`) e outros formatos usando os métodos de API apropriados.

**Q: Qual é o tamanho máximo de um arquivo PST que eu posso criar?**  
A: Com o formato Unicode (`FileFormatVersion.Unicode`), os arquivos PST podem crescer até 2 TB, limitados apenas pelo espaço disponível em disco.

---

**Última Atualização:** 2026-08-01  
**Testado com:** Aspose.Email for Java 25.4 (jdk16 classifier)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriais Relacionados

- [Domine Aspose.Email para Java: Gerencie eficientemente arquivos PST do Outlook](/email/java/outlook-pst-ost-operations/aspose-email-java-manage-outlook-pst-files/)
- [Domine a Criação e Salvamento de Itens de Calendário com Aspose.Email para Java](/email/java/calendar-appointments/create-save-calendar-items-aspose-email-java/)
- [Como Ler Múltiplos Eventos de Calendário de um Arquivo ICS Usando Aspose.Email em Java](/email/java/calendar-appointments/read-multiple-ics-events-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}