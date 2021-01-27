---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformationA
title: ApplyWithInputTransformationA-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformationA
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: 3ab07f301f310e3ec380981bdb53201fc74bd289
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841129"
---
# <a name="applywithinputtransformationa-operation"></a><span data-ttu-id="a9780-102">ApplyWithInputTransformationA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="a9780-102">ApplyWithInputTransformationA operation</span></span>

<span data-ttu-id="a9780-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a9780-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a9780-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a9780-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a9780-105">Vid en åtgärd som accepterar vissa indata, en funktion som returnerar en utmatning som är kompatibel med den åtgärden och en indata till den funktionen, används åtgärden med funktionen för att transformera indata till ett formulär som förväntas av åtgärden.</span><span class="sxs-lookup"><span data-stu-id="a9780-105">Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.</span></span>

```qsharp
operation ApplyWithInputTransformationA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj), input : 'U) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="a9780-106">Indata</span><span class="sxs-lookup"><span data-stu-id="a9780-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="a9780-107">FN: U-></span><span class="sxs-lookup"><span data-stu-id="a9780-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="a9780-108">En funktion som transformerar den angivna ingången i ett formulär som förväntas av åtgärden.</span><span class="sxs-lookup"><span data-stu-id="a9780-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit--is-adj"></a><span data-ttu-id="a9780-109">OP: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just</span><span class="sxs-lookup"><span data-stu-id="a9780-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="a9780-110">Åtgärden som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="a9780-110">The operation to be applied.</span></span>


### <a name="input--u"></a><span data-ttu-id="a9780-111">inmatade: ' U</span><span class="sxs-lookup"><span data-stu-id="a9780-111">input : 'U</span></span>

<span data-ttu-id="a9780-112">En indatamängd till funktionen.</span><span class="sxs-lookup"><span data-stu-id="a9780-112">An input to the function.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a9780-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a9780-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="a9780-114">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="a9780-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a9780-115">Inte</span><span class="sxs-lookup"><span data-stu-id="a9780-115">'T</span></span>


### <a name="u"></a><span data-ttu-id="a9780-116">' U</span><span class="sxs-lookup"><span data-stu-id="a9780-116">'U</span></span>



## <a name="example"></a><span data-ttu-id="a9780-117">Exempel</span><span class="sxs-lookup"><span data-stu-id="a9780-117">Example</span></span>

<span data-ttu-id="a9780-118">Följande anrop använder @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" för att tillämpa en åtgärd som har utformats för @"Microsoft.Quantum.Arithmetic.BigEndian" indata till en indata av typen @"Microsoft.Quantum.Arithmetic.LittleEndian" :</span><span class="sxs-lookup"><span data-stu-id="a9780-118">The following call uses @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" to apply an operation designed for @"Microsoft.Quantum.Arithmetic.BigEndian" inputs to an input of type @"Microsoft.Quantum.Arithmetic.LittleEndian":</span></span>

```qsharp
ApplyWithInputTransformation(LittleEndianAsBigEndian, ApplyXorInPlaceBE, LittleEndian(qubits));
```

## <a name="see-also"></a><span data-ttu-id="a9780-119">Se även</span><span class="sxs-lookup"><span data-stu-id="a9780-119">See Also</span></span>

- [<span data-ttu-id="a9780-120">Microsoft. Quantum. Canon. ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="a9780-120">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="a9780-121">Microsoft. Quantum. Canon. ApplyWithInputTransformationC</span><span class="sxs-lookup"><span data-stu-id="a9780-121">Microsoft.Quantum.Canon.ApplyWithInputTransformationC</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationC)
- [<span data-ttu-id="a9780-122">Microsoft. Quantum. Canon. ApplyWithInputTransformationCA</span><span class="sxs-lookup"><span data-stu-id="a9780-122">Microsoft.Quantum.Canon.ApplyWithInputTransformationCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationCA)
- [<span data-ttu-id="a9780-123">Microsoft. Quantum. Canon. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="a9780-123">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)