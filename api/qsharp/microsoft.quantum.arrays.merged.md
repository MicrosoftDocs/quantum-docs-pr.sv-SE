---
uid: Microsoft.Quantum.Arrays.Merged
title: Sammanfogad funktion
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Merged
qsharp.summary: Given two sorted arrays, returns a single array containing the elements of both in sorted order. Used internally by merge sort.
ms.openlocfilehash: b3383f8a04e6fa23562aa81e5b911d06752f4fb5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220645"
---
# <a name="merged-function"></a><span data-ttu-id="33843-102">Sammanfogad funktion</span><span class="sxs-lookup"><span data-stu-id="33843-102">Merged function</span></span>

<span data-ttu-id="33843-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="33843-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="33843-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="33843-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="33843-105">Med två sorterade matriser returnerar en enskild matris som innehåller elementen i både i sorterad ordning.</span><span class="sxs-lookup"><span data-stu-id="33843-105">Given two sorted arrays, returns a single array containing the elements of both in sorted order.</span></span> <span data-ttu-id="33843-106">Används internt genom sammanslagnings sortering.</span><span class="sxs-lookup"><span data-stu-id="33843-106">Used internally by merge sort.</span></span>

```qsharp
function Merged<'T> (comparison : (('T, 'T) -> Bool), left : 'T[], right : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="33843-107">Indata</span><span class="sxs-lookup"><span data-stu-id="33843-107">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="33843-108">jämförelse: (t)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="33843-108">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>




### <a name="left--t"></a><span data-ttu-id="33843-109">vänster: ' ' []</span><span class="sxs-lookup"><span data-stu-id="33843-109">left : 'T[]</span></span>




### <a name="right--t"></a><span data-ttu-id="33843-110">höger: ' t ']</span><span class="sxs-lookup"><span data-stu-id="33843-110">right : 'T[]</span></span>





## <a name="output--t"></a><span data-ttu-id="33843-111">Utdata: ' t []</span><span class="sxs-lookup"><span data-stu-id="33843-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="33843-112">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="33843-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="33843-113">Inte</span><span class="sxs-lookup"><span data-stu-id="33843-113">'T</span></span>

