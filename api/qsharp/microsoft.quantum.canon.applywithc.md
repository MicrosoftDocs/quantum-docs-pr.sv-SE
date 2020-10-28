---
uid: Microsoft.Quantum.Canon.ApplyWithC
title: ApplyWithC-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithC
qsharp.summary: Given two operations, applies one as conjugated with the other.
ms.openlocfilehash: 8de1ddf0bf176853b33926be7647bc5d1d35095d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729013"
---
# <a name="applywithc-operation"></a><span data-ttu-id="dbb55-102">ApplyWithC-åtgärd</span><span class="sxs-lookup"><span data-stu-id="dbb55-102">ApplyWithC operation</span></span>

<span data-ttu-id="dbb55-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="dbb55-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="dbb55-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="dbb55-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="dbb55-105">Med två åtgärder används en som konjugaten med den andra.</span><span class="sxs-lookup"><span data-stu-id="dbb55-105">Given two operations, applies one as conjugated with the other.</span></span>

```qsharp
operation ApplyWithC<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Ctl), target : 'T) : Unit
```


## <a name="description"></a><span data-ttu-id="dbb55-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="dbb55-106">Description</span></span>

<span data-ttu-id="dbb55-107">Två åtgärder, som beskrivs av de enhetliga operatörerna $U $ och $V $, tillämpar dem i sekvensen $U ^ {\dagger} V U $.</span><span class="sxs-lookup"><span data-stu-id="dbb55-107">Given two operations, respectively described by unitary operators $U$ and $V$, applies them in the sequence $U^{\dagger} V U$.</span></span> <span data-ttu-id="dbb55-108">Det innebär att den här åtgärden implementerar den enhetliga operatorn som tillhandahålls av $V $ som har avgivits med $U $.</span><span class="sxs-lookup"><span data-stu-id="dbb55-108">That is, this operation implements the unitary operator given by $V$ conjugated with $U$.</span></span>

## <a name="input"></a><span data-ttu-id="dbb55-109">Indata</span><span class="sxs-lookup"><span data-stu-id="dbb55-109">Input</span></span>

### <a name="outeroperation--t--unit-adj"></a><span data-ttu-id="dbb55-110">outerOperation: t => [enhets](xref:microsoft.quantum.lang-ref.unit) justering</span><span class="sxs-lookup"><span data-stu-id="dbb55-110">outerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="dbb55-111">Åtgärden $U $ som ska användas för att konjugata $V $.</span><span class="sxs-lookup"><span data-stu-id="dbb55-111">The operation $U$ that should be used to conjugate $V$.</span></span> <span data-ttu-id="dbb55-112">Observera att den yttre åtgärden $U $ måste vara adjointable, men behöver inte vara kontrollerbar.</span><span class="sxs-lookup"><span data-stu-id="dbb55-112">Note that the outer operation $U$ needs to be adjointable, but does not need to be controllable.</span></span>


### <a name="inneroperation--t--unit-ctl"></a><span data-ttu-id="dbb55-113">innerOperation: t => [enhet](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="dbb55-113">innerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="dbb55-114">Åtgärden $V $ som är konjugaten.</span><span class="sxs-lookup"><span data-stu-id="dbb55-114">The operation $V$ being conjugated.</span></span>


### <a name="target--t"></a><span data-ttu-id="dbb55-115">mål: ' t</span><span class="sxs-lookup"><span data-stu-id="dbb55-115">target : 'T</span></span>

<span data-ttu-id="dbb55-116">Indata som ska tillhandahållas de yttre och inre åtgärderna.</span><span class="sxs-lookup"><span data-stu-id="dbb55-116">The input to be provided to the outer and inner operations.</span></span>



## <a name="output--unit"></a><span data-ttu-id="dbb55-117">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dbb55-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="dbb55-118">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="dbb55-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="dbb55-119">Inte</span><span class="sxs-lookup"><span data-stu-id="dbb55-119">'T</span></span>

<span data-ttu-id="dbb55-120">Målet där var och en av de inre och yttre åtgärderna fungerar.</span><span class="sxs-lookup"><span data-stu-id="dbb55-120">The target on which each of the inner and outer operations act.</span></span>

## <a name="remarks"></a><span data-ttu-id="dbb55-121">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="dbb55-121">Remarks</span></span>

<span data-ttu-id="dbb55-122">Den yttre åtgärden antas alltid vara adjointable, men behöver inte vara kontrollerbar för att den kombinerade åtgärden ska kunna kontrol leras.</span><span class="sxs-lookup"><span data-stu-id="dbb55-122">The outer operation is always assumed to be adjointable, but does not need to be controllable in order for the combined operation to be controllable.</span></span>

## <a name="see-also"></a><span data-ttu-id="dbb55-123">Se även</span><span class="sxs-lookup"><span data-stu-id="dbb55-123">See Also</span></span>

- [<span data-ttu-id="dbb55-124">Microsoft. Quantum. Canon. ApplyWith</span><span class="sxs-lookup"><span data-stu-id="dbb55-124">Microsoft.Quantum.Canon.ApplyWith</span></span>](xref:Microsoft.Quantum.Canon.ApplyWith)
- [<span data-ttu-id="dbb55-125">Microsoft. Quantum. Canon. ApplyWithA</span><span class="sxs-lookup"><span data-stu-id="dbb55-125">Microsoft.Quantum.Canon.ApplyWithA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithA)
- [<span data-ttu-id="dbb55-126">Microsoft. Quantum. Canon. ApplyWithCA</span><span class="sxs-lookup"><span data-stu-id="dbb55-126">Microsoft.Quantum.Canon.ApplyWithCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithCA)