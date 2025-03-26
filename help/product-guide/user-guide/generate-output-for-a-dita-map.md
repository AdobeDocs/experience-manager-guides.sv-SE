---
title: Generera utdata
description: Generera utdata för en DITA-karta från kartkonsolen och kartpanelen i AEM Guides.
exl-id: d6cbd44c-e74c-4192-bcc4-fb7752c59508
feature: Publishing
role: User
source-git-commit: ac83f613d87547fc7f6a18070545e40ad4963616
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 0%

---

# Generera utdata

Det finns två sätt att generera utdata för en DITA-karta:

- [Generera utdata för en DITA-karta från kartkonsolen](#generate-output-for-a-dita-map-from-the-map-console)
- [Generera utdata för en DITA-karta från kontrollpanelen för kartor](#generate-output-for-a-dita-map-from-the-map-dashboard)

## Generera utdata för en DITA-karta från kartkonsolen

Utför följande steg för att generera utdata för en DITA-karta med hjälp av Kartkonsol:

1. [Öppna en kartfil i kartkonsolen](./open-files-map-console.md).
2. DITA-kartkonsolen visas med en lista över **utdataförinställningar** som är tillgängliga för att generera utdata.

3. Öppna den förinställning som du vill använda för att generera utdata och välj **Generera utdata** för att starta genereringsprocessen.

   <img src="images/generate-output-pdf.png" alt="metadata, flik" width="600">

   Du kan också hovra över förinställningen och välja **Generera** på snabbmenyn för förinställningen.


   <img src="images/generate-preset-map-console.png" alt="metadata, flik" width="600">

När utdatagenereringen är klar väljer du **Visa utdata** för att visa utdata.

En dialogruta **Slutfört** visas längst ned till höger på skärmen.

Om utdata inte lyckas visas felmeddelandet nedan.

<img src="images/error-log.png" alt="fellogg" width="250">

Om du vill visa felloggen väljer du **Stäng**, håller pekaren över den valda förinställningsfliken och väljer **Visa logg** på snabbmenyn för förinställningen.

## Generera utdata för en DITA-karta från kontrollpanelen för kartor

Utför följande steg för att generera utdata för en DITA-karta med hjälp av kontrollpanelen Karta:

1. Navigera till och markera den DITA-kartfil som du vill publicera i Assets-gränssnittet.

   DITA-kartkonsolen visas med en lista över tillgängliga utdatapresentationer för att generera utdata.

1. Välj en eller flera förinställningar som du vill använda för att generera utdata.

   ![](images/generate-multiple-outputs-uuid.png){align="left"}

1. Välj ikonen **Generera** för att starta genereringsprocessen för utdata.


Du kan visa aktuell status för begäran om generering av utdata på fliken **Utdata**. Mer information finns i [Visa status för utdatagenereringsaktiviteten](./generate-output-manage-process.md#view-the-status-of-the-output-generation-task).

>[!IMPORTANT]
>
> Om en utdatagenereringsprocess för en förinställning antingen finns i kön eller pågår kan du inte initiera en annan utdatagenereringsåtgärd för samma förinställning.

Du kan också generera AEM Sites-utdata för ett eller flera ämnen, eller hela DITA-kartan från kartkonsolen. Mer information finns i [Generera kunskapsbas-utdata](web-editor-article-publishing.md#id218CK0U019I).




**Överordnat ämne:**[ Utdatagenerering](generate-output.md)
