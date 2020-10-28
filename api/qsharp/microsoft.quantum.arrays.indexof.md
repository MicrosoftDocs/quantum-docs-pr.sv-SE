---
uid: Microsoft.Quantum.Arrays.IndexOf
title: Funktionen IndexOf
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexOf
qsharp.summary: Returns the first index of the first element in an array that satisfies a given predicate. If no such element exists, returns -1.
ms.openlocfilehash: 7ff80f13f432a18f216b2dee4bd65b1e82034fa5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730219"
---
# <a name="indexof-function"></a><span data-ttu-id="20bad-102">Funktionen IndexOf</span><span class="sxs-lookup"><span data-stu-id="20bad-102">IndexOf function</span></span>

<span data-ttu-id="20bad-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="20bad-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="20bad-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="20bad-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="20bad-105">Returnerar det första indexet för det första elementet i en matris som uppfyller ett angivet predikat.</span><span class="sxs-lookup"><span data-stu-id="20bad-105">Returns the first index of the first element in an array that satisfies a given predicate.</span></span> <span data-ttu-id="20bad-106">Returnerar-1 om det inte finns något sådant element.</span><span class="sxs-lookup"><span data-stu-id="20bad-106">If no such element exists, returns -1.</span></span>

```qsharp
function IndexOf<'T> (predicate : ('T -> Bool), arr : 'T[]) : Int
```


## <a name="input"></a><span data-ttu-id="20bad-107">Indata</span><span class="sxs-lookup"><span data-stu-id="20bad-107">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="20bad-108">predikat: ' t-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="20bad-108">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="20bad-109">En predika funktion som fungerar på element i matrisen.</span><span class="sxs-lookup"><span data-stu-id="20bad-109">A predicate function acting on elements of the array.</span></span>


### <a name="arr--t"></a><span data-ttu-id="20bad-110">arr: ' t []</span><span class="sxs-lookup"><span data-stu-id="20bad-110">arr : 'T[]</span></span>

<span data-ttu-id="20bad-111">En matris som ska genomsökas med det aktuella predikatet.</span><span class="sxs-lookup"><span data-stu-id="20bad-111">An array to be searched using the given predicate.</span></span>



## <a name="output--int"></a><span data-ttu-id="20bad-112">Utdata: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="20bad-112">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="20bad-113">Antingen det minsta indexet `idx` som `predicate(arr[idx])` är sant eller-1 om det inte finns något sådant element.</span><span class="sxs-lookup"><span data-stu-id="20bad-113">Either the smallest index `idx` such that `predicate(arr[idx])` is true, or -1 if no such element exists.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="20bad-114">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="20bad-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="20bad-115">Inte</span><span class="sxs-lookup"><span data-stu-id="20bad-115">'T</span></span>

