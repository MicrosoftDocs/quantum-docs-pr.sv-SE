---
title: Media – viktigt
description: Tips om att ladda upp bilder
author: geduardo
ms.author: v-edsanc
ms.date: 03/04/2020
ms.topic: readme
ms.openlocfilehash: bf28f57820e95bbbf81f5ac7ade582d89b945a26
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834541"
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
