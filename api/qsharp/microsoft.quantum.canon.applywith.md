---
uid: Microsoft.Quantum.Canon.ApplyWith
title: ApplyWith-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWith
qsharp.summary: Given two operations, applies one as conjugated with the other.
ms.openlocfilehash: 7127df047a260b18d75efb092e8e090e2d0b207a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850408"
---
# <a name="applywith-operation"></a><span data-ttu-id="a7e93-102">ApplyWith-åtgärd</span><span class="sxs-lookup"><span data-stu-id="a7e93-102">ApplyWith operation</span></span>

<span data-ttu-id="a7e93-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a7e93-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a7e93-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a7e93-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a7e93-105">Med två åtgärder används en som konjugaten med den andra.</span><span class="sxs-lookup"><span data-stu-id="a7e93-105">Given two operations, applies one as conjugated with the other.</span></span>

```qsharp
operation ApplyWith<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit), target : 'T) : Unit
```


## <a name="description"></a><span data-ttu-id="a7e93-106">Description</span><span class="sxs-lookup"><span data-stu-id="a7e93-106">Description</span></span>

<span data-ttu-id="a7e93-107">Två åtgärder, som beskrivs av de enhetliga operatörerna $U $ och $V $, tillämpar dem i sekvensen $U ^ {\dagger} V U $.</span><span class="sxs-lookup"><span data-stu-id="a7e93-107">Given two operations, respectively described by unitary operators $U$ and $V$, applies them in the sequence $U^{\dagger} V U$.</span></span> <span data-ttu-id="a7e93-108">Det innebär att den här åtgärden implementerar den enhetliga operatorn som tillhandahålls av $V $ som har avgivits med $U $.</span><span class="sxs-lookup"><span data-stu-id="a7e93-108">That is, this operation implements the unitary operator given by $V$ conjugated with $U$.</span></span>

## <a name="input"></a><span data-ttu-id="a7e93-109">Indata</span><span class="sxs-lookup"><span data-stu-id="a7e93-109">Input</span></span>

### <a name="outeroperation--t--unit--is-adj"></a><span data-ttu-id="a7e93-110">outerOperation: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just just</span><span class="sxs-lookup"><span data-stu-id="a7e93-110">outerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="a7e93-111">Åtgärden $U $ som ska användas för att konjugata $V $.</span><span class="sxs-lookup"><span data-stu-id="a7e93-111">The operation $U$ that should be used to conjugate $V$.</span></span> <span data-ttu-id="a7e93-112">Observera att den yttre åtgärden $U $ måste vara adjointable, men behöver inte vara kontrollerbar.</span><span class="sxs-lookup"><span data-stu-id="a7e93-112">Note that the outer operation $U$ needs to be adjointable, but does not need to be controllable.</span></span>


### <a name="inneroperation--t--unit"></a><span data-ttu-id="a7e93-113">innerOperation: t => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a7e93-113">innerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="a7e93-114">Åtgärden $V $ som är konjugaten.</span><span class="sxs-lookup"><span data-stu-id="a7e93-114">The operation $V$ being conjugated.</span></span>


### <a name="target--t"></a><span data-ttu-id="a7e93-115">mål: ' t</span><span class="sxs-lookup"><span data-stu-id="a7e93-115">target : 'T</span></span>

<span data-ttu-id="a7e93-116">Indata som ska tillhandahållas de yttre och inre åtgärderna.</span><span class="sxs-lookup"><span data-stu-id="a7e93-116">The input to be provided to the outer and inner operations.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a7e93-117">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a7e93-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="a7e93-118">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="a7e93-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a7e93-119">Inte</span><span class="sxs-lookup"><span data-stu-id="a7e93-119">'T</span></span>

<span data-ttu-id="a7e93-120">Målet där var och en av de inre och yttre åtgärderna fungerar.</span><span class="sxs-lookup"><span data-stu-id="a7e93-120">The target on which each of the inner and outer operations act.</span></span>

## <a name="remarks"></a><span data-ttu-id="a7e93-121">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="a7e93-121">Remarks</span></span>

<span data-ttu-id="a7e93-122">Den yttre åtgärden antas alltid vara adjointable, men behöver inte vara kontrollerbar för att den kombinerade åtgärden ska kunna kontrol leras.</span><span class="sxs-lookup"><span data-stu-id="a7e93-122">The outer operation is always assumed to be adjointable, but does not need to be controllable in order for the combined operation to be controllable.</span></span>

## <a name="see-also"></a><span data-ttu-id="a7e93-123">Se även</span><span class="sxs-lookup"><span data-stu-id="a7e93-123">See Also</span></span>

- [<span data-ttu-id="a7e93-124">Microsoft. Quantum. Canon. ApplyWithA</span><span class="sxs-lookup"><span data-stu-id="a7e93-124">Microsoft.Quantum.Canon.ApplyWithA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithA)
- [<span data-ttu-id="a7e93-125">Microsoft. Quantum. Canon. ApplyWithC</span><span class="sxs-lookup"><span data-stu-id="a7e93-125">Microsoft.Quantum.Canon.ApplyWithC</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithC)
- [<span data-ttu-id="a7e93-126">Microsoft. Quantum. Canon. ApplyWithCA</span><span class="sxs-lookup"><span data-stu-id="a7e93-126">Microsoft.Quantum.Canon.ApplyWithCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithCA)