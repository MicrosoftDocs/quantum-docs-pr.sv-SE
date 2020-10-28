---
uid: Microsoft.Quantum.Simulation._IdentityTimeDependentGeneratorSystem
title: _IdentityTimeDependentGeneratorSystem funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: _IdentityTimeDependentGeneratorSystem
qsharp.summary: Returns a generator system consistent with the Hamiltonian `H(s) = 0`, where `s` is a schedule parameter.
ms.openlocfilehash: 0b440ce9adaab562e16b02da46844c68a7470b11
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726352"
---
# <a name="_identitytimedependentgeneratorsystem-function"></a><span data-ttu-id="a8349-102">_IdentityTimeDependentGeneratorSystem funktion</span><span class="sxs-lookup"><span data-stu-id="a8349-102">_IdentityTimeDependentGeneratorSystem function</span></span>

<span data-ttu-id="a8349-103">Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="a8349-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="a8349-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a8349-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a8349-105">Returnerar ett generatorsystem som är konsekvent med Hamiltonian `H(s) = 0` , där `s` är en schema parameter.</span><span class="sxs-lookup"><span data-stu-id="a8349-105">Returns a generator system consistent with the Hamiltonian `H(s) = 0`, where `s` is a schedule parameter.</span></span>

```qsharp
function _IdentityTimeDependentGeneratorSystem (schedule : Double) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="a8349-106">Indata</span><span class="sxs-lookup"><span data-stu-id="a8349-106">Input</span></span>

### <a name="schedule--double"></a><span data-ttu-id="a8349-107">schema: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a8349-107">schedule : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a8349-108">Den här indatan ignoreras och definieras för konsekvens med den <xref:microsoft.quantum.canon.timedependentgeneratorsystem> användardefinierade typen.</span><span class="sxs-lookup"><span data-stu-id="a8349-108">This input is ignored, and is defined for consistency with the <xref:microsoft.quantum.canon.timedependentgeneratorsystem> user-defined type.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="a8349-109">Utdata: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="a8349-109">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="a8349-110">Ett generatorsystem som representerar utvecklingen under Hamiltonian-$H (s) = $0 för alla $s $.</span><span class="sxs-lookup"><span data-stu-id="a8349-110">A generator system representing evolution under the Hamiltonian $H(s) = 0$ for all $s$.</span></span>