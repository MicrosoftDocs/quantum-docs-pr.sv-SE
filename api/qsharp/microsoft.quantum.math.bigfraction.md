---
uid: Microsoft.Quantum.Math.BigFraction
title: BigFraction-användardefinierad typ
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BigFraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: bfbf49e7a3d060417e506a1977c20adc08b81f0e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846909"
---
# <a name="bigfraction-user-defined-type"></a><span data-ttu-id="38cf7-102">BigFraction-användardefinierad typ</span><span class="sxs-lookup"><span data-stu-id="38cf7-102">BigFraction user defined type</span></span>

<span data-ttu-id="38cf7-103">Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="38cf7-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="38cf7-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="38cf7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="38cf7-105">Representerar ett rationellt antal formulär `p/q` .</span><span class="sxs-lookup"><span data-stu-id="38cf7-105">Represents a rational number of the form `p/q`.</span></span> <span data-ttu-id="38cf7-106">Integer `p` är det första elementet i tuppeln och `q` är det andra elementet i tuppeln.</span><span class="sxs-lookup"><span data-stu-id="38cf7-106">Integer `p` is the first element of the tuple and `q` is the second element of the tuple.</span></span>

```qsharp

newtype BigFraction = (Numerator : BigInt, Denominator : BigInt);
```



## <a name="named-items"></a><span data-ttu-id="38cf7-107">Namngivna objekt</span><span class="sxs-lookup"><span data-stu-id="38cf7-107">Named Items</span></span>

### <a name="numerator--bigint"></a><span data-ttu-id="38cf7-108">Täljare: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="38cf7-108">Numerator : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="38cf7-109">Täljare för bråket.</span><span class="sxs-lookup"><span data-stu-id="38cf7-109">Numerator of the fraction.</span></span>
### <a name="denominator--bigint"></a><span data-ttu-id="38cf7-110">Nämnare: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="38cf7-110">Denominator : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="38cf7-111">Nämnaren för bråk/</span><span class="sxs-lookup"><span data-stu-id="38cf7-111">Denominator of the fraction/</span></span>