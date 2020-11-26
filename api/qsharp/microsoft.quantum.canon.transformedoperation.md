---
uid: Microsoft.Quantum.Canon.TransformedOperation
title: Funktionen TransformedOperation
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperation
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: a26cc178f67fd99324355ac230d9e91081b6e238
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204937"
---
# <a name="transformedoperation-function"></a><span data-ttu-id="39fd0-102">Funktionen TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="39fd0-102">TransformedOperation function</span></span>

<span data-ttu-id="39fd0-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="39fd0-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="39fd0-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="39fd0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="39fd0-105">Med en funktion och en åtgärd returnerar en ny åtgärd vars Indatatyp omvandlas av den angivna funktionen.</span><span class="sxs-lookup"><span data-stu-id="39fd0-105">Given a function and an operation, returns a new operation whose input is transformed by the given function.</span></span>

```qsharp
function TransformedOperation<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit)) : ('U => Unit)
```


## <a name="input"></a><span data-ttu-id="39fd0-106">Indata</span><span class="sxs-lookup"><span data-stu-id="39fd0-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="39fd0-107">FN: U-></span><span class="sxs-lookup"><span data-stu-id="39fd0-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="39fd0-108">En funktion som transformerar den angivna ingången i ett formulär som förväntas av åtgärden.</span><span class="sxs-lookup"><span data-stu-id="39fd0-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit"></a><span data-ttu-id="39fd0-109">OP: t => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="39fd0-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="39fd0-110">Åtgärden som ska transformeras.</span><span class="sxs-lookup"><span data-stu-id="39fd0-110">The operation to be transformed.</span></span>



## <a name="output--u--unit"></a><span data-ttu-id="39fd0-111">Utdata: U => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="39fd0-111">Output : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="39fd0-112">En ny åtgärd tbat anropar `fn` sina indata och skickar sedan resultatet till `op` .</span><span class="sxs-lookup"><span data-stu-id="39fd0-112">A new operation tbat calls `fn` with its input, then passes the resulting output to `op`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="39fd0-113">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="39fd0-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="39fd0-114">Inte</span><span class="sxs-lookup"><span data-stu-id="39fd0-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="39fd0-115">' U</span><span class="sxs-lookup"><span data-stu-id="39fd0-115">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="39fd0-116">Se även</span><span class="sxs-lookup"><span data-stu-id="39fd0-116">See Also</span></span>

- [<span data-ttu-id="39fd0-117">Microsoft. Quantum. Canon. TransformedOperationA</span><span class="sxs-lookup"><span data-stu-id="39fd0-117">Microsoft.Quantum.Canon.TransformedOperationA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationA)
- [<span data-ttu-id="39fd0-118">Microsoft. Quantum. Canon. TransformedOperationC</span><span class="sxs-lookup"><span data-stu-id="39fd0-118">Microsoft.Quantum.Canon.TransformedOperationC</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationC)
- [<span data-ttu-id="39fd0-119">Microsoft. Quantum. Canon. TransformedOperationCA</span><span class="sxs-lookup"><span data-stu-id="39fd0-119">Microsoft.Quantum.Canon.TransformedOperationCA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [<span data-ttu-id="39fd0-120">Microsoft. Quantum. Canon. ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="39fd0-120">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="39fd0-121">Microsoft. Quantum. Canon. sammansatt</span><span class="sxs-lookup"><span data-stu-id="39fd0-121">Microsoft.Quantum.Canon.Composed</span></span>](xref:Microsoft.Quantum.Canon.Composed)