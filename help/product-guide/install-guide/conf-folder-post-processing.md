---
title: Konfigurera filnamn
description: Lär dig hur du inaktiverar efterbearbetning för en mapp som har överförts till Adobe Experience Manager Assets
feature: Filename Configuration
role: Admin
level: Experienced
source-git-commit: 532e7c562a233619a8c4b7cbdbaef44bc73eb4b2
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 0%

---


# Inaktivera efterbearbetning för en mapp

Som standard bearbetas alla överförda resurser med arbetsflödet DAM-uppdatering. Experience Manager Guides kör ytterligare en bearbetning, som kallas efterbearbetning, som en del av det här arbetsflödet. Detta hjälper även till att generera UUID

När du överför filer och mappar till *Adobe Experience Manager Assets* kan du även inaktivera efterbearbetning och generering av UUID:n.


Utför följande steg för att inaktivera efterbearbetningen på en viss sökväg eller ignorera efterbearbetningen för en mapp:


1. Öppna konfigurationssidan för Adobe Experience Manager Web Console.

   Standardwebbadressen för åtkomst till konfigurationssidan är:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Sök efter och klicka på **com.adobe.fmdita.config.ConfigManager** paket.

1. Välj **Ignorerade sökvägar för efterbearbetning** om du vill ignorera en mapp för efterbearbetning.

   Strängvärde för att ange valfri NODE_OPTIONS-standard (flervärdesegenskap, strängar med sökväg som utelämnas) `/` i slutet)

   **Standardvärde**: `/content/dam/projects/translation_output`

   >[!NOTE]
   >
   > Den här egenskapen är inaktiverad som standard och översättningsfliken är tillgänglig på kartkontrollpanelen.

1. Välj **Aktiverade sökvägar för efterbearbetning** om du vill aktivera en sökväg för efterbearbetning.

   Strängvärde för att ange valfri NODE_OPTIONS-standard (flervärdesegenskap, strängar med sökväg som utelämnas) `/` i slutet)

   **Standardvärde**: `/content/dam/`

   >[!NOTE]
   >
   > Den här egenskapen är inaktiverad som standard och översättningsfliken är tillgänglig på kartkontrollpanelen.


1. Klicka **Spara**.



## Regler för att aktivera eller inaktivera efterbearbetning

Som standard utförs efterbearbetning för alla mappsökvägar under Experience Manager DAM-mappen. Konfigurationer används för alla mappar enligt följande regler:

* Om den överordnade mappen ignoreras för efterbearbetning men den underordnade mappen är aktiverad, anses den underordnade mappen och alla dess efterföljande vara aktiverade.
* Om det överordnade objektet är aktiverat för efterbearbetning men det underordnade objektet ignoreras, kommer det underordnade objektet och alla dess efterföljande att ignoreras.
* Om samma mappsökväg finns i konfigurationerna ignore.post.processing.paths och enabled.post.processing.paths ignoreras den för efterbearbetning.
