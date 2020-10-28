---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsA
title: ApplySeriesOfOpsA-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsA
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Adjoint)
ms.openlocfilehash: e2b928fa4c9446e16d2bf5e7b68a32d4bba3a528
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729337"
---
# <a name="applyseriesofopsa-operation"></a><span data-ttu-id="b5453-102">ApplySeriesOfOpsA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="b5453-102">ApplySeriesOfOpsA operation</span></span>

<span data-ttu-id="b5453-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b5453-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b5453-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b5453-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b5453-105">Använder en lista med OPS och deras mål sekventiellt i en matris.</span><span class="sxs-lookup"><span data-stu-id="b5453-105">Applies a list of ops and their targets sequentially on an array.</span></span> <span data-ttu-id="b5453-106">(Angränsande)</span><span class="sxs-lookup"><span data-stu-id="b5453-106">(Adjoint)</span></span>

```qsharp
operation ApplySeriesOfOpsA<'T> (listOfOps : ('T[] => Unit is Adj)[], targets : Int[][], register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="b5453-107">Indata</span><span class="sxs-lookup"><span data-stu-id="b5453-107">Input</span></span>

### <a name="listofops--t--unit-adj"></a><span data-ttu-id="b5453-108">listOfOps: ' t [] => [enhets](xref:microsoft.quantum.lang-ref.unit) justering []</span><span class="sxs-lookup"><span data-stu-id="b5453-108">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj[]</span></span>

<span data-ttu-id="b5453-109">En lista med OPS, vart och ett som tar en matris som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="b5453-109">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="b5453-110">De tillämpas sekventiellt, lägsta index först.</span><span class="sxs-lookup"><span data-stu-id="b5453-110">They are applied sequentially, lowest index first.</span></span>
<span data-ttu-id="b5453-111">Varje måste ha ett angränsande Functor</span><span class="sxs-lookup"><span data-stu-id="b5453-111">Each must have an adjoint functor</span></span>


### <a name="targets--int"></a><span data-ttu-id="b5453-112">mål: [int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="b5453-112">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="b5453-113">Kapslade matriser som beskriver målen för op.</span><span class="sxs-lookup"><span data-stu-id="b5453-113">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="b5453-114">Varje matris ska innehålla en lista över InTS som beskriver de index som ska användas.</span><span class="sxs-lookup"><span data-stu-id="b5453-114">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="b5453-115">Registrera: ' ' []</span><span class="sxs-lookup"><span data-stu-id="b5453-115">register : 'T[]</span></span>

<span data-ttu-id="b5453-116">Qubit-register att du ska handla på.</span><span class="sxs-lookup"><span data-stu-id="b5453-116">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b5453-117">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b5453-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b5453-118">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="b5453-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b5453-119">Inte</span><span class="sxs-lookup"><span data-stu-id="b5453-119">'T</span></span>



## <a name="see-also"></a><span data-ttu-id="b5453-120">Se även</span><span class="sxs-lookup"><span data-stu-id="b5453-120">See Also</span></span>

- [<span data-ttu-id="b5453-121">Microsoft. Quantum. Canon. ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="b5453-121">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)