---
uid: Microsoft.Quantum.Synthesis.TruthTablesFromPermutationFolder
title: Funktionen TruthTablesFromPermutationFolder
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: TruthTablesFromPermutationFolder
qsharp.summary: Decomposition logic for a single variable index
ms.openlocfilehash: 6b00c9e880ed7b7b3bf446dcb17dab3bab7a83a7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733478"
---
# <a name="truthtablesfrompermutationfolder-function"></a><span data-ttu-id="e5c11-102">Funktionen TruthTablesFromPermutationFolder</span><span class="sxs-lookup"><span data-stu-id="e5c11-102">TruthTablesFromPermutationFolder function</span></span>

<span data-ttu-id="e5c11-103">Namnrymd: [Microsoft. Quantum. syntes](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="e5c11-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="e5c11-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e5c11-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e5c11-105">Diskompositions logik för ett enda variabel index</span><span class="sxs-lookup"><span data-stu-id="e5c11-105">Decomposition logic for a single variable index</span></span>

```qsharp
function TruthTablesFromPermutationFolder (numVars : Int, state : Microsoft.Quantum.Synthesis.DecompositionState, index : Int) : Microsoft.Quantum.Synthesis.DecompositionState
```


## <a name="description"></a><span data-ttu-id="e5c11-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="e5c11-106">Description</span></span>

<span data-ttu-id="e5c11-107">Detta tar det aktuella läget och genererar en uppdaterad permutation och eventuellt lägger till nya funktioner för kontrollerade portar.</span><span class="sxs-lookup"><span data-stu-id="e5c11-107">This takes the current state and generates an updated permutation and possibly adds new functions for controlled gates.</span></span>

## <a name="input"></a><span data-ttu-id="e5c11-108">Indata</span><span class="sxs-lookup"><span data-stu-id="e5c11-108">Input</span></span>

### <a name="numvars--int"></a><span data-ttu-id="e5c11-109">numVars: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e5c11-109">numVars : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="state--decompositionstate"></a><span data-ttu-id="e5c11-110">tillstånd: [DecompositionState](xref:Microsoft.Quantum.Synthesis.DecompositionState)</span><span class="sxs-lookup"><span data-stu-id="e5c11-110">state : [DecompositionState](xref:Microsoft.Quantum.Synthesis.DecompositionState)</span></span>




### <a name="index--int"></a><span data-ttu-id="e5c11-111">index: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e5c11-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--decompositionstate"></a><span data-ttu-id="e5c11-112">Utdata: [DecompositionState](xref:Microsoft.Quantum.Synthesis.DecompositionState)</span><span class="sxs-lookup"><span data-stu-id="e5c11-112">Output : [DecompositionState](xref:Microsoft.Quantum.Synthesis.DecompositionState)</span></span>

