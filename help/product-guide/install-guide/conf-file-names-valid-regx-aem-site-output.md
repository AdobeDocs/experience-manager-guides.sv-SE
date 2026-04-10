---
title: Konfigurera giltiga filnamn för utdata från AEM Site
description: Lär dig hur du konfigurerar giltiga filnamn för utdata från AEM Site
exl-id: 1e69d6f8-7baf-4189-bbbd-34cd0fec6634
feature: Filename Configuration
role: Admin
level: Experienced
hidefromtoc: true
source-git-commit: 3aadc59f5034828cf319992b7acb32d5a88eaf93
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 0%

---

# Konfigurera giltiga filnamn för utdata från AEM Site {#id214GK0X0KXA}

På samma sätt som listan med giltiga filnamnstecken som tillåts för DITA-avsnitt kan du även konfigurera en lista med giltiga filnamnstecken för utdata från AEM Site. Vissa av de kända tecken som inte tillåts i en URL är: ```'<>`@$```. Dessa tecken konverteras automatiskt till understreck&quot;_&quot; när de påträffas när utdatafilnamn för AEM Site genereras. Konfigurationen som gör att du kan ange giltiga tecken i AEM Site-utdata finns i paketet `com.adobe.fmdita.common.SanitizeNodeNameImpl`. **Ange inställningen Otillåten teckenuppsättning för publicering till AEM Sites** om du vill ta med tecken som du vill ersätta med ett understreck i AEM Site-utdatafilens namn.

**Överordnat ämne:**[ Konfigurera filnamn](conf-file-names.md)
