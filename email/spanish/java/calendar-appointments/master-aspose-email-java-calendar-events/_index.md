---
date: '2026-02-24'
description: Aprenda cómo exportar el calendario a PST con Aspose.Email para Java,
  incluyendo cómo agregar asistentes, establecer fechas de inicio y fin, y gestionar
  citas de manera eficiente.
keywords:
- Aspose.Email Java Calendar Events
- Create Calendar Events in Java
- Manage Calendar Appointments with Java
- export calendar to pst
title: Exportar calendario a PST con Aspose.Email para Java
url: /es/java/calendar-appointments/master-aspose-email-java-calendar-events/
weight: 1
---

Now produce final content.

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Exportar calendario a PST con Aspose.Email para Java

Si estás desarrollando una aplicación Java que necesita compartir datos de programación con Outlook, a menudo tendrás que **exportar calendario a PST**. En este tutorial repasaremos todo lo que necesitas—desde crear una cita simple hasta añadir asistentes y, finalmente, escribir los eventos en un archivo PST, todo con Aspose.Email para Java.

## Respuestas rápidas
- **¿Cuál es el objetivo principal?** Exportar eventos de calendario a un archivo PST.  
- **¿Qué biblioteca se requiere?** Aspose.Email para Java (v25.4+).  
- **¿Necesito una licencia?** Sí, una licencia válida de Aspose.Email elimina los límites de evaluación.  
- **¿Puedo añadir asistentes?** Por supuesto – usa `MapiRecipientCollection`.  
- **¿Qué versión de Java es compatible?** JDK 16 o superior.

## ¿Qué es **export calendar to pst**?
Exportar un calendario a PST significa convertir objetos `MapiCalendar` en memoria en una Microsoft Outlook Personal Storage Table (PST). El archivo resultante puede abrirse directamente en Outlook, compartirse con colegas o importarse a cualquier sistema que entienda el formato PST.

## ¿Por qué usar Aspose.Email para Java para exportar calendario a PST?
- **Compatibilidad total con MAPI** – crea, modifica y guarda citas sin necesidad de Outlook instalado.  
- **Multiplataforma** – funciona en Windows, Linux y macOS.  
- **API rica** – gestiona asistentes, recurrencias, recordatorios y más.  
- **Optimizado para rendimiento** – maneja grandes volúmenes de eventos con un bajo consumo de memoria.

## Requisitos previos
- **Bibliotecas y dependencias**: Aspose.Email para Java versión 25.4 o posterior.  
- **Entorno**: JDK 16 o superior, Maven para la gestión de dependencias.  
- **Conocimientos**: Programación básica en Java y familiaridad con Maven.

## Cómo configurar Aspose.Email para Java
Añade la dependencia de Aspose.Email a tu `pom.xml`:

```xml
<dependency>
  <groupId>com.aspose</groupId>
  <artifactId>aspose-email</artifactId>
  <version>25.4</version>
  <classifier>jdk16</classifier>
</dependency>
```

### Obtención de licencia
Desbloquea la funcionalidad completa de Aspose.Email sin limitaciones de evaluación adquiriendo una licencia:

1. **Prueba gratuita**: Visita la [página de descarga de Aspose](https://releases.aspose.com/email/java/) para obtener una licencia temporal.  
2. **Licencia temporal**: Solicítala a través de la [página de compra](https://purchase.aspose.com/temporary-license/).  
3. **Licencia de compra**: Considera adquirirla en el [portal de compras de Aspose](https://purchase.aspose.com/buy) para uso a largo plazo.

Una vez que tengas tu licencia, inicialízala en tu aplicación para habilitar todas las funciones.

## Cómo **crear cita** (Create Calendar Event Java)

### Paso 1: Definir fechas de inicio y fin (java calendar start date / java calendar end date)
El siguiente método muestra cómo establecer las fechas de inicio y fin para una cita y devolver un objeto `MapiCalendar`:

```java
import com.aspose.email.MapiCalendar;
import java.util.Calendar;
import java.util.Date;

public MapiCalendar createAppointment() {
    Calendar cal = Calendar.getInstance();
    
    // Setting the start date
    cal.set(Calendar.YEAR, 2023);
    cal.set(Calendar.MONTH, Calendar.OCTOBER);
    cal.set(Calendar.DAY_OF_MONTH, 1);
    Date startDate = cal.getTime();
    
    // Setting the end date
    cal.set(Calendar.HOUR_OF_DAY, 10);
    Date endDate = cal.getTime();
    
    return new MapiCalendar("Conference Room", "Important Meeting",
        "Discuss project milestones and updates.", startDate, endDate);
}
```

*Explicación*: Este fragmento crea un `MapiCalendar` con una ubicación específica, asunto, descripción y la **fecha de inicio del calendario java** / **fecha de fin del calendario java** que definiste.

## Cómo **añadir asistentes** (java add meeting attendees)

### Paso 2: Construir la lista de asistentes
Utiliza `MapiRecipientCollection` para especificar a quién debe enviarse la invitación a la reunión:

```java
import com.aspose.email.MapiCalendar;
import com.aspose.email.MapiRecipientCollection;
import com.aspose.email.MapiRecipientType;
import java.util.Date;

public MapiCalendar createMeetingWithAttendees(Date startDate, Date endDate) {
    MapiRecipientCollection attendees = new MapiRecipientCollection();
    
    // Adding primary recipients
    attendees.add("attendee1@example.com", "John Doe", MapiRecipientType.MAPI_TO);
    attendees.add("attendee2@example.com", "Jane Smith", MapiRecipientType.MAPI_TO);
    
    return new MapiCalendar(
        "Main Office Boardroom",
        "Team Meeting",
        "Discuss quarterly goals.",
        startDate,
        endDate,
        "organizer@example.com",
        attendees
    );
}
```

*Explicación*: Este código crea una reunión, establece el organizador y adjunta la lista de **asistentes de la reunión java** para que todos reciban una invitación adecuada.

## Cómo **exportar calendario a pst** (Create PST with calendar events)

### Paso 3: Crear un archivo PST y añadir los eventos
El método a continuación demuestra cómo crear un archivo PST Unicode y almacenar tanto la cita simple como la reunión con asistentes:

```java
import com.aspose.email.FileFormatVersion;
import com.aspose.email.FolderInfo;
import com.aspose.email.PersonalStorage;
import com.aspose.email.StandardIpmFolder;

public void createPSTWithCalendarEvents() {
    String pstFilePath = "/path/to/output/MapiCalendarToPST_out.pst";
    
    PersonalStorage pst = PersonalStorage.create(pstFilePath, FileFormatVersion.Unicode);
    FolderInfo calendarFolder = pst.createPredefinedFolder("Calendar", StandardIpmFolder.Appointments);

    MapiCalendar appointment = createAppointment();
    calendarFolder.addMapiMessageItem(appointment);
    
    Date startDate = new Date(); // Use actual dates from your event
    Date endDate = new Date();
    MapiCalendar meeting = createMeetingWithAttendees(startDate, endDate);
    calendarFolder.addMapiMessageItem(meeting);
}
```

*Explicación*: Este fragmento **exporta calendario a PST** creando un contenedor PST, añadiendo una carpeta predefinida "Calendar" e insertando los objetos `MapiCalendar` previamente construidos.

## Aplicaciones prácticas
1. **Programación empresarial** – Automatiza la creación y distribución interna de reuniones.  
2. **Gestión de eventos** – Rastrea conferencias, talleres y listas de participantes.  
3. **Integración CRM** – Sincroniza citas con herramientas de gestión de relaciones con clientes.  
4. **Planificación de proyectos** – Almacena hitos del proyecto como elementos de calendario.  
5. **Colaboración de equipos remotos** – Genera archivos PST para compartir sin conexión.

## Consideraciones de rendimiento
- **Descarta objetos** que ya no necesites para liberar memoria.  
- **Elige colecciones eficientes** para listas grandes de asistentes.  
- **Cachea eventos consultados frecuentemente** si accedes al PST de forma repetida.

## Problemas comunes y soluciones
| Problema | Solución |
|----------|----------|
| **No se crea el archivo PST** | Verifica los permisos de escritura en el directorio de destino y asegura que la ruta de la carpeta exista. |
| **Los asistentes no reciben invitaciones** | Confirma que cada `MapiRecipient` use `MapiRecipientType.MAPI_TO` y que el correo del organizador sea válido. |
| **Desfase de fechas** | Usa `Calendar` de forma consistente para las fechas de inicio/fin; evita mezclar `java.util.Date` con otras bibliotecas de fechas sin conversión. |

## Preguntas frecuentes

**P: ¿Cómo empiezo con Aspose.Email para Java?**  
R: Añade la dependencia Maven mostrada arriba, obtén una licencia y sigue los pasos de esta guía para crear y exportar eventos de calendario.

**P: ¿Puedo personalizar el nombre y la ubicación del archivo PST?**  
R: Sí, cambia la variable `pstFilePath` en `createPSTWithCalendarEvents()` a cualquier ruta válida en tu sistema.

**P: ¿Es posible añadir patrones de recurrencia a las citas?**  
R: Por supuesto – `MapiCalendar` expone propiedades de recurrencia como `RecurrencePattern` que puedes configurar antes de guardar.

**P: ¿Aspose.Email admite otros formatos de calendario además de PST?**  
R: Sí, puedes exportar a iCalendar (`.ics`) y a otros formatos usando los métodos API correspondientes.

**P: ¿Cuál es el tamaño máximo de un archivo PST que puedo crear?**  
R: Con el formato Unicode (`FileFormatVersion.Unicode`), los archivos PST pueden crecer hasta 2 TB, limitados solo por el espacio disponible en disco.

---

**Última actualización:** 2026-02-24  
**Probado con:** Aspose.Email para Java 25.4 (clasificador jdk16)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}