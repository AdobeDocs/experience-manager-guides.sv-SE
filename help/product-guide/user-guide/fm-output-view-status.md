---
title: Visa status för utdatagenereringsaktiviteten
description: Visa utdatagenereringskön för FrameMaker-dokument. Lär dig hur du visar status för en utdatagenereringsuppgift.
exl-id: c358f747-f0a5-4d9e-a96f-20f30663101f
feature: Publishing FrameMaker Documents
role: User
source-git-commit: b78a34430476c15cadacb23d65bd978b3c25bd23
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 0%

---

# Visa status för utdatagenereringsaktiviteten {#viewing_output_history}

När du har initierat genereringsuppgiften för ett FrameMaker-dokument skickar Adobe Experience Manager Guides den här uppgiften till kön för utdatagenerering. Den här kön uppdateras i realtid och visar statusen för varje utdatagenereringsuppgift i kön.

Utför följande steg för att visa kön för generering av utdata:

1. I Assets-användargränssnittet navigerar du till och väljer det FrameMaker-dokument som du vill kontrollera utdatagenereringsstatus för.

1. Välj Utdata.

   ![](images/output-queued-fm.png){align="left"}

1. Sidan Utdata är uppdelad i två delar:

   - **Utdata i kö:**

     Visar utdata som väntar på att skapas eller som håller på att genereras. Du kan också hitta den inställning eller förinställning för generering av utdata som används för uppgiften som står i kö, typ, användare som initierade uppgiften, tid sedan uppgiften placerades i kö samt aktuell status.

   - **Genererade utdata**

     Visar en lista över utdataaktiviteter som har slutförts. Informationen som visas här liknar den som visas i avsnittet Utdata i kö, med den enda skillnaden mellan genereringstiden för utdata.

     I den här listan kan du ha uppgifter som har utförts eller uppgifter som misslyckats. För de uppgifter som har slutförts skapas en loggfil, \(logs.txt\), som du kommer åt genom att välja länken i kolumnen Genererad den.


**Överordnat ämne:**[ Generera utdata för FrameMaker-dokument](fm-output-generatation.md)
