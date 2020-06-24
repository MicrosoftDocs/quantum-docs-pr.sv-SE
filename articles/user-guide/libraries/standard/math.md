---
title: 'Matematik i Q # standard-bibliotek'
description: 'Lär dig mer om de klassiska matematiska funktionerna i de Q # standard-bibliotek som används med de inbyggda data typerna.'
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: bec866472abc0d4327cdc570306341375395f492
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275662"
---
# <a name="classical-mathematical-functions"></a>Klassiska matematiska funktioner #

Dessa funktioner används främst för att arbeta med de inbyggda data typerna Q #, `Int` `Double` och `Range` .

<xref:microsoft.quantum.intrinsic.random>Åtgärden har en signatur `(Double[] => Int)` .
Det tar en matris med dubbla värden som indatatyper och returnerar ett slumpmässigt markerat index i matrisen som en `Int` .
Sannolikheten för att välja ett speciellt index är proportionerlig till värdet för mat ris elementet i det indexet. n mat ris element som är lika med noll ignoreras och deras index returneras aldrig.
Om något mat ris element är mindre än noll, eller om inget mat ris element är större än noll, så Miss lyckas åtgärden.
