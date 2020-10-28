---
uid: Microsoft.Quantum.Bitwise.LeftShiftedI
title: Funktionen LeftShiftedI
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedI
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: ce68311adf211169c2fb499bb189332370a6d6ac
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729878"
---
# <a name="leftshiftedi-function"></a><span data-ttu-id="beea6-102">Funktionen LeftShiftedI</span><span class="sxs-lookup"><span data-stu-id="beea6-102">LeftShiftedI function</span></span>

<span data-ttu-id="beea6-103">Namnrymd: [Microsoft. Quantum. bitvis](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="beea6-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="beea6-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="beea6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="beea6-105">Växlar den bitvisa representationen av ett tal till vänster med ett angivet antal bitar.</span><span class="sxs-lookup"><span data-stu-id="beea6-105">Shifts the bitwise representation of a number left by a given number of bits.</span></span>

```qsharp
function LeftShiftedI (value : Int, amount : Int) : Int
```


## <a name="input"></a><span data-ttu-id="beea6-106">Indata</span><span class="sxs-lookup"><span data-stu-id="beea6-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="beea6-107">värde: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="beea6-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="beea6-108">Det tal vars bitvisa representation ska flyttas till vänster (mer signifikant).</span><span class="sxs-lookup"><span data-stu-id="beea6-108">The number whose bitwise representation is to be shifted to the left (more significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="beea6-109">belopp: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="beea6-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="beea6-110">Antalet bitar som ska `value` flyttas till vänster.</span><span class="sxs-lookup"><span data-stu-id="beea6-110">The number of bits by which `value` is to be shifted to the left.</span></span>



## <a name="output--int"></a><span data-ttu-id="beea6-111">Utdata: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="beea6-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="beea6-112">Värdet för `value` , flyttas till vänster med `amount` bitar.</span><span class="sxs-lookup"><span data-stu-id="beea6-112">The value of `value`, shifted left by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="beea6-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="beea6-113">Remarks</span></span>

<span data-ttu-id="beea6-114">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="beea6-114">The following are equivalent:</span></span>

```Q#
let c = a <<< b;
let c = LeftShiftedI(a, b);
```