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
# <a name="classical-mathematical-functions"></a><span data-ttu-id="d276f-103">Klassiska matematiska funktioner</span><span class="sxs-lookup"><span data-stu-id="d276f-103">Classical Mathematical Functions</span></span> #

<span data-ttu-id="d276f-104">Dessa funktioner används främst för att arbeta med de inbyggda data typerna Q #, `Int` `Double` och `Range` .</span><span class="sxs-lookup"><span data-stu-id="d276f-104">These functions are primarily used to work with the Q# built-in data types `Int`, `Double`, and `Range`.</span></span>

<span data-ttu-id="d276f-105"><xref:microsoft.quantum.intrinsic.random>Åtgärden har en signatur `(Double[] => Int)` .</span><span class="sxs-lookup"><span data-stu-id="d276f-105">The <xref:microsoft.quantum.intrinsic.random> operation has signature `(Double[] => Int)`.</span></span>
<span data-ttu-id="d276f-106">Det tar en matris med dubbla värden som indatatyper och returnerar ett slumpmässigt markerat index i matrisen som en `Int` .</span><span class="sxs-lookup"><span data-stu-id="d276f-106">It takes an array of doubles as input, and returns a randomly-selected index into the array as an `Int`.</span></span>
<span data-ttu-id="d276f-107">Sannolikheten för att välja ett speciellt index är proportionerlig till värdet för mat ris elementet i det indexet.</span><span class="sxs-lookup"><span data-stu-id="d276f-107">The probability of selecting a specific index is proportional to the value of the array element at that index.</span></span> <span data-ttu-id="d276f-108">n mat ris element som är lika med noll ignoreras och deras index returneras aldrig.</span><span class="sxs-lookup"><span data-stu-id="d276f-108">n Array elements that are equal to zero are ignored and their indices are never returned.</span></span>
<span data-ttu-id="d276f-109">Om något mat ris element är mindre än noll, eller om inget mat ris element är större än noll, så Miss lyckas åtgärden.</span><span class="sxs-lookup"><span data-stu-id="d276f-109">If any array element is less than zero, or if no array element is greater than zero, then the operation fails.</span></span>
