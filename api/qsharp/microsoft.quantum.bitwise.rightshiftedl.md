---
uid: Microsoft.Quantum.Bitwise.RightShiftedL
title: Funktionen RightShiftedL
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedL
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: 2929ba58b636847257391930e1019769fd2c2580
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729819"
---
# <a name="rightshiftedl-function"></a><span data-ttu-id="8b147-102">Funktionen RightShiftedL</span><span class="sxs-lookup"><span data-stu-id="8b147-102">RightShiftedL function</span></span>

<span data-ttu-id="8b147-103">Namnrymd: [Microsoft. Quantum. bitvis](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="8b147-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="8b147-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8b147-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8b147-105">Skiftar den bitvisa representationen av ett tal direkt med ett angivet antal bitar.</span><span class="sxs-lookup"><span data-stu-id="8b147-105">Shifts the bitwise representation of a number right by a given number of bits.</span></span>

```qsharp
function RightShiftedL (value : BigInt, amount : Int) : BigInt
```


## <a name="input"></a><span data-ttu-id="8b147-106">Indata</span><span class="sxs-lookup"><span data-stu-id="8b147-106">Input</span></span>

### <a name="value--bigint"></a><span data-ttu-id="8b147-107">värde: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="8b147-107">value : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="8b147-108">Det tal vars bitvisa representation ska flyttas till höger (mindre signifikant).</span><span class="sxs-lookup"><span data-stu-id="8b147-108">The number whose bitwise representation is to be shifted to the right (less significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="8b147-109">belopp: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8b147-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8b147-110">Antalet bitar som ska `value` flyttas till höger.</span><span class="sxs-lookup"><span data-stu-id="8b147-110">The number of bits by which `value` is to be shifted to the right.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="8b147-111">Utdata: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="8b147-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="8b147-112">Värdet för `value` , flyttas direkt med `amount` bitar.</span><span class="sxs-lookup"><span data-stu-id="8b147-112">The value of `value`, shifted right by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="8b147-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="8b147-113">Remarks</span></span>

<span data-ttu-id="8b147-114">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="8b147-114">The following are equivalent:</span></span>

```Q#
let c = a >>> b;
let c = RightShiftedL(a, b);
```