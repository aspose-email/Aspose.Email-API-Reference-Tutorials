---
title: Configuración de texto alternativo para imágenes - Guía de C#
linktitle: Configuración de texto alternativo para imágenes - Guía de C#
second_title: Aspose.Email API de procesamiento de correo electrónico .NET
description: Aprenda a configurar texto alternativo para imágenes en correos electrónicos usando Aspose.Email para .NET. Garantice la accesibilidad con texto alternativo claro. Documentación y código incluidos.
weight: 15
url: /es/net/email-composition-and-creation/setting-alternative-text-for-images-csharp-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Configuración de texto alternativo para imágenes - Guía de C#


Esta guía lo guiará a través del proceso de configuración de texto alternativo para imágenes en correos electrónicos usando Aspose.Email para .NET. El texto alternativo, también conocido como "texto alternativo", se utiliza para proporcionar una descripción textual de una imagen en caso de que la imagen no se pueda mostrar. Aspose.Email para .NET es una poderosa biblioteca que le permite trabajar con correos electrónicos y archivos adjuntos en varios formatos. En esta guía, nos centraremos en configurar texto alternativo para imágenes en mensajes de correo electrónico usando C#.

## Requisitos previos

Antes de comenzar, asegúrese de tener los siguientes requisitos previos:

1. Visual Studio o cualquier entorno de desarrollo C# compatible instalado.
2. Aspose.Email para la biblioteca .NET. Puede utilizar el Administrador de paquetes NuGet en Visual Studio.

## Paso 1: crear un nuevo proyecto

1. Inicie Visual Studio y cree un nuevo proyecto de aplicación de consola C#.

## Paso 2: Instale Aspose.Email a través de NuGet

1. Haga clic derecho en su proyecto en el Explorador de soluciones y seleccione "Administrar paquetes NuGet".
2. Busque "Aspose.Email" e instale la última versión del paquete.

## Paso 3: agregar declaraciones de uso

```csharp

using Aspose.Email.Mime;
```

## Paso 4: cargue y modifique el mensaje de correo electrónico

1.  Cargue el mensaje de correo electrónico usando el`MailMessage` clase:

```csharp
MailMessage message = new MailMessage();
message.Subject = "Sample Email with Alternative Text";
message.From = new MailAddress("sender@example.com");
message.To.Add("recipient@example.com");
```

3. Cargue el contenido HTML del mensaje de correo electrónico:

```csharp
var htmlView = AlternateView.CreateAlternateViewFromString("<html><body><img src='cid:logo.jpg' alt='Company Logo'></body></html>", null, "text/html");
```

## Paso 5: agregue AlternativeView para texto alternativo a las imágenes

Agregue htmlview para texto alternativo a imagen como vista alternativa en el mensaje. 
```csharp
message.AlternateViews.Add(htmlView);
```

## Paso 6: guarde y envíe el correo electrónico

1. Guarde el mensaje modificado en un archivo o envíelo utilizando el método que desee:

```csharp
message.Save("output.eml", SaveOptions.DefaultEml);
```

## Conclusión

En esta guía, aprendió cómo configurar texto alternativo para imágenes en mensajes de correo electrónico usando Aspose.Email para .NET. Si sigue los pasos descritos anteriormente, puede asegurarse de que el contenido de su correo electrónico permanezca accesible e informativo incluso cuando las imágenes no se puedan mostrar.

## Preguntas más frecuentes

## ¿Cómo puedo descargar la biblioteca Aspose.Email?

Puede descargar la biblioteca Aspose.Email desde las versiones de Aspose o instalarla a través del Administrador de paquetes NuGet en Visual Studio.

### ¿Cómo agrego imágenes como recursos vinculados en un correo electrónico?

Para agregar imágenes como recursos vinculados en un correo electrónico, puede utilizar el`LinkedResource` clase. Asigne un ID de contenido al recurso vinculado y luego haga referencia a este ID de contenido en el cuerpo HTML utilizando el`cid:` esquema. Para obtener información detallada, consulte la[Documentación de recursos vinculados](https://reference.aspose.com/email/net/aspose.email/linkedresource/).
### ¿Dónde puedo encontrar más documentación sobre Aspose.Email para .NET?

 Puede encontrar documentación más detallada, tutoriales y ejemplos sobre cómo trabajar con Aspose.Email para .NET en el[Referencia de API](https://reference.aspose.com/email/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
