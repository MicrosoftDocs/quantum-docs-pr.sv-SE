---
uid: Microsoft.Quantum.Simulation.EvolutionSet
title: EvolutionSet-användardefinierad typ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionSet
qsharp.summary: >-
  Represents a set of gates that can be readily implemented and used to implement simulation algorithms.

  Elements in the set are indexed by a  <xref:microsoft.quantum.simulation.generatorindex>, and each set is described by a function from `GeneratorIndex` to  <xref:microsoft.quantum.simulation.evolutionunitary>, which are operations parameterized by a real number representing time
ms.openlocfilehash: 41504837b281b1021a2d09ef75acc10315b4fd07
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726319"
---
# <a name="evolutionset-user-defined-type"></a><span data-ttu-id="411ac-102">EvolutionSet-användardefinierad typ</span><span class="sxs-lookup"><span data-stu-id="411ac-102">EvolutionSet user defined type</span></span>

<span data-ttu-id="411ac-103">Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="411ac-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="411ac-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="411ac-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="411ac-105">Representerar en uppsättning portar som kan implementeras snabbt och användas för att implementera simulerings algoritmer.</span><span class="sxs-lookup"><span data-stu-id="411ac-105">Represents a set of gates that can be readily implemented and used to implement simulation algorithms.</span></span>

<span data-ttu-id="411ac-106">Element i uppsättningen indexeras av en  <xref:microsoft.quantum.simulation.generatorindex> , och varje uppsättning beskrivs av en funktion från `GeneratorIndex` till  <xref:microsoft.quantum.simulation.evolutionunitary> , vilket är åtgärder som parameteras av ett reellt tal som representerar tid</span><span class="sxs-lookup"><span data-stu-id="411ac-106">Elements in the set are indexed by a  <xref:microsoft.quantum.simulation.generatorindex>, and each set is described by a function from `GeneratorIndex` to  <xref:microsoft.quantum.simulation.evolutionunitary>, which are operations parameterized by a real number representing time</span></span>

```qsharp

newtype EvolutionSet = ((Microsoft.Quantum.Simulation.GeneratorIndex -> Microsoft.Quantum.Simulation.EvolutionUnitary));
```

