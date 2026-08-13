---
date: '2026-05-18'
description: Guia passo a passo sobre como criar item de calendário Java com Aspose.Email
  para Java, incluindo código para salvar como .ics, adicionar lembretes e trabalhar
  com MAPI.
keywords:
- how to create calendar item java
- Aspose.Email Java
- calendar item Java
- ICS format Java
- MAPI calendar Java
schemas:
- author: Aspose
  dateModified: '2026-05-18'
  description: Step‑by‑step guide on how to create calendar item java with Aspose.Email
    for Java, including code to save as .ics, add reminders, and work with MAPI.
  headline: How to Create Calendar Item Java Using Aspose.Email
  type: TechArticle
- description: Step‑by‑step guide on how to create calendar item java with Aspose.Email
    for Java, including code to save as .ics, add reminders, and work with MAPI.
  name: How to Create Calendar Item Java Using Aspose.Email
  steps:
  - name: '**Add Dependency:** Ensure your `pom.xml` includes the necessary dependency
      as shown above.'
    text: '**Add Dependency:** Ensure your `pom.xml` includes the necessary dependency
      as shown above.'
  - name: '**Download and Include JAR:** Alternatively, download the JAR file from
      [Aspose Downloads](https://releases.aspose.com/email/java/) and add it to your
      project’s classpath.'
    text: '**Download and Include JAR:** Alternatively, download the JAR file from
      [Aspose Downloads](https://releases.aspose.com/email/java/) and add it to your
      project’s classpath.'
  - name: '**License Setup:** If you have a license file, initialize it in your code
      to unlock full features:'
    text: '**License Setup:** If you have a license file, initialize it in your code
      to unlock full features:'
  - name: '**Initialize MapiCalendar:**'
    text: '**Initialize MapiCalendar:**'
  - name: '**Set Appointment Details:**'
    text: '**Set Appointment Details:**'
  - name: '**Define Start and End Dates:**'
    text: '**Define Start and End Dates:**'
  - name: '**Add Reminders (Optional):**'
    text: '**Add Reminders (Optional):**'
  - name: '**Save the Appointment:**'
    text: '**Save the Appointment:**'
  type: HowTo
- questions:
  - answer: Yes – set the `Recurrence` property on `MapiCalendar` and define the recurrence
      pattern (daily, weekly, etc.).
    question: Can I generate recurring appointments?
  - answer: Absolutely – use `MapiCalendar.fromFile("path.ics")` to load and manipulate
      existing calendar data.
    question: Is it possible to read existing .ics files?
  - answer: It does; the library converts UTC to the target zone based on the `TimeZoneInfo`
      object you provide.
    question: Does Aspose.Email support time‑zone conversion automatically?
  - answer: Attach a `MapiReminderAudio` object to the `Reminders` collection and
      specify the path to a .wav file.
    question: How do I add an audio reminder?
  - answer: Up to **2 GB** per file without performance degradation, thanks to streaming
      APIs.
    question: What is the maximum file size Aspose.Email can handle?
  type: FAQPage
title: Como criar item de calendário Java usando Aspose.Email
url: /pt/java/calendar-appointments/create-save-calendar-items-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Como Criar Item de Calendário Java Usando Aspose.Email

Em aplicações empresariais modernas, automatizar convites de reunião e entradas de calendário economiza inúmeras horas. Este tutorial mostra **how to create calendar item java** com Aspose.Email, cobrindo tudo, desde a inicialização de objetos até a gravação de um compromisso como um arquivo *.ics*, a adição de lembretes visuais e de áudio e a extração de status dos destinatários de mensagens MAPI. Ao final, você poderá incorporar funcionalidade de calendário totalmente equipada diretamente em seus serviços Java.

## Respostas Rápidas
- **Qual biblioteca é necessária?** Aspose.Email for Java (v25.4 ou posterior).  
- **Posso salvar como .ics?** Sim – chame `MapiCalendar.save(..., SaveOptions.getIcs())`.  
- **Preciso de licença para produção?** Uma licença válida do Aspose.Email remove as limitações de avaliação.  
- **Qual versão do Java é suportada?** JDK 8 + (incluindo Java 11 e 17).  
- **O Maven é suportado?** Absolutamente – adicione a dependência Maven ao `pom.xml`.

A classe `SaveOptions` fornece opções de gravação; `getIcs()` devolve as configurações para o formato iCalendar.

## Como Criar um Item de Calendário em Java?

Carregue a classe `MapiCalendar`, defina as propriedades necessárias (assunto, local, horários de início/fim) e chame `save` com o formato ICS – toda a operação pode ser realizada em menos de dez linhas de código. Aspose.Email lida automaticamente com a conversão de fuso horário e regras de recorrência, garantindo que o arquivo *.ics* gerado esteja em conformidade com a RFC 5545.

## Por que Usar Aspose.Email para Gerenciamento de Calendário?

Aspose.Email suporta **70+** formatos de e‑mail e calendário, processa arquivos de até **2 GB** sem carregar todo o documento na memória e oferece uma abordagem **single‑API** tanto para padrões MAPI quanto iCalendar. Essa capacidade quantificada permite gerar, modificar e ler itens de calendário em escala de forma confiável.

## Pré-requisitos
- **Java Development Kit (JDK):** Versão 8 ou superior.  
- **Maven:** Para gerenciamento de dependências.  
- **Aspose.Email for Java:** Versão 25.4 ou mais recente (recomenda‑se a última versão).

## Configuração do Ambiente

Para incluir Aspose.Email em seu projeto Maven, adicione a dependência a seguir ao seu `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

## Aquisição de Licença

Aspose.Email oferece uma licença de avaliação gratuita que remove a maioria das restrições de avaliação. Para uso em produção, adquira uma assinatura ou solicite uma licença temporária para testes.

## Configurando Aspose.Email para Java

1. **Adicionar Dependência:** Certifique‑se de que seu `pom.xml` inclui a dependência necessária conforme mostrado acima.  
2. **Baixar e Incluir o JAR:** Alternativamente, baixe o arquivo JAR em [Aspose Downloads](https://releases.aspose.com/email/java/) e adicione‑o ao classpath do seu projeto.  
3. **Configuração da Licença:** Se você possui um arquivo de licença, inicialize‑o em seu código para desbloquear todos os recursos:

   ```java
   License license = new License();
   license.setLicense("Path_to_Aspose.Email_License_File");
   ```

A classe `License` carrega e aplica um arquivo de licença Aspose.Email, habilitando o uso completo dos recursos.

## Guia de Implementação

A seguir, percorremos as etapas principais necessárias para **create calendar item java** objetos, enriquecê‑los com lembretes e persistir como arquivos *.ics*.

### Criando e Salvando Itens de Calendário

#### Visão Geral
Esta seção demonstra como construir programaticamente um compromisso de calendário, anexar lembretes de exibição e áudio e salvar o resultado no formato iCalendar universal.

#### Implementação Passo a Passo

1. **Inicializar MapiCalendar:**  
   A classe `MapiCalendar` representa um objeto de calendário no formato MAPI. Ela serve como ponto de entrada para definir todas as propriedades do compromisso.

   ```java
   MapiCalendar appointment = new MapiCalendar();
   ```

2. **Definir Detalhes do Compromisso:**  
   Forneça um assunto claro, local e corpo descritivo para a reunião.

   ```java
   appointment.setLocation("LAKE ARGYLE WA 6743");
   appointment.setSubject("Appointment");
   appointment.setBody("This is a very important meeting");
   ```

3. **Definir Datas de Início e Fim:**  
   Use `GregorianCalendar` para especificar os timestamps exatos de início e fim, levando em conta considerações de fuso horário.

   ```java
   Calendar cal = GregorianCalendar.getInstance();
   cal.set(2016, 10, 2); // Month is zero-based.
   Date startDate = cal.getTime();

   cal.setTime(startDate);
   cal.add(Calendar.DAY_OF_MONTH, 1); // End date is one day later.
   Date endDate = cal.getTime();

   appointment.setStartDate(startDate);
   appointment.setEndDate(endDate);
   ```

4. **Adicionar Lembretes (Opcional):**  
   Você pode anexar um lembrete visual (pop‑up) e um lembrete de áudio (arquivo wav) para melhorar a notificação dos participantes.  
   *Dica:* Defina `ReminderMinutesBeforeStart` como `15` para um aviso de 15 minutos antes do início.  
   A classe `MapiReminderAudio` representa um lembrete de áudio anexado a um item de calendário.

5. **Salvar o Compromisso:**  
   Persista o item de calendário como um arquivo *.ics* na pasta de saída desejada.

   ```java
   String dataDir = "YOUR_OUTPUT_DIRECTORY/";
   appointment.save(dataDir + "CalendarItem_out.ics\
   ```

## Armadilhas Comuns e Dicas

- **Descompasso de fusos horários:** Sempre especifique o fuso horário ao definir `StartDate` e `EndDate` para evitar erros de horário de verão.  
- **Listas grandes de participantes:** Para reuniões com mais de 200 participantes, use o loteamento `MapiRecipientCollection` para permanecer dentro dos limites de memória.  
  A classe `MapiRecipientCollection` contém uma lista de participantes da reunião.  
- **Licença ausente:** Se o arquivo de licença não for carregado, a API reverte para o modo de avaliação que limita o número de itens salvos a **10** por execução.

## Perguntas Frequentes

**Q: Posso gerar compromissos recorrentes?**  
A: Sim – defina a propriedade `Recurrence` em `MapiCalendar` e especifique o padrão de recorrência (diário, semanal etc.).

**Q: É possível ler arquivos .ics existentes?**  
A: Absolutamente – use `MapiCalendar.fromFile("path.ics")` para carregar e manipular dados de calendário existentes.

**Q: O Aspose.Email suporta conversão automática de fusos horários?**  
A: Sim; a biblioteca converte UTC para o fuso alvo com base no objeto `TimeZoneInfo` fornecido.

**Q: Como adiciono um lembrete de áudio?**  
A: Anexe um objeto `MapiReminderAudio` à coleção `Reminders` e especifique o caminho para um arquivo .wav.

**Q: Qual é o tamanho máximo de arquivo que o Aspose.Email pode manipular?**  
A: Até **2 GB** por arquivo sem degradação de desempenho, graças às APIs de streaming.

---

**Last Updated:** 2026-05-18  
**Tested With:** Aspose.Email for Java 25.4  
**Author:** Aspose

## Tutoriais Relacionados

- [Manage Calendar Sharing - Aspose.Email for Java Guide](/email/java/calendar-appointments/create-send-calendar-invitations-aspose-email-java/)
- [How to Extract Outlook Calendar Items to ICS Using Aspose.Email for Java](/email/java/calendar-appointments/extract-outlook-calendar-to-ics-aspose-email-java/)
- [How to Read Multiple Calendar Events from an ICS File Using Aspose.Email in Java](/email/java/calendar-appointments/read-multiple-ics-events-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}