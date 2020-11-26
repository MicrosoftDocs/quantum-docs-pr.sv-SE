---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsC
title: ApplySeriesOfOpsC-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsC
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Controlled)
ms.openlocfilehash: eaa0ea3e33cce708af5879cfbe875397fbb82a8a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217942"
---
# <a name="applyseriesofopsc-operation"></a><span data-ttu-id="85b8d-102">ApplySeriesOfOpsC-åtgärd</span><span class="sxs-lookup"><span data-stu-id="85b8d-102">ApplySeriesOfOpsC operation</span></span>

<span data-ttu-id="85b8d-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="85b8d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="85b8d-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="85b8d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="85b8d-105">Använder en lista med OPS och deras mål sekventiellt i en matris.</span><span class="sxs-lookup"><span data-stu-id="85b8d-105">Applies a list of ops and their targets sequentially on an array.</span></span> <span data-ttu-id="85b8d-106">Styr</span><span class="sxs-lookup"><span data-stu-id="85b8d-106">(Controlled)</span></span>

```qsharp
operation ApplySeriesOfOpsC<'T> (listOfOps : ('T[] => Unit is Ctl)[], targets : Int[][], register : 'T[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="85b8d-107">Indata</span><span class="sxs-lookup"><span data-stu-id="85b8d-107">Input</span></span>

### <a name="listofops--t--unit--is-ctl"></a><span data-ttu-id="85b8d-108">listOfOps: ' t [] => [enhet](xref:microsoft.quantum.lang-ref.unit)  är CTL []</span><span class="sxs-lookup"><span data-stu-id="85b8d-108">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl[]</span></span>

<span data-ttu-id="85b8d-109">En lista med OPS, vart och ett som tar en matris som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="85b8d-109">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="85b8d-110">De tillämpas sekventiellt, lägsta index först.</span><span class="sxs-lookup"><span data-stu-id="85b8d-110">They are applied sequentially, lowest index first.</span></span>
<span data-ttu-id="85b8d-111">Varje måste ha en kontrollerad Functor</span><span class="sxs-lookup"><span data-stu-id="85b8d-111">Each must have a Controlled functor</span></span>


### <a name="targets--int"></a><span data-ttu-id="85b8d-112">mål: [int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="85b8d-112">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="85b8d-113">Kapslade matriser som beskriver målen för op.</span><span class="sxs-lookup"><span data-stu-id="85b8d-113">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="85b8d-114">Varje matris ska innehålla en lista över InTS som beskriver de index som ska användas.</span><span class="sxs-lookup"><span data-stu-id="85b8d-114">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="85b8d-115">Registrera: ' ' []</span><span class="sxs-lookup"><span data-stu-id="85b8d-115">register : 'T[]</span></span>

<span data-ttu-id="85b8d-116">Qubit-register att du ska handla på.</span><span class="sxs-lookup"><span data-stu-id="85b8d-116">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="85b8d-117">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="85b8d-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="85b8d-118">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="85b8d-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="85b8d-119">Inte</span><span class="sxs-lookup"><span data-stu-id="85b8d-119">'T</span></span>



## <a name="see-also"></a><span data-ttu-id="85b8d-120">Se även</span><span class="sxs-lookup"><span data-stu-id="85b8d-120">See Also</span></span>

- [<span data-ttu-id="85b8d-121">Microsoft. Quantum. Canon. ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="85b8d-121">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)