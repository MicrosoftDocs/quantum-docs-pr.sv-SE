---
uid: Microsoft.Quantum.Math.BitSizeL
title: Funktionen BitSizeL
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BitSizeL
qsharp.summary: >-
  For a non-negative integer `a`, returns the number of bits required to represent `a`.

  That is, returns the smallest $n$ such that $a < 2^n$.
ms.openlocfilehash: 97068f12050317a9aa17c95f33650ef6f406066d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732755"
---
# <a name="bitsizel-function"></a><span data-ttu-id="0cf57-102">Funktionen BitSizeL</span><span class="sxs-lookup"><span data-stu-id="0cf57-102">BitSizeL function</span></span>

<span data-ttu-id="0cf57-103">Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="0cf57-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="0cf57-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0cf57-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0cf57-105">För ett icke-negativt heltal `a` returnerar antalet bitar som krävs för att representera `a` .</span><span class="sxs-lookup"><span data-stu-id="0cf57-105">For a non-negative integer `a`, returns the number of bits required to represent `a`.</span></span>

<span data-ttu-id="0cf57-106">Det vill säga returnerar det minsta $n $ som $a < 2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="0cf57-106">That is, returns the smallest $n$ such that $a < 2^n$.</span></span>

```qsharp
function BitSizeL (a : BigInt) : Int
```


## <a name="input"></a><span data-ttu-id="0cf57-107">Indata</span><span class="sxs-lookup"><span data-stu-id="0cf57-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="0cf57-108">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="0cf57-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="0cf57-109">Det heltal vars bit-storlek ska beräknas.</span><span class="sxs-lookup"><span data-stu-id="0cf57-109">The integer whose bit-size is to be computed.</span></span>



## <a name="output--int"></a><span data-ttu-id="0cf57-110">Utdata: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0cf57-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0cf57-111">Bit-storlek för `a` .</span><span class="sxs-lookup"><span data-stu-id="0cf57-111">The bit-size of `a`.</span></span>