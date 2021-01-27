---
uid: Microsoft.Quantum.Research.Chemistry.JordanWignerOptimizedFermionEvolutionSet
title: Funktionen JordanWignerOptimizedFermionEvolutionSet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: JordanWignerOptimizedFermionEvolutionSet
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.
ms.openlocfilehash: 941d66a936ef1a2ac76230d14ca8437ac2a4a049
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857886"
---
# <a name="jordanwigneroptimizedfermionevolutionset-function"></a><span data-ttu-id="302bd-102">Funktionen JordanWignerOptimizedFermionEvolutionSet</span><span class="sxs-lookup"><span data-stu-id="302bd-102">JordanWignerOptimizedFermionEvolutionSet function</span></span>

<span data-ttu-id="302bd-103">Namnrymd: [Microsoft. Quantum. Research. kemi](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="302bd-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="302bd-104">Paket: [Microsoft. Quantum. Research. kemi](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="302bd-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="302bd-105">Representerar en dynamisk generator som en uppsättning simulerade grindar och en expansion i Pauli-basen.</span><span class="sxs-lookup"><span data-stu-id="302bd-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.</span></span>

```qsharp
function JordanWignerOptimizedFermionEvolutionSet (parityQubit : Qubit) : Microsoft.Quantum.Simulation.EvolutionSet
```


## <a name="input"></a><span data-ttu-id="302bd-106">Indata</span><span class="sxs-lookup"><span data-stu-id="302bd-106">Input</span></span>

### <a name="parityqubit--qubit"></a><span data-ttu-id="302bd-107">parityQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="302bd-107">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="302bd-108">Qubit som avgör tids utvecklingen.</span><span class="sxs-lookup"><span data-stu-id="302bd-108">Qubit that determines the sign of time-evolution.</span></span>



## <a name="output--evolutionset"></a><span data-ttu-id="302bd-109">Utdata: [EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)</span><span class="sxs-lookup"><span data-stu-id="302bd-109">Output : [EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)</span></span>

<span data-ttu-id="302bd-110">En `EvolutionSet` som mappar en `GeneratorIndex` för JWOptimized-basen till en EvolutionUnitary.</span><span class="sxs-lookup"><span data-stu-id="302bd-110">An `EvolutionSet` that maps a `GeneratorIndex` for the JWOptimized basis to an \`EvolutionUnitary.</span></span>