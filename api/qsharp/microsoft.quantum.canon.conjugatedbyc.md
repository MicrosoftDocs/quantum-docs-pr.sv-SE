---
uid: Microsoft.Quantum.Canon.ConjugatedByC
title: Funktionen ConjugatedByC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ConjugatedByC
qsharp.summary: Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.
ms.openlocfilehash: c4c381e40c5a941487bcf78ebe5339574aedb45d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728824"
---
# <a name="conjugatedbyc-function"></a><span data-ttu-id="832d7-102">Funktionen ConjugatedByC</span><span class="sxs-lookup"><span data-stu-id="832d7-102">ConjugatedByC function</span></span>

<span data-ttu-id="832d7-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="832d7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="832d7-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="832d7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="832d7-105">Vissa yttre och inre åtgärder returnerar en ny åtgärd som konjugaterar den inre åtgärden med den yttre åtgärden.</span><span class="sxs-lookup"><span data-stu-id="832d7-105">Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.</span></span>

```qsharp
function ConjugatedByC<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Ctl)) : ('T => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="832d7-106">Indata</span><span class="sxs-lookup"><span data-stu-id="832d7-106">Input</span></span>

### <a name="outeroperation--t--unit-adj"></a><span data-ttu-id="832d7-107">outerOperation: t => [enhets](xref:microsoft.quantum.lang-ref.unit) justering</span><span class="sxs-lookup"><span data-stu-id="832d7-107">outerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="832d7-108">Åtgärden $U $ som ska användas för att konjugata $V $.</span><span class="sxs-lookup"><span data-stu-id="832d7-108">The operation $U$ that should be used to conjugate $V$.</span></span> <span data-ttu-id="832d7-109">Observera att den yttre åtgärden $U $ måste vara adjointable, men behöver inte vara kontrollerbar.</span><span class="sxs-lookup"><span data-stu-id="832d7-109">Note that the outer operation $U$ needs to be adjointable, but does not need to be controllable.</span></span>


### <a name="inneroperation--t--unit-ctl"></a><span data-ttu-id="832d7-110">innerOperation: t => [enhet](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="832d7-110">innerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="832d7-111">Åtgärden $V $ som är konjugaten.</span><span class="sxs-lookup"><span data-stu-id="832d7-111">The operation $V$ being conjugated.</span></span>



## <a name="output--t--unit-ctl"></a><span data-ttu-id="832d7-112">Utdata: t => [enhet](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="832d7-112">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="832d7-113">En ny åtgärd vars åtgärd representeras av den enhetliga $U ^ {\dagger} V U $.</span><span class="sxs-lookup"><span data-stu-id="832d7-113">A new operation whose action is represented by the unitary $U^{\dagger} V U$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="832d7-114">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="832d7-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="832d7-115">Inte</span><span class="sxs-lookup"><span data-stu-id="832d7-115">'T</span></span>

<span data-ttu-id="832d7-116">Typen av mål där var och en av de inre och yttre åtgärderna fungerar.</span><span class="sxs-lookup"><span data-stu-id="832d7-116">The type of the target on which each of the inner and outer operations act.</span></span>

## <a name="remarks"></a><span data-ttu-id="832d7-117">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="832d7-117">Remarks</span></span>

<span data-ttu-id="832d7-118">Den yttre åtgärden antas alltid vara adjointable, men behöver inte vara kontrollerbar för att den kombinerade åtgärden ska kunna kontrol leras.</span><span class="sxs-lookup"><span data-stu-id="832d7-118">The outer operation is always assumed to be adjointable, but does not need to be controllable in order for the combined operation to be controllable.</span></span>

## <a name="see-also"></a><span data-ttu-id="832d7-119">Se även</span><span class="sxs-lookup"><span data-stu-id="832d7-119">See Also</span></span>

- [<span data-ttu-id="832d7-120">Microsoft. Quantum. Canon. ConjugatedBy</span><span class="sxs-lookup"><span data-stu-id="832d7-120">Microsoft.Quantum.Canon.ConjugatedBy</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedBy)
- [<span data-ttu-id="832d7-121">Microsoft. Quantum. Canon. ConjugatedByA</span><span class="sxs-lookup"><span data-stu-id="832d7-121">Microsoft.Quantum.Canon.ConjugatedByA</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByA)
- [<span data-ttu-id="832d7-122">Microsoft. Quantum. Canon. ConjugatedByCA</span><span class="sxs-lookup"><span data-stu-id="832d7-122">Microsoft.Quantum.Canon.ConjugatedByCA</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByCA)
- [<span data-ttu-id="832d7-123">Microsoft. Quantum. Canon. ApplyWith</span><span class="sxs-lookup"><span data-stu-id="832d7-123">Microsoft.Quantum.Canon.ApplyWith</span></span>](xref:Microsoft.Quantum.Canon.ApplyWith)