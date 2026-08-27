---
date: '2026-08-27'
description: Aprenda a cargar archivos MSG y convertirlos a MHTML con Aspose.Email
  for Java, incluyendo configuraciones personalizadas de zona horaria y consejos para
  el procesamiento por lotes de correos electrónicos.
keywords:
- how to load msg
- Aspose.Email Java
- convert MSG to MHTML
- email timezone offset
lastmod: '2026-08-27'
og_description: Aprenda a cargar archivos msg y exportarlos como MHTML usando Aspose.Email
  for Java. Incluye manejo de zona horaria y consejos de procesamiento por lotes.
og_image_alt: Guide to loading MSG files and saving as MHTML with Aspose.Email for
  Java
og_title: Cómo cargar msg y guardarlo como MHTML con Aspose.Email for Java
schemas:
- author: Aspose
  dateModified: '2026-08-27'
  description: Learn how to load MSG files and convert them to MHTML with Aspose.Email
    for Java, including custom timezone settings and batch email processing tips.
  headline: How to load msg and save as MHTML using Aspose.Email for Java
  type: TechArticle
- description: Learn how to load MSG files and convert them to MHTML with Aspose.Email
    for Java, including custom timezone settings and batch email processing tips.
  name: How to load msg and save as MHTML using Aspose.Email for Java
  steps:
  - name: '**Reuse the license** – call `new License().setLicense(...)` once at application
      startup.'
    text: '**Reuse the license** – call `new License().setLicense(...)` once at application
      startup.'
  - name: '**Use try‑with‑resources** for automatic cleanup of streams.'
    text: '**Use try‑with‑resources** for automatic cleanup of streams.'
  - name: '**Log failures** to a separate file so you can retry problematic messages
      later.'
    text: '**Log failures** to a separate file so you can retry problematic messages
      later.'
  - name: '**Consider parallelism** with `ForkJoinPool` for large batches, but ensure
      each thread uses its own `MailMessage` instance.'
    text: '**Consider parallelism** with `ForkJoinPool` for large batches, but ensure
      each thread uses its own `MailMessage` instance.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Email supports EML, MHT, EMLX, and several other formats,
      totaling over 30 input types.
    question: Can I load emails from formats other than .msg?
  - answer: Use the streaming APIs (`MailMessage.load(InputStream, ...)`) to read
      and write data in chunks, which keeps memory consumption under 50 MB even for
      500‑page messages.
    question: How can I handle very large email files efficiently?
  - answer: Absolutely. You can add, remove, or replace attachments via the `msg.getAttachments()`
      collection, then call `save` to persist changes.
    question: Is it possible to modify attachments within a MailMessage?
  - answer: Pass a negative millisecond value to `setTimeZoneOffset`, e.g., `-3 *
      60 * 60 * 1000` for UTC‑3.
    question: What if my timezone offset is negative (behind UTC)?
  - answer: Yes, provided you have a valid commercial license. The free trial is limited
      to 20 MB per document.
    question: Can I use Aspose.Email in commercial projects?
  type: FAQPage
tags:
- email processing
- Aspose.Email
- Java email conversion
title: Cómo cargar msg y guardarlo como MHTML usando Aspose.Email for Java
url: /es/java/email-message-operations/load-save-emails-mhtml-aspose-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo cargar msg y guardar como MHTML usando Aspose.Email para Java

## Introducción

Si necesitas **how to load msg** archivos, ajustar sus marcas de tiempo y luego **convert msg to mhtml**, estás en el lugar correcto. En este tutorial recorreremos la carga de un correo electrónico `.msg`, aplicando un desplazamiento de zona horaria personalizado y guardando el resultado como un archivo MHTML, todo con Aspose.Email para Java. Ya sea que estés manejando un solo mensaje o una **batch email processing** pipeline, estos pasos te proporcionarán una base sólida para un archivado y migración confiables.

**Qué aprenderás**
- Cómo cargar un `MailMessage` desde un archivo `.msg`.
- Cómo establecer una zona horaria personalizada y la fecha actual.
- Cómo guardar el mensaje como MHTML con formato preciso.
- Consejos para escalar el enfoque a escenarios por lotes.

¿Listo para mejorar tu flujo de trabajo de correo electrónico? Primero preparemos el entorno.

## Respuestas rápidas
- **¿Cuál es la biblioteca principal?** Aspose.Email for Java.
- **¿Puedo cargar MSG y exportar a MHTML en un solo paso?** No, cargas, ajustas y luego guardas.
- **¿Necesito una licencia para producción?** Sí, se requiere una licencia válida de Aspose.Email.
- **¿Se admite el manejo de zona horaria?** Sí, mediante `setTimeZoneOffset`.
- **¿Se puede usar en procesamiento por lotes?** Absolutamente – envuelve los pasos en un bucle.

## ¿Qué es Aspose.Email para Java?

Aspose.Email para Java es una API integral que te permite crear, leer, convertir y manipular mensajes de correo electrónico sin requerir Microsoft Outlook. Soporta más de 30 formatos de correo electrónico y puede procesar mensajes de cientos de páginas manteniendo bajo el uso de memoria.

## ¿Por qué convertir MSG a MHTML?

Convertir archivos MSG a MHTML te brinda una representación web‑amigable, de un solo archivo, que puede abrirse en cualquier navegador moderno. Este formato conserva el estilo original, imágenes incrustadas y archivos adjuntos, lo que lo hace ideal para **legal archiving**, **cross‑platform sharing**, y **embedding emails into web pages or documentation**.

## Requisitos previos

Antes de comenzar, asegúrate de tener lo siguiente:

### Bibliotecas y dependencias requeridas
- **Aspose.Email for Java** library version 25.4 (jdk16 classifier) – la biblioteca soporta **50+** formatos de correo de entrada y salida.
- Conocimientos básicos de Java.
- Un IDE como IntelliJ IDEA o Eclipse.

### Requisitos de configuración del entorno
- JDK 16 o superior instalado.
- Maven para la gestión de dependencias.

## Configuración de Aspose.Email para Java

Para agregar la biblioteca a un proyecto Maven, incluye la siguiente dependencia:

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

### Pasos para adquirir la licencia

Comienza con una **free trial** o obtén una **temporary license** para evaluar todas las capacidades de la biblioteca sin limitaciones. Para uso a largo plazo, considera comprar una licencia:

- [Prueba gratuita](https://releases.aspose.com/email/java/)
- [Licencia temporal](https://purchase.aspose.com/temporary-license/)
- [Comprar licencia](https://purchase.aspose.com/buy)

### Inicialización básica

La clase `License` registra tu licencia de Aspose.Email para desbloquear todas las funciones.  
Después de agregar la dependencia, inicializa la licencia en tu código Java:

```java
import com.aspose.email.License;

License license = new License();
license.setLicense("Aspose.Email.lic");
```
```java
import com.aspose.email.License;

License license = new License();
license.setLicense("path_to_your_license_file.lic");
```

## ¿Cómo cargar msg y guardar como MHTML?

Carga el archivo MSG, ajusta la marca de tiempo y guárdalo como MHTML en tres pasos sencillos. Primero, instancia un `MailMessage` a partir del archivo MSG usando `MsgLoadOptions`. Luego, establece el desplazamiento de zona horaria deseado con `setTimeZoneOffset`. Finalmente, configura `MhtSaveOptions` y llama a `save` para generar el archivo MHTML.

### Función 1: cargar un MailMessage desde un archivo

La clase `MailMessage` representa un mensaje de correo electrónico con encabezados, cuerpo y archivos adjuntos.

```java
import com.aspose.email.MailMessage;
import com.aspose.email.MsgLoadOptions;
```
```java
import com.aspose.email.MailMessage;
import com.aspose.email.MsgLoadOptions;
```

```java
MsgLoadOptions loadOptions = new MsgLoadOptions();
MailMessage msg = MailMessage.load("sample.msg", loadOptions);
```
```java
String filename = "YOUR_DOCUMENT_DIRECTORY/MSG file with RTF Formatting.msg";
MailMessage msg = MailMessage.load(filename, new MsgLoadOptions());
```

`MsgLoadOptions` te permite controlar cómo se analiza el archivo MSG; la configuración predeterminada funciona para la mayoría de los escenarios.

### Función 2: establecer la fecha actual y el desplazamiento de zona horaria personalizado

El objeto `Date` contiene la marca de tiempo que se escribirá en el encabezado **Date** del correo.

```java
java.util.Date now = new java.util.Date();
msg.setDate(now);
```
```java
import java.util.Date;

msg.setDate(new Date());
```

El desplazamiento se expresa en milisegundos; para UTC+5 pasa `5 * 60 * 60 * 1000`.

```java
int utcPlusFive = 5 * 60 * 60 * 1000;
msg.setTimeZoneOffset(utcPlusFive);
```
```java
msg.setTimeZoneOffset(5 * 60 * 60 * 1000); // 5 hours ahead of UTC in milliseconds.
```

### Función 3: guardar un MailMessage como archivo MHTML

`MhtSaveOptions` define cómo el correo se empaqueta en un archivo MHTML, preservando imágenes en línea y archivos adjuntos.

```java
import com.aspose.email.MhtSaveOptions;
MhtSaveOptions saveOptions = new MhtSaveOptions();
saveOptions.setWriteHeader(true);
```
```java
import com.aspose.email.MhtSaveOptions;
import com.aspose.email.MhtFormatOptions;

MhtSaveOptions mhtOptions = new MhtSaveOptions();
mhtOptions.setMhtFormatOptions(MhtFormatOptions.WriteHeader);
```

```java
msg.save("output.mhtml", saveOptions);
```
```java
msg.save("YOUR_OUTPUT_DIRECTORY/ExportToMHTWithCustomTimezone_out.mhtml", mhtOptions);
```

El archivo `.mhtml` resultante conserva el formato original, imágenes y archivos adjuntos, convirtiéndose en una copia visual fiel del MSG original.

## ¿Cómo establecer un desplazamiento de zona horaria personalizado?

Puedes modificar la zona horaria llamando a `setTimeZoneOffset` en la instancia de `MailMessage`. El método espera un desplazamiento en milisegundos, permitiendo valores positivos (este de UTC) y negativos (oeste de UTC). Por ejemplo, UTC‑3 es `-3 * 60 * 60 * 1000`.

## ¿Cómo procesar archivos MSG por lotes?

Envuelve el flujo de trabajo de tres pasos dentro de un bucle que itere sobre un directorio de archivos `.msg`. Reutiliza una única instancia de `License` para evitar I/O repetido y libera cada `MailMessage` después de guardarlo para mantener bajo el uso de memoria.

```java
File folder = new File("msg_folder");
for (File file : folder.listFiles((dir, name) -> name.toLowerCase().endsWith(".msg"))) {
    MailMessage msg = MailMessage.load(file.getAbsolutePath(), new MsgLoadOptions());
    // set date & timezone as shown earlier
    msg.save(file.getName().replace(".msg", ".mhtml"), new MhtSaveOptions());
    msg.dispose(); // releases native resources
}
```

### Consejos para procesamiento por lotes
1. **Reutiliza la licencia** – llama a `new License().setLicense(...)` una vez al iniciar la aplicación.
2. **Usa try‑with‑resources** para la limpieza automática de streams.
3. **Registra fallos** en un archivo separado para que puedas reintentar los mensajes problemáticos más tarde.
4. **Considera paralelismo** con `ForkJoinPool` para lotes grandes, pero asegura que cada hilo use su propia instancia de `MailMessage`.

## Problemas comunes y soluciones

- **Picos de memoria con archivos MSG enormes** – habilita streaming usando `MailMessage.load(InputStream, MsgLoadOptions)` y procesa el stream en fragmentos.
- **Marcas de tiempo incorrectas** – verifica que el reloj del sistema esté configurado a UTC antes de aplicar desplazamientos, o pasa explícitamente una instancia de `java.util.Calendar`.
- **Faltan archivos adjuntos en MHTML** – asegura `MhtSaveOptions.setWriteHeader(true)`; esto incrusta los adjuntos como recursos `cid:`.

## Preguntas frecuentes

**Q: ¿Puedo cargar correos electrónicos de formatos diferentes a .msg?**  
A: Sí, Aspose.Email soporta EML, MHT, EMLX y varios otros formatos, sumando más de 30 tipos de entrada.

**Q: ¿Cómo puedo manejar archivos de correo muy grandes de manera eficiente?**  
A: Usa las APIs de streaming (`MailMessage.load(InputStream, ...)`) para leer y escribir datos en fragmentos, lo que mantiene el consumo de memoria bajo 50 MB incluso para mensajes de 500 páginas.

**Q: ¿Es posible modificar los archivos adjuntos dentro de un MailMessage?**  
A: Absolutamente. Puedes agregar, eliminar o reemplazar adjuntos a través de la colección `msg.getAttachments()`, luego llamar a `save` para persistir los cambios.

**Q: ¿Qué pasa si mi desplazamiento de zona horaria es negativo (detrás de UTC)?**  
A: Pasa un valor negativo en milisegundos a `setTimeZoneOffset`, por ejemplo, `-3 * 60 * 60 * 1000` para UTC‑3.

**Q: ¿Puedo usar Aspose.Email en proyectos comerciales?**  
A: Sí, siempre que cuentes con una licencia comercial válida. La prueba gratuita está limitada a 20 MB por documento.

**Q: ¿Cómo proceso miles de archivos MSG sin quedarme sin memoria?**  
A: Procesa los archivos en lotes, libera cada `MailMessage` después de guardarlo y emplea el patrón `try‑with‑resources` de Java para la limpieza automática.

## Recursos
- [documentación](https://reference.aspose.com/email/java/)
- [Documentación](https://reference.aspose.com/email/java/)
- [Descargar biblioteca](https://releases.aspose.com/email/java/)
- [Comprar licencia](https://purchase.aspose.com/buy)
- [Prueba gratuita](https://releases.aspose.com/email/java/)
- [Licencia temporal](https://purchase.aspose.com/temporary-license/)
- [Foro de soporte](https://forum.aspose.com/c/email/10)

---

**Última actualización:** 2026-08-27  
**Probado con:** Aspose.Email for Java 25.4 (jdk16 classifier)  
**Autor:** Aspose

## Tutoriales relacionados

- [Cómo cargar y analizar archivos Outlook MSG usando Aspose.Email para Java: Guía completa](/email/java/mapi-operations/outlook-msg-aspose-email-java-guide/)
- [Maven Aspose.Email para Java: Guardar correos como archivos MHT](/email/java/email-message-operations/save-emails-as-mht-using-aspose-email-java/)
- [Cómo extraer archivos adjuntos de archivos msg usando Aspose.Email para Java](/email/java/advanced-email-attachments/extracting-attachments-from-email-messages/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}