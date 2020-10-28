---
uid: Microsoft.Quantum.Synthesis.IntegerBits
title: Funktionen IntegerBits
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: IntegerBits
qsharp.summary: Returns all positions in which bits of an integer are set.
ms.openlocfilehash: ab459cd841cdac116cf0e98c094834f628b6a2d3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730667"
---
# <a name="integerbits-function"></a><span data-ttu-id="affb3-102">Funktionen IntegerBits</span><span class="sxs-lookup"><span data-stu-id="affb3-102">IntegerBits function</span></span>

<span data-ttu-id="affb3-103">Namnrymd: [Microsoft. Quantum. syntes](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="affb3-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="affb3-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="affb3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="affb3-105">Returnerar alla positioner där bitar av ett heltal anges.</span><span class="sxs-lookup"><span data-stu-id="affb3-105">Returns all positions in which bits of an integer are set.</span></span>

```qsharp
function IntegerBits (value : Int, length : Int) : Int[]
```


## <a name="input"></a><span data-ttu-id="affb3-106">Indata</span><span class="sxs-lookup"><span data-stu-id="affb3-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="affb3-107">värde: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="affb3-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="affb3-108">Ett icke-negativt tal.</span><span class="sxs-lookup"><span data-stu-id="affb3-108">A nonnegative number.</span></span>


### <a name="length--int"></a><span data-ttu-id="affb3-109">Längd: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="affb3-109">length : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="affb3-110">Antalet bitar i den binära expanderingen av `value` .</span><span class="sxs-lookup"><span data-stu-id="affb3-110">The number of bits in the binary expansion of `value`.</span></span>



## <a name="output--int"></a><span data-ttu-id="affb3-111">Utdata: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="affb3-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="affb3-112">En matris som innehåller alla bit positioner (från 0) som är 1 i den binära expanderingen av `value` alla bitar upp till positionen `length - 1` .</span><span class="sxs-lookup"><span data-stu-id="affb3-112">An array containing all bit positions (starting from 0) that are 1 in the binary expansion of `value` considering all bits up to position `length - 1`.</span></span>  <span data-ttu-id="affb3-113">Alla positioner sorteras i matrisen efter position i ökande ordning.</span><span class="sxs-lookup"><span data-stu-id="affb3-113">All positions are ordered in the array by position in an increasing order.</span></span>