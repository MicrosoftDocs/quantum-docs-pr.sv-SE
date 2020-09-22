---
title: Quantum Development Kit-bibliotek
description: Översikt över de standard-, kemi- och matematikbibliotek som ingår i Microsoft Quantum Development Kit.
author: cgranade
ms.author: chgranad
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries
no-loc:
- Q#
- $$v
ms.openlocfilehash: 90672b6ec78bf8305bdb3ab8326002cf8ce34bfe
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835731"
---
# <a name="overview-of-no-locq-libraries"></a><span data-ttu-id="0a368-103">Översikt av Q#-bibliotek</span><span class="sxs-lookup"><span data-stu-id="0a368-103">Overview of Q# Libraries</span></span>
<span data-ttu-id="0a368-104">Det finns flera bibliotek som medföljer Quantum Development Kit och som gör det enklare att utveckla kvantprogram i Q#.</span><span class="sxs-lookup"><span data-stu-id="0a368-104">The Quantum Development Kit is provided with several libraries to make it easier to develop quantum applications in Q#.</span></span>
<span data-ttu-id="0a368-105">I det här avsnittet av dokumentationen beskriver vi dessa bibliotek och hur du använder dem i dina program.</span><span class="sxs-lookup"><span data-stu-id="0a368-105">In this section of the documentation, we describe these libraries and how to use them in your programs.</span></span>

- <span data-ttu-id="0a368-106">[**Standardbibliotek**](xref:microsoft.quantum.libraries.standard.intro): I det här avsnittet beskrivs inledningen, som definierar gränssnittet mellan Q#-program och måldatorer samt canon, ett Q#-bibliotek som tillhandahåller generella åtgärder och funktioner som används vid skrivandet av Q#-program.</span><span class="sxs-lookup"><span data-stu-id="0a368-106">[**Standard libraries**](xref:microsoft.quantum.libraries.standard.intro): This section describes the prelude, which defines the interface between Q# programs and target machines, and the canon, a Q# library that provides general-purpose operations and functions for use in writing Q# programs.</span></span>
- <span data-ttu-id="0a368-107">[**Bibliotek för kvantkemi**](xref:microsoft.quantum.chemistry.concepts.intro): Det här avsnittet beskriver kvantkemibiblioteket, som tillhandahåller en datamodell för inläsning av representationer av fermioniska hamiltonska värden samt åtgärder och funktioner för kvantsimulering som agerar på dessa representationer.</span><span class="sxs-lookup"><span data-stu-id="0a368-107">[**Quantum chemistry library**](xref:microsoft.quantum.chemistry.concepts.intro): This section describes the quantum chemistry library, which provides a data model for loading representations of fermionic Hamiltonians and quantum simulation operations and functions which act on these representations.</span></span>
- <span data-ttu-id="0a368-108">[**Bibliotek för kvantmatematik**](xref:microsoft.quantum.numerics.intro): I det här avsnittet beskrivs biblioteket för kvantmatematik, som innehåller implementeringar för en mängd olika matematiska funktioner.</span><span class="sxs-lookup"><span data-stu-id="0a368-108">[**Quantum numerics library**](xref:microsoft.quantum.numerics.intro): This section describes the quantum numerics library, which provides implementations for a host of mathematical functions.</span></span> <span data-ttu-id="0a368-109">Det stöder heltal (signerade och osignerade) samt representationer av fast punkt.</span><span class="sxs-lookup"><span data-stu-id="0a368-109">It supports integer (signed & unsigned) and fixed-point representations.</span></span>
- <span data-ttu-id="0a368-110">[**Bibliotek för kvantmaskininlärning**](xref:microsoft.quantum.machine-learning.concepts.intro): I det här avsnittet beskrivs biblioteket för kvantmaskininlärning, som innehåller en implementering av de sekventiella klassificerare som använder kvantberäkning för att förstå data.</span><span class="sxs-lookup"><span data-stu-id="0a368-110">[**Quantum machine learning library**](xref:microsoft.quantum.machine-learning.concepts.intro): This section describes the quantum machine learning library, which provides an implementation of the sequential classifiers that take advantage of quantum computing to understand data.</span></span>

<span data-ttu-id="0a368-111">Bibliotekets källor samt kodexempel kan hämtas från GitHub.</span><span class="sxs-lookup"><span data-stu-id="0a368-111">Sources of the libraries as well as code samples can be obtained from GitHub.</span></span>
<span data-ttu-id="0a368-112">Mer information finns i [Licensiering](xref:microsoft.quantum.libraries.licensing).</span><span class="sxs-lookup"><span data-stu-id="0a368-112">See [Licensing](xref:microsoft.quantum.libraries.licensing) for further information.</span></span> <span data-ttu-id="0a368-113">Observera att det även finns paketreferenser (”binärfiler”) för biblioteken, vilket är ett annat sätt att inkludera biblioteken i projekt på.</span><span class="sxs-lookup"><span data-stu-id="0a368-113">Note that package references ("binaries") are available also for the libraries and offer another way of including the libraries in projects.</span></span>
<span data-ttu-id="0a368-114">Du kan enkelt hämta dem via [NuGet](https://nuget.org).</span><span class="sxs-lookup"><span data-stu-id="0a368-114">A convenient way of obtaining them is via [NuGet](https://nuget.org).</span></span>
