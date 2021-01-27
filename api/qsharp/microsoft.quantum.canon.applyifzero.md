---
uid: Microsoft.Quantum.Canon.ApplyIfZero
title: ApplyIfZero-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfZero
qsharp.summary: Applies an operation conditioned on a classical result value being zero.
ms.openlocfilehash: 215b71a8d2e4f8a22df05b210824bc40a969b6f6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841733"
---
# <a name="applyifzero-operation"></a><span data-ttu-id="ffc1e-102">ApplyIfZero-åtgärd</span><span class="sxs-lookup"><span data-stu-id="ffc1e-102">ApplyIfZero operation</span></span>

<span data-ttu-id="ffc1e-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ffc1e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ffc1e-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ffc1e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ffc1e-105">Tillämpar ett åtgärds villkor på ett klassiskt resultat värde som noll.</span><span class="sxs-lookup"><span data-stu-id="ffc1e-105">Applies an operation conditioned on a classical result value being zero.</span></span>

```qsharp
operation ApplyIfZero<'T> (result : Result, (op : ('T => Unit), target : 'T)) : Unit
```


## <a name="description"></a><span data-ttu-id="ffc1e-106">Description</span><span class="sxs-lookup"><span data-stu-id="ffc1e-106">Description</span></span>

<span data-ttu-id="ffc1e-107">En åtgärd `op` och ett resultat värde `result` gäller `op` för `target` IF `result` `Zero` .</span><span class="sxs-lookup"><span data-stu-id="ffc1e-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `Zero`.</span></span> <span data-ttu-id="ffc1e-108">Om `One` händer ingenting `target` .</span><span class="sxs-lookup"><span data-stu-id="ffc1e-108">If `One`, nothing happens to the `target`.</span></span>

## <a name="input"></a><span data-ttu-id="ffc1e-109">Indata</span><span class="sxs-lookup"><span data-stu-id="ffc1e-109">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="ffc1e-110">resultat: __ogiltigt <Result>__</span><span class="sxs-lookup"><span data-stu-id="ffc1e-110">result : __invalid<Result>__</span></span>

<span data-ttu-id="ffc1e-111">Ett mått resultat som styr om OP används eller inte.</span><span class="sxs-lookup"><span data-stu-id="ffc1e-111">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit"></a><span data-ttu-id="ffc1e-112">OP: t => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ffc1e-112">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="ffc1e-113">En åtgärd som ska tillämpas villkorligt.</span><span class="sxs-lookup"><span data-stu-id="ffc1e-113">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="ffc1e-114">mål: ' t</span><span class="sxs-lookup"><span data-stu-id="ffc1e-114">target : 'T</span></span>

<span data-ttu-id="ffc1e-115">De indatatyper som åtgärden tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="ffc1e-115">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ffc1e-116">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ffc1e-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ffc1e-117">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="ffc1e-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ffc1e-118">Inte</span><span class="sxs-lookup"><span data-stu-id="ffc1e-118">'T</span></span>

<span data-ttu-id="ffc1e-119">Indatatypen för den åtgärd som ska tillämpas villkorligt.</span><span class="sxs-lookup"><span data-stu-id="ffc1e-119">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="ffc1e-120">Se även</span><span class="sxs-lookup"><span data-stu-id="ffc1e-120">See Also</span></span>

- [<span data-ttu-id="ffc1e-121">Microsoft. Quantum. Canon. ApplyIfZeroC</span><span class="sxs-lookup"><span data-stu-id="ffc1e-121">Microsoft.Quantum.Canon.ApplyIfZeroC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroC)
- [<span data-ttu-id="ffc1e-122">Microsoft. Quantum. Canon. ApplyIfZeroA</span><span class="sxs-lookup"><span data-stu-id="ffc1e-122">Microsoft.Quantum.Canon.ApplyIfZeroA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroA)
- [<span data-ttu-id="ffc1e-123">Microsoft. Quantum. Canon. ApplyIfZeroCA</span><span class="sxs-lookup"><span data-stu-id="ffc1e-123">Microsoft.Quantum.Canon.ApplyIfZeroCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroCA)