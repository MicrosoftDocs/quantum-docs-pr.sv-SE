---
uid: Microsoft.Quantum.Arithmetic.IncrementPhaseByModularInteger
title: IncrementPhaseByModularInteger-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementPhaseByModularInteger
qsharp.summary: Performs a modular increment of a qubit register by an integer constant.
ms.openlocfilehash: 52309c056a3eae25ffdfbfa848f94bf744c71132
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731475"
---
# <a name="incrementphasebymodularinteger-operation"></a><span data-ttu-id="f52c2-102">IncrementPhaseByModularInteger-åtgärd</span><span class="sxs-lookup"><span data-stu-id="f52c2-102">IncrementPhaseByModularInteger operation</span></span>

<span data-ttu-id="f52c2-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="f52c2-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="f52c2-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f52c2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f52c2-105">Utför en modulär ökning av ett qubit-register med en heltalskonstant.</span><span class="sxs-lookup"><span data-stu-id="f52c2-105">Performs a modular increment of a qubit register by an integer constant.</span></span>

```qsharp
operation IncrementPhaseByModularInteger (increment : Int, modulus : Int, target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="f52c2-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="f52c2-106">Description</span></span>

<span data-ttu-id="f52c2-107">Låt oss ange `increment` $a $, `modulus` genom att $N $ och Integer som är kodat i `target` $y $.</span><span class="sxs-lookup"><span data-stu-id="f52c2-107">Let us denote `increment` by $a$, `modulus` by $N$ and integer encoded in `target` by $y$.</span></span>
<span data-ttu-id="f52c2-108">Åtgärden utför sedan följande omvandling: \begin{align} \ket{y} \mapsto \ket{(y + a) \operatorname{mod} N} \end{align} heltal kodas i litet endian-format i QFT.</span><span class="sxs-lookup"><span data-stu-id="f52c2-108">Then the operation performs the following transformation: \begin{align} \ket{y} \mapsto \ket{(y + a) \operatorname{mod} N} \end{align} Integers are encoded in little-endian format in QFT basis.</span></span>

## <a name="input"></a><span data-ttu-id="f52c2-109">Indata</span><span class="sxs-lookup"><span data-stu-id="f52c2-109">Input</span></span>

### <a name="increment--int"></a><span data-ttu-id="f52c2-110">ökning: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f52c2-110">increment : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f52c2-111">Heltals ökning $a $ som ska läggas till i $y $.</span><span class="sxs-lookup"><span data-stu-id="f52c2-111">Integer increment $a$ to be added to $y$.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="f52c2-112">Modulus: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f52c2-112">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f52c2-113">Integer $N $ som mods $y + a $.</span><span class="sxs-lookup"><span data-stu-id="f52c2-113">Integer $N$ that mods $y + a$.</span></span>


### <a name="target--phaselittleendian"></a><span data-ttu-id="f52c2-114">mål: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="f52c2-114">target : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="f52c2-115">Integer $y $ i fas-kodat litet endian-format som `increment` $a $ läggs till i.</span><span class="sxs-lookup"><span data-stu-id="f52c2-115">Integer $y$ in phase-encoded little-endian format that `increment` $a$ is added to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f52c2-116">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f52c2-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="f52c2-117">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="f52c2-117">Remarks</span></span>

<span data-ttu-id="f52c2-118">Förutsätter att `target` har den högsta bit inställningen 0.</span><span class="sxs-lookup"><span data-stu-id="f52c2-118">Assumes that `target` has the highest bit set to 0.</span></span>
<span data-ttu-id="f52c2-119">Förutsätter också att målets värde är mindre än $N $.</span><span class="sxs-lookup"><span data-stu-id="f52c2-119">Also assumes that the value of target is less than $N$.</span></span>

<span data-ttu-id="f52c2-120">För krets diagrammet och förklaringen, se figur 5 på [sidan 5 i arXiv: Quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=5).</span><span class="sxs-lookup"><span data-stu-id="f52c2-120">For the circuit diagram and explanation see Figure 5 on [Page 5 of arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=5).</span></span>

## <a name="see-also"></a><span data-ttu-id="f52c2-121">Se även</span><span class="sxs-lookup"><span data-stu-id="f52c2-121">See Also</span></span>

- [<span data-ttu-id="f52c2-122">Microsoft. Quantum. aritmetiska. IncrementByModularInteger</span><span class="sxs-lookup"><span data-stu-id="f52c2-122">Microsoft.Quantum.Arithmetic.IncrementByModularInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.IncrementByModularInteger)