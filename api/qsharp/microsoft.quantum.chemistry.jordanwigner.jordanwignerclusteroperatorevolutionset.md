---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerClusterOperatorEvolutionSet
title: Funktionen JordanWignerClusterOperatorEvolutionSet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerClusterOperatorEvolutionSet
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.
ms.openlocfilehash: 81a2a109be0b19da5aa0a3feca76966deabeb665
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727804"
---
# <a name="jordanwignerclusteroperatorevolutionset-function"></a><span data-ttu-id="d3fdc-102">Funktionen JordanWignerClusterOperatorEvolutionSet</span><span class="sxs-lookup"><span data-stu-id="d3fdc-102">JordanWignerClusterOperatorEvolutionSet function</span></span>

<span data-ttu-id="d3fdc-103">Namnrymd: [Microsoft. Quantum. kemi. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="d3fdc-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="d3fdc-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d3fdc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d3fdc-105">Representerar en dynamisk generator som en uppsättning simulerade grindar och en expansion i JordanWigner-basen.</span><span class="sxs-lookup"><span data-stu-id="d3fdc-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.</span></span>

```qsharp
function JordanWignerClusterOperatorEvolutionSet () : Microsoft.Quantum.Simulation.EvolutionSet
```


## <a name="output--evolutionset"></a><span data-ttu-id="d3fdc-106">Utdata: [EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)</span><span class="sxs-lookup"><span data-stu-id="d3fdc-106">Output : [EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)</span></span>

<span data-ttu-id="d3fdc-107">En `EvolutionSet` som mappar en `GeneratorIndex` för JordanWigner-basen till en EvolutionUnitary.</span><span class="sxs-lookup"><span data-stu-id="d3fdc-107">An `EvolutionSet` that maps a `GeneratorIndex` for the JordanWigner basis to an \`EvolutionUnitary.</span></span>