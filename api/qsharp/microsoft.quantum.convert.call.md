---
uid: Microsoft.Quantum.Convert.Call
title: Anrops åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: Call
qsharp.summary: Calls a function with a given input.
ms.openlocfilehash: 92c159cef878fb587b0ed514fd6660dd19527cab
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214219"
---
# <a name="call-operation"></a><span data-ttu-id="8a189-102">Anrops åtgärd</span><span class="sxs-lookup"><span data-stu-id="8a189-102">Call operation</span></span>

<span data-ttu-id="8a189-103">Namnrymd: [Microsoft. Quantum. convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="8a189-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="8a189-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8a189-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8a189-105">Anropar en funktion med en specifik Indatatyp.</span><span class="sxs-lookup"><span data-stu-id="8a189-105">Calls a function with a given input.</span></span>

```qsharp
operation Call<'Input, 'Output> (fn : ('Input -> 'Output), input : 'Input) : 'Output
```


## <a name="description"></a><span data-ttu-id="8a189-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="8a189-106">Description</span></span>

<span data-ttu-id="8a189-107">Med en funktion och indata till funktionen anropar funktionen och returnerar dess utdata.</span><span class="sxs-lookup"><span data-stu-id="8a189-107">Given a function and an input to that function, calls the function and returns its output.</span></span>

## <a name="input"></a><span data-ttu-id="8a189-108">Indata</span><span class="sxs-lookup"><span data-stu-id="8a189-108">Input</span></span>

### <a name="fn--input---output"></a><span data-ttu-id="8a189-109">FN: "indata >"-utdata</span><span class="sxs-lookup"><span data-stu-id="8a189-109">fn : 'Input -> 'Output</span></span>

<span data-ttu-id="8a189-110">En funktion som ska anropas.</span><span class="sxs-lookup"><span data-stu-id="8a189-110">A function to be called.</span></span>


### <a name="input--input"></a><span data-ttu-id="8a189-111">inmatade: ' inmatare</span><span class="sxs-lookup"><span data-stu-id="8a189-111">input : 'Input</span></span>

<span data-ttu-id="8a189-112">Indatamängden som ska skickas till funktionen.</span><span class="sxs-lookup"><span data-stu-id="8a189-112">The input to be passed to the function.</span></span>



## <a name="output--output"></a><span data-ttu-id="8a189-113">Utdata: utdata</span><span class="sxs-lookup"><span data-stu-id="8a189-113">Output : 'Output</span></span>

<span data-ttu-id="8a189-114">Resultatet av anropet `fn` .</span><span class="sxs-lookup"><span data-stu-id="8a189-114">The result of calling `fn`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="8a189-115">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="8a189-115">Type Parameters</span></span>

### <a name="input"></a><span data-ttu-id="8a189-116">' Inmatare</span><span class="sxs-lookup"><span data-stu-id="8a189-116">'Input</span></span>


### <a name="output"></a><span data-ttu-id="8a189-117">' Utdata</span><span class="sxs-lookup"><span data-stu-id="8a189-117">'Output</span></span>



## <a name="remarks"></a><span data-ttu-id="8a189-118">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="8a189-118">Remarks</span></span>

<span data-ttu-id="8a189-119">Den här åtgärden är främst användbar för att tvinga en funktion att anropas på en viss plats i en åtgärd eller för att anropa en funktion där en åtgärd förväntas.</span><span class="sxs-lookup"><span data-stu-id="8a189-119">This operation is mainly useful for forcing a function to be called at a specific place within an operation, or for calling a function where an operation is expected.</span></span>