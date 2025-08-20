---
title: Versionsinformation | Nyheter i Adobe Experience Manager Guides 2025.06.0
description: Läs om de nya och förbättrade funktionerna i version 2025.06.0 av Adobe Experience Manager Guides
role: Leader
exl-id: 48f27aa6-d870-4228-8e62-db81699a25f7
source-git-commit: d418ffb254b11430509609b91e0174690815cf73
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 0%

---

# Nyheter i version 2025.06.0 (juni 2025)

I den här artikeln beskrivs de nya och förbättrade funktionerna som introducerades i version 2025.06.0 av Adobe Experience Manager Guides as a Cloud Service.

En lista över problem som har åtgärdats i den här versionen finns i [Åtgärdade problem i version 2025.06.0](fixed-issues-2025-06-0.md).

Läs mer om [uppgraderingsinstruktioner för version 2025.06.0](../release-info/upgrade-instructions-2025-06-0.md).

## Sessionstidsfråga för att förhindra oavsiktlig innehållsförlust

Ett popup-meddelande meddelar dig nu när din Adobe Experience Manager-session upphör att gälla och du är utloggad på grund av inaktivitet. Det här meddelandet utlöses när du försöker redigera innehåll i Experience Manager Guides efter att sessionen har avslutats. Funktionen minskar risken för att förlora osparat arbete och förbättrar den övergripande tillförlitligheten och flödet i upplevelsen, även under inaktivitetsperioder.

![](assets/sign-out-prompt.png)

Läs mer om [timeout-fråga för sessioner](../user-guide/session-timeout-prompt.md) i Experience Manager Guides.

## Förbättrade hämtningsalternativ för kartor i Redigeraren

Experience Manager Guides introducerar ett nytt **Använd faktiska filnamn**-alternativ i dialogrutan **Hämta karta**. När du laddar ned kartfiler kan du nu välja att behålla originalfilnamnen i stället för standard-UID:n, vilket gör det mycket enklare att identifiera och hantera filerna. Det här alternativet är bara tillgängligt om du väljer **Behåll filhierarkin** och är inaktiverat när du väljer **Förenkla filhierarkin**, vilket ger dig större flexibilitet när du ordnar dina hämtade kartor.

Mer information finns i [Hämta filer](../user-guide/authoring-download-assets.md#download-a-dita-map-file-from-the-editor).

![](assets/download-map-dialog-new.png){width="300" align="left"}


## Förbättrad `navref`-hantering i redigeraren

De senaste förbättringarna av redigeraren förbättrar hanteringen av `navref` element i en DITA-karta. När du lägger till ett `navref`-element på en karta öppnas dialogrutan **Välj sökväg** så att du enkelt kan välja vilka kartreferenser som ska inkluderas som navigeringslänkar på kartan. När du har lagt till titeln för den tillagda kartan visas den i både redigeringsvyn och layoutvyn, vilket ger bättre synlighet för den inkluderade navigeringen vid redigering.  Dessutom tolkas det tillagda `navref`-elementet automatiskt så att den refererade kartan visas i redigeraren.

Mer information finns i [Lägg till navigeringsreferenser](../user-guide/map-editor-other-features.md#add-navigation-references).

## Prestandaförbättringar i AI Assistant

I den här versionen har AI Assistant-motorn förbättrats, vilket ger bättre prestanda och större stabilitet. Om du vill aktivera den här uppdateringen och fortsätta använda hjälpen för AI Assistant:

- Uppdatera `chat.url`-konfigurationen så att den återspeglar den nya slutpunkts-URL:en.
- Lägg till en ny miljövariabel `GUIDES_AI_SITE_ID` i Cloud Manager.

Mer information finns i [Konfigurera AI-assistenten](../cs-install-guide/conf-smart-suggestions.md).

