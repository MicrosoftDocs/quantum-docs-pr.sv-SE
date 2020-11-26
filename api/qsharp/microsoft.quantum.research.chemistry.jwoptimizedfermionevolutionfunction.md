---
uid: Microsoft.Quantum.Research.Chemistry.JWOptimizedFermionEvolutionFunction
title: Funktionen JWOptimizedFermionEvolutionFunction
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: JWOptimizedFermionEvolutionFunction
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the JWOptimized basis.
ms.openlocfilehash: 40a4bccc6cf74a63c354bfd628baa45768916fe2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229927"
---
# <a name="jwoptimizedfermionevolutionfunction-function"></a><span data-ttu-id="b4e61-102">Funktionen JWOptimizedFermionEvolutionFunction</span><span class="sxs-lookup"><span data-stu-id="b4e61-102">JWOptimizedFermionEvolutionFunction function</span></span>

<span data-ttu-id="b4e61-103">Namnrymd: [Microsoft. Quantum. Research. kemi](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="b4e61-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="b4e61-104">Paket: [Microsoft. Quantum. Research. kemi](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="b4e61-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="b4e61-105">Representerar en dynamisk generator som en uppsättning simulerade grindar och en expansion i JWOptimized-basen.</span><span class="sxs-lookup"><span data-stu-id="b4e61-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the JWOptimized basis.</span></span>

```qsharp
function JWOptimizedFermionEvolutionFunction (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex, parityQubit : Qubit) : Microsoft.Quantum.Simulation.EvolutionUnitary
```


## <a name="input"></a><span data-ttu-id="b4e61-106">Indata</span><span class="sxs-lookup"><span data-stu-id="b4e61-106">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="b4e61-107">generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="b4e61-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="b4e61-108">Ett Generator index som återges som en enhetlig utveckling i JWOptimized-basen.</span><span class="sxs-lookup"><span data-stu-id="b4e61-108">A generator index to be represented as unitary evolution in the JWOptimized basis.</span></span>


### <a name="parityqubit--qubit"></a><span data-ttu-id="b4e61-109">parityQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="b4e61-109">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="b4e61-110">Qubit som avgör tids utvecklingen.</span><span class="sxs-lookup"><span data-stu-id="b4e61-110">Qubit that determines the sign of time-evolution.</span></span>



## <a name="output--evolutionunitary"></a><span data-ttu-id="b4e61-111">Utdata: [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)</span><span class="sxs-lookup"><span data-stu-id="b4e61-111">Output : [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)</span></span>

<span data-ttu-id="b4e61-112">En `EvolutionUnitary` som visar tids utveckling enligt termen som refereras i generatorIndex.</span><span class="sxs-lookup"><span data-stu-id="b4e61-112">An `EvolutionUnitary` representing time-evolution by the term referenced in \`generatorIndex.</span></span>