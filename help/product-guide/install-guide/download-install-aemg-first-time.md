---
title: Ladda ned och installera AEM Guides för första gången
description: Lär dig hur du hämtar och installerar AEM Guides för första gången
exl-id: 830a4381-303c-419c-b87f-9563352a7eeb
feature: Introduction, Installation
role: Admin
level: Experienced
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 0%

---

# Ladda ned och installera AEM Guides för första gången {#id213BCL00KEV}

Så här hämtar och installerar du AEM Guides första gången på en dator:

>[!IMPORTANT]
>
> Om du vill använda Livefyre tillsammans med AEM Guides måste du installera Livefyre-versionerna tidigare än 3.0 innan du installerar AEM Guides. Om du använder Livefyre version 3.0 eller senare finns det ingen sådan begränsning.

1. Hämta AEM Guides från Adobe Software Distribution Portal.

1. Logga in i AEM och navigera till CRX Package Manager. Standardwebbadressen för att få åtkomst till pakethanteraren är:

   ```http
   http://<server name>:<port>/crx/packmgr/index.jsp
   ```

   Pakethanteraren hanterar paketen i din lokala AEM. Mer information om hur du arbetar med pakethanteraren finns i [Arbeta med paket](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/package-manager.html) i AEM.

   ![](assets/package-manager.png){width="650" align="left"}

1. Klicka på **Överför paket** om du vill överföra AEM Guides-paketet.

1. I dialogrutan Överför paket går du till AEM Guides-filen som du hämtade i steg 1 och klickar på **OK**.

   Paketet överförs till din AEM.

1. Klicka på **Installera** om du vill installera paketet.

   ![](assets/install-package.png){width="650" align="left"}

1. Klicka på **Installera** i dialogrutan Installera paket.

1. Kom igång med AEM Guides genom att klicka på hemknappen ![](assets/home-button.png) i det övre vänstra hörnet av CRX Package Manager.


>[!NOTE]
>
> Utför installationsproceduren på alla instanser av AEM servrar i installationen.

**Överordnat ämne:**[ Hämta och installera](download-install.md)
