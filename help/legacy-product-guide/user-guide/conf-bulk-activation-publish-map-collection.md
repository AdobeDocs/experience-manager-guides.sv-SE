---
title: Aktivera utdata
description: Aktivera utdata från DITA-kartor i AEM Guides. Lär dig hur du aktiverar ditt innehåll på publiceringsinstansen.
feature: Publishing, Bulk Activation
role: User
hide: true
exl-id: de1fd057-60c6-4b1a-9e55-f32969eb0079
source-git-commit: 4801f0d327b4bd0641aa195d39ec2c4be2a2ce74
workflow-type: tm+mt
source-wordcount: '444'
ht-degree: 0%

---

# Aktivera utdata {#id214GGF00V5U}

När du har skapat en kartsamling för massaktivering är nästa steg att aktivera ditt innehåll på publiceringsinstansen. Så här aktiverar du ditt innehåll:

1. Välj **Stödlinjer** i listan över verktyg.

1. Klicka på länken Adobe Experience Manager överst och välj **Verktyg**.

1. Klicka på panelen **Masspubliceringspanel**.

   En lista över massaktiveringskarta visas.

1. Markera samlingen som du vill publicera och klicka på **Öppna**.

   ![](images/bulk-activation-collection-open.png){width="800" align="left"}

1. \(*Valfritt*\) Använd de filter som krävs från den vänstra listen för att filtrera kartan baserat på deras ändrade \(status\), utdataförinställning eller språk.

   >[!NOTE]
   >
   >Generera utdata för kartan med förinställningen för utdata innan du aktiverar dem i kartsamlingen.


Visa olika sätt att aktivera din samling baserat på dina inställningar.

<details>
<summary> Molntjänster </summary>

![bulk-collection-publish on cloud service](images/bulk-activation-collection-quick-publish-CS.png){width="650" align="left"}

Du kan aktivera utdata för instanserna **Förhandsgranska** eller **Publicera**.

**Förhandsgranska**

* Om du vill aktivera utdata för markerade kartor markerar du förgenererade kartutdata och väljer **Publicera till** > **Förhandsgranska**.
* Om du vill aktivera utdata för alla DITA-kartor med deras konfigurerade förinställningar markerar du kryssrutan bredvid kolumnen **Karta** och väljer sedan **Publicera till** > **Publicera**.


**Publicera**

* Om du vill aktivera utdata för markerade kartor markerar du förgenererade kartutdata och väljer **Publicera till** > **Publicera**.

* Om du vill aktivera utdata för alla DITA-kartor med deras konfigurerade förinställningar markerar du kryssrutan bredvid kartan (kolumn) och väljer sedan **Publicera till** > **Publicera**.


>[!NOTE]
> 
> Kryssrutan för en karteutdata är bara aktiverad om du har genererat utdata för en karta.

Ett meddelande om att kartan lyckades visas när kartutdata är köade för publicering.

När utdata har aktiverats för de markerade mappfilerna uppdateras fliken för granskningshistorik och de senaste aktiverade utdata visas överst. Kolumnen **Publicerad** uppdateras med publiceringsdatum och -tid.

</details>

<details>    
<summary>  Lokal programvara </summary>


Gör något av följande:

* Om du vill aktivera utdata för markerade kartor markerar du förgenererade kartutdata och väljer **Snabbpublicering**.
* Om du vill aktivera utdata för alla DITA-kartor med deras konfigurerade förinställningar markerar du kryssrutan bredvid kartan (kolumn) och väljer sedan **Snabbpublicering.**
  ![bulk-collection-publish](images/bulk-activation-collection-quick-publish.png){width="650" align="left"}

  >[!NOTE]
  > 
  >Kryssrutan för en karteutdata är bara aktiverad om du har genererat utdata för en karta.


Ett meddelande om att kartan lyckades visas när kartutdata är köade för publicering.

När utdata har aktiverats för de markerade mappfilerna uppdateras fliken för granskningshistorik och de senaste aktiverade utdata visas överst. Kolumnen **Publicerad** uppdateras med publiceringsdatum och -tid.

**Överordnat ämne: &#x200B;** [Massaktivering av publicerat innehåll](conf-bulk-activation.md)
