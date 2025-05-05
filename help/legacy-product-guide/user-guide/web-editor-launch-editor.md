---
title: Starta Web Editor
description: Lär dig hur du startar webbredigeraren från AEM Navigation Page, AEM Assets UI och DITA map Console i AEM Guides.
feature: Authoring, Web Editor
role: User
hide: true
exl-id: 374042e4-0f1c-44cf-926c-c9fefa4b1de0
source-git-commit: ea597cd14469f21e197c700542b9be7c373aef14
workflow-type: tm+mt
source-wordcount: '590'
ht-degree: 0%

---

# Starta Web Editor {#id2056B0140HS}

Du kan starta Web Editor från följande platser:

- [AEM Navigation page](#id2056BG00RZJ)
- [AEM Assets UI](#id2056BG0307U)
- [DITA map console](#id2056BG090BF)

I följande avsnitt beskrivs hur du kommer åt och startar webbredigeraren från olika platser.

## AEM Navigation page {#id2056BG00RZJ}

När du loggar in i AEM visas navigeringssidan:

![](images/web-editor-from-navigation-page.png){width="800" align="left"}

Om du klickar på länken **Stödlinjer** dirigeras du direkt till webbredigeraren.

![](images/web-editor-launch-page.png){width="800" align="left"}

När du har startat webbredigeraren utan att välja någon fil visas en tom webbredigeringsskärm. Du kan öppna en fil för redigering från AEM-databasen eller din Favoriter-samling.

- Klicka på ikonen **Stödlinjer** (![](images/aem-guides-icon.png) ) för att gå tillbaka till AEM navigeringssida.

- Knappen **Stäng** tar dig till ett mål baserat på dina inställningar:



  <details>

  <summary> Molntjänster </summary>

  Om du använder molntjänster klickar du på knappen **Stäng** för att gå tillbaka till AEM navigeringssida.
  </details>

  <details>

  <summary> Lokal programvara</summary>

  Om du använder AEM Guides On-Local Software (4.2.1 och senare) klickar du på knappen **Close** till höger för att gå tillbaka till den aktuella filsökvägen i Assets-gränssnittet.

  </details>

## AEM Assets UI {#id2056BG0307U}

En annan plats där du kan starta Web Editor är från AEM Assets-gränssnittet. Du kan markera ett eller flera ämnen och öppna dem direkt i Web Editor. Så här öppnar du ett ämne i Web Editor:

1. Gå till det avsnitt du vill redigera i användargränssnittet för Assets.

   >[!NOTE]
   >
   > Du kan också se Ämnets UUID.

   .

   ![](images/assets_ui_with_uuid_cs.png){width="800" align="left"}

   >[!IMPORTANT]
   >
   > Kontrollera att du har läs- och skrivbehörighet för mappen som innehåller det ämne som du vill redigera.

1. Om du vill låsa ämnet exklusivt markerar du ämnet och klickar på **Checka ut**.

   >[!IMPORTANT]
   >
   > Om administratören har konfigurerat alternativet **Inaktivera redigering utan utcheckning** måste du checka ut filen innan du redigerar. Om du inte checkar ut filen kan du inte se redigeringsalternativet.

1. Stäng resursurvalsläget och klicka på det ämne som du vill redigera.

   Ämnets förhandsgranskning visas.

   Du kan öppna Web Editor från listvyn, kortvyn och förhandsgranskningsläget.

   >[!IMPORTANT]
   >
   > Om du vill öppna flera ämnen för redigering väljer du önskade ämnen i resursgränssnittet och klickar på Redigera. Kontrollera att webbläsaren inte har aktiverat popup-blockering, annars öppnas bara det första avsnittet i den markerade listan för redigering.

   ![](images/edit-from-preview_cs.png){width="800" align="left"}

   Om du inte vill förhandsgranska ett ämne och vill öppna det direkt i Web Editor klickar du på ikonen Redigera på snabbmenyn i kortvyn:

   ![](images/edit-topic-from-quick-action_cs.png){width="800" align="left"}

1. Klicka på **Redigera** för att öppna ämnet i webbredigeraren.

   ![](images/edit-mode.png){width="800" align="left"}


## DITA map console {#id2056BG090BF}

Så här öppnar du Web Editor från DITA-kartkonsolen:

1. Navigera till och klicka på DITA-kartfilen som innehåller det avsnitt du vill redigera i Assets-användargränssnittet.

   DITA-kartkonsolen visas.

1. Klicka på **Ämnen**.

   En lista med ämnen i kartfilen visas. UUID för ämnen visas under ämnesrubriken.

1. Markera ämnesfilen som du vill redigera.

1. Klicka på **Redigera ämne**.

   ![](images/edit-topics-map-console_cs.png){width="800" align="left"}

1. Ämnet öppnas i webbredigeraren.

   >[!IMPORTANT]
   >
   > Om administratören har konfigurerat alternativet **Inaktivera redigering utan utcheckning** måste du checka ut filen innan du redigerar. Om du inte checkar ut filen öppnas dokumentet i redigeraren i skrivskyddat läge.


**Överordnat ämne:**&#x200B;[ Arbeta med webbredigeraren](web-editor.md)
