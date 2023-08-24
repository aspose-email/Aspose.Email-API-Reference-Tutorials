---
title: Recuperar notificaciones de estado de entrega con C#
linktitle: Recuperar notificaciones de estado de entrega con C#
second_title: Aspose.Email API de procesamiento de correo electrónico .NET
description: Aprenda cómo recuperar notificaciones de estado de entrega de correo electrónico usando C# y Aspose.Email para .NET.
type: docs
weight: 18
url: /es/net/email-processing-and-analysis/retrieving-delivery-status-notifications-with-csharp/
---

## Introducción

En la comunicación por correo electrónico, las notificaciones de estado de entrega (DSN) desempeñan un papel crucial a la hora de informar a los remitentes sobre el estado de entrega de sus correos electrónicos. Aspose.Email para .NET es una poderosa biblioteca que proporciona funcionalidades para trabajar con correos electrónicos, incluida la recuperación de DSN. En esta guía, recorreremos el proceso de recuperación de notificaciones de estado de entrega utilizando C# y la biblioteca Aspose.Email para .NET.

## Requisitos previos

Antes de comenzar, asegúrese de tener los siguientes requisitos previos:

1. Visual Studio instalado.
2.  Aspose.Email para la biblioteca .NET. Puedes descargarlo desde[aquí](https://releases.aspose.com/email/net).
3. Conocimientos básicos de programación en C#.

## Pasos

Siga estos pasos para recuperar notificaciones de estado de entrega usando Aspose.Email para .NET:

### Paso 1: crear un nuevo proyecto

Abra Visual Studio y cree un nuevo proyecto de aplicación de consola C#.

### Paso 2: Agregar referencia de correo electrónico de Aspose

Copie la DLL Aspose.Email descargada al directorio de su proyecto. Luego, haga clic derecho en el proyecto en el Explorador de soluciones, elija "Agregar" > "Referencia" y busque la DLL Aspose.Email. Haga clic en "Aceptar" para agregar la referencia a su proyecto.

### Paso 3: escribir código para recuperar DSN

 Abre el`Program.cs` archivo en su proyecto e importe los espacios de nombres necesarios:

```csharp
using Aspose.Email;
using Aspose.Email.Imap;
using Aspose.Email.Mail;
```

 Dentro de`Main` método, escriba el código para conectarse al servidor de correo electrónico, recuperar los DSN y procesarlos:

```csharp
class Program
{
    static void Main(string[] args)
    {
        // Configure las credenciales de su servidor IMAP y su host
        string host = "your_imap_host";
        int port = 993;
        string username = "your_email";
        string password = "your_password";

        using (ImapClient client = new ImapClient(host, port, username, password))
        {
            // Seleccione la carpeta Bandeja de entrada
            client.SelectFolder(ImapFolderInfo.InBox);

            // Buscar mensajes con DSN
            MailQueryBuilder queryBuilder = new MailQueryBuilder();
            queryBuilder.HasFlags(Aspose.Email.Mail.MessageFlags.DeliveryNotification);
            MailQuery query = queryBuilder.GetQuery();
            ImapMessageInfoCollection messages = client.ListMessages(query);

            // Procesar DSN recuperados
            foreach (ImapMessageInfo messageInfo in messages)
            {
                MailMessage message = client.FetchMessage(messageInfo.SequenceNumber);

                // Procesar detalles de DSN
                Console.WriteLine("Subject: " + message.Subject);
                Console.WriteLine("From: " + message.From);
                // ... Procesar otros detalles del DSN

                // Marcar el mensaje como leído o borrarlo
                client.DeleteMessage(messageInfo.SequenceNumber);
            }
        }
    }
}
```

 Reemplazar`"your_imap_host"`, `"your_email"` , y`"your_password"` con los detalles reales de su servidor IMAP.

### Paso 4: Ejecute la aplicación

Construya y ejecute su aplicación. Se conectará a su servidor de correo electrónico, recuperará los DSN de la carpeta Bandeja de entrada, procesará sus detalles y, opcionalmente, los eliminará o los marcará como leídos.

## Preguntas frecuentes

### ¿Cómo encuentro el host del servidor IMAP?

 Puede encontrar el host del servidor IMAP en la documentación o configuración de su proveedor de servicios de correo electrónico. Suele tener el formato de`imap.yourdomain.com`.

### ¿Cómo puedo procesar datos de DSN distintos del asunto y el remitente?

 Puede acceder a varias propiedades del`MailMessage` objeto para recuperar detalles de DSN, como direcciones de destinatarios, estado de entrega, marca de tiempo y más. Referirse a[Aspose.Documentación por correo electrónico](https://reference.aspose.com/email/net/) para más información.

### ¿Es necesario eliminar o marcar los DSN como leídos?

No, no es necesario. La eliminación o marcación de DSN como leídos depende de los requisitos de su aplicación. El código proporcionado demuestra ambas opciones, pero puede personalizarlo según sus necesidades.

## Conclusión

Recuperar notificaciones de estado de entrega usando C# y Aspose.Email para .NET es un proceso sencillo. La biblioteca Aspose.Email simplifica la comunicación con el servidor IMAP y proporciona API fáciles de usar para procesar mensajes de correo electrónico. Con esta guía, ahora puede incorporar la funcionalidad de recuperación de DSN en sus aplicaciones C#.