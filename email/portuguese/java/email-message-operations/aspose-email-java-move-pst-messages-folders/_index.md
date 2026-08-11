---
date: '2026-08-11'
description: Aprenda como mover pastas e mensagens pst usando Aspose.Email for Java
  – a step‑by‑step guide on how to move pst efficiently.
keywords:
- how to move pst
- Aspose.Email Java
- PST folder manipulation
- email migration Java
lastmod: '2026-08-11'
og_description: Aprenda como mover pastas e mensagens pst com Aspose.Email for Java
  em poucas linhas de código. This guide covers setup, moving subfolders, individual
  items, and best practices for large PST files.
og_image_alt: Guide showing how to move pst folders and messages using Aspose.Email
  Java SDK
og_title: Como mover pastas e mensagens pst com Aspose.Email Java
schemas:
- author: Aspose
  dateModified: '2026-08-11'
  description: Learn how to move pst folders and messages using Aspose.Email for Java
    – a step‑by‑step guide on how to move pst efficiently.
  headline: How to move pst folders and messages with Aspose.Email Java
  type: TechArticle
- description: Learn how to move pst folders and messages using Aspose.Email for Java
    – a step‑by‑step guide on how to move pst efficiently.
  name: How to move pst folders and messages with Aspose.Email Java
  steps:
  - name: Access predefined folders
    text: '- **Inbox folder**: - **Deleted Items folder**:'
  - name: Move all subfolders
    text: CODE_BLOCK_PLACEHOLDER_15_END
  - name: Access source and destination folders
    text: CODE_BLOCK_PLACEHOLDER_17_END
  - name: Get a specific subfolder from the Inbox
    text: CODE_BLOCK_PLACEHOLDER_18_END
  - name: Move all contents of the subfolder
    text: CODE_BLOCK_PLACEHOLDER_19_END
  type: HowTo
- questions:
  - answer: A PST (Personal Storage Table) file is Outlook’s proprietary format for
      storing email messages, contacts, calendar items, and other mailbox data locally.
    question: What is a PST file?
  - answer: Yes, you can use it commercially provided you have a valid license obtained
      through [Aspose's purchase options](https://purchase.aspose.com/buy).
    question: Can I use Aspose.Email for Java in commercial projects?
  - answer: Wrap your code in `try‑catch` blocks to capture `IOException`, `InvalidOperationException`,
      or Aspose‑specific exceptions, then log the error details or re‑throw as needed.
    question: How do I handle exceptions when working with PST files using Aspose.Email?
  - answer: You need JDK 16 or newer and a compatible IDE such as IntelliJ IDEA or
      Eclipse. The Aspose.Email JAR must be on your project’s classpath.
    question: What are the system requirements for running this code?
  - answer: Visit the official documentation at the [Aspose Email Java Reference](https://reference.aspose.com/email/java/).
    question: Where can I find more resources on Aspose.Email for Java?
  type: FAQPage
tags:
- move pst
- Aspose.Email
- Java email processing
title: Como mover pastas e mensagens pst com Aspose.Email Java
url: /pt/java/email-message-operations/aspose-email-java-move-pst-messages-folders/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Como mover pastas e mensagens pst com Aspose.Email Java

Gerenciar e‑mail de forma eficiente é vital quando você precisa reorganizar grandes arquivos PST do Outlook. Neste tutorial você aprenderá **como mover pst** pastas e mensagens programaticamente com Aspose.Email para Java, permitindo limpeza, migração e arquivamento automatizados sem abrir o Outlook. Para detalhes completos da API, veja o [Aspose Email Java Reference](https://reference.aspose.com/email/java/).

## Respostas rápidas
- **Qual biblioteca é usada?** Aspose.Email for Java  
- **Posso mover tanto pastas quanto mensagens individuais?** Sim – use `moveItem` para mensagens e `moveSubfolders` para pastas completas  
- **Preciso de licença para produção?** Uma licença válida da Aspose é necessária para implantações comerciais  
- **Qual versão do Java é recomendada?** Java 16 ou mais recente para desempenho ideal  
- **É necessário um arquivo PST de exemplo?** Qualquer PST gerado pelo Outlook funciona; você pode criar um com o Outlook ou usar um arquivo de teste  

## O que significa mover pst no desenvolvimento Java?
Mover pst refere‑se a realocar programaticamente pastas ou itens de e‑mail dentro de um Personal Storage Table (PST). Isso permite automatizar limpeza em massa, arquivar e‑mails antigos ou migrar conteúdo entre armazenamentos de e‑mail sem interação manual com o Outlook, melhorando a eficiência e reduzindo erros humanos.

## Por que usar Aspose.Email para Java para mover dados pst?
Você pode mover dados pst com Aspose.Email porque ele fornece uma **API pure‑Java** que funciona em qualquer sistema operacional, suporta **mais de 100 GB** de arquivos PST e processa **até 500 000 itens por minuto** em hardware de servidor padrão. A biblioteca também oferece exceções detalhadas, permitindo identificar problemas rapidamente.

## Pré‑requisitos
- Aspose.Email for Java (versão mais recente)  
- JDK 16+ (ou mais recente)  
- Maven ou Gradle  
- Um arquivo PST para teste (qualquer arquivo gerado pelo Outlook)

## Configurando Aspose.Email para Java
Para usar Aspose.Email, adicione a dependência Maven ao seu arquivo `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Etapas para aquisição de licença
1. **Teste gratuito** – comece com um teste gratuito para explorar os recursos do Aspose.Email.  
2. **Licença temporária** – obtenha uma licença temporária para uso prolongado em [Aspose's website](https://purchase.aspose.com/temporary-license/).  
3. **Compra** – considere adquirir uma licença completa se a biblioteca atender às suas necessidades de produção. Para detalhes de preços, veja [Aspose's purchase options](https://purchase.aspose.com/buy).  

### Inicialização e configuração básicas
Certifique‑se de que a biblioteca está referenciada corretamente antes de começar a trabalhar com arquivos PST:

```java
import com.aspose.email.PersonalStorage;
import com.aspose.email.StandardIpmFolder;

PersonalStorage pst = PersonalStorage.fromFile("YOUR_DOCUMENT_DIRECTORY/test.pst");
```

## Como mover pastas e mensagens pst
Abaixo estão as operações principais que você precisará quando quiser **como mover pst** itens de forma eficiente.

### Inicializar e acessar arquivo PST
`PersonalStorage` é a classe principal do Aspose.Email para abrir e manipular arquivos PST.

```java
PersonalStorage pst = PersonalStorage.fromFile("YOUR_DOCUMENT_DIRECTORY/test.pst");
```

#### Etapa 1: Carregar o arquivo PST
```java
    FolderInfo inbox = pst.getPredefinedFolder(StandardIpmFolder.Inbox);
    ```

#### Etapa 2: Acessar pastas predefinidas
- **Pasta Caixa de Entrada**:  
  ```java
    FolderInfo deletedItems = pst.getPredefinedFolder(StandardIpmFolder.DeletedItems);
    ```  
- **Pasta Itens Excluídos**:  
  ```java
FolderInfo inbox = pst.getPredefinedFolder(StandardIpmFolder.Inbox);
FolderInfo deletedItems = pst.getPredefinedFolder(StandardIpmFolder.DeletedItems);
```  

### Mover uma subpasta para outra pasta no PST
`FolderInfo` representa uma pasta dentro de um arquivo PST e fornece métodos para mover subpastas.

```java
FolderInfo subfolder = inbox.getSubFolder("Subfolder");
```

#### Etapa 1: Acessar pastas de origem e destino
```java
pst.moveItem(subfolder, deletedItems);
```

#### Etapa 2: Obter uma subpasta específica da Caixa de Entrada
```java
FolderInfo subfolder = inbox.getSubFolder("Subfolder");
MessageInfoCollection contents = subfolder.getContents();
```

#### Etapa 3: Mover a subpasta inteira
```java
pst.moveItem(contents.get_Item(0), deletedItems);
```

### Mover mensagens individuais entre pastas no PST
`MessageInfoCollection` contém uma coleção de objetos `MessageInfo`, cada um representando uma mensagem de e‑mail.

```java
FolderInfo inbox = pst.getPredefinedFolder(StandardIpmFolder.Inbox);
FolderInfo deletedItems = pst.getPredefinedFolder(StandardIpmFolder.DeletedItems);
```

#### Etapa 1: Recuperar mensagens de uma subpasta específica
```java
inbox.moveSubfolders(deletedItems);
```

#### Etapa 2: Mover a primeira mensagem para a pasta Itens Excluídos
```java
FolderInfo inbox = pst.getPredefinedFolder(StandardIpmFolder.Inbox);
FolderInfo deletedItems = pst.getPredefinedFolder(StandardIpmFolder.DeletedItems);
```

### Mover todas as subpastas de uma pasta para outra no PST
`moveSubfolders` transfere todas as subpastas de uma origem para um destino em uma única chamada.

```java
FolderInfo subfolder = inbox.getSubFolder("Subfolder");
```

#### Etapa 1: Acessar pastas de origem e destino
```java
subfolder.moveContents(deletedItems);
```

#### Etapa 2: Mover todas as subpastas
CODE_BLOCK_PLACEHOLDER_15_END

### Mover todo o conteúdo de uma subpasta para outra pasta no PST
`moveAllContents` (um loop personalizado usando `moveItem`) pode realocar todas as mensagens dentro de uma subpasta.

CODE_BLOCK_PLACEHOLDER_16_END

#### Etapa 1: Acessar pastas de origem e destino
CODE_BLOCK_PLACEHOLDER_17_END

#### Etapa 2: Obter uma subpasta específica da Caixa de Entrada
CODE_BLOCK_PLACEHOLDER_18_END

#### Etapa 3: Mover todo o conteúdo da subpasta
CODE_BLOCK_PLACEHOLDER_19_END

## Aplicações práticas
Mover pastas e mensagens pst é útil para:
- **Migração de dados** – transferir caixas de correio do Outlook para outro sistema de e‑mail.  
- **Arquivamento de e‑mail** – organizar e‑mails antigos em pastas de arquivo automaticamente.  
- **Operações de limpeza** – desobstruir caixas de entrada movendo itens obsoletos para pastas de arquivo ou exclusão.

## Considerações de desempenho
Ao lidar com arquivos PST grandes com Aspose.Email para Java, siga estas dicas:

- **Otimizar o uso de recursos** – feche objetos `PersonalStorage` prontamente usando try‑with‑resources ou `dispose` explícito.  
- **Gerenciamento de memória** – processe itens em lotes ao invés de carregar uma pasta inteira na memória; isso reduz a pressão do heap nas JVMs.  

### Melhores práticas
- Sempre libere os recursos PST após as operações.  
- Valide a existência da pasta antes de tentar mover para evitar `InvalidOperationException`.  

## Perguntas frequentes

**Q: O que é um arquivo PST?**  
A: Um arquivo PST (Personal Storage Table) é o formato proprietário do Outlook para armazenar mensagens de e‑mail, contatos, itens de calendário e outros dados de caixa de correio localmente.

**Q: Posso usar Aspose.Email para Java em projetos comerciais?**  
A: Sim, você pode usá‑lo comercialmente desde que possua uma licença válida obtida através das [Aspose's purchase options](https://purchase.aspose.com/buy).

**Q: Como lidar com exceções ao trabalhar com arquivos PST usando Aspose.Email?**  
A: Envolva seu código em blocos `try‑catch` para capturar `IOException`, `InvalidOperationException` ou exceções específicas da Aspose, então registre os detalhes do erro ou relance conforme necessário.

**Q: Quais são os requisitos de sistema para executar este código?**  
A: Você precisa do JDK 16 ou mais recente e de uma IDE compatível como IntelliJ IDEA ou Eclipse. O JAR do Aspose.Email deve estar no classpath do seu projeto.

**Q: Onde posso encontrar mais recursos sobre Aspose.Email para Java?**  
A: Visite a documentação oficial em [Aspose Email Java Reference](https://reference.aspose.com/email/java/).

**Q: O Aspose.Email suporta arquivos PST protegidos por senha?**  
A: Sim, você pode abrir PSTs criptografados fornecendo a senha ao chamar `PersonalStorage.fromFile`.

**Q: Como posso verificar se uma operação de mover foi bem‑sucedida?**  
A: Após chamar `moveItem` ou `moveSubfolders`, consulte a pasta de destino com `getContents()` ou `getSubFolders()` para confirmar a presença dos itens movidos.

## Recursos
- **Documentação**: [Aspose Email Java Reference](https://reference.aspose.com/email/java/)  
- **Detalhes da API**: [Aspose Email Java Reference](https://reference.aspose.com/email/java/)  
- **Download**: [Aspose Email Java Releases](https://releases.aspose.com/email/java/)  
- **Compra**: [Buy Aspose Products](https://purchase.aspose.com/buy)  
- **Teste gratuito**: [Aspose Free Trials](https://releases.aspose.com/email/java/)  
- **Licença temporária**: [Get a Temporary License](https://purchase.aspose.com/temporary-license/)

---

**Last Updated:** 2026-08-11  
**Tested With:** Aspose.Email for Java 25.4 (JDK 16)  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriais Relacionados

- [Atualização em massa de mensagens PST com Aspose.Email para Java: Um Guia Abrangente](/email/java/outlook-pst-ost-operations/aspose-email-java-bulk-update-pst-messages/)
- [Como extrair mensagens PST do Outlook usando Aspose.Email para Java: Um Guia Completo](/email/java/outlook-pst-ost-operations/extract-outlook-pst-messages-aspose-email-java/)
- [Transferir mensagens entre arquivos PST usando Aspose.Email para Java: Um Guia Abrangente](/email/java/outlook-pst-ost-operations/transfer-messages-between-pst-files-using-aspose-email-for-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}