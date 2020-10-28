---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformationCA
title: ApplyWithInputTransformationCA-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformationCA
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: c80ce0887a202a60de81c2d12fa95ce1eab59058
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728986"
---
# <a name="applywithinputtransformationca-operation"></a><span data-ttu-id="0c7fc-102">ApplyWithInputTransformationCA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="0c7fc-102">ApplyWithInputTransformationCA operation</span></span>

<span data-ttu-id="0c7fc-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0c7fc-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0c7fc-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0c7fc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0c7fc-105">Vid en åtgärd som accepterar vissa indata, en funktion som returnerar en utmatning som är kompatibel med den åtgärden och en indata till den funktionen, används åtgärden med funktionen för att transformera indata till ett formulär som förväntas av åtgärden.</span><span class="sxs-lookup"><span data-stu-id="0c7fc-105">Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.</span></span>

```qsharp
operation ApplyWithInputTransformationCA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj + Ctl), input : 'U) : Unit
```


## <a name="input"></a><span data-ttu-id="0c7fc-106">Indata</span><span class="sxs-lookup"><span data-stu-id="0c7fc-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="0c7fc-107">FN: U-></span><span class="sxs-lookup"><span data-stu-id="0c7fc-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="0c7fc-108">En funktion som transformerar den angivna ingången i ett formulär som förväntas av åtgärden.</span><span class="sxs-lookup"><span data-stu-id="0c7fc-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit-adj--ctl"></a><span data-ttu-id="0c7fc-109">OP: t => [enhet](xref:microsoft.quantum.lang-ref.unit) just + CTL</span><span class="sxs-lookup"><span data-stu-id="0c7fc-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="0c7fc-110">Åtgärden som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="0c7fc-110">The operation to be applied.</span></span>


### <a name="input--u"></a><span data-ttu-id="0c7fc-111">inmatade: ' U</span><span class="sxs-lookup"><span data-stu-id="0c7fc-111">input : 'U</span></span>

<span data-ttu-id="0c7fc-112">En indatamängd till funktionen.</span><span class="sxs-lookup"><span data-stu-id="0c7fc-112">An input to the function.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0c7fc-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0c7fc-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="0c7fc-114">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="0c7fc-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0c7fc-115">Inte</span><span class="sxs-lookup"><span data-stu-id="0c7fc-115">'T</span></span>


### <a name="u"></a><span data-ttu-id="0c7fc-116">' U</span><span class="sxs-lookup"><span data-stu-id="0c7fc-116">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="0c7fc-117">Se även</span><span class="sxs-lookup"><span data-stu-id="0c7fc-117">See Also</span></span>

- [<span data-ttu-id="0c7fc-118">Microsoft. Quantum. Canon. ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="0c7fc-118">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="0c7fc-119">Microsoft. Quantum. Canon. ApplyWithInputTransformationA</span><span class="sxs-lookup"><span data-stu-id="0c7fc-119">Microsoft.Quantum.Canon.ApplyWithInputTransformationA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationA)
- [<span data-ttu-id="0c7fc-120">Microsoft. Quantum. Canon. ApplyWithInputTransformationC</span><span class="sxs-lookup"><span data-stu-id="0c7fc-120">Microsoft.Quantum.Canon.ApplyWithInputTransformationC</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationC)
- [<span data-ttu-id="0c7fc-121">Microsoft. Quantum. Canon. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="0c7fc-121">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)