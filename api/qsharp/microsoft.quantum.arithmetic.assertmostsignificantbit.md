---
uid: Microsoft.Quantum.Arithmetic.AssertMostSignificantBit
title: AssertMostSignificantBit-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertMostSignificantBit
qsharp.summary: Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.
ms.openlocfilehash: 408e50ed9f2e6c8ba35db20855608d2bd1f24eea
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731691"
---
# <a name="assertmostsignificantbit-operation"></a><span data-ttu-id="6b1b5-102">AssertMostSignificantBit-åtgärd</span><span class="sxs-lookup"><span data-stu-id="6b1b5-102">AssertMostSignificantBit operation</span></span>

<span data-ttu-id="6b1b5-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="6b1b5-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="6b1b5-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6b1b5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6b1b5-105">Förutsätter att den viktigaste qubit i ett qubit-register som representerar ett osignerat heltal är i ett visst tillstånd.</span><span class="sxs-lookup"><span data-stu-id="6b1b5-105">Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.</span></span>

```qsharp
operation AssertMostSignificantBit (value : Result, number : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="6b1b5-106">Indata</span><span class="sxs-lookup"><span data-stu-id="6b1b5-106">Input</span></span>

### <a name="value--__invalidresult__"></a><span data-ttu-id="6b1b5-107">värde: __ogiltigt <Result>__</span><span class="sxs-lookup"><span data-stu-id="6b1b5-107">value : __invalid<Result>__</span></span>

<span data-ttu-id="6b1b5-108">Värdet för den högsta biten som verifieras.</span><span class="sxs-lookup"><span data-stu-id="6b1b5-108">The value of the highest bit being asserted.</span></span>


### <a name="number--littleendian"></a><span data-ttu-id="6b1b5-109">nummer: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="6b1b5-109">number : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="6b1b5-110">Osignerat heltal som den högsta biten är markerad med.</span><span class="sxs-lookup"><span data-stu-id="6b1b5-110">Unsigned integer of which the highest bit is checked.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6b1b5-111">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6b1b5-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="6b1b5-112">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="6b1b5-112">Remarks</span></span>

<span data-ttu-id="6b1b5-113">Den kontrollerade versionen av den här åtgärden ignorerar kontroller.</span><span class="sxs-lookup"><span data-stu-id="6b1b5-113">The controlled version of this operation ignores controls.</span></span>

## <a name="see-also"></a><span data-ttu-id="6b1b5-114">Se även</span><span class="sxs-lookup"><span data-stu-id="6b1b5-114">See Also</span></span>

- [<span data-ttu-id="6b1b5-115">Microsoft. Quantum. inre. assert</span><span class="sxs-lookup"><span data-stu-id="6b1b5-115">Microsoft.Quantum.Intrinsic.Assert</span></span>](xref:Microsoft.Quantum.Intrinsic.Assert)