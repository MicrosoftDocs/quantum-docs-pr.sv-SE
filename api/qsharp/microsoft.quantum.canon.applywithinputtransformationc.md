---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformationC
title: ApplyWithInputTransformationC-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformationC
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: f166880d3ca8a7fc45635c0105aa5c83fe1b4f4a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728989"
---
# <a name="applywithinputtransformationc-operation"></a><span data-ttu-id="8e594-102">ApplyWithInputTransformationC-åtgärd</span><span class="sxs-lookup"><span data-stu-id="8e594-102">ApplyWithInputTransformationC operation</span></span>

<span data-ttu-id="8e594-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8e594-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8e594-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8e594-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8e594-105">Vid en åtgärd som accepterar vissa indata, en funktion som returnerar en utmatning som är kompatibel med den åtgärden och en indata till den funktionen, används åtgärden med funktionen för att transformera indata till ett formulär som förväntas av åtgärden.</span><span class="sxs-lookup"><span data-stu-id="8e594-105">Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.</span></span>

```qsharp
operation ApplyWithInputTransformationC<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Ctl), input : 'U) : Unit
```


## <a name="input"></a><span data-ttu-id="8e594-106">Indata</span><span class="sxs-lookup"><span data-stu-id="8e594-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="8e594-107">FN: U-></span><span class="sxs-lookup"><span data-stu-id="8e594-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="8e594-108">En funktion som transformerar den angivna ingången i ett formulär som förväntas av åtgärden.</span><span class="sxs-lookup"><span data-stu-id="8e594-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit-ctl"></a><span data-ttu-id="8e594-109">OP: t => [enhet](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="8e594-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="8e594-110">Åtgärden som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="8e594-110">The operation to be applied.</span></span>


### <a name="input--u"></a><span data-ttu-id="8e594-111">inmatade: ' U</span><span class="sxs-lookup"><span data-stu-id="8e594-111">input : 'U</span></span>

<span data-ttu-id="8e594-112">En indatamängd till funktionen.</span><span class="sxs-lookup"><span data-stu-id="8e594-112">An input to the function.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8e594-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8e594-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="8e594-114">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="8e594-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8e594-115">Inte</span><span class="sxs-lookup"><span data-stu-id="8e594-115">'T</span></span>


### <a name="u"></a><span data-ttu-id="8e594-116">' U</span><span class="sxs-lookup"><span data-stu-id="8e594-116">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="8e594-117">Se även</span><span class="sxs-lookup"><span data-stu-id="8e594-117">See Also</span></span>

- [<span data-ttu-id="8e594-118">Microsoft. Quantum. Canon. ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="8e594-118">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="8e594-119">Microsoft. Quantum. Canon. ApplyWithInputTransformationA</span><span class="sxs-lookup"><span data-stu-id="8e594-119">Microsoft.Quantum.Canon.ApplyWithInputTransformationA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationA)
- [<span data-ttu-id="8e594-120">Microsoft. Quantum. Canon. ApplyWithInputTransformationCA</span><span class="sxs-lookup"><span data-stu-id="8e594-120">Microsoft.Quantum.Canon.ApplyWithInputTransformationCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationCA)
- [<span data-ttu-id="8e594-121">Microsoft. Quantum. Canon. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="8e594-121">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)