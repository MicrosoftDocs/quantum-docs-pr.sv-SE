---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformationC
title: ApplyWithInputTransformationC-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformationC
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: 030c41d3ce0a5d613a95c6511f7278497ec5cda1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217177"
---
# <a name="applywithinputtransformationc-operation"></a><span data-ttu-id="bf86d-102">ApplyWithInputTransformationC-åtgärd</span><span class="sxs-lookup"><span data-stu-id="bf86d-102">ApplyWithInputTransformationC operation</span></span>

<span data-ttu-id="bf86d-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="bf86d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="bf86d-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bf86d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bf86d-105">Vid en åtgärd som accepterar vissa indata, en funktion som returnerar en utmatning som är kompatibel med den åtgärden och en indata till den funktionen, används åtgärden med funktionen för att transformera indata till ett formulär som förväntas av åtgärden.</span><span class="sxs-lookup"><span data-stu-id="bf86d-105">Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.</span></span>

```qsharp
operation ApplyWithInputTransformationC<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Ctl), input : 'U) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="bf86d-106">Indata</span><span class="sxs-lookup"><span data-stu-id="bf86d-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="bf86d-107">FN: U-></span><span class="sxs-lookup"><span data-stu-id="bf86d-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="bf86d-108">En funktion som transformerar den angivna ingången i ett formulär som förväntas av åtgärden.</span><span class="sxs-lookup"><span data-stu-id="bf86d-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="bf86d-109">OP: t => [enheten](xref:microsoft.quantum.lang-ref.unit)  är CTL</span><span class="sxs-lookup"><span data-stu-id="bf86d-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="bf86d-110">Åtgärden som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="bf86d-110">The operation to be applied.</span></span>


### <a name="input--u"></a><span data-ttu-id="bf86d-111">inmatade: ' U</span><span class="sxs-lookup"><span data-stu-id="bf86d-111">input : 'U</span></span>

<span data-ttu-id="bf86d-112">En indatamängd till funktionen.</span><span class="sxs-lookup"><span data-stu-id="bf86d-112">An input to the function.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bf86d-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bf86d-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="bf86d-114">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="bf86d-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bf86d-115">Inte</span><span class="sxs-lookup"><span data-stu-id="bf86d-115">'T</span></span>


### <a name="u"></a><span data-ttu-id="bf86d-116">' U</span><span class="sxs-lookup"><span data-stu-id="bf86d-116">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="bf86d-117">Se även</span><span class="sxs-lookup"><span data-stu-id="bf86d-117">See Also</span></span>

- [<span data-ttu-id="bf86d-118">Microsoft. Quantum. Canon. ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="bf86d-118">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="bf86d-119">Microsoft. Quantum. Canon. ApplyWithInputTransformationA</span><span class="sxs-lookup"><span data-stu-id="bf86d-119">Microsoft.Quantum.Canon.ApplyWithInputTransformationA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationA)
- [<span data-ttu-id="bf86d-120">Microsoft. Quantum. Canon. ApplyWithInputTransformationCA</span><span class="sxs-lookup"><span data-stu-id="bf86d-120">Microsoft.Quantum.Canon.ApplyWithInputTransformationCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationCA)
- [<span data-ttu-id="bf86d-121">Microsoft. Quantum. Canon. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="bf86d-121">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)