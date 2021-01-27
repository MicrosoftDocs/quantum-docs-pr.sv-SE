---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformationCA
title: ApplyWithInputTransformationCA-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformationCA
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: b31ed1b3da0d5467588f4cb2e4368e68f0dbe9d5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841103"
---
# <a name="applywithinputtransformationca-operation"></a><span data-ttu-id="2cb44-102">ApplyWithInputTransformationCA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="2cb44-102">ApplyWithInputTransformationCA operation</span></span>

<span data-ttu-id="2cb44-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2cb44-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2cb44-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2cb44-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2cb44-105">Vid en åtgärd som accepterar vissa indata, en funktion som returnerar en utmatning som är kompatibel med den åtgärden och en indata till den funktionen, används åtgärden med funktionen för att transformera indata till ett formulär som förväntas av åtgärden.</span><span class="sxs-lookup"><span data-stu-id="2cb44-105">Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.</span></span>

```qsharp
operation ApplyWithInputTransformationCA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj + Ctl), input : 'U) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="2cb44-106">Indata</span><span class="sxs-lookup"><span data-stu-id="2cb44-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="2cb44-107">FN: U-></span><span class="sxs-lookup"><span data-stu-id="2cb44-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="2cb44-108">En funktion som transformerar den angivna ingången i ett formulär som förväntas av åtgärden.</span><span class="sxs-lookup"><span data-stu-id="2cb44-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="2cb44-109">OP: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL</span><span class="sxs-lookup"><span data-stu-id="2cb44-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="2cb44-110">Åtgärden som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="2cb44-110">The operation to be applied.</span></span>


### <a name="input--u"></a><span data-ttu-id="2cb44-111">inmatade: ' U</span><span class="sxs-lookup"><span data-stu-id="2cb44-111">input : 'U</span></span>

<span data-ttu-id="2cb44-112">En indatamängd till funktionen.</span><span class="sxs-lookup"><span data-stu-id="2cb44-112">An input to the function.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2cb44-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2cb44-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="2cb44-114">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="2cb44-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2cb44-115">Inte</span><span class="sxs-lookup"><span data-stu-id="2cb44-115">'T</span></span>


### <a name="u"></a><span data-ttu-id="2cb44-116">' U</span><span class="sxs-lookup"><span data-stu-id="2cb44-116">'U</span></span>



## <a name="example"></a><span data-ttu-id="2cb44-117">Exempel</span><span class="sxs-lookup"><span data-stu-id="2cb44-117">Example</span></span>

<span data-ttu-id="2cb44-118">Följande anrop använder @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" för att tillämpa en åtgärd som har utformats för @"Microsoft.Quantum.Arithmetic.BigEndian" indata till en indata av typen @"Microsoft.Quantum.Arithmetic.LittleEndian" :</span><span class="sxs-lookup"><span data-stu-id="2cb44-118">The following call uses @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" to apply an operation designed for @"Microsoft.Quantum.Arithmetic.BigEndian" inputs to an input of type @"Microsoft.Quantum.Arithmetic.LittleEndian":</span></span>

```qsharp
ApplyWithInputTransformation(LittleEndianAsBigEndian, ApplyXorInPlaceBE, LittleEndian(qubits));
```

## <a name="see-also"></a><span data-ttu-id="2cb44-119">Se även</span><span class="sxs-lookup"><span data-stu-id="2cb44-119">See Also</span></span>

- [<span data-ttu-id="2cb44-120">Microsoft. Quantum. Canon. ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="2cb44-120">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="2cb44-121">Microsoft. Quantum. Canon. ApplyWithInputTransformationA</span><span class="sxs-lookup"><span data-stu-id="2cb44-121">Microsoft.Quantum.Canon.ApplyWithInputTransformationA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationA)
- [<span data-ttu-id="2cb44-122">Microsoft. Quantum. Canon. ApplyWithInputTransformationC</span><span class="sxs-lookup"><span data-stu-id="2cb44-122">Microsoft.Quantum.Canon.ApplyWithInputTransformationC</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationC)
- [<span data-ttu-id="2cb44-123">Microsoft. Quantum. Canon. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="2cb44-123">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)