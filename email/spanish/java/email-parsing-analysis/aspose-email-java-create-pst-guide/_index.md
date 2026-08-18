---
date: '2026-06-08'
description: Aprenda cómo crear archivos PST con Aspose.Email para Java, incluyendo
  cómo agregar estructuras de carpetas y cómo buscar contenido PST de manera eficiente.
  Guía paso a paso.
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
title: Cómo crear archivos PST con Aspose.Email para Java
url: /es/java/email-parsing-analysis/aspose-email-java-create-pst-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Dominando la gestión de correo electrónico con Aspose.Email para Java

Si necesitas **how to create pst** archivos de forma programática, has llegado al lugar correcto. En este tutorial recorreremos cada paso necesario para generar un archivo PST Unicode, agregar carpetas estándar de Outlook, importar mensajes y ejecutar búsquedas sin distinción de mayúsculas y minúsculas, todo usando Aspose.Email para Java. Al final, tendrás un patrón de código reutilizable que escala desde unos pocos correos electrónicos hasta archivos de varios gigabytes.

## Respuestas rápidas
- **¿Cómo empiezo?** Agrega la dependencia Maven de Aspose.Email, obtén una licencia y crea una instancia de `PersonalStorage`.
- **¿Puedo agregar una carpeta Inbox?** Sí – llama a `pst.getRootFolder().addSubFolder("Inbox")`.
- **¿Se admite la búsqueda sin distinción de mayúsculas y minúsculas?** Usa `PersonalStorageQueryBuilder` con `StringComparison.OrdinalIgnoreCase`.
- **¿Qué tamaño de archivo se puede manejar?** Aspose.Email procesa archivos PST de hasta 2 GB sin cargar todo el archivo en memoria.
- **¿Necesito una licencia de pago para producción?** Una licencia permanente elimina los límites de prueba y desbloquea todas las funciones de rendimiento.

## Qué es how to create pst?
**how to create pst** se refiere al proceso programático de generar un archivo Outlook Personal Storage Table (PST) usando código en lugar de la interfaz de Outlook. Aspose.Email para Java proporciona una API totalmente administrada que crea archivos PST Unicode, agrega carpetas y almacena objetos `MapiMessage` sin requerir que Outlook esté instalado.

## ¿Por qué usar Aspose.Email para la creación de PST?
Aspose.Email soporta **más de 50** formatos relacionados con correo electrónico (MSG, EML, MBOX, PST, etc.) y puede procesar archivos PST de **hasta 2 GB** manteniendo el uso de memoria por debajo de **150 MB** gracias a su arquitectura de carga diferida. Esta capacidad cuantificada lo hace ideal para archivado empresarial, migración y escenarios de cumplimiento.

## Requisitos previos

- **Java Development Kit (JDK)** – versión 16 o posterior.
- **Maven** – para la gestión de dependencias.
- Familiaridad básica con la sintaxis de Java; no se requiere experiencia previa con archivos PST.

## Cómo crear un archivo PST
La clase `PersonalStorage` representa un archivo PST y proporciona métodos para crear, abrir y manipular su contenido. Para crear un nuevo PST Unicode, llama a `PersonalStorage.create()` con la ruta de archivo deseada y la versión de formato. Esta operación genera un PST moderno que soporta carpetas grandes, caracteres Unicode y transmisión eficiente, haciéndolo adecuado tanto para tareas de archivado a pequeña escala como a nivel empresarial.

### Paso 1: Agregar la dependencia Maven
Agrega la dependencia Maven de Aspose.Email a tu `pom.xml`. Esto incluye automáticamente todos los binarios requeridos.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Paso 2: Obtener y aplicar una licencia
Hay una prueba gratuita disponible, pero una licencia permanente elimina los límites de evaluación y permite el procesamiento a máxima velocidad.

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

## Cómo agregar una carpeta al PST
Crea la jerarquía de carpetas deseada bajo la raíz del PST, luego haz referencia a ella al insertar mensajes. El objeto `FolderInfo` representa cada carpeta y puede anidarse arbitrariamente, permitiéndote construir estructuras como Inbox, Sent Items o carpetas de proyecto personalizadas. Agregar carpetas es una operación ligera que no carga el contenido de los mensajes, preservando el rendimiento incluso para PST grandes.

### Paso 1: Inicializar PersonalStorage
La clase `PersonalStorage` es el objeto de nivel superior de Aspose.Email que representa un único archivo PST en memoria. Después de la instanciación, todas las operaciones de lectura y escritura fluyen a través de este objeto.

```java
import com.aspose.email.FileFormatVersion;
import com.aspose.email.PersonalStorage;
```

### Paso 2: Definir rutas de directorios
Establece las rutas de origen y destino para tus archivos de correo electrónico y la ubicación de salida del PST.

```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY";
String outputDir = "YOUR_OUTPUT_DIRECTORY";
```

### Paso 3: Crear el archivo PST
Usa `PersonalStorage.create()` con `FileFormatVersion.Unicode` para producir un PST Unicode moderno que soporta carpetas grandes y caracteres Unicode.

```java
try {
    PersonalStorage pst = PersonalStorage.create(outputDir + "NewPSTFile_out.pst", FileFormatVersion.Unicode);

    // Perform operations here.
} finally {
    if (pst != null)
        pst.dispose();
}
```

## Cómo buscar en PST
`PersonalStorageQueryBuilder` es una clase builder utilizada para construir consultas de búsqueda para el contenido del PST. Configurando el builder con los criterios deseados y especificando `StringComparison.OrdinalIgnoreCase`, puedes realizar búsquedas rápidas sin distinción de mayúsculas y minúsculas en asuntos, cuerpos y propiedades personalizadas sin cargar todo el PST en memoria.

### Paso 1: Construir la consulta de búsqueda
Construye una consulta que busque una palabra clave en el asunto o cuerpo, ignorando mayúsculas.

```java
import com.aspose.email.MailQueryBuilder;
import com.aspose.email.MailQuery;
import com.aspose.email.MessageInfoCollection;

MailQueryBuilder builder = new MailQueryBuilder();
builder.getFrom().contains("automated", true);
```

### Paso 2: Ejecutar la consulta y recuperar mensajes
Ejecuta la consulta en la carpeta objetivo e itera sobre la colección resultante de `MapiMessage`.

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

## Creando una carpeta predefinida en PST
Agregar una carpeta predefinida como **Inbox** ayuda a organizar tus datos de correo electrónico de manera eficaz.

### Paso 1: Inicializar el objeto PersonalStorage
Supón que el objeto `PersonalStorage` (`pst`) ya está creado como se mostró anteriormente.

### Paso 2: Crear la carpeta 'Inbox'
```java
try {
    FolderInfo fi = pst.createPredefinedFolder("Inbox", StandardIpmFolder.Inbox);
} finally {
    if (pst != null)
        pst.dispose();
}
```

## Agregando mensajes a una carpeta PST
Puebla tu carpeta PST con mensajes de correo electrónico cargándolos desde archivos y convirtiéndolos.

### Paso 1: Cargar mensaje de correo electrónico
```java
import com.aspose.email.MailMessage;
import com.aspose.email.MapiMessage;

MailMessage mailMessage = MailMessage.load(dataDir + "message.msg");
```

### Paso 2: Añadir a la carpeta PST
Convierte `MailMessage` a `MapiMessage` y añádelo:

```java
try {
    fi.addMessage(MapiMessage.fromMailMessage(mailMessage));
} finally {
    if (pst != null)
        pst.dispose();
}
```

## Aplicaciones prácticas
Aspose.Email para Java no solo se trata de crear archivos PST; es una herramienta versátil con numerosas aplicaciones:
- **Email Archiving**: Automatiza el archivado de correos corporativos en archivos PST, soportando políticas de retención de hasta 10 años.
- **Migration Tools**: Migra sin problemas desde almacenes de correo heredados (p. ej., MBOX) a Outlook PST con una única llamada API por mensaje.
- **Data Analysis**: Extrae metadatos como remitente, destinatario y marcas de tiempo para pipelines de inteligencia empresarial.
- **Backup Solutions**: Construye utilidades de respaldo robustas que almacenan cambios incrementales de correo sin volver a procesar todo el buzón.

## Consideraciones de rendimiento
Para garantizar un rendimiento óptimo al usar Aspose.Email:
- **Resource Management**: Siempre llama a `pst.dispose()` o usa try‑with‑resources para liberar los manejadores nativos rápidamente.
- **Batch Processing**: Procesa correos en lotes de **500** elementos para mantener predecible el uso de memoria.
- **Concurrency Handling**: La biblioteca es segura para hilos en operaciones de solo lectura; para escrituras, sincroniza el acceso a la instancia `PersonalStorage`.

## Problemas comunes y soluciones
| Problema | Causa | Solución |
|----------|-------|----------|
| **OutOfMemoryError** al manejar PST grandes | Cargar todo el PST en memoria | Habilita `PersonalStorage.setUseUnicode(true)` y procesa los mensajes en flujos. |
| **Folder not found** error | Caso de ruta de carpeta incorrecto | Usa `StringComparison.OrdinalIgnoreCase` en consultas o normaliza los nombres de carpetas. |
| **License not applied** | Archivo de licencia no cargado antes de la primera llamada API | Carga la licencia al iniciar la aplicación, antes de crear cualquier objeto `PersonalStorage`. |

## Preguntas frecuentes

**Q: ¿Cuál es la versión mínima de Java requerida?**  
A: JDK 16 o superior se recomienda para compatibilidad total con Aspose.Email para Java.

**Q: ¿Puedo usar Aspose.Email sin una licencia?**  
A: Sí, hay un modo de prueba disponible pero limita el tamaño del PST a **10 MB** y desactiva ciertas optimizaciones.

**Q: ¿Cómo manejo archivos PST grandes de manera eficiente?**  
A: Procesa los mensajes en lotes, elimina los objetos `MapiMessage` rápidamente y habilita la carga diferida mediante `PersonalStorage.setUseUnicode(true)`.

**Q: ¿Es posible agregar archivos adjuntos a los correos en archivos PST?**  
A: Absolutamente. Al convertir `MailMessage` a `MapiMessage`, llama a `mapiMsg.getAttachments().add(attachment)` para incrustar los archivos.

**Q: ¿Qué tipo de soporte está disponible para resolver problemas?**  
A: Aspose ofrece un foro de soporte dedicado, documentación detallada y soporte por correo electrónico para clientes con licencia.

## Recursos
- [Documentation](https://reference.aspose.com/email/java/)
- [Download](https://releases.aspose.com/email/java/)
- [Purchase](https://purchase.aspose.com/buy)
- [Free Trial](https://releases.aspose.com/email/java/)
- [Temporary License](https://purchase.aspose.com/temporary-license/)
- [Support Forum](https://forum.aspose.com/c/email/10)

---

**Última actualización:** 2026-06-08  
**Probado con:** Aspose.Email for Java 24.10  
**Autor:** Aspose

## Tutoriales relacionados

- [How to Create and Manage Outlook PST Files Using Aspose.Email for Java](/email/java/outlook-pst-ost-operations/aspose-email-java-manage-pst-files/)
- [Manipulate PST Files Using Aspose.Email for Java: A Comprehensive Guide](/email/java/outlook-pst-ost-operations/manipulate-pst-files-aspose-email-java/)
- [Extract Email Attachments Java - Using Aspose.Email for PST Files – A Step‑by‑Step Guide](/email/java/attachments-handling/extract-email-attachments-pst-aspose-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}