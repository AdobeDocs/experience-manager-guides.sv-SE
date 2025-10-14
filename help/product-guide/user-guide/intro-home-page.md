---
title: Adobe Experience Manager Guides hemsida
description: Lär känna Adobe Experience Manager Guides hemsida.
feature: Authoring
role: User
exl-id: 4e6e40ba-277b-43d5-a2a9-665f4586c7e3
source-git-commit: f9b879d6d374334a08a1d3b0a47b0cb419f02140
workflow-type: tm+mt
source-wordcount: '1966'
ht-degree: 0%

---

# Experience Manager Guides hemsida

Hemsidan är den första skärmen som visas när du loggar in på Experience Manager Guides. Den ger dig en enhetlig och intuitiv välkomstskärm, som innehåller en snabb vy av de filer du nyligen har öppnat, samlingar med mera.

![](images/aem-home-page.png){align="left"}

Experience Manager Guides hemsida är indelad i följande avsnitt:

- Sidhuvudsfält
- Navigeringsfält
- Vänster panel

## Sidhuvudsfält

Huvudfältet är det översta fältet på hemsidan som visar Adobe Experience Manager-logotypen (eller ett enhetligt gränssnitt om du använder det enhetliga skalet som Experience Manager Guides-gränssnitt). När du markerar logotypen dirigeras du till Experience Manager navigeringssida.

![](images/aem-home-header.png){align="left"}

## Navigeringsfält

Verktygen för navigeringsfältets ytor för att växla navigering, anpassa översiktslayouten och justera sidvyn. Den visar också den aktuella mappprofilen som används.

>[!NOTE]
>
> Om du använder Adobe Experience Manager Guides as a Cloud Service visas ytterligare en funktion som heter **AI Assistant** i navigeringsfältet.

![](images/aem-home-nav-bar.png){align="left"}

De funktioner som är tillgängliga i navigeringsfältet förklaras på följande sätt:

- **Navigeringsväljare**: Gör det möjligt att navigera till andra sidor utan synliga skarvar:
   - **Hem**: Standardsidan som du visar när du loggar in på Experience Manager Guides.
   - **Redigeraren**: En lättanvänd webbaserad redigerare där du kan skapa och hantera strukturerade dokument i Experience Manager Guides. [Lär känna redigeringsgränssnittet](./web-editor.md).
   - **Kartkonsol**: Ger dig en dedikerad arbetsyta för att hantera alla aspekter av karthantering och publicering. [Lär dig mer om gränssnittet i kartkonsolen](./map-console-overview.md).
- **AI Assistant**: Ett kraftfullt AI-drivet verktyg som har utformats för att öka din produktivitet med smarta hjälpfunktioner. När du arbetar i redigeringsgränssnittet kan du dessutom utnyttja de smarta redigeringsfunktionerna i AI Assistant som gör redigeringsprocessen smartare och snabbare med intelligenta förslag på återanvändning och optimering av innehåll.

  Funktionen [AI-assistenten](./ai-assistant.md) är för närvarande bara tillgänglig för Adobe Experience Manager som Cloud Service.
- **Anpassa översiktsavsnittet**: Gör att du kan dölja eller visa widgetar i widgetavsnittet.
- **Mappprofilen används**: Visar den mappprofil som används för närvarande.
- **Fler åtgärder**: Ger åtkomst till ytterligare alternativ. Om du väljer den här knappen öppnas en meny med följande alternativ:

   - **Assets**: Flyttar dig till ett mål baserat på din konfiguration.
      - **Molntjänster**: Om du använder molntjänster kan du gå till AEM navigeringssida genom att välja alternativet **Assets** .

      - **Lokal programvara**: Om du använder Adobe Experience Manager Guides (4.2.1 och senare) kan du välja alternativet **Assets** för att komma till den aktuella filsökvägen i Assets användargränssnitt.
   - **Workspace-inställningar**: Öppnar dialogrutan **Workspace-inställningar**. Mer information finns i [Konfigurera Workspace-inställningar](../cs-install-guide/workspace-settings.md).

     >[!NOTE]
     >
     > På startsidan är alternativet för Workspace-inställningar bara tillgängligt för installation av molntjänster. I en lokal konfiguration är alternativet Fler åtgärder inte tillgängligt på hemsidan. Du kan dock fortfarande komma åt de relevanta inställningarna via redigeringsgränssnittet och kartkonsolen genom att gå till Fler alternativ > Inställningar.

- **Expandera vy**: Gör att du kan expandera sidvyn med hjälp av ikonen **Expandera** . I den här vyn är sidhuvudsfältet dolt och innehållsområdet maximeras. Om du vill gå tillbaka till standardvyn använder du ikonen **Avsluta den expanderade vyn** .

## Vänster panel

I den vänstra panelen får du snabb åtkomst till funktionerna Översikt, Kartsamlingar, Masspublicering, Publiceringskö och Användarinställningar. Du kan expandera panelen genom att markera ikonen **Expandera** som finns i det nedre vänstra hörnet av gränssnittet. När du har expanderat använder du ikonen **Komprimera** för att komprimera panelen.

![](images/aem-home-left-panel.png){width="300" align="left"}

Vad du visar på den här panelen beror på din användarroll. I följande tabell visas de roller och de respektive avsnitt som visas på den vänstra panelen.

- **Admin &amp; Publisher**: Möjlighet att visa alla avsnitt i panelen.
- **Författare**: Möjligheten att visa alla avsnitt utom publicering. Författare har inte tillgång till Mappningssamlingar, Publiceringskö och Publiceringskö i grupp.
- **Granskare**: Det går endast att visa översiktsavsnittet. Om du väljer översiktsavsnittet visas antingen ett tomt standardmeddelande eller Workfront-åtgärdswidgeten beroende på om Adobe Workfront är konfigurerat.


De funktioner som är tillgängliga i den vänstra panelen förklaras på följande sätt:

- [Ökning](#overview)
- [Mappa samlingar](#map-collections)
- [Masspublicera](#bulk-publish)
- [Publiceringskö](#publish-queue)
- [Användarinställningar](#user-preferences)

>[!NOTE]
>
> Om administratören har konfigurerat Adobe Workfront-integrering i systemet visas dessutom ett **Workfront**-alternativ i den vänstra panelen. Läs mer om [Adobe Workfront-integrering](./workfront-integration.md) i Experience Manager Guides.


### Ökning

**Översikt** fungerar som en anpassad kontrollpanel som utformats för att öka produktiviteten. Den innehåller olika widgetar som hjälper dig att vara organiserad och fokuserad.

Widgetarna innehåller även alternativ för att sortera och ändra storlek på kolumner. Om du vill visa de här alternativen markerar du kolumnrubriken så visas alternativen i en lista.


Följande widgetar finns i widgetavsnittet:

- **Senaste filer**: I widgeten finns en ögonblicksbild av nyligen öppnade filer (en lista med filer som du har öppnat i Redigeraren) tillsammans med nyckelfilinformationen, inklusive namn, filnamn, filtyp, filsökväg och datum för åtkomst.

  ![](images/aem-home-recent-files.png){align="left"}

  Du kan sortera och ändra storlek på kolumnerna genom att välja alternativ på den nedrullningsbara menyn för kolumner. Som standard sorteras data baserat på senaste åtkomstdatum och -tid.

  ![](images/aem-home-recent-files-sort-resize-options.png){align="left"}


  Från [Användarinställningar](#user-preferences) kan du ange det maximala antalet filer som kan visas i den här widgeten. Som standard är den här gränsen inställd på **20**.

  Följande alternativ är tillgängliga när du hovrar över en fil:

   - **Öppna i redigeraren**: Gör att du kan öppna filen i redigeraren. Du kan också öppna en fil genom att markera den.
   - **Fäst/ta bort**: Gör att du kan fästa en eller flera filer i widgeten Senaste filer. Fastnålade filer visas högst upp i widgetlistan. Använd alternativet **Ta bort** om du vill ta bort en fil.
   - **Ta bort**: Gör att du kan ta bort filen från widgeten Senaste filer.

  **Skapa ny fil från listrutan Ny fil**

  Med listrutan **Ny fil** kan du skapa ett ämne eller en DITA-karta direkt från widgeten **Senaste filer**. När filen har skapats omdirigeras du till redigeringsgränssnittet där du kan arbeta med filen.

- **Samlingar**: Om du arbetar med en uppsättning filer eller mappar kan du lägga till dem i den här widgeten för att komma åt dem snabbt. När du har lagt till dem kan du visa filerna efter namn tillsammans med annan nyckelinformation som Ägare och Skapad den. När du väljer listrutan för kolumner kan du visa alternativen för att sortera och ändra storlek på kolumnen.


  ![](images/aem-home-collections.png){align="left"}

  Den markerade samlingens vägbeskrivningar visas högst upp i samlingswidgeten. Du kan markera den om du vill gå tillbaka till en viss mapp i hierarkin.

  ![](images/aem-home-collections-breadcrumbs.png){align="left"}

  Följande alternativ är tillgängliga när du hovrar över en samling och väljer ikonen Mer ![](images/Smock_MoreSmallList_18_N.svg):

   - **Byt namn**: Gör att du kan byta namn på samlingen.
   - **Ta bort**: Låter dig ta bort samlingen.
   - **Visa i Assets-gränssnitt**: Gör att du kan öppna samlingen i Assets-gränssnittet.

  Du kan öppna en samling genom att välja samlingsrubriken. Följande alternativ är tillgängliga när du håller muspekaren över en samlingsfil och väljer ikonen Mer ![](images/Smock_MoreSmallList_18_N.svg):

   - **Öppna i redigeraren**: Gör att du kan öppna filen i redigeraren. Du kan också välja filnamnet för att öppna filen.
   - **Öppna i kartkonsol**: Gör att du kan öppna kartfilen i kartkonsolen. (Endast tillgängligt för en DITA-kartfil).
   - **Lägg till i samlingar**: Gör att du kan lägga till filen i en ny eller befintlig samling.
   - **Ta bort från samlingar**: Gör att du kan ta bort filen från samlingslistan.
   - **Visa i Assets-användargränssnitt**: Gör att du kan hitta filen i Assets användargränssnitt.

  **Skapa en ny samling från listrutan Ny samling**

  Med listrutan **Ny samling** kan du skapa en ny samling och lägga till den i widgeten **Samlingar**.

>[!NOTE]
>
> Om din administratör dessutom har konfigurerat Adobe Workfront-integrering i systemet visas **Widgeten** för dina uppgifter även i widgetavsnittet. Läs mer om [Adobe Workfront-integrering](./workfront-integration.md#working-with-the-your-tasks-widget) i Experience Manager Guides.

### Mappa samlingar

I Experience Manager Guides kan du ordna ditt innehåll för publicering med hjälp av en kontrollpanel som kallas **Kartsamlingar**. Om du vill använda den här funktionen väljer du **Mappa samlingar** på den vänstra panelen. Den tar dig till sidan Kartsamlingar i **Assets-gränssnittet** där du kan [använda kartsamling för att generera utdata.](./generate-output-use-map-collection-output-generation.md)

### Publicera satsvis

Med funktionen för massaktivering kan du snabbt och enkelt aktivera ditt innehåll från redigering till publiceringsinstans. Om du vill använda den här funktionen väljer du **Masspublicera** på den vänstra panelen. Den tar dig till sidan Samlingar för massaktivering i Assets-gränssnittet där du kan skapa och hantera [massaktivering av publicerat innehåll](./conf-bulk-activation.md).

### Publiceringskö

När du har ett stort antal publiceringsuppgifter som körs på datorn blir det praktiskt taget omöjligt att kontrollera varje DITA-karta individuellt för att övervaka dess publiceringsuppgift. Experience Manager Guides ger administratörer och utgivare en enhetlig översikt över alla publiceringsuppgifter som körs i systemet.

Om du vill använda den här funktionen väljer du **Publiceringskö** i den vänstra panelen. Den tar dig till sidan Publish Dashboard i Assets-användargränssnittet där du kan [hantera publiceringsuppgifter med hjälp av publiceringspanelen](./generate-output-publish-dashboard.md).

### Användarinställningar

Användarinställningarna är tillgängliga för alla författare. Med hjälp av inställningarna kan du konfigurera följande inställningar:

- **Allmänt**: På fliken Allmänt kan du konfigurera följande inställningar:

  ![](images/user_preference_editor-new.png){align="left"}

   - **Mappprofil**: Mappprofilen styr olika konfigurationer som är relaterade till villkorsattribut, redigeringsmallar, förinställningar för utdata och redigeringskonfigurationer. Den globala profilen visas som standard. Om administratören har konfigurerat mappprofiler i systemet visas även dessa mappprofiler i listan Mappprofiler.
   - **Bassökväg**: När du öppnar Experience Manager Guides-databasen från Redigeraren visas som standard resurser från /content/dam-platsen. Arbetsmappen finns förmodligen i mappen /content/dam/. Du kan ange grundsökvägen till din arbetsmapp och i databasvyn visas sedan innehållet från den platsen direkt. Detta minskar tiden för åtkomst till din arbetsmapp. När du infogar en referens- eller mediefil i ditt ämne börjar filbläddringsplatsen med mappen inställd i bassökvägen.
   - **Välj rotkarta**: Välj en DITA-mappningsfil för att lösa nyckelreferenser eller ordlisteposter. Den markerade rotkartan har högsta prioritet för att lösa nyckelreferenser. Mer information finns i [Lös nyckelreferenser](./map-editor-other-features.md).
   - **Maximalt antal senaste filer**: Använd det här fältet om du vill ange en maxgräns för de filer som visas i widgeten Senaste filer.
   - **Öppnar inställningar för kartor**: Här kan du välja ett standardbeteende som systemet kommer att följa när en DITA-kartfil öppnas.

- **Utseende**: På fliken Utseende kan du välja teman för programmet och källvyn för innehållets redigeringsområde. Använd den här fliken för att konfigurera följande inställningar:

  ![](images/user_preference_editor_appearance.png){align="left"}

   - **Programtema och Source-vy**: Du kan välja mellan ljusa eller mörka teman för programmet och källvyn. När det gäller ljustemat använder verktygsfälten och panelerna en ljusgrå bakgrund. När det gäller det mörka temat använder verktygsfälten och panelerna en svart färgbakgrund. Välj **Använd enhetstemat** om du vill att Experience Manager Guides ska kunna välja ljusa och mörka teman baserat på temat på din enhet.

     I alla teman visas området för innehållsredigering med vit färgbakgrund i redigeringsvyn.

   - **Redigerarfiler visar konfigurationen**: Välj standardsättet att visa filerna i Redigeraren. Du kan visa fillistan efter filnamnen eller filnamnen från de olika panelerna i redigeringsvyn. Som standard visas filerna som titlar i Redigeraren.

   - **Hitta alltid filer i databasen**: Välj det här alternativet om du vill visa platsen för en fil i databasen när du redigerar den i Redigeraren.
