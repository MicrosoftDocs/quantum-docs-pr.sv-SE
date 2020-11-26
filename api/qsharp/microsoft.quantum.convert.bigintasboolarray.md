---
uid: Microsoft.Quantum.Convert.BigIntAsBoolArray
title: Funktionen BigIntAsBoolArray
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BigIntAsBoolArray
qsharp.summary: Converts a given big integer to an array of Booleans. The 0 element of the array is the least significant bit of the big integer.
ms.openlocfilehash: 593fad99ef22d3c906b9f10adc07638bed227509
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224555"
---
# <a name="bigintasboolarray-function"></a><span data-ttu-id="36a67-102">Funktionen BigIntAsBoolArray</span><span class="sxs-lookup"><span data-stu-id="36a67-102">BigIntAsBoolArray function</span></span>

<span data-ttu-id="36a67-103">Namnrymd: [Microsoft. Quantum. convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="36a67-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="36a67-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="36a67-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="36a67-105">Konverterar ett angivet stort heltal till en matris med booleska värden.</span><span class="sxs-lookup"><span data-stu-id="36a67-105">Converts a given big integer to an array of Booleans.</span></span>
<span data-ttu-id="36a67-106">Elementet 0 i matrisen är den minst signifikanta biten av Big-heltalet.</span><span class="sxs-lookup"><span data-stu-id="36a67-106">The 0 element of the array is the least significant bit of the big integer.</span></span>

```qsharp
function BigIntAsBoolArray (a : BigInt) : Bool[]
```


## <a name="input"></a><span data-ttu-id="36a67-107">Indata</span><span class="sxs-lookup"><span data-stu-id="36a67-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="36a67-108">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="36a67-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>





## <a name="output--bool"></a><span data-ttu-id="36a67-109">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="36a67-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>



## <a name="remarks"></a><span data-ttu-id="36a67-110">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="36a67-110">Remarks</span></span>

<span data-ttu-id="36a67-111">Mer information finns i [C# BigInteger-konstruktorn](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) .</span><span class="sxs-lookup"><span data-stu-id="36a67-111">See [C# BigInteger constructor](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) for more details.</span></span>