---
uid: Microsoft.Quantum.Arithmetic.AssertMostSignificantBit
title: AssertMostSignificantBit-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertMostSignificantBit
qsharp.summary: Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.
ms.openlocfilehash: b0b52a4ba7492d68896669aeb0b6b550d2f27f64
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843428"
---
# <a name="assertmostsignificantbit-operation"></a><span data-ttu-id="74ebf-102">AssertMostSignificantBit-åtgärd</span><span class="sxs-lookup"><span data-stu-id="74ebf-102">AssertMostSignificantBit operation</span></span>

<span data-ttu-id="74ebf-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="74ebf-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="74ebf-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="74ebf-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="74ebf-105">Förutsätter att den viktigaste qubit i ett qubit-register som representerar ett osignerat heltal är i ett visst tillstånd.</span><span class="sxs-lookup"><span data-stu-id="74ebf-105">Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.</span></span>

```qsharp
operation AssertMostSignificantBit (value : Result, number : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="74ebf-106">Indata</span><span class="sxs-lookup"><span data-stu-id="74ebf-106">Input</span></span>

### <a name="value--__invalidresult__"></a><span data-ttu-id="74ebf-107">värde: __ogiltigt <Result>__</span><span class="sxs-lookup"><span data-stu-id="74ebf-107">value : __invalid<Result>__</span></span>

<span data-ttu-id="74ebf-108">Värdet för den högsta biten som verifieras.</span><span class="sxs-lookup"><span data-stu-id="74ebf-108">The value of the highest bit being asserted.</span></span>


### <a name="number--littleendian"></a><span data-ttu-id="74ebf-109">nummer: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="74ebf-109">number : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="74ebf-110">Osignerat heltal som den högsta biten är markerad med.</span><span class="sxs-lookup"><span data-stu-id="74ebf-110">Unsigned integer of which the highest bit is checked.</span></span>



## <a name="output--unit"></a><span data-ttu-id="74ebf-111">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="74ebf-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="74ebf-112">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="74ebf-112">Remarks</span></span>

<span data-ttu-id="74ebf-113">Den kontrollerade versionen av den här åtgärden ignorerar kontroller.</span><span class="sxs-lookup"><span data-stu-id="74ebf-113">The controlled version of this operation ignores controls.</span></span>

## <a name="see-also"></a><span data-ttu-id="74ebf-114">Se även</span><span class="sxs-lookup"><span data-stu-id="74ebf-114">See Also</span></span>

- [<span data-ttu-id="74ebf-115">Microsoft. Quantum. inre. assert</span><span class="sxs-lookup"><span data-stu-id="74ebf-115">Microsoft.Quantum.Intrinsic.Assert</span></span>](xref:Microsoft.Quantum.Intrinsic.Assert)