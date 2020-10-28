---
uid: Microsoft.Quantum.Convert.FunctionAsOperation
title: Funktionen FunctionAsOperation
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: FunctionAsOperation
qsharp.summary: Converts functions to operations.
ms.openlocfilehash: 90e9f0c922a77fbb6d6faf8945d4f5d1c8ff33b7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727561"
---
# <a name="functionasoperation-function"></a><span data-ttu-id="9c5d2-102">Funktionen FunctionAsOperation</span><span class="sxs-lookup"><span data-stu-id="9c5d2-102">FunctionAsOperation function</span></span>

<span data-ttu-id="9c5d2-103">Namnrymd: [Microsoft. Quantum. convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="9c5d2-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="9c5d2-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9c5d2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9c5d2-105">Konverterar funktioner till åtgärder.</span><span class="sxs-lookup"><span data-stu-id="9c5d2-105">Converts functions to operations.</span></span>

```qsharp
function FunctionAsOperation<'Input, 'Output> (fn : ('Input -> 'Output)) : ('Input => 'Output)
```


## <a name="description"></a><span data-ttu-id="9c5d2-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="9c5d2-106">Description</span></span>

<span data-ttu-id="9c5d2-107">Med en funktion returnerar en åtgärd som anropar funktionen och som inte gör något annat.</span><span class="sxs-lookup"><span data-stu-id="9c5d2-107">Given a function, returns an operation which calls that function, and which does nothing else.</span></span>

## <a name="input"></a><span data-ttu-id="9c5d2-108">Indata</span><span class="sxs-lookup"><span data-stu-id="9c5d2-108">Input</span></span>

### <a name="fn--input---output"></a><span data-ttu-id="9c5d2-109">FN: "indata >"-utdata</span><span class="sxs-lookup"><span data-stu-id="9c5d2-109">fn : 'Input -> 'Output</span></span>

<span data-ttu-id="9c5d2-110">En funktion som ska konverteras till en åtgärd.</span><span class="sxs-lookup"><span data-stu-id="9c5d2-110">A function to be converted to an operation.</span></span>



## <a name="output--input--output"></a><span data-ttu-id="9c5d2-111">Output: ' indata => ' utdata</span><span class="sxs-lookup"><span data-stu-id="9c5d2-111">Output : 'Input => 'Output</span></span> 

<span data-ttu-id="9c5d2-112">En åtgärd `op` som `op(input)` är identisk med `fn(input)` för alla `input` .</span><span class="sxs-lookup"><span data-stu-id="9c5d2-112">An operation `op` such that `op(input)` is identical to `fn(input)` for all `input`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="9c5d2-113">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="9c5d2-113">Type Parameters</span></span>

### <a name="input"></a><span data-ttu-id="9c5d2-114">' Inmatare</span><span class="sxs-lookup"><span data-stu-id="9c5d2-114">'Input</span></span>

<span data-ttu-id="9c5d2-115">Indatatypen för funktionen som ska konverteras.</span><span class="sxs-lookup"><span data-stu-id="9c5d2-115">Input type of the function to be converted.</span></span>
### <a name="output"></a><span data-ttu-id="9c5d2-116">' Utdata</span><span class="sxs-lookup"><span data-stu-id="9c5d2-116">'Output</span></span>

<span data-ttu-id="9c5d2-117">Utdatatypen för funktionen som ska konverteras.</span><span class="sxs-lookup"><span data-stu-id="9c5d2-117">Output type of the function to be converted.</span></span>

## <a name="remarks"></a><span data-ttu-id="9c5d2-118">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="9c5d2-118">Remarks</span></span>

<span data-ttu-id="9c5d2-119">Detta är främst användbart för att skicka funktioner till Functions eller åtgärder som förväntar sig en åtgärd som indatamängd.</span><span class="sxs-lookup"><span data-stu-id="9c5d2-119">This is mainly useful for passing functions to functions or operations which expect an operation as input.</span></span>