---
title: Introduktion
description: Introduktion till API-referenshandboken för AEM Guides
exl-id: d8ee9cf7-1d67-4b4a-aa80-64e893a99463
feature: API Introduction
role: Developer
level: Experienced
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '594'
ht-degree: 0%

---

# Introduktion {#id1761C0007W7}

Adobe Experience Manager Guides \(senare kallat *AEM Guides*\) är en totallösning för företag som gör det möjligt för Adobe Experience Manager \(AEM\) att ha CCMS-funktioner (Component Content Management Solution) för att skapa och leverera DITA-baserat innehåll. Kunderna får tillgång till AEM Guides-arbetsflöden via programmeringsgränssnitt i AEM Guides för att integrera dem med andra företagsapplikationer. Dessa API:er kan också användas av Adobe partners för att förbättra AEM Guides värdeförslag genom att utöka dess funktionalitet eller genom att integrera den med andra program eller tjänster.

## AEM Guides API:er

AEM Guides API:er finns i två format:

- [Java-baserade API:er](#java-based-apis)
- [REST-baserade API:er](#rest-based-apis)

Dessa API:er visar AEM Guides nyckelfunktioner för programutvecklare. Med de här funktionerna kan utvecklare skapa egna plugin-program för att utöka färdiga arbetsflöden. API:erna är tillgängliga när det gäller att hantera utdata för DITA-innehåll, arbeta med DITA-kartor, lägga till villkorsattribut i mappnivåprofiler och konvertera HTML- och Word-dokument till DITA-format.


### Java-baserade API:er

Du kan använda Java-baserade API:er som finns i Experience Manager Guides för att skapa anpassade plugin-program och utöka färdiga arbetsflöden.

**Konfigurera SDK från Maven central databas för AEM Guides as a Cloud Service**

>[!INFO]
>
>I [![javadoc](./images/javadoc-cs-icon.svg)](https://javadoc.io/doc/com.adobe.aem/aem-dox-sdk-api/latest/index.html) finns den senaste och detaljerade dokumentationen om hur du använder det Java-baserade API:t för Experience Manager Guides as a Cloud Service.

Om du vill konfigurera och använda tjänstens API JAR från Maven-databasen i dina projekt lägger du till API-SDK som ett projektberoende i projektets `pom.xml`-fil enligt nedan.

```XML
<dependency>
<groupId>com.adobe.aem</groupId>
<artifactId>aem-dox-sdk-api</artifactId>
<version>${RELEASE}</version>
</dependency>
```

>[!NOTE]
>
> Se till att du använder samma version av API JAR som det AEM Guides-paket som är installerat på servern.

**Konfigurera och använd API JAR från Maven central databas (lokal)**

>[!INFO]
>
>Visa [![javadoc](https://javadoc.io/badge2/com.adobe.aem/aem-guides-sdk-api/javadoc.svg)](https://javadoc.io/doc/com.adobe.aem/aem-guides-sdk-api/latest/index.html) om du vill ha den senaste och detaljerade dokumentationen om hur du använder det Java-baserade API:t för installation på Experience Manager Guides.

Om du vill konfigurera och använda tjänstens API JAR för lokala distributioner lägger du till tjänstens API JAR som ett projektberoende i projektets `pom.xml`-fil enligt nedan:

```XML
<dependency>
<groupId>com.adobe.aem</groupId>
<artifactId>aem-guides-sdk-api</artifactId>
<version>${RELEASE}</version>
</dependency>
```

>[!NOTE]
>
> Se till att du använder samma version av API JAR som det AEM Guides-paket som är installerat på servern.


**Konfigurera och använda API JAR från AEM Guides offentliga Maven-databas (lokal)**

>[!NOTE]
>
> Den offentliga AEM Guides Maven-databasen kommer att bli inaktuell efter version 5.3.0 av Experience Manager Guides. API JAR kommer endast att vara tillgängligt i Maven central databas därefter.

Utför följande steg för att använda JAR-tjänstens API från den offentliga Maven-databasen:

1. Konfigurera AEM Guides publika Maven-databas i din `pom.xml`- eller `settings.xml`-fil enligt nedan:

   ```XML
   <repository>
       <id>fmdita-public</id>
       <name>fmdita-public</name>
       <url>https://repo.aem-guides.com/repository/fmdita-public</url>
    </repository>
   ```

1. När databasen har konfigurerats lägger du till tjänstens API JAR som ett projektberoende i projektets `pom.xml`-fil.

   ```XML
   <dependency>
       <groupId>com.adobe.fmdita</groupId>
       <artifactId>api</artifactId>
       <version>${RELEASE}</version>
   </dependency>
   ```

   >[!NOTE]
   >
   > Använd samma version av API JAR som det AEM Guides-paket som du har installerat på servern.

När JAR för tjänst-API har lagts till som ett projektberoende i projektets `pom.xml`-fil kan du skapa och använda AEM Guides Java API:er i ditt projekt.


### REST-baserade API:er

Experience Manager Guides har en omfattande uppsättning REST-baserade API:er som gör att utvecklare kan komma åt och interagera med centrala funktioner via HTTP.

Dessa API:er är idealiska för:

- Integrera Experience Manager Guides med andra affärssystem
- Automatisera publicerings- och granskningsflöden
- Skapa anpassade program och tillägg

Detaljerad information om API-användning, parametrar och exempelbegäranden finns i avsnittet **API-referens** i Experience Manager Guides-dokumentationen.

## Ytterligare resurser

Nedan följer en lista över andra användbara resurser i AEM Guides som finns på sidan [Lär dig mer och support](https://helpx.adobe.com/se/support/xml-documentation-for-experience-manager.html):

- Användarhandbok
- Installations- och konfigureringshandbok
- Snabbstartsguide
- [Hjälparkivsida](https://helpx.adobe.com/se/xml-documentation-for-experience-manager/archive.html) \(använd äldre versionsdokumentation\)
