---
title: Konfigurera standardvärde för taggvyn
description: Lär dig hur du konfigurerar standardvärdet för taggvyn
exl-id: 3ab75101-4c23-4e45-bfcf-76c1f5b92c96
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '215'
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

```
"defaultValues":
                {
                "tagsView": true
                }
```

1.) Spara filen och överför den.

>[!NOTE]
>
> Användarens inställning i Web Editor för att aktivera/inaktivera taggvyn har företräde framför det här standardvärdet. Om en användare aktiverar taggvyn från Web Editor är den alltså aktiverad även i alla sessioner.

**Överordnat ämne:**[ Anpassa Web Editor](conf-web-editor.md)
