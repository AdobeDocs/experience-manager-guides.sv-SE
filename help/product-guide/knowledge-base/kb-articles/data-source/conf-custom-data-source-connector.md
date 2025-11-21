---
title: Konfigurera en anpassad anslutning för datakällorna
description: Lär dig hur du konfigurerar en anpassad koppling för datakällorna.
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: ef7ab117-7541-4e89-9ba4-22254a17efc0
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '1521'
ht-degree: 0%

---

# Konfigurera anpassade datakällanslutningar

Med Experience Manager Guides kan du anpassa anslutningarna efter dina behov och sedan använda dem med olika datakällor. Om du vill anpassa en koppling måste du implementera anslutningsgränssnittet och dess viktiga funktioner, och sedan konfigurera gränssnittet. Du kan också tillhandahålla resurserna tillsammans med de anpassade kopplingarna.


- [Anpassa en anslutning för Experience Manager Guides](#customize-connector)
- [Implementera anslutningsgränssnittet](#implement-interface)
- [Viktiga funktioner](#important-functions)
- [Typer av standardanslutningar](#default-connectors)
   - [Konfigurationsgränssnitt](#config-interface)
   - [Typer av standardkonfigurationsimplementeringar](#default-config-types)
   - [Konkreta konfigurationsimplementationer](#concrete-config-implementation)
   - [Ytterligare resurser](#resources)



## Anpassa en anslutning för Experience Manager Guides {#customize-connector}

Du kan anpassa eller konfigurera en koppling för en datakälla med hjälp av fördefinierade gränssnitt och abstrakta klasser. Hela källkoden finns på [https://github.com/adobe/guides-data-source-connectors/tree/main/konnect-definitions](https://github.com/adobe/guides-data-source-connectors/tree/main/konnect-definitions).


Mer information om konnect-definitioner finns i [![javadoc](https://javadoc.io/badge2/com.adobe.aem.addon.guides/konnect-definitions/javadoc.svg)](https://javadoc.io/doc/com.adobe.aem.addon.guides/konnect-definitions).

## Implementera anslutningsgränssnittet {#implement-interface}

Utför följande steg för att implementera gränssnittet och dess funktioner enligt dina krav:

1. Definiera ett standardiserat sätt för kopplingarna att integreras med ett system, vilket möjliggör körning av frågor, validering av anslutningar och hämtning av metadata.
1. Underlätta integreringen av användargränssnittet genom att tillhandahålla standardmetoder för att konfigurera mallar, logotyper, frågor och andra inställningar.
1. Kontrollera att anslutningarna är korrekt verifierade och kan hantera fel (`KonnectException`) vid interaktion med datakällor.

Gränssnittet fungerar som en plan för implementering av olika typer av dataanslutningar och ser till att anslutningarna uppfyller alla specifika integrerings- och driftskrav i ett större programvaruekosystem.

## Viktiga funktioner {#important-functions}

Implementera följande viktiga funktioner:

| Metod | Obligatoriskt | Beskrivning |
|---|---|---|
| getLogoUrl |  | <ul><li> Den här metoden returnerar den URL som används som anslutningsprogrammets logotyp. <li> Som standard returneras en tom sträng, vilket anger att ingen logotyp-URL anges om den inte åsidosätts. <br><b> Ytterligare anteckningar</b>: <br> <ul><li> Om du anger både en logotypadress och ett logotypklassnamn används logotypens URL för att visa logotypen i användargränssnittet. <li> Om du anger logotypens URL via konfigurationsinställningarna åsidosätter den URL som angetts i metodimplementeringen. |
| validateConnection | Ja | <ul><li> Använd den här metoden för att validera om anslutningen kan upprätta en anslutning till dess datakälla. <li> Det tar ett `ConfigDto`-objekt som en parameter, som innehåller konfigurationsinställningarna, till exempel anslutningsautentiseringsuppgifter och URL:er för slutpunkter. <li> Metoden returnerar true om valideringen (anslutningstestet) lyckas, vilket anger att kopplingen kan ansluta till sin datakälla. |
| execute | ja | <ul><li>Använd den här metoden om du vill köra en enskild fråga för kopplingen och interagera med en datakälla. <li> Kopplingarna som stöder den här åtgärden hanterar frågekörningen, tolkar svaret och konverterar det till en JSON-sträng vid behov. <li> Kapsla in frågan som ska köras i den här metoden i ett `QueryInfoDto`-objekt, som innehåller information som frågesträngen och parametrar. <li> Metoden returnerar en JSON-sträng som representerar svaret från körningen av frågan. <br><b> Ytterligare anteckningar</b>: <li>Implementeringen av den här metoden varierar beroende på den specifika kopplingen och dess interaktion med datakällan. <li> Använd `KonnectException` för att hantera eventuella undantag eller fel som inträffar under körningen eller anslutningen till datakällan. |
| executeWithLimit | ja | <ul><li> Använd den här metoden i samma syfte som `execute()`, men med den extra funktionaliteten att tillämpa en begränsande fråga, vanligtvis för att visa förhandsvisningarna i UI-komponenter. <li> Kopplingar som stöder den här åtgärden hanterar frågekörningen, tolkar svaret och konverterar det till en JSON-sträng om det behövs. <li> Kapsla in frågan som ska köras i den här metoden i ett `QueryInfoDto`-objekt, ungefär som med föregående metod. <br><b> Ytterligare anteckningar</b>: <ul><li> `QueryResultDto` är en anpassad klass eller ett dataöverföringsobjekt som kapslar in resultatet av frågekörningen, inklusive metadata om frågan och dess körningsstatus. |
| getSampleQuery | | <ul><li>Den här metoden returnerar en exempelfrågesträng som kan visas i användargränssnittet, till exempel i dialogrutan där användare kan infoga eller redigera frågor. <li>Som standard returneras en tom sträng, vilket anger att ingen provfråga har angetts om den inte åsidosätts. <br><b> Ytterligare anteckningar</b>: <ul> <li> Om du inte definierar någon exempelfråga och metoden returnerar en tom sträng, visas ingen exempelfråga i dialogrutan Infoga fråga för användargränssnittet. |
| getTemplates | | <ul> <li> Den här metoden returnerar en lista med mallar som är associerade med kopplingen. <li> Som standard returneras en tom lista, vilket anger att inga mallar finns såvida de inte åsidosätts. |
| getLogoClassName | | <ul> <li> Den här metoden returnerar klassnamnet som kopplingens logotyp. Som standard returneras en tom sträng, vilket anger att inget logotypklassnamn anges om det inte åsidosätts. <br><b> Ytterligare anteckningar</b>: <ul><li> Om du anger både en logotypadress och ett logotypklassnamn används logotypens URL för att visa logotypen i användargränssnittet. <li> Om du anger namnet på logotypklassen via konfigurationsinställningarna åsidosätter det klassnamn som angetts i metodimplementeringen. |
| aktiverad | ja | <ul><li> Den här metoden kontrollerar om en `connector` är aktiverad. <li> Som standard returnerar metoden false, vilket innebär att kopplingen inte är aktiverad om den inte åsidosätts av en klass som implementerar den här metoden. |
| getDescription | | <ul><li>Använd den här metoden för att returnera en beskrivningssträng som kan visas i användargränssnittet. <li> Som standard returneras en tom sträng, vilket anger att ingen beskrivning anges om den inte åsidosätts. |
| getAuthor | | <ul><li> Med den här metoden kan du hämta namnet på författaren som skapade eller är ansvarig för kopplingen. <li> Det är vanligtvis till hjälp för att identifiera och bekräfta att anslutningsprogrammet har skapats eller underhållits inom ett system eller ramverk. |
| getName | ja | <ul><li>Med den här metoden kan du hämta det unika namn som tilldelats en koppling. <li>Det returnerade namnet är viktigt för att identifiera kopplingen i ett användargränssnittskontext (UI), särskilt om anslutarens konfigurationsinställningar inte uttryckligen anger ett namn. <li>Det här namnet används i olika gränssnittskomponenter för att visa eller hantera anslutningar på ett användarvänligt sätt. |
| getGroup | ja | <ul> <li>Med den här metoden kan du hämta gruppnamnet som är associerat med en koppling. <li>Gruppnamn används vanligtvis för att ordna eller kategorisera kopplingar i logiska grupper utifrån deras funktion, syfte eller typ. <li> Detta gör det enklare att hantera och presentera anslutningar i konfigurationsgränssnittet. |
| getDefaultTemplatePath |  | <ul><li> Den här metoden returnerar standardsökvägen för mallarna som är associerade med den här kopplingen. <li> Som standard returneras en tom sträng, vilket anger att ingen standardsökväg har angetts om den inte åsidosätts. |
| getLogoSvg |  | <ul><li>Använd den här metoden för att returnera SVG-representationen av kopplingens logotyp. <li> Som standard returneras en tom sträng, vilket anger att inga SVG-data anges om de inte åsidosätts. |
| getMaxNoRowsForPreviewQuery | | <ul><li>Den här metoden returnerar det maximala antalet rader som har frågats eller visas i gränssnittsförhandsvisningen. <li> Som standard returneras värdet DEFAULT_LIMIT_PREVIEW, en konstant som representerar standardgränsen för förhandsgranskningsrader. |
| getConfigClass | ja | <ul><li>Den här metoden ger information om de klasser som implementerar Config-gränssnittet och som stöds av den här kopplingen. <li> Det gör att programmet eller ramverket dynamiskt kan identifiera och arbeta med konfigurationer som är kompatibla med anslutningen. |

## Typer av standardanslutningar {#default-connectors}

Biblioteket *konnect-definitions* skickar abstrakta kopplingsimplementeringar och med fördefinierade funktioner för att köra frågor. Dessa implementeringar fungerar som mallar som kan utökas direkt och användas som de är. Om en anpassad implementering krävs kan dess funktioner åsidosättas.

Förutom att implementera standardanslutningarna kan du även implementera en av följande abstrakta standardklasser:

- Restanslutning
- Filanslutning
- GraphQL Connector
- SQL Connector
- NoSQL Connector


Om en koppling passar in i någon av dessa typer, utökar du kopplingen till motsvarande basklass. I annat fall skapar du det från grunden genom att implementera anslutningsgränssnittet.

## Konfigurationsgränssnitt {#config-interface}

Gränssnittet `Config` är utformat för att konfigurera en datakälla med en viss autentiseringsmetod, vilket ger dig exakt kontroll över hur du skapar anslutningen.

Gränssnittet `Config` ger flexibilitet i hur autentiseringsinformation hanteras och implementeras. Olika implementeringar kan erbjuda olika sätt att autentisera datakällor. En koppling använder en Config-instans för att köra och validera frågor mot en datakälla, vilket utgör ett fullständigt arbetsflöde.
En koppling använder en `Config`-instans för att köra och validera frågor mot en datakälla, vilket utgör ett fullständigt arbetsflöde.

En config-implementering definierar hur autentisering hanteras för att ansluta till en datakälla. Den här konfigurationen används sedan av en kopplingsimplementering för att interagera med datakällan, vilket säkerställer att frågorna körs och valideras korrekt.

Gränssnittet `Config` är generellt en viktig del av arbetsflödet för att ansluta till datakällor, med särskild inriktning på autentiseringskonfiguration.

### Typer av standardkonfigurationsimplementeringar {#default-config-types}

Det finns tre typer av standardkonfigurationsimplementeringar för abstrakt konfiguration för autentisering:

- RestConfig
- SqlConfig
- NoSqlConfig

Om en konfiguration justeras mot någon av dessa typer kan motsvarande basklass utökas. Annars kan den skapas från grunden genom att implementera Config-gränssnittet.

### Konkreta konfigurationsimplementationer {#concrete-config-implementation}

Biblioteket *konnect-definitions* levereras med fördefinierade implementeringar av Config-gränssnittet för några vanliga autentiseringskonfigurationer. Du kan använda dessa konfigurationer direkt i kopplingen eller definiera nya med hjälp av Config-gränssnittet. Dessa implementeringar omfattar:

- API Key Auth Config
- Grundläggande autentiseringstokenbaserad konfiguration
- Basic Auth Config
- Konfiguration för Bearer-token
- Lösenordskonfiguration för användarnamn för SQL
- Autentiseringskonfiguration för anslutningssträng för NoSQL

### Ytterligare resurser{#resources}

Med Experience Manager Guides kan du också tillhandahålla anpassade resurser för logotyper och mallar tillsammans med implementeringen. Du kan behålla de här resurserna i mappen `resources`.
För att de ska kunna användas av kopplingen måste du implementera följande anslutningsfunktioner:


- `getLogoSvg` - Returnerar logotypen SVG som en sträng.

- `getTemplates` - Returnerar listan med mallar i det angivna formatet.
