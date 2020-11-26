---
uid: Microsoft.Quantum.Simulation.EvolutionSet
title: EvolutionSet-användardefinierad typ
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionSet
qsharp.summary: >-
  Represents a set of gates that can be readily implemented and used to implement simulation algorithms.

  Elements in the set are indexed by a  <xref:microsoft.quantum.simulation.generatorindex>, and each set is described by a function from `GeneratorIndex` to  <xref:microsoft.quantum.simulation.evolutionunitary>, which are operations parameterized by a real number representing time
ms.openlocfilehash: ee8f3c0716f035dcb0c4fad557092fbf8dd3c356
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229417"
---
# <a name="evolutionset-user-defined-type"></a><span data-ttu-id="5fd9e-102">EvolutionSet-användardefinierad typ</span><span class="sxs-lookup"><span data-stu-id="5fd9e-102">EvolutionSet user defined type</span></span>

<span data-ttu-id="5fd9e-103">Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="5fd9e-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="5fd9e-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5fd9e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5fd9e-105">Representerar en uppsättning portar som kan implementeras snabbt och användas för att implementera simulerings algoritmer.</span><span class="sxs-lookup"><span data-stu-id="5fd9e-105">Represents a set of gates that can be readily implemented and used to implement simulation algorithms.</span></span>

<span data-ttu-id="5fd9e-106">Element i uppsättningen indexeras av en  <xref:microsoft.quantum.simulation.generatorindex> , och varje uppsättning beskrivs av en funktion från `GeneratorIndex` till  <xref:microsoft.quantum.simulation.evolutionunitary> , vilket är åtgärder som parameteras av ett reellt tal som representerar tid</span><span class="sxs-lookup"><span data-stu-id="5fd9e-106">Elements in the set are indexed by a  <xref:microsoft.quantum.simulation.generatorindex>, and each set is described by a function from `GeneratorIndex` to  <xref:microsoft.quantum.simulation.evolutionunitary>, which are operations parameterized by a real number representing time</span></span>

```qsharp

newtype EvolutionSet = ((Microsoft.Quantum.Simulation.GeneratorIndex -> Microsoft.Quantum.Simulation.EvolutionUnitary));
```

