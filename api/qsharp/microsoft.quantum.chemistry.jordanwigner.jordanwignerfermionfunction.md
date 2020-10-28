---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerFermionFunction
title: Funktionen JordanWignerFermionFunction
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerFermionFunction
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.
ms.openlocfilehash: 7d29393293acfc1748a1805f339951b1ff0f9b10
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727783"
---
# <a name="jordanwignerfermionfunction-function"></a><span data-ttu-id="f7088-102">Funktionen JordanWignerFermionFunction</span><span class="sxs-lookup"><span data-stu-id="f7088-102">JordanWignerFermionFunction function</span></span>

<span data-ttu-id="f7088-103">Namnrymd: [Microsoft. Quantum. kemi. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="f7088-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="f7088-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f7088-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f7088-105">Representerar en dynamisk generator som en uppsättning simulerade grindar och en expansion i JordanWigner-basen.</span><span class="sxs-lookup"><span data-stu-id="f7088-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.</span></span>

```qsharp
function JordanWignerFermionFunction (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.EvolutionUnitary
```


## <a name="input"></a><span data-ttu-id="f7088-106">Indata</span><span class="sxs-lookup"><span data-stu-id="f7088-106">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="f7088-107">generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="f7088-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="f7088-108">Ett Generator index som återges som en enhetlig utveckling i JordanWigner.</span><span class="sxs-lookup"><span data-stu-id="f7088-108">A generator index to be represented as unitary evolution in the JordanWigner.</span></span>



## <a name="output--evolutionunitary"></a><span data-ttu-id="f7088-109">Utdata: [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)</span><span class="sxs-lookup"><span data-stu-id="f7088-109">Output : [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)</span></span>

<span data-ttu-id="f7088-110">En `EvolutionUnitary` som visar tids utveckling enligt termen som refereras i generatorIndex.</span><span class="sxs-lookup"><span data-stu-id="f7088-110">An `EvolutionUnitary` representing time-evolution by the term referenced in \`generatorIndex.</span></span>