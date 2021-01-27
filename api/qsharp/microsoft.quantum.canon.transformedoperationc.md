---
uid: Microsoft.Quantum.Canon.TransformedOperationC
title: Funktionen TransformedOperationC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperationC
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: 9475c5a1cc3b7e14c56c301749311a72e15f71e0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852032"
---
# <a name="transformedoperationc-function"></a><span data-ttu-id="7bba7-102">Funktionen TransformedOperationC</span><span class="sxs-lookup"><span data-stu-id="7bba7-102">TransformedOperationC function</span></span>

<span data-ttu-id="7bba7-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7bba7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7bba7-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7bba7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7bba7-105">Med en funktion och en åtgärd returnerar en ny åtgärd vars Indatatyp omvandlas av den angivna funktionen.</span><span class="sxs-lookup"><span data-stu-id="7bba7-105">Given a function and an operation, returns a new operation whose input is transformed by the given function.</span></span>

```qsharp
function TransformedOperationC<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Ctl)) : ('U => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="7bba7-106">Indata</span><span class="sxs-lookup"><span data-stu-id="7bba7-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="7bba7-107">FN: U-></span><span class="sxs-lookup"><span data-stu-id="7bba7-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="7bba7-108">En funktion som transformerar den angivna ingången i ett formulär som förväntas av åtgärden.</span><span class="sxs-lookup"><span data-stu-id="7bba7-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="7bba7-109">OP: t => [enheten](xref:microsoft.quantum.lang-ref.unit)  är CTL</span><span class="sxs-lookup"><span data-stu-id="7bba7-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="7bba7-110">Åtgärden som ska transformeras.</span><span class="sxs-lookup"><span data-stu-id="7bba7-110">The operation to be transformed.</span></span>



## <a name="output--u--unit--is-ctl"></a><span data-ttu-id="7bba7-111">Utdata: U => [enhet](xref:microsoft.quantum.lang-ref.unit)  är CTL</span><span class="sxs-lookup"><span data-stu-id="7bba7-111">Output : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="7bba7-112">En ny åtgärd tbat anropar `fn` sina indata och skickar sedan resultatet till `op` .</span><span class="sxs-lookup"><span data-stu-id="7bba7-112">A new operation tbat calls `fn` with its input, then passes the resulting output to `op`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="7bba7-113">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="7bba7-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7bba7-114">Inte</span><span class="sxs-lookup"><span data-stu-id="7bba7-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="7bba7-115">' U</span><span class="sxs-lookup"><span data-stu-id="7bba7-115">'U</span></span>



## <a name="example"></a><span data-ttu-id="7bba7-116">Exempel</span><span class="sxs-lookup"><span data-stu-id="7bba7-116">Example</span></span>

<span data-ttu-id="7bba7-117">Följande anrop använder @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" för att transformera en åtgärd som har utformats för @"Microsoft.Quantum.Arithmetic.BigEndian" indata till en åtgärd som accepterar indata av typen @"Microsoft.Quantum.Arithmetic.LittleEndian" :</span><span class="sxs-lookup"><span data-stu-id="7bba7-117">The following call uses @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" to transform an operation designed for @"Microsoft.Quantum.Arithmetic.BigEndian" inputs into an operation that accepts inputs of type @"Microsoft.Quantum.Arithmetic.LittleEndian":</span></span>

```qsharp
let leOp = TransformedOperation(LittleEndianAsBigEndian, ApplyXorInPlaceBE);
```

## <a name="see-also"></a><span data-ttu-id="7bba7-118">Se även</span><span class="sxs-lookup"><span data-stu-id="7bba7-118">See Also</span></span>

- [<span data-ttu-id="7bba7-119">Microsoft. Quantum. Canon. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="7bba7-119">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)
- [<span data-ttu-id="7bba7-120">Microsoft. Quantum. Canon. TransformedOperationA</span><span class="sxs-lookup"><span data-stu-id="7bba7-120">Microsoft.Quantum.Canon.TransformedOperationA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationA)
- [<span data-ttu-id="7bba7-121">Microsoft. Quantum. Canon. TransformedOperationCA</span><span class="sxs-lookup"><span data-stu-id="7bba7-121">Microsoft.Quantum.Canon.TransformedOperationCA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [<span data-ttu-id="7bba7-122">Microsoft. Quantum. Canon. ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="7bba7-122">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="7bba7-123">Microsoft. Quantum. Canon. sammansatt</span><span class="sxs-lookup"><span data-stu-id="7bba7-123">Microsoft.Quantum.Canon.Composed</span></span>](xref:Microsoft.Quantum.Canon.Composed)