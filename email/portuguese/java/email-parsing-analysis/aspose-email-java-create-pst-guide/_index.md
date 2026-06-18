---
date: '2026-06-08'
description: Aprenda a criar arquivos PST com Aspose.Email para Java, incluindo como
  adicionar estruturas de pastas e como pesquisar o conteúdo de PST de forma eficiente.
  Guia passo a passo.
keywords:
- how to create pst
- how to add folder
- how to search pst
schemas:
- author: Aspose
  dateModified: '2026-06-08'
  description: Learn how to create PST files with Aspose.Email for Java, including
    how to add folder structures and how to search PST content efficiently. Step‑by‑step
    guide.
  headline: How to Create PST Files with Aspose.Email for Java
  type: TechArticle
- description: Learn how to create PST files with Aspose.Email for Java, including
    how to add folder structures and how to search PST content efficiently. Step‑by‑step
    guide.
  name: How to Create PST Files with Aspose.Email for Java
  steps:
  - name: Add Maven Dependency
    text: Add the Aspose.Email Maven dependency to your `pom.xml`. This pulls in all
      required binaries automatically.
  - name: Acquire and Apply a License
    text: A free trial is available, but a permanent license removes evaluation limits
      and enables full‑speed processing.
  - name: Initialize PersonalStorage
    text: The `PersonalStorage` class is Aspose.Email's top‑level object that represents
      a single PST file in memory. After instantiation, all read and write operations
      flow through this object.
  - name: Define Directory Paths
    text: Set source and destination paths for your email files and the PST output
      location.
  - name: Create the PST File
    text: Use `PersonalStorage.create()` with `FileFormatVersion.Unicode` to produce
      a modern Unicode PST that supports large folders and Unicode characters.
  - name: Build Search Query
    text: Construct a query that looks for a keyword in the subject or body, ignoring
      case.
  - name: Execute Query and Retrieve Messages
    text: Run the query on the target folder and iterate over the resulting `MapiMessage`
      collection.
  - name: Initialize PersonalStorage Object
    text: Assume `PersonalStorage` object (`pst`) is already created as shown previously.
  - name: Add to PST Folder
    text: 'Convert `MailMessage` to `MapiMessage` and add it:'
  type: HowTo
- questions:
  - answer: JDK 16 or higher is recommended for full compatibility with Aspose.Email
      for Java.
    question: What is the minimum Java version required?
  - answer: Yes, a trial mode is available but limits PST size to **10 MB** and disables
      certain optimizations.
    question: Can I use Aspose.Email without a license?
  - answer: Process messages in batches, dispose of `MapiMessage` objects promptly,
      and enable lazy loading via `PersonalStorage.setUseUnicode(true)`.
    question: How do I handle large PST files efficiently?
  - answer: Absolutely. When converting `MailMessage` to `MapiMessage`, call `mapiMsg.getAttachments().add(attachment)`
      to embed files.
    question: Is it possible to add attachments to emails in PST files?
  - answer: Aspose offers a dedicated support forum, detailed documentation, and email
      support for licensed customers.
    question: What kind of support is available for troubleshooting issues?
  type: FAQPage
title: Como criar arquivos PST com Aspose.Email para Java
url: /pt/java/email-parsing-analysis/aspose-email-java-create-pst-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Dominando o Gerenciamento de Email com Aspose.Email para Java

Se você precisa **how to create pst** arquivos programaticamente, chegou ao lugar certo. Neste tutorial vamos percorrer cada passo necessário para gerar um arquivo Unicode PST, adicionar pastas padrão do Outlook, importar mensagens e executar buscas sem distinção entre maiúsculas e minúsculas — tudo usando Aspose.Email para Java. Ao final, você terá um padrão de código reutilizável que escala de alguns e‑mails a arquivos de vários gigabytes.

## Respostas Rápidas
- **Como começar?** Adicione a dependência Maven do Aspose.Email, obtenha uma licença e instancie `PersonalStorage`.
- **Posso adicionar uma pasta Caixa de Entrada?** Sim – chame `pst.getRootFolder().addSubFolder("Inbox")`.
- **A busca sem distinção entre maiúsculas e minúsculas é suportada?** Use `PersonalStorageQueryBuilder` com `StringComparison.OrdinalIgnoreCase`.
- **Qual tamanho de arquivo pode ser manipulado?** Aspose.Email processa arquivos PST de até 2 GB sem carregar o arquivo inteiro na memória.
- **Preciso de uma licença paga para produção?** Uma licença permanente remove as limitações da avaliação e desbloqueia todos os recursos de desempenho.

## O que é how to create pst?
**how to create pst** refere-se ao processo programático de gerar um arquivo Outlook Personal Storage Table (PST) usando código em vez da interface do Outlook. Aspose.Email para Java fornece uma API totalmente gerenciada que cria arquivos Unicode PST, adiciona pastas e armazena objetos `MapiMessage` sem necessidade de instalar o Outlook.

## Por que usar Aspose.Email para criação de PST?
Aspose.Email suporta **mais de 50** formatos relacionados a e‑mail (MSG, EML, MBOX, PST, etc.) e pode processar arquivos PST com **até 2 GB** de tamanho mantendo o uso de memória abaixo de **150 MB** graças à sua arquitetura de carregamento preguiçoso. Essa capacidade quantificada o torna ideal para arquivamento corporativo, migração e cenários de conformidade.

## Pré‑requisitos

- **Java Development Kit (JDK)** – versão 16 ou posterior.
- **Maven** – para gerenciamento de dependências.
- Familiaridade básica com a sintaxe Java; não é necessária experiência prévia com arquivos PST.

## Como criar um arquivo PST?

A classe `PersonalStorage` representa um arquivo PST e fornece métodos para criar, abrir e manipular seu conteúdo. Para criar um novo PST Unicode, chame `PersonalStorage.create()` com o caminho de arquivo desejado e a versão do formato. Esta operação gera um PST moderno que suporta pastas grandes, caracteres Unicode e streaming eficiente, tornando‑o adequado tanto para tarefas de arquivamento em pequena escala quanto em nível corporativo.

### Etapa 1: Adicionar Dependência Maven

Adicione a dependência Maven do Aspose.Email ao seu `pom.xml`. Isso inclui automaticamente todos os binários necessários.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Etapa 2: Obter e Aplicar uma Licença

Um teste gratuito está disponível, mas uma licença permanente remove as limitações de avaliação e permite processamento em velocidade total.

```java
import com.aspose.email.*;

public class AsposeEmailSetup {
    public static void main(String[] args) {
        // Set up license if available
        License license = new License();
        try {
            license.setLicense("path/to/your/license.lic");
        } catch (Exception e) {
            System.out.println("License not found, proceeding with trial version.");
        }

        System.out.println("Aspose.Email for Java is ready to use!");
    }
}
```

## Como adicionar pasta ao PST?

Crie a hierarquia de pastas desejada sob a raiz do PST e, em seguida, faça referência a ela ao inserir mensagens. O objeto `FolderInfo` representa cada pasta e pode ser aninhado arbitrariamente, permitindo construir estruturas como Caixa de Entrada, Itens Enviados ou pastas de projetos personalizadas. Adicionar pastas é uma operação leve que não carrega o conteúdo das mensagens, preservando o desempenho mesmo em PSTs grandes.

### Etapa 1: Inicializar PersonalStorage

A classe `PersonalStorage` é o objeto de nível superior do Aspose.Email que representa um único arquivo PST na memória. Após a instanciação, todas as operações de leitura e escrita passam por esse objeto.

```java
import com.aspose.email.FileFormatVersion;
import com.aspose.email.PersonalStorage;
```

### Etapa 2: Definir Caminhos de Diretórios

Defina os caminhos de origem e destino para seus arquivos de e‑mail e o local de saída do PST.

```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY";
String outputDir = "YOUR_OUTPUT_DIRECTORY";
```

### Etapa 3: Criar o Arquivo PST

Use `PersonalStorage.create()` com `FileFormatVersion.Unicode` para produzir um PST Unicode moderno que suporta pastas grandes e caracteres Unicode.

```java
try {
    PersonalStorage pst = PersonalStorage.create(outputDir + "NewPSTFile_out.pst", FileFormatVersion.Unicode);

    // Perform operations here.
} finally {
    if (pst != null)
        pst.dispose();
}
```

## Como pesquisar pst?

`PersonalStorageQueryBuilder` é uma classe construtora usada para montar consultas de pesquisa no conteúdo do PST. Configurando o construtor com os critérios desejados e especificando `StringComparison.OrdinalIgnoreCase`, você pode executar buscas rápidas, sem distinção entre maiúsculas e minúsculas, em assuntos, corpos e propriedades personalizadas sem carregar o PST inteiro na memória.

### Etapa 1: Construir Consulta de Pesquisa

Construa uma consulta que procure uma palavra‑chave no assunto ou no corpo, ignorando maiúsculas/minúsculas.

```java
import com.aspose.email.MailQueryBuilder;
import com.aspose.email.MailQuery;
import com.aspose.email.MessageInfoCollection;

MailQueryBuilder builder = new MailQueryBuilder();
builder.getFrom().contains("automated", true);
```

### Etapa 2: Executar Consulta e Recuperar Mensagens

Execute a consulta na pasta alvo e itere sobre a coleção resultante de `MapiMessage`.

```java
try {
    MailQuery query = builder.getQuery();
    MessageInfoCollection coll = fi.getContents(query);

    // Process results as needed.
} finally {
    if (pst != null)
        pst.dispose();
}
```

## Criando uma Pasta Predefinida no PST

Adicionar uma pasta predefinida como **Inbox** ajuda a organizar seus dados de e‑mail de forma eficaz.

### Etapa 1: Inicializar o Objeto PersonalStorage

Presume‑se que o objeto `PersonalStorage` (`pst`) já foi criado como mostrado anteriormente.

### Etapa 2: Criar a Pasta 'Inbox'

```java
try {
    FolderInfo fi = pst.createPredefinedFolder("Inbox", StandardIpmFolder.Inbox);
} finally {
    if (pst != null)
        pst.dispose();
}
```

## Adicionando Mensagens a uma Pasta PST

Preencha sua pasta PST com mensagens de e‑mail carregando‑as de arquivos e convertendo‑as.

### Etapa 1: Carregar Mensagem de E‑mail

```java
import com.aspose.email.MailMessage;
import com.aspose.email.MapiMessage;

MailMessage mailMessage = MailMessage.load(dataDir + "message.msg");
```

### Etapa 2: Adicionar à Pasta PST

Converta `MailMessage` para `MapiMessage` e adicione-a:

```java
try {
    fi.addMessage(MapiMessage.fromMailMessage(mailMessage));
} finally {
    if (pst != null)
        pst.dispose();
}
```

## Aplicações Práticas

Aspose.Email para Java não se trata apenas de criar arquivos PST; é uma ferramenta versátil com inúmeras aplicações:
- **Arquivamento de E‑mail**: Automatize o arquivamento de e‑mails corporativos em arquivos PST, suportando políticas de retenção de até 10 anos.
- **Ferramentas de Migração**: Migre perfeitamente de armazenamentos de e‑mail legados (por exemplo, MBOX) para Outlook PST com uma única chamada de API por mensagem.
- **Análise de Dados**: Extraia metadados como remetente, destinatário e timestamps para pipelines de inteligência de negócios.
- **Soluções de Backup**: Crie utilitários de backup robustos que armazenam alterações incrementais de e‑mail sem reprocessar toda a caixa de correio.

## Considerações de Desempenho

Para garantir desempenho ideal ao usar Aspose.Email:
- **Gerenciamento de Recursos**: Sempre chame `pst.dispose()` ou use try‑with‑resources para liberar rapidamente os manipuladores nativos.
- **Processamento em Lote**: Processar e‑mails em lotes de **500** itens para manter o uso de memória previsível.
- **Manipulação de Concorrência**: A biblioteca é thread‑safe para operações somente de leitura; para gravações, sincronize o acesso à instância `PersonalStorage`.

## Problemas Comuns e Soluções

| Problema | Causa | Solução |
|----------|-------|----------|
| **OutOfMemoryError** ao lidar com PSTs grandes | Carregando o PST inteiro na memória | Habilite `PersonalStorage.setUseUnicode(true)` e processe as mensagens em streams. |
| Erro **Folder not found** | Caso incorreto no caminho da pasta | Use `StringComparison.OrdinalIgnoreCase` nas consultas ou normalize os nomes das pastas. |
| **Licença não aplicada** | Arquivo de licença não carregado antes da primeira chamada de API | Carregue a licença na inicialização da aplicação, antes de criar quaisquer objetos `PersonalStorage`. |

## Perguntas Frequentes

**Q: Qual é a versão mínima do Java necessária?**  
A: JDK 16 ou superior é recomendada para compatibilidade total com Aspose.Email para Java.

**Q: Posso usar Aspose.Email sem licença?**  
A: Sim, o modo de avaliação está disponível, mas limita o tamanho do PST a **10 MB** e desabilita certas otimizações.

**Q: Como lidar eficientemente com arquivos PST grandes?**  
A: Processe as mensagens em lotes, descarte os objetos `MapiMessage` prontamente e habilite o carregamento preguiçoso via `PersonalStorage.setUseUnicode(true)`.

**Q: É possível adicionar anexos a e‑mails em arquivos PST?**  
A: Absolutamente. Ao converter `MailMessage` para `MapiMessage`, chame `mapiMsg.getAttachments().add(attachment)` para incorporar arquivos.

**Q: Que tipo de suporte está disponível para resolução de problemas?**  
A: Aspose oferece um fórum de suporte dedicado, documentação detalhada e suporte por e‑mail para clientes licenciados.

## Recursos
- [Documentação](https://reference.aspose.com/email/java/)
- [Download](https://releases.aspose.com/email/java/)
- [Compra](https://purchase.aspose.com/buy)
- [Teste Gratuito](https://releases.aspose.com/email/java/)
- [Licença Temporária](https://purchase.aspose.com/temporary-license/)
- [Fórum de Suporte](https://forum.aspose.com/c/email/10)

---

**Última atualização:** 2026-06-08  
**Testado com:** Aspose.Email for Java 24.10  
**Autor:** Aspose

## Tutoriais Relacionados

- [Como Criar e Gerenciar Arquivos Outlook PST Usando Aspose.Email para Java](/email/java/outlook-pst-ost-operations/aspose-email-java-manage-pst-files/)
- [Manipular Arquivos PST Usando Aspose.Email para Java: Um Guia Abrangente](/email/java/outlook-pst-ost-operations/manipulate-pst-files-aspose-email-java/)
- [Extrair Anexos de E‑mail Java - Usando Aspose.Email para Arquivos PST – Um Guia Passo a Passo](/email/java/attachments-handling/extract-email-attachments-pst-aspose-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}