---
title: Komponenter
description: Granska appkomponenter
role: User, Admin
exl-id: 78d626f9-9f96-4748-a268-39fa57aef495
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
workflow-type: tm+mt
source-wordcount: '127'
ht-degree: 0%

---

# Granskningsappens komponenter

Följande är huvudkomponenterna i granskningsappen:

- Textbunden granskningspanel: `id: inline_review_panel`
   - Den högra panelen där granskningskommentarerna återges på XML-redigeringssidan.

![Skärmbild på panelen Textbunden granskning](./imgs/inline_review.png)

- Ämnesgranskningar: `id: topic_reviews`
   - Den högra panelen där kommentarerna återges i granskningsappen.

![Skärmbild på panelen Ämnesgranskning](./imgs/topic_reviews.png)

- Granskningskommentar: `id: review_comment`
   - Widgeten för varje granskningskommentar.

Granskningskommentar på granskningsappen:
![Granska skärmbild för kommentarer](./imgs/review_comment.png)

Granska kommentaren i xml-redigeraren:
![Granska skärmbild för kommentarer](./imgs/review_comment_xmleditor.png)

- Granskningskommentarssvar: `id: comment_reply`
   - Widgeten för varje svar på granskningskommentar.
     ![Förhandsgranska kommentarsvar, skärmbild](./imgs/reply.png)

- Nytt svar på granskningskommentar: `id: comment_new_reply`
   - Widgeten för svar på nya granskningskommentarer.
     ![Nytt svar på granskningskommentar, bild](./imgs/new_reply.png)

- Anteckningsverktygslåda: `id: annotation_toolbox`
   - Det övre högra verktygsfältet i granskningsappen.
     ![Skärmbild för anteckningsverktygslåda](./imgs/annotation_toolbox.png)
