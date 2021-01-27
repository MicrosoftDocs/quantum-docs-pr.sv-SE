---
uid: Microsoft.Quantum.Synthesis.IntegerBits
title: Funktionen IntegerBits
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: IntegerBits
qsharp.summary: Returns all positions in which bits of an integer are set.
ms.openlocfilehash: 3352c1b3003ee387fb03b72461fedb400e29046d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855406"
---
# <a name="integerbits-function"></a><span data-ttu-id="2f03a-102">Funktionen IntegerBits</span><span class="sxs-lookup"><span data-stu-id="2f03a-102">IntegerBits function</span></span>

<span data-ttu-id="2f03a-103">Namnrymd: [Microsoft. Quantum. syntes](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="2f03a-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="2f03a-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2f03a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2f03a-105">Returnerar alla positioner där bitar av ett heltal anges.</span><span class="sxs-lookup"><span data-stu-id="2f03a-105">Returns all positions in which bits of an integer are set.</span></span>

```qsharp
function IntegerBits (value : Int, length : Int) : Int[]
```


## <a name="input"></a><span data-ttu-id="2f03a-106">Indata</span><span class="sxs-lookup"><span data-stu-id="2f03a-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="2f03a-107">värde: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2f03a-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2f03a-108">Ett icke-negativt tal.</span><span class="sxs-lookup"><span data-stu-id="2f03a-108">A nonnegative number.</span></span>


### <a name="length--int"></a><span data-ttu-id="2f03a-109">Längd: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2f03a-109">length : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2f03a-110">Antalet bitar i den binära expanderingen av `value` .</span><span class="sxs-lookup"><span data-stu-id="2f03a-110">The number of bits in the binary expansion of `value`.</span></span>



## <a name="output--int"></a><span data-ttu-id="2f03a-111">Utdata: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="2f03a-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="2f03a-112">En matris som innehåller alla bit positioner (från 0) som är 1 i den binära expanderingen av `value` alla bitar upp till positionen `length - 1` .</span><span class="sxs-lookup"><span data-stu-id="2f03a-112">An array containing all bit positions (starting from 0) that are 1 in the binary expansion of `value` considering all bits up to position `length - 1`.</span></span>  <span data-ttu-id="2f03a-113">Alla positioner sorteras i matrisen efter position i ökande ordning.</span><span class="sxs-lookup"><span data-stu-id="2f03a-113">All positions are ordered in the array by position in an increasing order.</span></span>

## <a name="example"></a><span data-ttu-id="2f03a-114">Exempel</span><span class="sxs-lookup"><span data-stu-id="2f03a-114">Example</span></span>

```qsharp
IntegerBits(23, 5); // [0, 1, 2, 4]
IntegerBits(10, 4); // [1, 3]
```