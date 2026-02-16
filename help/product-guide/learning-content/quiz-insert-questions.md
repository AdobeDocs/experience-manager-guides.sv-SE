---
title: Infoga frågor i ett frågeformulär
description: Lär dig infoga frågor i ett frågeformulär i produktutbildning och -inlärning,
feature: Authoring
role: User
exl-id: dff38476-c078-4970-b967-05a902430015
source-git-commit: 1df47cf35590f10bdfe7fdbc3501d7c47137ed56
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 0%

---

# Infoga frågor i en Quiz

Följ de här stegen för att infoga frågor i ett frågeformulär:

1. Välj önskad frågetyp i listrutan **Frågor** i verktygsfältet. Beroende på dina behov kan du lägga till frågor i något av de fyra tillgängliga formaten: Sant eller Falskt, Enkelrätt, Flera korrekta, Matcha följande och Kort svar enligt nedan. Mer information finns i [Frågetyper](#question-types).

   ![](assets/question-types.png){width="650" align="left"}

   När du infogar en fråga och markören är på ett frågeblock läggs den nya frågan till direkt efter det som standard.

   Om du vill infoga en fråga mellan de två befintliga frågorna [infogar du först ett stycke](#insert-paragraph-within-the-quiz) och infogar sedan frågor.

1. En fråga infogas i det valda formatet. Du kan sedan redigera frågan utifrån dina önskemål.

1. Du kan markera en fråga och konfigurera dess egenskaper med panelen **Innehållsegenskaper** .

   ![](assets/question-properties.png){width="650" align="left"}

1. Spara alla ändringar du har gjort i frågeformuläret.


## Frågeegenskaper

Du kan konfigurera frågorna med följande frågeegenskaper från panelen **Innehållsegenskaper**:

![](assets/question-properties-new.png){width="350" align="left"}

- **Alternativ**: Ange rätt svar på frågan
- **Fråga-ID**: Anger fråge-ID för varje fråga. Om det inte finns något fråge-ID bör du alltid lägga till det.
- **Poäng för korrekt svar**: Ange poäng som ska tilldelas för rätt svar.
- **Påföljd för felaktigt svar**: Ange vilka poäng som ska dras av för ett felaktigt svar.
- **Frågeetikett**: Aktivera om du vill lägga till en frågeetikett.
- **Feedback**: Aktivera för att ge feedback för korrekt eller felaktigt svar.
- **Fäst alternativet vid position**: När ett visst alternativ för en fråga är fäst är det fortfarande fast på den angivna positionen i alternativlistan, även om **Slumpmässigt svarsalternativ för varje försök** är aktiverat i SCORM-förinställningskonfigurationen, som annars skulle ändra de tillgängliga alternativen. Du kan hålla muspekaren över önskat alternativ för en fråga på panelen Innehållsegenskaper och fästa den.

  ![](assets/pin-question.png){width="350" align="left"}

## Infoga stycke i frågeformuläret

När du placerar markören på en fråga eller ett tomt utrymme mellan de två frågorna visas en blå vågrät linje med en blå pil längst till höger på skärmen. Om du väljer den blå pilen kan du infoga ett stycke i frågeformulärsredigeringsgränssnittet.

![](assets/insert-paragraph-here-arrow.png){width="650" align="left"}

- När det används i en fråga kan du lägga till fler element som bilder, tabeller, textelement och mycket mer i frågan.
- Du kan använda det mellan frågorna för att infoga en annan fråga eller lägga till andra redigeringselement som nämns ovan.

## Ta bort fråga eller alternativ

Så här tar du bort en fråga eller ett specifikt alternativ från ett frågeformulär:

1. Högerklicka på frågan eller alternativet som du vill ta bort.
1. Välj **Ta bort fråga** (om du vill ta bort hela frågan) eller **Ta bort alternativ** (om du bara vill ta bort det markerade alternativet) på snabbmenyn.

![](assets/delete-options-lc.png){width="650" align="left"}

## Frågetyper

Följande frågetyper stöds i en Quiz:

- **Enkelt korrekt**: En fråga med flera alternativ där bara ett svar är korrekt.

  ![](assets/single-correct.png){width="650" align="left"}

- **Sant/falskt**: En satsbaserad fråga där eleverna väljer om det är sant eller falskt.

  ![](assets/true-false.png){width="650" align="left"}


- **Flera korrekta**: En fråga med flera alternativ där mer än ett svar kan vara korrekt.

  ![](assets/multi-correct.png){width="650" align="left"}

- **Matcha följande**: Låter eleverna matcha objekt från två listor för att bilda korrekta par. Du kan lägga till nya alternativuppsättningar från panelen **Innehållsegenskaper**. Om du vill öka komplexiteten kan du ta bort ett alternativ från den första listan och ta med en extra matchning i kolumnen Matcha. Detta skapar problem genom att kräva att eleverna kritiskt tänker på vilket alternativ som inte har något direktpar.

  ![](assets/match-the-following.png){width="650" align="left"}

  I publicerade utdata visas frågan **Matcha följande** med en listruta för varje objekt, så att du kan välja rätt matchning bland de tillgängliga alternativen.

  ![](assets/question-type-publishing.png){width="650" align="left"}


- **Kort svar**: Låter eleverna svara med en kort textinmatning. Den accepterar alfanumeriska svar, matchar svar inte skiftlägeskänsligt och för mycket långa svar innehåller den en vågrät rullningslist.

  ![](assets/short-answer.png){width="650" align="left"}
