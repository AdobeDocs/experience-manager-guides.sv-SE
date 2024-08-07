---
title: Snabbmenyer
description: Anpassa snabbmenyer
role: User, Admin
exl-id: 25aa76dd-ef05-41ed-b980-14bbc1626059
source-git-commit: 492f72768e0de74a91eb7acc9db8264e21bfc810
workflow-type: tm+mt
source-wordcount: '154'
ht-degree: 0%

---

# Anpassa snabbmenyer

Följande snabbmenyer kan anpassas:

- `file_options`
styrenheter:
   - Kartvy: `ditamap_viewer_controller`
   - Databaspanel: `repository_panel_controller`
   - Favoritpanel: `collection_tree_controller`
   - Referenslänkar för filegenskaper: `file_references_links_controller`
   - Databassökpanel: `repository_search_controller`
   - Ämnesschema: `subject_scheme_tree_controller`

- `folder_options`
styrenheter:
   - Databaspanel: `repository_panel_controller`
   - Favoritpanel: `collection_tree_controller`

- `collection_options`
styrenheter:
   - Favoritpanel: `collection_tree_controller`

- `map_view_options`
styrenheter:
   - Kartvy: `ditamap_viewer_controller`

- `baseline_panel_menu`
styrenheter:
   - Baslinjepanel: `baseline_panel`

- `preset_item_menu`
styrenheter:
   - Förinställningspanelen: `preset_panel`

Du kan också skapa en egen snabbmeny genom att definiera ett nytt unikt ID.

Nu har varje snabbmeny en `controller id` kopplad till sig. Den här kontrollenheten hanterar `on-event`-funktionen för de olika alternativen på snabbmenyn

Låt oss ta ett exempel

```js title=customise_context_menu.js"
const loadDitaFile = (filePath, uuid) =>{
  return $.ajax({
    type: 'POST',
    url: '/bin/referencelistener',
    data: {
        operation: 'getdita',
        path: filePath,
        type: uuid ? 'UUID' : 'PATH',
        cache: false,
    },
  })
}

const fileOptions = {
    id: "file_options",
    contextMenuWidget: "repository_panel",
    view: {
            items: [
                {
                    component: "div",
                    target: {
                        key:"displayName",value: "Delete",                    
                        viewState: VIEW_STATE.REPLACE
                    }
                },
                {
                    component: "div",
                    target: {
                        key:"displayName",value: "Edit",                    
                        viewState: VIEW_STATE.REPLACE
                    }
                },
                {
                    "displayName": "Download",
                    "data": {
                      "eventid": "downloadFile"
                    },
                    "icon": "downloadFromCloud",
                    "class": "menu-separator",         
                    target: {
                        key:"displayName",value: "Duplicate",                    
                        viewState: VIEW_STATE.REPLACE
                    }
                },
            ]

    },

    controller: {
        downloadFile(){
            const path  = this.getValue('selectedItems')[0].path
            loadDitaFile(path).then((file) => {
              function download_file(name, contents) {
                const mime_type = "text/plain";
        
                const blob = new Blob([contents], {type: mime_type});
        
                const dlink = document.createElement('a');
                dlink.download = name;
                dlink.href = window.URL.createObjectURL(blob);
                dlink.onclick = function() {
                    // revokeObjectURL needs a delay to work properly
                    const that = this;
                    setTimeout(function() {
                        window.URL.revokeObjectURL(that.href);
                    }, 1500);
                };
        
                dlink.click();
                dlink.remove();
            }
            download_file(path,file.xml)
            });
          }
    }
}
```

Låt oss nu förstå vad den här koden gör.

1. `id` används för att identifiera den snabbmeny som vi vill anpassa.
2. `contextMenuWidget` används för att definiera `widget id` eller `component` som anropar snabbmenyn och hanterar `events`.

Resten av den är densamma, vilket innebär att `view` används för att definiera objekten, `target` identifierar var alternativet ska ersättas, läggas till eller föregås av tillägg och att `contextMenuWidget`-kontrollanten hanterar `on-click` -händelserna.
