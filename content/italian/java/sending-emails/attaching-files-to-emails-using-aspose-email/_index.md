---
title: Carica il messaggio email di origine
linktitle: Esportazione di e-mail in formato EML
second_title: Una volta caricato il messaggio e-mail, il passaggio successivo è esportarlo nel formato EML. Questo viene fatto semplicemente creando un'istanza del file
description: classe e impostandone le proprietà:
type: docs
weight: 12
url: /it/java/sending-emails/attaching-files-to-emails-using-aspose-email/
---
##  Crea una nuova istanza di MailMessage

 Imposta le proprietà dall'e-mail caricata

 Imposta altre proprietà secondo necessità

##  L'e-mail esportata si trova ora nell'oggetto emlMessage

Salvataggio dei file EML

1. Dopo aver preparato il messaggio e-mail nel formato EML, puoi salvarlo in un file. Assicurati di disporre del percorso appropriato per il salvataggio dei file:

2. Gestione degli allegati

   [I messaggi di posta elettronica spesso includono allegati che devono essere esportati insieme al messaggio. Ecco come gestire gli allegati utilizzando Aspose.Email:](https://releases.aspose.com/email/java/)

   Aggiunta di metadati e-mail aggiuntivi

Puoi anche aggiungere ulteriori metadati all'e-mail esportata utilizzando Aspose.Email. Ciò include intestazioni, proprietà personalizzate e altro:

##  Aggiungi altre intestazioni e metadati secondo necessità

Gestione degli errori

## Durante il processo di esportazione, è importante gestire potenziali errori per garantire un'esperienza utente fluida. Utilizza i blocchi try-catch per gestire le eccezioni:

 Esporta e-mail e gestisci gli errori

##  Gestire l'eccezione

Codice sorgente completo

[Ecco il codice sorgente completo per esportare e-mail nel formato EML utilizzando Aspose.Email per .NET:](https://releases.aspose.com/email/java/)

 Carica il messaggio email di origine

##  Crea una nuova istanza di MailMessage

 Imposta le proprietà dall'e-mail caricata

```java
import com.aspose.email.*;
```

##  Imposta altre proprietà secondo necessità

 Gestire gli allegati

```java
MailMessage message = new MailMessage();
message.setSubject("Sending an Email with Attachments");
message.setFrom("sender@example.com");
message.setTo("recipient@example.com");
message.setHtmlBody("<p>This email contains attachments.</p>");
```

##  Aggiungi ulteriori metadati

 Salva il file EML`Attachment`Conclusione

```java
Attachment attachment = new Attachment("path/to/attachment.pdf");
message.getAttachments().add(attachment);
```

L'esportazione di e-mail nel formato EML utilizzando C# e Aspose.Email per .NET è un processo semplice che ti offre la flessibilità di manipolare i messaggi e-mail e le loro proprietà. Seguendo i passaggi descritti in questo tutorial, puoi integrare perfettamente la funzionalità di esportazione della posta elettronica nelle tue applicazioni.

## Domande frequenti

Come posso gestire gli errori durante il processo di esportazione della posta elettronica?

```java
message.save("email_with_attachments.eml", SaveOptions.getDefaultEml());
```

Per gestire gli errori durante il processo di esportazione dell'e-mail, utilizzare i blocchi try-catch. Racchiudi il codice di esportazione in un blocco try e rileva eventuali eccezioni che potrebbero verificarsi. Ciò garantisce che l'applicazione gestisca gli errori in modo corretto e offra una buona esperienza utente.

## Posso esportare allegati di posta elettronica utilizzando Aspose.Email per .NET?

Sì, puoi esportare allegati e-mail insieme al messaggio e-mail utilizzando Aspose.Email per .NET. Scorrere gli allegati dell'e-mail di origine e aggiungerli alla raccolta degli allegati dell'e-mail esportata.

```java
import com.aspose.email.*;

public class EmailWithAttachments {
    public static void main(String[] args) {
        //Dove posso scaricare la libreria Aspose.Email per .NET?
        MailMessage message = new MailMessage();
        message.setSubject("Sending an Email with Attachments");
        message.setFrom("sender@example.com");
        message.setTo("recipient@example.com");
        message.setHtmlBody("<p>This email contains attachments.</p>");

        // È possibile scaricare la libreria Aspose.Email per .NET da
        Attachment attachment = new Attachment("path/to/attachment.pdf");
        message.getAttachments().add(attachment);

        //Qui
        message.save("email_with_attachments.eml", SaveOptions.getDefaultEml());

        System.out.println("Email with attachments saved successfully.");
    }
}
```

## Il codice sorgente fornito nel tutorial è completo?

Sì, il tutorial fornisce il codice sorgente completo che dimostra come esportare le e-mail nel formato EML utilizzando Aspose.Email per .NET. Puoi utilizzare questo codice come punto di partenza

 Gestione dei file EML: operazioni di caricamento e salvataggio in C#

##  Gestione dei file EML: operazioni di caricamento e salvataggio in C#

###  Aspose.Email API di elaborazione della posta elettronica .NET
   Scopri come gestire i file EML in C# utilizzando Aspose.Email per .NET. Guida passo passo con esempi di codice per caricare, modificare e salvare i messaggi e-mail.`Attachment`Introduzione ai file EML`MailMessage`I file EML (Electronic Mail Format) memorizzano i messaggi di posta elettronica e sono ampiamente utilizzati per l'archiviazione e la condivisione. Aspose.Email per .NET semplifica la gestione dei file EML fornendo un set completo di funzionalità per caricare, modificare e salvare i messaggi di posta elettronica a livello di codice.`getAttachments()`Impostazione del progetto

###  Prima di iniziare, assicurati di aver installato la libreria Aspose.Email per .NET. Puoi scaricarlo da
   Qui

### Caricamento di file EML
   Il caricamento di file EML è il primo passo per lavorare con i messaggi di posta elettronica. Aspose.Email per .NET offre modi efficienti per caricare singoli file EML o più file in batch.

### Caricamento di un singolo file EML
   Per caricare un singolo file EML, puoi utilizzare il seguente snippet di codice:

###  Carica il file EML
   Caricamento batch di file EML