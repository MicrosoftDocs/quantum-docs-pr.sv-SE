---
uid: Microsoft.Quantum.Canon.ConjugatedByA
title: Funktionen ConjugatedByA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ConjugatedByA
qsharp.summary: Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.
ms.openlocfilehash: eaa104039b857f0469ddc0aaba97698eca20860d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207351"
---
# <a name="conjugatedbya-function"></a><span data-ttu-id="6acef-102">Funktionen ConjugatedByA</span><span class="sxs-lookup"><span data-stu-id="6acef-102">ConjugatedByA function</span></span>

<span data-ttu-id="6acef-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6acef-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6acef-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6acef-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6acef-105">Vissa yttre och inre åtgärder returnerar en ny åtgärd som konjugaterar den inre åtgärden med den yttre åtgärden.</span><span class="sxs-lookup"><span data-stu-id="6acef-105">Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.</span></span>

```qsharp
function ConjugatedByA<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Adj)) : ('T => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="6acef-106">Indata</span><span class="sxs-lookup"><span data-stu-id="6acef-106">Input</span></span>

### <a name="outeroperation--t--unit--is-adj"></a><span data-ttu-id="6acef-107">outerOperation: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just just</span><span class="sxs-lookup"><span data-stu-id="6acef-107">outerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="6acef-108">Åtgärden $U $ som ska användas för att konjugata $V $.</span><span class="sxs-lookup"><span data-stu-id="6acef-108">The operation $U$ that should be used to conjugate $V$.</span></span> <span data-ttu-id="6acef-109">Observera att den yttre åtgärden $U $ måste vara adjointable, men behöver inte vara kontrollerbar.</span><span class="sxs-lookup"><span data-stu-id="6acef-109">Note that the outer operation $U$ needs to be adjointable, but does not need to be controllable.</span></span>


### <a name="inneroperation--t--unit--is-adj"></a><span data-ttu-id="6acef-110">innerOperation: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just just</span><span class="sxs-lookup"><span data-stu-id="6acef-110">innerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="6acef-111">Åtgärden $V $ som är konjugaten.</span><span class="sxs-lookup"><span data-stu-id="6acef-111">The operation $V$ being conjugated.</span></span>



## <a name="output--t--unit--is-adj"></a><span data-ttu-id="6acef-112">Utdata: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just</span><span class="sxs-lookup"><span data-stu-id="6acef-112">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="6acef-113">En ny åtgärd vars åtgärd representeras av den enhetliga $U ^ {\dagger} V U $.</span><span class="sxs-lookup"><span data-stu-id="6acef-113">A new operation whose action is represented by the unitary $U^{\dagger} V U$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="6acef-114">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="6acef-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6acef-115">Inte</span><span class="sxs-lookup"><span data-stu-id="6acef-115">'T</span></span>

<span data-ttu-id="6acef-116">Typen av mål där var och en av de inre och yttre åtgärderna fungerar.</span><span class="sxs-lookup"><span data-stu-id="6acef-116">The type of the target on which each of the inner and outer operations act.</span></span>

## <a name="remarks"></a><span data-ttu-id="6acef-117">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="6acef-117">Remarks</span></span>

<span data-ttu-id="6acef-118">Den yttre åtgärden antas alltid vara adjointable, men behöver inte vara kontrollerbar för att den kombinerade åtgärden ska kunna kontrol leras.</span><span class="sxs-lookup"><span data-stu-id="6acef-118">The outer operation is always assumed to be adjointable, but does not need to be controllable in order for the combined operation to be controllable.</span></span>

## <a name="see-also"></a><span data-ttu-id="6acef-119">Se även</span><span class="sxs-lookup"><span data-stu-id="6acef-119">See Also</span></span>

- [<span data-ttu-id="6acef-120">Microsoft. Quantum. Canon. ConjugatedByA</span><span class="sxs-lookup"><span data-stu-id="6acef-120">Microsoft.Quantum.Canon.ConjugatedByA</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByA)
- [<span data-ttu-id="6acef-121">Microsoft. Quantum. Canon. ConjugatedByC</span><span class="sxs-lookup"><span data-stu-id="6acef-121">Microsoft.Quantum.Canon.ConjugatedByC</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByC)
- [<span data-ttu-id="6acef-122">Microsoft. Quantum. Canon. ConjugatedByCA</span><span class="sxs-lookup"><span data-stu-id="6acef-122">Microsoft.Quantum.Canon.ConjugatedByCA</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByCA)
- [<span data-ttu-id="6acef-123">Microsoft. Quantum. Canon. ApplyWith</span><span class="sxs-lookup"><span data-stu-id="6acef-123">Microsoft.Quantum.Canon.ApplyWith</span></span>](xref:Microsoft.Quantum.Canon.ApplyWith)