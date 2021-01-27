---
uid: Microsoft.Quantum.Convert.FunctionAsOperation
title: Funktionen FunctionAsOperation
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: FunctionAsOperation
qsharp.summary: Converts functions to operations.
ms.openlocfilehash: cf4f8c97bf38b3a64eb952d0a502bc21c29c579c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98833827"
---
# <a name="functionasoperation-function"></a><span data-ttu-id="86430-102">Funktionen FunctionAsOperation</span><span class="sxs-lookup"><span data-stu-id="86430-102">FunctionAsOperation function</span></span>

<span data-ttu-id="86430-103">Namnrymd: [Microsoft. Quantum. convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="86430-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="86430-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="86430-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="86430-105">Konverterar funktioner till åtgärder.</span><span class="sxs-lookup"><span data-stu-id="86430-105">Converts functions to operations.</span></span>

```qsharp
function FunctionAsOperation<'Input, 'Output> (fn : ('Input -> 'Output)) : ('Input => 'Output)
```


## <a name="description"></a><span data-ttu-id="86430-106">Description</span><span class="sxs-lookup"><span data-stu-id="86430-106">Description</span></span>

<span data-ttu-id="86430-107">Med en funktion returnerar en åtgärd som anropar funktionen och som inte gör något annat.</span><span class="sxs-lookup"><span data-stu-id="86430-107">Given a function, returns an operation which calls that function, and which does nothing else.</span></span>

## <a name="input"></a><span data-ttu-id="86430-108">Indata</span><span class="sxs-lookup"><span data-stu-id="86430-108">Input</span></span>

### <a name="fn--input---output"></a><span data-ttu-id="86430-109">FN: "indata >"-utdata</span><span class="sxs-lookup"><span data-stu-id="86430-109">fn : 'Input -> 'Output</span></span>

<span data-ttu-id="86430-110">En funktion som ska konverteras till en åtgärd.</span><span class="sxs-lookup"><span data-stu-id="86430-110">A function to be converted to an operation.</span></span>



## <a name="output--input--output"></a><span data-ttu-id="86430-111">Output: ' indata => ' utdata</span><span class="sxs-lookup"><span data-stu-id="86430-111">Output : 'Input => 'Output</span></span> 

<span data-ttu-id="86430-112">En åtgärd `op` som `op(input)` är identisk med `fn(input)` för alla `input` .</span><span class="sxs-lookup"><span data-stu-id="86430-112">An operation `op` such that `op(input)` is identical to `fn(input)` for all `input`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="86430-113">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="86430-113">Type Parameters</span></span>

### <a name="input"></a><span data-ttu-id="86430-114">' Inmatare</span><span class="sxs-lookup"><span data-stu-id="86430-114">'Input</span></span>

<span data-ttu-id="86430-115">Indatatypen för funktionen som ska konverteras.</span><span class="sxs-lookup"><span data-stu-id="86430-115">Input type of the function to be converted.</span></span>
### <a name="output"></a><span data-ttu-id="86430-116">' Utdata</span><span class="sxs-lookup"><span data-stu-id="86430-116">'Output</span></span>

<span data-ttu-id="86430-117">Utdatatypen för funktionen som ska konverteras.</span><span class="sxs-lookup"><span data-stu-id="86430-117">Output type of the function to be converted.</span></span>

## <a name="remarks"></a><span data-ttu-id="86430-118">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="86430-118">Remarks</span></span>

<span data-ttu-id="86430-119">Detta är främst användbart för att skicka funktioner till Functions eller åtgärder som förväntar sig en åtgärd som indatamängd.</span><span class="sxs-lookup"><span data-stu-id="86430-119">This is mainly useful for passing functions to functions or operations which expect an operation as input.</span></span>