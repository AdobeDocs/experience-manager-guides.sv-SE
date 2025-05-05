---
title: Visa status för utdatagenereringsaktiviteten
description: Visa utdatagenereringskön för FrameMaker-dokument. Lär dig hur du visar status för en utdatagenereringsuppgift.
feature: Publishing FrameMaker Documents
role: User
hide: true
exl-id: bf5a4365-0183-43d5-a39a-b9eb8a34b27d
source-git-commit: 26fa1e52920c1f1abd5655b9ca7341600a9bca67
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 0%

---

# Visa status för utdatagenereringsaktiviteten {#viewing_output_history}

När du har initierat genereringsuppgiften för ett FrameMaker-dokument skickar AEM Guides den här uppgiften till kön för utdatagenerering. Den här kön uppdateras i realtid och visar statusen för varje utdatagenereringsuppgift i kön.

Utför följande steg för att visa kön för generering av utdata:

1. Navigera till och klicka på det FrameMaker-dokument som du vill kontrollera status för utdatagenerering för i Assets-användargränssnittet.

1. Klicka på Utdata.

   ![](images/output-queued-fm.png){width="800" align="left"}

1. Sidan Utdata är uppdelad i två delar:

   - **Utdata i kö:**

     Visar utdata som väntar på att skapas eller som håller på att genereras. Du kan också hitta den inställning eller förinställning för generering av utdata som används för uppgiften som står i kö, typ, användare som initierade uppgiften, tid sedan uppgiften placerades i kö samt aktuell status.

   - **Genererade utdata**

     Visar en lista över utdataaktiviteter som har slutförts. Informationen som visas här liknar den som visas i avsnittet Utdata i kö, med den enda skillnaden mellan genereringstiden för utdata.

     I den här listan kan du ha uppgifter som har utförts eller uppgifter som misslyckats. För de uppgifter som har slutförts skapas en loggfil, \(logs.txt\), som du kommer åt genom att klicka på länken i kolumnen Genererad den.


**Överordnat ämne:**&#x200B;[ Generera utdata för FrameMaker-dokument](fm-output-generatation.md)
