---
title: Anpassa Web Editor
description: Lär dig hur du anpassar visningen av inklistrade tabeller i redigeraren
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 834959a6a0e22cd5d2b2c5d0e57ceb6d45c0c666
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 0%

---

# Konfigurera visning av inklistrade tabeller för Cloud Service

Med det sekundära verktygsfältet i redigeraren kan du infoga en enkel tabell på den aktuella eller nästa giltiga platsen för ett ämne. Du kan också kopiera en tabell från Microsoft Word eller Excel och klistra in den direkt i en ämnesfil.

Administratörer kan konfigurera hur kopierade tabeller visas. Som standard visas sådana kopierade tabeller som `simpletable` i redigeraren. Du kan dock ändra den här inställningen så att kopierade tabeller visas som `tgroup` genom att uppdatera konfigurationsinställningen för XML-redigeraren.

>[!NOTE]
>
> Om du kopierar en tabell med sammanfogade rader eller kolumner klistras tabellen in som den normala tabellen `trgoup` och inte `simpletable` oavsett vilken tabellinställning som har konfigurerats i XML-redigerarkonfigurationen.

Så här uppdaterar du standardtabellformatet:

1. Öppna Adobe Experience Manager Navigations-sidan och välj **Tools** till vänster.
2. Välj **Stödlinjer** i listan med verktyg på verktygspanelen.
3. Välj **Mappprofiler** och markera sedan den profil där du vill uppdatera tabellinställningen.
4. Gå till fliken **XML-redigerarkonfiguration**.
5. Välj ikonen **Redigera** längst upp.
6. Välj ikonen **Hämta** om du vill hämta filen `ui_config.json` på din lokala dator.
7. Uppdatera inställningen för `ui_config.json` i filen `simpletable` enligt nedan:

   ```
   "htmlToDitaMapping":{ "table": {
   "name" : "tgroup",
   "wrapTag" : {
       "dita" : "table",
       "html" : "div"
   }
   } },
   ```


När filen har uppdaterats sparar du den och överför den.
