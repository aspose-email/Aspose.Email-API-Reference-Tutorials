---
"date": "2025-05-29"
"description": "Scopri come gestire in modo efficiente più proprietà nei messaggi MAPI utilizzando Aspose.Email per Java. Questa guida illustra l'impostazione di tipi float, double, long e altri."
"title": "Imposta più proprietà MAPI in Java con Aspose.Email&#58; una guida completa"
"url": "/it/java/mapi-operations/aspose-email-java-set-mapi-properties/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Impostare più proprietà MAPI in Java con Aspose.Email: una guida completa

## Introduzione

Gestire efficacemente le proprietà dei messaggi MAPI è fondamentale per migliorare le applicazioni Java. Con Aspose.Email per Java, è possibile impostare diverse proprietà come float, double, long, short, boolean e proprietà personalizzate in modo semplice. Questa guida illustra diversi metodi per raggiungere questo obiettivo.

**Cosa imparerai:**
- Impostazione di più proprietà nei messaggi MAPI utilizzando Aspose.Email Java
- Comprendere i diversi tipi di proprietà e i loro usi
- Esempi pratici di codice per l'implementazione

Cominciamo col parlare dei prerequisiti.

## Prerequisiti

Per seguire, assicurati di avere:
- **Kit di sviluppo Java (JDK):** JDK 8 o versione successiva installata.
- **Libreria Aspose.Email:** Si consiglia la versione 25.4.
- **Configurazione Maven:** Maven dovrebbe essere configurato nel tuo IDE per la gestione delle dipendenze.

### Librerie richieste

Includi Aspose.Email come dipendenza nel tuo `pom.xml`:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Acquisizione della licenza
- **Prova gratuita:** Inizia con una prova gratuita per esplorare le funzionalità.
- **Licenza temporanea:** Ottienilo per test estesi senza limitazioni.
- **Acquistare:** Se soddisfa le tue esigenze, prendi in considerazione l'acquisto.

## Impostazione di Aspose.Email per Java

Assicurati che Aspose.Email sia configurato correttamente nel tuo ambiente di sviluppo:
1. **Dipendenze di importazione:** Risolvere le dipendenze di Maven.
2. **Imposta licenza:**
   - Scarica un file di licenza da [Posare](https://purchase.aspose.com/buy).
   - Applicalo utilizzando:
     ```java
     com.aspose.email.License license = new com.aspose.email.License();
     license.setLicense("path/to/your/license.lic");
     ```

Una volta completata la configurazione, vediamo come impostare le varie proprietà.

## Guida all'implementazione

### Impostazione di più proprietà float

L'impostazione delle proprietà float consente un'archiviazione efficiente dei dati numerici:

#### Panoramica
Questa funzionalità illustra come aggiungere più valori float come proprietà del messaggio MAPI utilizzando Aspose.Email per Java.

#### Passi
1. **Crea e inizializza il messaggio**
   ```java
   import java.util.ArrayList;
   import com.aspose.email.MapiMessage;
   import com.aspose.email.MapiProperty;
   import com.aspose.email.system.collections.IList;

   MapiMessage msg = new MapiMessage();
   ```
2. **Aggiungere valori float a un elenco**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((float) 1);
   values.addItem((float) 2);
   ```
3. **Imposta la proprietà con un identificatore univoco**
   ```java
   msg.setProperty(new MapiProperty(0x23901004, values));
   ```
*Spiegazione:* Il tag di proprietà `0x23901004` identifica questo set di proprietà float.

### Impostazione di più proprietà doppie

Le proprietà doppie memorizzano numeri in virgola mobile ad alta precisione:

#### Panoramica
Questa sezione illustra come memorizzare più valori double come proprietà del messaggio MAPI.

#### Passi
1. **Inizializza il messaggio**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Popola i valori doppi**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((double) 1);
   values.addItem((double) 2);
   ```
3. **Assegna al tag della proprietà**
   ```java
   msg.setProperty(new MapiProperty(0x23901005, values));
   ```

### Impostazione di più proprietà APPTIME

Le proprietà APPTIME memorizzano le durate temporali in modo efficiente:

#### Panoramica
Questa funzionalità illustra l'utilizzo di numeri a doppia precisione per le rappresentazioni temporali.

#### Passi
1. **Crea oggetto messaggio**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Aggiungi valori di tempo**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem(30456.34);
   values.addItem(40655.45);
   ```
3. **Imposta la proprietà**
   ```java
   msg.setProperty(new MapiProperty(0x23901007, values));
   ```

### Impostazione di più proprietà lunghe

Le proprietà lunghe sono ideali per i numeri interi grandi:

#### Panoramica
Questa funzionalità si concentra sull'impostazione di più valori interi lunghi in un messaggio.

#### Passi
1. **Inizializza il messaggio MAPI**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Aggiungi valori lunghi**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((long) 30456);
   values.addItem((long) 40655);
   ```
3. **Definisci tag proprietà**
   ```java
   msg.setProperty(new MapiProperty(0x23901014, values));
   ```

### Impostazione di più proprietà brevi

Le proprietà brevi memorizzano in modo efficiente i dati interi di piccole dimensioni:

#### Panoramica
Questa guida illustra come impostare numeri interi brevi come proprietà del messaggio.

#### Passi
1. **Inizializza il messaggio**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Aggiungi valori brevi**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((short) 1);
   values.addItem((short) 2);
   ```
3. **Assegna tag proprietà**
   ```java
   msg.setProperty(new MapiProperty(0x23901002, values));
   ```

### Impostazione di più proprietà booleane

Le proprietà booleane memorizzano gli stati vero/falso:

#### Panoramica
Scopri come impostare più valori booleani in un messaggio.

#### Passi
1. **Crea oggetto messaggio**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Aggiungi valori booleani**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem(true);
   values.addItem(false);
   ```
3. **Imposta proprietà con identificatore**
   ```java
   msg.setProperty(new MapiProperty(0x2390100b, values));
   ```

### Impostazione di una proprietà Null

Impostare esplicitamente una proprietà come null può essere utile:

#### Panoramica
Questa sezione illustra come assegnare un valore null a una proprietà.

#### Passi
1. **Inizializza il messaggio**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Assegna proprietà Null**
   ```java
   msg.setProperty(new MapiProperty(0x67400001, new byte[1]));
   ```

### Impostazione della proprietà lunga denominata con ID personalizzato e UUID

Per scenari complessi, imposta le proprietà denominate:

#### Panoramica
Questa funzionalità illustra come impostare una proprietà lunga con un identificatore personalizzato e un UUID.

#### Passi
1. **Inizializza il messaggio**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Aggiungi valori lunghi**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((int) 4);
   UUID uuid = UUID.randomUUID();
   ```
3. **Crea e mappa proprietà**
   ```java
   MapiProperty property = new MapiProperty(msg.getNamedPropertyMapping().getNextAvailablePropertyId(com.aspose.email.MapiPropertyType.PT_MV_LONG), values);
   msg.getNamedPropertyMapping().addNamedPropertyMapping(property, (long) 0x00008028, uuid);
   msg.setProperty(property);
   ```

### Impostazione della proprietà personalizzata con nome

Le proprietà personalizzate possono essere denominate per una più facile identificazione:

#### Panoramica
Questa guida illustra come impostare proprietà con nomi personalizzati.

#### Passi
1. **Inizializza l'oggetto messaggio**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Definisci proprietà personalizzata**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem("Custom Value");
   UUID uuid = UUID.randomUUID();
   
   MapiProperty property = new MapiProperty(msg.getNamedPropertyMapping().getNextAvailablePropertyId(com.aspose.email.MapiPropertyType.PT_STRING), values);
   msg.getNamedPropertyMapping().addNamedPropertyMapping(property, "CustomName", uuid);
   ```

### Impostazione e convalida delle proprietà

È fondamentale assicurarsi che le proprietà siano impostate correttamente:

#### Panoramica
Questa sezione riguarda l'impostazione e la convalida di più proprietà nei messaggi MAPI.

#### Passi
1. **Imposta proprietà**
   Per impostare una proprietà, seguire gli esempi precedenti.
2. **Convalida proprietà**
   ```java
   if (msg.getProperties().containsKey(0x23901004)) {
       System.out.println("Property is set correctly.");
   } else {
       System.err.println("Property setting failed.");
   }
   ```

## Conclusione

Questa guida ha fornito un approccio completo alla gestione di più proprietà nei messaggi MAPI utilizzando Aspose.Email per Java. Seguendo questi passaggi, è possibile archiviare e gestire in modo efficiente diversi tipi di dati all'interno delle applicazioni.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}