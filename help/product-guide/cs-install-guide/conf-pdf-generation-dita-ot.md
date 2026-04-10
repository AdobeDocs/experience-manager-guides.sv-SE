---
title: Konfigurera generering av enskilda ämnen i PDF
description: Lär dig hur du konfigurerar generering av enskilda ämnen i PDF
exl-id: 5b66fd3b-6450-49ce-b06e-d2d5bab37990
feature: Web Editor Configuration
role: Admin
level: Experienced
hidefromtoc: true
source-git-commit: 564ee1731be2378744ffd2ed54a2fd423901a0b3
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 0%

---

# Konfigurera generering av enskilda ämnen i PDF {#id22ADC70M0XA}

Med AEM Guides kan du generera PDF för enskilda ämnen eller en hel kartfil. Du kan publicera dina ämnen i ett PDF-format med PDF- eller DITA-OT-metoder. Använd den inbyggda PDF-metoden för att generera funktionsrika PDF-utdata baserade på W3C CSS3 och CSS-sidindelad mediestandard. Du kan använda metoden DITA-OT för att generera PDF-utdata för en karta från kontrollpanelen för kartan.

>[!NOTE]
>
> PDF är standardmetoden för att generera en PDF i den aktuella versionen av AEM Guides.

Så här aktiverar du den gamla PDF-generationen via DITA-OT i läget för ämnesförhandsgranskning:

1. Logga in på Adobe Experience Manager som administratör och hämta UI-konfigurationsfilen.

1. Det gör du genom att klicka på länken Adobe Experience Manager överst och välja **Verktyg**.
1. Välj **Stödlinjer** i listan över verktyg och klicka på **Mappprofiler**.
1. Klicka på rutan **Global profil**.
1. Välj fliken **Konfiguration av XML-redigerare** och klicka på ikonen **Redigera** överst
1. Klicka på ikonen **Hämta** för att hämta filen ui\_config.json på din lokala dator. Du kan sedan göra ändringar i filen och sedan överföra samma fil.
1. Sök efter följande konfiguration i filen `ui_config.json`:

   ```
   {
                           "component": "button",
                           "variant": "action",
                           "quiet": true,
                           "icon": "filePDF",
                           "title": "Download as PDF",
                           "on-click": "EDITOR_SAVE_AS_PDF"
                           }
   ```

   och ersätta den med

   ```
   {
                           "component": "button",
                           "icon": "filePDF",
                           "variant": "action",
                           "quiet": true, "title": "Export as PDF",
                           "on-click": "DOWNLOAD_TOPIC_PDF",
                           "show" : ["@isPreviewMode", "@isXmlMode"]
                           }
   ```

1. Spara filen och överför den.

När du har utfört stegen ovan och väljer samma mappprofil i Användarinställningar i Web Editor, visas alternativet för PDF-generering i förhandsgranskningsläget för ett ämne.

**Överordnat ämne:**[ Anpassa Web Editor](conf-web-editor.md)
