---
title: Konfigurera anpassad DITA-mappningsmall
description: Lär dig hur du konfigurerar en anpassad DITA-mappningsmall
exl-id: a0eeb43c-06e4-4922-a005-704e8929063f
feature: Template Configuration
role: Admin
level: Experienced
source-git-commit: 83971ee35a19cf0146ddd034b1ae7a345f587663
workflow-type: tm+mt
source-wordcount: '489'
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


Nästa gång du skapar en ny karta visas mallen på sidan Design. Mer information om hur du skapar en DITA-karta finns i as a Cloud Service om att använda Adobe Experience Manager Guides.

>[!TIP]
>
> Mer information om hur du använder anpassade mappningsmallar finns i avsnittet *Egna mallar* i guiden Bästa metoder.


## Anpassa antalet referenser i en DITA-karta

Du kan konfigurera tröskelvärdet för asynkron bearbetning baserat på antalet referenser i DITA-kartan. Som standard skapas kartor med fler än 5 referenser via asynkrona åtgärder, medan kartor med färre referenser fortsätter med synkrona åtgärder.


Använd instruktionerna i [Konfigurationsåsidosättningar](download-install-additional-config-override.md#) för att skapa konfigurationsfilen. I konfigurationsfilen anger du följande (egenskaps) information för att ange antalet referenser i DITA-mappningsmallen för att behålla processen synkron:

| PID | Egenskapsnyckel | Egenskapsvärde |
|---|------------|--------------|
| com.adobe.fmdita.xmleditor.config.XmlEditorConfig | xmleditor.asyncmapcreation | > 0 <br> **Standardvärde**: 5 |

När du skapar en DITA-karta med stora ämnesreferenser med hjälp av en anpassad mall kommer kartan inte att kunna skapas på molnservern om den totala bearbetningstiden överstiger 60 sekunder.

För att förhindra detta konfigurerar du **asynkron datamappning** i XmlEditorConfig som tillåter att aktiviteter körs parallellt och minskar behandlingstiderna för större DITA-kartor.

**Överordnat ämne:** [Konfigurera ämne- och mappningsmallar](conf-template-tags.md)
