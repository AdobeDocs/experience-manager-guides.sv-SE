---
title: Publish ett ämne på en AEM Sites-sida
description: Publish ett ämne eller de element som finns i ett avsnitt i ett Adobe Experience Manager Sites-dokument.  Lär dig hur du visar Experience Manager Sites-sidan för ett ämne och publicerar dem igen.
feature: Publishing
role: User
source-git-commit: fa07db6a9cb8d8f5b133258acd5647631b22e28a
workflow-type: tm+mt
source-wordcount: '638'
ht-degree: 0%

---

# Publish Adobe Experience Manager Sites


Experience Manager Sites sida avser innehåll som publicerats på Adobe Experience Manager webbplats. Med Experience Manager Guides kan du publicera ett fristående ämne på en Sites-sida.

Med den här funktionen kan du publicera ett ämne och dess element utan att skapa en DITA-karta eller förinställningar för utdata. Du kan enkelt uppdatera ämnet, publicera om sidan Webbplatser och återanvända det på olika webbsidor. Med den här funktionen kan du enkelt publicera fristående artiklar eller marknadsföringsmaterial.





Så här skapar du en platssida:




1. Välj **Ny utdata** ![ny utdataikon](./images/Add_icon.svg) i avsnittet **Utdata** i **filegenskaper** för ett ämne.
1. Välj sidan **Webbplatser**.


1. Fyll i följande information i dialogrutan **Skapa platser**:
   ![Lägg till sökvägen och mallinformationen på sidan Generera platser](images/aem-sites-page-generate.png){width="500" align="left"}

   *Lägg till sökvägen, titeln, namnet och mallinformationen för att publicera ett ämne eller dess element som en webbplatssida. *

   * **Sökväg**: Bläddra och välj sökvägen till mappen där du vill publicera sidan Platser.
   * **Titel**: Ange webbplatsens titel. Som standard fylls rubriken i med ämnestiteln. Du kan redigera det. Den här titeln används för att generera namnet på sidan Platser.
   * **Namn**: Ange namnet på sidan Platser. Som standard fylls namnet i med ämnesrubriken och otillåtna tecken som blanksteg och specialtecken ersätts med&quot;_&quot;. Exempel: *sample_sites_page*. Du kan redigera det. Det här namnet används för att generera URL:en för sidan Platser.
   * **Sidmall**: Välj sidmallen Platser för att skapa din platssida. Du kan visa mallarna i mappen på den sökväg du väljer. Administratören kan även överföra egna mallar.


   * Du kan också välja olika villkor för att publicera innehållet.  Välj något av följande alternativ:


      * **Inget**: Välj det här alternativet om du inte vill använda något villkor på publicerade utdata.
      * **Använder DITAVAL**: Välj DITAVAL-filen för att generera anpassat innehåll. Du kan markera DITAVAL-filen i dialogrutan Bläddra eller genom att skriva filsökvägen.
      * **Använda attribut**: Du kan definiera villkorsattribut i dina DITA-avsnitt. Välj sedan villkorsattributet för att publicera det relevanta innehållet.

     >[!NOTE]
     > 
     >Villkor aktiveras bara om villkorsattribut definieras i avsnittet.



1. Klicka på **Generera** för att publicera sidan Webbplatser.
1. Du kan visa sidan Webbplatser för ett avsnitt under avsnittet **Utdata** i **Filegenskaper**. Webbplatssidorna visas efter publiceringsdatum och -tid, med det senaste som det första.

   ![Visa webbplatssidan för ett ämne](images/aem-sites-outputs.png){width=300 align=&quot;left&quot;}

   *Visa webbplatssidan som finns för ett ämne och publicera dem igen.*




När du har publicerat sidan Webbplatser kan du även använda dem på alla Adobe Experience Manager-webbplatser.


## Menyn Alternativ för en Experience Manager Sites

Du kan även utföra följande åtgärder för en Experience Manager Sites på menyn **Alternativ** :

* **Generera**: Publicera om sidan Webbplatser för att uppdatera den med det senaste innehållet från DITA-avsnittet. När du genererar om utdata utan att ändra sökväg, namn, titel, mall och villkor uppdateras webbplatssidan helt enkelt med det senaste innehållet.

* **Duplicera**: Duplicera en webbplatssida. Du kan ändra sökväg, namn, titel och mall. Du kan också välja olika villkor när du duplicerar en platssida.

* **Ta bort**: Ta bort en webbplatssida från utdatalistan. En bekräftelsefråga visas. När du har bekräftat tas sidan Webbplatser bort från listan **Utdata**. Men sidan Platser tas inte bort permanent.

* **Visa**: Visa sidredigeraren Webbplatser. Du kan också göra ändringar och spara dem.
