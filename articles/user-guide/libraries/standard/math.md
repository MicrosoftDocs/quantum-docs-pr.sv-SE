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
# <a name="classical-mathematical-functions"></a><span data-ttu-id="64e62-103">Klassiska matematiska funktioner</span><span class="sxs-lookup"><span data-stu-id="64e62-103">Classical Mathematical Functions</span></span> #

<span data-ttu-id="64e62-104">Dessa funktioner används främst för att arbeta med de Q# inbyggda data typerna `Int` , `Double` och `Range` .</span><span class="sxs-lookup"><span data-stu-id="64e62-104">These functions are primarily used to work with the Q# built-in data types `Int`, `Double`, and `Range`.</span></span>

<span data-ttu-id="64e62-105"><xref:Microsoft.Quantum.Intrinsic.Random>Åtgärden har en signatur `(Double[] => Int)` .</span><span class="sxs-lookup"><span data-stu-id="64e62-105">The <xref:Microsoft.Quantum.Intrinsic.Random> operation has signature `(Double[] => Int)`.</span></span>
<span data-ttu-id="64e62-106">Det tar en matris med dubbla värden som indatatyper och returnerar ett slumpmässigt markerat index i matrisen som en `Int` .</span><span class="sxs-lookup"><span data-stu-id="64e62-106">It takes an array of doubles as input, and returns a randomly-selected index into the array as an `Int`.</span></span>
<span data-ttu-id="64e62-107">Sannolikheten för att välja ett speciellt index är proportionerlig till värdet för mat ris elementet i det indexet.</span><span class="sxs-lookup"><span data-stu-id="64e62-107">The probability of selecting a specific index is proportional to the value of the array element at that index.</span></span> <span data-ttu-id="64e62-108">n mat ris element som är lika med noll ignoreras och deras index returneras aldrig.</span><span class="sxs-lookup"><span data-stu-id="64e62-108">n Array elements that are equal to zero are ignored and their indices are never returned.</span></span>
<span data-ttu-id="64e62-109">Om något mat ris element är mindre än noll, eller om inget mat ris element är större än noll, så Miss lyckas åtgärden.</span><span class="sxs-lookup"><span data-stu-id="64e62-109">If any array element is less than zero, or if no array element is greater than zero, then the operation fails.</span></span>
