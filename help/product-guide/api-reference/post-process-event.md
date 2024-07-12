---
title: Händelsehanterare för Post-bearbetning
description: Läs om händelsehanteraren i Post-bearbetning
exl-id: 3b105ff5-02d4-40e3-a713-206a7fcf18b2
feature: Post-Processing Event Handler
role: Developer
level: Experienced
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 0%

---

# Händelsehanterare för Post-bearbetning {#id175UB30E05Z}

AEM Guides visar com/adobe/fmdita/postprocess/complete-händelse som används för att utföra eventuella efterbehandlingsåtgärder. Den här händelsen utlöses när en åtgärd utförs på en DITA-fil. Följande åtgärder i en DITA-fil utlöser den här händelsen:

>[!NOTE]
>
> Den här händelsen aktiveras inte för borttagningsåtgärden i AEM 6.1.

- Överför
- Skapande
- Ändring
- Borttagning

Du måste skapa en AEM händelsehanterare för att kunna läsa de egenskaper som är tillgängliga i den här händelsen och utföra ytterligare bearbetning.

Händelseinformation förklaras nedan:

**Händelsenamn**:

```
com/adobe/fmdita/postprocess/complete 
```

**Parametrar**:
|Namn|Typ|Beskrivning|
|—|—|—|
|`path`|String|Sökvägen till filen som utlöste den här händelsen. Det här är vanligtvis den fil som en åtgärd har utförts på.|
|`status`|Sträng|Returstatus för den åtgärd som utfördes. Möjliga alternativ är: - <br> - LYCKADES: Efterbehandlingsåtgärden slutfördes utan fel. <br>- SLUTFÖRD MED FEL: Efterbearbetningen slutfördes men med vissa fel. <br> - MISSLYCKADES: Efterbearbetningen misslyckades på grund av ett allvarligt fel.|
|`message`|Sträng|Om statusen ÄR SLUTFÖRD MED FEL eller MISSLYCKAD innehåller den här parametern information om felet eller orsaken till felet.|
|`operation`|Sträng|Efterbearbetningen av filen utfördes. Möjliga alternativ är: <br>- Tillägg <br>- Uppdatering <br> - Borttagning|
