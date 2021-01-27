---
uid: Microsoft.Quantum.Arrays.IndexOf
title: Funktionen IndexOf
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexOf
qsharp.summary: Returns the first index of the first element in an array that satisfies a given predicate. If no such element exists, returns -1.
ms.openlocfilehash: 64db55e831078a7130a3ced6a30bfbd2299c392d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848513"
---
# <a name="indexof-function"></a><span data-ttu-id="59a4a-102">Funktionen IndexOf</span><span class="sxs-lookup"><span data-stu-id="59a4a-102">IndexOf function</span></span>

<span data-ttu-id="59a4a-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="59a4a-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="59a4a-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="59a4a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="59a4a-105">Returnerar det första indexet för det första elementet i en matris som uppfyller ett angivet predikat.</span><span class="sxs-lookup"><span data-stu-id="59a4a-105">Returns the first index of the first element in an array that satisfies a given predicate.</span></span> <span data-ttu-id="59a4a-106">Returnerar-1 om det inte finns något sådant element.</span><span class="sxs-lookup"><span data-stu-id="59a4a-106">If no such element exists, returns -1.</span></span>

```qsharp
function IndexOf<'T> (predicate : ('T -> Bool), arr : 'T[]) : Int
```


## <a name="input"></a><span data-ttu-id="59a4a-107">Indata</span><span class="sxs-lookup"><span data-stu-id="59a4a-107">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="59a4a-108">predikat: ' t-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="59a4a-108">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="59a4a-109">En predika funktion som fungerar på element i matrisen.</span><span class="sxs-lookup"><span data-stu-id="59a4a-109">A predicate function acting on elements of the array.</span></span>


### <a name="arr--t"></a><span data-ttu-id="59a4a-110">arr: ' t []</span><span class="sxs-lookup"><span data-stu-id="59a4a-110">arr : 'T[]</span></span>

<span data-ttu-id="59a4a-111">En matris som ska genomsökas med det aktuella predikatet.</span><span class="sxs-lookup"><span data-stu-id="59a4a-111">An array to be searched using the given predicate.</span></span>



## <a name="output--int"></a><span data-ttu-id="59a4a-112">Utdata: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="59a4a-112">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="59a4a-113">Antingen det minsta indexet `idx` som `predicate(arr[idx])` är sant eller-1 om det inte finns något sådant element.</span><span class="sxs-lookup"><span data-stu-id="59a4a-113">Either the smallest index `idx` such that `predicate(arr[idx])` is true, or -1 if no such element exists.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="59a4a-114">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="59a4a-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="59a4a-115">Inte</span><span class="sxs-lookup"><span data-stu-id="59a4a-115">'T</span></span>



## <a name="example"></a><span data-ttu-id="59a4a-116">Exempel</span><span class="sxs-lookup"><span data-stu-id="59a4a-116">Example</span></span>

<span data-ttu-id="59a4a-117">Anta att `IsEven : Int -> Bool` är en funktion som returnerar `true` om och bara om indatatypen är till och med.</span><span class="sxs-lookup"><span data-stu-id="59a4a-117">Suppose that `IsEven : Int -> Bool` is a function that returns `true` if and only if its input is even.</span></span> <span data-ttu-id="59a4a-118">Sedan kan du använda `IndexOf` för att hitta det första elementet till och med en matris:</span><span class="sxs-lookup"><span data-stu-id="59a4a-118">Then, this can be used with `IndexOf` to find the first even element in an array:</span></span>

```qsharp
let items = [1, 3, 17, 2, 21];
let idx = IndexOf(IsEven, items); // returns 3
```