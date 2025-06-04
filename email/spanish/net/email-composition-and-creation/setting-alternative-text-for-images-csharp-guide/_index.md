---
"description": "Aprenda a configurar texto alternativo para imágenes en correos electrónicos con Aspose.Email para .NET. Garantice la accesibilidad con texto alternativo claro. Documentación y código incluidos."
"linktitle": "Configuración de texto alternativo para imágenes - Guía de C#"
"second_title": "API de procesamiento de correo electrónico Aspose.Email .NET"
"title": "Configuración de texto alternativo para imágenes - Guía de C#"
"url": "/es/net/email-composition-and-creation/setting-alternative-text-for-images-csharp-guide/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Configuración de texto alternativo para imágenes - Guía de C#


Esta guía le guiará a través del proceso de configuración de texto alternativo para imágenes en correos electrónicos con Aspose.Email para .NET. El texto alternativo, también conocido como "texto alt", se utiliza para proporcionar una descripción textual de una imagen en caso de que no se pueda mostrar. Aspose.Email para .NET es una potente biblioteca que permite trabajar con correos electrónicos y archivos adjuntos en varios formatos. En esta guía, nos centraremos en la configuración de texto alternativo para imágenes en mensajes de correo electrónico con C#.

## Prerrequisitos

Antes de comenzar, asegúrese de tener los siguientes requisitos previos:

1. Visual Studio o cualquier entorno de desarrollo C# compatible instalado.
2. Biblioteca Aspose.Email para .NET. Puede usar el Administrador de paquetes NuGet en Visual Studio.

## Paso 1: Crear un nuevo proyecto

1. Inicie Visual Studio y cree un nuevo proyecto de aplicación de consola C#.

## Paso 2: Instalar Aspose.Email mediante NuGet

1. Haga clic derecho en su proyecto en el Explorador de soluciones y seleccione "Administrar paquetes NuGet".
2. Busque "Aspose.Email" e instale la última versión del paquete.

## Paso 3: Agregar declaraciones Using

```csharp

using Aspose.Email.Mime;
```

## Paso 4: Cargar y modificar el mensaje de correo electrónico

1. Cargue el mensaje de correo electrónico utilizando el `MailMessage` clase:

```csharp
MailMessage message = new MailMessage();
message.Subject = "Sample Email with Alternative Text";
message.From = new MailAddress("sender@example.com");
message.To.Add("recipient@example.com");
```

3. Cargar el contenido HTML del mensaje de correo electrónico:

```csharp
var htmlView = AlternateView.CreateAlternateViewFromString("<html><body><img src='cid:logo.jpg' alt='Company Logo'></body></html>", null, "text/html");
```

## Paso 5: Agregar AlternativeView para texto alternativo a las imágenes

Agregue htmlview para texto alternativo a la imagen como AlternateView en el mensaje. 
```csharp
message.AlternateViews.Add(htmlView);
```

## Paso 6: Guardar y enviar el correo electrónico

1. Guarde el mensaje modificado en un archivo o envíelo utilizando el método deseado:

```csharp
message.Save("output.eml", SaveOptions.DefaultEml);
```

## Conclusión

En esta guía, aprendió a configurar texto alternativo para imágenes en correos electrónicos con Aspose.Email para .NET. Siguiendo los pasos descritos anteriormente, puede garantizar que el contenido de su correo electrónico siga siendo accesible e informativo incluso cuando no se puedan mostrar las imágenes.

## Preguntas frecuentes

## ¿Cómo puedo descargar la biblioteca Aspose.Email?

Puede descargar la biblioteca Aspose.Email desde Aspose Releases o instalarla a través del Administrador de paquetes NuGet en Visual Studio.

### ¿Cómo agrego imágenes como recursos vinculados en un correo electrónico?

Para agregar imágenes como recursos vinculados en un correo electrónico, puede utilizar el `LinkedResource` clase. Asigne un ID de contenido al recurso vinculado y luego haga referencia a este ID de contenido en el cuerpo HTML utilizando el `cid:` esquema. Para obtener información detallada, consulte el [Documentación de LinkedResource](https://reference.aspose.com/email/net/aspose.email/linkedresource/).
### ¿Dónde puedo encontrar más documentación sobre Aspose.Email para .NET?

Puede encontrar documentación más detallada, tutoriales y ejemplos sobre cómo trabajar con Aspose.Email para .NET en [Referencia de API](https://reference.aspose.com/email/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}