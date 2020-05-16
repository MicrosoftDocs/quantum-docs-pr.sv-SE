---
title: Magiska kommandon för IQ#
description: 'Sidan snabb referens för SWEETIQ # Magic-kommandon med Q # Jupyter Notebooks'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
uid: microsoft.quantum.guide.quickref.iqsharp
ms.openlocfilehash: 0cd1a2289132e2760a21fd9d4f4083696353e271
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83431027"
---
# <a name="iq-magic-commands"></a><span data-ttu-id="fa314-103">Magiska kommandon för IQ#</span><span class="sxs-lookup"><span data-stu-id="fa314-103">IQ# Magic Commands</span></span>

### <a name="general"></a><span data-ttu-id="fa314-104">Allmänt</span><span class="sxs-lookup"><span data-stu-id="fa314-104">General</span></span>

- <span data-ttu-id="fa314-105">`%config`: Anger eller hämtar konfigurations inställningar.</span><span class="sxs-lookup"><span data-stu-id="fa314-105">`%config`: Sets or gets configuration preferences.</span></span>
- <span data-ttu-id="fa314-106">`%estimate`: Kör en specifik funktion eller åtgärd på QuantumSimulator-mål datorn.</span><span class="sxs-lookup"><span data-stu-id="fa314-106">`%estimate`: Runs a given function or operation on the QuantumSimulator target machine.</span></span>
- <span data-ttu-id="fa314-107">`%lsmagic`: Returnerar en lista med alla tillgängliga Magic-kommandon.</span><span class="sxs-lookup"><span data-stu-id="fa314-107">`%lsmagic`: Returns a list of all currently available magic commands.</span></span>
- <span data-ttu-id="fa314-108">`%package`: Ger möjlighet att läsa in ett NuGet-paket.</span><span class="sxs-lookup"><span data-stu-id="fa314-108">`%package`: Provides the ability to load a Nuget package.</span></span>
- <span data-ttu-id="fa314-109">`%performance`: Rapporterar aktuella prestanda mått för denna kernel.</span><span class="sxs-lookup"><span data-stu-id="fa314-109">`%performance`: Reports current performance metrics for this kernel.</span></span>
- <span data-ttu-id="fa314-110">`%simulate`: Kör en specifik funktion eller åtgärd på QuantumSimulator-mål datorn.</span><span class="sxs-lookup"><span data-stu-id="fa314-110">`%simulate`: Runs a given function or operation on the QuantumSimulator target machine.</span></span>
- <span data-ttu-id="fa314-111">`%toffoli`: Kör en specifik funktion eller åtgärd på ToffoliSimulator Simulator mål datorn.</span><span class="sxs-lookup"><span data-stu-id="fa314-111">`%toffoli`: Runs a given function or operation on the ToffoliSimulator simulator target machine.</span></span>
- <span data-ttu-id="fa314-112">`%who`: Innehåller åtgärder relaterade till den aktuella arbets ytan.</span><span class="sxs-lookup"><span data-stu-id="fa314-112">`%who`: Provides actions related to the current workspace.</span></span>
- <span data-ttu-id="fa314-113">`%workspace`: Returnerar en lista över alla åtgärder och funktioner som definierats i den aktuella sessionen, antingen interaktivt eller har lästs in från den aktuella arbets ytan.</span><span class="sxs-lookup"><span data-stu-id="fa314-113">`%workspace`: Returns a list of all operations and functions defined in the current session, either interactively or loaded from the current workspace.</span></span>

### <a name="chemistry"></a><span data-ttu-id="fa314-114">Kemiska</span><span class="sxs-lookup"><span data-stu-id="fa314-114">Chemistry</span></span>

- <span data-ttu-id="fa314-115">`%chemistry.broombridge`: Läser in och returnerar Broombridge för det elektroniska strukturs problemet från en specifik. yaml-fil.</span><span class="sxs-lookup"><span data-stu-id="fa314-115">`%chemistry.broombridge`: Loads and returns Broombridge electronic structure problem representation from a given .yaml file.</span></span>
- <span data-ttu-id="fa314-116">`%chemistry.encode`: Kodar en fermion-Hamiltonian till ett format som kan förbrukas av Q #.</span><span class="sxs-lookup"><span data-stu-id="fa314-116">`%chemistry.encode`: Encodes a fermion Hamiltonian to a format consumable by Q#.</span></span>
- <span data-ttu-id="fa314-117">`%chemistry.fh.add_terms`: Lägger till villkor till en fermion-Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="fa314-117">`%chemistry.fh.add_terms`: Adds terms to a fermion Hamiltonian.</span></span>
- <span data-ttu-id="fa314-118">`%chemistry.fh.load`: Läser in fermion-Hamiltonian för ett elektroniskt struktur problem.</span><span class="sxs-lookup"><span data-stu-id="fa314-118">`%chemistry.fh.load`: Loads the fermion Hamiltonian for an electronic structure problem.</span></span> <span data-ttu-id="fa314-119">Problemet läses in från en fil eller skickas som ett argument.</span><span class="sxs-lookup"><span data-stu-id="fa314-119">The problem is loaded from a file or passed as an argument.</span></span>
- <span data-ttu-id="fa314-120">`%chemistry.inputstate.load`: Läser in Broombridge elektroniskt struktur problem och returnerar valt indatamängds tillstånd.</span><span class="sxs-lookup"><span data-stu-id="fa314-120">`%chemistry.inputstate.load`: Loads Broombridge electronic structure problem and returns selected input state.</span></span>

### <a name="from-microsoftquantumkatas-package"></a><span data-ttu-id="fa314-121">Från Microsoft. Quantum. Katas-paket</span><span class="sxs-lookup"><span data-stu-id="fa314-121">From Microsoft.Quantum.Katas package</span></span>

- <span data-ttu-id="fa314-122">`%kata`: Kör ett enda test och rapporterar om testet lyckades.</span><span class="sxs-lookup"><span data-stu-id="fa314-122">`%kata`: Executes a single test, and reports whether the test passed successfully.</span></span>
- <span data-ttu-id="fa314-123">`%check_kata`: Kontrollerar referens implementeringen för ett enskilt Kata-test.</span><span class="sxs-lookup"><span data-stu-id="fa314-123">`%check_kata`: Checks the reference implementation for a single kata's test.</span></span>
    <span data-ttu-id="fa314-124">Mer specifikt ersätter den referens implementeringen för en enskild uppgift i cellen och rapporterar om testet lyckades.</span><span class="sxs-lookup"><span data-stu-id="fa314-124">Specifically, it substitutes the reference implementation for a single task into the cell, and reports whether the test passed successfully.</span></span>
