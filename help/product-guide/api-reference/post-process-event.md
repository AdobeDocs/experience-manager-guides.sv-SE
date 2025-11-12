---
title: Händelsehanterare efter bearbetning
description: Läs om händelsehanterare efter bearbetning
exl-id: 3b105ff5-02d4-40e3-a713-206a7fcf18b2
feature: Post-Processing Event Handler
role: Developer
level: Experienced
source-git-commit: 6f212862855e5ce1125137f462b88c933d23ed26
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 0%

---

# Händelsehanterare efter bearbetning {#id175UB30E05Z}

## UUID och Cloud Service

Adobe Experience Manager Guides visar `com/adobe/guides/postprocess/complete`-händelse som används för att utföra efterbehandlingsåtgärder. Den här händelsen utlöses när en åtgärd utförs på en DITA-fil. Följande åtgärder i en DITA-fil utlöser den här händelsen:

- Överför
- Skapa
- Ändra

>[!NOTE]
>
> Händelsen efter bearbetning aktiveras genom att flaggan `fire.processing.events` aktiveras, som är en konfigurationsparameter i `fmdita config manager`. Om värdet är true utlöses händelser (com/adobe/guides/postprocess/complete) för att spåra efterbearbetningen. Som standard är värdet false (inaktiverat).

Du måste skapa en Adobe Experience Manager-händelsehanterare för att kunna läsa de egenskaper som är tillgängliga i den här händelsen och utföra ytterligare bearbetning.

Händelseinformation förklaras nedan:

**Händelsenamn**:

```
com/adobe/guides/postprocess/complete 
```

**Parametrar**:

| Namn | Typ | Beskrivning |
|----|----|-----------|
| `path` | Sträng | Sökvägen till filen som utlöste den här händelsen. Det här är vanligtvis den fil som en åtgärd har utförts på. |
| `eventType` | Sträng | Typ av händelse, dvs. CREATE eller MODIFY. |
| `status` | Sträng | Returstatus för den åtgärd som utfördes. Möjliga alternativ är: <br> - LYCKADES: Efterbehandlingsåtgärden slutfördes utan fel. <br> - MISSLYCKADES: Efterbearbetningen misslyckades på grund av ett fel. |
| `errorMsg` | Sträng | Felmeddelandet om efterbearbetningen misslyckas. |
| `uuid` | Sträng | UUID för filen som utlöste den här händelsen. Det här är vanligtvis den fil som en åtgärd har utförts på. |

**Exempelhändelseavlyssnare**


```
@Component(service = EventHandler.class,
        immediate = true,
        property = {
                EventConstants.EVENT_TOPIC + "=" + "com/adobe/guides/postprocess/complete",
        })
public class PostProcessCompleteEventHandler implements EventHandler {

    protected final Logger log = LoggerFactory.getLogger(this.getClass());

    @Override
    public void handleEvent(final Event event) {
        Set<String> propertyNames = new HashSet<>(Arrays.asList(event.getPropertyNames()));
        Map<String, String> properties = new HashMap<>();
        properties.put("path", (String) event.getProperty("path"));
        properties.put("eventType", (String) event.getProperty("eventType"));
        properties.put("status", (String) event.getProperty("status"));
        if(propertyNames.contains("errorMsg")) {
            properties.put("errorMsg", (String) event.getProperty("errorMsg"));
        }
        if (propertyNames.contains("uuid")) {
            properties.put("uuid", (String) event.getProperty("uuid"));
        }
        String eventTopic = event.getTopic();
        log.debug("eventTopic {}", eventTopic);
        for(Map.Entry entry:properties.entrySet()) {
            log.debug(entry.getKey() + " : " + entry.getValue());
        }
    }
}
```

## Ej UUID


Adobe Experience Manager Guides visar com/adobe/fmdita/postprocess/complete-händelse som används för att utföra eventuella efterbehandlingsåtgärder. Den här händelsen utlöses när en åtgärd utförs på en DITA-fil. Följande åtgärder i en DITA-fil utlöser den här händelsen:

>[!NOTE]
>
> Den här händelsen aktiveras inte för borttagningsåtgärden i AEM 6.1.

- Överför
- Skapande
- Ändring
- Borttagning

Du måste skapa en Adobe Experience Manager-händelsehanterare för att kunna läsa de egenskaper som är tillgängliga i den här händelsen och utföra ytterligare bearbetning.

Händelseinformation förklaras nedan:

**Händelsenamn**:

```
com/adobe/fmdita/postprocess/complete 
```

**Parametrar**:

| Namn | Typ | Beskrivning |
|----|----|-----------|
| `path` | Sträng | Sökvägen till filen som utlöste den här händelsen. Det här är vanligtvis den fil som en åtgärd har utförts på. |
| `status` | Sträng | Returstatus för den åtgärd som utfördes. Möjliga alternativ är: <br> - LYCKADES: Efterbehandlingsåtgärden slutfördes utan fel. <br>- SLUTFÖRD MED FEL: Efterbearbetningen slutfördes men med vissa fel. <br> - MISSLYCKADES: Efterbearbetningen misslyckades på grund av ett fel. |
| `message` | Sträng | Om statusen är SLUTFÖRD MED FEL eller MISSLYCKAD innehåller den här parametern information om felet eller orsaken till felet. |
| `operation` | Sträng | Efterbehandlingsåtgärden som utfördes på filen. Möjliga alternativ är: <br>- Tillägg <br>- Uppdatering <br> - Borttagning |
