---
title: Skapa ett DITA-projekt
description: Skapa ett DITA-projekt med en mall i AEM Guides. Lär dig hur du använder ett DITA-projekt för att initiera granskningarna.
feature: Reviewing
role: User
hide: true
exl-id: 1b29c50a-04d0-4052-b893-44fb8bcc3c97
source-git-commit: 7286c3fb36695caa08157296fd6e0de722078c2b
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 0%

---

# Skapa ett DITA-projekt {#id1645HA00NM6}

AEM Guides tillhandahåller en DITA-projektmall som du kan använda för att skapa och hantera dina granskningsuppgifter.

Du kan skapa ett DITA-projekt och sedan använda det för att starta granskningarna. Med ett projekt kan du definiera en deadline och styra de uppgifter och den tid som krävs för att slutföra den granskningsåtgärd som du har skapat projektet för.

Du kan lägga till teammedlemmar i ett projekt som sedan kan tilldelas olika roller - Författare, Granskare och Utgivare.

När du har skapat ditt DITA-projekt kan du starta en granskning från webbredigeraren eller Assets-gränssnittet. Mer information finns i [Skicka ämnen för granskning](review-send-topics-for-review.md#).

När en författare initierar ett granskningsarbetsflöde får de markerade medlemmarna i projektet ett e-postmeddelande. Information om hur du konfigurerar e-postmeddelanden finns i *Anpassa e-postmallar* i Installera och konfigurera Adobe Experience Manager Guides as a Cloud Service.

Så här skapar du ett DITA-projekt:

1. Öppna projektkonsolen.

   Du kan även komma åt projektkonsolen via följande URL:

   ```http
   http://<server name>:<port>/projects.html
   ```

1. Klicka på **Skapa** \> **Projekt** för att starta guiden Skapa projekt.

   ![](images/project-console-63.png){width="650" align="left"}

1. Välj mallen **DITA-projekt** på sidan Skapa projekt och klicka på **Nästa**.

1. Ange följande information på sidan Projektegenskaper:

   Information på fliken **Grundläggande**:

   ![](images/create-project.png){width="650" align="left"}

   - Ange projektets **titel**, **beskrivning** och **förfallodatum**.

   - Du kan också välja en miniatyrbild för projektet.

   - Som standard blir du projektägare. Så här lägger du till fler användare i det här projektet:

   1. Ange eller välj en användare i listrutan **Användare**.

   1. Välj en användartyp - Författare, Granskare eller Utgivare.

      >[!NOTE]
      >
      >Du kommer att se andra användartyper i den här listrutan, men för ett DITA-projekt bör du bara välja mellan användartypen Författare, Granskare eller Utgivare. Även om du lägger till en användare av en annan typ kommer den användaren inte att kunna komma åt några DITA-specifika funktioner som är tillgängliga i AEM Guides.

   1. Klicka på **Lägg till**.

      >[!NOTE]
      >
      >Om du använder AEM Guides version 3.5 eller tidigare visas ett alternativ för att välja en DITA-kartfil för att lösa nyckelreferenser för ämnesredigering, förhandsgranskning och granskningsarbetsflöden. I 3.6 och senare versioner kan du ange rotkartan via webbredigeraren. Mer information finns i [Användarinställningar](web-editor-features.md#id2087G0P40SB) i webbredigeraren. Ett annat sätt att ställa in rotkartan är att konfigurera den på global nivå eller på mappnivå. Mer information finns i *Konfigurera globala profiler och profiler på mappnivå* i installations- och konfigureringshandboken.

   Information på fliken **Avancerat**:

   - Ange ett namn för projektet. Det här namnet används för att skapa URL:en för det här projektet.

1. Klicka på **Skapa**.

   Dialogrutan Projekt skapat visas.

1. Klicka på **Öppna** för att öppna projektsidan.


**Överordnat ämne:**&#x200B;[ Granska ämnen eller kartor](review.md)
