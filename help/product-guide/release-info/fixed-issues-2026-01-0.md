---
title: Versionsinformation | Korrigerade problem i Adobe Experience Manager Guides, version 2026.01.0
description: Läs mer om felkorrigeringarna i version 2026.01.0 av Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: 8a9a82e79c757e403141e853aafbc64e1618c30a
workflow-type: tm+mt
source-wordcount: '719'
ht-degree: 0%

---

# Problem i version 2026.01.0 har korrigerats

Den här artikeln handlar om buggar som har åtgärdats i olika delar av version 2026.01.0 av Adobe Experience Manager Guides as a Cloud Service.

Mer information om de nya funktionerna och förbättringarna finns i [Nyheter i version 2026.01.0](whats-new-2026-01-0.md).

Läs mer om [uppgraderingsinstruktioner för version 2026.01.0](upgrade-instructions-2026-01-0.md).

## Redigering

- När du uppdaterar en textbunden MathML-ekvation med alternativet Redigera MathML på snabbmenyn, återspeglas inte det uppdaterade värdet förrän sidan uppdateras. (GUIDES-38198)
- När ett ämne innehåller många återanvändbara element (de med ID:n) som har lagts till på panelen Återanvändbart, kanske vissa element inte är tillgängliga på grund av den fasta behållarhöjden. (GUIDES-37220)
- När du infogar en korsreferens till en fil är ikonerna för kartor och ämnen identiska.(GUIDES-36662)
- När du redigerar en karta visas inte specialsymboler i `navtitle` för `topichead` i redigeringsvyn. (GUIDES-35435)
- Det går inte att lägga till flera versionsetiketter i ett ämne från dialogrutan **Spara som ny version**. (GUIDES-32716)

## Resurshantering

- Det går inte att ta bort versionsetiketter från versionshistorikpanelen i Assets-användargränssnittet. (GUIDES-38276)
- När resurser med ett filnamn som innehåller ogiltiga tecken överförs inte resursen och det felaktiga meddelandet **Filen är låst av en annan användare** visas trots att resursen låses upp. (GUIDES-32680)
- I Assets-sökningen inkluderas underresurser och metadatanoder (som bilder och PDF-filer) felaktigt i resultatet. Dessutom returnerar sökningen internt genererade DITAVAL-filer som skapats från villkorsförinställningar för en förinställning för utdata när DITAVAL-filter används. (GUIDES-35418)

## Publicering

- När du genererar utdata från AEM Sites inkluderas inte karttitlar som innehåller nyckelord och ämnesrubriker med elementet `<ph>` i publicerade utdata. (GUIDES-36641)
- När du publicerar med en anpassad förinställning med innehåll som innehåller länkar till PDF-filer utan omfånget angett som externt, slutförs inte processen. (GUIDES-21708)
- När gruppaktivering utförs läggs filter till för alla sökvägar som listas under egenskapen `fileReference` på en sida, inklusive externa sökvägar och peer-sökvägar. (GUIDES-24887)
- I ursprungliga PDF-utdata visar `abbreviated-form`-elementet `glossterm` i stället för `glossSurfaceForm` eller `glossAcronym`. (GUIDES-26393)
- För inbyggda PDF-utdata ignoreras elementet `<alt>` för bilder, vilket förhindrar att alternativ text används för hjälpmedel. (GUIDES-29087)
- När du hämtar tillfälliga filer för en karta med en baslinje vid publicering för en förinställning refererar filen `metadata.xml` felaktigt till `versionPath` i stället för `dampath`.(GUIDES-29815)
- När du skapar eller redigerar ett ämne som innehåller ett citat, och om fältet Författare inte läggs till i dialogrutan för citat, genereras inte PDF. (GUIDES-37934)
- CSS-filen (`rhdefault.css`) tillämpas felaktigt på PDF-mallen trots att ingen CSS refereras, vilket orsakar att CSS-filens felloggar saknas.(GUIDES-31752)

## Plattform

- När du försöker spara ett ämne eller en karta kan åtgärden ibland misslyckas med felet **Det gick inte att spara filen**, särskilt under intensiva resurshanteringsuppgifter eller översättningsarbetsflöden som körs i bakgrunden. (GUIDES-37837)
- Om du använder `scope="external"` för en referens till DAM-innehåll i ett ämne eller en karta ersätts resursens relativa sökväg med ett GUID. (GUIDES-38783)

## Rapporter

- Rapporten Bruten lista innehåller felaktiga externa länkar, giltiga `keyrefs` och nyckelord som är korrekt lösta inom den aktuella kartans omfång. (GUIDES-27774)

## Kända fel

Adobe har identifierat följande kända fel i version 2026.01.0:

- När ett ämne i en granskning tas bort från en pågående granskningsåtgärd fortsätter dokumentläget att vara **Under granskning**, även om ämnet inte längre ingår i någon granskningsåtgärd. (GUIDES-38709)<br>**Tillfällig lösning**: Ändra dokumentläget för ämnet från **Under granskning** till lämpligt läge på egenskapssidan eller panelen Filegenskaper.
- När du gör en sökning med **Sök och ersätt** och öppnar en fil från sökresultaten, stänger den och försöker sedan öppna den igen genom att välja det listade resultatet, kan filen inte öppnas igen. (GUIDES-39050)<br>**Tillfällig lösning**: Öppna först en annan fil från sökresultaten och öppna sedan den tidigare stängda filen igen från listan för att lösa problemet.
- När du använder stödlinjer med DB-servern visar rapporten Ämneslista ogiltiga poster för varje självreferens, vilket resulterar i ett felaktigt antal filer. (GUIDES-39420)












