---
title: 'Matematik i Q # standard-bibliotek'
description: 'Lär dig mer om de klassiska matematiska funktionerna i de Q # standard-bibliotek som används med de inbyggda data typerna.'
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: bec866472abc0d4327cdc570306341375395f492
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906159"
---
# <a name="classical-mathematical-functions"></a>Klassiska matematiska funktioner #

Dessa funktioner används främst för att arbeta med de inbyggda data typerna Q # som `Int`, `Double`och `Range`.

Signaturen för åtgärden <xref:microsoft.quantum.intrinsic.random> har `(Double[] => Int)`.
Det tar en matris med dubbla värden som indatatyper och returnerar ett slumpmässigt markerat index i matrisen som en `Int`.
Sannolikheten för att välja ett speciellt index är proportionerlig till värdet för mat ris elementet i det indexet. n mat ris element som är lika med noll ignoreras och deras index returneras aldrig.
Om något mat ris element är mindre än noll, eller om inget mat ris element är större än noll, så Miss lyckas åtgärden.
