---
title: Avinstallera AEM Guides
description: Så här avinstallerar du AEM Guides
feature: Installation
role: Admin
level: Experienced
source-git-commit: 834959a6a0e22cd5d2b2c5d0e57ceb6d45c0c666
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 0%

---

# Avinstallera AEM Guides för lokal installation{#id21BHG0C0SXA}

Du kan avinstallera AEM Guides för On-Premise med CRX Package Manager. Under avinstallationen återställs innehållet i databasen till ögonblicksbilden som gjordes omedelbart innan paketet installerades.

Så här avinstallerar du AEM Guides för lokal installation:

1. Logga in på din AEM-instans och navigera till CRX Package Manager. Standardwebbadressen för att få åtkomst till pakethanteraren är:

   ```http
   http://<server name>:<port>/crx/packmgr/index.jsp
   ```

1. Sök efter paketet `com.adobe.fmdita`.
1. Klicka på paketet för att expandera det.
1. Klicka på **Mer** för att öppna listrutan.
1. Klicka på **Avinstallera** och vänta tills avinstallationen är klar.
1. Om du inte längre behöver det här paketet klickar du på **Ta bort** när du har avinstallerat paketet.

## Efter avinstallation

Så här rensar du de återstående filerna efter avinstallationen:

1. Rensa skriptcachen med:

   ```http
   http://<host>:<port>/system/console/scriptcache
   ```

1. Du kan göra cacheminnet ogiltigt med:

   ```http
   http://<host>:<port>/libs/granite/ui/content/dumplibs.rebuild.html?back=true
   ```

1. Klicka på **Invalidera cache**.
1. Rensa webbläsarens cache.
