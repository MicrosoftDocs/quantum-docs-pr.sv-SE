---
title: Matematik i Q# standard biblioteken
description: Lär dig mer om de klassiska matematiska funktionerna i de Q# standard bibliotek som används med de inbyggda data typerna.
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad
ms.topic: conceptual
no-loc:
- Q#
- $$v
ms.openlocfilehash: a2e2656f42213c8ae9e984f63f3ebf4058520532
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854001"
---
# <a name="classical-mathematical-functions"></a>Klassiska matematiska funktioner #

Dessa funktioner används främst för att arbeta med de Q# inbyggda data typerna `Int` , `Double` och `Range` .

<xref:Microsoft.Quantum.Intrinsic.Random>Åtgärden har en signatur `(Double[] => Int)` .
Det tar en matris med dubbla värden som indatatyper och returnerar ett slumpmässigt markerat index i matrisen som en `Int` .
Sannolikheten för att välja ett speciellt index är proportionerlig till värdet för mat ris elementet i det indexet. n mat ris element som är lika med noll ignoreras och deras index returneras aldrig.
Om något mat ris element är mindre än noll, eller om inget mat ris element är större än noll, så Miss lyckas åtgärden.
