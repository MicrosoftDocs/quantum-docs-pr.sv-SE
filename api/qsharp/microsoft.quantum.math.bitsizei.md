---
uid: Microsoft.Quantum.Math.BitSizeI
title: Funktionen BitSizeI
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BitSizeI
qsharp.summary: >-
  For a non-negative integer `a`, returns the number of bits required to represent `a`.

  That is, returns the smallest $n$ such that $a < 2^n$.
ms.openlocfilehash: 561450ef43144aa4d7820e1f15d9300018104acd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195859"
---
# <a name="bitsizei-function"></a><span data-ttu-id="541c4-102">Funktionen BitSizeI</span><span class="sxs-lookup"><span data-stu-id="541c4-102">BitSizeI function</span></span>

<span data-ttu-id="541c4-103">Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="541c4-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="541c4-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="541c4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="541c4-105">För ett icke-negativt heltal `a` returnerar antalet bitar som krävs för att representera `a` .</span><span class="sxs-lookup"><span data-stu-id="541c4-105">For a non-negative integer `a`, returns the number of bits required to represent `a`.</span></span>

<span data-ttu-id="541c4-106">Det vill säga returnerar det minsta $n $ som $a < 2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="541c4-106">That is, returns the smallest $n$ such that $a < 2^n$.</span></span>

```qsharp
function BitSizeI (a : Int) : Int
```


## <a name="input"></a><span data-ttu-id="541c4-107">Indata</span><span class="sxs-lookup"><span data-stu-id="541c4-107">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="541c4-108">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="541c4-108">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="541c4-109">Det heltal vars bit-storlek ska beräknas.</span><span class="sxs-lookup"><span data-stu-id="541c4-109">The integer whose bit-size is to be computed.</span></span>



## <a name="output--int"></a><span data-ttu-id="541c4-110">Utdata: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="541c4-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="541c4-111">Bit-storlek för `a` .</span><span class="sxs-lookup"><span data-stu-id="541c4-111">The bit-size of `a`.</span></span>