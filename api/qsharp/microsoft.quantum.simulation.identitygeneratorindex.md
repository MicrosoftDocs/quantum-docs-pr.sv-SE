---
uid: Microsoft.Quantum.Simulation.IdentityGeneratorIndex
title: Funktionen IdentityGeneratorIndex
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IdentityGeneratorIndex
qsharp.summary: Returns a generator index consistent with the zero Hamiltonian, `H = 0`, which corresponds to the identity evolution operation.
ms.openlocfilehash: d2af2dafaf75a68546cb3f16c04cf4c7ee50c6ff
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733526"
---
# <a name="identitygeneratorindex-function"></a><span data-ttu-id="d3786-102">Funktionen IdentityGeneratorIndex</span><span class="sxs-lookup"><span data-stu-id="d3786-102">IdentityGeneratorIndex function</span></span>

<span data-ttu-id="d3786-103">Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="d3786-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="d3786-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d3786-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d3786-105">Returnerar ett Generator index som är konsekvent med noll-Hamiltonian, `H = 0` som motsvarar Identity Evolutionary-åtgärden.</span><span class="sxs-lookup"><span data-stu-id="d3786-105">Returns a generator index consistent with the zero Hamiltonian, `H = 0`, which corresponds to the identity evolution operation.</span></span>

```qsharp
function IdentityGeneratorIndex (idxTerm : Int) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="d3786-106">Indata</span><span class="sxs-lookup"><span data-stu-id="d3786-106">Input</span></span>

### <a name="idxterm--int"></a><span data-ttu-id="d3786-107">idxTerm: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d3786-107">idxTerm : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d3786-108">Den här indatan ignoreras och definieras för konsekvens med den <xref:microsoft.quantum.simulation.generatorsystem> användardefinierade typen.</span><span class="sxs-lookup"><span data-stu-id="d3786-108">This input is ignored, and is defined for consistency with the <xref:microsoft.quantum.simulation.generatorsystem> user-defined type.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="d3786-109">Utdata: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="d3786-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="d3786-110">Ett Generator index som representerar utvecklingen under Hamiltonian-$H = $0.</span><span class="sxs-lookup"><span data-stu-id="d3786-110">A generator index representing evolution under the Hamiltonian $H = 0$.</span></span>