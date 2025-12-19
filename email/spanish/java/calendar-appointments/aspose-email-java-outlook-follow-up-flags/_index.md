---
date: '2025-12-19'
description: Aprenda cómo establecer banderas de seguimiento en Outlook usando Aspose.Email
  para Java, incluido cómo establecer la bandera de seguimiento de Outlook y cómo
  eliminarla de manera eficiente.
keywords:
- Manage Outlook follow-up flags
- Set follow-up flags in Outlook with Aspose.Email for Java
- Integrate email task management with Aspose.Email
title: Cómo establecer banderas de seguimiento en Outlook usando Aspose.Email para
  Java
url: /es/java/calendar-appointments/aspose-email-java-outlook-follow-up-flags/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cómo establecer banderas de seguimiento en Outlook usando Aspose.Email para Java

## Introducción
Si alguna vez has tenido dificultades para hacer seguimiento de correos electrónicos importantes, sabes lo valiosas que pueden ser las banderas de seguimiento de Outlook. En esta guía mostraremos **cómo establecer banderas de seguimiento** de forma programática con Aspose.Email para Java, y también cubriremos cómo **establecer la bandera de seguimiento de Outlook** para los destinatarios, así como cómo **eliminar la bandera de seguimiento de Outlook** cuando una tarea está terminada. Al final, podrás automatizar el seguimiento de tareas, recordatorios y auditorías directamente desde tu código Java.

**Lo que aprenderás**
- Crear y aplicar una bandera de seguimiento en un mensaje de Outlook.  
- Establecer banderas de seguimiento para destinatarios específicos.  
- Marcar una bandera como completada y luego eliminarla.  
- Leer opciones de bandera para informes o cumplimiento.  

Preparemos el entorno antes de sumergirnos en el código.

## Respuestas rápidas
- **¿Qué significa “cómo establecer seguimiento”?** Añadir una bandera con fechas de inicio, recordatorio y vencimiento a un elemento de Outlook.  
- **¿Qué biblioteca se requiere?** Aspose.Email para Java (v25.4 o superior).  
- **¿Necesito una licencia?** Sí, se requiere una licencia de prueba o comprada para la funcionalidad completa.  
- **¿Puedo establecer banderas solo para los destinatarios?** Absolutamente – usa `FollowUpManager.setFlagForRecipients`.  
- **¿Es posible eliminar una bandera después?** Sí, llama a `FollowUpManager.clearFlag`.

## ¿Qué es una bandera de seguimiento?
Una bandera de seguimiento es una función de Outlook que marca un correo electrónico como una tarea, opcionalmente adjuntando fechas de inicio, recordatorio y vencimiento. Ayuda a ti y a tu equipo a mantenerse al tanto de acciones pendientes.

## ¿Por qué usar Aspose.Email para Java?
Aspose.Email ofrece una API pura de Java que funciona sin necesidad de Outlook instalado, permitiéndote manipular archivos .msg, establecer banderas y gestionar tareas en cualquier plataforma—perfecto para servicios backend, flujos de trabajo automatizados o integración con herramientas de gestión de proyectos.

## Requisitos previos
- **Aspose.Email para Java** versión 25.4 o posterior.  
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

Inicializa la licencia antes de cualquier operación de correo electrónico:

```java
License license = new License();
license.setLicense("path/to/Aspose.Total.Java.lic");
```

## Guía de implementación

### Cómo establecer banderas de seguimiento (Función 1)
#### Visión general
Esta sección te guía paso a paso para crear un mensaje de Outlook, definir fechas de inicio/recordatorio/vencimiento y aplicar una bandera de seguimiento.

#### Paso 1: Crear e inicializar el mensaje
```java
MailMessage mailMsg = new MailMessage();
mailMsg.setSender(new MailAddress("AETest12@gmail.com"));
mailMsg.getTo().addMailAddress(new MailAddress("receiver@gmail.com"));
mailMsg.setBody("This message will test if follow up options can be added to a new mapi message.");
MapiMessage mapi = MapiMessage.fromMailMessage(mailMsg);
```
*Primero construimos un `MailMessage`, establecemos remitente/destinatario y luego lo convertimos a un `MapiMessage` para manipular la bandera.*

#### Paso 2: Definir fechas de seguimiento
```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 14, 40, 0);
Date dtStartDate = calendar.getTime();
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
calendar.add(Calendar.DATE, 1);
Date dtDueDate = calendar.getTime();
```
*Aquí establecemos las fechas de inicio, recordatorio y vencimiento usando la clase `Calendar`.*

#### Paso 3: Aplicar opciones de seguimiento
```java
FollowUpOptions options = new FollowUpOptions("Follow Up", dtStartDate, dtDueDate, dtReminderDate);
FollowUpManager.setOptions(mapi, options);
```
*El objeto `FollowUpOptions` contiene todos los detalles de la bandera, que aplicamos con `FollowUpManager.setOptions`.*

#### Paso 4: Guardar el mensaje
```java
mapi.save(outputDir + "SetFollowUpflag_out.msg");
```
*El mensaje se guarda como un archivo `.msg` con la bandera adjunta.*

### Cómo establecer la bandera de seguimiento de Outlook para destinatarios (Función 2)
#### Visión general
A veces necesitas marcar un mensaje solo para los destinatarios. Este ejemplo marca el mensaje como borrador primero, luego agrega la bandera.

#### Paso 1: Marcar como borrador
```java
mapi.setMessageFlags(MapiMessageFlags.MSGFLAG_UNSENT);
```
*Marcar el mensaje como no enviado asegura que Outlook lo trate como un borrador.*

#### Paso 2: Establecer bandera para destinatario
```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
FollowUpManager.setFlagForRecipients(mapi, "Follow up", dtReminderDate);
```
*La bandera ahora es visible solo para los destinatarios.*

### Cómo marcar una bandera de seguimiento de Outlook como completada (Función 3)
#### Visión general
Cuando una tarea está terminada, puedes marcar programáticamente la bandera como completada.

#### Paso 1: Cargar el mensaje
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
```

#### Paso 2: Marcar como completada y guardar
```java
FollowUpManager.markAsCompleted(mapi);
mapi.save(outputDir + "MarkedCompleted_out.msg");
```
*El estado de la bandera cambia a “Completed” y el archivo actualizado se guarda.*

### Cómo eliminar la bandera de seguimiento de Outlook (Función 4)
#### Visión general
Si una bandera ya no es necesaria, puedes eliminarla por completo.

#### Paso 1: Cargar y limpiar la bandera
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpManager.clearFlag(mapi);
mapi.save(outputDir + "FollowUpFlagRemoved_out.msg");
```
*El mensaje se guarda sin ninguna bandera de seguimiento.*

### Cómo leer opciones de bandera de seguimiento (Función 5)
#### Visión general
Para auditorías o informes, puede que necesites leer la configuración de la bandera existente.

#### Paso 1: Recuperar opciones
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpOptions options = FollowUpManager.getOptions(mapi);
```
*El objeto `options` ahora contiene las fechas de inicio, vencimiento y recordatorio, además del asunto de la bandera.*

## Aplicaciones prácticas
- **Integración de gestión de tareas:** Sincroniza correos electrónicos con banderas con Jira, Trello o Azure Boards.  
- **Recordatorios automáticos:** Genera correos de recordatorio diarios para seguimientos pendientes.  
- **Auditorías de cumplimiento:** Exporta datos de banderas para informes regulatorios.

## Consideraciones de rendimiento
- **Cálculos de fechas:** Calcula las fechas una sola vez por lote en lugar de dentro de bucles.  
- **Gestión de recursos:** Cierra cualquier flujo o manejador de archivos después de guardar los mensajes.  
- **Uso de memoria:** Procesa buzones grandes en fragmentos para evitar presión en el heap.

## Problemas comunes y soluciones
| Problema | Causa | Solución |
|----------|-------|----------|
| La bandera no aparece en Outlook | Mensaje guardado sin `MessageFlags` adecuados | Asegúrate de que `setMessageFlags` esté configurado a `MSGFLAG_UNSENT` antes de aplicar banderas para destinatarios. |
| Guardado lanza `AccessDeniedException` | Ruta de archivo incorrecta o permisos de escritura insuficientes | Verifica que el directorio de salida exista y que la aplicación tenga derechos de escritura. |
| Las fechas están desplazadas un día | Desajuste de zona horaria | Usa `TimeZone.getTimeZone("GMT")` o tu zona local de forma consistente. |

## Preguntas frecuentes
**P: ¿Qué es Aspose.Email para Java?**  
R: Es una API pura de Java que permite crear, leer y manipular archivos de correo (MSG, EML, etc.) sin necesidad de Outlook instalado.

**P: ¿Cómo obtengo una licencia de prueba gratuita?**  
R: Visita el [sitio web de Aspose](https://releases.aspose.com/email/java/) para descargar una prueba de 30 días.

**P: ¿Puedo establecer múltiples banderas de seguimiento en un solo mensaje?**  
R: Outlook solo admite una bandera por mensaje, pero puedes almacenar datos de tarea adicionales en propiedades MAPI personalizadas.

**P: Mi mensaje no se guarda después de establecer una bandera. ¿Qué debo comprobar?**  
R: Confirma que la ruta `outputDir` sea válida y que la aplicación tenga permiso para escribir en esa ubicación.

**P: ¿Cómo puedo eliminar banderas de muchos mensajes a la vez?**  
R: Recorre tu colección de mensajes y llama a `FollowUpManager.clearFlag` en cada `MapiMessage`.

## Recursos
- [Documentación](https://reference.aspose.com/email/java/)
- [Descargar Aspose.Email para Java](https://releases.aspose.com/email/java/)
- [Prueba gratuita de Aspose.Email](https://purchase.aspose.com/purchase/free-trial/aspose-email-java)

---

**Última actualización:** 2025-12-19  
**Probado con:** Aspose.Email para Java 25.4 (jdk16)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}