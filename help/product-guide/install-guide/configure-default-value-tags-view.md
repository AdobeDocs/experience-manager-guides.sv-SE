---
title: Konfigurera standardvärde för taggvyn
description: Lär dig hur du konfigurerar standardvärdet för taggvyn
exl-id: 52214459-74b8-47ec-982b-6176145348a8
feature: Web Editor Configuration
role: Admin
level: Experienced
hidefromtoc: true
source-git-commit: 3aadc59f5034828cf319992b7acb32d5a88eaf93
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 0%

---

# Konfigurera standardvärde för taggvyn {#id223GN0M0NDC}

I AEM Guides kan du konfigurera standardläget för taggvyn i webbredigeraren, vilket gör att du kan aktivera eller inaktivera taggvyn som standard för en ny användarsession. Utför följande steg för att konfigurera standardvärdet för taggvyn:

1. Hämta UI-konfigurationsfilen genom att logga in i Adobe Experience Manager som administratör.
1. Klicka på länken Adobe Experience Manager överst och välj **Verktyg**.
1. Välj **Stödlinjer** i listan över verktyg och klicka på **Mappprofiler**.
1. Klicka på rutan **Global profil**.
1. Välj fliken **XML-redigerarkonfiguration** och klicka på ikonen **Redigera** överst.
1. Klicka på ikonen **Hämta** i **gränssnittskonfigurationen för XML-redigeraren** för att hämta filen `ui_config.json` på din lokala dator.
1. Ändra standardläget för taggvyn i filen `ui_config.json` genom att ändra avsnittet defaultValues enligt nedan:

   ```json
   "defaultValues":
                   {
                   "tagsView": true
                   }
   ```

1. Spara filen och överför den.

>[!NOTE]
>
> Användarens inställning i Web Editor för att aktivera/inaktivera taggvyn har företräde framför det här standardvärdet. Om en användare aktiverar taggvyn från Web Editor är den alltså aktiverad även i alla sessioner.

**Överordnat ämne:**&#x200B;[&#x200B; Anpassa Web Editor](conf-web-editor.md)
