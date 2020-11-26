---
uid: Microsoft.Quantum.Arithmetic.MultiplyAndAddPhaseByModularInteger
title: MultiplyAndAddPhaseByModularInteger-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyAndAddPhaseByModularInteger
qsharp.summary: The same as MultiplyAndAddByModularInteger, but assumes that the summand encodes integers in QFT basis.
ms.openlocfilehash: 1ca20b525d2a76e554d5a2e8d4f40060b5ef51cf
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223875"
---
# <a name="multiplyandaddphasebymodularinteger-operation"></a><span data-ttu-id="da8c6-102">MultiplyAndAddPhaseByModularInteger-åtgärd</span><span class="sxs-lookup"><span data-stu-id="da8c6-102">MultiplyAndAddPhaseByModularInteger operation</span></span>

<span data-ttu-id="da8c6-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="da8c6-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="da8c6-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="da8c6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="da8c6-105">Samma som MultiplyAndAddByModularInteger, men förutsätter att summand kodar heltal i QFT-basen.</span><span class="sxs-lookup"><span data-stu-id="da8c6-105">The same as MultiplyAndAddByModularInteger, but assumes that the summand encodes integers in QFT basis.</span></span>

```qsharp
operation MultiplyAndAddPhaseByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian, phaseSummand : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="da8c6-106">Indata</span><span class="sxs-lookup"><span data-stu-id="da8c6-106">Input</span></span>

### <a name="constmultiplier--int"></a><span data-ttu-id="da8c6-107">constMultiplier: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="da8c6-107">constMultiplier : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="da8c6-108">Ett heltal som $a $ som ska läggas till i varje tillstånds etikett.</span><span class="sxs-lookup"><span data-stu-id="da8c6-108">An integer $a$ to be added to each basis state label.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="da8c6-109">Modulus: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="da8c6-109">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="da8c6-110">Modulus $N $ som addition och multiplikation tas med avseende på.</span><span class="sxs-lookup"><span data-stu-id="da8c6-110">The modulus $N$ which addition and multiplication is taken with respect to.</span></span>


### <a name="multiplier--littleendian"></a><span data-ttu-id="da8c6-111">multiplikator: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="da8c6-111">multiplier : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="da8c6-112">Ett Quantum-register som representerar ett osignerat heltal vars värde ska läggas till i varje bas tillstånds etikett för `summand` .</span><span class="sxs-lookup"><span data-stu-id="da8c6-112">A quantum register representing an unsigned integer whose value is to be added to each basis state label of `summand`.</span></span>


### <a name="phasesummand--phaselittleendian"></a><span data-ttu-id="da8c6-113">phaseSummand: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="da8c6-113">phaseSummand : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="da8c6-114">Ett Quantum-register som representerar ett osignerat heltal som används som mål för den här åtgärden.</span><span class="sxs-lookup"><span data-stu-id="da8c6-114">A quantum register representing an unsigned integer to use as the target for this operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="da8c6-115">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="da8c6-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="da8c6-116">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="da8c6-116">Remarks</span></span>

<span data-ttu-id="da8c6-117">Förutsätter att `phaseSummand` har den högsta bit inställningen 0.</span><span class="sxs-lookup"><span data-stu-id="da8c6-117">Assumes that `phaseSummand` has the highest bit set to 0.</span></span>
<span data-ttu-id="da8c6-118">Förutsätter också att värdet för `phaseSummand` är mindre än $N $.</span><span class="sxs-lookup"><span data-stu-id="da8c6-118">Also assumes that the value of `phaseSummand` is less than $N$.</span></span>

## <a name="see-also"></a><span data-ttu-id="da8c6-119">Se även</span><span class="sxs-lookup"><span data-stu-id="da8c6-119">See Also</span></span>

- [<span data-ttu-id="da8c6-120">Microsoft. Quantum. aritmetiska. MultiplyAndAddByModularInteger</span><span class="sxs-lookup"><span data-stu-id="da8c6-120">Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger)