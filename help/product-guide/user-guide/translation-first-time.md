---
title: Bästa tillvägagångssätt för innehållsöversättning
description: Lär dig de bästa sätten att översätta innehåll i AEM Guides. Lär dig hur du konfigurerar översättningstjänsten, skapar ett nytt översättningsprojekt och startar översättningsjobbet.
exl-id: f2a4df86-bba7-434c-b7f9-3587b8a4f9bc
feature: Translation
role: User
source-git-commit: ae36a7fdff6ae147619340aa3a3d2bb6c7774fe0
workflow-type: tm+mt
source-wordcount: '838'
ht-degree: 0%

---

# Bästa tillvägagångssätt för innehållsöversättning {#id1678G0S702F}

Tänk på följande när du översätter innehåll:

- Mappens och filens namn måste uppfylla filnamnsstandarderna, t.ex.: blanksteg, apostrof, klammerparenteser, likhetstecken, specialtecken eller icke-ASCII-tecken.

- Om du översätter innehåll på olika språk måste du skapa mappar för varje språk. Var och en av dessa språkmappar kommer att innehålla det innehåll som motsvarar det språket. Du kan till exempel skapa mappar med språkdesignern som `de` för tyska, `fr` för franska och så vidare. Eller så kan du skapa mappar med språk- och regiondesigners som `fr-FR` för franska som används i Frankrike eller `fr-CA` för franska som används i Kanada.
- Målspråket ska också ha de faktiska språkinställningarna valda enligt målspråksmapparna i sin förekomst.
- Molnkonfigurationen bör vara densamma som för källmappen och det ska bara finnas en molnkonfiguration i en mapp. Du kan skapa flera mappar under /conf om du vill använda flera översättningskopplingar.
- En mapp får inte innehålla fler än 1 000 filer.
- Kontrollera att den användare som ansvarar för att initiera översättningsprocessen har behörigheterna Läs, Ändra, Skapa och Ta bort för käll- och målspråksmapparna.
- Eftersom översättning av innehåll kräver att ett översättningsprojekt skapas måste användaren ha tillgång till projektet i Adobe Experience Manager.
- Om du vill använda villkorliga förinställningar tillsammans med kartan måste du skapa dem innan du startar översättningsprocessen. Eftersom villkorliga förinställningar också paketeras i den översatta versionen av kartan, kan du se till att de är tillgängliga i den översatta versionen genom att skapa förinställningarna innan översättningsprocessen påbörjas.
- Översättningsprocessen för innehåll måste startas från DITA-kartkonsolen och inte från Adobe Experience Manager Assets-gränssnittet.
- Det komponentbaserade arbetsflödet för DITA-översättning får inte användas om du översätter innehåll via mänsklig översättning. Det här alternativet måste dock användas för maskinöversättning.
- Det globalt använda innehållet och mediet som inte kräver lokalisering bör inte tas med i språkkopiorna.
- Allt vanligt innehåll som måste lokaliseras ska finnas i en gemensam mapp i mappen language.

Följande bild visar ett exempel på en mappstruktur i Adobe Experience Manager när du har globalt använt innehåll och tre språkversioner.

![](images/aem-directory_structure.png){width="800" align="left"}

## Konfigurera översättningstjänst

Utför följande steg för att konfigurera den mänskliga översättningstjänsten eller maskinöversättningstjänsten att använda:

1. I Assets-gränssnittet väljer du källspråksmappen.

1. Öppna mappegenskaperna och gå till fliken **Cloud Services**.

1. Konfigurera översättningstjänsten som du vill använda på fliken **Cloud-tjänster**.

   Du kan konfigurera maskinbaserad eller mänsklig översättning.

   Se till att det bara finns en konfiguration för översättningskopplingen i en mapp. Flera mappar kan skapas under /conf om det finns flera översättningskopplingar. En molnkonfiguration måste vara markerad för källspråksmappen innan översättningsprocessen startas.

   >[!NOTE]
   >
   > Visa [Konfigurera översättningsintegreringsramverket](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/integration-framework.html?lang=en) i Adobe Experience Manager-dokumentationen för mer information om integrering med översättningstjänster från tredje part.

1. Välj **Spara och stäng** om du vill spara de uppdaterade mappegenskaperna.


## Starta översättningsjobbet {#id225IK030OE8}

Så här startar du översättningsjobbet:

1. Gå till projektmappen som du skapade för lokalisering i **Project**-konsolen.

1. Välj lokaliseringsprojektet för att öppna informationssidan.

1. Markera pilen i rutan **Översättningsjobb** och välj **Start** i listan för att starta översättningsarbetsflödet.

   >[!NOTE]
   >
   > Om du använder översättningstjänsten för människor måste du exportera innehållet för översättning. När du har det översatta innehållet måste du importera det tillbaka till översättningsprojektet.

1. Om du vill visa översättningsjobbets status markerar du ellipsen längst ned i rutan **Översättningsjobb**.


När översättningen är klar ändras översättningsjobbets status till *Klar att granskas*. För att slutföra översättningsprocessen måste du godkänna den översatta kopian och resursmetadata från översättningsjobbpanelen i projektkonsolen. Visa [Skapa ett översättningsprojekt](translate-documents-web-editor.md#create-a-translation-project) om du vill starta ett nytt översättningsprojekt.

>[!NOTE]
>
>- Om du avvisar översättningen för ett eller flera ämnen i ett översättningsjobb återställs översättningsstatusen **Pågår** för alla avvisade ämnen till den ursprungliga statusen. Statusen för de refererade ämnena kontrolleras och återställs enligt det senaste översättningstillståndet. Översättningsfilerna som skapas i målspråksmappen tas inte bort även om översättningen avvisas för dem.
>- Om du avvisar, tar bort eller avbryter översättningsjobbet för ett ämne som finns i flera projekt (för något av projekten) återställs inte översättningsstatusen **Pågår** för ämnet, men projektet tas bort från projektlistan **Pågår** för den aktuella resursen.
>- Om du dessutom avbryter eller tar bort översättningsjobbet eller tar bort hela projektet återställs översättningsstatusen **Pågår** till den ursprungliga statusen.

**Överordnat ämne:**[&#x200B;Översikt över innehållsöversättning](translation.md)
