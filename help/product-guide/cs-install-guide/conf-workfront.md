---
title: Konfigurera Adobe Workfront i Experience Manager Guides
description: Så här konfigurerar du Workfront i Experience Manager Guides
feature: Authoring
role: Admin
level: Experienced
exl-id: 1f72642c-e694-47cd-9182-f4f4aaf69655
source-git-commit: 4ac91ae3be8a7eda99389288c4a70a2047456071
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 0%

---

# Konfigurera Adobe Workfront

Adobe Workfront är en molnbaserad arbetshanteringslösning som hjälper team och organisationer att planera, spåra och hantera sitt arbete effektivt. Integrationen mellan Experience Manager Guides och Adobe Workfront ger dig tillgång till robusta projekthanteringsfunktioner utöver Experience Manager Guides centrala CCMS-funktioner, så att du effektivt kan planera, fördela och spåra uppgifter.

Läs mer om [Adobe Workfront-integrering](../user-guide/workfront-integration.md) i Experience Manager Guides.

## Förutsättningar

Innan du börjar, se till att:

1. Du har standardåtkomst till Adobe Workfront och administratörsåtkomst till Experience Manager Guides.
2. Du [skapar ett nytt anpassat formulär i Adobe Workfront](https://experienceleague.adobe.com/en/docs/workfront/using/administration-and-setup/customize/custom-forms/design-a-form/design-a-form) som krävs för Experience Manager Guides genom att använda följande fält:

   | Fälttyp | Etikett | Namn | Alternativ (Visa värden är aktiverade) |
   |------------|------|------|-------------------------------|
   | Listruta med ett val | Typ av aktivitet | uppgiftstyp | Authoring (value = AUTHOR), Publishing (value = PUBLISH), Translation (value = TRANSLATION), Review (value = REVIEW) |
   | Listruta med ett val | Aktivitetsläge | uppgiftsläge | Authoring (value = AUTHOR), Publishing (value = PUBLISH), Translation (value = TRANSLATION), Review (value = REVIEW) |
   | Text med formatering | Författarlista | författarlista | - |
   | Text med formatering | Granskarlista | granskarlista | - |
   | Enkelradig text | Granska URL | review-url | - |
   | Enkelradig text | Aktivitets-URL | task-url | - |
   | Enkelradstext | E-postämne | e-postämne | - |

>[!NOTE]
>
> * I tabellen ovan representerar alternativen tillgängliga under fältet **Åtgärdstyp**. För varje alternativ måste du ange **aktivitetsnamnet** och **aktivitetsvärdet**. Namnet och värdena för varje uppgiftstyp måste vara exakt desamma som i tabellen ovan. För uppgiftstypen Författare anger du till exempel **Författare** som namn och **FÖRFATTARE** som motsvarande värde.
> * När du arbetar med prem-tjänster ska du alltid se till att `localhost` ersätts med rätt serveradress i konfigurationen **Day CQ Link Externalizer** för att kunna ta emot den lösta aktivitetslänken i e-postmeddelanden.
> * När du skapar en granskningsåtgärd i Workfront måste användare (författare eller granskare) ingå i gruppen **workflow-users**. Som **författare** måste du dessutom vara en del av gruppen **content-authors** och **authors** , medan du som **granskare** måste vara en del av gruppen **reviewers** .


## Kom igång

Utför följande steg för att konfigurera Adobe Workfront i Experience Manager Guides.

1. Öppna **verktygspanelen** och välj **Stödlinjer**.
2. Välj **Konfigurera Workfront**.

   Sidan **Workfront-konfiguration** visas.

   ![](assets/configure-workfront-page.png)

3. Ange den fullständiga URL:en för din organisations Workfront-domän, klient-ID och klienthemlighet på **Workfront-konfigurationssidan**.

   Navigera till **om du vill komma åt nyckeln** Klient-ID **och** Klienthemlighet`Setup >> Systems>> oAuth2 Applications` som konfigurerats i din Adobe Workfront-konfiguration.

   Mer information om hur du konfigurerar din Adobe Workfront-domän finns i avsnittet Auktoriseringskoder i [Skapa OAuth2-program för Workfront-integreringar](https://experienceleague.adobe.com/en/docs/workfront/using/administration-and-setup/configure-integrations/create-oauth-application#create-an-oauth2-application-using-user-credentials-authorization-code-flow).

4. Välj **Logga in och verifiera**.

   Du omdirigeras till Adobe Workfront Sign-sidan.
5. Logga in med din Adobe Workfront-e-postadress och välj sedan **Tillåt åtkomst** för att Oauth2-programmet ska få åtkomst till ditt respektive Adobe Workfront-konto.

   Du omdirigeras automatiskt till Workfront konfigurationssida på Experience Manager Guides.

6. I den anpassade formulärlistrutan väljer du det anpassade Adobe Workfront-formulär som du har skapat för Experience Manager Guides. Visa [Krav](#prerequisites).
7. Välj **Spara och stäng** för att tillämpa och spara konfigurationsändringarna för Workfront.

När konfigurationen är klar lägger [till användare i Adobe Workfront](https://experienceleague.adobe.com/en/docs/workfront/using/administration-and-setup/add-users/create-manage-users/add-users) med samma e-postadresser som de har i Experience Manager Guides.
