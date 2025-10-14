---
title: Öka översättningsprestanda för DITA-filer i AEM
description: Best Practices, tips and tricks to increase DITA translation project performance in AEM Guides
feature: Translation
role: User, Admin
author: Pulkit Nagpal (punagpal)
exl-id: d7e4f3ae-2143-4767-b7ab-c89f5e5eef59
source-git-commit: 18fe3cbb1439d489d243d98a546ef1095104a863
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 0%

---

# De bästa sätten att följa för översättning i AEM Guides

Prestanda för ditt översättningsprojekt kan minska i takt med att översättningsaktiviteten på systemet ökar med tiden.

Varje översättningsprojekt genererar flera användargrupper för åtkomst, vilket leder till ett ökat antal användargrupper i systemet. När antalet användargrupper ökar kan det gradvis minska antalet CRUD-åtgärder som rör användarbehörigheter, vilket kan påverka den övergripande AEM. Om översättningsprojekt förblir aktiva efter slutförandet kan det dessutom påverka resultatet av översättningssynkroniseringen mellan AEM och översättningsleverantören negativt.

**Om du följer de bästa metoderna som beskrivs nedan kan du upprätthålla en effektiv miljö.**

## Om du använder en äldre version än 4.6 (lokal) eller 2404 (moln):

- Markera alla projekt som&quot;inaktiva&quot; när översättningen är klar och godkänd. Projektet är fortfarande tillgängligt för granskning och markeras helt enkelt som inaktivt.
   - Följ dessa steg för att upprätthålla övergripande översättningsprestanda vid god hälsa.

     ![Inaktivt översättningsprojekt &#x200B;](../assets/translation/translation-project-image1.png)

- För äldre projektmapp, som är markerad som inaktiv, bör godkänd och granskad tas bort
   - Följ de här stegen för att behålla övergripande översättningsprestanda i god hälsa genom att rensa upp temporära översättningsfiler och användargrupper som är kopplade till den här projektmappen.

     ![Ta bort översättningsprojekt och mapp &#x200B;](../assets/translation/translation-project-image2.png)


## Om du är på, bygg 4.6 eller 2404 eller senare:

Du kan fortsätta att följa samma steg som ovan. Från och med version 4.6/2404 introducerar AEM Guides en redigeringsinställning där administratörer kan inaktivera automatisk borttagning av översättningsprojekt.

Referens: [Ta bort eller inaktivera ett slutfört översättningsprojekt automatiskt](https://experienceleague.adobe.com/en/docs/experience-manager-guides/using/user-guide/author-content/create-preview-topics/author-content-aem-guides/work-with-web-editor/translate-documents-web-editor#automatically-delete-or-disable-a-completed-translation-project)

![Automatiska inställningar för att ta bort och inaktivera översättningsprojekt i AEM Guides &#x200B;](../assets/translation/translation-project-image3.png)
