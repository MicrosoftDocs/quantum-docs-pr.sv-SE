---
uid: Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger
title: MultiplyAndAddByModularInteger-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyAndAddByModularInteger
qsharp.summary: Performs a modular multiply-and-add by integer constants on a qubit register.
ms.openlocfilehash: e4de934a5776e80dbf5f0d8334bf806e6a84b743
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846520"
---
# <a name="multiplyandaddbymodularinteger-operation"></a><span data-ttu-id="bcee8-102">MultiplyAndAddByModularInteger-åtgärd</span><span class="sxs-lookup"><span data-stu-id="bcee8-102">MultiplyAndAddByModularInteger operation</span></span>

<span data-ttu-id="bcee8-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="bcee8-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="bcee8-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bcee8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bcee8-105">Utför en modulär multiplicering och lägger till en heltals konstant i ett qubit-register.</span><span class="sxs-lookup"><span data-stu-id="bcee8-105">Performs a modular multiply-and-add by integer constants on a qubit register.</span></span>

```qsharp
operation MultiplyAndAddByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian, summand : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="bcee8-106">Description</span><span class="sxs-lookup"><span data-stu-id="bcee8-106">Description</span></span>

<span data-ttu-id="bcee8-107">Implementerar kartan $ $ \begin{align} \ket{x} \ket{b} \mapsto \ket{x} \ket{(b + a \cdot x) \operatorname{mod} N} \end{align} $ $ för en specifik Modulus $N $, konstant multiplikator $a $ och summand $y $.</span><span class="sxs-lookup"><span data-stu-id="bcee8-107">Implements the map $$ \begin{align} \ket{x} \ket{b} \mapsto \ket{x} \ket{(b + a \cdot x) \operatorname{mod} N} \end{align} $$ for a given modulus $N$, constant multiplier $a$, and summand $y$.</span></span>

## <a name="input"></a><span data-ttu-id="bcee8-108">Indata</span><span class="sxs-lookup"><span data-stu-id="bcee8-108">Input</span></span>

### <a name="constmultiplier--int"></a><span data-ttu-id="bcee8-109">constMultiplier: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="bcee8-109">constMultiplier : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="bcee8-110">Ett heltal som $a $ som ska läggas till i varje tillstånds etikett.</span><span class="sxs-lookup"><span data-stu-id="bcee8-110">An integer $a$ to be added to each basis state label.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="bcee8-111">Modulus: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="bcee8-111">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="bcee8-112">Modulus $N $ som addition och multiplikation tas med avseende på.</span><span class="sxs-lookup"><span data-stu-id="bcee8-112">The modulus $N$ which addition and multiplication is taken with respect to.</span></span>


### <a name="multiplier--littleendian"></a><span data-ttu-id="bcee8-113">multiplikator: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="bcee8-113">multiplier : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="bcee8-114">Ett Quantum-register som representerar ett osignerat heltal vars värde ska läggas till i varje bas tillstånds etikett för `summand` .</span><span class="sxs-lookup"><span data-stu-id="bcee8-114">A quantum register representing an unsigned integer whose value is to be added to each basis state label of `summand`.</span></span>


### <a name="summand--littleendian"></a><span data-ttu-id="bcee8-115">summand: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="bcee8-115">summand : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="bcee8-116">Ett Quantum-register som representerar ett osignerat heltal som används som mål för den här åtgärden.</span><span class="sxs-lookup"><span data-stu-id="bcee8-116">A quantum register representing an unsigned integer to use as the target for this operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bcee8-117">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bcee8-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="bcee8-118">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="bcee8-118">Remarks</span></span>

- <span data-ttu-id="bcee8-119">För krets diagrammet och förklaring, se figur 6 på [sidan 7 i arXiv: Quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=7)</span><span class="sxs-lookup"><span data-stu-id="bcee8-119">For the circuit diagram and explanation see Figure 6 on [Page 7 of arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=7)</span></span>
- <span data-ttu-id="bcee8-120">Den här åtgärden motsvarar CMULT (a) MOD (N) i [arXiv: Quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)</span><span class="sxs-lookup"><span data-stu-id="bcee8-120">This operation corresponds to CMULT(a)MOD(N) in [arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)</span></span>

## <a name="see-also"></a><span data-ttu-id="bcee8-121">Se även</span><span class="sxs-lookup"><span data-stu-id="bcee8-121">See Also</span></span>

- [<span data-ttu-id="bcee8-122">Microsoft. Quantum. aritmetiska. MultiplyAndAddPhaseByModularInteger</span><span class="sxs-lookup"><span data-stu-id="bcee8-122">Microsoft.Quantum.Arithmetic.MultiplyAndAddPhaseByModularInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.MultiplyAndAddPhaseByModularInteger)