---
"date": "2025-05-29"
"description": "Scopri come configurare i client SMTP con Aspose.Email per Java e inoltrare le email in modo efficiente. Ideale per gli sviluppatori di applicazioni aziendali."
"title": "Inoltro di posta elettronica SMTP tramite Aspose.Email per Java&#58; una guida completa"
"url": "/it/java/smtp-client-operations/smtp-email-forwarding-aspose-email-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Inoltro di posta elettronica SMTP tramite Aspose.Email per Java: una guida completa

Nell'era digitale, la gestione delle email a livello di programmazione è essenziale per gli sviluppatori che lavorano su sistemi di comunicazione aziendali o con i clienti. Questa guida fornisce una guida dettagliata alla configurazione di un client SMTP con Aspose.Email per Java per inoltrare le email in modo efficiente senza utilizzare `MailMessage`Scopriamo come questo potente strumento può soddisfare le tue esigenze di automazione delle email.

## Cosa imparerai:
- Configurazione di un client SMTP con Aspose.Email per Java
- Gestione dei destinatari di posta elettronica tramite una raccolta
- Inoltro di e-mail direttamente dai flussi di file

**Prerequisiti:** Prima di iniziare, assicurati di avere a disposizione la seguente configurazione per seguire efficacemente questo tutorial.

### Prerequisiti
Per completare con successo questa guida, assicurati di avere:

- **Librerie e dipendenze:**
  - Aspose.Email per Java versione 25.4 o successiva.
  
- **Configurazione dell'ambiente:**
  - Un JDK (Java Development Kit) compatibile, preferibilmente JDK 16 come specificato dal classificatore nella nostra dipendenza Maven.
- **Prerequisiti di conoscenza:**
  - Conoscenza di base dei protocolli SMTP
  - Familiarità con la programmazione Java

## Impostazione di Aspose.Email per Java

Integrare Aspose.Email nel tuo progetto è semplice utilizzando Maven. Aggiungi la seguente dipendenza al tuo `pom.xml` file:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Acquisizione di una licenza
Aspose.Email offre una licenza di prova gratuita per testarne tutte le funzionalità senza limitazioni. Ecco come ottenerla:

1. **Prova gratuita:** Visita [Pagina di prova gratuita di Aspose](https://releases.aspose.com/email/java/) per scaricare e iniziare con la versione di valutazione.
2. **Licenza temporanea:** Per test prolungati, richiedi una licenza temporanea tramite [Pagina di richiesta della licenza](https://purchase.aspose.com/temporary-license/).
3. **Acquistare:** Se ritieni che Aspose.Email sia utile per i tuoi progetti, valuta l'acquisto di una licenza completa su [Pagina di acquisto di Aspose](https://purchase.aspose.com/buy).

### Inizializzazione e configurazione di base

Una volta incluso Aspose.Email nel progetto, inizializza i componenti necessari:

```java
import com.aspose.email.SecurityOptions;
import com.aspose.email.SmtpClient;

String host = "mail.domain.com"; // L'indirizzo del tuo server SMTP
String username = "username";    // Nome utente per l'autenticazione
int smtpPort = 587;              // Numero di porta, in genere 587 per TLS/STARTTLS
String password = "password";    // Password per l'autenticazione

// Crea un'istanza di SmtpClient con le credenziali specificate.
SmtpClient client = new SmtpClient(host, smtpPort, username, password, SecurityOptions.SSLExplicit);
```

## Guida all'implementazione

### Configurazione del client SMTP
Questa sezione ti guida attraverso la configurazione di un client SMTP per l'invio di email. Impostando il `SmtpClient`, stabilisci una connessione con il tuo server di posta elettronica utilizzando le credenziali e le opzioni di sicurezza specificate.

#### Panoramica
La configurazione prevede la specificazione dell'host SMTP, della porta, del nome utente, della password e dell'opzione di sicurezza, in genere SSLExplicit per le connessioni sicure.

```java
import com.aspose.email.SecurityOptions;
import com.aspose.email.SmtpClient;

String host = "mail.domain.com";
String username = "username";
int smtpPort = 587;
String password = "password";

// Inizializza SmtpClient con le credenziali specificate.
SmtpClient client = new SmtpClient(host, smtpPort, username, password, SecurityOptions.SSLExplicit);
```

### Raccolta destinatari e-mail
La gestione di un elenco di destinatari è semplificata utilizzando `MailAddressCollection`, che consente di aggiungere facilmente più indirizzi email.

#### Panoramica
Questa raccolta consente l'archiviazione e la gestione delle email dei destinatari per le operazioni di inoltro o invio.

```java
import com.aspose.email.MailAddressCollection;

// Crea una nuova istanza di MailAddressCollection.
MailAddressCollection recipients = new MailAddressCollection();

// Aggiungere più destinatari alla raccolta.
recipients.add("to1@domain.com");
recipients.add("to2@domain.com");
```

### Inoltro di posta elettronica senza utilizzare MailMessage
Questa potente funzionalità consente di inoltrare un file di posta elettronica direttamente utilizzando un `FileInputStream` e il `SmtpClient`.

#### Panoramica
Invece di creare un nuovo `MailMessage`, questo metodo utilizza i file EML esistenti, rendendolo efficiente per l'inoltro in blocco.

```java
import java.io.FileInputStream;
import java.io.IOException;

String fileName = "YOUR_DOCUMENT_DIRECTORY/test.eml"; // Percorso al tuo file EML

// Aprire FileInputStream per il file di posta elettronica.
FileInputStream fos = new FileInputStream(fileName);

try {
    // Inoltra l'e-mail utilizzando l'istanza SmtpClient e la raccolta dei destinatari.
    client.forward("Sender@domain.com\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}