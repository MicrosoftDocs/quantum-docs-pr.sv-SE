---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsCA
title: ApplySeriesOfOpsCA-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsCA
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Adjoint + Controlled)
ms.openlocfilehash: 9dd1343b3ebcc75592441f150eee822cfe83f9a1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217891"
---
# <a name="applyseriesofopsca-operation"></a><span data-ttu-id="9a721-102">ApplySeriesOfOpsCA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="9a721-102">ApplySeriesOfOpsCA operation</span></span>

<span data-ttu-id="9a721-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9a721-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9a721-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9a721-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9a721-105">Använder en lista med OPS och deras mål sekventiellt i en matris.</span><span class="sxs-lookup"><span data-stu-id="9a721-105">Applies a list of ops and their targets sequentially on an array.</span></span> <span data-ttu-id="9a721-106">(Angränsande + styrd)</span><span class="sxs-lookup"><span data-stu-id="9a721-106">(Adjoint + Controlled)</span></span>

```qsharp
operation ApplySeriesOfOpsCA<'T> (listOfOps : ('T[] => Unit is Adj + Ctl)[], targets : Int[][], register : 'T[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="9a721-107">Indata</span><span class="sxs-lookup"><span data-stu-id="9a721-107">Input</span></span>

### <a name="listofops--t--unit--is-adj--ctl"></a><span data-ttu-id="9a721-108">listOfOps: ' t [] => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL []</span><span class="sxs-lookup"><span data-stu-id="9a721-108">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl[]</span></span>

<span data-ttu-id="9a721-109">En lista med OPS, vart och ett som tar en matris som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="9a721-109">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="9a721-110">De tillämpas sekventiellt, lägsta index först.</span><span class="sxs-lookup"><span data-stu-id="9a721-110">They are applied sequentially, lowest index first.</span></span>
<span data-ttu-id="9a721-111">Varje måste ha både ett överfunctort och kontrollerat.</span><span class="sxs-lookup"><span data-stu-id="9a721-111">Each must have both an Adjoint and Controlled functor.</span></span>


### <a name="targets--int"></a><span data-ttu-id="9a721-112">mål: [int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="9a721-112">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="9a721-113">Kapslade matriser som beskriver målen för op.</span><span class="sxs-lookup"><span data-stu-id="9a721-113">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="9a721-114">Varje matris ska innehålla en lista över InTS som beskriver de index som ska användas.</span><span class="sxs-lookup"><span data-stu-id="9a721-114">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="9a721-115">Registrera: ' ' []</span><span class="sxs-lookup"><span data-stu-id="9a721-115">register : 'T[]</span></span>

<span data-ttu-id="9a721-116">Qubit-register att du ska handla på.</span><span class="sxs-lookup"><span data-stu-id="9a721-116">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9a721-117">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9a721-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="9a721-118">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="9a721-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9a721-119">Inte</span><span class="sxs-lookup"><span data-stu-id="9a721-119">'T</span></span>



## <a name="see-also"></a><span data-ttu-id="9a721-120">Se även</span><span class="sxs-lookup"><span data-stu-id="9a721-120">See Also</span></span>

- [<span data-ttu-id="9a721-121">Microsoft. Quantum. Canon. ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="9a721-121">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)