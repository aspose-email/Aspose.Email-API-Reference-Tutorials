---
date: '2026-03-20'
description: Aprenda cómo crear una invitación para compartir el calendario, configurar
  los permisos del calendario y establecer el acceso de delegado usando Aspose.Email
  para Java.
keywords:
- Aspose.Email for Java
- create calendar invitations
- send calendar invitations
title: Crear invitación para compartir calendario con Aspose.Email para Java
url: /es/java/calendar-appointments/create-send-calendar-invitations-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Gestionar el uso compartido de calendarios: Guía de Aspose.Email para Java

## Introducción a la gestión del uso compartido de calendarios
Gestionar invitaciones de uso compartido de calendarios puede ser una tarea compleja, especialmente al tratar con múltiples usuarios en diferentes plataformas. En este tutorial **creará una invitación de uso compartido de calendario** con Aspose.Email para Java, cubriendo todo desde la creación de acceso delegado hasta el envío de correos electrónicos de uso compartido de calendario. Al final, podrá establecer permisos de delegado, **configurar permisos de calendario**, y optimizar la colaboración en su organización.

**Qué aprenderá**
- Cómo inicializar el cliente EWS con Aspose.Email para Java  
- Crear un usuario delegado y **establecer permisos de delegado**  
- **Crear acceso delegado** y configurar permisos de calendario  
- Enviar un **correo electrónico de uso compartido de calendario** (invitación) de forma programática  
- Escenarios del mundo real donde estas funciones aportan valor  

Antes de profundizar, asegurémonos de que tiene todo lo necesario.

## Respuestas rápidas
- **¿Cuál es el propósito principal de esta guía?** Mostrar cómo **crear una invitación de uso compartido de calendario** usando Aspose.Email para Java.  
- **¿Qué versión de la biblioteca se requiere?** Aspose.Email para Java 25.4 (clasificador JDK 16).  
- **¿Necesito una licencia?** Sí, se requiere una licencia de prueba o completa para uso en producción.  
- **¿Qué entorno se necesita?** JDK 16+, Maven y una cuenta de Exchange Online.  
- **¿Puedo usar esto con otros servidores Exchange?** Sí, pero puede que necesite ajustar la URL del servicio y los niveles de permiso.

## ¿Qué es una invitación de uso compartido de calendario?
Una invitación de uso compartido de calendario es un mensaje de correo electrónico que otorga a otro usuario acceso para ver (o editar) su calendario sin conceder derechos completos de buzón. Se utiliza comúnmente para la coordinación de equipos, la planificación de proyectos y la gestión de eventos.

## ¿Por qué configurar permisos de calendario?
Configurar permisos de calendario le permite controlar exactamente lo que un delegado puede hacer: si solo puede leer eventos, proponer nuevos o editar entradas existentes. Una configuración adecuada de permisos protege la información sensible mientras permite una colaboración eficaz.

## Requisitos previos
- **Java Development Kit (JDK):** Versión 16 o posterior.  
- **Maven:** Para la gestión de dependencias y la compilación del proyecto.  
- **Biblioteca Aspose.Email para Java:** Versión 25.4 con soporte para JDK 16.  

### Requisitos de configuración del entorno
1. Instale JDK si aún no lo ha hecho. Puede descargarlo desde [Oracle's official site](https://www.oracle.com/java/technologies/javase-downloads.html).  
2. Asegúrese de que Maven esté instalado y configurado en su máquina.  
3. Elija un IDE como IntelliJ IDEA o Eclipse para facilitar el desarrollo.

### Conocimientos previos
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
Aspose.Email for Java requiere una licencia para funcionalidad completa. Puede:
- **Prueba gratuita:** Descargue desde [Aspose's release page](https://releases.aspose.com/email/java/).  
- **Licencia temporal:** Solicite una clave temporal en el sitio web de Aspose.  
- **Compra:** Obtenga una licencia permanente para implementaciones en producción.

### Inicialización y configuración básica
Una vez que Maven resuelva la dependencia, inicialice el cliente EWS:

```java
IEWSClient client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser", "pwd", "domain");
```

## Cómo crear una invitación de uso compartido de calendario
A continuación cubrimos dos funciones principales: crear y enviar una invitación de uso compartido de calendario, y **establecer permisos de delegado** para el acceso al calendario.

### Función 1: Crear y enviar una invitación de uso compartido de calendario
#### Visión general
Esta función le guía a través de la inicialización del cliente, **crear acceso delegado**, y el envío del correo de invitación.

#### Implementación paso a paso
##### 1️⃣ Initialize EWS Client
```java
IEWSClient client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser", "pwd", "domain");
```
Esto conecta su aplicación Java a Exchange Online.

##### 2️⃣ Create Delegate User
```java
ExchangeDelegateUser delegateUser = new ExchangeDelegateUser("sharingfrom@domain.com", ExchangeDelegateFolderPermissionLevel.NotSpecified);
delegateUser.getFolderPermissions().setCalendarFolderPermissionLevel(ExchangeDelegateFolderPermissionLevel.Reviewer);
client.delegateAccess(delegateUser, "sharingfrom@domain.com");
```
Aquí **creamos acceso delegado** y asignamos el nivel `Reviewer`, que permite al delegado ver los elementos del calendario.

##### 3️⃣ Send Calendar Sharing Invitation
```java
MapiMessage mapiMessage = client.createCalendarSharingInvitationMessage("sharingfrom@domain.com");

MailConversionOptions options = new MailConversionOptions();
options.setConvertAsTnef(true);

MailMessage mail = mapiMessage.toMailMessage(options);
client.send(mail);
```
El código construye un **correo electrónico de uso compartido de calendario** (invitación) y lo envía a través del cliente EWS.

### Función 2: Permiso de acceso al calendario delegado
#### Visión general
Esta sección muestra cómo **configurar permisos de calendario** y asegurar que el delegado tenga los derechos adecuados.

#### Pasos de implementación
##### 1️⃣ Initialize EWS Client (reuse)
```java
IEWSClient client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser", "pwd", "domain");
```

##### 2️⃣ Create and Set Delegate Permissions
```java
ExchangeDelegateUser delegateUser = new ExchangeDelegateUser("sharingfrom@domain.com", ExchangeDelegateFolderPermissionLevel.NotSpecified);
delegateUser.getFolderPermissions().setCalendarFolderPermissionLevel(ExchangeDelegateFolderPermissionLevel.Reviewer);

client.delegateAccess(delegateUser, "sharingfrom@domain.com");
```
Este fragmento **establece permisos de delegado** para que el usuario pueda ver entradas del calendario sin acceso completo al buzón.

## Cómo configurar permisos de calendario para delegados
Cuando necesita que un delegado haga más que solo ver eventos—como editar o eliminar—puede cambiar el `ExchangeDelegateFolderPermissionLevel`:

- `Reviewer` – acceso solo de lectura.  
- `Editor` – acceso de lectura/escritura.  
- `Author` – crear y leer, pero no puede eliminar.  
- `Owner` – control total, incluyendo cambios de permisos.  

**Consejo profesional:** Use el nivel de privilegio mínimo que satisfaga el requisito empresarial para mantener seguros los datos de su calendario.

## Aplicaciones prácticas
Escenarios del mundo real donde **gestionar el uso compartido de calendarios** destaca:
1. **Reuniones corporativas** – Permita que los miembros del equipo vean los horarios de reuniones sin otorgar derechos completos de buzón.  
2. **Gestión de proyectos** – Los líderes de proyecto pueden monitorear cronogramas mientras los desarrolladores mantienen el control de sus propios calendarios.  
3. **Planificación de eventos** – Los proveedores reciben un **correo electrónico de uso compartido de calendario** para coordinar la logística sin exponer detalles internos.

## Consideraciones de rendimiento
- **Gestión de memoria:** Elimine rápidamente los objetos `MailMessage` grandes en aplicaciones de alto volumen.  
- **Manejo de excepciones:** Envuelva las llamadas de red en bloques try‑catch para manejar fallos de conectividad de forma elegante.  
- **Actualizaciones de la biblioteca:** Mantenga Aspose.Email actualizado para beneficiarse de mejoras de rendimiento y correcciones de errores.

## Problemas comunes y soluciones
| Problema | Causa probable | Solución |
|----------|----------------|----------|
| Invitación no recibida | Filtros de spam o dirección de correo incorrecta | Verifique la dirección del destinatario y añada el dominio de envío a la lista de remitentes seguros |
| Permiso no aplicado | Uso del `ExchangeDelegateFolderPermissionLevel` incorrecto | Verifique que el nivel de permiso coincida con el acceso requerido |
| Excepción en tiempo de ejecución en `createCalendarSharingInvitationMessage` | Licencia faltante o biblioteca desactualizada | Asegúrese de que se cargue una licencia válida y esté usando la última versión de Aspose.Email |

## Preguntas frecuentes
**P: ¿Para qué se utiliza Aspose.Email para Java?**  
R: Es una biblioteca integral para manejar correos electrónicos, calendarios y contactos en aplicaciones Java, compatible con Outlook, Exchange y otros protocolos.

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

**Última actualización:** 2026-03-20  
**Probado con:** Aspose.Email para Java 25.4 (clasificador JDK 16)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}