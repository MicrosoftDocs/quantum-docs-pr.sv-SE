---
uid: Microsoft.Quantum.Math.Fraction
title: Användardefinierad typ av fraktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: Fraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: 350d470c374fc8e0a3f4c4a9a68ad8566ab88727
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733022"
---
# <a name="fraction-user-defined-type"></a><span data-ttu-id="6ba2e-102">Användardefinierad typ av fraktion</span><span class="sxs-lookup"><span data-stu-id="6ba2e-102">Fraction user defined type</span></span>

<span data-ttu-id="6ba2e-103">Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="6ba2e-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="6ba2e-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6ba2e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6ba2e-105">Representerar ett rationellt antal formulär `p/q` .</span><span class="sxs-lookup"><span data-stu-id="6ba2e-105">Represents a rational number of the form `p/q`.</span></span> <span data-ttu-id="6ba2e-106">Integer `p` är det första elementet i tuppeln och `q` är det andra elementet i tuppeln.</span><span class="sxs-lookup"><span data-stu-id="6ba2e-106">Integer `p` is the first element of the tuple and `q` is the second element of the tuple.</span></span>

```qsharp

newtype Fraction = (Numerator : Int, Denominator : Int);
```



## <a name="named-items"></a><span data-ttu-id="6ba2e-107">Namngivna objekt</span><span class="sxs-lookup"><span data-stu-id="6ba2e-107">Named Items</span></span>

### <a name="numerator--int"></a><span data-ttu-id="6ba2e-108">Täljare: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6ba2e-108">Numerator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6ba2e-109">Täljare för bråket.</span><span class="sxs-lookup"><span data-stu-id="6ba2e-109">Numerator of the fraction.</span></span>
### <a name="denominator--int"></a><span data-ttu-id="6ba2e-110">Nämnare: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6ba2e-110">Denominator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6ba2e-111">Nämnaren för bråk/</span><span class="sxs-lookup"><span data-stu-id="6ba2e-111">Denominator of the fraction/</span></span>