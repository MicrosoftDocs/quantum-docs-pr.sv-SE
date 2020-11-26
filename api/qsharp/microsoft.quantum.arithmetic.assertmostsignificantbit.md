---
uid: Microsoft.Quantum.Arithmetic.AssertMostSignificantBit
title: AssertMostSignificantBit-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertMostSignificantBit
qsharp.summary: Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.
ms.openlocfilehash: 41381455d1a96970647f887e038f7dff3a4eb204
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223790"
---
# <a name="assertmostsignificantbit-operation"></a><span data-ttu-id="a2e7b-102">AssertMostSignificantBit-åtgärd</span><span class="sxs-lookup"><span data-stu-id="a2e7b-102">AssertMostSignificantBit operation</span></span>

<span data-ttu-id="a2e7b-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="a2e7b-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="a2e7b-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a2e7b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a2e7b-105">Förutsätter att den viktigaste qubit i ett qubit-register som representerar ett osignerat heltal är i ett visst tillstånd.</span><span class="sxs-lookup"><span data-stu-id="a2e7b-105">Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.</span></span>

```qsharp
operation AssertMostSignificantBit (value : Result, number : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="a2e7b-106">Indata</span><span class="sxs-lookup"><span data-stu-id="a2e7b-106">Input</span></span>

### <a name="value--__invalidresult__"></a><span data-ttu-id="a2e7b-107">värde: __ogiltigt <Result>__</span><span class="sxs-lookup"><span data-stu-id="a2e7b-107">value : __invalid<Result>__</span></span>

<span data-ttu-id="a2e7b-108">Värdet för den högsta biten som verifieras.</span><span class="sxs-lookup"><span data-stu-id="a2e7b-108">The value of the highest bit being asserted.</span></span>


### <a name="number--littleendian"></a><span data-ttu-id="a2e7b-109">nummer: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="a2e7b-109">number : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="a2e7b-110">Osignerat heltal som den högsta biten är markerad med.</span><span class="sxs-lookup"><span data-stu-id="a2e7b-110">Unsigned integer of which the highest bit is checked.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a2e7b-111">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a2e7b-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="a2e7b-112">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="a2e7b-112">Remarks</span></span>

<span data-ttu-id="a2e7b-113">Den kontrollerade versionen av den här åtgärden ignorerar kontroller.</span><span class="sxs-lookup"><span data-stu-id="a2e7b-113">The controlled version of this operation ignores controls.</span></span>

## <a name="see-also"></a><span data-ttu-id="a2e7b-114">Se även</span><span class="sxs-lookup"><span data-stu-id="a2e7b-114">See Also</span></span>

- [<span data-ttu-id="a2e7b-115">Microsoft. Quantum. inre. assert</span><span class="sxs-lookup"><span data-stu-id="a2e7b-115">Microsoft.Quantum.Intrinsic.Assert</span></span>](xref:Microsoft.Quantum.Intrinsic.Assert)