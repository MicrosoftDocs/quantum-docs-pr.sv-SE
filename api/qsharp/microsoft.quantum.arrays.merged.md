---
uid: Microsoft.Quantum.Arrays.Merged
title: Sammanfogad funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Merged
qsharp.summary: Given two sorted arrays, returns a single array containing the elements of both in sorted order. Used internally by merge sort.
ms.openlocfilehash: da15a36f8f057cdc15062c96070ec21becc4794a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730110"
---
# <a name="merged-function"></a><span data-ttu-id="e8272-102">Sammanfogad funktion</span><span class="sxs-lookup"><span data-stu-id="e8272-102">Merged function</span></span>

<span data-ttu-id="e8272-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="e8272-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="e8272-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e8272-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e8272-105">Med två sorterade matriser returnerar en enskild matris som innehåller elementen i både i sorterad ordning.</span><span class="sxs-lookup"><span data-stu-id="e8272-105">Given two sorted arrays, returns a single array containing the elements of both in sorted order.</span></span> <span data-ttu-id="e8272-106">Används internt genom sammanslagnings sortering.</span><span class="sxs-lookup"><span data-stu-id="e8272-106">Used internally by merge sort.</span></span>

```qsharp
function Merged<'T> (comparison : (('T, 'T) -> Bool), left : 'T[], right : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="e8272-107">Indata</span><span class="sxs-lookup"><span data-stu-id="e8272-107">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="e8272-108">jämförelse: (t)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e8272-108">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>




### <a name="left--t"></a><span data-ttu-id="e8272-109">vänster: ' ' []</span><span class="sxs-lookup"><span data-stu-id="e8272-109">left : 'T[]</span></span>




### <a name="right--t"></a><span data-ttu-id="e8272-110">höger: ' t ']</span><span class="sxs-lookup"><span data-stu-id="e8272-110">right : 'T[]</span></span>





## <a name="output--t"></a><span data-ttu-id="e8272-111">Utdata: ' t []</span><span class="sxs-lookup"><span data-stu-id="e8272-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="e8272-112">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="e8272-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e8272-113">Inte</span><span class="sxs-lookup"><span data-stu-id="e8272-113">'T</span></span>

