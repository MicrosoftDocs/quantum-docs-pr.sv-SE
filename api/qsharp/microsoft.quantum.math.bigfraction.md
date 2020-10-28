---
uid: Microsoft.Quantum.Math.BigFraction
title: BigFraction-användardefinierad typ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BigFraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: a8daa54947097b95040a2dfa7a4d1b90bfaff856
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732766"
---
# <a name="bigfraction-user-defined-type"></a><span data-ttu-id="b5a60-102">BigFraction-användardefinierad typ</span><span class="sxs-lookup"><span data-stu-id="b5a60-102">BigFraction user defined type</span></span>

<span data-ttu-id="b5a60-103">Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="b5a60-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="b5a60-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b5a60-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b5a60-105">Representerar ett rationellt antal formulär `p/q` .</span><span class="sxs-lookup"><span data-stu-id="b5a60-105">Represents a rational number of the form `p/q`.</span></span> <span data-ttu-id="b5a60-106">Integer `p` är det första elementet i tuppeln och `q` är det andra elementet i tuppeln.</span><span class="sxs-lookup"><span data-stu-id="b5a60-106">Integer `p` is the first element of the tuple and `q` is the second element of the tuple.</span></span>

```qsharp

newtype BigFraction = (Numerator : BigInt, Denominator : BigInt);
```



## <a name="named-items"></a><span data-ttu-id="b5a60-107">Namngivna objekt</span><span class="sxs-lookup"><span data-stu-id="b5a60-107">Named Items</span></span>

### <a name="numerator--bigint"></a><span data-ttu-id="b5a60-108">Täljare: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="b5a60-108">Numerator : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="b5a60-109">Täljare för bråket.</span><span class="sxs-lookup"><span data-stu-id="b5a60-109">Numerator of the fraction.</span></span>
### <a name="denominator--bigint"></a><span data-ttu-id="b5a60-110">Nämnare: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="b5a60-110">Denominator : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="b5a60-111">Nämnaren för bråk/</span><span class="sxs-lookup"><span data-stu-id="b5a60-111">Denominator of the fraction/</span></span>