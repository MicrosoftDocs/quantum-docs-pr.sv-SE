---
uid: Microsoft.Quantum.Canon.ApplyWithA
title: ApplyWithA-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithA
qsharp.summary: Given two operations, applies one as conjugated with the other.
ms.openlocfilehash: f1ff31da53952931426d358cbedad44a50d87f5e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729025"
---
# <a name="applywitha-operation"></a><span data-ttu-id="1b44a-102">ApplyWithA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="1b44a-102">ApplyWithA operation</span></span>

<span data-ttu-id="1b44a-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1b44a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1b44a-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1b44a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1b44a-105">Med två åtgärder används en som konjugaten med den andra.</span><span class="sxs-lookup"><span data-stu-id="1b44a-105">Given two operations, applies one as conjugated with the other.</span></span>

```qsharp
operation ApplyWithA<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Adj), target : 'T) : Unit
```


## <a name="description"></a><span data-ttu-id="1b44a-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="1b44a-106">Description</span></span>

<span data-ttu-id="1b44a-107">Två åtgärder, som beskrivs av de enhetliga operatörerna $U $ och $V $, tillämpar dem i sekvensen $U ^ {\dagger} V U $.</span><span class="sxs-lookup"><span data-stu-id="1b44a-107">Given two operations, respectively described by unitary operators $U$ and $V$, applies them in the sequence $U^{\dagger} V U$.</span></span> <span data-ttu-id="1b44a-108">Det innebär att den här åtgärden implementerar den enhetliga operatorn som tillhandahålls av $V $ som har avgivits med $U $.</span><span class="sxs-lookup"><span data-stu-id="1b44a-108">That is, this operation implements the unitary operator given by $V$ conjugated with $U$.</span></span>

## <a name="input"></a><span data-ttu-id="1b44a-109">Indata</span><span class="sxs-lookup"><span data-stu-id="1b44a-109">Input</span></span>

### <a name="outeroperation--t--unit-adj"></a><span data-ttu-id="1b44a-110">outerOperation: t => [enhets](xref:microsoft.quantum.lang-ref.unit) justering</span><span class="sxs-lookup"><span data-stu-id="1b44a-110">outerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="1b44a-111">Åtgärden $U $ som ska användas för att konjugata $V $.</span><span class="sxs-lookup"><span data-stu-id="1b44a-111">The operation $U$ that should be used to conjugate $V$.</span></span> <span data-ttu-id="1b44a-112">Observera att den yttre åtgärden $U $ måste vara adjointable, men behöver inte vara kontrollerbar.</span><span class="sxs-lookup"><span data-stu-id="1b44a-112">Note that the outer operation $U$ needs to be adjointable, but does not need to be controllable.</span></span>


### <a name="inneroperation--t--unit-adj"></a><span data-ttu-id="1b44a-113">innerOperation: t => [enhets](xref:microsoft.quantum.lang-ref.unit) justering</span><span class="sxs-lookup"><span data-stu-id="1b44a-113">innerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="1b44a-114">Åtgärden $V $ som är konjugaten.</span><span class="sxs-lookup"><span data-stu-id="1b44a-114">The operation $V$ being conjugated.</span></span>


### <a name="target--t"></a><span data-ttu-id="1b44a-115">mål: ' t</span><span class="sxs-lookup"><span data-stu-id="1b44a-115">target : 'T</span></span>

<span data-ttu-id="1b44a-116">Indata som ska tillhandahållas de yttre och inre åtgärderna.</span><span class="sxs-lookup"><span data-stu-id="1b44a-116">The input to be provided to the outer and inner operations.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1b44a-117">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1b44a-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="1b44a-118">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="1b44a-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1b44a-119">Inte</span><span class="sxs-lookup"><span data-stu-id="1b44a-119">'T</span></span>

<span data-ttu-id="1b44a-120">Målet där var och en av de inre och yttre åtgärderna fungerar.</span><span class="sxs-lookup"><span data-stu-id="1b44a-120">The target on which each of the inner and outer operations act.</span></span>

## <a name="remarks"></a><span data-ttu-id="1b44a-121">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="1b44a-121">Remarks</span></span>

<span data-ttu-id="1b44a-122">Den yttre åtgärden antas alltid vara adjointable, men behöver inte vara kontrollerbar för att den kombinerade åtgärden ska kunna kontrol leras.</span><span class="sxs-lookup"><span data-stu-id="1b44a-122">The outer operation is always assumed to be adjointable, but does not need to be controllable in order for the combined operation to be controllable.</span></span>

## <a name="see-also"></a><span data-ttu-id="1b44a-123">Se även</span><span class="sxs-lookup"><span data-stu-id="1b44a-123">See Also</span></span>

- [<span data-ttu-id="1b44a-124">Microsoft. Quantum. Canon. ApplyWith</span><span class="sxs-lookup"><span data-stu-id="1b44a-124">Microsoft.Quantum.Canon.ApplyWith</span></span>](xref:Microsoft.Quantum.Canon.ApplyWith)
- [<span data-ttu-id="1b44a-125">Microsoft. Quantum. Canon. ApplyWithC</span><span class="sxs-lookup"><span data-stu-id="1b44a-125">Microsoft.Quantum.Canon.ApplyWithC</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithC)
- [<span data-ttu-id="1b44a-126">Microsoft. Quantum. Canon. ApplyWithCA</span><span class="sxs-lookup"><span data-stu-id="1b44a-126">Microsoft.Quantum.Canon.ApplyWithCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithCA)