---
title: Konfigurera giltiga filnamn för AEM
description: Lär dig hur du konfigurerar giltiga filnamn för AEM webbplatsutdata
exl-id: 05215bec-653b-4563-83c6-a1bb16200469
feature: Filename Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 0%

---

# Konfigurera giltiga filnamn för AEM {#id214GK0X0KXA}

På samma sätt som listan med giltiga filnamnstecken som tillåts för DITA-avsnitt kan du även konfigurera en lista med giltiga filnamnstecken för AEM. Vissa av de kända tecken som inte tillåts i en URL är: ``'<>`@$``. Dessa tecken konverteras automatiskt till understreck `_` när de påträffas när AEM webbplatsens utdatafilnamn genereras.

Använd instruktionerna i [Konfigurationsåsidosättningar](download-install-additional-config-override.md#) för att skapa konfigurationsfilen. I konfigurationsfilen anger du följande \(egenskap\)-information för att ange giltiga tecken i AEM platsutdata:

| PID | Egenskapsnyckel | Egenskapsvärde |
|---|------------|--------------|
| `com.adobe.fmdita.common.SanitizeNodeNameImpl` | `aemsite.DisallowedFileNameChars` | Lägg till tecken som du vill ersätta med ett understreck i AEM Platsens utdatafilnamn. <br> **Standardvärde**: ``'<\>\`@$`` |

**Överordnat ämne:**[ Konfigurera filnamn](conf-file-names.md)
