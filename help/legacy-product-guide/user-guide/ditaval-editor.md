---
title: Använd DITAVAL-redigerare
description: Lär dig skapa och redigera DITAVAL-filer med DIVATAL Editor i AEM Guides. Ta reda på hur DITAVAL-redigeraren stöder DITAVAL-filer i skribent- och källvyer.
feature: Authoring, DITAVAL Editor
role: User
source-git-commit: fa07db6a9cb8d8f5b133258acd5647631b22e28a
workflow-type: tm+mt
source-wordcount: '758'
ht-degree: 0%

---

# DITAVAL editor {#ditaval-editor}

DITAVAL-filer används för att generera villkorsstyrda utdata. I ett enskilt ämne kan du lägga till villkor med elementattribut för att villkorsanpassa innehållet. Sedan skapar du en DITAVAL-fil där du anger villkoren som ska plockas upp för att generera innehåll och vilket villkor som ska utelämnas från det slutliga resultatet.

Med AEM Guides kan du enkelt skapa och redigera DITAVAL-filer med DITAVAL-redigeraren. DITAVAL-redigeraren hämtar attributen \(eller taggar\) som är definierade i systemet, och du kan använda dem för att skapa eller redigera DITAVAL-filer. Mer information om hur du skapar och hanterar taggar i AEM finns i avsnittet [Administrera taggar](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/tags.html?lang=en) i AEM.

## Skapa DITAVAL-fil

Så här skapar du en DITAVAL-fil:

1. I Assets-gränssnittet navigerar du till den plats där du vill skapa DITAVAL-filen.

1. Klicka på **Skapa** \> **DITA-ämne**.

1. På sidan Design väljer du DITAVAL-filmall och klickar på **Nästa**.

1. På sidan Egenskaper anger du **Title** och **Name** för DITAVAL-filen.

   >[!NOTE]
   >
   > Namnet föreslås automatiskt baserat på filens namn. Om du vill ange filnamnet manuellt kontrollerar du att namnet inte innehåller blanksteg, apostrof eller klammerparenteser och slutar med .ditaval.

1. Klicka på **Skapa**. Meddelandet Ämnet har skapats visas.

   Du kan välja att öppna DITAVAL-filen för redigering i DITAVAL-redigeraren eller att spara ämnesfilen i AEM.


## Redigera DITAVAL-fil

Utför följande steg för att redigera en DITAVAL-fil:

1. I Assets-gränssnittet navigerar du till den DITAVAL-fil som du vill redigera.

1. Om du vill låsa filen exklusivt markerar du filen och klickar på **Checka ut**.

1. Markera filen och klicka på **Redigera** för att öppna filen i AEM Guides DITAVAL-redigeraren.

   Med DITAVAL-redigeraren kan du utföra följande uppgifter:

   A: Växla vänster panel
Växla den vänstra panelvyn. Om du har öppnat DITAVAL-filen via DITA-kartan visas kartan och databasen på den här panelen. Mer information om hur du öppnar en fil via DITA-kartan finns i [Redigera ämnen via DITA-kartan](map-editor-advanced-map-editor.md#id17ACJ0F0FHS).

   B: Spara
Sparar de ändringar du har gjort i filen. Alla ändringar sparas i den aktuella versionen av filen.

   C: Lägg till egenskap
Lägg till en enda egenskap i DITAVAL-filen.

   ![](images/ditaval-editor-props.png)

   I den första listrutan visas de tillåtna DITA-attribut som du kan använda i DITAVAL-filen. Det finns fem attribut som stöds - `audience`, `platform`, `product`, `props` och `otherprops`.

   I den andra listrutan visas de värden som konfigurerats för det valda attributet. I nästa nedrullningsbara lista visas de åtgärder som du kan konfigurera för det valda attributet. De tillåtna värdena i åtgärdslistrutan är - `include`, `exclude`, `passthrough` och `flag`. Mer information om dessa värden finns i definitionen av elementet [prop](http://docs.oasis-open.org/dita/dita/v1.3/errata01/os/complete/part3-all-inclusive/langRef/ditaval/ditaval-prop.html#ditaval-prop) i dokumentationen för OASIS DITA

   D: Lägg till alla egenskaper
Om du vill lägga till alla villkorliga egenskaper eller attribut som definierats i systemet med ett enda klick använder du funktionen Lägg till alla egenskaper.

   >[!NOTE]
   >
   > Om alla definierade villkorliga egenskaper redan finns i DITAVAL-filen kan du inte lägga till fler egenskaper. Du får ett felmeddelande i det här scenariot.

   ![](images/ditaval-all-props.png)

1. När du har redigerat DITAVAL-filen klickar du på **Spara**.

   >[!NOTE]
   >
   > Om du stänger filen utan att spara kommer ändringarna att gå förlorade. Om du inte vill spara ändringarna AEM databasen klickar du på **Stäng** och sedan på **Stäng utan att spara** i dialogrutan **Osparade ändringar**.


## DITAVAL-redigeringsvyer

AEM Guides DITAVAL-redigerare har stöd för att visa DITAVAL-filer i två olika lägen eller vyer:

**Författare**:   Detta är ett typiskt exempel på vad du ser i vyn What You Get \(WYSISYG\) i DITAVAL-redigeraren. Du kan lägga till eller ta bort egenskaper med det enkla användargränssnittet, som visar egenskaperna, dess värden och åtgärder i listrutan. I redigeringsvyn kan du infoga en enskild egenskap och infoga alla egenskaper med ett enda klick.

Du kan också hitta den version av DITAVAL-filen som du arbetar med genom att hålla pekaren över filnamnet.

**Source**:   I Source-vyn visas den underliggande XML-filen som utgör DITAVAL-filen. Förutom att göra vanliga textredigeringar i den här vyn kan en författare även lägga till eller redigera egenskaper med den smarta katalogen.

Om du vill anropa den smarta katalogen placerar du markören i slutet av en egenskapsdefinition och skriver &quot;&lt;&quot;. Redigeraren visar en lista över alla giltiga XML-element som du kan infoga på den platsen.

![](images/ditaval-source-view.png)
