---
title: Versionsinformation | Nyheter i Adobe Experience Manager Guides 2024.10.0
description: Läs om de nya och förbättrade funktionerna i version 2024.10.0 av Adobe Experience Manager Guides
role: Leader
source-git-commit: 545e51cbd970aa3df01a0fe2461a2e730c0db66a
workflow-type: tm+mt
source-wordcount: '1025'
ht-degree: 0%

---

# Nyheter i version 2024.10.0 (oktober 2024)

I den här artikeln beskrivs de nya och förbättrade funktionerna som introducerades i version 2024.10.0 av Adobe Experience Manager Guides as a Cloud Service.

En lista över problem som har åtgärdats i den här versionen finns i [Åtgärdade problem i version 2024.10.0](fixed-issues-2024-10-0.md).

Läs mer om [uppgraderingsinstruktioner för version 2024.10.0](../release-info/upgrade-instructions-2024-10-0.md).


## Förbättrad publicering

Följande förbättringar av innehållspublicering har gjorts i version 2024.10.0:




### Förbättringar i Content Fragment-publiceringen

Experience Manager Guides har även några praktiska förbättringar i Content Fragments:

- Med Experience Manager Guides kan du publicera ett ämne eller dess element i ett innehållsfragment.

- Du kan publicera och visa innehållsfragment för ett ämne i avsnittet **Utdata** i **Filegenskaper**.


- Du kan enkelt skapa varianter av innehållsfragment genom att filtrera innehåll med villkor när du publicerar till ett innehållsfragment.

- Använd det nya mappningsgränssnittet för att enkelt markera och publicera elementen i ett innehållsfragment.

Nu ersätter Content Fragment-publicering bara det mappade innehållet i stället för att skriva över hela innehållsfragmentet. Med den här funktionen kan ett innehållsfragment innehålla data från flera källor, till exempel flera ämnen eller innehållsfragmentets redigerare.

![Lägg till fragmentmodellen och mappningsinformation i dialogrutan Publish som innehållsfragment](assets/content-fragment-mapping.png)

Mer information finns i [Publish Content Fragments](../user-guide/publish-content-fragment.md).


### Publish Experience Fragment-varianter baserade på villkorsfilter

Med Experience Manager Guides kan du publicera ett ämne eller dess element i ett Experience Fragment. Nu kan ni också skapa Experience Fragment-varianter genom att använda villkor- eller DITAVAL-filter och återanvända dem i olika kanaler eller för olika målgrupper.

Läs mer om hur du [Publish Experience Fragments](../user-guide/publish-experience-fragment.md).


### AEM Sites förinställning har omorganiserats för att bli enkel att använda

Inställningarna har organiserats om för att du snabbt ska kunna konfigurera förinställningarna och generera utdata från AEM Sites.
Du kan skapa de befintliga förinställningarna för AEM Sites genom att välja alternativet **Använd äldre komponentmappning** i dialogrutan **Ny förinställning** .

Visa flikarna **Allmänt**, **Innehåll** och **Korsmappsreferens** i AEM Sites-förinställningarna:
- **Allmänt**: Innehåller allmänna konfigurationer för att generera utdata. Du kan ange plats- och utdatasökväg, ta bort eller skriva över befintliga utdatasidor, ta bort tidigare genererade sidor för borttagna ämnen, välja designmallen, behålla de tillfälliga filerna och ange arbetsflödet efter genereringen.
- **Innehåll**: Innehåller de inställningar som gäller för innehållet för utdatagenerering. Du kan välja filter, baslinje för DITA-kartan och metadataegenskaper för publicering.
- **Tvärmappningsreferenser**: Den här listan innehåller ämnen som innehåller korsmappningsreferenser med scope =&quot;peer&quot;. Du kan ange publiceringskontext för en lista över korsmappsreferenser med scope=&quot;peer&quot; för ämnen som finns i andra DITA-kartor. Den här fliken visas om du använder Experience Manager Guides-versionen (UUID).



### Korsmappsreferenser från AEM Sites-förinställningar i Web Editor

Den senaste förbättringen av Experience Manager Guides innehåller korsmappsreferenser i AEM Sites-förinställningarna i Web Editor.
Korsmappsreferenser i Experience Manager Guides hjälper till att förbättra innehållsnavigeringen, öka återanvändningen av innehåll och förbättra användarupplevelsen.


Du kan ange publiceringskontext för en lista med korsmappningsreferenser till ämnen som är tillgängliga i andra DITA-kartor med scope=&quot;peer&quot;. Ämne 1 i karta A innehåller till exempel en referens till ämne 2. Ämne 2 kan finnas på en eller flera kartor.  Du kan välja den överordnade kartan och en viss förinställning eller de senast publicerade utdata för varje länk.

Om samma ämne refereras till mer än en gång i en fil kan du lägga till olika publiceringskontexter för varje instans. Detta ger större flexibilitet och kontroll över innehållet. Ämne 3 finns t.ex. i både karta B och karta C. Ämne 1 innehåller två referenser till avsnitt 3. Du kan välja Map B som överordnad karta för den första länken och Map C som överordnad för den andra länken.

![Äldre AEM Sites-förinställning](assets/aem-sites-legacy.png)

*Ange publiceringskontext för de länkade avsnitten på fliken **Korsmappningsreferenser**i **AEM Sites**-förinställningen.*

Läs mer om [AEM Sites-förinställningar](../user-guide/generate-output-aem-site.md).

### Alternativ för att antingen välja en platt eller kapslad filhierarki för utdata från HTML5

Nu kan du använda Experience Manager Guides för att behålla den platta mapphierarkin för temporära filer där hela innehållet publiceras i utdataformatet HTML 5 och sparas i en enda mapp.
Om du inte väljer att förenkla filhierarkin skapas utdata från HTML5 i en kapslad mapphierarki. Detta innebär att innehållets ursprungliga mappstruktur, med filer ordnade i undermappar, replikeras i utdata. Den här kapslade mapphierarkin gör det enklare att hantera och navigera i stora datavolymer och det blir därför enklare att ordna och kategorisera filer.


Läs mer om hur du [genererar HTML5-utdata](../user-guide/generate-output-html5.md).


## Förbättringar i redigeraren

Följande redigeringsförbättringar har lagts till i version 2024.10.0:

### Skrivskyddad åtkomst till redigerings- och Source-läge för låsta filer

Om en DITA- eller Markdown-fil är låst eller utcheckad av en annan användare kan du inte redigera eller ändra innehållet. Förutom Förhandsgranska kan du även visa den som en skrivskyddad fil i redigeringsläge eller Source-läge.
I skrivskyddat läge kan du visa innehållet tillsammans med taggarna och attributen i **författarläget** eller **Source** och redigera filegenskaperna.

Du kan även komma åt vyn **Layout** för skrivskyddade DITA-kartor.
>[!NOTE]
>
> Mappprofiladministratörerna måste uppdatera *ui_config.json* så att du kan komma åt de skrivskyddade filerna i redigeringsläget, Source- och layoutläget.

![låst filredigerare](./assets/locked-file-editor.png)
*Visa låsta filer i redigeringsläge och Source-läge.*


Lär dig hur du [öppnar låsta filer i redigeringsläge och Source-läge](../user-guide/web-editor-edit-topics.md#open-locked-files-in-author-and-source-modes).


### Grupperade villkor för förbättrad innehållsorganisation

I Experience Manager Guides kan du nu gruppera villkor och presentera dem i en kapslad hierarki, så att du kan lägga till flera villkor i en enda grupp. Genom att gruppera villkor kan du bättre ordna och använda dem i hela innehållet.

![villkor ordnade i en kapslad hierarki](assets/conditions-nested-hierarchy.png){width="300" align="left"}

Läs mer om funktionsbeskrivningen för **Villkor** i avsnittet [Vänster panel](../user-guide/web-editor-features.md#id2051EA0M0HS).




