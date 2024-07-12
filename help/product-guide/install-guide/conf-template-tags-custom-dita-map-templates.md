---
title: Konfigurera anpassad DITA-mappningsmall
description: Lär dig konfigurera en anpassad DITA-mappningsmall
exl-id: ea8a6687-1a7b-45c7-8cbc-161f9e88a8be
feature: Template Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 0%

---

# Konfigurera anpassad DITA-mappningsmall {#id1774F04F05Z}

AEM Guides levereras med två färdiga kartmallar - DITA-karta och Bookmap. Du kan skapa kartor som baseras på dessa mallar eller definiera egna mappningsmallar som sedan kan användas för att skapa nya kartor.

Följ de här stegen för att lägga till egna mappningsmallar:

1. Logga in i Adobe Experience Manager som administratör.

1. I Assets-gränssnittet navigerar du till den mapp som konfigurerats för att lagra mappningsmallfilerna. Som standard lagras alla mappningsmallar i mappen /content/dam/dita-templates/maps.

   >[!NOTE]
   >
   > Information om hur du konfigurerar en anpassad plats för att lagra ämne- eller mappmallar finns i [Konfigurera anpassad DITA-mallmappsökväg](conf-template-tags-custom-dita-topic-template.md#id191LCF0095Z)

1. Klicka på **Skapa** \> **DITA-mall**.

1. På sidan Design väljer du den typ av karta som du vill skapa.

   >[!NOTE]
   >
   > Du kan använda karta- eller bokmappsmallen som bas för den nya mallen.

1. Klicka på **Nästa**.

1. På den nya mallegenskapssidan anger du mallens **rubrik** och **namn**.

   >[!NOTE]
   >
   > Namnet föreslås automatiskt baserat på mallens rubrik. Om du vill ange namnet manuellt kontrollerar du att namnet inte innehåller blanksteg, apostrof eller klammerparenteser och slutar med .ditamap.

1. Klicka på **Skapa**.

   Meddelandet Kartan har skapats visas.

   Du kan välja att öppna mallen för redigering i kartredigeraren eller spara mallfilen på malllagringsplatsen. När mallen har skapats kan du använda kartredigeraren för att anpassa mallen efter dina behov. När du har skapat en mall måste du associera den med en global profil eller en profil på mappnivå.


Nästa gång du skapar en ny karta visas mallen på sidan Design. Mer information om hur du skapar en DITA-karta finns i *Använda Adobe Experience Manager Guides*.

>[!TIP]
>
> Mer information om hur du använder anpassade mappningsmallar finns i avsnittet *Anpassade mallar* i guiden Bästa metoder.

**Överordnat ämne:** [Konfigurera ämne- och mappningsmallar](conf-template-tags.md)
