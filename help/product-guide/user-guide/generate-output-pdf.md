---
title: Förinställningstyper för PDF
description: Lär dig mer om de typer av förinställningar för PDF som du kan skapa med Adobe Experience Manager Guides.
exl-id: f12c91fd-3f95-478e-a9cd-68d037206ee8
feature: Publishing
role: User
source-git-commit: 558cc1a724a483353eb5d912354e1ab37dab348a
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 0%

---

# Översikt över förinställda utdata för PDF {#id205BE600HAH}

Med Experience Manager Guides kan du skapa PDF-förinställningar för att generera PDF-filer av enskilda ämnen eller en hel kartfil. Du kan publicera ditt innehåll i ett PDF-format på något av följande tre sätt:

**DITA-OT**

Använd den här metoden om du vill generera PDF-utdata för en karta från kartkonsolen eller kartkontrollpanelen. Du kan ange publiceringsegenskaper innan du genererar PDF genom att skapa en förinställning för kartan som är öppen i kartkonsolen eller på kartkontrollpanelen.

Mer information om hur du skapar en förinställning för PDF-utdata med metoden DITA-OT finns i [Skapa en DITA-OT-förinställning för PDF](./generate-output-pdf-dita-ot.md)

**FrameMaker Publishing Server (FMPS)**

>[!NOTE]
>
> Alternativet för FMPS-publicering är bara tillgängligt på Map-kontrollpanelen.

Använd den här metoden för att generera PDF-utdata från både DITA-innehåll och FrameMaker-dokument (.book och .fm) som finns i AEM-databasen. Du kan skapa PDF genom att konfigurera en förinställning och publicera den med FrameMaker Publishing Server (FMPS). Du kan utforma och konfigurera utdatafilens utseende och känsla för PDF och andra format och lagra samma i en inställningsfil (.sts). Inställningsfilen används sedan av FMPS för att generera utdata för en DITA-karta eller en .book-fil. Visa [Om du vill skapa eller redigera en förinställning för utdata](../user-guide/generate-output-understand-presets.md).

Mer information om hur du konfigurerar FMPS finns i [Generera utdata från FrameMaker-dokument](../user-guide/fm-output-generatation.md).

**Inbyggd PDF**

Använd den här metoden om du vill generera funktionsrika PDF-utdata baserat på W3C CSS3- och CSS-sidmediestandarderna. Med den inbyggda PDF-publiceringen kan du använda mallar för att ange layout och format för ditt innehåll och använda olika inställningar för att finjustera din PDF. Dessutom kan du ändra och skapa egna mallar med mallredigeraren.

Mer information om hur du skapar PDF-förinställningar finns i [Skapa ursprungliga PDF-förinställningar](../web-editor/native-pdf-web-editor.md).





**Överordnat ämne:**&#x200B;[ Förstå förinställningarna för utdata](generate-output-understand-presets.md)
