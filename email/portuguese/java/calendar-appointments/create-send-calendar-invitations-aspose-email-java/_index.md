---
date: '2026-09-17'
description: Como criar convite de calendário com Aspose.Email for Java permite que
  você compartilhe calendários, defina permissões de delegado e envie e‑mails de compartilhamento
  programaticamente.
keywords:
- how to create calendar invitation
- calendar sharing invitation
- Aspose.Email Java
- delegate calendar permissions
lastmod: '2026-09-17'
og_description: Como criar convite de calendário com Aspose.Email for Java permite
  que você compartilhe calendários programaticamente, defina permissões de delegado
  e envie e‑mails de compartilhamento via Exchange Web Services, melhorando a colaboração
  da equipe.
og_image_alt: Guide showing how to create calendar invitation with Aspose.Email for
  Java
og_title: Como criar convite de calendário com Aspose.Email for Java
schemas:
- author: Aspose
  dateModified: '2026-09-17'
  description: How to create calendar invitation with Aspose.Email for Java lets you
    share calendars, set delegate permissions, and send sharing emails programmatically.
  headline: How to create calendar invitation with Aspose.Email for Java
  type: TechArticle
- description: How to create calendar invitation with Aspose.Email for Java lets you
    share calendars, set delegate permissions, and send sharing emails programmatically.
  name: How to create calendar invitation with Aspose.Email for Java
  steps:
  - name: Install JDK if you haven't already. You can download it from [Oracle's official
      site](https://www.oracle.com/java/technologies/javase-downloads.html).
    text: Install JDK if you haven't already. You can download it from [Oracle's official
      site](https://www.oracle.com/java/technologies/javase-downloads.html).
  - name: Ensure Maven is installed and configured on your machine.
    text: Ensure Maven is installed and configured on your machine.
  - name: Choose an IDE such as IntelliJ IDEA or Eclipse for easier development.
    text: Choose an IDE such as IntelliJ IDEA or Eclipse for easier development.
  - name: '**Corporate meetings** – Let team members view meeting schedules without
      giving full mailbox rights.'
    text: '**Corporate meetings** – Let team members view meeting schedules without
      giving full mailbox rights.'
  - name: '**Project management** – Project leads can monitor timelines while developers
      retain control of their own calendars.'
    text: '**Project management** – Project leads can monitor timelines while developers
      retain control of their own calendars.'
  - name: '**Event planning** – Vendors receive a **calendar sharing email** to coordinate
      logistics without exposing internal details.'
    text: '**Event planning** – Vendors receive a **calendar sharing email** to coordinate
      logistics without exposing internal details.'
  type: HowTo
- questions:
  - answer: It’s a comprehensive library for handling emails, calendars, and contacts
      in Java applications, supporting Outlook, Exchange, and other protocols.
    question: What is Aspose.Email for Java used for?
  - answer: Install JDK 16+, Maven, add the Aspose.Email dependency to `pom.xml`,
      and obtain a license (trial or full).
    question: How do I set up my environment for using Aspose.Email?
  - answer: Yes, but verify the service URL and permission levels match your server’s
      configuration.
    question: Can I use this code with other versions of Exchange Online?
  - answer: Check network connectivity, credentials, and that the delegate user has
      valid permissions. Review exception details for clues.
    question: What should I do if the calendar sharing invitation fails to send?
  - answer: Absolutely – replace `ExchangeDelegateFolderPermissionLevel.Reviewer`
      with `Editor`, `Author`, or `Owner` as needed.
    question: Is it possible to add additional permissions like editing or full access?
  type: FAQPage
tags:
- calendar sharing
- Aspose.Email
- Java email API
- delegate permissions
- EWS client
title: Como criar convite de calendário com Aspose.Email for Java
url: /pt/java/calendar-appointments/create-send-calendar-invitations-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gerenciar compartilhamento de calendário: Guia Aspose.Email para Java

## Introdução ao gerenciamento de compartilhamento de calendário
Gerenciar convites de compartilhamento de calendário pode ser uma tarefa complexa, especialmente ao lidar com vários usuários em diferentes plataformas. Neste tutorial você **criará convite de compartilhamento de calendário** com Aspose.Email para Java, cobrindo tudo, desde a criação de acesso delegado até o envio de e‑mails de compartilhamento de calendário. Ao final, você será capaz de definir permissões de delegado, **configurar permissões de calendário** e simplificar a colaboração em sua organização.

**O que você aprenderá**
- Como inicializar o cliente EWS com Aspose.Email para Java  
- Criar um usuário delegado e **definir permissões de delegado**  
- **Criar acesso delegado** e configurar permissões de calendário  
- Enviar um **e‑mail de compartilhamento de calendário** (convite) programaticamente  
- Cenários do mundo real onde esses recursos agregam valor  

Antes de mergulharmos, vamos garantir que você tem tudo o que precisa.

## Respostas rápidas
- **Qual é o objetivo principal deste guia?** Mostrar como **criar convite de compartilhamento de calendário** usando Aspose.Email para Java.  
- **Qual versão da biblioteca é necessária?** Aspose.Email para Java 25.4 (classificador JDK 16).  
- **Preciso de licença?** Sim – uma licença de avaliação ou completa é necessária para uso em produção.  
- **Qual ambiente é necessário?** JDK 16+, Maven e uma conta Exchange Online.  
- **Posso usar isso com outros servidores Exchange?** Sim, mas pode ser necessário ajustar a URL do serviço e os níveis de permissão.

## O que é um convite de compartilhamento de calendário?
Um convite de compartilhamento de calendário é uma mensagem de e‑mail que concede a outro usuário acesso para visualizar (ou editar) seu calendário sem conceder direitos completos de caixa de correio. Ele permite que membros da equipe vejam sua agenda, proponham reuniões ou gerenciem eventos, mantendo sua caixa de correio segura.

## Por que configurar permissões de calendário?
Configurar permissões de calendário permite que você controle exatamente o que um delegado pode fazer — se ele pode apenas ler eventos, propor novos ou editar entradas existentes. Configurações adequadas de permissão protegem informações sensíveis enquanto possibilitam colaboração eficaz. Por exemplo, conceder acesso somente leitura impede alterações acidentais, enquanto direitos de edição permitem que o delegado agende ou modifique reuniões em seu nome.

## Pré-requisitos
- **Java Development Kit (JDK):** Versão 16 ou superior.  
- **Maven:** Para gerenciamento de dependências e construção do projeto.  
- **Aspose.Email para Java:** Versão 25.4 com suporte ao JDK 16.  

### Requisitos de configuração do ambiente
1. Instale o JDK se ainda não o fez. Você pode baixá‑lo em [site oficial da Oracle](https://www.oracle.com/java/technologies/javase-downloads.html).  
2. Certifique‑se de que o Maven está instalado e configurado em sua máquina.  
3. Escolha uma IDE como IntelliJ IDEA ou Eclipse para facilitar o desenvolvimento.

### Pré-requisitos de conhecimento
- Habilidades básicas de programação Java  
- Familiaridade com dependências Maven  
- Opcional: Experiência com Exchange Web Services (EWS)

## Configurando Aspose.Email para Java
### Configuração do Maven
Adicione a seguinte dependência ao seu arquivo `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Aquisição de licença
Aspose.Email para Java requer uma licença para funcionalidade completa. Você pode:
- **Teste gratuito:** Baixe em [página de releases da Aspose](https://releases.aspose.com/email/java/).  
- **Licença temporária:** Solicite uma chave temporária no site da Aspose.  
- **Compra:** Obtenha uma licença permanente para implantações de produção.

### Inicialização e configuração básicas
Depois que o Maven resolver a dependência, inicialize o cliente EWS:

`ExchangeService` é a classe principal usada para comunicar‑se com o Exchange Web Services.  

```java
IEWSClient client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser", "pwd", "domain");
```

## Como criar convite de compartilhamento de calendário
Para criar um convite de compartilhamento de calendário, primeiro conecte‑se ao Exchange usando o cliente `ExchangeService`, então defina um delegado com o nível de permissão desejado e, finalmente, componha um `MailMessage` que inclua a solicitação de compartilhamento. Os passos a seguir demonstram esse fluxo de trabalho em Java.

A seguir, cobrimos duas funcionalidades principais: criar e enviar um convite de compartilhamento de calendário, e **definir permissões de delegado** para acesso ao calendário.

### Recurso 1: criar e enviar convite de compartilhamento de calendário
#### Visão geral
Este recurso orienta você na inicialização do cliente, **criar acesso delegado**, e enviar o e‑mail de convite.

#### Implementação passo a passo
##### 1️⃣ Inicializar cliente EWS
`ExchangeService` representa a conexão com um servidor Exchange e é usado para enviar e receber mensagens.  

```java
IEWSClient client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser", "pwd", "domain");
```  
Isso conecta seu aplicativo Java ao Exchange Online.

##### 2️⃣ Criar usuário delegado
`DelegateUser` define o endereço de e‑mail do delegado e o nível de permissão a ser concedido.  

```java
ExchangeDelegateUser delegateUser = new ExchangeDelegateUser("sharingfrom@domain.com", ExchangeDelegateFolderPermissionLevel.NotSpecified);
delegateUser.getFolderPermissions().setCalendarFolderPermissionLevel(ExchangeDelegateFolderPermissionLevel.Reviewer);
client.delegateAccess(delegateUser, "sharingfrom@domain.com");
```  
Aqui nós **criamos acesso delegado** e atribuímos o nível `Reviewer`, que permite ao delegado visualizar itens do calendário.

##### 3️⃣ Enviar convite de compartilhamento de calendário
`MailMessage` constrói o e‑mail que transporta o convite de compartilhamento de calendário.  

```java
MapiMessage mapiMessage = client.createCalendarSharingInvitationMessage("sharingfrom@domain.com");

MailConversionOptions options = new MailConversionOptions();
options.setConvertAsTnef(true);

MailMessage mail = mapiMessage.toMailMessage(options);
client.send(mail);
```  
O código cria um **e‑mail de compartilhamento de calendário** (convite) e o envia via cliente EWS.

### Recurso 2: permissão de acesso ao calendário delegado
#### Visão geral
Esta seção mostra como **configurar permissões de calendário** e garantir que o delegado tenha os direitos corretos.

#### Etapas de implementação
##### 1️⃣ Inicializar cliente EWS (reutilizar)
`ExchangeService` pode ser reutilizado para múltiplas operações após a configuração inicial.  

```java
IEWSClient client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser", "pwd", "domain");
```  

##### 2️⃣ Criar e definir permissões de delegado
`ExchangeDelegateFolderPermissionLevel` enumera os níveis de acesso que um delegado pode ter a uma pasta de calendário.  

```java
ExchangeDelegateUser delegateUser = new ExchangeDelegateUser("sharingfrom@domain.com", ExchangeDelegateFolderPermissionLevel.NotSpecified);
delegateUser.getFolderPermissions().setCalendarFolderPermissionLevel(ExchangeDelegateFolderPermissionLevel.Reviewer);

client.delegateAccess(delegateUser, "sharingfrom@domain.com");
```  
Este trecho **define permissões de delegado** para que o usuário possa visualizar entradas do calendário sem acesso total à caixa de correio.

## Como configurar permissões de calendário para delegados
Quando um delegado precisa de mais que acesso somente leitura, você pode ajustar o `ExchangeDelegateFolderPermissionLevel` para conceder direitos de edição, autor ou proprietário. Escolha o nível mínimo que satisfaça a necessidade de negócio para manter a segurança enquanto fornece a funcionalidade necessária. Por exemplo, atribuir o nível Editor permite ao delegado criar, modificar e excluir eventos, enquanto o nível Reviewer apenas permite visualização.

- `Reviewer` – acesso somente leitura.  
- `Editor` – acesso leitura/escrita.  
- `Author` – criar e ler, mas não excluir.  
- `Owner` – controle total, incluindo alterações de permissão.  

**Dica profissional:** Use o nível de privilégio mínimo que atenda ao requisito de negócio para manter seus dados de calendário seguros.

## Aplicações práticas
Cenários do mundo real onde **gerenciar compartilhamento de calendário** se destaca:
1. **Reuniões corporativas** – Permita que membros da equipe visualizem agendas de reuniões sem conceder direitos completos de caixa de correio.  
2. **Gerenciamento de projetos** – Líderes de projeto podem monitorar cronogramas enquanto desenvolvedores mantêm controle de seus próprios calendários.  
3. **Planejamento de eventos** – Fornecedores recebem um **e‑mail de compartilhamento de calendário** para coordenar a logística sem expor detalhes internos.

## Considerações de desempenho
- **Gerenciamento de memória:** Libere objetos grandes de `MailMessage` prontamente em aplicativos de alto volume.  
- **Tratamento de exceções:** Envolva chamadas de rede em blocos try‑catch para lidar com falhas de conectividade de forma elegante.  
- **Atualizações da biblioteca:** Aspose.Email para Java suporta mais de 50 protocolos e pode processar calendários com até 10 000 itens sem carregar o arquivo inteiro na memória, portanto mantenha a biblioteca atualizada para aproveitar melhorias de desempenho e correções de bugs.

## Problemas comuns e soluções
| Problema | Causa provável | Solução |
|----------|----------------|---------|
| Convite não recebido | Filtros de spam ou endereço de e‑mail incorreto | Verifique o endereço do destinatário e adicione o domínio de envio à lista de remetentes seguros |
| Permissão não aplicada | Uso do `ExchangeDelegateFolderPermissionLevel` errado | Confirme se o nível de permissão corresponde ao acesso requerido |
| Exceção em tempo de execução ao `createCalendarSharingInvitationMessage` | Licença ausente ou biblioteca desatualizada | Garanta que uma licença válida esteja carregada e que você esteja usando a versão mais recente do Aspose.Email |

## Perguntas frequentes
**P: Para que serve o Aspose.Email para Java?**  
R: É uma biblioteca abrangente para manipular e‑mails, calendários e contatos em aplicações Java, suportando Outlook, Exchange e outros protocolos.

**P: Como configuro meu ambiente para usar o Aspose.Email?**  
R: Instale JDK 16+, Maven, adicione a dependência Aspose.Email ao `pom.xml` e obtenha uma licença (de avaliação ou completa).

**P: Posso usar este código com outras versões do Exchange Online?**  
R: Sim, mas verifique se a URL do serviço e os níveis de permissão correspondem à configuração do seu servidor.

**P: O que fazer se o convite de compartilhamento de calendário falhar ao enviar?**  
R: Verifique a conectividade de rede, credenciais e se o usuário delegado tem permissões válidas. Analise os detalhes da exceção para pistas.

**P: É possível adicionar permissões adicionais, como edição ou acesso total?**  
R: Absolutamente – substitua `ExchangeDelegateFolderPermissionLevel.Reviewer` por `Editor`, `Author` ou `Owner`, conforme necessário.

## Conclusão
Você agora possui uma solução completa, de ponta a ponta, para **criar convite de compartilhamento de calendário** com Aspose.Email para Java. Ao inicializar o cliente EWS, **criar acesso delegado**, **definir permissões de delegado** e enviar um **e‑mail de compartilhamento de calendário**, você pode automatizar a colaboração em toda a sua organização.

**Próximos passos**
- Experimente outros níveis de permissão (Editor, Owner).  
- Integre essa lógica aos seus sistemas de agendamento ou RH existentes.  
- Explore recursos adicionais do Aspose.Email, como eventos recorrentes ou solicitações de reunião.

---

**Última atualização:** 2026-09-17  
**Testado com:** Aspose.Email para Java 25.4 (classificador JDK 16)  
**Autor:** Aspose

## Tutoriais Relacionados

- [Como criar item de calendário Java usando Aspose.Email](/email/java/calendar-appointments/create-save-calendar-items-aspose-email-java/)
- [Aspose Email Java Filtrar compromissos Exchange por data](/email/java/calendar-appointments/aspose-email-java-filter-exchange-appointments-by-date/)
- [Criar calendário Exchange Java com Aspose.Email – Um Guia Completo](/email/java/calendar-appointments/mastering-exchange-calendar-management-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}