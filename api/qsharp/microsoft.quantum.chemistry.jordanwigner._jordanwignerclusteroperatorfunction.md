---
uid: Microsoft.Quantum.Chemistry.JordanWigner._JordanWignerClusterOperatorFunction
title: _JordanWignerClusterOperatorFunction funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _JordanWignerClusterOperatorFunction
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.
ms.openlocfilehash: 58b0c7ad2216b1f58b9ea2765494b85fab4e1ff9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728053"
---
# <a name="_jordanwignerclusteroperatorfunction-function"></a><span data-ttu-id="246fd-102">_JordanWignerClusterOperatorFunction funktion</span><span class="sxs-lookup"><span data-stu-id="246fd-102">_JordanWignerClusterOperatorFunction function</span></span>

<span data-ttu-id="246fd-103">Namnrymd: [Microsoft. Quantum. kemi. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="246fd-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="246fd-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="246fd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="246fd-105">Representerar en dynamisk generator som en uppsättning simulerade grindar och en expansion i JordanWigner-basen.</span><span class="sxs-lookup"><span data-stu-id="246fd-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.</span></span>

```qsharp
function _JordanWignerClusterOperatorFunction (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.EvolutionUnitary
```


## <a name="input"></a><span data-ttu-id="246fd-106">Indata</span><span class="sxs-lookup"><span data-stu-id="246fd-106">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="246fd-107">generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="246fd-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="246fd-108">Ett Generator index som återges som en enhetlig utveckling i JordanWigner.</span><span class="sxs-lookup"><span data-stu-id="246fd-108">A generator index to be represented as unitary evolution in the JordanWigner.</span></span>



## <a name="output--evolutionunitary"></a><span data-ttu-id="246fd-109">Utdata: [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)</span><span class="sxs-lookup"><span data-stu-id="246fd-109">Output : [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)</span></span>

<span data-ttu-id="246fd-110">En `EvolutionUnitary` som visar tids utveckling enligt termen som refereras i generatorIndex.</span><span class="sxs-lookup"><span data-stu-id="246fd-110">An `EvolutionUnitary` representing time-evolution by the term referenced in \`generatorIndex.</span></span>