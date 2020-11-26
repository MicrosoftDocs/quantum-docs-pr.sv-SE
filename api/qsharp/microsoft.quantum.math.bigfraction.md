---
uid: Microsoft.Quantum.Math.BigFraction
title: BigFraction-användardefinierad typ
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BigFraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: 1c9b9e350c4fa3664b2c66da05149005b1170ec3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211091"
---
# <a name="bigfraction-user-defined-type"></a><span data-ttu-id="d7457-102">BigFraction-användardefinierad typ</span><span class="sxs-lookup"><span data-stu-id="d7457-102">BigFraction user defined type</span></span>

<span data-ttu-id="d7457-103">Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="d7457-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="d7457-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d7457-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d7457-105">Representerar ett rationellt antal formulär `p/q` .</span><span class="sxs-lookup"><span data-stu-id="d7457-105">Represents a rational number of the form `p/q`.</span></span> <span data-ttu-id="d7457-106">Integer `p` är det första elementet i tuppeln och `q` är det andra elementet i tuppeln.</span><span class="sxs-lookup"><span data-stu-id="d7457-106">Integer `p` is the first element of the tuple and `q` is the second element of the tuple.</span></span>

```qsharp

newtype BigFraction = (Numerator : BigInt, Denominator : BigInt);
```



## <a name="named-items"></a><span data-ttu-id="d7457-107">Namngivna objekt</span><span class="sxs-lookup"><span data-stu-id="d7457-107">Named Items</span></span>

### <a name="numerator--bigint"></a><span data-ttu-id="d7457-108">Täljare: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="d7457-108">Numerator : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="d7457-109">Täljare för bråket.</span><span class="sxs-lookup"><span data-stu-id="d7457-109">Numerator of the fraction.</span></span>
### <a name="denominator--bigint"></a><span data-ttu-id="d7457-110">Nämnare: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="d7457-110">Denominator : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="d7457-111">Nämnaren för bråk/</span><span class="sxs-lookup"><span data-stu-id="d7457-111">Denominator of the fraction/</span></span>