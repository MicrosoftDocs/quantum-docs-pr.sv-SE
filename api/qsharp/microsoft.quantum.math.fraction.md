---
uid: Microsoft.Quantum.Math.Fraction
title: Användardefinierad typ av fraktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: Fraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: a56d28e34938729a8e4ffda5f870e0b6a25be017
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857520"
---
# <a name="fraction-user-defined-type"></a><span data-ttu-id="d3b39-102">Användardefinierad typ av fraktion</span><span class="sxs-lookup"><span data-stu-id="d3b39-102">Fraction user defined type</span></span>

<span data-ttu-id="d3b39-103">Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="d3b39-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="d3b39-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d3b39-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d3b39-105">Representerar ett rationellt antal formulär `p/q` .</span><span class="sxs-lookup"><span data-stu-id="d3b39-105">Represents a rational number of the form `p/q`.</span></span> <span data-ttu-id="d3b39-106">Integer `p` är det första elementet i tuppeln och `q` är det andra elementet i tuppeln.</span><span class="sxs-lookup"><span data-stu-id="d3b39-106">Integer `p` is the first element of the tuple and `q` is the second element of the tuple.</span></span>

```qsharp

newtype Fraction = (Numerator : Int, Denominator : Int);
```



## <a name="named-items"></a><span data-ttu-id="d3b39-107">Namngivna objekt</span><span class="sxs-lookup"><span data-stu-id="d3b39-107">Named Items</span></span>

### <a name="numerator--int"></a><span data-ttu-id="d3b39-108">Täljare: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d3b39-108">Numerator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d3b39-109">Täljare för bråket.</span><span class="sxs-lookup"><span data-stu-id="d3b39-109">Numerator of the fraction.</span></span>
### <a name="denominator--int"></a><span data-ttu-id="d3b39-110">Nämnare: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d3b39-110">Denominator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d3b39-111">Nämnaren för bråk/</span><span class="sxs-lookup"><span data-stu-id="d3b39-111">Denominator of the fraction/</span></span>