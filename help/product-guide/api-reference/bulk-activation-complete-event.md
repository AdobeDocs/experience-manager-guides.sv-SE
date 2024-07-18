---
title: Händelsehanterare för slutförd gruppaktivering
description: Läs om händelsehanterare för massaktivering
feature: Bulk Activation Event Handler
role: Developer
level: Experienced
exl-id: 08b153d7-3d13-4804-9e3e-38790dbea1f3
source-git-commit: 9b8971bf7065a94a2e42669094249c822c555718
workflow-type: tm+mt
source-wordcount: '185'
ht-degree: 0%

---

# Händelsehanterare för slutförd gruppaktivering

Experience Manager Guides visar `com/adobe/fmdita/replication/complete`-händelse som används för att utföra åtgärder efter att en gruppaktiveringsprocess har slutförts. Den här händelsen utlöses när en gruppaktiveringsprocess slutförs. Om du t.ex. kör gruppaktiveringen av en förinställning för AEM plats för en karta anropas den här händelsen när aktiveringsprocessen har avslutats.

Du måste skapa en AEM händelsehanterare för att kunna läsa de egenskaper som är tillgängliga i den här händelsen och utföra ytterligare bearbetning.

Händelseinformation förklaras nedan:

**Händelsenamn**:

```
com/adobe/fmdita/replication/complete 
```

**Parametrar**:

| Namn | Typ | Beskrivning |
|----|----|-----------|
| `path` | Sträng | Sökvägen till filen som utlöste den här händelsen. <br>, till exempel `/content/output/sites/ditamap1-ditamap`. <br> Det är en lista med sökvägar som har serialiserats som en JSON-array. |
| `messageType` | Sträng | Meddelandets typ. <br>Möjligt alternativ: `REPLICATION` |
| `action` | Sträng | Detta är den åtgärd som utfördes. <br>Möjligt alternativ: `BulkReplicate` |
| `user` | Sträng | Användaren som startade åtgärden. |
| `result` | Sträng | Resultatet av gruppaktiveringen. Det är ett serialiserat JSON-objekt: <br>`{"success":boolean,"code":integer,"message":"" }` |
| `agentId` | Sträng | AgentId som används i replikeringen. Exempel: `"publish"`. |
| `importMode` | Sträng | Det importläge som används i aktiveringen. Möjliga alternativ är: <br>`REPLACE, MERGE, UPDATE`. |


**Exempelhändelseavlyssnare**:

```XML
@Component(service = EventHandler.class,
        immediate = true,
        property = {
                EventConstants.EVENT_TOPIC + "=" + "com/adobe/fmdita/replication/complete",
        })
 
public class SampleEventHandler implements EventHandler {
 
    protected final Logger log = LoggerFactory.getLogger(this.getClass());
 
    @Override
    public void handleEvent(final Event event) {
        Map<String, String> properties = new HashMap<>();
        properties.put("paths", (String) event.getProperty("paths"));
        properties.put("messageType", (String) event.getProperty("messageType"));
        properties.put("action", (String) event.getProperty("action"));
        properties.put("result", (String) event.getProperty("result"));
        properties.put("user", (String) event.getProperty("user"));
        properties.put("agentId", (String) event.getProperty("agentId"));
        properties.put("importMode", (String) event.getProperty("importMode"));
 
        String eventTopic = event.getTopic();
        log.debug("eventTopic {}", eventTopic);
        for(Map.Entry entry:properties.entrySet()) {
            log.debug(entry.getKey() + " : " + entry.getValue());
        }
 
    }
}
```
