---
title: Konfigurera filnamn
description: Lär dig hur du inaktiverar efterbearbetning för en mapp som har överförts till Adobe Experience Manager Assets
feature: Filename Configuration
role: Admin
level: Experienced
exl-id: 42722c6f-1b1c-4a7e-89ef-a373623eb774
source-git-commit: 635206ca34db633a998b0156e2549d86a83f8131
workflow-type: tm+mt
source-wordcount: '574'
ht-degree: 0%

---

# Inaktivera efterbearbetning för en mapp

Som standard bearbetas alla överförda resurser med arbetsflödet DAM-uppdatering. Experience Manager Guides kör ytterligare en bearbetning, som kallas efterbearbetning, som en del av det här arbetsflödet. Detta hjälper även till att generera UUID

När du överför filer och mappar till *Adobe Experience Manager Assets*-servern kan du även inaktivera efterbearbetningen och genereringen av UUID:n.

Använd instruktionerna i [Konfigurationsåsidosättningar](download-install-additional-config-override.md#) för att skapa konfigurationsfilen. Ange följande (egenskap) information i konfigurationsfilen för att inaktivera efterbearbetningen på en viss sökväg eller ignorera efterbearbetningen för en mapp:

>[!NOTE]
>
> Du kan också använda reguljära uttryck (regex) för att definiera regler som gäller för flera mappar eller en hel mapphierarki. Mer information finns i avsnittet [Använd regex för att aktivera eller inaktivera efterbearbetning](#use-regex-to-enable-or-disable-post-processing).

| PID | Egenskapsnyckel | Egenskapsvärde |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `ignored.post.processing.paths` | Strängvärde för att ange valfri NODE_OPTIONS-standard (flervärdesegenskap, strängar med sökväg som utelämnar `/` i slutet eller regex) <br> **Standardvärde**: `/content/dam/projects/translation_output` |

| PID | Egenskapsnyckel | Egenskapsvärde |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `enabled.post.processing.paths` | Strängvärde för att ange valfri NODE_OPTIONS-standard (flervärdesegenskap, strängar med sökväg som utelämnar `/` i slutet eller regex) <br> **Standardvärde**: `/content/dam` |

## Regler för att aktivera eller inaktivera efterbearbetning

Som standard utförs efterbearbetning för alla mappsökvägar i Experience Manager DAM-mappen. Konfigurationer används för alla mappar enligt följande regler:

* Om den överordnade mappen ignoreras för efterbearbetning men den underordnade mappen är aktiverad, anses den underordnade mappen och alla dess efterföljande vara aktiverade.
* Om det överordnade objektet är aktiverat för efterbearbetning men det underordnade objektet ignoreras, kommer det underordnade objektet och alla dess efterföljande att ignoreras.
* Om samma mappsökväg finns i både `ignored.post.processing.paths`- och `enabled.post.processing.paths`-konfigurationer kommer den att ignoreras för efterbearbetning.

## Använd regex för att aktivera eller inaktivera efterbearbetning

I stället för att ange enskilda mappsökvägar kan du använda reguljära uttryck (regex) för att definiera regler som gäller för flera mappar eller hela mapphierarkier.

Regex-mönster utvärderas mot den fullständiga resurssökvägen under efterbearbetningen.

När reguljära uttryck (regex) används för att konfigurera ignorerade och aktiverade efterbearbetningssökvägar utvärderar AEM Guides båda konfigurationerna mot resurssökvägen. Om en sökväg matchar både en ignoreringsregel och en aktiveringsregel har ignoreringsreglerna alltid företräde.

Följande exempel visar hur regex-baserade regler för ignorering och aktivering utvärderas.

## Regex-utvärderingsscenarier för efterbearbetning

### Ignorera överordnad hierarki, aktivera specifik mapp

**Ignorera regex**

`regex:/content/dam/lang-test/.*`

**Aktivera regex**

`regex:/content/dam/lang-test/.*/parent1`

I exemplet ovan inaktiveras efterbearbetning för `/content/dam/lang-test/en/parent1`.

Även om sökvägen matchar den aktiverade regex, matchas den redan av den ignorerade regex. Ignorera regler har företräde, så efterbearbetning är inte aktiverat.

### Ignorera en specifik mapp, aktivera en bredare hierarki

**Ignorera regex**

`regex:/content/dam/lang-test/.*/parent1`

**Aktivera regex**

`regex:/content/dam/lang-test/.*`

I exemplet ovan inaktiveras efterbearbetning för `/content/dam/lang-test/en/parent1` och aktiveras för `/content/dam/lang-test/en/parent2`.

Sökvägen `parent1` ignoreras explicit och är fortfarande inaktiverad. Andra mappar som bara matchar aktiveringsregex bearbetas.

### Ignorera överordnad mapp, aktivera en underordnad mapp

**Ignorera regex**

`regex:/content/dam/lang-test/.*/parent1`

**Aktivera regex**

`regex:/content/dam/lang-test/.*/parent1/child1`

I ovanstående exempel inaktiveras efterbearbetning för `/content/dam/lang-test/en/parent1` och `/content/dam/lang-test/en/parent1/child2` och aktiveras för `/content/dam/lang-test/en/parent1/child1`.

Den underordnade mappen som uttryckligen aktiveras av regex bearbetas. Andra underordnade mappar förblir inaktiverade eftersom deras överordnade sökväg matchar ignoreringsregex.

### Ignorera specifik underordnad mapp, aktivera överordnad hierarki

**Ignorera regex**

`regex:/content/dam/lang-test/.*/parent1/child1`

**Aktivera regex**

`regex:/content/dam/lang-test/.*/parent1`

I ovanstående exempel inaktiveras efterbearbetning för `/content/dam/lang-test/en/parent1/child1` och aktiveras för `/content/dam/lang-test/en/parent1` och `/content/dam/lang-test/en/parent1/child2`.

Endast den uttryckligen ignorerade undermappen hoppas över. Den överordnade mappen och andra underordnade mappar bearbetas eftersom de matchar den aktiverade regionen och inte matchar den ignorerade regionen.

