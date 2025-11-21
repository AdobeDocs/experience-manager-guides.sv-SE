---
title: Migrering av icke-UID till UUID-innehåll
description: Lär dig hur du migrerar icke-UID till UUID-innehåll
exl-id: f8b723bf-84c0-4fe6-936e-63970fb3e417
feature: Migration
role: Admin
level: Experienced
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 0%

---

# Migrering av icke-UID till UUID-innehåll {#id226TI0U20XA}


Du kan migrera ditt icke-UUID-innehåll till UUID baserat på den aktuella versionen av Experience Manager Guides som du använder.

>[!IMPORTANT]
>
> Innan du migrerar innehåll till UUID-servern kontrollerar du att du har en icke-UID-server med kompatibel AEM Guides-version installerad på den.

## Kompatibilitetsmatris

Använd följande matris för att fastställa rätt migreringssökväg baserat på din aktuella version som inte är UUID. Detta ger en smidig övergång efter migrering.

| Icke-UID-version krävs för migrering | UUID-version efter migrering | Uppgraderingsväg som stöds efter migrering |
|---|---|---|
| 4.3.1 ej UUID | 4.3.2 UUID | Efter migrering till UUID version 4.3.2 kan du installera 4.6.0 (UUID) direkt. När du är på 4.6.0 uppgraderar du till version 5.1.0 och installerar sedan 5.1.0 Service Pack 1. |
| 4.6.0 Service Pack 4, ej UUID | 4.6.1 UUID | Efter migrering till version 4.6.1 UUID kan du uppgradera direkt till 5.1.0 (UUID). Installera version 5.1.0 Service Pack 1 när uppgraderingen är klar. |

Mer information om hur du migrerar innehåll finns i följande artiklar:

- [**4.3.1 non-UUID to 4.3.2 UUID content migration**](./migrate-non-uuid-4-3.md)
- [**4.6.0 Service Pack 4 icke-UUID till 4.6.1 migrering av UUID-innehåll**](./migrate-non-uuid-uuid-4-6.md)



