---
uid: Microsoft.Quantum.Simulation.EvolutionSet
title: EvolutionSet-användardefinierad typ
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionSet
qsharp.summary: >-
  Represents a set of gates that can be readily implemented and used to implement simulation algorithms.

  Elements in the set are indexed by a  <xref:microsoft.quantum.simulation.generatorindex>, and each set is described by a function from `GeneratorIndex` to  <xref:microsoft.quantum.simulation.evolutionunitary>, which are operations parameterized by a real number representing time
ms.openlocfilehash: 35c0b24da284a5871fd11b6d624102b853b89d19
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856060"
---
# <a name="evolutionset-user-defined-type"></a><span data-ttu-id="6f145-102">EvolutionSet-användardefinierad typ</span><span class="sxs-lookup"><span data-stu-id="6f145-102">EvolutionSet user defined type</span></span>

<span data-ttu-id="6f145-103">Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="6f145-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="6f145-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6f145-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6f145-105">Representerar en uppsättning portar som kan implementeras snabbt och användas för att implementera simulerings algoritmer.</span><span class="sxs-lookup"><span data-stu-id="6f145-105">Represents a set of gates that can be readily implemented and used to implement simulation algorithms.</span></span>

<span data-ttu-id="6f145-106">Element i uppsättningen indexeras av en  <xref:microsoft.quantum.simulation.generatorindex> , och varje uppsättning beskrivs av en funktion från `GeneratorIndex` till  <xref:microsoft.quantum.simulation.evolutionunitary> , vilket är åtgärder som parameteras av ett reellt tal som representerar tid</span><span class="sxs-lookup"><span data-stu-id="6f145-106">Elements in the set are indexed by a  <xref:microsoft.quantum.simulation.generatorindex>, and each set is described by a function from `GeneratorIndex` to  <xref:microsoft.quantum.simulation.evolutionunitary>, which are operations parameterized by a real number representing time</span></span>

```qsharp

newtype EvolutionSet = ((Microsoft.Quantum.Simulation.GeneratorIndex -> Microsoft.Quantum.Simulation.EvolutionUnitary));
```

