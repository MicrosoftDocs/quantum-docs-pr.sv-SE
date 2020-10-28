---
uid: Microsoft.Quantum.Convert.Call
title: Anrops åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: Call
qsharp.summary: Calls a function with a given input.
ms.openlocfilehash: 8630f846b4b9823ce1c1dfd61dc8ca81e468517d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727570"
---
# <a name="call-operation"></a><span data-ttu-id="1caf9-102">Anrops åtgärd</span><span class="sxs-lookup"><span data-stu-id="1caf9-102">Call operation</span></span>

<span data-ttu-id="1caf9-103">Namnrymd: [Microsoft. Quantum. convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="1caf9-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="1caf9-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1caf9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1caf9-105">Anropar en funktion med en specifik Indatatyp.</span><span class="sxs-lookup"><span data-stu-id="1caf9-105">Calls a function with a given input.</span></span>

```qsharp
operation Call<'Input, 'Output> (fn : ('Input -> 'Output), input : 'Input) : 'Output
```


## <a name="description"></a><span data-ttu-id="1caf9-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="1caf9-106">Description</span></span>

<span data-ttu-id="1caf9-107">Med en funktion och indata till funktionen anropar funktionen och returnerar dess utdata.</span><span class="sxs-lookup"><span data-stu-id="1caf9-107">Given a function and an input to that function, calls the function and returns its output.</span></span>

## <a name="input"></a><span data-ttu-id="1caf9-108">Indata</span><span class="sxs-lookup"><span data-stu-id="1caf9-108">Input</span></span>

### <a name="fn--input---output"></a><span data-ttu-id="1caf9-109">FN: "indata >"-utdata</span><span class="sxs-lookup"><span data-stu-id="1caf9-109">fn : 'Input -> 'Output</span></span>

<span data-ttu-id="1caf9-110">En funktion som ska anropas.</span><span class="sxs-lookup"><span data-stu-id="1caf9-110">A function to be called.</span></span>


### <a name="input--input"></a><span data-ttu-id="1caf9-111">inmatade: ' inmatare</span><span class="sxs-lookup"><span data-stu-id="1caf9-111">input : 'Input</span></span>

<span data-ttu-id="1caf9-112">Indatamängden som ska skickas till funktionen.</span><span class="sxs-lookup"><span data-stu-id="1caf9-112">The input to be passed to the function.</span></span>



## <a name="output--output"></a><span data-ttu-id="1caf9-113">Utdata: utdata</span><span class="sxs-lookup"><span data-stu-id="1caf9-113">Output : 'Output</span></span>

<span data-ttu-id="1caf9-114">Resultatet av anropet `fn` .</span><span class="sxs-lookup"><span data-stu-id="1caf9-114">The result of calling `fn`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="1caf9-115">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="1caf9-115">Type Parameters</span></span>

### <a name="input"></a><span data-ttu-id="1caf9-116">' Inmatare</span><span class="sxs-lookup"><span data-stu-id="1caf9-116">'Input</span></span>


### <a name="output"></a><span data-ttu-id="1caf9-117">' Utdata</span><span class="sxs-lookup"><span data-stu-id="1caf9-117">'Output</span></span>



## <a name="remarks"></a><span data-ttu-id="1caf9-118">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="1caf9-118">Remarks</span></span>

<span data-ttu-id="1caf9-119">Den här åtgärden är främst användbar för att tvinga en funktion att anropas på en viss plats i en åtgärd eller för att anropa en funktion där en åtgärd förväntas.</span><span class="sxs-lookup"><span data-stu-id="1caf9-119">This operation is mainly useful for forcing a function to be called at a specific place within an operation, or for calling a function where an operation is expected.</span></span>