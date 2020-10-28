---
uid: Microsoft.Quantum.Canon.TransformedOperation
title: Funktionen TransformedOperation
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperation
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: d8c2f52290ce89d0a8ff138ba25f6b2e5e0516d5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728344"
---
# <a name="transformedoperation-function"></a><span data-ttu-id="393a2-102">Funktionen TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="393a2-102">TransformedOperation function</span></span>

<span data-ttu-id="393a2-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="393a2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="393a2-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="393a2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="393a2-105">Med en funktion och en åtgärd returnerar en ny åtgärd vars Indatatyp omvandlas av den angivna funktionen.</span><span class="sxs-lookup"><span data-stu-id="393a2-105">Given a function and an operation, returns a new operation whose input is transformed by the given function.</span></span>

```qsharp
function TransformedOperation<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit)) : ('U => Unit)
```


## <a name="input"></a><span data-ttu-id="393a2-106">Indata</span><span class="sxs-lookup"><span data-stu-id="393a2-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="393a2-107">FN: U-></span><span class="sxs-lookup"><span data-stu-id="393a2-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="393a2-108">En funktion som transformerar den angivna ingången i ett formulär som förväntas av åtgärden.</span><span class="sxs-lookup"><span data-stu-id="393a2-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit"></a><span data-ttu-id="393a2-109">OP: t => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="393a2-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="393a2-110">Åtgärden som ska transformeras.</span><span class="sxs-lookup"><span data-stu-id="393a2-110">The operation to be transformed.</span></span>



## <a name="output--u--unit"></a><span data-ttu-id="393a2-111">Utdata: U => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="393a2-111">Output : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="393a2-112">En ny åtgärd tbat anropar `fn` sina indata och skickar sedan resultatet till `op` .</span><span class="sxs-lookup"><span data-stu-id="393a2-112">A new operation tbat calls `fn` with its input, then passes the resulting output to `op`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="393a2-113">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="393a2-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="393a2-114">Inte</span><span class="sxs-lookup"><span data-stu-id="393a2-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="393a2-115">' U</span><span class="sxs-lookup"><span data-stu-id="393a2-115">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="393a2-116">Se även</span><span class="sxs-lookup"><span data-stu-id="393a2-116">See Also</span></span>

- [<span data-ttu-id="393a2-117">Microsoft. Quantum. Canon. TransformedOperationA</span><span class="sxs-lookup"><span data-stu-id="393a2-117">Microsoft.Quantum.Canon.TransformedOperationA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationA)
- [<span data-ttu-id="393a2-118">Microsoft. Quantum. Canon. TransformedOperationC</span><span class="sxs-lookup"><span data-stu-id="393a2-118">Microsoft.Quantum.Canon.TransformedOperationC</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationC)
- [<span data-ttu-id="393a2-119">Microsoft. Quantum. Canon. TransformedOperationCA</span><span class="sxs-lookup"><span data-stu-id="393a2-119">Microsoft.Quantum.Canon.TransformedOperationCA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [<span data-ttu-id="393a2-120">Microsoft. Quantum. Canon. ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="393a2-120">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="393a2-121">Microsoft. Quantum. Canon. sammansatt</span><span class="sxs-lookup"><span data-stu-id="393a2-121">Microsoft.Quantum.Canon.Composed</span></span>](xref:Microsoft.Quantum.Canon.Composed)