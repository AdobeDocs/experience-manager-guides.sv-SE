---
title: Publicera ett ämne till ett Experience Fragment
description: Publicera ett ämne eller elementen i ett ämne till ett Experience Fragment i AEM Guides.  Lär dig hur du visar de Experience Fragments som finns för ett ämne och publicerar dem igen.
feature: Publishing
role: User
hide: true
exl-id: c3c6c063-441c-413b-a63e-0acbd126ca6d
source-git-commit: ea597cd14469f21e197c700542b9be7c373aef14
workflow-type: tm+mt
source-wordcount: '995'
ht-degree: 0%

---

# Publicera upplevelsefragment

Experience Fragments är delar av modulärt innehåll i Adobe Experience Manager. Dessa innehållsblock är baserade på mallar och kapslar in både innehållet och layouten. Dessa återanvändbara innehållsdelar gör det möjligt för innehållsskapare att sammanställa och leverera enhetliga, skalbara upplevelser över flera kanaler som Experience Manager stöder. Med den här funktionen kan ni enkelt skapa enhetliga marknadsföringsupplevelser effektivt, som nyhetsbrev, kampanjbanners och kundutlåtanden.

Med Experience Manager Guides kan du publicera ett ämne eller dess element i ett Experience Fragment. Du kan skapa en JSON-baserad mappning mellan ett ämne och dess element i ett Experience Fragment. Använd sedan mappningen för att publicera ett ämne eller dess element till ett Experience Fragment. Du kan sedan använda Experience Fragments på valfri Experience Manager-webbplats eller extrahera informationen via API:er som stöds av Experience Fragments.




Så här skapar du ett Experience Fragment:


1. Skapa en mapp i Experience Fragments. Använd den här mappen för att spara de Experience Fragments som du skapar baserat på Experience Fragment-mallarna. Exempel: *sälj-upplevelsefragment*.
1. Markera mappen och välj sedan ikonen **Egenskaper** högst upp.
1. Redigera mappens egenskaper (till exempel *sales-experience-fragments*).


   * **Titel**: Visa eller redigera mappens namn.

   * **Tillåtna mallar**: Innehåller listan med mallar som kan läggas till som underordnade sidor för upplevelsekorrigeringen. Om du vill lägga till den tillåtna mallen anger du det reguljära uttrycket för hämtning av de mallar som krävs i fältet **Tillåtna mallar**.
Till exempel:
     `/libs/cq/experience-fragments/components/experiencefragment/template`

     Om du inte definierar en tillåten mall för en mapp hämtas mallarna som standard från den överordnade mappen eller mallmappen.
   * **Kan beställas**: Gör att du kan ändra ordningen på resurserna i en mapp.

     ![lägg till information om molnkonfiguration i mappegenskaperna](images/experience-fragment-folder-properties.png){width="650" align="left"}
     *Lägg till molnkonfigurationen i mappegenskaperna för att ansluta den till fragmentmallarna.*
1. Om du vill generera ett Experience Fragment väljer du **Ny utdata** ![ny utdataikon](./images/Add_icon.svg) i avsnittet **Utdata** i **filegenskaper** för ett ämne.
1. Välj **Upplevelsefragment**.\
   Fliken ![Alternativ för filegenskaper](./images/file-properties-outputs.png){width="300" align="left"}

   *Lägg till ett nytt Experience Fragment från File Properties för ett ämne*.

   >[!NOTE]
   >
   > Du kan också publicera ett Experience Fragment från **databasvyn**. Välj det ämne som du vill publicera som ett Experience Fragment. På menyn **Alternativ** väljer du sedan **Publicera som** > **Upplevelsefragment**.

1. Fyll i följande information i dialogrutan **Skapa Experience Fragment**:
   ![Lägg till fragmentmodellen och mappningsinformationen i dialogrutan Publicera som Experience Fragment](images/experience-fragment-generate.png){width="500" align="left"}

   *Lägg till sökvägen, mallen och mappningsinformationen för att publicera ett ämne eller dess element som ett Experience Fragment. Du kan skriva över ett befintligt Experience Fragment.*

   * **Sökväg**: Bläddra och välj sökvägen till mappen där du vill publicera Experience Fragment. Du kan också välja ett befintligt Experience Fragment och publicera det igen.
   * **Titel**: Ange Experience Fragment-titeln. Som standard fylls rubriken i med ämnestiteln. Du kan redigera det. Den här titeln används för att generera namnet på Experience Fragment.
   * **Namn**: Ange namnet på Experience Fragment. Som standard fylls namnet i med rubriken för ämnet och blankstegen ersätts med &#39;_&#39;. Exempel: *sample_experience_fragment*. Du kan redigera det. Det här namnet används för att generera URL:en för Experience Fragment.
   * **Mall**: Välj den Experience Fragment-mall som du vill använda för att skapa din Experience Fragment. Mallarna hämtas från den mapp som du har konfigurerat i egenskaperna.
   * **Mapping**: Mappningen väljs från filen *experienceFragmentMapping.json* och visas.



     Din administratör kan lägga till mappningarna i filen *experienceFragmentMapping.json*.  Läs mer om hur du [skapar en mappning mellan ett ämne och ett Experience Fragment](/help/product-guide/cs-install-guide/conf-experience-fragment-mapping-cs.md) i installations- och konfigureringshandboken.

   * Du kan också välja olika villkor för att publicera innehållet.  Välj något av följande alternativ:


      * **Inget**: Välj det här alternativet om du inte vill använda något villkor på publicerade utdata.
      * **Använder DITAVAL**: Välj DITAVAL-filen för att generera anpassat innehåll. Du kan markera DITAVAL-filen i dialogrutan Bläddra eller genom att skriva filsökvägen.
      * **Använda attribut**: Du kan definiera villkorsattribut i dina DITA-avsnitt. Välj sedan villkorsattributet för att publicera det relevanta innehållet.

     >[!NOTE]
     > 
     >Villkor aktiveras bara om villkorsattribut definieras i avsnittet.


   * Markera kryssrutan **Skriv över befintligt innehåll** om Experience Fragment redan finns och du vill skriva över det. Ett fel visas i Experience Manager Guides om du inte markerar kryssrutan och din Experience Fragment redan finns.
1. Klicka på **Generera** för att publicera Experience Fragment.
1. Du kan visa Experience Fragments för ett ämne under avsnittet **Outputs** i **File Properties**. Experience Fragments visas efter datum och tid för publiceringen, med det senaste som det första.

   ![Visa Experience Fragments för ett ämne](images/experience-fragment-outputs.png){width=300 align=&quot;left&quot;}

   *Visa de Experience Fragments som finns för ett ämne och publicera dem igen.*




När du har publicerat Experience Fragments kan du även använda dem på alla Adobe Experience Manager-webbplatser.


## Alternativ-menyn för ett Experience Fragment

Du kan även utföra följande åtgärder för ett Experience Fragment på menyn **Alternativ** :

* **Generera**: Publicera om Experience Fragment för att uppdatera det med det senaste innehållet från DITA-avsnittet. När du genererar om utdata kan du inte ändra sökväg, namn, titel och mall för Experience Fragment. Du kan dock välja olika villkor när du återskapar utdata.

* **Duplicera**: Duplicera ett upplevelsefragment. Du kan ändra sökväg, namn, titel och mall. Du kan också välja olika villkor när du duplicerar ett Experience Fragment.

* **Ta bort**: Ta bort ett Experience Fragment från utdatalistan. En bekräftelsefråga visas. När du har bekräftat tas Experience Fragment bort från listan **Outputs**. Men Experience Fragment tas inte bort från mappen.

* **Visa**: Visa Experience Fragment-redigeraren. Du kan också göra ändringar och spara dem.
