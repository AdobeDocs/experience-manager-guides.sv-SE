---
title: Konfigurera filnamn
description: Lär dig hur du inaktiverar efterbearbetning för en mapp som har överförts till Adobe Experience Manager Assets
feature: Filename Configuration
role: Admin
level: Experienced
exl-id: ff6e1322-9655-42aa-b353-199c70c9de49
source-git-commit: e84a00237e61275c6cd1ddd312883ac4f66b65ff
workflow-type: tm+mt
source-wordcount: '394'
ht-degree: 0%

---

# Inaktivera efterbearbetning för en mapp

Som standard bearbetas alla överförda resurser med arbetsflödet DAM-uppdatering. Experience Manager Guides kör ytterligare en bearbetning, som kallas efterbearbetning, som en del av det här arbetsflödet. Detta hjälper även till att generera UUID:n.

När du överför filer och mappar till *Adobe Experience Manager Assets*-servern kan du även inaktivera efterbearbetningen och genereringen av UUID:n.


Utför följande steg för att inaktivera efterbearbetningen på en viss sökväg eller ignorera efterbearbetningen för en mapp:


1. Öppna konfigurationssidan för Adobe Experience Manager Web Console.

   Standardwebbadressen för åtkomst till konfigurationssidan är:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Sök efter och klicka på paketet **com.adobe.fmdita.config.ConfigManager**.

1. Markera alternativet **Ignorerade sökvägar för efterbearbetning** om du vill ignorera en mapp för efterbearbetning.

   Strängvärde för att ange valfri NODE_OPTIONS-standard (flervärdesegenskap, strängar med sökväg som utelämnar `/` i slutet)

   **Standardvärde**: `/content/dam/projects/translation_output`

   >[!NOTE]
   >
   > Den här egenskapen är inaktiverad som standard och översättningsfliken är tillgänglig på kartkontrollpanelen.

1. Markera alternativet **Aktiverade sökvägar för efterbearbetning** om du vill aktivera en sökväg för efterbearbetning.

   Strängvärde för att ange valfri NODE_OPTIONS-standard (flervärdesegenskap, strängar med sökväg som utelämnar `/` i slutet)

   **Standardvärde**: `/content/dam/`

   >[!NOTE]
   >
   > Den här egenskapen är inaktiverad som standard och översättningsfliken är tillgänglig på kartkontrollpanelen.


1. Klicka på **Spara**.

>[!NOTE]
>
> Förutom de ignorerade och aktiverade sökvägarna som konfigurerats via OSGi-konfigurationen påverkas även efterbearbetningsbeteendet av en databasnivånod på `/var/dxml/postprocess/ignoredPaths`. <br> Om en mapp oväntat har uteslutits från efterbearbetning och inte finns med i OSGi-konfigurationen bör du kontrollera den här databasnoden. Om sökvägen visas där och är inställd på `true` ignoreras den. Om du vill återaktivera bearbetning kan du ta bort motsvarande egenskap manuellt från noden.

## Regler för att aktivera eller inaktivera efterbearbetning

Som standard utförs efterbearbetning för alla mappsökvägar i Experience Manager DAM-mappen. Konfigurationer används för alla mappar enligt följande regler:

* Om den överordnade mappen ignoreras för efterbearbetning men den underordnade mappen är aktiverad, anses den underordnade mappen och alla dess efterföljande vara aktiverade.
* Om det överordnade objektet är aktiverat för efterbearbetning men det underordnade objektet ignoreras, kommer det underordnade objektet och alla dess efterföljande att ignoreras.
* Om samma mappsökväg finns i konfigurationerna ignore.post.processing.paths och enabled.post.processing.paths ignoreras den för efterbearbetning.
