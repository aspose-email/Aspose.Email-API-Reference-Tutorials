---
date: '2026-09-17'
description: Cómo crear una invitación de calendario con Aspose.Email for Java le
  permite compartir calendarios, establecer permisos de delegado y enviar correos
  de compartición de forma programática.
keywords:
- how to create calendar invitation
- calendar sharing invitation
- Aspose.Email Java
- delegate calendar permissions
lastmod: '2026-09-17'
og_description: Cómo crear una invitación de calendario con Aspose.Email for Java
  le permite compartir calendarios de forma programática, establecer permisos de delegado
  y enviar correos de compartición a través de Exchange Web Services, mejorando la
  colaboración del equipo.
og_image_alt: Guide showing how to create calendar invitation with Aspose.Email for
  Java
og_title: Cómo crear una invitación de calendario con Aspose.Email for Java
schemas:
- author: Aspose
  dateModified: '2026-09-17'
  description: How to create calendar invitation with Aspose.Email for Java lets you
    share calendars, set delegate permissions, and send sharing emails programmatically.
  headline: How to create calendar invitation with Aspose.Email for Java
  type: TechArticle
- description: How to create calendar invitation with Aspose.Email for Java lets you
    share calendars, set delegate permissions, and send sharing emails programmatically.
  name: How to create calendar invitation with Aspose.Email for Java
  steps:
  - name: Install JDK if you haven't already. You can download it from [Oracle's official
      site](https://www.oracle.com/java/technologies/javase-downloads.html).
    text: Install JDK if you haven't already. You can download it from [Oracle's official
      site](https://www.oracle.com/java/technologies/javase-downloads.html).
  - name: Ensure Maven is installed and configured on your machine.
    text: Ensure Maven is installed and configured on your machine.
  - name: Choose an IDE such as IntelliJ IDEA or Eclipse for easier development.
    text: Choose an IDE such as IntelliJ IDEA or Eclipse for easier development.
  - name: '**Corporate meetings** – Let team members view meeting schedules without
      giving full mailbox rights.'
    text: '**Corporate meetings** – Let team members view meeting schedules without
      giving full mailbox rights.'
  - name: '**Project management** – Project leads can monitor timelines while developers
      retain control of their own calendars.'
    text: '**Project management** – Project leads can monitor timelines while developers
      retain control of their own calendars.'
  - name: '**Event planning** – Vendors receive a **calendar sharing email** to coordinate
      logistics without exposing internal details.'
    text: '**Event planning** – Vendors receive a **calendar sharing email** to coordinate
      logistics without exposing internal details.'
  type: HowTo
- questions:
  - answer: It’s a comprehensive library for handling emails, calendars, and contacts
      in Java applications, supporting Outlook, Exchange, and other protocols.
    question: What is Aspose.Email for Java used for?
  - answer: Install JDK 16+, Maven, add the Aspose.Email dependency to `pom.xml`,
      and obtain a license (trial or full).
    question: How do I set up my environment for using Aspose.Email?
  - answer: Yes, but verify the service URL and permission levels match your server’s
      configuration.
    question: Can I use this code with other versions of Exchange Online?
  - answer: Check network connectivity, credentials, and that the delegate user has
      valid permissions. Review exception details for clues.
    question: What should I do if the calendar sharing invitation fails to send?
  - answer: Absolutely – replace `ExchangeDelegateFolderPermissionLevel.Reviewer`
      with `Editor`, `Author`, or `Owner` as needed.
    question: Is it possible to add additional permissions like editing or full access?
  type: FAQPage
tags:
- calendar sharing
- Aspose.Email
- Java email API
- delegate permissions
- EWS client
title: Cómo crear una invitación de calendario con Aspose.Email for Java
url: /es/java/calendar-appointments/create-send-calendar-invitations-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Administrar el uso compartido de calendarios: guía de Aspose.Email para Java

## Introducción a la gestión del uso compartido de calendarios
Gestionar invitaciones de uso compartido de calendarios puede ser una tarea compleja, especialmente al tratar con múltiples usuarios en diferentes plataformas. En este tutorial usted **creará una invitación de uso compartido de calendario** con Aspose.Email para Java, cubriendo todo desde la creación de acceso delegado hasta el envío de correos electrónicos de uso compartido de calendario. Al final, podrá establecer permisos de delegado, **configurar permisos de calendario**, y optimizar la colaboración en su organización.

**Qué aprenderá**
- Cómo inicializar el cliente EWS con Aspose.Email para Java  
- Crear un usuario delegado y **establecer permisos de delegado**  
- **Crear acceso delegado** y configurar permisos de calendario  
- Enviar un **correo electrónico de uso compartido de calendario** (invitación) programáticamente  
- Escenarios del mundo real donde estas funciones añaden valor  

Antes de comenzar, asegúrese de que tiene todo lo necesario.

## Respuestas rápidas
- **¿Cuál es el propósito principal de esta guía?** Mostrar cómo **crear una invitación de uso compartido de calendario** usando Aspose.Email para Java.  
- **¿Qué versión de la biblioteca se requiere?** Aspose.Email para Java 25.4 (clasificador JDK 16).  
- **¿Necesito una licencia?** Sí – se requiere una licencia de prueba o completa para uso en producción.  
- **¿Qué entorno se necesita?** JDK 16+, Maven y una cuenta de Exchange Online.  
- **¿Puedo usar esto con otros servidores Exchange?** Sí, pero puede que necesite ajustar la URL del servicio y los niveles de permiso.

## ¿Qué es una invitación de uso compartido de calendario?
Una invitación de uso compartido de calendario es un mensaje de correo electrónico que otorga a otro usuario acceso para ver (o editar) su calendario sin conceder derechos completos de buzón. Permite a los miembros del equipo ver su agenda, proponer reuniones o gestionar eventos mientras mantiene su buzón seguro.

## ¿Por qué configurar permisos de calendario?
Configurar permisos de calendario le permite controlar exactamente lo que un delegado puede hacer—si solo puede leer eventos, proponer nuevos o editar entradas existentes. Los ajustes de permiso adecuados protegen la información sensible mientras habilitan una colaboración eficaz. Por ejemplo, conceder acceso solo de lectura evita cambios accidentales, mientras que los derechos de edición permiten al delegado programar o modificar reuniones en su nombre.

## Requisitos previos
- **Java Development Kit (JDK):** Versión 16 o posterior.  
- **Maven:** Para la gestión de dependencias y la compilación del proyecto.  
- **Biblioteca Aspose.Email para Java:** Versión 25.4 con soporte para JDK 16.  

### Requisitos de configuración del entorno
1. Instale JDK si aún no lo ha hecho. Puede descargarlo desde [Oracle's official site](https://www.oracle.com/java/technologies/javase-downloads.html).  
2. Asegúrese de que Maven esté instalado y configurado en su máquina.  
3. Elija un IDE como IntelliJ IDEA o Eclipse para facilitar el desarrollo.

### Requisitos de conocimientos
- Habilidades básicas de programación en Java  
- Familiaridad con dependencias de Maven  
- Opcional: Experiencia con Exchange Web Services (EWS)

## Configuración de Aspose.Email para Java
### Configuración de Maven
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
Aspose.Email para Java requiere una licencia para la funcionalidad completa. Puede:
- **Prueba gratuita:** Descargue desde [Aspose's release page](https://releases.aspose.com/email/java/).  
- **Licencia temporal:** Solicite una clave temporal en el sitio web de Aspose.  
- **Compra:** Obtenga una licencia permanente para implementaciones en producción.

### Inicialización y configuración básica
Una vez que Maven resuelva la dependencia, inicialice el cliente EWS:

`ExchangeService` es la clase principal utilizada para comunicarse con Exchange Web Services.  

```java
IEWSClient client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser", "pwd", "domain");
```

## Cómo crear una invitación de uso compartido de calendario
En este tutorial creará una invitación de uso compartido de calendario conectándose primero a Exchange mediante el cliente `ExchangeService`, luego definiendo un delegado con el nivel de permiso deseado y, finalmente, componiendo un `MailMessage` que incluya la solicitud de uso compartido. Los siguientes pasos demuestran este flujo de trabajo en Java.

A continuación cubrimos dos funciones principales: crear y enviar una invitación de uso compartido de calendario, y **establecer permisos de delegado** para el acceso al calendario.

### Función 1: crear y enviar una invitación de uso compartido de calendario
#### Visión general
Esta función le guía a través de la inicialización del cliente, **crear acceso delegado**, y el envío del correo de invitación.

#### Implementación paso a paso
##### 1️⃣ Inicializar cliente EWS
`ExchangeService` representa la conexión a un servidor Exchange y se usa para enviar y recibir mensajes.  

```java
IEWSClient client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser", "pwd", "domain");
```  
Esto conecta su aplicación Java a Exchange Online.

##### 2️⃣ Crear usuario delegado
`DelegateUser` define la dirección de correo electrónico del delegado y el nivel de permiso que se otorgará.  

```java
ExchangeDelegateUser delegateUser = new ExchangeDelegateUser("sharingfrom@domain.com", ExchangeDelegateFolderPermissionLevel.NotSpecified);
delegateUser.getFolderPermissions().setCalendarFolderPermissionLevel(ExchangeDelegateFolderPermissionLevel.Reviewer);
client.delegateAccess(delegateUser, "sharingfrom@domain.com");
```  
Aquí **creamos acceso delegado** y asignamos el nivel `Reviewer`, que permite al delegado ver los elementos del calendario.

##### 3️⃣ Enviar invitación de uso compartido de calendario
`MailMessage` construye el correo electrónico que lleva la invitación de uso compartido de calendario.  

```java
MapiMessage mapiMessage = client.createCalendarSharingInvitationMessage("sharingfrom@domain.com");

MailConversionOptions options = new MailConversionOptions();
options.setConvertAsTnef(true);

MailMessage mail = mapiMessage.toMailMessage(options);
client.send(mail);
```  
El código crea un **correo electrónico de uso compartido de calendario** (invitación) y lo envía a través del cliente EWS.

### Función 2: permiso de acceso al calendario del delegado
#### Visión general
Esta sección muestra cómo **configurar permisos de calendario** y asegurar que el delegado tenga los derechos correctos.

#### Pasos de implementación
##### 1️⃣ Inicializar cliente EWS (reutilizar)
`ExchangeService` puede reutilizarse para múltiples operaciones después de la configuración inicial.  

```java
IEWSClient client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser", "pwd", "domain");
```  

##### 2️⃣ Crear y establecer permisos de delegado
`ExchangeDelegateFolderPermissionLevel` enumera los niveles de acceso que un delegado puede tener a una carpeta de calendario.  

```java
ExchangeDelegateUser delegateUser = new ExchangeDelegateUser("sharingfrom@domain.com", ExchangeDelegateFolderPermissionLevel.NotSpecified);
delegateUser.getFolderPermissions().setCalendarFolderPermissionLevel(ExchangeDelegateFolderPermissionLevel.Reviewer);

client.delegateAccess(delegateUser, "sharingfrom@domain.com");
```  
Este fragmento **establece permisos de delegado** para que el usuario pueda ver entradas del calendario sin acceso completo al buzón.

## Cómo configurar permisos de calendario para delegados
Cuando un delegado necesita más que acceso solo de lectura, puede ajustar `ExchangeDelegateFolderPermissionLevel` para conceder derechos de edición, autor o propietario. Elija el nivel mínimo que satisfaga la necesidad empresarial para mantener la seguridad mientras brinda la funcionalidad necesaria. Por ejemplo, asignar el nivel Editor permite al delegado crear, modificar y eliminar eventos, mientras que el nivel Reviewer solo permite la visualización.

- `Reviewer` – acceso solo de lectura.  
- `Editor` – acceso de lectura/escritura.  
- `Author` – crear y leer, pero no puede eliminar.  
- `Owner` – control total, incluyendo cambios de permisos.  

**Consejo profesional:** Use el nivel de menor privilegio que satisfaga el requisito empresarial para mantener seguros sus datos de calendario.

## Aplicaciones prácticas
Escenarios del mundo real donde **gestionar el uso compartido de calendarios** destaca:
1. **Reuniones corporativas** – Permita que los miembros del equipo vean los horarios de reuniones sin otorgar derechos completos al buzón.  
2. **Gestión de proyectos** – Los líderes de proyecto pueden monitorear cronogramas mientras los desarrolladores mantienen el control de sus propios calendarios.  
3. **Planificación de eventos** – Los proveedores reciben un **correo electrónico de uso compartido de calendario** para coordinar la logística sin exponer detalles internos.

## Consideraciones de rendimiento
- **Gestión de memoria:** Deseche rápidamente los objetos `MailMessage` grandes en aplicaciones de alto volumen.  
- **Manejo de excepciones:** Envuelva las llamadas de red en bloques try‑catch para manejar fallos de conectividad de forma elegante.  
- **Actualizaciones de la biblioteca:** Aspose.Email para Java soporta más de 50 protocolos y puede procesar calendarios con hasta 10,000 elementos sin cargar todo el archivo en memoria, por lo que mantenga la biblioteca actualizada para beneficiarse de mejoras de rendimiento y correcciones de errores.

## Problemas comunes y soluciones
| Problema | Causa probable | Solución |
|----------|----------------|----------|
| Invitación no recibida | Filtros de spam o dirección de correo incorrecta | Verifique la dirección del destinatario y añada el dominio de envío a la lista de remitentes seguros |
| Permiso no aplicado | Uso del `ExchangeDelegateFolderPermissionLevel` incorrecto | Verifique que el nivel de permiso coincida con el acceso requerido |
| Excepción en tiempo de ejecución en `createCalendarSharingInvitationMessage` | Licencia faltante o biblioteca desactualizada | Asegúrese de que se cargue una licencia válida y esté usando la última versión de Aspose.Email |

## Preguntas frecuentes
**P: ¿Para qué se usa Aspose.Email para Java?**  
R: Es una biblioteca integral para manejar correos electrónicos, calendarios y contactos en aplicaciones Java, soportando Outlook, Exchange y otros protocolos.

**P: ¿Cómo configuro mi entorno para usar Aspose.Email?**  
R: Instale JDK 16+, Maven, añada la dependencia Aspose.Email a `pom.xml` y obtenga una licencia (prueba o completa).

**P: ¿Puedo usar este código con otras versiones de Exchange Online?**  
R: Sí, pero verifique que la URL del servicio y los niveles de permiso coincidan con la configuración de su servidor.

**P: ¿Qué debo hacer si la invitación de uso compartido de calendario no se envía?**  
R: Verifique la conectividad de red, credenciales y que el usuario delegado tenga permisos válidos. Revise los detalles de la excepción para obtener pistas.

**P: ¿Es posible añadir permisos adicionales como edición o acceso total?**  
R: Por supuesto – reemplace `ExchangeDelegateFolderPermissionLevel.Reviewer` por `Editor`, `Author` o `Owner` según sea necesario.

## Conclusión
Ahora dispone de una solución completa de extremo a extremo para **crear una invitación de uso compartido de calendario** con Aspose.Email para Java. Al inicializar el cliente EWS, **crear acceso delegado**, **establecer permisos de delegado**, y enviar un **correo electrónico de uso compartido de calendario**, puede automatizar la colaboración en toda su organización.

**Próximos pasos**
- Experimente con otros niveles de permiso (Editor, Owner).  
- Integre esta lógica en sus sistemas de programación o recursos humanos existentes.  
- Explore características adicionales de Aspose.Email como eventos recurrentes o solicitudes de reunión.

---

**Last Updated:** 2026-09-17  
**Tested With:** Aspose.Email for Java 25.4 (JDK 16 classifier)  
**Author:** Aspose

## Tutoriales relacionados

- [Cómo crear elemento de calendario Java usando Aspose.Email](/email/java/calendar-appointments/create-save-calendar-items-aspose-email-java/)
- [Filtrar citas de Exchange por fecha con Aspose Email Java](/email/java/calendar-appointments/aspose-email-java-filter-exchange-appointments-by-date/)
- [Crear calendario Exchange Java con Aspose.Email – Guía completa](/email/java/calendar-appointments/mastering-exchange-calendar-management-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}