---
uid: Microsoft.Quantum.Simulation.EvolutionUnitary
title: EvolutionUnitary-användardefinierad typ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionUnitary
qsharp.summary: >-
  Represents a unitary time-evolution operator.

  The first parameter is is duration of time-evolution, and the second parameter is the qubit register acted upon by the unitary.
ms.openlocfilehash: 28ab492573b67e4aa42392e4ee499596b9c0225f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733707"
---
# <a name="evolutionunitary-user-defined-type"></a><span data-ttu-id="58f9c-102">EvolutionUnitary-användardefinierad typ</span><span class="sxs-lookup"><span data-stu-id="58f9c-102">EvolutionUnitary user defined type</span></span>

<span data-ttu-id="58f9c-103">Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="58f9c-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="58f9c-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="58f9c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="58f9c-105">Representerar en enhetlig tids utvecklings operatör.</span><span class="sxs-lookup"><span data-stu-id="58f9c-105">Represents a unitary time-evolution operator.</span></span>

<span data-ttu-id="58f9c-106">Den första parametern är varaktigheten för tids utvecklingen och den andra parametern är qubit-registret som har åtgärd ATS av den enhetliga.</span><span class="sxs-lookup"><span data-stu-id="58f9c-106">The first parameter is is duration of time-evolution, and the second parameter is the qubit register acted upon by the unitary.</span></span>

```qsharp

newtype EvolutionUnitary = (((Double, Qubit[]) => Unit is Adj + Ctl));
```
