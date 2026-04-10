---
title: Konfigurera giltiga filnamn för utdata från AEM Site
description: Lär dig hur du konfigurerar giltiga filnamn för utdata från AEM Site
feature: Filename Configuration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 0%

---

# Konfigurera giltiga filnamn för utdata från AEM Site {#id214GK0X0KXA}

På samma sätt som listan med giltiga filnamnstecken som tillåts för DITA-avsnitt kan du även konfigurera en lista med giltiga filnamnstecken för utdata från AEM Site. Vissa av de kända tecken som inte tillåts i en URL är: ``'<>`@$``. Dessa tecken konverteras automatiskt till understreck `_` när de påträffas när utdatafilnamn för AEM Site genereras.

Följande flikar innehåller anvisningar om hur du konfigurerar giltiga filnamn för utdata från AEM Site baserat på din Experience Manager Guides-konfiguration: Cloud Service eller On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

Använd instruktionerna i [Konfigurationsåsidosättningar](download-install-config-override.md#) för att skapa konfigurationsfilen. Ange följande \(egenskap\)-information i konfigurationsfilen för att ange giltiga tecken i utdata för AEM Site:

| PID | Egenskapsnyckel | Egenskapsvärde |
|---|------------|--------------|
| `com.adobe.fmdita.common.SanitizeNodeNameImpl` | `aemsite.DisallowedFileNameChars` | Lägg till tecken som du vill ersätta med ett understreck i utdatafilnamnen för AEM Site. <br> **Standardvärde**: ``'<\>\`@$`` |

>[!TAB Lokal]

Konfigurationen som gör att du kan ange giltiga tecken i AEM Site-utdata finns i paketet `com.adobe.fmdita.common.SanitizeNodeNameImpl`. **Ange inställningen Otillåten teckenuppsättning för publicering till AEM Sites** om du vill ta med tecken som du vill ersätta med ett understreck i AEM Site-utdatafilens namn.

>[!ENDTABS]
