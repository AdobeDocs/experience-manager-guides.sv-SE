---
title: Migrering av icke-UID till UUID-innehåll
description: Lär dig hur du migrerar icke-UID till UUID-innehåll
exl-id: f8b723bf-84c0-4fe6-936e-63970fb3e417
feature: Migration
role: Admin
level: Experienced
source-git-commit: 56f1bd81e74ad9b479b2dcbcf04e1ee82e9a9041
workflow-type: tm+mt
source-wordcount: '320'
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
| 4.3.1 ej UUID | 4.3.2 UUID | Efter migrering till version 4.3.2 UUID måste du installera 4.6.0 (UUID) direkt. När du är på 4.6.0 uppgraderar du till version 5.1.0 och installerar sedan 5.1.0 Service Pack 3. |
| 4.6.0 Service Pack 4, ej UUID | 4.6.1 UUID | Efter migrering till version 4.6.1 UUID måste du uppgradera direkt till 5.1.0 (UUID). Installera version 5.1.0 Service Pack 3 när uppgraderingen är klar. |

## Beräkning av migreringstid

Migreringsverktyget bearbetar resurser med en genomsnittlig hastighet på cirka 50 ms per tillgång. Följande tabell innehåller uppskattningar av migreringstid för ett system som har konfigurerats med 64 vCPU:er, 128 GB RAM och SSD-baserat lagringsutrymme. Minneskraven kan öka för större databaser eller resurser med många renderingar eller högupplösta binära filer.

>[!NOTE]
>
> Den faktiska migreringstiden kan variera beroende på maskinvarans prestanda, lagringsflöde, samtidiga AEM-aktiviteter och total systembelastning.


| **Resursantal** | **Cirka. Tid** |
|-----------------|-------------------------|
| 10 kB | ~8-9 minuter |
| 50 kB | ~42 minuter |
| 100 kB | ~1,4 timmar |
| 250 kB | ~3,5 timmar |
| 500 kB | Cirka 7 timmar |
| 750 kB | ~10,5 timmar |
| 1 MB | ~14 timmar |
| 2 MB | ~28 timmar (~1,2 dagar) |
| 3M | ~42 timmar (~1,75 dagar) |
| 5 MB | ~69 timmar (~2,9 dagar) |
| 10 MB | ~139 timmar (~5,8 dagar) |


Mer information om hur du migrerar innehåll finns i följande artiklar:

- [**4.3.1 non-UUID to 4.3.2 UUID content migration**](./migrate-non-uuid-4-3.md)
- [**4.6.0 Service Pack 4 icke-UUID till 4.6.1 migrering av UUID-innehåll**](./migrate-non-uuid-uuid-4-6.md)



