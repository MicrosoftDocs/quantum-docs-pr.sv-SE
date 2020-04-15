---
title: Quantum Development Kit-bibliotek
description: Översikt över de standard-, kemi- och matematikbibliotek som ingår i Microsoft Quantum Development Kit.
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries
ms.openlocfilehash: 89612aaa5c11e1a5e0d418256e96366953fdd3fe
ms.sourcegitcommit: 9d1c045cf1a2c3e19030cb38dbc7496dbd24ab58
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2020
ms.locfileid: "77906414"
---
# <a name="overview-of-q-libraries"></a><span data-ttu-id="231e3-103">Översikt över Q#-biblioteken</span><span class="sxs-lookup"><span data-stu-id="231e3-103">Overview of Q# Libraries</span></span>
<span data-ttu-id="231e3-104">Det finns flera bibliotek som medföljer Quantum Development Kit och gör det enklare att utveckla kvantprogram i Q#.</span><span class="sxs-lookup"><span data-stu-id="231e3-104">The Quantum Development Kit is provided with several libraries to make it easier to develop quantum applications in Q#.</span></span>
<span data-ttu-id="231e3-105">I det här avsnittet av dokumentationen beskriver vi dessa bibliotek och hur du använder dem i dina program.</span><span class="sxs-lookup"><span data-stu-id="231e3-105">In this section of the documentation, we describe these libraries and how to use them in your programs.</span></span>

- <span data-ttu-id="231e3-106">[**Standardbibliotek**](xref:microsoft.quantum.libraries.standard.intro): I det här avsnittet beskrivs inledningen, som definierar gränssnittet mellan Q#-program och måldatorer samt Canon, ett Q#-bibliotek som tillhandahåller generella åtgärder och funktioner som används vid skrivandet av Q#-program.</span><span class="sxs-lookup"><span data-stu-id="231e3-106">[**Standard libraries**](xref:microsoft.quantum.libraries.standard.intro): This section describes the prelude, which defines the interface between Q# programs and target machines, and the canon, a Q# library that provides general-purpose operations and functions for use in writing Q# programs.</span></span>
- <span data-ttu-id="231e3-107">[**Bibliotek för kvantkemi**](xref:microsoft.quantum.chemistry.concepts.intro): Det här avsnittet beskriver kvantkemibiblioteket, som tillhandahåller en datamodell för inläsning av representationer av fermioniska hamiltonska värden samt åtgärder och funktioner för kvantsimulering som agerar på dessa representationer.</span><span class="sxs-lookup"><span data-stu-id="231e3-107">[**Quantum chemistry library**](xref:microsoft.quantum.chemistry.concepts.intro): This section describes the quantum chemistry library, which provides a data model for loading representations of fermionic Hamiltonians and quantum simulation operations and functions which act on these representations.</span></span>
- <span data-ttu-id="231e3-108">[**Bibliotek för kvantmatematik**](xref:microsoft.quantum.numerics.intro): I det här avsnittet beskrivs biblioteket för kvantmatematik, som innehåller implementeringar för en mängd olika matematiska funktioner.</span><span class="sxs-lookup"><span data-stu-id="231e3-108">[**Quantum numerics library**](xref:microsoft.quantum.numerics.intro): This section describes the quantum numerics library, which provides implementations for a host of mathematical functions.</span></span> <span data-ttu-id="231e3-109">Det stöder heltal (signerade och osignerade) samt representationer av fast punkt.</span><span class="sxs-lookup"><span data-stu-id="231e3-109">It supports integer (signed & unsigned) and fixed-point representations.</span></span>

<span data-ttu-id="231e3-110">Bibliotekets källor samt kodexempel kan hämtas från GitHub.</span><span class="sxs-lookup"><span data-stu-id="231e3-110">Sources of the libraries as well as code samples can be obtained from GitHub.</span></span> <span data-ttu-id="231e3-111">Mer information finns i [licensavsnittet](xref:microsoft.quantum.libraries.licensing).</span><span class="sxs-lookup"><span data-stu-id="231e3-111">See also the [licensing](xref:microsoft.quantum.libraries.licensing) section for further information.</span></span> <span data-ttu-id="231e3-112">Observera att det även finns paketreferenser (”binärfiler”) för biblioteken, vilket är ett annat sätt att inkludera biblioteken i projekt.</span><span class="sxs-lookup"><span data-stu-id="231e3-112">It should be noted that package references ("binaries") are available also for the libraries which offers another way of including the libraries in projects.</span></span> <span data-ttu-id="231e3-113">Du kan enkelt skaffa dem via [NuGet](https://nuget.org).</span><span class="sxs-lookup"><span data-stu-id="231e3-113">A convenient way of obtaining them is via [nuget](https://nuget.org).</span></span>
