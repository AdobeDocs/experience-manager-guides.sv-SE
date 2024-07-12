---
title: Visa status för utdatagenereringsaktiviteten
description: Visa utdatagenereringskön för FrameMaker-dokument. Lär dig hur du visar status för en utdatagenereringsuppgift.
exl-id: c358f747-f0a5-4d9e-a96f-20f30663101f
feature: Publishing FrameMaker Documents
role: User
source-git-commit: 462647f953895f1976af5383124129c3ee869fe9
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 0%

---

# Visa status för utdatagenereringsaktiviteten {#viewing_output_history}

När du har initierat genereringsuppgiften för ett FrameMaker-dokument skickar AEM Guides den här uppgiften till kön för utdatagenerering. Den här kön uppdateras i realtid och visar statusen för varje utdatagenereringsuppgift i kön.

Utför följande steg för att visa kön för generering av utdata:

1. I Assets-användargränssnittet navigerar du till och klickar på det FrameMaker-dokument som du vill kontrollera utdatagenereringsstatusen för.

1. Klicka på Utdata.

   ![](images/output-queued-fm.png){width="800" align="left"}

1. Sidan Utdata är uppdelad i två delar:

   - **Utdata i kö:**

     Visar utdata som väntar på att skapas eller som håller på att genereras. Du kan också hitta den inställning eller förinställning för generering av utdata som används för uppgiften som står i kö, typ, användare som initierade uppgiften, tid sedan uppgiften placerades i kö samt aktuell status.

   - **Genererade utdata**

     Visar en lista över utdataaktiviteter som har slutförts. Informationen som visas här liknar den som visas i avsnittet Utdata i kö, med den enda skillnaden mellan genereringstiden för utdata.

     I den här listan kan du ha uppgifter som har utförts eller uppgifter som misslyckats. För de uppgifter som har slutförts skapas en loggfil, \(logs.txt\), som du kommer åt genom att klicka på länken i kolumnen Genererad den.


**Överordnat ämne:**[ Generera utdata för FrameMaker-dokument](fm-output-generatation.md)
