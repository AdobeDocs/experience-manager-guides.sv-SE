---
title: Masstaggning av DITA-innehåll
description: Använd bulktaggning av innehåll i AEM Guides för att förbättra identifieringen av DITA-innehåll. Lär dig hur du använder, tar bort, visar eller döljer gruppmärkord i ett eller flera ämnen.
exl-id: 4c6639a3-333b-44ad-9aec-735a327c3320
feature: Metadata Management
role: User
source-git-commit: 4b4abf5958f251da05257d34a68471d5f36969a3
workflow-type: tm+mt
source-wordcount: '706'
ht-degree: 0%

---


# Masstaggning av DITA-innehåll {#id179SG0TN05Z}

![](images/test-version-info-table.svg){width="650" align="left"}

Med taggar kan du gruppera eller klassificera innehåll i innehållsdatabasen och även i publicerade utdata. Om du har använt taggar på innehållet kan du enkelt hitta relaterade ämnen i en DITA-karta som kan hjälpa dig att skapa innehåll. Med publicerade utdata kommer slutanvändarna att kunna hitta rätt innehåll snabbare med rätt taggar på plats.

Med Adobe Experience Manager Guides kan du tagga DITA-innehåll i några få steg. Du kan använda funktionen för bulktaggning för att tillämpa flera taggar på flera ämnen, en DITA-karta eller på en underkarta. Du kan också lägga till märkord i ett enskilt ämne. Taggning är den inbyggda funktionen i Adobe Experience Manager. Mer information om hur du skapar och hanterar taggar finns i avsnittet [Administrera taggar](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/tags.html?lang=en) i Adobe Experience Manager-dokumentationen.

Som standard ger Experience Manager Guides inte läsåtkomst till någon användare i den mapp där alla taggar i Adobe Experience Manager-databasen lagras. Om du vill använda taggar som definieras i Adobe Experience Manager-databasen måste du be systemadministratören att ge åtkomst till den mapp där taggarna lagras.

## Använda gruppmärkord

Använd funktionen för bulktaggning för att lägga till flera taggar samtidigt. Utför följande steg för att använda taggar i dina ämnen på en DITA-karta:

1. I Assets-gränssnittet navigerar du och väljer DITA-kartfilen.

   DITA-kartkonsolen visas med en lista över tillgängliga utdatapresentationer för att generera utdata.

1. Välj **Ämnen**.

   En lista med ämnen som är tillgängliga på DITA-kartan visas. UUID för topics&#39; visas under ämnesrubriken.

1. Markera de ämnen eller delmappar som du vill använda taggar på.

   ![](images/apply-tags-uuid.png){width="650" align="left"}


   >[!NOTE]
   >
   > På skärmbilden ovan visas en delkarta som är markerad och utökad. När du väljer en delkarta markeras även alla ämnen under delkartan.

1. Välj **Använd taggar**.

   Dialogrutan Välj taggar visas.

1. Markera en eller flera taggar som du vill använda för de markerade avsnitten.

1. Bekräfta ditt val.

   De markerade taggarna används i avsnitten och visas bredvid ämnestiteln.

   >[!NOTE]
   >
   > När du har lagt till taggar i dina ämnen och flyttar eller tar bort ett ämne, tas även taggarna för dessa ämnen bort. Ämnet finns dock kvar på kartan tills du tar bort det.


## Tillämpa taggar på ett enskilt ämne

Gör så här för att använda taggar på ett enskilt ämne:

1. Navigera till och markera ämnesfilen som du vill använda taggar på i Assets-gränssnittet.

1. Välj **Egenskaper** i verktygsfältet.

   Ämnets egenskapssida visas.

1. Välj bläddringsikonen bredvid fältet **Taggar** på fliken Grundläggande.

1. Markera en eller flera taggar som du vill använda i det markerade ämnet.

1. Bekräfta ditt val.

1. Välj **Använd taggar**.

   De markerade taggarna används i avsnittet och visas i fältet Taggar.

1. Välj **Spara och stäng**.


## Ta bort taggar

Du kan ändra taggningsinformationen för alla DITA-avsnitt beroende på vilka behov ditt företag har. Du kan enkelt ta bort alla taggar samtidigt eller bara de taggar som inte är giltiga i ämnet.

Utför följande steg för att ta bort alla taggar från ett eller flera ämnen:

1. Navigera till och markera DITA-kartfilen i Assets-gränssnittet.

   DITA-kartkonsolen visas med en lista över tillgängliga utdatapresentationer för att generera utdata.

1. Välj **Ämnen**.

   En lista med ämnen som är tillgängliga på DITA-kartan visas.

1. Markera de ämnen som du vill ta bort taggar från.

1. Välj **Ta bort taggar**.

   >[!NOTE]
   >
   > Om ikonen Ta bort taggar inte visas kontrollerar du att du inte har aktiverat funktionen Dölj taggar.

1. I dialogrutan Bekräfta borttagning väljer du **OK** för att ta bort taggar från de markerade ämnena.


## Visa eller dölj taggar

Om du har en lång lista med taggar som används i dina ämnen kan det vara lite besvärligt att navigera. Du kan enkelt dölja taggar i från DITA-kartkonsolvyn genom att välja ikonen Dölj taggar. På samma sätt visas alla taggar när taggarna inte visas om du markerar Visa taggar.

**Överordnat ämne:**&#x200B;[&#x200B; Hantera metadata](manage-metadata.md)
