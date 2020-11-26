---
uid: Microsoft.Quantum.Bitwise.RightShiftedL
title: Funktionen RightShiftedL
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedL
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: 3d941e1a0bcd96fe54ab01019293d883f11547a1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219523"
---
# <a name="rightshiftedl-function"></a><span data-ttu-id="eb97b-102">Funktionen RightShiftedL</span><span class="sxs-lookup"><span data-stu-id="eb97b-102">RightShiftedL function</span></span>

<span data-ttu-id="eb97b-103">Namnrymd: [Microsoft. Quantum. bitvis](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="eb97b-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="eb97b-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="eb97b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="eb97b-105">Skiftar den bitvisa representationen av ett tal direkt med ett angivet antal bitar.</span><span class="sxs-lookup"><span data-stu-id="eb97b-105">Shifts the bitwise representation of a number right by a given number of bits.</span></span>

```qsharp
function RightShiftedL (value : BigInt, amount : Int) : BigInt
```


## <a name="input"></a><span data-ttu-id="eb97b-106">Indata</span><span class="sxs-lookup"><span data-stu-id="eb97b-106">Input</span></span>

### <a name="value--bigint"></a><span data-ttu-id="eb97b-107">värde: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="eb97b-107">value : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="eb97b-108">Det tal vars bitvisa representation ska flyttas till höger (mindre signifikant).</span><span class="sxs-lookup"><span data-stu-id="eb97b-108">The number whose bitwise representation is to be shifted to the right (less significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="eb97b-109">belopp: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="eb97b-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="eb97b-110">Antalet bitar som ska `value` flyttas till höger.</span><span class="sxs-lookup"><span data-stu-id="eb97b-110">The number of bits by which `value` is to be shifted to the right.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="eb97b-111">Utdata: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="eb97b-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="eb97b-112">Värdet för `value` , flyttas direkt med `amount` bitar.</span><span class="sxs-lookup"><span data-stu-id="eb97b-112">The value of `value`, shifted right by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="eb97b-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="eb97b-113">Remarks</span></span>

<span data-ttu-id="eb97b-114">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="eb97b-114">The following are equivalent:</span></span>

```Q#
let c = a >>> b;
let c = RightShiftedL(a, b);
```