---
uid: Microsoft.Quantum.Math.BitSizeI
title: Funktionen BitSizeI
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BitSizeI
qsharp.summary: >-
  For a non-negative integer `a`, returns the number of bits required to represent `a`.

  That is, returns the smallest $n$ such that $a < 2^n$.
ms.openlocfilehash: e7edf37a81571dfa1d4cb755493e1863a44c694e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857703"
---
# <a name="bitsizei-function"></a><span data-ttu-id="ddee9-102">Funktionen BitSizeI</span><span class="sxs-lookup"><span data-stu-id="ddee9-102">BitSizeI function</span></span>

<span data-ttu-id="ddee9-103">Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="ddee9-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="ddee9-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ddee9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ddee9-105">För ett icke-negativt heltal `a` returnerar antalet bitar som krävs för att representera `a` .</span><span class="sxs-lookup"><span data-stu-id="ddee9-105">For a non-negative integer `a`, returns the number of bits required to represent `a`.</span></span>

<span data-ttu-id="ddee9-106">Det vill säga returnerar det minsta $n $ som $a < 2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="ddee9-106">That is, returns the smallest $n$ such that $a < 2^n$.</span></span>

```qsharp
function BitSizeI (a : Int) : Int
```


## <a name="input"></a><span data-ttu-id="ddee9-107">Indata</span><span class="sxs-lookup"><span data-stu-id="ddee9-107">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="ddee9-108">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ddee9-108">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ddee9-109">Det heltal vars bit-storlek ska beräknas.</span><span class="sxs-lookup"><span data-stu-id="ddee9-109">The integer whose bit-size is to be computed.</span></span>



## <a name="output--int"></a><span data-ttu-id="ddee9-110">Utdata: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ddee9-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ddee9-111">Bit-storlek för `a` .</span><span class="sxs-lookup"><span data-stu-id="ddee9-111">The bit-size of `a`.</span></span>