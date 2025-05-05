---
title: Konfigurera en anpassad panel i den vänstra panelen
description: Lär dig hur du konfigurerar en anpassad panel i den vänstra panelen
exl-id: 5c25efc1-0976-4554-a186-2ffd5e62f500
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '87'
ht-degree: 0%

---

# Konfigurera en anpassad panel i den vänstra panelen {#id224JI200Y6F}

Gör så här för att lägga till en anpassad panel i den vänstra panelen i Web Editor:

1. Skapa en *clientlib*-mapp och lägg till din JavaScript- och CSS-fil i den här mappen.
1. Uppdatera egenskapen categories i mappen *clientlib* genom att tilldela den värdet för *apps.fmdita.xml\_editor.page\_overrides*.

Exempelkod för att konfigurera en anpassad panel:

```
tcx.ready(function () { //Ready will call the callback after editor code is set for events and global variable excess
 
 
    // APP_ADD_AUTHOR_LEFT_TAB event will add a new left tab in the left panel, user can show hide it using editor settings
    tcx.eventHandler.next(tcx.eventHandler.KEYS.APP_ADD_AUTHOR_LEFT_TAB, {
            id: 'my_panel',
            class: 'my-panel-tab',
            icon: 'file', //Any valid Adobe Spectrum icon name https://spectrum.adobe.com/page/icons/
            label: 'My Tab',
            prevTabID: 'repository_panel' //Existing tab ids are 'collection_panel', 'repository_panel', 'map_panel', 'outline_panel', 'conref_panel', 'glossary_panel', 'condition_panel', 'subject_scheme_panel', 'snippet_panel', 'template_panel', 'search_panel'
    })
 
    // APP_PANEL_DID_MOUNT event will be called after user has selected the panel and panel is rendered in the DOM
    tcx.eventHandler.subscribe({
        key: tcx.eventHandler.KEYS.APP_PANEL_DID_MOUNT,
        next: function(opts) {
            // TODO create panel ui inside $el
            let $el = opts.$el //$el is Tab panel content html node
            let id = opts.id //id is tab panel id (my_panel)
            console.log("mounted", opts)
        }
    })
 
  // APP_PANEL_WILL_UNMOUNT will be called before destorying the new left panel
  tcx.eventHandler.subscribe({
        key: tcx.eventHandler.KEYS.APP_PANEL_WILL_UNMOUNT,
        next: function(opts) {
            //TODO do some cleanup
            let id = opts.id //id is tab panel id (my_panel)
            console.log("unmounted", opts)
        }
    })
 
});
```

**Överordnat ämne:**&#x200B;[ Anpassa Web Editor](conf-web-editor.md)
