---
uid: Microsoft.Quantum.Convert.Call
title: Anrops åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: Call
qsharp.summary: Calls a function with a given input.
ms.openlocfilehash: 93458d08aa83ffa8b7b33de8bf51c970af291db9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850201"
---
# <a name="call-operation"></a><span data-ttu-id="4c51c-102">Anrops åtgärd</span><span class="sxs-lookup"><span data-stu-id="4c51c-102">Call operation</span></span>

<span data-ttu-id="4c51c-103">Namnrymd: [Microsoft. Quantum. convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="4c51c-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="4c51c-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4c51c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4c51c-105">Anropar en funktion med en specifik Indatatyp.</span><span class="sxs-lookup"><span data-stu-id="4c51c-105">Calls a function with a given input.</span></span>

```qsharp
operation Call<'Input, 'Output> (fn : ('Input -> 'Output), input : 'Input) : 'Output
```


## <a name="description"></a><span data-ttu-id="4c51c-106">Description</span><span class="sxs-lookup"><span data-stu-id="4c51c-106">Description</span></span>

<span data-ttu-id="4c51c-107">Med en funktion och indata till funktionen anropar funktionen och returnerar dess utdata.</span><span class="sxs-lookup"><span data-stu-id="4c51c-107">Given a function and an input to that function, calls the function and returns its output.</span></span>

## <a name="input"></a><span data-ttu-id="4c51c-108">Indata</span><span class="sxs-lookup"><span data-stu-id="4c51c-108">Input</span></span>

### <a name="fn--input---output"></a><span data-ttu-id="4c51c-109">FN: "indata >"-utdata</span><span class="sxs-lookup"><span data-stu-id="4c51c-109">fn : 'Input -> 'Output</span></span>

<span data-ttu-id="4c51c-110">En funktion som ska anropas.</span><span class="sxs-lookup"><span data-stu-id="4c51c-110">A function to be called.</span></span>


### <a name="input--input"></a><span data-ttu-id="4c51c-111">inmatade: ' inmatare</span><span class="sxs-lookup"><span data-stu-id="4c51c-111">input : 'Input</span></span>

<span data-ttu-id="4c51c-112">Indatamängden som ska skickas till funktionen.</span><span class="sxs-lookup"><span data-stu-id="4c51c-112">The input to be passed to the function.</span></span>



## <a name="output--output"></a><span data-ttu-id="4c51c-113">Utdata: utdata</span><span class="sxs-lookup"><span data-stu-id="4c51c-113">Output : 'Output</span></span>

<span data-ttu-id="4c51c-114">Resultatet av anropet `fn` .</span><span class="sxs-lookup"><span data-stu-id="4c51c-114">The result of calling `fn`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="4c51c-115">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="4c51c-115">Type Parameters</span></span>

### <a name="input"></a><span data-ttu-id="4c51c-116">' Inmatare</span><span class="sxs-lookup"><span data-stu-id="4c51c-116">'Input</span></span>


### <a name="output"></a><span data-ttu-id="4c51c-117">' Utdata</span><span class="sxs-lookup"><span data-stu-id="4c51c-117">'Output</span></span>



## <a name="remarks"></a><span data-ttu-id="4c51c-118">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="4c51c-118">Remarks</span></span>

<span data-ttu-id="4c51c-119">Den här åtgärden är främst användbar för att tvinga en funktion att anropas på en viss plats i en åtgärd eller för att anropa en funktion där en åtgärd förväntas.</span><span class="sxs-lookup"><span data-stu-id="4c51c-119">This operation is mainly useful for forcing a function to be called at a specific place within an operation, or for calling a function where an operation is expected.</span></span>