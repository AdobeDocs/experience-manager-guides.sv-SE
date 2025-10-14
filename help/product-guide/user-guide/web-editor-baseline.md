---
title: Skapa och hantera baslinjer från kartkonsolen
description: Skapa och hantera baslinjer från kartkonsolen i Adobe Experience Manager Guides. Lär dig hur du skapar baslinjer baserat på etiketter och tillämpar filter på baslinjerna.
exl-id: 14f87bdd-3042-46f9-853e-e9ded81b10ed
feature: Authoring, Features of Web Editor, Publishing
role: User
source-git-commit: c7e76de14a3dd63eff794ecca16ebbccb3cb2d8a
workflow-type: tm+mt
source-wordcount: '1881'
ht-degree: 0%

---

# Skapa och hantera baslinjer från kartkonsolen {#id223MB0ZF043}

Med funktionen Baslinje kan du skapa en version av dina ämnen och resurser som sedan kan användas för publicering eller översättning. Om din DITA-karta till exempel har `topicA` och `imageA` kan du skapa en baslinje som använder den tredje versionen av `topicA`, men den fjärde versionen av `ImageA`. När du har en originalplan kan du publicera eller översätta ämnen från olika versioner i ett enda steg.

Det är valfritt att välja en baslinje för förinställningar och en DITA-karta kan ha mer än en baslinje. Varje förinställning i en DITA-karta kan emellertid bara kopplas till en baslinje. Om ingen baslinje har angetts vid publiceringen publiceras utdata med den senaste versionen av innehållet.

På samma sätt är det valfritt att markera en baslinje för att översätta innehåll. Om du väljer att översätta innehåll med hjälp av en baslinje, sparas innehållet i baslinjen också tillsammans med de översatta kopiorna. Du kan sedan använda den översatta baslinjen för att utföra ytterligare åtgärder som att dela den med externa utgivare eller arkivera den.


>[!TIP]
>
> Vi rekommenderar att du använder den här baslinjefunktionen från kartkonsolen. Du kan även [använda kartkontrollpanelen för att skapa och hantera baslinjer](./generate-output-use-baseline-for-publishing.md).

På fliken **Baslinje** kan du utföra följande åtgärder:

- [Skapa en baslinje](#create-a-baseline)
- [Hantera baslinjer](#manage-baselines)


## Skapa en baslinje

Du kan skapa en baslinje från kartkonsolen genom att utföra följande steg:

1. [Öppna DITA-kartfilen i kartkonsolen](./open-files-map-console.md).
1. Navigera till fliken **Baslinje** och välj ikonen + längst upp till höger för att börja skapa en baslinje.
1. Ange följande information i dialogrutan **Ny baslinje**:

   ![Panelen Baslinje](images/baseline-manage.png){width="500" align="left"}

   - Ange ett namn för baslinjen i fältet **Namn**.
   - Välj [Manuell uppdatering](#configuring-baseline-for-manual-update) eller [Automatisk uppdatering](#configuring-baseline-for-automatic-update) i **Konfiguration**.
   - Välj **Använd**.

Baslinjen skapas. Baslinjen skapas asynkront, så du kan fortsätta arbeta med andra filer. När baslinjen har skapats visas ett popup-meddelande som bekräftar att baslinjen har skapats, och du får även ett inkorgsmeddelande för det.

### Konfigurera baslinje för manuell uppdatering

Du kan skapa en statisk baslinje manuellt med en specifik version av ämnen och refererat innehåll som är tillgängligt på ett visst datum och en viss tid, eller med en etikett definierad för en ämnesversion:

I **Markera versionen baserat på** väljer du ett av följande alternativ:

- **Datum** : Hämtar ämnesversionen som angivet datum och angiven tid.
- **Etikett**: Välj det här alternativet om du vill välja ämnen enligt den etikett som används för dem. Om rubrikerna har etiketter som är angivna för dem visas etiketterna i listrutan. Du kan välja en etikett i listan. Du kan också lägga till en etikett i textrutan.

  >[!NOTE]
  >
  > När du väljer etiketter visas etikettinläsaren tills alla etiketter har hämtats och lästs in fullständigt. När etiketterna har lästs in visas de i en skiftlägesokänslig alfabetisk ordning. De hämtas i grupper om 20, med oändlig rullning aktiverat i listrutan för att läsa in ytterligare grupper när du rullar.

  För direkta referenser i statiska baslinjer hämtas etiketterna från den senaste sparade versionen av kartan. Om du till exempel har skapat etiketterna `Label Release 1.0` och `Label Release 1.1` för versionerna 1.0 och 1.1 i ämne A och sedan lägger till ämne A i kartan som sparats som version 1.0. I det här fallet kan du visa etiketterna `Label Release 1.0` och `Label Release 1.1` i listrutan för statiska baslinjeetiketter.

  När du väljer **Etikett** kan du välja direkta och indirekta referenser.
   - För direkta referenser inom DITA-kartan får du ett alternativ att använda den senaste versionen av ämnen som inte har den angivna etiketten.

     >[!NOTE]
     >
     > Om du anger en etikett som inte finns och väljer alternativet **Skapa inte en baslinje** misslyckas baslinjen och ett felmeddelande visas nära baslinjenamnet på baslinjepanelen.

   - För indirekta referenser inom DITA-kartan får du ett extra alternativ att använda den senaste versionen av ämnen som inte har den angivna etiketten. Du kan också välja att **välja automatiskt** för det refererade innehållet, så väljs automatiskt den version av det refererade innehållet som motsvarar den version av innehållet som det refereras till i.

När du har markerat en etikett eller version som den är, markeras alla refererade ämnen och mediefiler på kartan därefter. Det här valet av ämnen visas inte i användargränssnittet, men sparas i serverdelen.

### Konfigurera baslinje för automatisk uppdatering

Välj det här alternativet för att skapa baslinjen om du automatiskt vill välja ämnen enligt den etikett som används på dem.

Baslinjer som skapas med den automatiska uppdateringskonfigurationen uppdateras dynamiskt. Om du genererar en baslinje, hämtar en baslinje eller skapar ett översättningsprojekt med hjälp av en baslinje, hämtas filerna dynamiskt baserat på de uppdaterade etiketterna. Om du till exempel har använt version 1.2 av ett ämne med Label Release 1.0 för baslinjen och senare uppdaterat version 1.5 med Label Release 1.0, uppdateras baslinjen dynamiskt och version 1.5 används.

![Skapa en baslinje](images/dynamic-baseline.png){width="300" align="left"}

- **Etiketter**: Om ämnena har etiketter angivna för dem använder du listrutan **Etiketter** och väljer bland de [listade etiketterna](#labels-list).

  De etiketter som är markerade först får högre prioritet än de som väljs senare.

  >[!NOTE]
  >
  >När etiketterna hämtas visas en inläsare och listrutan inaktiveras.

  För dynamiska baslinjer hämtas etiketterna från den senaste sparade versionen och den aktuella arbetskopian av kartan. Om du till exempel har skapat etiketter   `Label Release A.1.0 ` och `Label Release A.1.1` för version 1.0 och 1.1 av ämne A och etiketter `Label Release B.1.0` och `Label Release B.1.1` för version 1.0 och 1.1 av ämne B. Sedan kan du lägga till ämne A i karta A i version 1.0 och ämne B i karta A i 1.0* (arbetskopia). I det här fallet kan du visa `Label Release A.1.0 `, `Label Release A.1.1`, `Label Release B.1.0` och `Label Release B.1.1` i listrutan med dynamiska baslinjeetiketter.
- **Indirekta referenser**: För indirekta referenser inom DITA-kartan får du följande alternativ:

   - **Välj automatiskt**: Du kan välja att **Välj automatiskt** för det refererade innehållet, och systemet väljer automatiskt den version av det refererade innehållet som motsvarar versionen av det refererade innehållet.
   - **Använd markerad etikett**: Du kan skapa en baslinje med den markerade etiketten definierad för en ämnesversion.
   - **Använd den senaste versionen eller arbetskopian**: Använd den senaste versionen av ämnen som inte har den angivna etiketten tillämpad på dem, eller om ingen version har skapats, använd arbetskopian av ämnena för att skapa baslinjen.

## Hantera baslinjer

Du kan hantera befintliga baslinjer med hjälp av de olika funktionerna på kontrollpanelen för baslinjer.

- Du kan söka efter en befintlig baslinje med textrutan på panelen Baslinje. Använd ikonen **Använd filter** för att visa alla baslinjer eller lista baslinjerna med status Slutförd, Pågående eller Misslyckad.
- Använd ikonen **Uppdatera** på panelen Baslinje om du vill kontrollera alla baslinjer och visa en ny lista med baslinjer för DITA-kartan som öppnas i Kartvyn.
- Markera baslinjen om du vill visa eller redigera innehållet i en befintlig statisk baslinje på panelen **Baslinje**. Baslinjeredigeringsfönstret visar DITA-kartfilen, kartans innehåll eller ämnen samt det refererade innehållet.

  >[!NOTE]
  >
  >Redigeringsåtgärden för statiska baslinjer rekommenderas bara för ett litet antal referensändringar. Redigeringsåtgärden rekommenderas inte för att ändra versionen av DITA-huvudkartan eftersom alla referenser måste beräknas om. Detta kan orsaka ett baslinjeuppdateringsfel för stora DITA-kartor. För större DITA-scheman kan du skapa en ny baslinje eller redigera egenskaperna för baslinjen.
  >
  >Redigera om det är en dynamisk baslinje kan du redigera egenskaperna för baslinjen eftersom referenserna för dynamiska baslinjer genereras vid körning med hjälp av etiketterna.

  ![alternativ för en baslinje](images/baseline-options.png){width="500" align="left"}

### Tillgängliga åtgärder för en befintlig baslinje

Du kan även utföra följande åtgärder på baslinjen på Alternativ-menyn:

**Duplicera en baslinje**

Du kan duplicera en baslinje och ändra den enligt dina önskemål.

![duplicera en baslinje](images/baseline-duplicate.png){width="300" align="left"}
*Duplicera en baslinje baserat på en etikett eller skapa en exakt kopia.*

1. Välj **Duplicera** på Alternativ-menyn för en baslinje. Dialogrutan **Duplicera baslinje** öppnas.
>[!NOTE]
>
>Baslinjens standardnamn är `<selected baseline name>`_suffix (som sample-baseline_1). Du kan ändra namnet enligt dina önskemål.

   I **Markera versionen baserat på** kan du antingen välja alternativet **Exakt kopia** eller alternativet **Etikett**:

   - **Exakt kopia**: Experience Manager Guides väljer samma version av alla ämnen och skapar en exakt kopia av den duplicerade baslinjen.
   - **Etikett**: Med listrutan kan du välja någon av de [listade etiketterna](#labels-list). Experience Manager Guides väljer de versionerna av ämnena med den valda etiketten som definierats för dem, medan den för de återstående avsnitten väljer versionen från den duplicerade baslinjen. Du kan till exempel välja etiketten `Release 1.0` i listrutan och sedan välja de versioner av avsnitten som du har definierat den här etiketten för. För alla andra ämnen väljs versionen från den duplicerade baslinjen.
1. Välj **Duplicera**.

- **Byt namn på** eller **Ta bort** en befintlig baslinje**.
- **Hantera etiketter** som gör att du kan lägga till, ta bort eller ändra befintliga etiketter för statiska baslinjer. Om administratören har konfigurerat fördefinierade etiketter visas dessa etiketter i listrutan Lägg till etikett. Mer information om hur du lägger till etiketter finns i [Använd etiketter](web-editor-use-label.md#).

  >[!NOTE]
  >
  > Processen att lägga till eller ta bort etiketter sker asynkront, så du kan fortsätta arbeta med andra filer. När etiketten har lagts till eller tagits bort visas ett popup-meddelande som bekräftar att etiketten har lagts till eller tagits bort, och du får även ett inkorgsmeddelande om detta.

- **Redigera egenskaper** för en befintlig statisk baslinje som du angav när du skapade baslinjen.
- Alternativet **Exportera baslinje** exporterar en ögonblicksbild av baslinjen i Microsoft Excel-filen, inklusive all viktig information, till exempel titel, filnamn, filtyp, versionsnummer, dokumenttillstånd och annan relevant information.


### Förteckning över etiketter {#labels-list}

Etiketterna i listrutan baseras på följande kriterier:
- Etiketterna ska läggas till i en av versionerna av avsnitten i DITA-kartan (som baslinjen skapas på).
- Och bara de första nivåreferenserna (ämnen eller undermappar) i DITA-kartan beaktas när etiketterna väljs.

## Baslinjefilter

Med ikonen Filter på panelen **Baslinjefilter** kan du använda filter på baslinjen som är öppen i redigeringsfönstret för baslinjen:

![baslinjefilter](images/baseline-filter.png){width="300" align="left"}

- Filtrera filerna baserat på filnamn eller filplats.
- Filtrera filerna baserat på värdena för olika kolumner som filtyp, referenstyp och så vidare.
- Välj de kolumner som ska visas i redigeringsfönstret för baslinjen.

>[!NOTE]
>
> Du kan markera en kolumnrubrik och sortera filerna baserat på kolumnerna i redigeringsfönstret för baslinjen.

**Spara eller återställa en baslinje**

När du har redigerat baslinjen väljer du **Spara** om du vill spara ändringarna i baslinjen. Du kan välja **Återställ** om du inte vill spara ändringen och återställa baslinjen. När du väljer **Återställ** visas en varning om att ändringar som inte sparats går förlorade.

**Överordnat ämne:**&#x200B;[&#x200B; Utdatagenerering](generate-output.md)

