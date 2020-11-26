---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOps
title: ApplySeriesOfOps-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOps
qsharp.summary: Applies a list of ops and their targets sequentially on an array.
ms.openlocfilehash: b8810e7d31689046e72905195a3a25ef80fc8d67
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218010"
---
# <a name="applyseriesofops-operation"></a><span data-ttu-id="683cb-102">ApplySeriesOfOps-åtgärd</span><span class="sxs-lookup"><span data-stu-id="683cb-102">ApplySeriesOfOps operation</span></span>

<span data-ttu-id="683cb-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="683cb-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="683cb-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="683cb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="683cb-105">Använder en lista med OPS och deras mål sekventiellt i en matris.</span><span class="sxs-lookup"><span data-stu-id="683cb-105">Applies a list of ops and their targets sequentially on an array.</span></span>

```qsharp
operation ApplySeriesOfOps<'T> (listOfOps : ('T[] => Unit)[], targets : Int[][], register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="683cb-106">Indata</span><span class="sxs-lookup"><span data-stu-id="683cb-106">Input</span></span>

### <a name="listofops--t--unit-"></a><span data-ttu-id="683cb-107">listOfOps: ' t [] => [enhet](xref:microsoft.quantum.lang-ref.unit) []</span><span class="sxs-lookup"><span data-stu-id="683cb-107">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) []</span></span>

<span data-ttu-id="683cb-108">En lista med OPS, vart och ett som tar en matris som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="683cb-108">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="683cb-109">De tillämpas sekventiellt, lägsta index först.</span><span class="sxs-lookup"><span data-stu-id="683cb-109">They are applied sequentially, lowest index first.</span></span>


### <a name="targets--int"></a><span data-ttu-id="683cb-110">mål: [int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="683cb-110">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="683cb-111">Kapslade matriser som beskriver målen för op.</span><span class="sxs-lookup"><span data-stu-id="683cb-111">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="683cb-112">Varje matris ska innehålla en lista över InTS som beskriver de index som ska användas.</span><span class="sxs-lookup"><span data-stu-id="683cb-112">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="683cb-113">Registrera: ' ' []</span><span class="sxs-lookup"><span data-stu-id="683cb-113">register : 'T[]</span></span>

<span data-ttu-id="683cb-114">Qubit-register att du ska handla på.</span><span class="sxs-lookup"><span data-stu-id="683cb-114">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="683cb-115">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="683cb-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="683cb-116">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="683cb-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="683cb-117">Inte</span><span class="sxs-lookup"><span data-stu-id="683cb-117">'T</span></span>



## <a name="see-also"></a><span data-ttu-id="683cb-118">Se även</span><span class="sxs-lookup"><span data-stu-id="683cb-118">See Also</span></span>

- [<span data-ttu-id="683cb-119">Microsoft. Quantum. Canon. ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="683cb-119">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)