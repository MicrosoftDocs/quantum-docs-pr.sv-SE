---
uid: Microsoft.Quantum.Arithmetic.IncrementPhaseByInteger
title: IncrementPhaseByInteger-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementPhaseByInteger
qsharp.summary: Increments an unsigned quantum register by a classical integer, using phase rotations.
ms.openlocfilehash: fb67455dadbc7a2f38880581f0e413a747faa8ef
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731486"
---
# <a name="incrementphasebyinteger-operation"></a><span data-ttu-id="5fcb6-102">IncrementPhaseByInteger-åtgärd</span><span class="sxs-lookup"><span data-stu-id="5fcb6-102">IncrementPhaseByInteger operation</span></span>

<span data-ttu-id="5fcb6-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="5fcb6-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="5fcb6-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5fcb6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5fcb6-105">Ökar en osignerad Quantum-registrering med ett klassiskt heltal med hjälp av fas rotationer.</span><span class="sxs-lookup"><span data-stu-id="5fcb6-105">Increments an unsigned quantum register by a classical integer, using phase rotations.</span></span>

```qsharp
operation IncrementPhaseByInteger (increment : Int, target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="5fcb6-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="5fcb6-106">Description</span></span>

<span data-ttu-id="5fcb6-107">Anta att `target` koda ett osignerat heltal $x $ i en lite-endian-kodning och att det `increment` motsvarar $a $.</span><span class="sxs-lookup"><span data-stu-id="5fcb6-107">Suppose that `target` encodes an unsigned integer $x$ in a little-endian encoding and that `increment` is equal to $a$.</span></span>
<span data-ttu-id="5fcb6-108">Den här åtgärden implementerar sedan den enhetliga $ \ket{x} \mapsto \ket{x + a} $, där additionen utförs med modulo $2 ^ n $, där $n = \texttt{Length (Target!)} $.</span><span class="sxs-lookup"><span data-stu-id="5fcb6-108">Then, this operation implements the unitary $\ket{x} \mapsto \ket{x + a}$, where the addition is performed modulo $2^n$, where $n = \texttt{Length(target!)}$.</span></span>

## <a name="input"></a><span data-ttu-id="5fcb6-109">Indata</span><span class="sxs-lookup"><span data-stu-id="5fcb6-109">Input</span></span>

### <a name="increment--int"></a><span data-ttu-id="5fcb6-110">ökning: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5fcb6-110">increment : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5fcb6-111">Det heltal som `target` ökar med.</span><span class="sxs-lookup"><span data-stu-id="5fcb6-111">The integer by which the `target` is incremented by.</span></span>


### <a name="target--phaselittleendian"></a><span data-ttu-id="5fcb6-112">mål: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="5fcb6-112">target : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="5fcb6-113">Ett Quantum-register som kodar ett osignerat heltal med lite endian-kodning i dubbel (QFT)-grunden.</span><span class="sxs-lookup"><span data-stu-id="5fcb6-113">A quantum register encoding an unsigned integer using little-endian encoding in the dual (QFT) basis.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5fcb6-114">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5fcb6-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="5fcb6-115">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="5fcb6-115">Remarks</span></span>

<span data-ttu-id="5fcb6-116">Observera att vi har förenklat kretsen eftersom ökningen är en klassisk konstant, inte ett Quantum-register.</span><span class="sxs-lookup"><span data-stu-id="5fcb6-116">Note that we have simplified the circuit because the increment is a classical constant, not a quantum register.</span></span>

<span data-ttu-id="5fcb6-117">Se figuren på [ sidan 6 i arXiv: Quant-pH/0008033v1 ](https://arxiv.org/pdf/quant-ph/0008033.pdf#page=6) för krets diagrammet och förklaringen.</span><span class="sxs-lookup"><span data-stu-id="5fcb6-117">See the figure on [ Page 6 of arXiv:quant-ph/0008033v1 ](https://arxiv.org/pdf/quant-ph/0008033.pdf#page=6) for the circuit diagram and explanation.</span></span>

## <a name="references"></a><span data-ttu-id="5fcb6-118">Referenser</span><span class="sxs-lookup"><span data-stu-id="5fcb6-118">References</span></span>

- [<span data-ttu-id="5fcb6-119">*Thomas G. Draper* , arXiv: Quant-pH/0008033</span><span class="sxs-lookup"><span data-stu-id="5fcb6-119"> *Thomas G. Draper* , arXiv:quant-ph/0008033</span></span>](https://arxiv.org/pdf/quant-ph/0008033v1.pdf)

## <a name="see-also"></a><span data-ttu-id="5fcb6-120">Se även</span><span class="sxs-lookup"><span data-stu-id="5fcb6-120">See Also</span></span>

- [<span data-ttu-id="5fcb6-121">Microsoft. Quantum. aritmetiska. IncrementByInteger</span><span class="sxs-lookup"><span data-stu-id="5fcb6-121">Microsoft.Quantum.Arithmetic.IncrementByInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.IncrementByInteger)