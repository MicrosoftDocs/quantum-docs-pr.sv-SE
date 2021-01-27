---
uid: Microsoft.Quantum.Simulation._IdentityTimeDependentGeneratorSystem
title: _IdentityTimeDependentGeneratorSystem funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: _IdentityTimeDependentGeneratorSystem
qsharp.summary: Returns a generator system consistent with the Hamiltonian `H(s) = 0`, where `s` is a schedule parameter.
ms.openlocfilehash: 960842f50353c01362f90eb38d979fb7c4f15d9a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857991"
---
# <a name="_identitytimedependentgeneratorsystem-function"></a><span data-ttu-id="19b7e-102">_IdentityTimeDependentGeneratorSystem funktion</span><span class="sxs-lookup"><span data-stu-id="19b7e-102">_IdentityTimeDependentGeneratorSystem function</span></span>

<span data-ttu-id="19b7e-103">Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="19b7e-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="19b7e-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="19b7e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="19b7e-105">Returnerar ett generatorsystem som är konsekvent med Hamiltonian `H(s) = 0` , där `s` är en schema parameter.</span><span class="sxs-lookup"><span data-stu-id="19b7e-105">Returns a generator system consistent with the Hamiltonian `H(s) = 0`, where `s` is a schedule parameter.</span></span>

```qsharp
function _IdentityTimeDependentGeneratorSystem (schedule : Double) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="19b7e-106">Indata</span><span class="sxs-lookup"><span data-stu-id="19b7e-106">Input</span></span>

### <a name="schedule--double"></a><span data-ttu-id="19b7e-107">schema: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="19b7e-107">schedule : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="19b7e-108">Den här indatan ignoreras och definieras för konsekvens med den <xref:microsoft.quantum.canon.timedependentgeneratorsystem> användardefinierade typen.</span><span class="sxs-lookup"><span data-stu-id="19b7e-108">This input is ignored, and is defined for consistency with the <xref:microsoft.quantum.canon.timedependentgeneratorsystem> user-defined type.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="19b7e-109">Utdata: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="19b7e-109">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="19b7e-110">Ett generatorsystem som representerar utvecklingen under Hamiltonian-$H (s) = $0 för alla $s $.</span><span class="sxs-lookup"><span data-stu-id="19b7e-110">A generator system representing evolution under the Hamiltonian $H(s) = 0$ for all $s$.</span></span>