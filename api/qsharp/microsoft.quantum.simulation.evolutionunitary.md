---
uid: Microsoft.Quantum.Simulation.EvolutionUnitary
title: EvolutionUnitary-användardefinierad typ
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionUnitary
qsharp.summary: >-
  Represents a unitary time-evolution operator.

  The first parameter is is duration of time-evolution, and the second parameter is the qubit register acted upon by the unitary.
ms.openlocfilehash: 38e7da28d4146df9cc132ad69ee939c44bc917f7
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225269"
---
# <a name="evolutionunitary-user-defined-type"></a><span data-ttu-id="6777f-102">EvolutionUnitary-användardefinierad typ</span><span class="sxs-lookup"><span data-stu-id="6777f-102">EvolutionUnitary user defined type</span></span>

<span data-ttu-id="6777f-103">Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="6777f-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="6777f-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6777f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6777f-105">Representerar en enhetlig tids utvecklings operatör.</span><span class="sxs-lookup"><span data-stu-id="6777f-105">Represents a unitary time-evolution operator.</span></span>

<span data-ttu-id="6777f-106">Den första parametern är varaktigheten för tids utvecklingen och den andra parametern är qubit-registret som har åtgärd ATS av den enhetliga.</span><span class="sxs-lookup"><span data-stu-id="6777f-106">The first parameter is is duration of time-evolution, and the second parameter is the qubit register acted upon by the unitary.</span></span>

```qsharp

newtype EvolutionUnitary = (((Double, Qubit[]) => Unit is Adj + Ctl));
```

