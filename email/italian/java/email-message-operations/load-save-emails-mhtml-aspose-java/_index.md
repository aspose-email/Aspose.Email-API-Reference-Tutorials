---
date: '2026-02-27'
description: Scopri come caricare file MSG e convertirli in MHTML con Aspose.Email
  per Java, includendo impostazioni di fuso orario personalizzate e consigli per l'elaborazione
  batch di email.
keywords:
- Aspose.Email for Java
- load emails in MHTML format
- custom timezone settings
title: Come caricare MSG e salvare come MHTML usando Aspose.Email per Java
url: /it/java/email-message-operations/load-save-emails-mhtml-aspose-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Come caricare MSG e salvare come MHTML usando Aspose.Email per Java

## Introduzione

Se hai bisogno di **come caricare file msg**, regolare i loro timestamp e poi **convertire msg in mhtml**, sei nel posto giusto. In questo tutorial vedremo come caricare un'email `.msg`, applicare un offset di fuso orario personalizzato e salvare il risultato come archivio MHTML, il tutto con Aspose.Email per Java. Che tu stia gestendo un singolo messaggio o una pipeline di **elaborazione batch di email**, questi passaggi ti forniranno una solida base.

**Ciò che imparerai**
- Come caricare un `MailMessage` da un file `.msg`.
- Come impostare un fuso orario personalizzato e la data corrente.
- Come salvare il messaggio come MHTML con formattazione precisa.
- Suggerimenti per scalare l'approccio a scenari batch.

Pronto a potenziare il tuo flusso di lavoro email? Prepariamo prima l'ambiente.

## Risposte rapide
- **Qual è la libreria principale?** Aspose.Email per Java.
- **Posso caricare MSG ed esportare in MHTML in un solo passaggio?** No, devi caricare, regolare, poi salvare.
- **È necessaria una licenza per la produzione?** Sì, è richiesta una licenza valida di Aspose.Email.
- **La gestione dei fusi orari è supportata?** Sì, tramite `setTimeZoneOffset`.
- **Questo può essere usato in elaborazione batch?** Assolutamente – avvolgi i passaggi in un ciclo.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

### Librerie e dipendenze richieste
- Libreria **Aspose.Email per Java** versione 25.4 (classificatore jdk16)
- Conoscenze di base di Java.
- Un IDE come IntelliJ IDEA o Eclipse.

### Requisiti per la configurazione dell'ambiente
- JDK 16 o versioni successive installate.
- Maven per la gestione delle dipendenze.

## Configurazione di Aspose.Email per Java

Per aggiungere la libreria a un progetto Maven, includi la seguente dipendenza:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Passaggi per l'acquisizione della licenza

Inizia con una **prova gratuita** o ottieni una **licenza temporanea** per valutare le capacità complete della libreria senza limitazioni. Per un utilizzo a lungo termine, considera l'acquisto di una licenza:

- [Free Trial](https://releases.aspose.com/email/java/)
- [Temporary License](https://purchase.aspose.com/temporary-license/)
- [Purchase License](https://purchase.aspose.com/buy)

### Inizializzazione di base

Dopo aver aggiunto la dipendenza, inizializza la licenza nel tuo codice Java:

```java
import com.aspose.email.License;

License license = new License();
license.setLicense("path_to_your_license_file.lic");
```

## Guida all'implementazione

Divideremo l'implementazione in tre funzionalità chiare.

### Funzionalità 1: Caricare un MailMessage da un file

#### Panoramica
Caricare un file `.msg` ti dà pieno accesso programmatico al contenuto dell'email, agli allegati e ai metadati.

#### Passo‑per‑passo

**Importa le classi necessarie**

```java
import com.aspose.email.MailMessage;
import com.aspose.email.MsgLoadOptions;
```

**Carica l'email**

```java
String filename = "YOUR_DOCUMENT_DIRECTORY/MSG file with RTF Formatting.msg";
MailMessage msg = MailMessage.load(filename, new MsgLoadOptions());
```

`MsgLoadOptions` ti consente di controllare come il file MSG viene interpretato; le impostazioni predefinite funzionano nella maggior parte degli scenari.

### Funzionalità 2: Impostare la data corrente e un offset di fuso orario personalizzato

#### Panoramica
Timestamp accurati sono essenziali quando si gestiscono utenti in regioni diverse.

**Imposta la data corrente**

```java
import java.util.Date;

msg.setDate(new Date());
```

**Applica un offset di fuso orario personalizzato (es. UTC+5)**

```java
msg.setTimeZoneOffset(5 * 60 * 60 * 1000); // 5 hours ahead of UTC in milliseconds.
```

L'offset è espresso in millisecondi, quindi puoi anche passare valori negativi per i fusi a ovest di UTC.

### Funzionalità 3: Salvare un MailMessage come file MHTML

#### Panoramica
MHTML raggruppa contenuto HTML e risorse incorporate in un unico file, perfetto per l'archiviazione o la condivisione.

**Configura le opzioni di salvataggio**

```java
import com.aspose.email.MhtSaveOptions;
import com.aspose.email.MhtFormatOptions;

MhtSaveOptions mhtOptions = new MhtSaveOptions();
mhtOptions.setMhtFormatOptions(MhtFormatOptions.WriteHeader);
```

**Salva l'email**

```java
msg.save("YOUR_OUTPUT_DIRECTORY/ExportToMHTWithCustomTimezone_out.mhtml", mhtOptions);
```

Il file `.mhtml` risultante conserva la formattazione originale, le immagini e gli allegati.

## Perché convertire MSG in MHTML?

Convertire i file MSG in MHTML ti fornisce una rappresentazione web‑friendly, a file unico, che può essere aperta in qualsiasi browser moderno. Questo è particolarmente utile per:

- **Archiviazione legale** dove è richiesta una copia visiva fedele.
- **Condivisione cross‑platform** senza necessità di Outlook.
- **Incorporare email** in pagine web o documentazione.

## Suggerimenti per l'elaborazione batch di email

Se devi effettuare **elaborazione batch di email**, avvolgi i passaggi di caricamento, regolazione del fuso orario e salvataggio all'interno di un ciclo che itera su una directory di file `.msg`. Ricorda di:

1. Riutilizzare una singola istanza di `License` per evitare overhead.
2. Rilasciare le risorse dopo ogni iterazione (`msg.dispose()` se applicabile).
3. Registrare eventuali errori in un file separato per una revisione successiva.

## Applicazioni pratiche

1. **Archiviazione email:** Conserva le comunicazioni in un formato portatile per la conformità.
2. **Pianificazione globale:** Regola i timestamp a un fuso orario unificato prima di inviare notifiche.
3. **Integrazione CRM:** Importa automaticamente le email archiviate in un sistema CRM come allegati MHTML.

## Considerazioni sulle prestazioni

- **Gestione della memoria:** Elabora grandi batch a blocchi per mantenere basso l'utilizzo di memoria.
- **Ottimizzazione I/O:** Usa stream bufferizzati se leggi/scrivi molti file.
- **Esecuzione parallela:** Considera `ForkJoinPool` di Java per l'elaborazione parallela, ma assicurati della thread‑safety degli oggetti Aspose.

## Conclusione

Ora sai **come caricare file msg**, applicare offset di fuso orario personalizzati e **convertire msg in mhtml** usando Aspose.Email per Java. Queste tecniche possono essere scalate per gestire attività di **elaborazione batch di email**, fornendoti una soluzione robusta per archiviazione, migrazione e automazione delle email.

**Passi successivi**  
Esplora altre funzionalità di Aspose.Email come la gestione degli allegati, l'estrazione di elementi di calendario o l'invio SMTP visitando la [documentazione ufficiale](https://reference.aspose.com/email/java/).

## Domande frequenti

**D: Posso caricare email da formati diversi da .msg?**  
R: Sì, Aspose.Email supporta EML, MSG, MHT e diversi altri formati.

**D: Come posso gestire file email molto grandi in modo efficiente?**  
R: Usa le API di streaming fornite da Aspose.Email per leggere/scrivere dati a blocchi, riducendo la pressione sulla memoria.

**D: È possibile modificare gli allegati all'interno di un MailMessage?**  
R: Assolutamente. Puoi aggiungere, rimuovere o sostituire gli allegati tramite la collezione `MailMessage.getAttachments()`.

**D: Cosa succede se il mio offset di fuso orario è negativo (dietro UTC)?**  
R: Passa un valore millisecondi negativo a `setTimeZoneOffset`, ad esempio `-3 * 60 * 60 * 1000` per UTC‑3.

**D: Posso usare Aspose.Email in progetti commerciali?**  
R: Sì, a condizione di possedere una licenza commerciale valida.

**D: Come elaboro migliaia di file MSG senza esaurire la memoria?**  
R: Elabora i file in batch, rilascia ogni `MailMessage` dopo il salvataggio e considera l'uso del pattern `try‑with‑resources` di Java per la pulizia automatica.

## Risorse
- [Documentation](https://reference.aspose.com/email/java/)
- [Download Library](https://releases.aspose.com/email/java/)
- [Purchase License](https://purchase.aspose.com/buy)
- [Free Trial](https://releases.aspose.com/email/java/)
- [Temporary License](https://purchase.aspose.com/temporary-license/)
- [Support Forum](https://forum.aspose.com/c/email/10)

---

**Ultimo aggiornamento:** 2026-02-27  
**Testato con:** Aspose.Email per Java 25.4 (classificatore jdk16)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}