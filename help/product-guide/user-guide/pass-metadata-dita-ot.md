---
title: Skicka metadata till utdata med DITA-OT
description: Lär dig hur du skickar metadata till utdata med DITA-OT-publicering i AEM Guides.
exl-id: 70ca32dc-56c3-45ee-b6b9-0efb8cc79ea1
feature: Publishing, Metadata Management
role: User
source-git-commit: ac83f613d87547fc7f6a18070545e40ad4963616
workflow-type: tm+mt
source-wordcount: '571'
ht-degree: 0%

---

# Skicka metadata till utdata med DITA-OT {#id21BJ00QD0XA}

Metadata är ytterligare information om utdata. I Adobe Experience Manager Guides kan du överföra befintliga metadata eller skapa anpassade metadatataggar. Du kan skicka metadata till AEM, PDF, HTML5, EPUB och anpassade format med DITA-OT-publicering.

Det finns två sätt att skicka metadata till utdata med DITA-OT:

- [Använda kartkonsolen](#using-map-console)
- [Använda Kartpanelen](#using-map-dashboard)

## Använda kartkonsolen

Utför följande steg för att skicka metadata till utdata med DITA-OT-publicering:

1. [Öppna DITA-mappningsfilen i kartkonsolen](./open-files-map-console.md) som du vill skicka metadata till DITA-OT för.
1. Markera och öppna en förinställning som du vill skicka metadatafälten till. Välj t.ex. PDF förinställning för utdata. Kontrollera att den har skapats med alternativet **DITA-OT** .
1. I listrutan **Filegenskaper** väljer du de metadata som du vill skicka till DITA-OT-publicering.

   ![](images/custom-metadata-output-preset-new.png){align="left"}

   I listrutan Egenskaper visas både de anpassade egenskaperna och standardegenskaperna. I skärmbilden ovan är till exempel `dc:description`, `dc:language`, `dc:title` och `docstate` standardegenskaper.

   >[!NOTE]
   >
   > Dessa egenskaper hämtas från filen metadataList som finns på följande plats:`/libs/fmdita/config/metadataList`. Som standard visas fyra egenskaper i den här filen - `dc:description`, `dc:language`, `dc:title` och `docstate`.

   Den här filen kan överlappas av: `/apps/fmdita/config/metadataList`.

   Visa [Använd AEM-metadata i DITA-OT PDF-utdata](https://experienceleaguecommunities.adobe.com/t5/xml-documentation-discussions/use-aem-metadata-in-dita-ot-pdf-output/td-p/411880) om du vill skicka en anpassad egenskap som du redan har definierat värdena för.

1. De valda egenskaperna visas under listrutan.

   ![](images/metadata-added-dropdown.png){width="300" align="left"}

1. Välj **Spara** längst upp till höger för att spara ändringarna.
1. Välj **Generera utdata**.

De valda metadataegenskaperna skickas till utdata som genereras med DITA-OT.

>[!NOTE]
>
> Från och med version 2502 av Experience Manager Guides har funktionen att skicka metadataargument för rotmappning via DITA-OT-kommandoraden tagits bort. För att undvika störningar har en ny egenskap lagts till i `Config.Manager` för att aktivera eller inaktivera funktionen.  Mer information finns i [Konfigurera inställningar för utdatagenerering](../cs-install-guide/conf-output-generation.md#configure-the-dita-ot-command-line-arguement-field-on-the-dita-map-dashboard).

## Använda Kartpanelen

Om du arbetar med **Assets-gränssnittet** utför du följande steg för att skicka metadata till utdata med DITA-OT-publicering:

1. I **Assets-gränssnittet** navigerar du till och väljer den DITA-mappningsfil som du vill skicka metadata till DITA-OT.
1. Markera och redigera en förinställning som du vill skicka metadatafälten till. Välj t.ex. PDF förinställning för utdata.
1. Välj alternativet **DITA-OT** i den valda förinställningen.

   ![](images/custom-meta-data-output-preset.png){align="left"}

1. I listrutan Egenskaper väljer du de metadata som du vill skicka till DITA-OT-publicering.

   I listrutan Egenskaper visas både de anpassade egenskaperna och standardegenskaperna. I skärmbildsförfattaren ovan är till exempel den anpassade egenskapen medan `dc:description`, `dc:language`, `dc:title` och `docstate` är standardegenskaper.

   >[!NOTE]
   >
   > Dessa egenskaper hämtas från filen metadataList som finns på följande plats:`/libs/fmdita/config/metadataList`. Som standard visas fyra egenskaper i den här filen - `dc:description`, `dc:language`, `dc:title` och `docstate`.

   Den här filen kan överlappas av: `/apps/fmdita/config/metadataList`.

   Visa [Använd AEM-metadata i DITA-OT PDF-utdata](https://experienceleaguecommunities.adobe.com/t5/xml-documentation-discussions/use-aem-metadata-in-dita-ot-pdf-output/td-p/411880) om du vill skicka en anpassad egenskap som du redan har definierat värdena för.

1. Välj önskade anpassade egenskaper och standardegenskaper i listrutan **Egenskaper**. Välj till exempel `author`, `dc:title` och `dc:description`. Det här är standarden `metadata/properties` som skapas när vi skapar en fil. De valda egenskaperna visas under listrutan.

   ![](images/selected-metadata-properties.png){width="300" align="left"}

1. Välj **Klar** längst upp till vänster om du vill spara ändringarna.
1. Generera utdata.

De valda metadataegenskaperna skickas till utdata som genereras med DITA-OT.



**Överordnat ämne:**&#x200B;[&#x200B; Utdatagenerering](generate-output.md)
