---
title: Skapa ämnen
description: Lär dig hur du skapar typer av DITA-ämnen med anpassade mallar i Adobe Experience Manager Guides.
exl-id: 84e9cfdf-e188-487f-9181-68708029c101
feature: Authoring
role: User
source-git-commit: c6709ffb8e415c88931e732456e2f2a5e6b63729
workflow-type: tm+mt
source-wordcount: '833'
ht-degree: 0%

---

# Skapa ämnen {#id2056AL00O5Z}

Med Adobe Experience Manager Guides kan du skapa DITA-ämnen av typen: variabel, uppgift, begrepp, referens, ordlista, DITAVAL, markering med mera. Förutom att skapa ämnen baserat på färdiga mallar kan du även definiera egna mallar. Mallarna måste läggas till i mappprofilen för att kunna visas i mallvalet Utskrift och Redigeraren.

>[!NOTE]
>
> Konfigurationen av global profil och mappprofil är bara tillgänglig för administratörer på mappnivå. Mer information om hur du konfigurerar globala profiler och profiler på mappnivå finns i *Konfigurera redigeringsmallar* i Installera och konfigurera Adobe Experience Manager Guides för installationen.


Det finns två sätt att skapa ämnen i Experience Manager Guides:

- [Skapa ämnen från Redigeraren](#create-topics-from-the-editor)
- [Skapa ämnen från Assets användargränssnitt](#create-topics-from-the-assets-ui)

## Skapa ämnen från Redigeraren

Utför följande steg för att skapa ett ämne från Redigeraren:

1. På panelen Databas markerar du ikonen **Ny fil** och väljer sedan **Ämne** i listrutan.

   ![](images/create-topic-option.png){width="500" align="left"}

   Du kan även komma åt det här alternativet från [Experience Manager Guides hemsida](./intro-home-page.md) och alternativmenyn för en mapp i databasvyn.

2. Dialogrutan **Nytt ämne** visas.

3. Ange följande information i dialogrutan **Nytt ämne**:
   - En rubrik för ämnet.
   - \(Valfritt\)* Ämnets filnamn. Filnamnet föreslås automatiskt baserat på ämnet Titel. Om administratören har aktiverat automatiska filnamn baserat på UUID-inställningen, kommer du inte att visa namnfältet.
   - En mall som ämnet baseras på. Om du till exempel har en färdig installation kan du välja bland mallarna Tom, Koncept, DITAVAL, Referens, Uppgift, Ämne, Markering, Ordlista och Felsökning. Om mappen har en konfigurerad mappprofil visas endast de ämnesmallar som har konfigurerats i mappprofilen.
   - Sökväg där du vill spara ämnesfilen. Som standard visas sökvägen till den markerade mappen i databasen i fältet Sökväg.

4. Välj **Skapa**.

   ![](images/create-topic-dialog-new.png){width="300" align="left"}

Ämnet skapas på den angivna sökvägen. Dessutom öppnas ämnet i Redigeraren för redigering.

![](images/new-topic-editor.png){align="left"}

## Skapa ämnen från Assets användargränssnitt

Följ de här stegen för att skapa ett ämne från Assets-gränssnittet:

1. Gå till den plats där du vill skapa ämnet i användargränssnittet för Assets.

1. Om du vill skapa ett nytt ämne väljer du **Skapa** \> **DITA-ämne**.

1. På sidan Design väljer du den typ av DITA-dokument som du vill skapa och väljer **Nästa**.

   ![](images/create_dita_topic.png){align="left"}

   Som standard innehåller Experience Manager Guides de vanligaste DITA-ämnesmallarna. Du kan konfigurera fler ämnesmallar enligt organisationens krav i *Konfigurera redigeringsmallar* i Installera och konfigurera Adobe Experience Manager Guides för din konfiguration.

   >[!NOTE]
   >
   > I listvyn för Assets-användargränssnittet visas DITA-ämnestypen i kolumnen Typ som Ämne, Aktivitet, Koncept, Referens, Ordlista, Markering eller DITAVAL. DITA-kartan visas som karta.

1. På sidan Egenskaper anger du dokumentet **Title**.

1. \(Valfritt\) Ange filen **Namn**.

   Om administratören har konfigurerat det automatiska filnamnet baserat på UUID-inställningen visas inte alternativet att ange filnamnet. Ett UUID-baserat filnamn tilldelas automatiskt till filen.

   Om filnamnsalternativet är tillgängligt föreslås också namnet automatiskt baserat på **titeln** i dokumentet. Om du vill ange dokumentnamnet manuellt kontrollerar du att **namnet** inte innehåller blanksteg, apostrof eller klammerparenteser och slutar med .xml eller .dita. Som standard ersätter Experience Manager Guides alla specialtecken med bindestreck. Se avsnittet Filnamn i guiden Bästa tillvägagångssätt för att få tips om hur du namnger DITA-filer.

1. Välj **Skapa**. Meddelandet Ämnet har skapats visas.

   Du kan välja att öppna ämnet för redigering i Redigeraren eller att spara ämnesfilen i Adobe Experience Manager-databasen.

**Ytterligare information**

1. Varje nytt ämne som du skapar från Assets-gränssnittet **Skapa** \> **DITA-ämne** eller redigeraren tilldelas ett unikt ämne-ID. Värdet för detta ID är själva filnamnet. Ett nytt dokument sparas också som den senaste arbetskopian av ämnet i DAM. Du kommer inte att visa något versionsnummer i Tidigare versioner förrän du har sparat en revision av ett nyligen skapat ämne. Om du öppnar ämnet för redigering visas versionsinformationen i det övre högra hörnet av verktygsfältet:

   ![](images/topic-version-none_cs.png){width="550" align="left"}

2. Versionsinformationen för ett nyligen skapat ämne visas som *none*. När du sparar en ny version tilldelas den ett versionsnummer som 1.0.

3. Om administratören har konfigurerat redigeraren så att filer låses före redigering kan du inte redigera en fil förrän du låser den. Om den är konfigurerad uppmanas du att låsa upp alla låsta filer innan du stänger den.

4. När du har skapat ditt DITA-avsnitt kan du fortsätta spara ändringarna i arbetskopian och skapa en ny version när du har slutfört uppdateringarna av ämnet.

**Överordnat ämne:**[ Skapa och förhandsgranska ämnen](create-preview-topics.md)
