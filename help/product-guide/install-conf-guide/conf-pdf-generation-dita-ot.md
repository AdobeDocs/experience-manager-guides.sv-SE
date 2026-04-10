---
title: Konfigurera generering av enskilda ämnen i PDF
description: Lär dig hur du konfigurerar generering av enskilda ämnen i PDF
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '271'
ht-degree: 0%

---

# Konfigurera single topic PDF generation for Cloud Service

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

**Överordnat ämne:**[ Anpassa Web Editor](customize-overview.md)
