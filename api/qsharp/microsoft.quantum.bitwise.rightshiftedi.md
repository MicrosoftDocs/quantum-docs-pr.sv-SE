---
uid: Microsoft.Quantum.Bitwise.RightShiftedI
title: Funktionen RightShiftedI
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedI
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: b20a4a8c281a470af9a4828f8a5ca905a7918723
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209782"
---
# <a name="rightshiftedi-function"></a><span data-ttu-id="447d4-102">Funktionen RightShiftedI</span><span class="sxs-lookup"><span data-stu-id="447d4-102">RightShiftedI function</span></span>

<span data-ttu-id="447d4-103">Namnrymd: [Microsoft. Quantum. bitvis](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="447d4-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="447d4-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="447d4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="447d4-105">Skiftar den bitvisa representationen av ett tal direkt med ett angivet antal bitar.</span><span class="sxs-lookup"><span data-stu-id="447d4-105">Shifts the bitwise representation of a number right by a given number of bits.</span></span>

```qsharp
function RightShiftedI (value : Int, amount : Int) : Int
```


## <a name="input"></a><span data-ttu-id="447d4-106">Indata</span><span class="sxs-lookup"><span data-stu-id="447d4-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="447d4-107">värde: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="447d4-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="447d4-108">Det tal vars bitvisa representation ska flyttas till höger (mindre signifikant).</span><span class="sxs-lookup"><span data-stu-id="447d4-108">The number whose bitwise representation is to be shifted to the right (less significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="447d4-109">belopp: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="447d4-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="447d4-110">Antalet bitar som ska `value` flyttas till höger.</span><span class="sxs-lookup"><span data-stu-id="447d4-110">The number of bits by which `value` is to be shifted to the right.</span></span>



## <a name="output--int"></a><span data-ttu-id="447d4-111">Utdata: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="447d4-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="447d4-112">Värdet för `value` , flyttas direkt med `amount` bitar.</span><span class="sxs-lookup"><span data-stu-id="447d4-112">The value of `value`, shifted right by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="447d4-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="447d4-113">Remarks</span></span>

<span data-ttu-id="447d4-114">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="447d4-114">The following are equivalent:</span></span>

```Q#
let c = a >>> b;
let c = RightShiftedI(a, b);
```