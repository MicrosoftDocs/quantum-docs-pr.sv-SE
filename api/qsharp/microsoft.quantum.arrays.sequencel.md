---
uid: Microsoft.Quantum.Arrays.SequenceL
title: Funktionen Sequence
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceL
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: 3e5c7f64825f09d82792d3e46fe3f53f5814510b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220271"
---
# <a name="sequencel-function"></a><span data-ttu-id="3585a-102">Funktionen Sequence</span><span class="sxs-lookup"><span data-stu-id="3585a-102">SequenceL function</span></span>

<span data-ttu-id="3585a-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="3585a-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="3585a-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3585a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3585a-105">Hämta en matris med heltal inom ett angivet intervall.</span><span class="sxs-lookup"><span data-stu-id="3585a-105">Get an array of integers in a given interval.</span></span>

```qsharp
function SequenceL (from : BigInt, to : BigInt) : BigInt[]
```


## <a name="input"></a><span data-ttu-id="3585a-106">Indata</span><span class="sxs-lookup"><span data-stu-id="3585a-106">Input</span></span>

### <a name="from--bigint"></a><span data-ttu-id="3585a-107">från: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="3585a-107">from : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="3585a-108">Ett inklusiv start index för intervallet.</span><span class="sxs-lookup"><span data-stu-id="3585a-108">An inclusive start index of the interval.</span></span>


### <a name="to--bigint"></a><span data-ttu-id="3585a-109">till: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="3585a-109">to : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="3585a-110">Ett partiellt slut index för intervallet som inte är mindre än `from` .</span><span class="sxs-lookup"><span data-stu-id="3585a-110">An inclusive end index of the interval that is not smaller than `from`.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="3585a-111">Utdata: [BigInt](xref:microsoft.quantum.lang-ref.bigint)[]</span><span class="sxs-lookup"><span data-stu-id="3585a-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)[]</span></span>

<span data-ttu-id="3585a-112">En matris som innehåller sekvensen med tal `from` , `from + 1` ,..., `to` .</span><span class="sxs-lookup"><span data-stu-id="3585a-112">An array containing the sequence of numbers `from`, `from + 1`, ..., `to`.</span></span>

## <a name="remarks"></a><span data-ttu-id="3585a-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="3585a-113">Remarks</span></span>

<span data-ttu-id="3585a-114">Skillnaden mellan `from` och `to` måste passa in i ett `Int` värde.</span><span class="sxs-lookup"><span data-stu-id="3585a-114">The difference between `from` and `to` must fit into an `Int` value.</span></span>