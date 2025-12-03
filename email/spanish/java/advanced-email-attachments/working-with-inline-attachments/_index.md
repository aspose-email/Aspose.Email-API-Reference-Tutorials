---
date: 2025-12-01
description: Aprenda a enviar correos electrónicos con imágenes incrustadas usando
  Aspose.Email para Java. Esta guía muestra cómo incrustar imágenes en el correo electrónico
  y crear correos electrónicos HTML en Java con archivos adjuntos en línea.
language: es
linktitle: Working with Inline Attachments in Aspose.Email
second_title: Aspose.Email Java Email Management API
title: Cómo enviar correo electrónico con imagen incrustada usando Aspose.Email para
  Java
url: /java/advanced-email-attachments/working-with-inline-attachments/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Cómo enviar correo electrónico con imagen incrustada usando Aspose.Email para Java

Incrustar imágenes directamente dentro de un correo electrónico hace que sus mensajes se vean pulidos y garantiza que el destinatario vea los gráficos sin necesidad de descargar archivos separados. En este tutorial aprenderá **cómo enviar correo electrónico con imagen incrustada** usando Aspose.Email para Java, cubriendo todo desde la configuración de la biblioteca hasta la creación de un correo HTML, la adición de recursos en línea y, finalmente, el envío del mensaje.

## Respuestas rápidas
- **¿Cuál es la clase principal para imágenes en línea?** `LinkedResource`
- **¿Qué método referencia la imagen en HTML?** Utilice `cid:yourContentId` en la etiqueta `<img>`
- **¿Necesito una licencia para desarrollo?** Una prueba gratuita funciona para pruebas; se requiere una licencia para producción
- **¿Puedo enviar el correo mediante cualquier servidor SMTP?** Sí, simplemente configure `SmtpClient` con los detalles de su servidor
- **¿Este enfoque es compatible con todos los principales clientes de correo?** La mayoría de los clientes modernos (Outlook, Gmail, Thunderbird) admiten imágenes incrustadas con CID

## ¿Qué son los archivos adjuntos en línea (imágenes incrustadas)?

Los archivos adjuntos en línea, a veces llamados imágenes incrustadas o CID, son archivos que viven dentro del cuerpo MIME de un correo electrónico. Se hacen referencia desde la parte HTML del mensaje con un **Content‑ID** (CID). Esta técnica le permite **incrustar imágenes en el correo** para que aparezcan justo donde coloca la etiqueta `<img>`, sin aparecer como archivos adjuntos descargables por separado.

## ¿Por qué usar imágenes incrustadas en sus correos Java?

- **Aspecto profesional:** Logos, banners y fotos de productos se renderizan instantáneamente.
- **Mejor compromiso:** Los destinatarios son más propensos a leer un correo que se ve completo.
- **Sin clics adicionales:** Los usuarios no necesitan descargar un adjunto para ver la imagen.
- **Marca consistente:** Los recursos de su marca permanecen en línea con el contenido del mensaje.

## Requisitos previos

- Biblioteca Aspose.Email para Java (descargue desde la [documentación oficial de Aspose.Email para Java](https://reference.aspose.com/email/java/))
- Entorno de desarrollo Java 8+
- Acceso a un servidor SMTP para enviar correo
- Archivo de imagen que desea incrustar (p. ej., `logo.png`)

## Guía paso a paso

### Paso 1: Crear un mensaje de correo electrónico HTML básico

Primero, configure un `MailMessage` simple con un cuerpo HTML. Este será el lienzo donde más adelante incrustaremos la imagen.

```java
// Import necessary classes
import com.aspose.email.MailAddress;
import com.aspose.email.MailMessage;

// Create a new email message
MailMessage message = new MailMessage();
message.setSubject("Hello, World!");
message.setFrom(new MailAddress("sender@example.com"));
message.setTo(new MailAddress("recipient@example.com"));
message.setHtmlBody("<html><body>This is a sample email with inline attachments.</body></html>");
```

### Paso 2: Añadir una imagen en línea usando `LinkedResource`

Ahora incrustamos una imagen. La clase `LinkedResource` representa el adjunto en línea. Asigne un **Content‑ID** único y haga referencia a él en el cuerpo HTML con `cid:`.

```java
import com.aspose.email.LinkedResource;

// Create a LinkedResource for the image
LinkedResource linkedResource = new LinkedResource("path/to/your/image.png");
linkedResource.setContentId("image001"); // Unique ID for the inline image

// Add the LinkedResource to the HTML body
message.getLinkedResources().add(linkedResource);

// Reference the inline image in the HTML body
message.setHtmlBody("<html><body>This is an inline image: <img src='cid:image001'></body></html>");
```

> **Consejo profesional:** Mantenga el `ContentId` simple y único dentro del mensaje para evitar conflictos.

### Paso 3: Enviar el correo mediante `SmtpClient`

Configure sus ajustes SMTP y envíe el mensaje. La imagen incrustada viaja junto con el correo, por lo que el destinatario la ve instantáneamente.

```java
import com.aspose.email.SmtpClient;

// Create an instance of SmtpClient
SmtpClient client = new SmtpClient("smtp.example.com", 587, "username", "password");

// Send the email
client.send(message);
```

### Paso 4: Recibir y extraer imágenes en línea (Opcional)

Si necesita procesar mensajes entrantes que contienen imágenes incrustadas, puede cargar el archivo `.eml` y acceder a sus `LinkedResources`.

```java
import com.aspose.email.MailMessage;
import com.aspose.email.LinkedResourceCollection;

// Load the received email message
MailMessage receivedMessage = MailMessage.load("path/to/received_email.eml");

// Access the inline attachments
LinkedResourceCollection inlineAttachments = receivedMessage.getLinkedResources();
```

## Problemas comunes y cómo solucionarlos

| Problema | Por qué ocurre | Solución |
|----------|----------------|----------|
| **Desajuste de Content‑ID** | La referencia `cid:` en HTML no coincide con el `ContentId` establecido en `LinkedResource`. | Asegúrese de que las cadenas sean idénticas (`image001` vs `cid:image001`). |
| **Archivo no encontrado** | La ruta a la imagen es incorrecta o el archivo falta. | Verifique la ruta absoluta/relativa y que el archivo exista en el servidor. |
| **Fallo de autenticación SMTP** | Credenciales o configuración del servidor incorrectas. | Verifique host, puerto, nombre de usuario y contraseña. Active TLS/SSL si es necesario. |
| **Imagen no mostrada en algunos clientes** | Algunos clientes bloquean recursos externos. | Utilice imágenes incrustadas con CID (como se muestra) en lugar de URLs externas. |

## Preguntas frecuentes

**P: ¿Cómo descargo Aspose.Email para Java?**  
R: Puede descargar Aspose.Email para Java desde la [documentación](https://reference.aspose.com/email/java/). Siga las instrucciones de instalación para configurarlo en su proyecto.

**P: ¿Puedo usar Aspose.Email para Java con otras bibliotecas Java?**  
R: Sí, Aspose.Email se integra sin problemas con otras bibliotecas Java, lo que le permite combinar el procesamiento de correo con generación de PDF, OCR o acceso a bases de datos.

**P: ¿Qué formatos de archivo son compatibles para archivos adjuntos en línea?**  
R: Se admiten formatos de imagen comunes como PNG, JPEG, GIF, así como otros tipos de documentos (p. ej., SVG) como recursos en línea.

**P: ¿Cómo manejo los archivos adjuntos en línea en correos HTML?**  
R: Use la clase `LinkedResource` para asignar un `ContentId`, agréguelo a `message.getLinkedResources()` y haga referencia a él en el cuerpo HTML con `<img src='cid:yourContentId'>`.

**P: ¿Aspose.Email para Java es compatible con diferentes servidores de correo?**  
R: Sí, funciona con cualquier servidor SMTP/IMAP/POP3. Simplemente proporcione la dirección del servidor, el puerto y los detalles de autenticación correctos.

---

**Última actualización:** 2025-12-01  
**Probado con:** Aspose.Email para Java 24.12 (última versión al momento de escribir)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}