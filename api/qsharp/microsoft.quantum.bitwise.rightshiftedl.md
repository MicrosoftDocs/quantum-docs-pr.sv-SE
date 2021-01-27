---
uid: Microsoft.Quantum.Bitwise.RightShiftedL
title: Funktionen RightShiftedL
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedL
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: 03ed69c7151e62b91c4a036e301f99b45ce5ab62
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842100"
---
# <a name="rightshiftedl-function"></a><span data-ttu-id="1d453-102">Funktionen RightShiftedL</span><span class="sxs-lookup"><span data-stu-id="1d453-102">RightShiftedL function</span></span>

<span data-ttu-id="1d453-103">Namnrymd: [Microsoft. Quantum. bitvis](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="1d453-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="1d453-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1d453-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1d453-105">Skiftar den bitvisa representationen av ett tal direkt med ett angivet antal bitar.</span><span class="sxs-lookup"><span data-stu-id="1d453-105">Shifts the bitwise representation of a number right by a given number of bits.</span></span>

```qsharp
function RightShiftedL (value : BigInt, amount : Int) : BigInt
```


## <a name="input"></a><span data-ttu-id="1d453-106">Indata</span><span class="sxs-lookup"><span data-stu-id="1d453-106">Input</span></span>

### <a name="value--bigint"></a><span data-ttu-id="1d453-107">värde: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="1d453-107">value : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="1d453-108">Det tal vars bitvisa representation ska flyttas till höger (mindre signifikant).</span><span class="sxs-lookup"><span data-stu-id="1d453-108">The number whose bitwise representation is to be shifted to the right (less significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="1d453-109">belopp: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1d453-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1d453-110">Antalet bitar som ska `value` flyttas till höger.</span><span class="sxs-lookup"><span data-stu-id="1d453-110">The number of bits by which `value` is to be shifted to the right.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="1d453-111">Utdata: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="1d453-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="1d453-112">Värdet för `value` , flyttas direkt med `amount` bitar.</span><span class="sxs-lookup"><span data-stu-id="1d453-112">The value of `value`, shifted right by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="1d453-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="1d453-113">Remarks</span></span>

<span data-ttu-id="1d453-114">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="1d453-114">The following are equivalent:</span></span>

```qsharp
let c = a >>> b;
let c = RightShiftedL(a, b);
```