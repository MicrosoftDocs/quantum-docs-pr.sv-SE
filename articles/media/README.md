---
title: Media – viktigt
description: Tips om att ladda upp bilder
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 03/04/2020
ms.topic: readme
ms.openlocfilehash: a4922e28a8fc5ddfb4cbc80302e23869154234d8
ms.sourcegitcommit: d61b388651351e5abd4bfe7a672e88b84a6697f8
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/10/2020
ms.locfileid: "79024193"
---
# <a name="readme"></a>FILEN
**Viktigt**: om du vill att bilderna ska återges korrekt i mörkt läge måste du undvika Oh-filer.
- För. jpg-filer behöver du inte göra någonting eftersom fil formatet inte stöder transparenta element.
- För. png-filer måste du lägga till en vit bakgrund eller ändra värdet för alfa kanalen till 100. Det enklaste sättet att göra detta i Windows är genom att öppna filen i Paint och spara, overwritting den ursprungliga filen.
- För. SVG-filer måste du lägga till en vit rektangel i det lägsta lagret. Det kan du göra med Inkscape:
  - Öppna SVG-filen.
  - Välj verktyget Square Maker och rita en vit rektangel ovanpå den ursprungliga bilden.
  - Välj verktyget "Välj och transformera objekt" genom att klicka på den mörka pilen eller trycka på F1.
  - När du har valt rektangeln klickar du på verktygsfälts elementet "nedre markering till nederkant" (slut) ".
  - Justera rektangeln med musen och piltangenterna.
