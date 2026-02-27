---
date: '2026-02-27'
description: Aprenda a cargar archivos MSG y convertirlos a MHTML con Aspose.Email
  para Java, incluyendo configuraciones de zona horaria personalizadas y consejos
  para el procesamiento por lotes de correos electrónicos.
keywords:
- Aspose.Email for Java
- load emails in MHTML format
- custom timezone settings
title: Cómo cargar MSG y guardar como MHTML usando Aspose.Email para Java
url: /es/java/email-message-operations/load-save-emails-mhtml-aspose-java/
weight: 1
---

 content.{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cómo cargar MSG y guardar como MHTML usando Aspose.Email para Java

## Introducción

Si necesitas **cargar archivos msg**, ajustar sus marcas de tiempo y luego **convertir msg a mhtml**, estás en el lugar correcto. En este tutorial recorreremos la carga de un correo electrónico `.msg`, la aplicación de un desplazamiento de zona horaria personalizado y el guardado del resultado como un archivo MHTML, todo con Aspose.Email para Java. Ya sea que estés manejando un solo mensaje o una **línea de procesamiento por lotes de correos electrónicos**, estos pasos te proporcionarán una base sólida.

**Lo que aprenderás**
- Cómo cargar un `MailMessage` desde un archivo `.msg`.
- Cómo establecer una zona horaria personalizada y la fecha actual.
- Cómo guardar el mensaje como MHTML con un formato preciso.
- Consejos para escalar el enfoque a escenarios por lotes.

¿Listo para mejorar tu flujo de trabajo de correo electrónico? Primero preparemos el entorno.

## Respuestas rápidas
- **¿Cuál es la biblioteca principal?** Aspose.Email para Java.
- **¿Puedo cargar MSG y exportar a MHTML en un solo paso?** No, primero cargas, ajustas y luego guardas.
- **¿Necesito una licencia para producción?** Sí, se requiere una licencia válida de Aspose.Email.
- **¿Se admite el manejo de zonas horarias?** Sí, mediante `setTimeZoneOffset`.
- **¿Puede usarse en procesamiento por lotes?** Absolutamente – envuelve los pasos en un bucle.

## Requisitos previos

Antes de comenzar, asegúrate de contar con lo siguiente:

### Bibliotecas y dependencias requeridas
- Biblioteca **Aspose.Email para Java** versión 25.4 (clasificador jdk16)
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

### Pasos para obtener la licencia

Comienza con una **prueba gratuita** o adquiere una **licencia temporal** para evaluar todas las capacidades de la biblioteca sin limitaciones. Para uso a largo plazo, considera comprar una licencia:

- [Free Trial](https://releases.aspose.com/email/java/)
- [Temporary License](https://purchase.aspose.com/temporary-license/)
- [Purchase License](https://purchase.aspose.com/buy)

### Inicialización básica

Después de agregar la dependencia, inicializa la licencia en tu código Java:

```java
import com.aspose.email.License;

License license = new License();
license.setLicense("path_to_your_license_file.lic");
```

## Guía de implementación

Dividiremos la implementación en tres características claras.

### Característica 1: Cargar un MailMessage desde un archivo

#### Visión general
Cargar un archivo `.msg` te brinda acceso programático completo al contenido del correo, sus adjuntos y metadatos.

#### Paso a paso

**Importa las clases necesarias**

```java
import com.aspose.email.MailMessage;
import com.aspose.email.MsgLoadOptions;
```

**Carga el correo**

```java
String filename = "YOUR_DOCUMENT_DIRECTORY/MSG file with RTF Formatting.msg";
MailMessage msg = MailMessage.load(filename, new MsgLoadOptions());
```

`MsgLoadOptions` te permite controlar cómo se interpreta el archivo MSG; la configuración predeterminada funciona para la mayoría de los escenarios.

### Característica 2: Establecer la fecha actual y un desplazamiento de zona horaria personalizado

#### Visión general
Las marcas de tiempo precisas son esenciales cuando trabajas con usuarios en diferentes regiones.

**Establece la fecha actual**

```java
import java.util.Date;

msg.setDate(new Date());
```

**Aplica un desplazamiento de zona horaria personalizado (p. ej., UTC+5)**

```java
msg.setTimeZoneOffset(5 * 60 * 60 * 1000); // 5 hours ahead of UTC in milliseconds.
```

El desplazamiento se expresa en milisegundos, por lo que también puedes pasar valores negativos para zonas al oeste de UTC.

### Característica 3: Guardar un MailMessage como archivo MHTML

#### Visión general
MHTML agrupa contenido HTML y recursos incrustados en un solo archivo, perfecto para archivado o compartición.

**Configura las opciones de guardado**

```java
import com.aspose.email.MhtSaveOptions;
import com.aspose.email.MhtFormatOptions;

MhtSaveOptions mhtOptions = new MhtSaveOptions();
mhtOptions.setMhtFormatOptions(MhtFormatOptions.WriteHeader);
```

**Guarda el correo**

```java
msg.save("YOUR_OUTPUT_DIRECTORY/ExportToMHTWithCustomTimezone_out.mhtml", mhtOptions);
```

El archivo `.mhtml` resultante conserva el formato original, imágenes y adjuntos.

## ¿Por qué convertir MSG a MHTML?

Convertir archivos MSG a MHTML te brinda una representación web‑amigable, de un solo archivo, que puede abrirse en cualquier navegador moderno. Esto es especialmente útil para:

- **Archivado legal** donde se requiere una copia visual fiel.
- **Compartición multiplataforma** sin necesidad de Outlook.
- **Incorporar correos** en páginas web o documentación.

## Consejos para el procesamiento por lotes de correos electrónicos

Si necesitas **procesamiento por lotes de correos electrónicos**, envuelve los pasos de carga, ajuste de zona horaria y guardado dentro de un bucle que recorra un directorio de archivos `.msg`. Recuerda:

1. Reutilizar una única instancia de `License` para evitar sobrecarga.
2. Liberar recursos después de cada iteración (`msg.dispose()` si corresponde).
3. Registrar cualquier fallo en un archivo separado para revisión posterior.

## Aplicaciones prácticas

1. **Archivado de correos:** Preserva comunicaciones en un formato portátil para cumplimiento.
2. **Programación global:** Ajusta marcas de tiempo a una zona horaria unificada antes de enviar notificaciones.
3. **Integración CRM:** Importa automáticamente correos archivados a un sistema CRM como adjuntos MHTML.

## Consideraciones de rendimiento

- **Gestión de memoria:** Procesa lotes grandes en fragmentos para mantener bajo el consumo de memoria.
- **Optimización de E/S:** Usa streams con búfer si lees/escribes muchos archivos.
- **Ejecución paralela:** Considera `ForkJoinPool` de Java para procesamiento paralelo, pero garantiza la seguridad de subprocesos de los objetos Aspose.

## Conclusión

Ahora sabes **cómo cargar archivos msg**, aplicar desplazamientos de zona horaria personalizados y **convertir msg a mhtml** usando Aspose.Email para Java. Estas técnicas pueden escalarse para manejar tareas de **procesamiento por lotes de correos electrónicos**, brindándote una solución robusta para archivado, migración y automatización de correos.

**Próximos pasos**  
Explora características adicionales de Aspose.Email como manejo de adjuntos, extracción de elementos de calendario o envío SMTP visitando la [documentación](https://reference.aspose.com/email/java/) oficial.

## Preguntas frecuentes

**P: ¿Puedo cargar correos de formatos distintos a .msg?**  
R: Sí, Aspose.Email admite EML, MSG, MHT y varios otros formatos.

**P: ¿Cómo puedo manejar archivos de correo muy grandes de forma eficiente?**  
R: Utiliza las API de streaming que proporciona Aspose.Email para leer/escribir datos en fragmentos, reduciendo la presión de memoria.

**P: ¿Es posible modificar los adjuntos dentro de un MailMessage?**  
R: Absolutamente. Puedes agregar, eliminar o reemplazar adjuntos mediante la colección `MailMessage.getAttachments()`.

**P: ¿Qué ocurre si mi desplazamiento de zona horaria es negativo (detrás de UTC)?**  
R: Pasa un valor negativo en milisegundos a `setTimeZoneOffset`, por ejemplo, `-3 * 60 * 60 * 1000` para UTC‑3.

**P: ¿Puedo usar Aspose.Email en proyectos comerciales?**  
R: Sí, siempre que cuentes con una licencia comercial válida.

**P: ¿Cómo proceso miles de archivos MSG sin quedarme sin memoria?**  
R: Procesa los archivos en lotes, libera cada `MailMessage` después de guardarlo y considera usar el patrón `try‑with‑resources` de Java para la limpieza automática.

---

**Última actualización:** 2026-02-27  
**Probado con:** Aspose.Email para Java 25.4 (clasificador jdk16)  
**Autor:** Aspose  

## Recursos
- [Documentation](https://reference.aspose.com/email/java/)
- [Download Library](https://releases.aspose.com/email/java/)
- [Purchase License](https://purchase.aspose.com/buy)
- [Free Trial](https://releases.aspose.com/email/java/)
- [Temporary License](https://purchase.aspose.com/temporary-license/)
- [Support Forum](https://forum.aspose.com/c/email/10)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}