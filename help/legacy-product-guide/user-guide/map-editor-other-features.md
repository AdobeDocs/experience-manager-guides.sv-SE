---
title: Andra funktioner i kartredigerarna
description: Upptäck några vanliga funktioner i de grundläggande och avancerade kartredigeringsprogrammen. Lär dig hur du löser nyckelreferenser i kartredigeraren.
feature: Authoring, Map Editor
role: User
source-git-commit: fa07db6a9cb8d8f5b133258acd5647631b22e28a
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 0%

---

# Andra funktioner i kartredigerarna {#id1942D0T0HUI}

Några vanliga funktioner i grundläggande och avancerade kartredigerare är:

## Lös nyckelreferenser {#id176GD01H05Z}

En DITA-innehållsnyckelreferens, eller `conkeyref`, är en mekanism som infogar en del av innehåll från ett ämne i ett annat. Den här mekanismen använder nyckel för att hitta det innehåll som ska återanvändas i stället för den direkta mekanismen för innehållsreferens. Mer information om direkt och indirekt referens i DITA finns i *DITA-adressering* i språkspecifikationen för OASIS DITA.

Om DITA-avsnittet har associerade nyckelreferenser måste de lösas innan du förhandsgranskar, redigerar eller granskar ett ämne.

Nyckelreferenserna tolkas utifrån rotmappningen i följande prioritetsordning:

1. Användarinställningar
1. Kartvyn, panel
1. Mappprofil

Rotmappningen som är markerad i användarinställningarna har den högsta prioriteten för att matcha nyckelreferenser följt av mappvypanelen och mappprofilens rotmappning. Om ingen karta har angetts i användarinställningarna används kartan som har öppnats på panelen Kartvy. Om ingen karta är öppen på panelen Kartvy används kartan i mappprofilerna för att matcha nyckelreferenserna.

Nyckelreferenserna kan lagras i en DITA-kartfil eller en separat DITA-fil. I AEM Guides kan du ange nyckelreferenser antingen på projektnivå eller sessionsnivå. Om en rotmappning redan har definierats för användarsessionen används den för att matcha nycklarna. I annat fall används standardrotkartan för den mappen. Om en standardrotkarta inte är konfigurerad markeras de saknade nyckelreferenserna för användaren.

Det finns flera sätt att lösa nyckelreferenser i ett DITA-avsnitt genom att definiera DITA-kartan som ska användas på följande platser:

**Projektegenskaper** - Du kan definiera en rotmappning för att matcha nyckelreferenser när du skapar ett projekt i avsnittet Projektegenskaper.

Den här rotmappningen kommer att gälla för alla resurser \(mappar och undermappar\) som är associerade med det projektet. För innehåll som refereras i flera projekt behålls en alfabetisk lista över projekt och den standardrotkarta som är associerad med det första projektet används. Du kan också välja den DITA-karta som ska användas i listan för att lösa nyckelreferenser.

**Förhandsgranskning av ämne** - I läget för ämnesförhandsgranskning klickar du på ikonen Tangentupplösning i verktygsfältet och väljer den DITA-fil som ska användas för nyckelreferenser.

**Ämnesredigeringsvy** - Klicka på ikonen Tangentmatchning när du redigerar ett DITA-ämne och välj den DITA-fil som ska användas för att matcha nyckelreferenserna.

**Överordnat ämne:**[ Arbeta med kartredigeraren](map-editor.md)
