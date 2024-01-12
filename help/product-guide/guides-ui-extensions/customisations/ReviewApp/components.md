---
title: Komponenter
description: Granska appkomponenter
role: User, Admin
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '127'
ht-degree: 0%

---


# Granskningsappens komponenter

Följande är huvudkomponenterna i granskningsappen:

- Textbunden granskningspanel: `id: inline_review_panel`
   - Den högra panelen där granskningskommentarerna återges på XML-redigeringssidan.

![Skärmbild på panelen Textgranskning](./imgs/inline_review.png)

- Ämnesgranskningar: `id: topic_reviews`
   - Den högra panelen där kommentarerna återges i granskningsappen.

![Ämnesgranskningspanel, bild](./imgs/topic_reviews.png)

- Granskningskommentar: `id: review_comment`
   - Widgeten för varje granskningskommentar.

Granskningskommentar på granskningsappen:
![Skärmbild för kommentarsgranskning](./imgs/review_comment.png)

Granska kommentaren i xml-redigeraren:
![Skärmbild för kommentarsgranskning](./imgs/review_comment_xmleditor.png)

- Granskningskommentarssvar: `id: comment_reply`
   - Widgeten för varje svar på granskningskommentar.
     ![Skärmbild av kommentarssvar](./imgs/reply.png)

- Nytt svar på granskningskommentar: `id: comment_new_reply`
   - Widgeten för svar på nya granskningskommentarer.
     ![Ny skärmbild för kommentarssvar](./imgs/new_reply.png)

- Anteckningsverktygslåda: `id: annotation_toolbox`
   - Det övre högra verktygsfältet i granskningsappen.
     ![Verktygslåda för anteckning, bild](./imgs/annotation_toolbox.png)
