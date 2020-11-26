---
uid: Microsoft.Quantum.Canon.TransformedOperationC
title: Funktionen TransformedOperationC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperationC
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: 964576788bc80dd8920acdfb62d5d69a060e75f6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204869"
---
# <a name="transformedoperationc-function"></a><span data-ttu-id="bb9e2-102">Funktionen TransformedOperationC</span><span class="sxs-lookup"><span data-stu-id="bb9e2-102">TransformedOperationC function</span></span>

<span data-ttu-id="bb9e2-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="bb9e2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="bb9e2-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bb9e2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bb9e2-105">Med en funktion och en åtgärd returnerar en ny åtgärd vars Indatatyp omvandlas av den angivna funktionen.</span><span class="sxs-lookup"><span data-stu-id="bb9e2-105">Given a function and an operation, returns a new operation whose input is transformed by the given function.</span></span>

```qsharp
function TransformedOperationC<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Ctl)) : ('U => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="bb9e2-106">Indata</span><span class="sxs-lookup"><span data-stu-id="bb9e2-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="bb9e2-107">FN: U-></span><span class="sxs-lookup"><span data-stu-id="bb9e2-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="bb9e2-108">En funktion som transformerar den angivna ingången i ett formulär som förväntas av åtgärden.</span><span class="sxs-lookup"><span data-stu-id="bb9e2-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="bb9e2-109">OP: t => [enheten](xref:microsoft.quantum.lang-ref.unit)  är CTL</span><span class="sxs-lookup"><span data-stu-id="bb9e2-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="bb9e2-110">Åtgärden som ska transformeras.</span><span class="sxs-lookup"><span data-stu-id="bb9e2-110">The operation to be transformed.</span></span>



## <a name="output--u--unit--is-ctl"></a><span data-ttu-id="bb9e2-111">Utdata: U => [enhet](xref:microsoft.quantum.lang-ref.unit)  är CTL</span><span class="sxs-lookup"><span data-stu-id="bb9e2-111">Output : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="bb9e2-112">En ny åtgärd tbat anropar `fn` sina indata och skickar sedan resultatet till `op` .</span><span class="sxs-lookup"><span data-stu-id="bb9e2-112">A new operation tbat calls `fn` with its input, then passes the resulting output to `op`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="bb9e2-113">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="bb9e2-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bb9e2-114">Inte</span><span class="sxs-lookup"><span data-stu-id="bb9e2-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="bb9e2-115">' U</span><span class="sxs-lookup"><span data-stu-id="bb9e2-115">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="bb9e2-116">Se även</span><span class="sxs-lookup"><span data-stu-id="bb9e2-116">See Also</span></span>

- [<span data-ttu-id="bb9e2-117">Microsoft. Quantum. Canon. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="bb9e2-117">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)
- [<span data-ttu-id="bb9e2-118">Microsoft. Quantum. Canon. TransformedOperationA</span><span class="sxs-lookup"><span data-stu-id="bb9e2-118">Microsoft.Quantum.Canon.TransformedOperationA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationA)
- [<span data-ttu-id="bb9e2-119">Microsoft. Quantum. Canon. TransformedOperationCA</span><span class="sxs-lookup"><span data-stu-id="bb9e2-119">Microsoft.Quantum.Canon.TransformedOperationCA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [<span data-ttu-id="bb9e2-120">Microsoft. Quantum. Canon. ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="bb9e2-120">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="bb9e2-121">Microsoft. Quantum. Canon. sammansatt</span><span class="sxs-lookup"><span data-stu-id="bb9e2-121">Microsoft.Quantum.Canon.Composed</span></span>](xref:Microsoft.Quantum.Canon.Composed)