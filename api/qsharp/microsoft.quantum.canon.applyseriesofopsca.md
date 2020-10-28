---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsCA
title: ApplySeriesOfOpsCA-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsCA
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Adjoint + Controlled)
ms.openlocfilehash: 2327a693e528cf46f95eae5ee052e9dd9b6ee187
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729328"
---
# <a name="applyseriesofopsca-operation"></a><span data-ttu-id="7e3e4-102">ApplySeriesOfOpsCA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="7e3e4-102">ApplySeriesOfOpsCA operation</span></span>

<span data-ttu-id="7e3e4-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7e3e4-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7e3e4-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7e3e4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7e3e4-105">Använder en lista med OPS och deras mål sekventiellt i en matris.</span><span class="sxs-lookup"><span data-stu-id="7e3e4-105">Applies a list of ops and their targets sequentially on an array.</span></span> <span data-ttu-id="7e3e4-106">(Angränsande + styrd)</span><span class="sxs-lookup"><span data-stu-id="7e3e4-106">(Adjoint + Controlled)</span></span>

```qsharp
operation ApplySeriesOfOpsCA<'T> (listOfOps : ('T[] => Unit is Adj + Ctl)[], targets : Int[][], register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="7e3e4-107">Indata</span><span class="sxs-lookup"><span data-stu-id="7e3e4-107">Input</span></span>

### <a name="listofops--t--unit-adj--ctl"></a><span data-ttu-id="7e3e4-108">listOfOps: ' t [] => [enhets](xref:microsoft.quantum.lang-ref.unit) justering + CTL []</span><span class="sxs-lookup"><span data-stu-id="7e3e4-108">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl[]</span></span>

<span data-ttu-id="7e3e4-109">En lista med OPS, vart och ett som tar en matris som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="7e3e4-109">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="7e3e4-110">De tillämpas sekventiellt, lägsta index först.</span><span class="sxs-lookup"><span data-stu-id="7e3e4-110">They are applied sequentially, lowest index first.</span></span>
<span data-ttu-id="7e3e4-111">Varje måste ha både ett överfunctort och kontrollerat.</span><span class="sxs-lookup"><span data-stu-id="7e3e4-111">Each must have both an Adjoint and Controlled functor.</span></span>


### <a name="targets--int"></a><span data-ttu-id="7e3e4-112">mål: [int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="7e3e4-112">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="7e3e4-113">Kapslade matriser som beskriver målen för op.</span><span class="sxs-lookup"><span data-stu-id="7e3e4-113">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="7e3e4-114">Varje matris ska innehålla en lista över InTS som beskriver de index som ska användas.</span><span class="sxs-lookup"><span data-stu-id="7e3e4-114">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="7e3e4-115">Registrera: ' ' []</span><span class="sxs-lookup"><span data-stu-id="7e3e4-115">register : 'T[]</span></span>

<span data-ttu-id="7e3e4-116">Qubit-register att du ska handla på.</span><span class="sxs-lookup"><span data-stu-id="7e3e4-116">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7e3e4-117">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7e3e4-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="7e3e4-118">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="7e3e4-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7e3e4-119">Inte</span><span class="sxs-lookup"><span data-stu-id="7e3e4-119">'T</span></span>



## <a name="see-also"></a><span data-ttu-id="7e3e4-120">Se även</span><span class="sxs-lookup"><span data-stu-id="7e3e4-120">See Also</span></span>

- [<span data-ttu-id="7e3e4-121">Microsoft. Quantum. Canon. ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="7e3e4-121">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)