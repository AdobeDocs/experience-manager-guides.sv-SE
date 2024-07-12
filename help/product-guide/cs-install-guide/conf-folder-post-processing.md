---
title: Konfigurera filnamn
description: Lär dig hur du inaktiverar efterbearbetning för en mapp som har överförts till Adobe Experience Manager Assets
feature: Filename Configuration
role: Admin
level: Experienced
exl-id: 42722c6f-1b1c-4a7e-89ef-a373623eb774
source-git-commit: 5d99274da8fdacbd255d426fa4913b5773ca45f8
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 0%

---

# Inaktivera efterbearbetning för en mapp

Som standard bearbetas alla överförda resurser med arbetsflödet DAM-uppdatering. Experience Manager Guides kör ytterligare en bearbetning, som kallas efterbearbetning, som en del av det här arbetsflödet. Detta hjälper även till att generera UUID

När du överför filer och mappar till *Adobe Experience Manager Assets*-servern kan du även inaktivera efterbearbetningen och genereringen av UUID:n.


Använd instruktionerna i [Konfigurationsåsidosättningar](download-install-additional-config-override.md#) för att skapa konfigurationsfilen. Ange följande (egenskap) information i konfigurationsfilen för att inaktivera efterbearbetningen på en viss sökväg eller ignorera efterbearbetningen för en mapp:

| PID | Egenskapsnyckel | Egenskapsvärde |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `ignored.post.processing.paths` | Strängvärde för att ange valfri NODE_OPTIONS-standard (flervärdesegenskap, strängar med sökväg som utelämnar `/` i slutet) <br> **Standardvärde**: `/content/dam/projects/translation_output` |


| PID | Egenskapsnyckel | Egenskapsvärde |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `enabled.post.processing.paths` | Strängvärde för att ange valfri NODE_OPTIONS-standard (flervärdesegenskap, strängar med sökväg som utelämnar `/` i slutet) <br> **Standardvärde**: `/content/dam` |


## Regler för att aktivera eller inaktivera efterbearbetning

Som standard utförs efterbearbetning för alla mappsökvägar under Experience Manager DAM-mappen. Konfigurationer används för alla mappar enligt följande regler:

* Om den överordnade mappen ignoreras för efterbearbetning men den underordnade mappen är aktiverad, anses den underordnade mappen och alla dess efterföljande vara aktiverade.
* Om det överordnade objektet är aktiverat för efterbearbetning men det underordnade objektet ignoreras, kommer det underordnade objektet och alla dess efterföljande att ignoreras.
* Om samma mappsökväg finns i konfigurationerna ignore.post.processing.paths och enabled.post.processing.paths ignoreras den för efterbearbetning.
