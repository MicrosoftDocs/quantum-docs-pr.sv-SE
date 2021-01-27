---
uid: Microsoft.Quantum.Arithmetic.IncrementPhaseByInteger
title: IncrementPhaseByInteger-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementPhaseByInteger
qsharp.summary: Increments an unsigned quantum register by a classical integer, using phase rotations.
ms.openlocfilehash: cc7922b2940cb979394958d5eb4e9933144eb062
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843149"
---
# <a name="incrementphasebyinteger-operation"></a><span data-ttu-id="80271-102">IncrementPhaseByInteger-åtgärd</span><span class="sxs-lookup"><span data-stu-id="80271-102">IncrementPhaseByInteger operation</span></span>

<span data-ttu-id="80271-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="80271-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="80271-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="80271-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="80271-105">Ökar en osignerad Quantum-registrering med ett klassiskt heltal med hjälp av fas rotationer.</span><span class="sxs-lookup"><span data-stu-id="80271-105">Increments an unsigned quantum register by a classical integer, using phase rotations.</span></span>

```qsharp
operation IncrementPhaseByInteger (increment : Int, target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="80271-106">Description</span><span class="sxs-lookup"><span data-stu-id="80271-106">Description</span></span>

<span data-ttu-id="80271-107">Anta att `target` koda ett osignerat heltal $x $ i en lite-endian-kodning och att det `increment` motsvarar $a $.</span><span class="sxs-lookup"><span data-stu-id="80271-107">Suppose that `target` encodes an unsigned integer $x$ in a little-endian encoding and that `increment` is equal to $a$.</span></span>
<span data-ttu-id="80271-108">Den här åtgärden implementerar sedan den enhetliga $ \ket{x} \mapsto \ket{x + a} $, där additionen utförs med modulo $2 ^ n $, där $n = \texttt{Length (Target!)} $.</span><span class="sxs-lookup"><span data-stu-id="80271-108">Then, this operation implements the unitary $\ket{x} \mapsto \ket{x + a}$, where the addition is performed modulo $2^n$, where $n = \texttt{Length(target!)}$.</span></span>

## <a name="input"></a><span data-ttu-id="80271-109">Indata</span><span class="sxs-lookup"><span data-stu-id="80271-109">Input</span></span>

### <a name="increment--int"></a><span data-ttu-id="80271-110">ökning: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="80271-110">increment : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="80271-111">Det heltal som `target` ökar med.</span><span class="sxs-lookup"><span data-stu-id="80271-111">The integer by which the `target` is incremented by.</span></span>


### <a name="target--phaselittleendian"></a><span data-ttu-id="80271-112">mål: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="80271-112">target : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="80271-113">Ett Quantum-register som kodar ett osignerat heltal med lite endian-kodning i dubbel (QFT)-grunden.</span><span class="sxs-lookup"><span data-stu-id="80271-113">A quantum register encoding an unsigned integer using little-endian encoding in the dual (QFT) basis.</span></span>



## <a name="output--unit"></a><span data-ttu-id="80271-114">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="80271-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="80271-115">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="80271-115">Remarks</span></span>

<span data-ttu-id="80271-116">Observera att vi har förenklat kretsen eftersom ökningen är en klassisk konstant, inte ett Quantum-register.</span><span class="sxs-lookup"><span data-stu-id="80271-116">Note that we have simplified the circuit because the increment is a classical constant, not a quantum register.</span></span>

<span data-ttu-id="80271-117">Se figuren på [ sidan 6 i arXiv: Quant-pH/0008033v1 ](https://arxiv.org/pdf/quant-ph/0008033.pdf#page=6) för krets diagrammet och förklaringen.</span><span class="sxs-lookup"><span data-stu-id="80271-117">See the figure on [ Page 6 of arXiv:quant-ph/0008033v1 ](https://arxiv.org/pdf/quant-ph/0008033.pdf#page=6) for the circuit diagram and explanation.</span></span>

## <a name="references"></a><span data-ttu-id="80271-118">Referenser</span><span class="sxs-lookup"><span data-stu-id="80271-118">References</span></span>

- [<span data-ttu-id="80271-119">*Thomas G. Draper*, arXiv: Quant-pH/0008033</span><span class="sxs-lookup"><span data-stu-id="80271-119"> *Thomas G. Draper*, arXiv:quant-ph/0008033</span></span>](https://arxiv.org/pdf/quant-ph/0008033v1.pdf)

## <a name="see-also"></a><span data-ttu-id="80271-120">Se även</span><span class="sxs-lookup"><span data-stu-id="80271-120">See Also</span></span>

- [<span data-ttu-id="80271-121">Microsoft. Quantum. aritmetiska. IncrementByInteger</span><span class="sxs-lookup"><span data-stu-id="80271-121">Microsoft.Quantum.Arithmetic.IncrementByInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.IncrementByInteger)