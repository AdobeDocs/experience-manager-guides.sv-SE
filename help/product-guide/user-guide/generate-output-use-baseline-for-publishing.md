---
title: Arbeta med baslinje
description: Lär känna användningen av baslinjer i AEM Guides. Lär dig hur du skapar, visar innehåll, redigerar, duplicerar, tar bort, lägger till etiketter och exporterar översatta baslinjer.
exl-id: 0554947f-3038-4fd2-8a62-ac0d4b858e94
feature: Publishing
role: User
source-git-commit: ac83f613d87547fc7f6a18070545e40ad4963616
workflow-type: tm+mt
source-wordcount: '1790'
ht-degree: 0%

---

# Arbeta med baslinje från kartpanelen {#id1825FI0J0PF}

Experience Manager Guides har en baslinjefunktion där användarna kan skapa baslinjer och använda dem för att publicera eller översätta ämnen från olika versioner. De kan också publicera flera förinställningar av samma DITA-karta parallellt.

>[!TIP]
>
> Visa avsnittet *Baslinje* i guiden Bästa metoder för att arbeta med baslinjer.

Administratören kan konfigurera fliken Baslinje på kartkontrollpanelen. Mer information finns på fliken *Konfigurera baslinje i DITA-kartkontrollpanelen* i installations- och konfigurationshandboken.

På fliken **Baslinjer** kan du utföra följande åtgärder:

- [Skapa en baslinje](#create-a-baseline)
- [Visa innehållet i en baslinje](#view-contents-of-a-baseline)
- [Redigera, duplicera eller ta bort baslinjer](#edit-duplicate-or-remove-baselines)
- [Lägga till etiketter i en baslinje](#add-labels-to-a-baseline)

## Skapa en baslinje

Du kan skapa en baslinje med en specifik version av ämnen och refererat innehåll som är tillgängligt på ett visst datum och en viss tid, eller med en etikett definierad för en ämnesversion. Du kan ange versioner av markerade ämnen separat på en baslinje så att de markerade avsnitten och tillhörande versioner inkluderas för generering eller översättning varje gång du använder baslinjen i arbetsflödet för publicering eller översättning.

Så här skapar du en baslinje:

1. Öppna en DITA-kartfil i Assets-gränssnittet och navigera till sidan **Baslinjer**.
2. Välj **Skapa** längst upp till vänster.
3. På sidan Baslinje anger du ett namn för baslinjen i fältet **Baslinjenamn**.

   ![](images/create-baseline-assets-ui.png){width="300" align="left"}

4. Välj något av följande alternativ i **Ange versionen baserat på**:

   - **Etikett**: Välj det här alternativet om du vill välja ämnen enligt den etikett som används för dem. Ange en etikett för att filtrera listan baserat på den angivna strängen. I den filtrerade listan kan du välja en etikett för att välja ämnen och andra resurser med den angivna etiketten.

     När du väljer Etikett får du också ett extra alternativ för att använda den senaste versionen av ämnen som inte har den angivna etiketten. Om du inte markerar det här alternativet och det finns ämnen eller mediefiler som inte har den angivna etiketten, kommer baslinjen inte att kunna skapas. Mer information om hur du lägger till etiketter finns i Använda etiketter.

   - **Version på**: Hämtar ämnesversionen som angivet datum och angiven tid. Observera att den tidpunkt som du anger här motsvarar tidszonen för din Adobe Experience Manager-server. Om servern befinner sig i en annan tidszon hämtas ämnen enligt serverns tidszon och inte enligt den lokala tidszonen.

     När du har markerat en etikett eller version som den är, markeras alla refererade ämnen och mediefiler på kartan därefter. Det här valet av ämnen visas inte i användargränssnittet, men sparas i serverdelen.
5. Välj **Spara**.

## Visa innehållet i en baslinje

Du kan visa innehållet i en befintlig baslinje genom att välja fliken Baslinje och sedan välja önskad baslinjeversion i listan. Sidan Baslinjer är uppdelad i tre delar - DITA-kartfil, kartans innehåll eller ämnen samt det refererade innehållet. Om kartan innehåller underkartor visas även de ämnen som refereras från underkartan i innehållsavsnittet. De olika kolumnerna på sidan Baslinje beskrivs nedan:

- **Namn**: Visar DITA-kartan eller objektets rubrik eller namnet på resursen, t.ex. filnamnet för en bild.

- **Typ**: Visar typ eller typ av resurs på kartan, t.ex. DITA-karta, DITA-avsnitt eller bildformat.

- **Version**: Visar vilken version av resursen som är tillgänglig på baslinjen.

- **Versionsdatum och -tid**: Visar datum och tid då resursen skapades för den valda versionen.

- **Senaste**: Visar om den senaste versionen av resursen används i baslinjen.

- **Överordnad karta**: Om kartfilen innehåller undermappar innehåller den här kolumnen namnet på den karta som ett ämne refereras till i.

- **Etikett**: Visar etiketten/etiketterna som används i versionen av ämnet.

- **Refererad av**: Den här kolumnen är endast tillgänglig för det refererade innehållet. Den anger det överordnade avsnittet för den refererade resursen. Om en resurs refereras av flera ämnen, separeras ämnena med kommatecken.

## Redigera, duplicera eller ta bort baslinjer

**Redigera baslinjer**

Utför följande steg för att redigera en befintlig baslinje:

1. Markera baslinjen och välj **Redigera**.
1. Gör önskade ändringar i baslinjen. Du kan ändra namn och version för ämnet eller det refererade innehållet.
1. Om du vill använda en annan version för ett eller flera ämnen kan du göra det genom att manuellt markera de ämnena. Välj **Bläddra i ämne** och markera det ämne som du vill använda en annan version för. I listrutan Välj en version för det markerade ämnet väljer du en version av ämnet som du vill använda i baslinjen och sedan **OK**.

   ![](images/baseline-select-version-drop-down.png){align="left"}

   Informationen om ämnet och den valda versionen lagras i serverdelen. Du kan upprepa det här steget om du vill ändra den valda versionen för flera ämnen.

1. Om du vill läsa in alla ämnen och mediefiler som refereras från DITA-kartan väljer du länken **Bläddra bland alla avsnitt** . UUID för ämnen och mediefiler visas också under ämnesrubriken eller filnamnet \(media\).

   >[!NOTE]
   >
   > Om du har en mycket stor uppsättning filer på DITA-kartan, med kapslade kartor och ämnen, kan det ta ett tag att läsa in alla filer om du väljer Bläddra bland alla ämnen.

   Innehållet i kartan visas i tre avsnitt: kartfilen, innehållet \(ämnesreferenser\) och referensinnehållet \(kapslade ämnen, kartor och andra resurser\). När du har allt refererat innehåll tillgängligt kan du välja den version av ämnet som du vill använda i baslinjen.

   Listrutan **Version** visar tillgängliga versioner av avsnitten eller det refererade innehållet. För det refererade innehållet kan du välja en version automatiskt.

   Om du väljer **Välj automatiskt** för det refererade innehållet väljs automatiskt den version av det refererade innehållet som motsvarar den version av innehållet som det refereras till i. Låt oss till exempel säga att ett ämne A har en referens till en bild B. När version 1.5 av avsnitt A skapades var version 1.2 i databasen. När en baslinje skapas med version 1.5 av ämnet A med bild B inställd på **Välj automatiskt** väljs automatiskt version 1.2 av bild B.

   Om du skapar en baslinje med etiketterna används **Välj automatiskt** på versionen av allt refererat innehåll.

   Om det refererade innehållet eller resurserna \(ämne, undermappar, bilder eller videoklipp\) inte har versionsnumret \(t.ex. nyligen överfört innehåll\), skapas en version för sådana filer när du skapar en baslinje. Om filerna har en ny version skapas dock ingen inkrementell version för dessa filer. Det här beteendet styrs av inställningen för att skapa automatiskt, som är aktiverad som standard. Detta krävs också för översättning av innehåll där alla filer förväntas ha en version i översättningsprocessen.

   >[!NOTE]
   >
   > Om du vill ange en annan version för en viss resurs kan du göra det genom att välja önskad version i listrutan **Version**.
1. Välj **Spara**.

**Duplicera baslinjer**

Markera baslinjen och välj **Duplicera** för att skapa en kopia av en befintlig baslinje. Ange ett annat namn för baslinjen, välj versionsnumret för avsnitten och det refererade innehållet och välj **Spara**.

**Ta bort baslinjer**

Markera baslinjeversionen och välj **Ta bort** för att ta bort en baslinje.

## Lägga till etiketter i en baslinje

Det kan vara tidskrävande att lägga till etiketter i varje enskilt ämne. Experience Manager Guides har en funktion för att lägga till etiketter i flera ämnen och refererat innehåll på en DITA-karta med ett enda klick.

Utför följande steg för att lägga till en etikett i flera ämnen och refererat innehåll i en DITA-karta:

1. På sidan Baslinjer väljer du en baslinje som innehåller ämnen och refererat innehåll som du vill lägga till en etikett för.

   >[!NOTE]
   >
   > Se till att baslinjen inte har den senaste versionen av något ämne eller material. En etikett kan bara läggas till i ett versionsämne eller en resurs.

1. Välj **Lägg till etiketter**.

   ![](images/add-label-baseline-uuid.png){align="left"}

1. I dialogrutan **Lägg till etikett** anger du en unik etikett som ska associeras med den här baslinjen.

   Om administratören har konfigurerat fördefinierade etiketter visas dessa i en listruta. Du måste välja en etikett i listan.

1. Om du vill använda etiketten för ämnen som refereras från undermappningarna väljer du alternativet **Använd etikett på underordnade kartor och deras underordnade kartor** .

   - Välj **Lägg till**.
Den angivna etiketten läggs till på DITA-kartan och de ämnen och innehåll som refereras.

     ![](images/label-added-baseline-uuid.png){width="650" align="left"}


## Exportera översatt originalplan

Du kan använda Baslinje för översättning av innehåll. Du kan till exempel skapa en baslinje för version 1.1 som är klar för översättning på franska. På fliken Översättning måste du använda Baslinje för att filtrera innehållet och sedan välja Baslinje för version 1.1 av innehållet. Genom att använda Baslinje för översättning av innehåll blir det enklare för dig att hantera ditt innehåll.

När innehållet har översatts kan du exportera den översatta baslinjen för arkivering eller dela den med olika team i organisationen. Du måste tänka på följande innan du exporterar en översatt baslinje:

- Det går bara att exportera en baslinje efter att innehållet i baslinjen har översatts. Om du försöker exportera en baslinje för vilken översättningen inte har startats eller inte är fullständig visas ett felmeddelande.
- Du kan bara överföra baslinjen för en version som redan är översatt. Om du t.ex. har skapat en baslinje för version 1.1 av ditt innehåll och samma är översatt, kan du exportera denna baslinje. Om du har skapat en baslinje för version 1.2, som inte är översatt, kan du inte exportera baslinjen.
- Om en baslinje redan har exporterats kan du skriva över den befintliga baslinjen genom att markera alternativet *Skriv över befintlig baslinje* vid exporten.

Utför följande steg för att exportera en översatt baslinje:

1. Öppna DITA-kartan som innehåller den översatta baslinjen.

1. Utöka alternativet **Baslinje** i den vänstra listen på fliken **Översättning**.

   ![](images/export-baseline-new.png){align="left"}

1. Markera alternativet **Använd baslinje** och välj den baslinje som du vill exportera.

1. Välj **Exportera baslinje**.

   Exportstatus visas. Om processen lyckas visas ett meddelande där du anger vilket språk baslinjen ska exporteras för. Om ett fel uppstår visas felorsaken.

   Om du försöker exportera den baslinje som redan har exporterats visas även felmeddelandet när baslinjen skapades.

1. \(Valfritt\) Om du vill exportera en baslinje som redan har exporterats väljer du **Skriv över befintlig baslinje** och sedan **Exportera baslinje**.


**Överordnat ämne:**&#x200B;[ Utdatagenerering](generate-output.md)
