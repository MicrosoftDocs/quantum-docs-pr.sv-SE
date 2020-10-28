---
uid: Microsoft.Quantum.Research.Chemistry.JWOptimizedFermionEvolutionFunction
title: Funktionen JWOptimizedFermionEvolutionFunction
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: JWOptimizedFermionEvolutionFunction
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the JWOptimized basis.
ms.openlocfilehash: 952f3dc4ab0595ace0ee34c040cb21969afa111f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726400"
---
# <a name="jwoptimizedfermionevolutionfunction-function"></a><span data-ttu-id="95dfe-102">Funktionen JWOptimizedFermionEvolutionFunction</span><span class="sxs-lookup"><span data-stu-id="95dfe-102">JWOptimizedFermionEvolutionFunction function</span></span>

<span data-ttu-id="95dfe-103">Namnrymd: [Microsoft. Quantum. Research. kemi](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="95dfe-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="95dfe-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="95dfe-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="95dfe-105">Representerar en dynamisk generator som en uppsättning simulerade grindar och en expansion i JWOptimized-basen.</span><span class="sxs-lookup"><span data-stu-id="95dfe-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the JWOptimized basis.</span></span>

```qsharp
function JWOptimizedFermionEvolutionFunction (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex, parityQubit : Qubit) : Microsoft.Quantum.Simulation.EvolutionUnitary
```


## <a name="input"></a><span data-ttu-id="95dfe-106">Indata</span><span class="sxs-lookup"><span data-stu-id="95dfe-106">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="95dfe-107">generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="95dfe-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="95dfe-108">Ett Generator index som återges som en enhetlig utveckling i JWOptimized-basen.</span><span class="sxs-lookup"><span data-stu-id="95dfe-108">A generator index to be represented as unitary evolution in the JWOptimized basis.</span></span>


### <a name="parityqubit--qubit"></a><span data-ttu-id="95dfe-109">parityQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="95dfe-109">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="95dfe-110">Qubit som avgör tids utvecklingen.</span><span class="sxs-lookup"><span data-stu-id="95dfe-110">Qubit that determines the sign of time-evolution.</span></span>



## <a name="output--evolutionunitary"></a><span data-ttu-id="95dfe-111">Utdata: [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)</span><span class="sxs-lookup"><span data-stu-id="95dfe-111">Output : [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)</span></span>

<span data-ttu-id="95dfe-112">En `EvolutionUnitary` som visar tids utveckling enligt termen som refereras i generatorIndex.</span><span class="sxs-lookup"><span data-stu-id="95dfe-112">An `EvolutionUnitary` representing time-evolution by the term referenced in \`generatorIndex.</span></span>