---
uid: Microsoft.Quantum.Canon.ApplyWithCA
title: ApplyWithCA-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithCA
qsharp.summary: Given two operations, applies one as conjugated with the other.
ms.openlocfilehash: e86c452e9693c5a4d0d4e5a36471ab46bbf66dfe
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208150"
---
# <a name="applywithca-operation"></a><span data-ttu-id="fab74-102">ApplyWithCA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="fab74-102">ApplyWithCA operation</span></span>

<span data-ttu-id="fab74-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="fab74-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="fab74-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fab74-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fab74-105">Med två åtgärder används en som konjugaten med den andra.</span><span class="sxs-lookup"><span data-stu-id="fab74-105">Given two operations, applies one as conjugated with the other.</span></span>

```qsharp
operation ApplyWithCA<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Adj + Ctl), target : 'T) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="fab74-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="fab74-106">Description</span></span>

<span data-ttu-id="fab74-107">Två åtgärder, som beskrivs av de enhetliga operatörerna $U $ och $V $, tillämpar dem i sekvensen $U ^ {\dagger} V U $.</span><span class="sxs-lookup"><span data-stu-id="fab74-107">Given two operations, respectively described by unitary operators $U$ and $V$, applies them in the sequence $U^{\dagger} V U$.</span></span> <span data-ttu-id="fab74-108">Det innebär att den här åtgärden implementerar den enhetliga operatorn som tillhandahålls av $V $ som har avgivits med $U $.</span><span class="sxs-lookup"><span data-stu-id="fab74-108">That is, this operation implements the unitary operator given by $V$ conjugated with $U$.</span></span>

## <a name="input"></a><span data-ttu-id="fab74-109">Indata</span><span class="sxs-lookup"><span data-stu-id="fab74-109">Input</span></span>

### <a name="outeroperation--t--unit--is-adj"></a><span data-ttu-id="fab74-110">outerOperation: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just just</span><span class="sxs-lookup"><span data-stu-id="fab74-110">outerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="fab74-111">Åtgärden $U $ som ska användas för att konjugata $V $.</span><span class="sxs-lookup"><span data-stu-id="fab74-111">The operation $U$ that should be used to conjugate $V$.</span></span> <span data-ttu-id="fab74-112">Observera att den yttre åtgärden $U $ måste vara adjointable, men behöver inte vara kontrollerbar.</span><span class="sxs-lookup"><span data-stu-id="fab74-112">Note that the outer operation $U$ needs to be adjointable, but does not need to be controllable.</span></span>


### <a name="inneroperation--t--unit--is-adj--ctl"></a><span data-ttu-id="fab74-113">innerOperation: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL</span><span class="sxs-lookup"><span data-stu-id="fab74-113">innerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="fab74-114">Åtgärden $V $ som är konjugaten.</span><span class="sxs-lookup"><span data-stu-id="fab74-114">The operation $V$ being conjugated.</span></span>


### <a name="target--t"></a><span data-ttu-id="fab74-115">mål: ' t</span><span class="sxs-lookup"><span data-stu-id="fab74-115">target : 'T</span></span>

<span data-ttu-id="fab74-116">Indata som ska tillhandahållas de yttre och inre åtgärderna.</span><span class="sxs-lookup"><span data-stu-id="fab74-116">The input to be provided to the outer and inner operations.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fab74-117">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fab74-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="fab74-118">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="fab74-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="fab74-119">Inte</span><span class="sxs-lookup"><span data-stu-id="fab74-119">'T</span></span>

<span data-ttu-id="fab74-120">Målet där var och en av de inre och yttre åtgärderna fungerar.</span><span class="sxs-lookup"><span data-stu-id="fab74-120">The target on which each of the inner and outer operations act.</span></span>

## <a name="remarks"></a><span data-ttu-id="fab74-121">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="fab74-121">Remarks</span></span>

<span data-ttu-id="fab74-122">Den yttre åtgärden antas alltid vara adjointable, men behöver inte vara kontrollerbar för att den kombinerade åtgärden ska kunna kontrol leras.</span><span class="sxs-lookup"><span data-stu-id="fab74-122">The outer operation is always assumed to be adjointable, but does not need to be controllable in order for the combined operation to be controllable.</span></span>

## <a name="see-also"></a><span data-ttu-id="fab74-123">Se även</span><span class="sxs-lookup"><span data-stu-id="fab74-123">See Also</span></span>

- [<span data-ttu-id="fab74-124">Microsoft. Quantum. Canon. ApplyWith</span><span class="sxs-lookup"><span data-stu-id="fab74-124">Microsoft.Quantum.Canon.ApplyWith</span></span>](xref:Microsoft.Quantum.Canon.ApplyWith)
- [<span data-ttu-id="fab74-125">Microsoft. Quantum. Canon. ApplyWithA</span><span class="sxs-lookup"><span data-stu-id="fab74-125">Microsoft.Quantum.Canon.ApplyWithA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithA)
- [<span data-ttu-id="fab74-126">Microsoft. Quantum. Canon. ApplyWithC</span><span class="sxs-lookup"><span data-stu-id="fab74-126">Microsoft.Quantum.Canon.ApplyWithC</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithC)