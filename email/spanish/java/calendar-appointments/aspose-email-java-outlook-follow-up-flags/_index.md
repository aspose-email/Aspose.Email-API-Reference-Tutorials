---
date: '2026-07-27'
description: Aprenda cómo establecer la bandera de Outlook Java usando Aspose.Email
  para Java, cubriendo la creación de banderas, banderas de destinatarios, finalización,
  eliminación y opciones de lectura.
keywords:
- set outlook flag java
- outlook follow up flag java
- aspose email java
lastmod: '2026-07-27'
og_description: Establezca la bandera de Outlook Java con Aspose.Email para Java.
  Esta guía muestra cómo crear, leer, completar y eliminar banderas de seguimiento
  de Outlook de manera eficiente.
og_image_alt: 'Developer guide: Set Outlook flag Java using Aspose.Email'
og_title: Establecer bandera de Outlook Java – Guía completa de programación de Aspose.Email
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Learn how to set outlook flag java using Aspose.Email for Java, covering
    flag creation, recipient flags, completion, removal, and reading options.
  headline: Set Outlook Flag Java – Complete Aspose.Email Programming Guide
  type: TechArticle
- description: Learn how to set outlook flag java using Aspose.Email for Java, covering
    flag creation, recipient flags, completion, removal, and reading options.
  name: Set Outlook Flag Java – Complete Aspose.Email Programming Guide
  steps:
  - name: Create and Initialize the Message
    text: '`MailMessage` is Aspose.Email’s high‑level class that represents an email.
      After you build the message, you convert it to a `MapiMessage` for flag manipulation.
      *We first build a `MailMessage`, set sender/recipient, then convert it to a
      `MapiMessage` for flag manipulation.*'
  - name: Define Follow‑Up Dates (Outlook Flag Reminder)
    text: '`FollowUpOptions` holds the start, reminder, and due dates. Use Java’s
      `Calendar` to set precise timestamps. *Here we set the start, reminder (the
      **outlook flag reminder**), and due dates using the `Calendar` class.*'
  - name: Apply Follow‑Up Options
    text: The `FollowUpManager.setOptions` method attaches the flag to the `MapiMessage`.
      *The `FollowUpOptions` object holds all flag details, which we apply with `FollowUpManager.setOptions`.*
  - name: Save the Message
    text: Save the flagged message as a `.msg` file so Outlook can display the flag.
      *The message is saved as a `.msg` file with the flag attached.*
  - name: Mark as Draft
    text: '`MessageFlags` is a MAPI enumeration that controls the state of the message.
      Setting `MSGFLAG_UNSENT` tells Outlook the item is a draft. *Marking the message
      as unsent ensures Outlook treats it as a draft.*'
  - name: Set Recipient Flag
    text: '`FollowUpManager.setFlagForRecipients` attaches the flag exclusively to
      the recipient’s copy. *The flag is now visible only to the recipients – a classic
      **flag for recipients** scenario.*'
  - name: Load the Message
    text: '`MapiMessage` can read a saved `.msg` file, giving you full access to its
      MAPI properties.'
  - name: Mark as Completed and Save
    text: '`FollowUpManager.completeFlag` updates the flag status, after which you
      persist the changes. *The flag status changes to “Completed” and the updated
      file is saved.*'
  - name: Load and Clear Flag
    text: '`FollowUpManager.clearFlag` removes all flag‑related properties from the
      message. *The message is saved without any follow‑up flag.*'
  - name: Retrieve Options
    text: The returned `options` object gives you full visibility into the flag’s
      configuration. *The `options` object now contains start, due, and reminder dates,
      plus the flag subject – useful when you need to **read flag options** for reporting.*
  type: HowTo
- questions:
  - answer: It’s a pure‑Java API that lets you create, read, and manipulate email
      files (MSG, EML, etc.) without needing Outlook installed.
    question: What is Aspose.Email for Java?
  - answer: Visit the [Aspose website](https://releases.aspose.com/email/java/) to
      download a 30‑day trial.
    question: How do I obtain a free trial license?
  - answer: Outlook supports only one flag per message, but you can store additional
      task data in custom MAPI properties.
    question: Can I set multiple follow‑up flags on a single message?
  - answer: Confirm the `outputDir` path is valid and that the application has permission
      to write to that location.
    question: My message isn’t saved after setting a flag. What should I check?
  - answer: Loop through your message collection and call `FollowUpManager.clearFlag`
      on each `MapiMessage`.
    question: How can I remove flags from many messages at once?
  type: FAQPage
tags:
- outlook flag
- aspose.email
- java email automation
title: Establecer bandera de Outlook Java – Guía completa de programación de Aspose.Email
url: /es/java/calendar-appointments/aspose-email-java-outlook-follow-up-flags/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Configurar bandera de Outlook Java usando Aspose.Email para Java

## Introducción
Si necesitas **set outlook flag java** de forma programática, has llegado al lugar correcto. La bandera de seguimiento de Outlook convierte un correo electrónico regular en una tarea rastreada, y Aspose.Email for Java te permite gestionar esas banderas sin tener Outlook instalado. En este tutorial recorreremos la creación, lectura, finalización y, finalmente, la eliminación de banderas, además de cómo aplicar banderas para destinatarios específicos. Al final tendrás un fragmento de Java reutilizable que automatiza el seguimiento de tareas directamente desde tus servicios backend.

## Respuestas rápidas
- **¿Qué significa “set outlook flag java”?** Añadir una bandera con fechas de inicio, recordatorio y vencimiento a un elemento de Outlook mediante código Java.  
- **¿Qué biblioteca se requiere?** Aspose.Email for Java (v25.4 o superior).  
- **¿Necesito una licencia?** Sí – una prueba funciona para evaluación, pero se requiere una licencia comprada para producción.  
- **¿Puedo establecer banderas solo para los destinatarios?** Absolutamente – usa `FollowUpManager.setFlagForRecipients`.  
- **¿Es posible eliminar una bandera más tarde?** Sí – llama a `FollowUpManager.clearFlag`.

## ¿Qué es una bandera de seguimiento de Outlook?
La bandera de seguimiento de Outlook es un marcador de tarea incorporado que puede adjuntar una fecha de inicio, un recordatorio y una fecha de vencimiento a cualquier elemento de correo. Convierte un email en un elemento de acción rastreado, ayudando a ti y a tu equipo a mantenerse al tanto del trabajo pendiente.

## ¿Por qué usar Aspose.Email para Java?
Aspose.Email for Java soporta **más de 70 formatos de correo** (incluidos MSG, EML, MHTML y TNEF) y puede procesar **más de 100 000 mensajes por minuto** en un servidor típico de 8 núcleos, todo sin requerir Outlook en la máquina host. Esto lo hace ideal para automatización backend, generación de informes de cumplimiento e integración con herramientas de gestión de proyectos.

## Requisitos previos
- **Aspose.Email for Java** versión 25.4 o posterior.  
- **JDK 16+** instalado.  
- IDE compatible con Maven (IntelliJ IDEA, Eclipse, etc.).  
- Conocimientos básicos de Java y familiaridad con conceptos de correo electrónico.

## Configuración de Aspose.Email para Java
### Configuración de Maven
Agrega la siguiente dependencia a tu `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Obtención de licencia
Aspose.Email requiere una licencia para uso en producción:

- **Prueba gratuita** – evaluación de 30 días.  
- **Licencia temporal** – pruebas extendidas.  
- **Licencia completa** – suscripción perpetua.

Inicializa la licencia antes de cualquier operación de correo:

```java
License license = new License();
license.setLicense("path/to/Aspose.Total.Java.lic");
```

## Configurar bandera de Outlook Java (Función 1)
### Respuesta directa
Carga un `MailMessage`, conviértelo a un `MapiMessage`, configura `FollowUpOptions` y llama a `FollowUpManager.setOptions`. Esta secuencia crea un elemento de Outlook totalmente marcado en solo unas pocas líneas de código Java.

### Paso 1: Crear e inicializar el mensaje
`MailMessage` es la clase de alto nivel de Aspose.Email que representa un email. Después de construir el mensaje, lo conviertes a un `MapiMessage` para la manipulación de la bandera.

```java
MailMessage mailMsg = new MailMessage();
mailMsg.setSender(new MailAddress("AETest12@gmail.com"));
mailMsg.getTo().addMailAddress(new MailAddress("receiver@gmail.com"));
mailMsg.setBody("This message will test if follow up options can be added to a new mapi message.");
MapiMessage mapi = MapiMessage.fromMailMessage(mailMsg);
```
*Primero construimos un `MailMessage`, establecemos el remitente/destinatario, y luego lo convertimos a un `MapiMessage` para la manipulación de la bandera.*

### Paso 2: Definir fechas de seguimiento (Recordatorio de bandera de Outlook)
`FollowUpOptions` contiene las fechas de inicio, recordatorio y vencimiento. Usa la clase `Calendar` de Java para establecer marcas de tiempo precisas.

```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 14, 40, 0);
Date dtStartDate = calendar.getTime();
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
calendar.add(Calendar.DATE, 1);
Date dtDueDate = calendar.getTime();
```
*Aquí establecemos la fecha de inicio, el recordatorio (el **outlook flag reminder**), y las fechas de vencimiento usando la clase `Calendar`.*

### Paso 3: Aplicar opciones de seguimiento
El método `FollowUpManager.setOptions` adjunta la bandera al `MapiMessage`.  

```java
FollowUpOptions options = new FollowUpOptions("Follow Up", dtStartDate, dtDueDate, dtReminderDate);
FollowUpManager.setOptions(mapi, options);
```
*El objeto `FollowUpOptions` contiene todos los detalles de la bandera, que aplicamos con `FollowUpManager.setOptions`.*

### Paso 4: Guardar el mensaje
Guarda el mensaje marcado como un archivo `.msg` para que Outlook pueda mostrar la bandera.

```java
mapi.save(outputDir + "SetFollowUpflag_out.msg");
```
*El mensaje se guarda como un archivo `.msg` con la bandera adjunta.*

## ¿Cómo establecer bandera para destinatarios (Función 2)?
Usa `FollowUpManager.setFlagForRecipients` después de marcar el mensaje como borrador. Este método agrega la bandera de seguimiento solo a la copia del destinatario, dejando la vista del remitente sin cambios. Requiere establecer `MessageFlags.MSGFLAG_UNSENT` antes de aplicar la bandera. También puedes personalizar las fechas de inicio, recordatorio y vencimiento usando un objeto `FollowUpOptions` antes de llamar al método.

### Respuesta directa
Marca el mensaje como borrador usando `MessageFlags.MSGFLAG_UNSENT`, luego llama a `FollowUpManager.setFlagForRecipients`. Outlook mostrará la bandera solo a los destinatarios, no al remitente.

### Visión general
A veces necesitas que la bandera aparezca **solo para los destinatarios**. Este ejemplo marca primero el mensaje como borrador y luego agrega la bandera.

#### Paso 1: Marcar como borrador
`MessageFlags` es una enumeración MAPI que controla el estado del mensaje. Configurar `MSGFLAG_UNSENT` indica a Outlook que el elemento es un borrador.

```java
mapi.setMessageFlags(MapiMessageFlags.MSGFLAG_UNSENT);
```
*Marcar el mensaje como no enviado asegura que Outlook lo trate como un borrador.*

#### Paso 2: Establecer bandera para destinatario
`FollowUpManager.setFlagForRecipients` adjunta la bandera exclusivamente a la copia del destinatario.

```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
FollowUpManager.setFlagForRecipients(mapi, "Follow up", dtReminderDate);
```
*La bandera ahora es visible solo para los destinatarios – un escenario clásico de **flag for recipients**.*

## ¿Cómo marcar una bandera de seguimiento de Outlook como completada (Función 3)?
Carga el archivo .msg en un `MapiMessage`, luego llama a `FollowUpManager.completeFlag`. Esto actualiza el estado de la bandera a Completed y agrega una marca de verificación en Outlook. Después de completarla, guarda el mensaje para persistir el cambio. También puedes establecer la hora de finalización ajustando la propiedad `FlagCompleteTime` si es necesario para auditorías.

### Respuesta directa
Carga el archivo `.msg` existente en un `MapiMessage`, llama a `FollowUpManager.completeFlag` y guarda el archivo. El estado de la bandera cambia a “Completed” y aparece con una marca de verificación en Outlook.

### Paso 1: Cargar el mensaje
`MapiMessage` puede leer un archivo `.msg` guardado, dándote acceso completo a sus propiedades MAPI.

```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
```

### Paso 2: Marcar como completada y guardar
`FollowUpManager.completeFlag` actualiza el estado de la bandera, tras lo cual persistes los cambios.

```java
FollowUpManager.markAsCompleted(mapi);
mapi.save(outputDir + "MarkedCompleted_out.msg");
```
*El estado de la bandera cambia a “Completed” y el archivo actualizado se guarda.*

## ¿Cómo eliminar una bandera de seguimiento de Outlook (Función 4)?
Abre el archivo .msg con `MapiMessage`, invoca `FollowUpManager.clearFlag` y luego guarda el mensaje. Esto elimina todas las propiedades MAPI relacionadas con la bandera, por lo que Outlook ya no mostrará ningún indicador de seguimiento. Úsalo cuando una tarea se cancela o ya no es relevante. Asegúrate también de limpiar cualquier propiedad de recordatorio personalizada para evitar notificaciones residuales.

### Respuesta directa
Abre el archivo `.msg` con `MapiMessage`, invoca `FollowUpManager.clearFlag` y guarda el archivo. El mensaje ya no mostrará ningún indicador de seguimiento en Outlook.

### Paso 1: Cargar y eliminar la bandera
`FollowUpManager.clearFlag` elimina todas las propiedades relacionadas con la bandera del mensaje.

```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpManager.clearFlag(mapi);
mapi.save(outputDir + "FollowUpFlagRemoved_out.msg");
```
*El mensaje se guarda sin ninguna bandera de seguimiento.*

## ¿Cómo leer opciones de bandera (Función 5)?
Llama a `FollowUpManager.getOptions` sobre un `MapiMessage` cargado para obtener un objeto `FollowUpOptions`. Este objeto proporciona las fechas de inicio, vencimiento, recordatorio y el asunto de la bandera, permitiéndote mostrar o registrar los detalles de la misma. Es útil para informes y auditorías de cumplimiento.

### Respuesta directa
Usa `FollowUpManager.getOptions` sobre un `MapiMessage` cargado para recuperar un objeto `FollowUpOptions` que contiene fechas de inicio, vencimiento, recordatorio y el asunto de la bandera. Esto es útil para informes o auditorías de cumplimiento.

### Paso 1: Recuperar opciones
El objeto `options` devuelto te brinda visibilidad completa de la configuración de la bandera.

```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpOptions options = FollowUpManager.getOptions(mapi);
```
*El objeto `options` ahora contiene fechas de inicio, vencimiento y recordatorio, además del asunto de la bandera – útil cuando necesitas **read flag options** para informes.*

## Aplicaciones prácticas
- **Integración de gestión de tareas:** Sincronizar correos con bandera con Jira, Trello o Azure Boards.  
- **Recordatorios automáticos:** Generar correos de recordatorio diarios para seguimientos pendientes.  
- **Auditorías de cumplimiento:** Exportar datos de banderas para informes regulatorios, aprovechando la capacidad de leer opciones de bandera programáticamente.

## Consideraciones de rendimiento
- **Cálculos de fechas:** Calcular fechas una vez por lote en lugar de dentro de bucles.  
- **Gestión de recursos:** Cerrar cualquier flujo o manejador de archivos después de guardar los mensajes.  
- **Uso de memoria:** Procesar buzones grandes en fragmentos para evitar presión en el heap; Aspose.Email puede manejar buzones de cientos de páginas sin cargar todo el archivo en memoria.

## Problemas comunes y soluciones
| Problema | Causa | Solución |
|----------|-------|----------|
| La bandera no aparece en Outlook | El mensaje se guardó sin los `MessageFlags` adecuados | Asegúrate de que `setMessageFlags` esté configurado a `MSGFLAG_UNSENT` antes de aplicar banderas a los destinatarios. |
| Guardar lanza `AccessDeniedException` | Ruta de archivo incorrecta o permisos de escritura faltantes | Verifica que el directorio de salida exista y que la aplicación tenga derechos de escritura. |
| Las fechas están desplazadas un día | Desajuste de zona horaria | Usa `TimeZone.getTimeZone("GMT")` o tu zona local de forma consistente. |

## Preguntas frecuentes
**P: ¿Qué es Aspose.Email para Java?**  
R: Es una API pura de Java que permite crear, leer y manipular archivos de correo (MSG, EML, etc.) sin necesidad de Outlook instalado.

**P: ¿Cómo obtengo una licencia de prueba gratuita?**  
R: Visita el [Aspose website](https://releases.aspose.com/email/java/) para descargar una prueba de 30 días.

**P: ¿Puedo establecer múltiples banderas de seguimiento en un solo mensaje?**  
R: Outlook solo admite una bandera por mensaje, pero puedes almacenar datos de tarea adicionales en propiedades MAPI personalizadas.

**P: Mi mensaje no se guarda después de establecer una bandera. ¿Qué debo comprobar?**  
R: Confirma que la ruta `outputDir` sea válida y que la aplicación tenga permiso de escritura en esa ubicación.

**P: ¿Cómo puedo eliminar banderas de muchos mensajes a la vez?**  
R: Recorre tu colección de mensajes y llama a `FollowUpManager.clearFlag` en cada `MapiMessage`.

## Recursos
- [Documentación](https://reference.aspose.com/email/java/)
- [Descargar Aspose.Email para Java](https://releases.aspose.com/email/java/)
- [Prueba gratuita de Aspose.Email](https://purchase.aspose.com/purchase/free-trial/aspose-email-java)

**Última actualización:** 2026-07-27  
**Probado con:** Aspose.Email for Java 25.4 (JDK 16)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriales relacionados

- [Gestionar categorías de Outlook con Aspose.Email para Java - Guía completa](/email/java/calendar-appointments/manage-outlook-categories-aspose-email-java/)
- [Crear notas de Outlook en Java con Aspose.Email – Guía completa](/email/java/calendar-appointments/create-customize-outlook-notes-aspose-email-java/)
- [Crear tareas en Microsoft Exchange usando Aspose.Email para Java: Guía completa](/email/java/exchange-server-integration/create-tasks-exchange-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}