---
"date": "2025-05-29"
"description": "Aprenda a gerenciar com eficiência múltiplas propriedades em mensagens MAPI usando o Aspose.Email para Java. Este guia aborda a configuração de tipos float, double, long e outros."
"title": "Definir várias propriedades MAPI em Java com Aspose.Email - Um guia completo"
"url": "/pt/java/mapi-operations/aspose-email-java-set-mapi-properties/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Definir várias propriedades MAPI em Java com Aspose.Email: um guia completo

## Introdução

Gerenciar as propriedades de mensagens MAPI com eficácia é crucial para aprimorar seus aplicativos Java. Com o Aspose.Email para Java, você pode definir diversas propriedades, como float, double, long, short, boolean e propriedades personalizadas, de forma integrada. Este guia apresentará vários métodos para isso.

**O que você aprenderá:**
- Configurando múltiplas propriedades em mensagens MAPI usando Aspose.Email Java
- Compreendendo os diferentes tipos de propriedades e seus usos
- Exemplos práticos de código para implementação

Vamos começar abordando os pré-requisitos.

## Pré-requisitos

Para acompanhar, certifique-se de ter:
- **Kit de Desenvolvimento Java (JDK):** JDK 8 ou posterior instalado.
- **Biblioteca Aspose.Email:** A versão 25.4 é recomendada.
- **Configuração do Maven:** O Maven deve ser configurado no seu IDE para gerenciamento de dependências.

### Bibliotecas necessárias

Inclua Aspose.Email como uma dependência em seu `pom.xml`:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Aquisição de Licença
- **Teste gratuito:** Comece com um teste gratuito para explorar os recursos.
- **Licença temporária:** Obtenha para testes estendidos sem limitações.
- **Comprar:** Considere comprar se for adequado às suas necessidades.

## Configurando o Aspose.Email para Java

Certifique-se de que o Aspose.Email esteja configurado corretamente no seu ambiente de desenvolvimento:
1. **Dependências de importação:** Resolver dependências do Maven.
2. **Definir Licença:**
   - Baixe um arquivo de licença de [Aspose](https://purchase.aspose.com/buy).
   - Aplique usando:
     ```java
     com.aspose.email.License license = new com.aspose.email.License();
     license.setLicense("path/to/your/license.lic");
     ```

Com a configuração concluída, vamos explorar como definir várias propriedades.

## Guia de Implementação

### Configurando múltiplas propriedades de flutuação

A definição de propriedades flutuantes permite o armazenamento eficiente de dados numéricos:

#### Visão geral
Este recurso demonstra como adicionar vários valores float como propriedades de mensagem MAPI usando Aspose.Email para Java.

#### Passos
1. **Crie e inicialize a mensagem**
   ```java
   import java.util.ArrayList;
   import com.aspose.email.MapiMessage;
   import com.aspose.email.MapiProperty;
   import com.aspose.email.system.collections.IList;

   MapiMessage msg = new MapiMessage();
   ```
2. **Adicionar valores flutuantes a uma lista**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((float) 1);
   values.addItem((float) 2);
   ```
3. **Defina a propriedade com um identificador exclusivo**
   ```java
   msg.setProperty(new MapiProperty(0x23901004, values));
   ```
*Explicação:* A etiqueta da propriedade `0x23901004` identifica este conjunto de propriedades float.

### Configurando várias propriedades duplas

Propriedades duplas armazenam números de ponto flutuante de alta precisão:

#### Visão geral
Esta seção mostra o armazenamento de vários valores double como propriedades de mensagem MAPI.

#### Passos
1. **Inicializar a mensagem**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Preencher valores duplos**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((double) 1);
   values.addItem((double) 2);
   ```
3. **Atribuir à etiqueta de propriedade**
   ```java
   msg.setProperty(new MapiProperty(0x23901005, values));
   ```

### Configurando várias propriedades APPTIME

As propriedades APPTIME armazenam durações de tempo de forma eficiente:

#### Visão geral
Este recurso ilustra o uso de números de precisão dupla para representações de tempo.

#### Passos
1. **Criar objeto de mensagem**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Adicionar valores de tempo**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem(30456.34);
   values.addItem(40655.45);
   ```
3. **Defina a propriedade**
   ```java
   msg.setProperty(new MapiProperty(0x23901007, values));
   ```

### Definindo várias propriedades longas

Propriedades longas são ideais para números inteiros grandes:

#### Visão geral
Este recurso se concentra na definição de vários valores inteiros longos em uma mensagem.

#### Passos
1. **Inicializar mensagem MAPI**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Adicionar valores longos**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((long) 30456);
   values.addItem((long) 40655);
   ```
3. **Definir tag de propriedade**
   ```java
   msg.setProperty(new MapiProperty(0x23901014, values));
   ```

### Definindo várias propriedades curtas

Propriedades curtas armazenam dados inteiros pequenos de forma eficiente:

#### Visão geral
Este guia demonstra como definir números inteiros curtos como propriedades de mensagem.

#### Passos
1. **Inicializar a mensagem**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Adicionar valores curtos**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((short) 1);
   values.addItem((short) 2);
   ```
3. **Atribuir etiqueta de propriedade**
   ```java
   msg.setProperty(new MapiProperty(0x23901002, values));
   ```

### Definindo múltiplas propriedades booleanas

Propriedades booleanas armazenam estados verdadeiro/falso:

#### Visão geral
Aprenda como definir vários valores booleanos em uma mensagem.

#### Passos
1. **Criar objeto de mensagem**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Adicionar valores booleanos**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem(true);
   values.addItem(false);
   ```
3. **Definir propriedade com identificador**
   ```java
   msg.setProperty(new MapiProperty(0x2390100b, values));
   ```

### Definindo uma propriedade nula

Definir explicitamente uma propriedade como nula pode ser útil:

#### Visão geral
Esta seção demonstra como atribuir um valor nulo a uma propriedade.

#### Passos
1. **Inicializar a mensagem**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Atribuir propriedade nula**
   ```java
   msg.setProperty(new MapiProperty(0x67400001, new byte[1]));
   ```

### Configurando propriedade longa nomeada com ID e UUID personalizados

Para cenários complexos, defina propriedades nomeadas:

#### Visão geral
Este recurso demonstra a configuração de uma propriedade longa com um identificador personalizado e UUID.

#### Passos
1. **Inicializar a mensagem**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Adicionar valores longos**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((int) 4);
   UUID uuid = UUID.randomUUID();
   ```
3. **Criar e mapear propriedade**
   ```java
   MapiProperty property = new MapiProperty(msg.getNamedPropertyMapping().getNextAvailablePropertyId(com.aspose.email.MapiPropertyType.PT_MV_LONG), values);
   msg.getNamedPropertyMapping().addNamedPropertyMapping(property, (long) 0x00008028, uuid);
   msg.setProperty(property);
   ```

### Configurando Propriedade Personalizada com Nome

Propriedades personalizadas podem ser nomeadas para facilitar a identificação:

#### Visão geral
Este guia mostra como definir propriedades com nomes personalizados.

#### Passos
1. **Inicializar objeto de mensagem**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Definir propriedade personalizada**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem("Custom Value");
   UUID uuid = UUID.randomUUID();
   
   MapiProperty property = new MapiProperty(msg.getNamedPropertyMapping().getNextAvailablePropertyId(com.aspose.email.MapiPropertyType.PT_STRING), values);
   msg.getNamedPropertyMapping().addNamedPropertyMapping(property, "CustomName", uuid);
   ```

### Configurando e Validando Propriedades

Garantir que as propriedades estejam definidas corretamente é crucial:

#### Visão geral
Esta seção aborda a configuração e validação de diversas propriedades em mensagens MAPI.

#### Passos
1. **Definir propriedade**
   Siga os exemplos anteriores para definir uma propriedade.
2. **Validar Propriedade**
   ```java
   if (msg.getProperties().containsKey(0x23901004)) {
       System.out.println("Property is set correctly.");
   } else {
       System.err.println("Property setting failed.");
   }
   ```

## Conclusão

Este guia oferece uma abordagem abrangente para gerenciar múltiplas propriedades em mensagens MAPI usando o Aspose.Email para Java. Seguindo esses passos, você poderá armazenar e gerenciar com eficiência diversos tipos de dados em seus aplicativos.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}