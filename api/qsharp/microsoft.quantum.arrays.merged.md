---
uid: Microsoft.Quantum.Arrays.Merged
title: Sammanfogad funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Merged
qsharp.summary: Given two sorted arrays, returns a single array containing the elements of both in sorted order. Used internally by merge sort.
ms.openlocfilehash: 262e7450188370212a7e2a57bf15e9f8ab162814
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845616"
---
# <a name="merged-function"></a><span data-ttu-id="52503-102">Sammanfogad funktion</span><span class="sxs-lookup"><span data-stu-id="52503-102">Merged function</span></span>

<span data-ttu-id="52503-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="52503-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="52503-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="52503-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="52503-105">Med två sorterade matriser returnerar en enskild matris som innehåller elementen i både i sorterad ordning.</span><span class="sxs-lookup"><span data-stu-id="52503-105">Given two sorted arrays, returns a single array containing the elements of both in sorted order.</span></span> <span data-ttu-id="52503-106">Används internt genom sammanslagnings sortering.</span><span class="sxs-lookup"><span data-stu-id="52503-106">Used internally by merge sort.</span></span>

```qsharp
function Merged<'T> (comparison : (('T, 'T) -> Bool), left : 'T[], right : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="52503-107">Indata</span><span class="sxs-lookup"><span data-stu-id="52503-107">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="52503-108">jämförelse: (t)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="52503-108">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>




### <a name="left--t"></a><span data-ttu-id="52503-109">vänster: ' ' []</span><span class="sxs-lookup"><span data-stu-id="52503-109">left : 'T[]</span></span>




### <a name="right--t"></a><span data-ttu-id="52503-110">höger: ' t ']</span><span class="sxs-lookup"><span data-stu-id="52503-110">right : 'T[]</span></span>





## <a name="output--t"></a><span data-ttu-id="52503-111">Utdata: ' t []</span><span class="sxs-lookup"><span data-stu-id="52503-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="52503-112">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="52503-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="52503-113">Inte</span><span class="sxs-lookup"><span data-stu-id="52503-113">'T</span></span>

