---
title: Databas på startsidan
description: Lär känna databasen på hemsidan. Läs mer om gränssnittet och funktionerna i Adobe Experience Manager Guides på hemsidan.
feature: Authoring
role: User
source-git-commit: 1919e622b1b148d16bcdb85f79e2a1cd706fe33e
workflow-type: tm+mt
source-wordcount: '1298'
ht-degree: 0%

---

# Lär dig gränssnittet Databas

Databasen är ett centraliserat utrymme som gör det enklare att hitta mappar och filer. Den innehåller en omfattande tabellvy över mappar och filer med flera kolumner, med sammanhangsberoende information för alla filer och resurser.

Det enhetliga gränssnittet effektiviserar flera funktioner, t.ex. att skapa nya filer eller mappar, redigera filer, ladda upp material och söka filer med robusta filtreringsfunktioner, vilket ger ökad effektivitet och användarvänlighet.

![](images/repository-view-home.png){align="left"}

Databasgränssnittet är indelat i följande avsnitt:

- Navigeringsfält för databas
- Tabellvy av databas

## Navigeringsfält för databas

Navigeringsfältet Databas, som finns högst upp i databasgränssnittet, ger snabb åtkomst till viktiga åtgärder som listas.

![](images/tab-bar-repository-view.png){align="left"}


- **Mappnavigeringspanelen**: Visar en hierarkisk trädvy med mappar i databasen, vilket möjliggör smidig navigering. I den här panelen visas endast information på mappnivå. När en mapp väljs härifrån visas dess innehåll, filer och undermappar i databasvyn. Du kan visa eller dölja den här panelen med ikonen som är markerad nedan.

  ![](images/folder-navigation-panel.png){align="left"}

- **Bläddra**: Anger den aktuella sökvägen i databasen, med hierarkin för de mappar som leder till den aktuella mappen. Du kan markera den om du vill gå tillbaka till en viss mapp i hierarkin.

  ![](images/breadcrumbs.png){width="650" align="left"}

- **Uppdatera**: Uppdaterar databasen för att återspegla de senaste ändringarna.
- **Överför Assets**: Tillåter att resurser överförs direkt till den aktuella mappen, vilket markeras i de synliga kolumnerna.
- **Nytt**: Gör det möjligt att skapa nya ämnen, kartor och mappar i den aktuella mappen, så som de markerats i kolumnerna.
- **AI Assistant**: Ett kraftfullt AI-drivet verktyg som har utformats för att öka din produktivitet med smarta hjälpfunktioner. Funktionen [AI-assistenten](./ai-assistant.md) är för närvarande bara tillgänglig för Adobe Experience Manager som Cloud Service.
- **Fler åtgärder**: Ger åtkomst till ytterligare alternativ. Om du väljer den här knappen öppnas en meny med följande alternativ:
   - **Assets**: Flyttar dig till ett mål baserat på din konfiguration.
      - **Molntjänster**: Om du använder molntjänster kan du gå till AEM navigeringssida genom att välja alternativet **Assets** .
      - **Lokal programvara**: Om du använder Adobe Experience Manager Guides (4.2.1 och senare) kan du välja alternativet **Assets** för att komma till den aktuella filsökvägen i Assets användargränssnitt.
   - **Workspace-inställningar**: Öppnar dialogrutan **Workspace-inställningar**. Mer information finns i [Konfigurera Workspace-inställningar](../cs-install-guide/workspace-settings.md).
- **Expandera vy**: Gör att du kan expandera sidvyn med hjälp av ikonen **Expandera** . I den här vyn är sidhuvudsfältet dolt och innehållsområdet maximeras. Om du vill återgå till standardvyn använder du ikonen Avsluta den expanderade vyn.

## Tabellvy av databas

Databasen fungerar som en central plats med en lista i tabellformat över alla mappar och filer. Den har följande funktioner:

- **Anpassa**: Du kan ändra de kolumner som visas med alternativet **Anpassa** längst upp till höger i databasvyn. Med det här alternativet kan du visa eller dölja valfri kolumn och även ordna om kolumnerna efter behov. Kolumnerna **Namn** eller **Titel** är obligatoriska och båda kan inte inaktiveras tillsammans. Andra fält, till exempel **Filtyp**, **UID**, **Dokumentläge**, **Låst av**, **Skapat den** och **Ändrat den**, kan aktiveras eller inaktiveras efter behov. Du kan ordna om dem genom att helt enkelt dra och släppa.

  ![](images/customize-repo-view.png){width="350" align="left"}

- **Storleksändring för kolumner**: Du kan ändra storlek på kolumner genom att välja alternativ i den nedrullningsbara menyn för kolumner.

- **Sortering**: Kolumnerna Namn, Titel, Skapad och Senast ändrad har stöd för sortering i stigande eller fallande ordning, som du kommer åt via deras kolumnmeny.

- **Redigerar filen**:

   - Du kan markera en eller flera filer i listan för redigering.
   - När du har markerat önskade filer med kryssrutan blir alternativet **Redigera** tillgängligt i det övre högra hörnet i databasvyn.
   - Om du väljer **Redigera** öppnas de markerade filerna i redigeringsgränssnittet, där du kan börja redigera filen.

     ![](images/edit-repo-view.png){align="left"}

- **Alternativ-menyn för mappar**: Du kan utföra följande åtgärder med **Alternativ** -menyn som är tillgänglig för en mapp:

  ![](images/options-folder-repo.png){width="350" align="left"}

   - **Nytt**: Skapa ett nytt DITA-ämne, en DITA-karta eller en mapp.
   - **Överför Assets**: Överför en fil från ditt lokala system till den valda mappen i databasen.
   - **Lägg till i samlingar**: Lägger till den markerade mappen i favoriter. Du kan lägga till den i en befintlig eller ny samling.
   - **Bearbeta om resurser**: Utlöser bearbetningen av alla nyskapade och obearbetade resurser.

- **Alternativ-menyn för filer**: Du kan utföra följande åtgärder med **Alternativ** -menyn för en fil:

  ![](images/options-file-repo.png){width="350" align="left"}

   - **Redigera**: Öppna filen för redigering.
   - **Redigera i syre**: Välj det här alternativet om du vill redigera den valda filen i syreanslutningens plugin-program.

     >[!NOTE]
     >
     >Kontakta kundgruppen för att aktivera den här funktionen i miljön. Detta är inte aktiverat som en del av det färdiga stödet. Mer information finns i avsnittet [Konfigurera alternativet att redigera i syre](../cs-install-guide/conf-edit-in-oxygen.md) i installations- och konfigurationshandboken.

   - **Öppna i kartkonsol**: Om den valda filen är en DITA-karta öppnas kartkonsolen med det här alternativet.
   - **Öppna på kartkontrollpanelen**: Om den valda filen är en DITA-karta öppnas kartkontrollpanelen med det här alternativet.
   - **Lås**: Lås den markerade filen för redigering.
   - **Förhandsgranska**: Få en snabb förhandsvisning av filen (.dita, .xml, ljud, video eller bild) utan att öppna den.
   - **Duplicera**: Använd det här alternativet om du vill skapa en dubblett eller en kopia av den markerade filen.
   - **Flytta till**: Använd det här alternativet om du vill flytta den markerade filen till en annan mapp.
   - **Byt namn**: Använd det här alternativet om du vill byta namn på den markerade filen.
   - **Ta bort**: Använd det här alternativet om du vill ta bort den markerade filen.
   - **Lägg till i**: Välj om du vill lägga till i samlingar eller återanvändbart innehåll.
   - **Kopiera**: Kopierar filens UUID eller fullständiga sökväg.
   - **Egenskaper**: Använd det här alternativet om du vill öppna sidan Egenskaper för den markerade filen.
   - **Hämta som PDF**: Använd alternativet för att generera PDF-utdata och hämta dem.

### Sökning och filtrering

Alternativet **Sök** hjälper dig att söka efter de filer som krävs från databasen huvudsakligen utifrån **filtiteln**, **filnamnet** och **innehållet**. Du kan använda ett, två eller alla tre villkor för sökningen. Om inget av villkoren är markerat, kommer resultatet att innehålla gemensamma värden för alla tre kriterierna.

![](images/search-in-repository.png){align="left"}

Välj ikonen **Filtersökning** \(![Sökfilterikon](images/filter-search-icon.svg)\) för att öppna filterpanelen till höger.

![](images/Search-filters-repo.png){align="left"}

Du har följande alternativ för att filtrera filerna och begränsa sökningen:

- **Sök i**: Välj den sökväg där du vill söka efter filerna som finns i databasen.

- **Filtyp**: Du kan söka efter alla **DITA-avsnitt**, **DITA-kartor**, **DITAVAL-filer**, **Bildfiler**, **Multimedia**, **Dokument** och **JSON**.

- **Låst av**: Visar en lista över användare. Listan sidnumreras och läses in asynkront, med en begränsad uppsättning användare åt gången och fler hämtas när du rullar eller navigerar. Detta förbättrar inläsningshastigheten och övergripande prestanda, särskilt när du arbetar med ett stort antal användare.

- **Senast ändrad**: Filtrera innehåll baserat på ändringsdatum. Välj ett datumintervall i kalendern eller välj något av följande alternativ för tidsram:
   - I förra veckan
   - Under den senaste månaden
   - Under förra året

- **Taggar**: Filtrera innehåll baserat på taggar.

- **DITA-element**: Filtrera innehåll baserat på olika DITA-element.

När du har använt alla nödvändiga filter väljer du **Använd** längst ned till höger på panelen Filter.

Sökresultat som har anpassats enligt det valda filtret visas endast som en **tabelllista med filer** (mappar visas inte). Du kan ta bort ett filter individuellt eller flera filter samtidigt, och resultatet uppdateras för att återspegla den uppdaterade markeringen.

![](images/search-results-with-filters.png){align="left"}

När sökresultaten visas kan du antingen markera flera filer och öppna dem i redigeraren med ikonen **Redigera** eller arbeta med alla resultat genom att skicka sökresultaten till redigeraren med alternativet **Visa i sökpanelen** .

![](images/post-search-operation.png){align="left"}

**Visa i sökpanelen**

Alternativet **Visa i sökpanelen** blir tillgängligt efter en sökning i databasen. Med den här funktionen kan du visa alla sökresultat på **sökpanelen** i redigeraren. Mer information finns i [sökpanelen](./search-panel-explorer.md).

![](images/search-panel-repo.png){align="left"}

