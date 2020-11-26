---
uid: Microsoft.Quantum.Bitwise.LeftShiftedL
title: Funktionen LeftShiftedL
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedL
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: 00d4f9151c620e044074930933ea2912b52534ed
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219676"
---
# <a name="leftshiftedl-function"></a><span data-ttu-id="e7bf2-102">Funktionen LeftShiftedL</span><span class="sxs-lookup"><span data-stu-id="e7bf2-102">LeftShiftedL function</span></span>

<span data-ttu-id="e7bf2-103">Namnrymd: [Microsoft. Quantum. bitvis](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="e7bf2-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="e7bf2-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e7bf2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e7bf2-105">Växlar den bitvisa representationen av ett tal till vänster med ett angivet antal bitar.</span><span class="sxs-lookup"><span data-stu-id="e7bf2-105">Shifts the bitwise representation of a number left by a given number of bits.</span></span>

```qsharp
function LeftShiftedL (value : BigInt, amount : Int) : BigInt
```


## <a name="input"></a><span data-ttu-id="e7bf2-106">Indata</span><span class="sxs-lookup"><span data-stu-id="e7bf2-106">Input</span></span>

### <a name="value--bigint"></a><span data-ttu-id="e7bf2-107">värde: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="e7bf2-107">value : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="e7bf2-108">Det tal vars bitvisa representation ska flyttas till vänster (mer signifikant).</span><span class="sxs-lookup"><span data-stu-id="e7bf2-108">The number whose bitwise representation is to be shifted to the left (more significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="e7bf2-109">belopp: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e7bf2-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e7bf2-110">Antalet bitar som ska `value` flyttas till vänster.</span><span class="sxs-lookup"><span data-stu-id="e7bf2-110">The number of bits by which `value` is to be shifted to the left.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="e7bf2-111">Utdata: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="e7bf2-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="e7bf2-112">Värdet för `value` , flyttas till vänster med `amount` bitar.</span><span class="sxs-lookup"><span data-stu-id="e7bf2-112">The value of `value`, shifted left by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="e7bf2-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="e7bf2-113">Remarks</span></span>

<span data-ttu-id="e7bf2-114">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="e7bf2-114">The following are equivalent:</span></span>

```Q#
let c = a <<< b;
let c = LeftShiftedL(a, b);
```