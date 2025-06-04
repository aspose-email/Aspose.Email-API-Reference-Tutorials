---
"date": "2025-05-30"
"description": "Scopri come manipolare in modo efficiente le proprietà MAPI utilizzando Aspose.Email .NET. Scopri tecniche per impostare più proprietà di valore, personalizzare con proprietà denominate e ottimizzare i flussi di lavoro email."
"title": "Aspose.Email .NET - Padroneggiare la manipolazione delle proprietà MAPI per una gestione avanzata della posta elettronica"
"url": "/it/net/mapi-operations/mastering-mapi-property-manipulation-aspose-email-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Email .NET: padroneggiare la manipolazione delle proprietà MAPI per una gestione avanzata della posta elettronica

Nel dinamico mondo della comunicazione via e-mail, la gestione e la personalizzazione efficaci delle proprietà dei messaggi sono fondamentali per flussi di lavoro ottimizzati e una migliore interoperabilità dei dati. **Aspose.Email per .NET**, gli sviluppatori possono impostare più proprietà di valore sui messaggi MAPI per soddisfare diverse esigenze aziendali. Questo tutorial approfondisce l'implementazione di queste funzionalità utilizzando Aspose.Email, assicurandoti di sfruttarne appieno il potenziale.

## Cosa imparerai
- Impostazione di più proprietà di valore nei messaggi MAPI.
- Utilizzo di proprietà denominate per una personalizzazione avanzata.
- Implementazione di impostazioni di proprietà a valore singolo.
- Applicazioni pratiche e considerazioni sulle prestazioni di Aspose.Email .NET.

Pronti a immergervi nella gestione avanzata della posta elettronica con **Aspose.Email**? Cominciamo!

## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:

### Librerie richieste
- **Aspose.Email per .NET**: Assicurati che il tuo progetto includa questa libreria.
- **.NET Framework o .NET Core/5+**:Il tuo ambiente di sviluppo dovrebbe supportare questi framework.

### Requisiti di configurazione dell'ambiente
- Un IDE C# funzionante come Visual Studio.
- Conoscenza di base dei messaggi MAPI e della gestione delle proprietà nei sistemi di posta elettronica.

## Impostazione di Aspose.Email per .NET
Per integrare Aspose.Email nel tuo progetto, segui questi passaggi di installazione:

**Interfaccia a riga di comando .NET**
```bash
dotnet add package Aspose.Email
```

**Gestore dei pacchetti**
```powershell
Install-Package Aspose.Email
```

**Interfaccia utente del gestore pacchetti NuGet**
- Cerca "Aspose.Email" e installa la versione più recente.

### Acquisizione della licenza
Puoi iniziare con una prova gratuita per esplorare le funzionalità di Aspose.Email. Per un utilizzo prolungato, valuta la possibilità di richiedere una licenza temporanea o di acquistare un abbonamento:
- [Prova gratuita](https://releases.aspose.com/email/net/)
- [Licenza temporanea](https://purchase.aspose.com/temporary-license/)
- [Opzioni di acquisto](https://purchase.aspose.com/buy)

#### Inizializzazione di base
Una volta installato, inizializza Aspose.Email nel tuo progetto:
```csharp
using Aspose.Email.Mapi;
```

## Guida all'implementazione

### Impostazione di proprietà con più valori
Questa funzionalità consente di associare più valori a una proprietà MAPI. È particolarmente utile per le proprietà che richiedono più di un valore.

#### PT_MV_FLOAT e PT_MV_R4
Queste proprietà rappresentano numeri in virgola mobile:
```csharp
string dataDir = "YOUR_DOCUMENT_DIRECTORY";
MapiMessage msg = MapiMessage.FromFile(dataDir + "message.msg");

IList<object> values = new List<object>();
values.Add((float)1);
values.Add((float)2);

msg.SetProperty(new MapiProperty(0x23901004, values));
```

#### PT_MV_DOUBLE e PT_MV_R8
Per numeri in virgola mobile a doppia precisione:
```csharp
values = new List<object>();
values.Add((double)1);
values.Add((double)2);

msg.SetProperty(new MapiProperty(0x23901005, values));
```

#### PT_MV_CURRENCY (mv.fixed.14.4)
Per impostare le proprietà relative alla valuta:
```csharp
values = new List<object>();
values.Add((decimal)123.34);
values.Add((decimal)289.45);

msg.SetProperty(new MapiProperty(0x23901006, values));
```

#### PT_MV_APPTIME
Per valori di tempo specifici dell'applicazione:
```csharp
values = new List<object>();
values.Add(30456.34);
values.Add(40655.45);

msg.SetProperty(new MapiProperty(0x23901007, values));
```

#### PT_MV_I8 e PT_MV_LONGLONG
Gestione di numeri interi grandi:
```csharp
values = new List<object>();
values.Add((long)30456);
values.Add((long)40655);

msg.SetProperty(new MapiProperty(0x23901014, values));
```

#### PT_MV_CLSID (mv.uuid)
Per identificatori univoci:
```csharp
values = new List<object>();
values.Add(Guid.NewGuid());
values.Add(Guid.NewGuid());

msg.SetProperty(new MapiProperty(0x23901048, values));
```

#### PT_MV_SHORT e PT_MV_I2
Impostazione delle proprietà degli interi brevi:
```csharp
values = new List<object>();
values.Add((short)1);
values.Add((short)2);

msg.SetProperty(new MapiProperty(0x23901002, values));
```

#### PT_MV_SYSTIME
Per i valori di tempo di sistema:
```csharp
values = new List<object>();
values.Add(DateTime.Now);
values.Add(DateTime.Now);

msg.SetProperty(new MapiProperty(0x23901040, values));
```

#### PT_MV_BOOLEANO
Le proprietà booleane possono essere impostate come segue:
```csharp
values = new List<object>();
values.Add(true);
values.Add(false);

msg.SetProperty(new MapiProperty(0x2390100b, values));
```

#### PT_MV_BINARIO
Per dati binari:
```csharp
values = new List<object>();
values.Add(Guid.NewGuid().ToByteArray());
values.Add(new byte[]{1,2,4,5,6,7,5,4,3,5,6,7,8,6,4,3,4,5,6,7,8,6,5,4,3,7,8,9,0,2,3,4});

msg.SetProperty(new MapiProperty(0x23901102, values));
```

#### PT_NULL
Per impostare una proprietà null:
```csharp
msg.SetProperty(new MapiProperty(0x67400001, new byte[1]));
```

### Impostazione delle proprietà denominate in un nuovo messaggio
Le proprietà denominate consentono personalizzazioni più descrittive:
```csharp
MapiMessage message = new MapiMessage("sender@test.com", "recipient@test.com", "subj", "Body of test msg");

IList<object> values = new List<object>();
values.Add((int)4);

MapiProperty property = new MapiProperty(message.NamedPropertyMapping.GetNextAvailablePropertyId(MapiPropertyType.PT_MV_LONG), values);
message.NamedPropertyMapping.AddNamedPropertyMapping(property, 0x00008028, new Guid("00062004-0000-0000-C000-000000000046"));
message.SetProperty(property);

// Imposta una proprietà personalizzata con un nome specifico
values = new List<object>();
values.Add((int)4);
property = new MapiProperty(message.NamedPropertyMapping.GetNextAvailablePropertyId(MapiPropertyType.PT_MV_LONG), values);
message.AddCustomProperty(property, "customProperty");
```

### Impostazione della proprietà a valore singolo
Per le proprietà a valore singolo:
```csharp
MapiMessage newMsg = new MapiMessage();
float floatValue = (float)123.456;
long floatTag = newMsg.NamedPropertyMapping.GetNextAvailablePropertyId(MapiPropertyType.PT_FLOAT);
Guid guid = Guid.NewGuid();

MapiProperty newMapiProperty = new MapiProperty(floatTag, BitConverter.GetBytes(floatValue));
newMsg.NamedPropertyMapping.AddNamedPropertyMapping(newMapiProperty, 12, guid);
newMsg.SetProperty(newMapiProperty);
```

## Applicazioni pratiche
Le funzionalità di manipolazione delle proprietà di Aspose.Email hanno diverse applicazioni:
1. **Tagging automatico delle e-mail**: Categorizza in modo efficiente le email per una migliore organizzazione.
2. **Integrazione di metadati personalizzati**: Allega dati aggiuntivi ai messaggi per un monitoraggio e un'analisi più efficaci.
3. **Supporto multivaluta**: Gestisci senza problemi le transazioni finanziarie che coinvolgono valute diverse.
4. **Sicurezza avanzata**: Utilizzare identificatori univoci (GUID) per la gestione sicura dei messaggi.
5. **Sincronizzazione dell'ora di sistema**: Garantire una marcatura temporale coerente nei sistemi distribuiti.

## Considerazioni sulle prestazioni
Quando si manipolano le proprietà MAPI, tenere presente quanto segue per ottimizzare le prestazioni:
- Ridurre al minimo le modifiche alle proprietà per diminuire i costi generali di elaborazione.
- Aggiornamenti batch ove possibile per migliorare l'efficienza.
- Monitorare l'utilizzo della memoria quando si gestiscono grandi set di dati o numerose e-mail.

## Conclusione
Padroneggiando la manipolazione delle proprietà MAPI con Aspose.Email .NET, puoi migliorare significativamente i tuoi flussi di lavoro di gestione delle email. Questa guida fornisce esempi pratici e applicazioni per aiutarti a iniziare. Per ulteriori approfondimenti, valuta la possibilità di sperimentare diversi tipi di proprietà e scenari.

Ricorda che la chiave per una gestione efficace della posta elettronica è comprendere gli strumenti a tua disposizione e applicarli in modo strategico.

## Consigli per le parole chiave
- "Aspose.Email .NET"
- "Manipolazione delle proprietà MAPI"
- "Ottimizzazione della gestione della posta elettronica"

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}