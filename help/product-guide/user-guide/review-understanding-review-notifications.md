---
title: Om granskningsmeddelanden
description: Lär dig mer om olika typer av granskningsmeddelanden och hur de utlöses under olika faser av granskningsarbetsflödet i Experience Manager Guides.
feature: Reviewing
role: User
exl-id: dc452e7d-a317-4168-8015-9fa4a06666ea
source-git-commit: 16688221c35e0b24c51cbff27953a93892cd0944
workflow-type: tm+mt
source-wordcount: '732'
ht-degree: 0%

---

# Om granskningsmeddelanden

>[!IMPORTANT]
>
> De nya funktionerna som beskrivs i den här artikeln är aktiverade som standard med 2508 års utgåva av Experience Manager Guides som molntjänster. Granskningar som skapades före migreringen påverkas inte och fortsätter att använda det tidigare arbetsflödet. Om du föredrar att fortsätta använda de befintliga funktionerna utan dessa uppdateringar kontaktar du ditt Customer Success-team för att inaktivera de nya funktionerna.

Experience Manager Guides effektiviserar samarbetet mellan författare och granskare genom ett strukturerat granskningsflöde. Som en del av det här arbetsflödet spelar meddelanden en viktig roll när det gäller att hålla alla deltagare i en granskningsuppgift informerade och responsiva på ändringar.

Varje gång en granskningsrelaterad åtgärd utförs, t.ex. tilldelning, slutförande eller uppdatering av feedback, skickas automatiskt ett meddelande till de berörda användarna av granskningsaktiviteten så att de omedelbart uppmärksammas. Dessa meddelanden levereras i två format:

- **AEM-meddelanden**: Visas i AEM gränssnitt.
- **E-postmeddelanden**: Skickat direkt till användarens inkorg.

Tabellen nedan ger en översikt över olika typer av granskningsmeddelanden, vilka åtgärder som utlöser dem och hur de visas i olika format:


## Granska meddelandeformat med exempelvärden

| **Granskningsåtgärd** | **Meddelanderubrik (AEM)** | **Meddelandetext (AEM)** | **Ämne för e-post** | **E-postaviseringstext** | **Mottagare** |
|-----------------------------|--------------------------------------------------|-------------------------------------------------------------|--------------------------------------------------------|------------------------------------------------------------------------------------------------|-----------------------------|
| Granskningsuppgift skapad | Granskningsaktivitet tilldelad: **Hemsidagranskning** | Tilldelad av **Författare** | Granskningsaktivitet tilldelad: **Hemsidagranskning** | **Författaren** har skapat en granskningsaktivitet **Hemsidsgranskning** i projektet **WebDocs Revamp** med förfallodatum **15 aug 2025**. Du har tilldelats som granskare. | **Granskare** |
| Synpunkter har lämnats in | Granska feedback som tagits emot för **hemsidsgranskning** | Feedback från **Reviewer** | Granska feedback som tagits emot för **hemsidsgranskning** | **Granskaren** har skickat feedback för aktiviteten **Hemsidsgranskning** i projektet **WebDocs Revamp**. Granska och gör nödvändiga uppdateringar långt före förfallodatumet **15 aug 2025**. | **Författare** eller **Initierare av uppgift** |
| Omgranskning begärd | Omgranskning begärd för **hemsidsgranskning** | Begärd av **författare** | Omgranskning begärd för **hemsidsgranskning** av **författare** | **Författaren** har uppdaterat dokumentet för uppgiften **Hemsidsgranskning** baserat på din feedback och begär en ny granskning. Granska i god tid före förfallodatumet **15 aug 2025**. | **Granskare** |
| Granskningen har stängts | Granskningsaktiviteten har stängts: **Hemsidsgranskning** | Stängd av **författare** | Granskningsaktiviteten har stängts: **Hemsidsgranskning** | Granskningsaktiviteten **Hemsidsgranskning** under projektet **WebDocs Revamp** har stängts av **Författare**. | **Författare** eller **Initierare av uppgift** , **Granskare** |
| Granskare ej tilldelad | Ej tilldelad från granskningsaktiviteten **hemsidesgranskning** | Ej tilldelad av **Författare** | Ej tilldelad från granskningsaktiviteten **hemsidesgranskning** | Du har tagits bort från granskningsaktiviteten **Hemsidsgranskning** under projektet **WebDocs Revamp** av **Författare**. | **Granskare** |
| Taggbeteckning | Omnämns i granskningsuppgiftskommentar för **hemsidesgranskning** | Omnämnd av **Författare** | Omnämns i granskningsuppgiftskommentar för **hemsidesgranskning** | Du har omnämnts i en kommentar om aktiviteten **Hemsidsgranskning** under **WebDocs Revamp** av **Författare**. **Kommentarutdrag:** *&quot;Uppdatera rubrikstrukturen så att den följer riktlinjerna för hjälpmedel.&quot;* | **Användare som nämns** |
| Innehåll som uppdaterats under granskning | Ämnet har uppdaterats i granskningsaktiviteten **Hemsidsgranskning** | Uppdaterat av **Författare** | Ämnet har uppdaterats i granskningsaktiviteten **Hemsidsgranskning** | **Författaren** har uppdaterat ämnesversionerna för granskningsaktiviteten **Hemsidsgranskning**. Granska i god tid före förfallodatumet **15 aug 2025**. | **Granskare** |
| Ämnen som läggs till eller tas bort eller versionsuppdateras medan en granskningsuppgift pågår med granskare | Ämnen som har uppdaterats i granskningsaktiviteten **Hemsidsgranskning** | Uppdaterat av **Författare** | Ämnen som har uppdaterats i granskningsaktiviteten **Hemsidsgranskning** | **Författaren** har uppdaterat ämnesversionerna för granskningsaktiviteten **Hemsidsgranskning**. Granska i god tid före förfallodatumet **15 aug 2025**. | **Granskare** |


I tabellen ovan representerar texten **i fet stil** exempelvärden och drivs av fördefinierade variabler som kan användas i meddelanden.


Till exempel:

- **Hemsidsgranskning** är ett exempel på aktivitetsnamn.
- **Priya** (författare) och **John** (granskare) är exempelanvändarnamn.
- **WebDocs Revamp** är ett exempelprojektnamn.
- **15 aug 2025** är ett exempelförfallodatum.

Om en uppgift dessutom innehåller kommentarer, inkluderas ett kommentarutdrag (en del av den fullständiga kommentaren) i e-postmeddelandet. Utdraget visas i följande fall:

- När du är taggad i en kommentar visas ett utdrag av den taggade kommentaren i e-postmeddelandet.
- När en kommentar på aktivitetsnivå läggs till i en granskningsåtgärd som du är en del av, visas ett utdrag av kommentaren i e-postmeddelandet.

En fullständig lista över fördefinierade variabler och anpassning av granskningsmeddelanden finns i [Konfigurera och anpassa arbetsflöden](../cs-install-guide/customize-workflows.md#customize-email-and-aem-notification-templates).




**Överordnat ämne:**&#x200B;[&#x200B; Introduktion till granskning](review.md)
