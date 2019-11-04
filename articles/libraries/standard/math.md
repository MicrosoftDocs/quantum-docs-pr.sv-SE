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
# <a name="classical-mathematical-functions"></a><span data-ttu-id="3915c-103">Klassiska matematiska funktioner</span><span class="sxs-lookup"><span data-stu-id="3915c-103">Classical Mathematical Functions</span></span> #

<span data-ttu-id="3915c-104">Dessa funktioner används främst för att arbeta med de inbyggda data typerna Q # som `Int`, `Double`och `Range`.</span><span class="sxs-lookup"><span data-stu-id="3915c-104">These functions are primarily used to work with the Q# built-in data types `Int`, `Double`, and `Range`.</span></span>

<span data-ttu-id="3915c-105">Signaturen för åtgärden <xref:microsoft.quantum.intrinsic.random> har `(Double[] => Int)`.</span><span class="sxs-lookup"><span data-stu-id="3915c-105">The <xref:microsoft.quantum.intrinsic.random> operation has signature `(Double[] => Int)`.</span></span>
<span data-ttu-id="3915c-106">Det tar en matris med dubbla värden som indatatyper och returnerar ett slumpmässigt markerat index i matrisen som en `Int`.</span><span class="sxs-lookup"><span data-stu-id="3915c-106">It takes an array of doubles as input, and returns a randomly-selected index into the array as an `Int`.</span></span>
<span data-ttu-id="3915c-107">Sannolikheten för att välja ett speciellt index är proportionerlig till värdet för mat ris elementet i det indexet.</span><span class="sxs-lookup"><span data-stu-id="3915c-107">The probability of selecting a specific index is proportional to the value of the array element at that index.</span></span> <span data-ttu-id="3915c-108">n mat ris element som är lika med noll ignoreras och deras index returneras aldrig.</span><span class="sxs-lookup"><span data-stu-id="3915c-108">n Array elements that are equal to zero are ignored and their indices are never returned.</span></span>
<span data-ttu-id="3915c-109">Om något mat ris element är mindre än noll, eller om inget mat ris element är större än noll, så Miss lyckas åtgärden.</span><span class="sxs-lookup"><span data-stu-id="3915c-109">If any array element is less than zero, or if no array element is greater than zero, then the operation fails.</span></span>