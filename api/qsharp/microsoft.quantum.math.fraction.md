---
uid: Microsoft.Quantum.Math.Fraction
title: Användardefinierad typ av fraktion
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: Fraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: 1838bb2b605b109742948ec0633b08ca01baea98
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210683"
---
# <a name="fraction-user-defined-type"></a><span data-ttu-id="5aa25-102">Användardefinierad typ av fraktion</span><span class="sxs-lookup"><span data-stu-id="5aa25-102">Fraction user defined type</span></span>

<span data-ttu-id="5aa25-103">Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="5aa25-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="5aa25-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5aa25-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5aa25-105">Representerar ett rationellt antal formulär `p/q` .</span><span class="sxs-lookup"><span data-stu-id="5aa25-105">Represents a rational number of the form `p/q`.</span></span> <span data-ttu-id="5aa25-106">Integer `p` är det första elementet i tuppeln och `q` är det andra elementet i tuppeln.</span><span class="sxs-lookup"><span data-stu-id="5aa25-106">Integer `p` is the first element of the tuple and `q` is the second element of the tuple.</span></span>

```qsharp

newtype Fraction = (Numerator : Int, Denominator : Int);
```



## <a name="named-items"></a><span data-ttu-id="5aa25-107">Namngivna objekt</span><span class="sxs-lookup"><span data-stu-id="5aa25-107">Named Items</span></span>

### <a name="numerator--int"></a><span data-ttu-id="5aa25-108">Täljare: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5aa25-108">Numerator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5aa25-109">Täljare för bråket.</span><span class="sxs-lookup"><span data-stu-id="5aa25-109">Numerator of the fraction.</span></span>
### <a name="denominator--int"></a><span data-ttu-id="5aa25-110">Nämnare: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5aa25-110">Denominator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5aa25-111">Nämnaren för bråk/</span><span class="sxs-lookup"><span data-stu-id="5aa25-111">Denominator of the fraction/</span></span>