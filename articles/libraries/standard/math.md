---
title: 'Q # standard bibliotek – matematik | Microsoft Docs'
description: 'Q # standard bibliotek – matematik'
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: 7ac9d321f59f7cc95ad8939a4cf7c36e0c5e0491
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2019
ms.locfileid: "73184465"
---
# <a name="classical-mathematical-functions"></a>Klassiska matematiska funktioner #

Dessa funktioner används främst för att arbeta med de inbyggda data typerna Q # som `Int`, `Double`och `Range`.

Signaturen för åtgärden <xref:microsoft.quantum.intrinsic.random> har `(Double[] => Int)`.
Det tar en matris med dubbla värden som indatatyper och returnerar ett slumpmässigt markerat index i matrisen som en `Int`.
Sannolikheten för att välja ett speciellt index är proportionerlig till värdet för mat ris elementet i det indexet. n mat ris element som är lika med noll ignoreras och deras index returneras aldrig.
Om något mat ris element är mindre än noll, eller om inget mat ris element är större än noll, så Miss lyckas åtgärden.