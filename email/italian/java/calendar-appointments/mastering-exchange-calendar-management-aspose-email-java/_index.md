---
date: '2026-01-04'
description: Impara come creare un calendario Exchange in Java usando Aspose.Email
  per Java. Include la dipendenza Maven, la connessione a Exchange in Java e la gestione
  degli appuntamenti.
keywords:
- Exchange Calendar Management
- Aspose.Email for Java
- Java Exchange Server Integration
title: Crea un calendario Exchange in Java con Aspose.Email – Guida completa
url: /it/java/calendar-appointments/mastering-exchange-calendar-management-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Crea calendario Exchange Java con Aspose.Email

## Introduzione

Gestire email e calendari in un ambiente aziendale può essere complesso, soprattutto quando è necessario **create exchange calendar java** programmi che funzionano su più utenti e fusi orari. Fortunatamente, **Aspose.Email for Java** semplifica queste attività fornendo API robuste per la gestione dei calendari di Exchange Server. In questa guida completa, imparerai a connetterti a un server Exchange, creare cartelle calendario e gestire gli appuntamenti—tutto con codice Java chiaro, passo dopo passo.

**Cosa imparerai**
- Come **connect to exchange java** usando Aspose.Email  
- Come aggiungere la **maven dependency aspose email** al tuo progetto  
- Creare una nuova cartella calendario e gestire gli appuntamenti  
- Aggiornare, elencare e annullare gli appuntamenti  

Iniziamo!

## Risposte rapide
- **Qual è la libreria principale?** Aspose.Email for Java  
- **Come aggiungo la libreria?** Usa la dipendenza Maven mostrata di seguito  
- **Posso creare una cartella calendario?** Sì, con una singola chiamata API  
- **Ho bisogno di una licenza?** Una versione di prova funziona per lo sviluppo; è necessaria una licenza completa per la produzione  
- **È compatibile con Office 365?** Assolutamente – lo stesso codice funziona con Exchange Online  

## Cos'è “create exchange calendar java”?
Creare un calendario Exchange in Java significa interagire programmaticamente con una casella di posta Exchange per aggiungere, modificare o rimuovere elementi del calendario. Questo approccio è ideale per la programmazione automatizzata, gli strumenti di gestione delle riunioni o la sincronizzazione del calendario a livello aziendale.

## Perché usare Aspose.Email per Java?
- **Full‑featured API** – Gestisce Exchange Web Services (EWS) senza la gestione SOAP a basso livello.  
- **Cross‑platform** – Funziona su Windows, Linux e macOS con qualsiasi runtime JDK 16+.  
- **No external dependencies** – La libreria include tutto il necessario per comunicare con Exchange.  

## Prerequisiti
- **Aspose.Email for Java** library (version 25.4 or later)  
- JDK 16 o superiore  
- Accesso a un server Exchange (Office 365 o on‑premises)  
- IDE come IntelliJ IDEA, Eclipse o NetBeans  

## Dipendenza Maven Aspose Email
Aggiungi il seguente frammento al tuo `pom.xml`. Questa è la **maven dependency aspose email** necessaria per scaricare la libreria da Maven Central.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Passaggi per l'acquisizione della licenza
1. **Free Trial:** Scarica una versione di prova dal [sito Aspose](https://releases.aspose.com/email/java/) per testare le funzionalità.  
2. **Temporary License:** Ottieni una licenza temporanea per l'accesso a tutte le funzionalità tramite [questo link](https://purchase.aspose.com/temporary-license/).  
3. **Purchase:** Se sei soddisfatto, considera l'acquisto di una licenza completa su [la pagina di acquisto di Aspose](https://purchase.aspose.com/buy).

## Connettersi a Exchange Java
**Panoramica:** Questa sezione mostra come **connect to exchange java** usando il client EWS.

### Passo 1: Stabilire la connessione
```java
import com.aspose.email.EWSClient;
import com.aspose.email.IEWSClient;

public class ConnectToExchangeServer {
    public static void main(String[] args) {
        IEWSClient client = null;
        try {
            // Connect to Exchange Server with provided URL and credentials
            client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "username", "password");
            System.out.println("Connected to Exchange server.");
        } finally {
            if (client != null)
                client.dispose();
        }
    }
}
```
**Spiegazione:** Sostituisci `"username"` e `"password"` con le tue credenziali reali. Questo codice crea un'istanza `IEWSClient` che riutilizzerai per tutte le operazioni successive sul calendario.

## Creare una cartella calendario
**Panoramica:** Crea una cartella dedicata all'interno del calendario della casella di posta per tenere organizzati gli appuntamenti correlati.

### Passo 2: Creare una nuova cartella calendario
```java
import com.aspose.email.MailboxInfo;

public class CreateCalendarFolder {
    public static void main(String[] args) {
        IEWSClient client = null;
        try {
            // Connect to Exchange Server (Replace with actual credentials)
            client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "username", "password");

            // Create a new calendar folder named 'new calendar'
            String calendarUri = client.getMailboxInfo().getCalendarUri();
            client.createFolder(calendarUri, "new calendar", null, "IPF.Appointment");
        } finally {
            if (client != null)
                client.dispose();
        }
    }
}
```
**Spiegazione:** La cartella `"new calendar"` appare sotto la gerarchia principale del calendario, pronta a contenere gli appuntamenti creati successivamente.

## Creare un appuntamento nella cartella calendario
**Panoramica:** Aggiungi una riunione o un evento alla cartella calendario appena creata.

### Passo 3: Configurare i dettagli dell'appuntamento
```java
import com.aspose.email.Appointment;
import com.aspose.email.MailAddress;
import java.util.Calendar;
import java.util.Date;
import java.util.UUID;

public class CreateAppointment {
    public static void main(String[] args) {
        IEWSClient client = null;
        try {
            // Connect to Exchange Server (Replace with actual credentials)
            client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "username", "password");

            // Setup appointment details
            Calendar calendar = Calendar.getInstance();
            Date startTime = calendar.getTime();
            calendar.add(Calendar.HOUR, 1);
            Date endTime = calendar.getTime();
            String timeZone = "America/New_York";

            Appointment appointment = new Appointment("Room 121", startTime, endTime,
                    MailAddress.to_MailAddress("email1@aspose.com"),
                    MailAddressCollection.to_MailAddressCollection("email2@aspose.com"));
            appointment.setTimeZone(timeZone);
            appointment.setSummary("EMAILNET-35198 - ".concat(UUID.randomUUID().toString()));
            appointment.setDescription("EMAILNET-35198 Ability to add Java event to Secondary Calendar of Office 365");

            // List subfolders and get the URI for the new calendar folder created earlier
            String newCalendarFolderUri = client.listSubFolders(client.getMailboxInfo().getCalendarUri()).get_Item(0).getUri();

            // Create appointment in the specified calendar folder
            client.createAppointment(appointment, newCalendarFolderUri);
        } finally {
            if (client != null)
                client.dispose();
        }
    }
}
```
**Spiegazione:** Questo codice crea un oggetto `Appointment`, imposta il suo fuso orario, aggiunge i partecipanti e lo salva nella cartella calendario personalizzata.

## Aggiornare l'appuntamento
**Panoramica:** Modifica le proprietà di un appuntamento esistente, come la posizione o l'oggetto.

### Passo 4: Definire l'appuntamento esistente
```java
import com.aspose.email.Appointment;

public class UpdateAppointment {
    public static void main(String[] args) {
        IEWSClient client = null;
        try {
            // Connect to Exchange Server (Replace with actual credentials)
            client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "username", "password");

            // Setup appointment details for existing appointment
            Appointment appointment = new Appointment();
            appointment.setLocation("Room 122");

            // Specify the URI of the calendar folder where the appointment exists
            String newCalendarFolderUri = "YOUR_DOCUMENT_DIRECTORY";

            // Update the location of the existing appointment
            client.updateAppointment(appointment, newCalendarFolderUri);
        } finally {
            if (client != null)
                client.dispose();
        }
    }
}
```
**Spiegazione:** Sostituisci `"YOUR_DOCUMENT_DIRECTORY"` con l'URI della cartella reale dell'appuntamento che desideri aggiornare. Questo frammento dimostra come modificare il campo della posizione.

## Problemi comuni e suggerimenti
- **Authentication errors:** Verifica che l'account abbia accesso EWS e che l'autenticazione a più fattori sia disabilitata o venga usata una password per app.  
- **Folder URI not found:** Usa `client.listSubFolders()` per scoprire l'URI corretto del calendario prima di creare o aggiornare elementi.  
- **Time‑zone mismatches:** Imposta sempre il fuso orario sull'oggetto `Appointment` per evitare sorprese legate all'ora legale.  

## Domande frequenti

**Q: Ho bisogno di una licenza per lo sviluppo?**  
A: Una versione di prova funziona per lo sviluppo e i test, ma è necessaria una licenza completa per le distribuzioni in produzione.

**Q: Posso usarlo con Exchange on‑premises?**  
A: Sì. Basta modificare l'URL EWS per puntare al tuo server on‑premises.

**Q: Java 8 è supportato?**  
A: La libreria supporta JDK 16 e versioni successive; le versioni JDK più vecchie non sono consigliate per l'ultima versione.

**Q: Come elimino un appuntamento?**  
A: Usa `client.deleteAppointment(appointmentId, calendarFolderUri);` dopo aver recuperato l'ID univoco dell'appuntamento.

**Q: Cosa fare se devo gestire riunioni ricorrenti?**  
A: Aspose.Email fornisce una classe `Recurrence` che puoi allegare a un `Appointment` prima di salvarlo.

---

**Ultimo aggiornamento:** 2026-01-04  
**Testato con:** Aspose.Email for Java 25.4 (classificatore jdk16)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}