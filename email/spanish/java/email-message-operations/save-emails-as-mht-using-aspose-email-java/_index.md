---
date: '2026-03-02'
description: Aprende a usar Maven Aspose.Email para Java para guardar correos electrónicos
  como archivos MHT. Esta guía paso a paso cubre la configuración, plantillas personalizadas
  y la conversión de correo electrónico a MHT.
keywords:
- save emails as MHT files
- Aspose.Email for Java
- convert emails to MHTML
title: 'Maven Aspose.Email para Java: Guardar correos electrónicos como archivos MHT'
url: /es/java/email-message-operations/save-emails-as-mht-using-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Maven Aspose.Email for Java: Cómo guardar correos electrónicos como archivos MHT

## Introducción

Gestionar los datos de correo electrónico de manera eficiente puede ser un desafío, especialmente cuando se trata de compartir y archivar. En esta guía le mostraremos **cómo guardar archivos MHT** usando **Maven Aspose.Email for Java**, para que pueda convertir correos a MHT con plantillas personalizadas y mantener los eventos del calendario intactos. Obtendrá una solución lista‑para‑ejecutar que funciona en cualquier entorno Java 16+.

## Respuestas rápidas
- **¿Qué biblioteca necesito?** Maven Aspose.Email for Java (v25.4+).  
- **¿Qué formato se produce?** Un archivo MHT (MHTML) que agrupa HTML, imágenes y datos del calendario.  
- **¿Puedo personalizar el encabezado?** Sí – use `MhtFormatOptions` y cadenas de plantilla.  
- **¿Necesito una licencia?** Una prueba gratuita funciona para evaluación; se requiere una licencia permanente para producción.  
- **¿Qué versión de Java se requiere?** JDK 16 o posterior.

## ¿Qué es Maven Aspose.Email for Java?
Maven Aspose.Email for Java es una API potente que le permite crear, leer, convertir y manipular mensajes de correo electrónico directamente desde código Java. Soporta una amplia gama de formatos —incluidos MSG, EML y MHT— lo que la hace ideal para tareas de **conversión de correo electrónico java**.

## ¿Por qué convertir correos electrónicos a MHT?
- **Amigable para la web**: los archivos MHT se renderizan en navegadores sin recursos externos.  
- **Estabilidad de archivo**: todos los recursos están incrustados, preservando el aspecto original.  
- **Soporte de calendario**: puede renderizar eventos recurrentes con plantillas personalizadas.  

## Requisitos previos
- **Aspose.Email for Java** (artefacto Maven `com.aspose:aspose-email:25.4` con clasificador `jdk16`).  
- **Maven** instalado y configurado en su máquina.  
- **JDK 16+** (la biblioteca está dirigida a Java 16).  
- Conocimientos básicos de Java (manejo de archivos, dependencias Maven).

## Configuración de Aspose.Email for Java

### Dependencia Maven

Agregue la siguiente dependencia a su archivo `pom.xml`:

```xml
<dependency>
  <groupId>com.aspose</groupId>
  <artifactId>aspose-email</artifactId>
  <version>25.4</version>
  <classifier>jdk16</classifier>
</dependency>
```

### Obtención de licencia

Aspose ofrece una prueba gratuita para explorar sus capacidades, junto con opciones para comprar una licencia u obtener una temporal.

1. **Prueba gratuita**: Descargue desde [Releases](https://releases.aspose.com/email/java/) y explore las funciones sin limitaciones.  
2. **Licencia temporal**: Acceda a una versión totalmente funcional solicitándola a través de la [Temporary License Page](https://purchase.aspose.com/temporary-license/).  
3. **Compra**: Considere comprar si Aspose.Email satisface las necesidades a largo plazo de su proyecto.

### Inicialización básica

Una vez instalado, inicialice la biblioteca en su aplicación Java:

```java
import com.aspose.email.License;

License license = new License();
license.setLicense("path/to/your/license/file");
```

Con estos pasos completados, está listo para usar las funciones de Aspose.Email para una gestión eficiente del correo electrónico.

## Guía de implementación

### Función 1: Cargar MailMessage

#### Visión general
Cargar un mensaje de correo electrónico es el primer paso para procesarlo y guardarlo como archivo MHT. Aquí, demostramos cómo cargar un archivo `.msg` usando `MailMessage`.

#### Paso a paso

**Importar clases requeridas**

```java
import com.aspose.email.MailMessage;
```

**Cargar correo electrónico desde archivo**

```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY" + "/email/";
MailMessage msg = MailMessage.load(dataDir + "Meeting with Recurring Occurrences.msg");
```

Este fragmento carga un mensaje de correo electrónico ubicado en el directorio que especificó.

### Función 2: Configurar MhtSaveOptions

#### Visión general
Configurar `MhtSaveOptions` es crucial para definir cómo se guardará su correo electrónico como archivo MHT, incluyendo formato personalizado para eventos de calendario.

#### Paso a paso

**Importar clases requeridas**

```java
import com.aspose.email.MhtSaveOptions;
import com.aspose.email.MhtFormatOptions;
import com.aspose.email.MhtTemplateName;
```

**Establecer opciones de guardado y plantillas**

```java
MhtSaveOptions options = new MhtSaveOptions();
options.setMhtFormatOptions(MhtFormatOptions.WriteHeader | MhtFormatOptions.RenderCalendarEvent);

// Customize templates for email properties
for (Map.Entry<MhtTemplateName, String> entry : options.getFormatTemplates().entrySet()) {
    switch (entry.getKey()) {
        case START:
            options.getFormatTemplates().set_Item(MhtTemplateName.START,
                    "<span class='headerLineTitle'>Start:</span><span class='headerLineText'>{0}</span><br/>");
            break;
        // Add other cases similarly...
    }
}

// Ensure entries are added if absent
options.getFormatTemplates().addIfAbsent(MhtTemplateName.START,
            "<span class='headerLineTitle'>Start:</span><span class='headerLineText'>{0}</span><br/>");
```

Esta configuración establece encabezados y la representación de eventos de calendario en la salida MHT.

### Función 3: Guardar MailMessage como MHT

#### Visión general
El paso final es guardar su `MailMessage` configurado como archivo MHT usando las opciones especificadas.

#### Paso a paso

**Importar clases requeridas**

```java
import com.aspose.email.MailMessage;
import com.aspose.email.MhtSaveOptions;
```

**Guardar mensaje de correo**

```java
msg.save("YOUR_OUTPUT_DIRECTORY" + "Meeting with Recurring Occurrences_out.mhtml", options);
```

Este comando escribe el correo electrónico en un archivo MHT, listo para compartir o archivar.

## Aplicaciones prácticas
- **Archivado de correos**: convierta y almacene correos importantes en un formato amigable para la web.  
- **Documentación legal**: use archivos MHT como parte de evidencia legal donde se necesita preservar los detalles del correo.  
- **Compartir multiplataforma**: comparta correos entre plataformas sin problemas de compatibilidad.  

Integrar con otros sistemas, como CRM o herramientas de gestión de proyectos, puede mejorar la colaboración al incrustar datos críticos de correo directamente en los flujos de trabajo.

## Consideraciones de rendimiento
Para garantizar un rendimiento óptimo:
- Gestione el uso de memoria de manera eficaz al manejar grandes lotes de correos.  
- Optimice las operaciones de E/S de archivos para evitar cuellos de botella durante el proceso de guardado.  

Seguir las mejores prácticas de gestión de memoria en Java mantendrá su aplicación receptiva.

## Problemas comunes y soluciones

| Problema | Causa | Solución |
|-------|-------|-----|
| **NullPointerException en `msg.save`** | Ruta de salida incorrecta | Verifique que `YOUR_OUTPUT_DIRECTORY` exista y tenga permisos de escritura. |
| **Imágenes faltantes en MHT** | `MhtFormatOptions` no está configurado para incrustar recursos | Añada `MhtFormatOptions.EmbedResources` al indicador de opciones. |
| **Eventos de calendario no renderizados** | Falta la bandera `RenderCalendarEvent` | Asegúrese de que `options.setMhtFormatOptions(MhtFormatOptions.WriteHeader \| MhtFormatOptions.RenderCalendarEvent);` |

## Preguntas frecuentes

**P: ¿Cómo manejo los archivos adjuntos al guardar correos como MHT?**  
R: Asegúrese de que `MhtSaveOptions` esté configurado para incluir la lógica de manejo de adjuntos. La biblioteca soporta incrustar adjuntos en el archivo MHT.

**P: ¿Puedo personalizar los encabezados del correo en el archivo MHT de salida?**  
R: Sí, use `MhtFormatOptions.WriteHeader` y defina plantillas personalizadas para varios campos de encabezado como se muestra en el tutorial.

**P: ¿Cuáles son los requisitos del sistema para usar Aspose.Email Java?**  
R: Se requiere JDK 16 o superior. La biblioteca funciona sin problemas con la mayoría de los IDE modernos que soportan proyectos Maven.

**P: ¿Es posible guardar solo partes específicas de un mensaje de correo?**  
R: Aunque el formato MHT normalmente incluye mensajes completos, puede usar las propiedades de `MailMessage` para procesar e incluir contenido de forma selectiva.

**P: ¿Cómo puedo solucionar problemas al cargar o guardar correos?**  
R: Verifique que las rutas de archivo sean correctas, asegure una configuración adecuada de la biblioteca en su proyecto y consulte el [foro de soporte de Aspose.Email](https://forum.aspose.com/c/email/10) para obtener ayuda.

**P: ¿La biblioteca soporta convertir otros formatos (EML, MSG) a MHT?**  
R: Absolutamente. `MailMessage.load` puede leer EML, MSG y otros formatos, después de lo cual puede guardarlos como MHT usando las mismas opciones.

## Recursos
- **Documentación**: Para profundizar en todas las funcionalidades, visite la [Aspose Email Java Documentation](https://reference.aspose.com/email/java/).  
- **Descarga**: Comience con su prueba gratuita descargando desde [Releases](https://releases.aspose.com/email/java/).  
- **Compra**: Explore opciones de compra en la [Official Purchase Page](https://purchase.aspose.com/buy) para uso a largo plazo.  
- **Prueba gratuita y licencia temporal**: Acceda a funciones completas durante una prueba gratuita u obtenga una licencia temporal a través de estos enlaces:  
  - [Free Trial](https://releases.aspose.com/email/java/)  
  - [Temporary License](https://purchase.aspose.com/temporary-license/)

¡Explore, implemente y transforme su gestión de correo electrónico con Aspose.Email for Java hoy!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Última actualización:** 2026-03-02  
**Probado con:** Aspose.Email for Java 25.4 (clasificador jdk16)  
**Autor:** Aspose