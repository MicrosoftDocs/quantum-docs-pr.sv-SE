---
title: Matematik i Q# standard biblioteken
description: Lär dig mer om de klassiska matematiska funktionerna i de Q# standard bibliotek som används med de inbyggda data typerna.
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: 55b1ef70eed1eb47ab0c6b30e2b8203c38c9a67a
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833601"
---
# <a name="classical-mathematical-functions"></a>Klassiska matematiska funktioner #

Dessa funktioner används främst för att arbeta med de Q# inbyggda data typerna `Int` , `Double` och `Range` .

<xref:microsoft.quantum.intrinsic.random>Åtgärden har en signatur `(Double[] => Int)` .
Det tar en matris med dubbla värden som indatatyper och returnerar ett slumpmässigt markerat index i matrisen som en `Int` .
Sannolikheten för att välja ett speciellt index är proportionerlig till värdet för mat ris elementet i det indexet. n mat ris element som är lika med noll ignoreras och deras index returneras aldrig.
Om något mat ris element är mindre än noll, eller om inget mat ris element är större än noll, så Miss lyckas åtgärden.
