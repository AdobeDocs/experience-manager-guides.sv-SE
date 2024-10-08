---
title: Publish ett ämne i ett innehållsfragment
description: Publish ett ämne eller elementen i ett ämne till ett innehållsfragment i AEM Guides.  Lär dig hur du visar innehållsfragment för ett ämne och publicerar dem på nytt.
feature: Publishing
role: User
source-git-commit: 76c731c6a0e496b5b1237b9b9fb84adda8fa8a92
workflow-type: tm+mt
source-wordcount: '925'
ht-degree: 0%

---

# Publish Content Fragments

Innehållsfragment är separata innehållsdelar i Adobe Experience Manager. De är strukturerade innehåll baserat på en innehållsmodell. Innehållsfragment är rent innehåll utan design- eller layoutinformation. De kan redigeras och hanteras oberoende av de kanaler som Adobe Experience Manager stöder. Innehållsfragment är modulära, där innehållet delas upp i mindre komponenter.

Med Adobe Experience Manager Guides kan du publicera ett ämne eller elementen i ett ämne till ett innehållsfragment. Du kan skapa en JSON-baserad mappning mellan ett ämne och en innehållsfragmentmodell. Använd den här mappningen för att publicera ett ämne eller elementen i ett ämne till ett innehållsfragment. Du kan sedan använda Content Fragments på valfri Adobe Experience Manager-webbplats eller extrahera informationen via API:er som stöds av Content Fragments.


Så här skapar du ett innehållsfragment:

1. Skapa en [innehållsfragmentmodell](https://experienceleague.adobe.com/docs/experience-manager-65/assets/content-fragments/content-fragments-models.html?lang=en) i Adobe Experience Manager Assets.
1. Skapa en mapp där du vill spara de innehållsfragment som du skapar baserat på modellen för innehållsfragment. Exempel:&quot;stock-content-fragments&quot;.
1. Redigera mappens egenskaper (till exempel&quot;stock-content-fragments&quot;) och lägg till sökvägen till mappen, som innehåller modellen för innehållsfragment i molnkonfigurationen.
Lägg till exempel till `/conf/we-retail` i molnkonfigurationen. Den här konfigurationen kopplar alla innehållsfragmentmodeller till mappen.\
   ![lägg till information om molnkonfiguration i mappegenskaperna](images/fragment-folder-cloud-configuration.png){width="650" align="left"}
   *Lägg till molnkonfigurationen i mappegenskaperna för att ansluta den till fragmentmodellerna.*

1. Om du vill generera ett innehållsfragment väljer du **Ny utdata** ![ny utdataikon](./images/Add_icon.svg) i avsnittet **Utdata** i **filegenskaper** för ett ämne.
1. Välj **Innehållsfragment**.\
   Fliken ![Alternativ för filegenskaper](./images/file-properties-outputs-tab.png){width="300" align="left"}

   *Lägg till ett nytt innehållsfragment från filegenskaperna för ett ämne*.

1. Fyll i följande information i dialogrutan **Skapa innehållsfragment**:
   ![Lägg till fragmentmodellen och mappningsinformation i dialogrutan Publish som innehållsfragment](images/content-fragment-publish.png){width="500" align="left"}
   *Lägg till information om sökväg, modell och mappning för att publicera ett ämne eller dess element som ett innehållsfragment. Du kan skriva över ett befintligt innehållsfragment.*

   >[!NOTE]
   >
   >Du kan också publicera ett innehållsfragment från **databasvyn**. Markera det ämne som du vill publicera som ett innehållsfragment. På menyn **Alternativ** väljer du sedan **Publish som** > **Innehållsfragment**.

   * **Sökväg**: Bläddra och välj sökvägen till mappen där du vill publicera innehållsfragmentet. Om du markerar ett befintligt innehållsfragment skrivs innehållet i de mappade fälten över.
   * **Titel**: Ange innehållsfragmentets rubrik. Som standard fylls rubriken i med ämnestiteln. Du kan redigera det. Den här titeln används för att generera namnet på innehållsfragmentet.
   * **Namn**: Ange namnet på innehållsfragmentet. Som standard fylls namnet i med rubriken för ämnet och blankstegen ersätts med &#39;_&#39;. Exempel: *sample_content_fragment*. Du kan redigera det.  Det här namnet används för att generera URL:en för innehållsfragmentet.
   * **Modell**: Välj den innehållsfragmentmodell som du vill använda för att skapa ditt innehållsfragment. Modellerna hämtas från mappen som du har konfigurerat i molntjänsterna.
   * **Mappning**: Välj en mappning i listrutan. Mappningarna från filen *contentFragmentMapping.json* väljs.



     Administratören kan lägga till mappningarna i filen *contentFragmentMapping.json*. Läs mer om hur du [skapar en mappning mellan ett ämne och ett innehållsfragment](/help/product-guide/cs-install-guide/conf-content-fragment-mapping-cs.md) i installations- och konfigureringshandboken.

   * Du kan också välja olika villkor för att publicera innehållet.  Välj något av följande alternativ:


      * **Inget**: Välj det här alternativet om du inte vill använda något villkor på publicerade utdata.
      * **Använder DITAVAL**: Välj DITAVAL-filen som ska genereras, vilket inkluderar specifikt innehåll. Du kan markera DITAVAL-filen i dialogrutan Bläddra eller genom att skriva filsökvägen.
      * **Använda attribut**: Du kan definiera villkorsattribut i dina DITA-avsnitt. Välj sedan villkorsattributet för att publicera det relevanta innehållet.
     >[!NOTE]
     > 
     >Villkor aktiveras bara om villkorsattribut definieras i avsnittet.



   * Välj **Skriv över befintligt innehåll** om ditt innehållsfragment redan finns och du vill skriva över det. Ett fel visas i Experience Manager Guides om du inte markerar kryssrutan och ditt innehållsfragment redan finns.
1. Klicka på **Generera** för att publicera innehållsfragmentet.

1. Du kan visa innehållsfragment för ett ämne under avsnittet **Utdata** i **Filegenskaper**.

   ![Visa innehållsfragment för ett ämne](images/outputs-options-menu.png){width="300" align="left"}

   *Visa innehållsfragment för ett ämne och publicera dem igen.*


När du har publicerat innehållsfragmenten kan du även använda dem på alla Adobe Experience Manager-webbplatser.




## Alternativ-menyn för ett innehållsfragment

Du kan även utföra följande åtgärder för ett innehållsfragment på menyn **Alternativ** :

* **Generera**: Publicera om innehållsfragmentet för att uppdatera det med det senaste innehållet från DITA-avsnittet. När du genererar om utdata kan du inte ändra sökvägen, namnet, titeln, modellen och mappningen för innehållsfragmentet. Du kan dock välja olika villkor när du återskapar utdata.

* **Duplicera**: Duplicera ett innehållsfragment. Du kan ändra sökväg, namn, titel, modell och mappning. Du kan också välja olika villkor när du duplicerar ett innehållsfragment.

* **Ta bort**: Ta bort ett innehållsfragment från utdatalistan. En bekräftelsefråga visas. När du har bekräftat tas innehållsfragmentet bort från listan **Utdata**.

  >[!NOTE]
  >
  > Inget innehåll tas bort från innehållsfragmentet av den här åtgärden.

* **Visa**: Visa redigeraren för innehållsfragment. Du kan också göra ändringar och spara dem.


