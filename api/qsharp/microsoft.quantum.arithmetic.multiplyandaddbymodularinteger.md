---
uid: Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger
title: MultiplyAndAddByModularInteger-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyAndAddByModularInteger
qsharp.summary: Performs a modular multiply-and-add by integer constants on a qubit register.
ms.openlocfilehash: 3f85f6aaea1d6f8095709c6f387322df7a5e047c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730643"
---
# <a name="multiplyandaddbymodularinteger-operation"></a><span data-ttu-id="33887-102">MultiplyAndAddByModularInteger-åtgärd</span><span class="sxs-lookup"><span data-stu-id="33887-102">MultiplyAndAddByModularInteger operation</span></span>

<span data-ttu-id="33887-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="33887-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="33887-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="33887-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="33887-105">Utför en modulär multiplicering och lägger till en heltals konstant i ett qubit-register.</span><span class="sxs-lookup"><span data-stu-id="33887-105">Performs a modular multiply-and-add by integer constants on a qubit register.</span></span>

```qsharp
operation MultiplyAndAddByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian, summand : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="33887-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="33887-106">Description</span></span>

<span data-ttu-id="33887-107">Implementerar kartan $ $ \begin{align} \ket{x} \ket{b} \mapsto \ket{x} \ket{(b + a \cdot x) \operatorname{mod} N} \end{align} $ $ för en specifik Modulus $N $, konstant multiplikator $a $ och summand $y $.</span><span class="sxs-lookup"><span data-stu-id="33887-107">Implements the map $$ \begin{align} \ket{x} \ket{b} \mapsto \ket{x} \ket{(b + a \cdot x) \operatorname{mod} N} \end{align} $$ for a given modulus $N$, constant multiplier $a$, and summand $y$.</span></span>

## <a name="input"></a><span data-ttu-id="33887-108">Indata</span><span class="sxs-lookup"><span data-stu-id="33887-108">Input</span></span>

### <a name="constmultiplier--int"></a><span data-ttu-id="33887-109">constMultiplier: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="33887-109">constMultiplier : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="33887-110">Ett heltal som $a $ som ska läggas till i varje tillstånds etikett.</span><span class="sxs-lookup"><span data-stu-id="33887-110">An integer $a$ to be added to each basis state label.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="33887-111">Modulus: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="33887-111">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="33887-112">Modulus $N $ som addition och multiplikation tas med avseende på.</span><span class="sxs-lookup"><span data-stu-id="33887-112">The modulus $N$ which addition and multiplication is taken with respect to.</span></span>


### <a name="multiplier--littleendian"></a><span data-ttu-id="33887-113">multiplikator: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="33887-113">multiplier : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="33887-114">Ett Quantum-register som representerar ett osignerat heltal vars värde ska läggas till i varje bas tillstånds etikett för `summand` .</span><span class="sxs-lookup"><span data-stu-id="33887-114">A quantum register representing an unsigned integer whose value is to be added to each basis state label of `summand`.</span></span>


### <a name="summand--littleendian"></a><span data-ttu-id="33887-115">summand: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="33887-115">summand : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="33887-116">Ett Quantum-register som representerar ett osignerat heltal som används som mål för den här åtgärden.</span><span class="sxs-lookup"><span data-stu-id="33887-116">A quantum register representing an unsigned integer to use as the target for this operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="33887-117">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="33887-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="33887-118">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="33887-118">Remarks</span></span>

- <span data-ttu-id="33887-119">För krets diagrammet och förklaring, se figur 6 på [sidan 7 i arXiv: Quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=7)</span><span class="sxs-lookup"><span data-stu-id="33887-119">For the circuit diagram and explanation see Figure 6 on [Page 7 of arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=7)</span></span>
- <span data-ttu-id="33887-120">Den här åtgärden motsvarar CMULT (a) MOD (N) i [arXiv: Quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)</span><span class="sxs-lookup"><span data-stu-id="33887-120">This operation corresponds to CMULT(a)MOD(N) in [arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)</span></span>

## <a name="see-also"></a><span data-ttu-id="33887-121">Se även</span><span class="sxs-lookup"><span data-stu-id="33887-121">See Also</span></span>

- [<span data-ttu-id="33887-122">Microsoft. Quantum. aritmetiska. MultiplyAndAddPhaseByModularInteger</span><span class="sxs-lookup"><span data-stu-id="33887-122">Microsoft.Quantum.Arithmetic.MultiplyAndAddPhaseByModularInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.MultiplyAndAddPhaseByModularInteger)