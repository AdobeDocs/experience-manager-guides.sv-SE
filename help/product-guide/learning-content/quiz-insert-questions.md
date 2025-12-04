---
title: Infoga frågor i ett frågeformulär
description: Lär dig infoga frågor i ett frågeformulär i produktutbildning och -inlärning,
feature: Authoring
role: User
exl-id: dff38476-c078-4970-b967-05a902430015
source-git-commit: 41ea5e91b5ee096ede2eb06dae7a44f01e0c0571
workflow-type: tm+mt
source-wordcount: '476'
ht-degree: 0%

---

# Infoga frågor i en Quiz

Följ de här stegen för att infoga frågor i ett frågeformulär:

1. Välj önskad frågetyp i listrutan **Frågor** i verktygsfältet. Beroende på dina behov kan du lägga till frågor med något av de fyra tillgängliga formaten: Sant eller Falskt, Enkelrätt, Flera korrekta och Matcha följande enligt nedan. Mer information finns i [Frågetyper](#question-types).

   ![](assets/question-types.png){width="650" align="left"}

   När du infogar en fråga och markören är på ett frågeblock läggs den nya frågan till direkt efter det som standard.

   Om du vill infoga en fråga mellan de två befintliga frågorna [infogar du först ett stycke](#insert-paragraph-within-the-quiz) och infogar sedan frågor.

1. En fråga infogas i det valda formatet. Du kan sedan redigera frågan utifrån dina önskemål.

1. Du kan markera en fråga och konfigurera dess egenskaper med panelen **Innehållsegenskaper** . Du kan till exempel ange rätt svar, ange vilka märken som ska tilldelas och definiera eventuella påföljder för felaktiga svar.

   ![](assets/question-properties.png){width="650" align="left"}

1. Spara alla ändringar du har gjort i frågeformuläret.

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

- **Enkelkorrigering**: En fråga med flera alternativ där bara ett svar är korrekt.

  ![](assets/single-correct.png){width="650" align="left"}

- **Sant/falskt**: En satsbaserad fråga där eleverna väljer om det är sant eller falskt.

  ![](assets/true-false.png){width="650" align="left"}


- **Flera korrigeringar**: En fråga med flera alternativ där mer än ett svar kan vara korrekt.

  ![](assets/multi-correct.png){width="650" align="left"}

- **Matcha följande**: Låter eleverna matcha objekt från två listor för att bilda korrekta par. Du kan lägga till nya alternativuppsättningar från panelen **Innehållsegenskaper**. Om du vill öka komplexiteten kan du ta bort ett alternativ från den första listan och ta med en extra matchning i kolumnen Matcha. Detta skapar problem genom att kräva att eleverna kritiskt tänker på vilket alternativ som inte har något direktpar.

  ![](assets/match-the-following.png){width="650" align="left"}

  I publicerade utdata visas frågan **Matcha följande** med en listruta för varje objekt, så att du kan välja rätt matchning bland de tillgängliga alternativen.

  ![](assets/question-type-publishing.png){width="650" align="left"}