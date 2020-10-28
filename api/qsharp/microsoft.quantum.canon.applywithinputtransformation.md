---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformation
title: ApplyWithInputTransformation-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformation
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: 2b7863337ef724d9c3ba10201a9a01d0b2226ea8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728998"
---
# <a name="applywithinputtransformation-operation"></a><span data-ttu-id="c6f4b-102">ApplyWithInputTransformation-åtgärd</span><span class="sxs-lookup"><span data-stu-id="c6f4b-102">ApplyWithInputTransformation operation</span></span>

<span data-ttu-id="c6f4b-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c6f4b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c6f4b-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c6f4b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c6f4b-105">Vid en åtgärd som accepterar vissa indata, en funktion som returnerar en utmatning som är kompatibel med den åtgärden och en indata till den funktionen, används åtgärden med funktionen för att transformera indata till ett formulär som förväntas av åtgärden.</span><span class="sxs-lookup"><span data-stu-id="c6f4b-105">Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.</span></span>

```qsharp
operation ApplyWithInputTransformation<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit), input : 'U) : Unit
```


## <a name="input"></a><span data-ttu-id="c6f4b-106">Indata</span><span class="sxs-lookup"><span data-stu-id="c6f4b-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="c6f4b-107">FN: U-></span><span class="sxs-lookup"><span data-stu-id="c6f4b-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="c6f4b-108">En funktion som transformerar den angivna ingången i ett formulär som förväntas av åtgärden.</span><span class="sxs-lookup"><span data-stu-id="c6f4b-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit"></a><span data-ttu-id="c6f4b-109">OP: t => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c6f4b-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="c6f4b-110">Åtgärden som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="c6f4b-110">The operation to be applied.</span></span>


### <a name="input--u"></a><span data-ttu-id="c6f4b-111">inmatade: ' U</span><span class="sxs-lookup"><span data-stu-id="c6f4b-111">input : 'U</span></span>

<span data-ttu-id="c6f4b-112">En indatamängd till funktionen.</span><span class="sxs-lookup"><span data-stu-id="c6f4b-112">An input to the function.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c6f4b-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c6f4b-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c6f4b-114">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="c6f4b-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c6f4b-115">Inte</span><span class="sxs-lookup"><span data-stu-id="c6f4b-115">'T</span></span>


### <a name="u"></a><span data-ttu-id="c6f4b-116">' U</span><span class="sxs-lookup"><span data-stu-id="c6f4b-116">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="c6f4b-117">Se även</span><span class="sxs-lookup"><span data-stu-id="c6f4b-117">See Also</span></span>

- [<span data-ttu-id="c6f4b-118">Microsoft. Quantum. Canon. ApplyWithInputTransformationA</span><span class="sxs-lookup"><span data-stu-id="c6f4b-118">Microsoft.Quantum.Canon.ApplyWithInputTransformationA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationA)
- [<span data-ttu-id="c6f4b-119">Microsoft. Quantum. Canon. ApplyWithInputTransformationC</span><span class="sxs-lookup"><span data-stu-id="c6f4b-119">Microsoft.Quantum.Canon.ApplyWithInputTransformationC</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationC)
- [<span data-ttu-id="c6f4b-120">Microsoft. Quantum. Canon. ApplyWithInputTransformationCA</span><span class="sxs-lookup"><span data-stu-id="c6f4b-120">Microsoft.Quantum.Canon.ApplyWithInputTransformationCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationCA)
- [<span data-ttu-id="c6f4b-121">Microsoft. Quantum. Canon. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="c6f4b-121">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)