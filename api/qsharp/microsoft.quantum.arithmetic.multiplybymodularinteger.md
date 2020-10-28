---
uid: Microsoft.Quantum.Arithmetic.MultiplyByModularInteger
title: MultiplyByModularInteger-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyByModularInteger
qsharp.summary: Performs modular multiplication by an integer constant on a qubit register.
ms.openlocfilehash: 6deced7862ab4cb74315219eaaab97380cdf0f92
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730630"
---
# <a name="multiplybymodularinteger-operation"></a><span data-ttu-id="c4c8c-102">MultiplyByModularInteger-åtgärd</span><span class="sxs-lookup"><span data-stu-id="c4c8c-102">MultiplyByModularInteger operation</span></span>

<span data-ttu-id="c4c8c-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="c4c8c-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="c4c8c-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c4c8c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c4c8c-105">Utför modulär multiplikation med en heltalskonstant i ett qubit-register.</span><span class="sxs-lookup"><span data-stu-id="c4c8c-105">Performs modular multiplication by an integer constant on a qubit register.</span></span>

```qsharp
operation MultiplyByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="c4c8c-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="c4c8c-106">Description</span></span>

<span data-ttu-id="c4c8c-107">Låt oss ange `modulus` $N $ och `constMultiplier` $a $.</span><span class="sxs-lookup"><span data-stu-id="c4c8c-107">Let us denote `modulus` by $N$ and `constMultiplier` by $a$.</span></span>
<span data-ttu-id="c4c8c-108">Den här åtgärden implementerar sedan en enhetlig åtgärd som definieras av följande karta i beräknings basen: $ $ \begin{align} \ket{y} \mapsto \ket{(a \cdot y) \operatorname{mod} N} \end{align} $ $ för alla $y $ mellan $0 $ och $N-$1.</span><span class="sxs-lookup"><span data-stu-id="c4c8c-108">Then this operation implements a unitary operation defined by the following map on the computational basis: $$ \begin{align} \ket{y} \mapsto \ket{(a \cdot y) \operatorname{mod} N} \end{align} $$ for all $y$ between $0$ and $N - 1$.</span></span>

## <a name="input"></a><span data-ttu-id="c4c8c-109">Indata</span><span class="sxs-lookup"><span data-stu-id="c4c8c-109">Input</span></span>

### <a name="constmultiplier--int"></a><span data-ttu-id="c4c8c-110">constMultiplier: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c4c8c-110">constMultiplier : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c4c8c-111">Konstant enligt vilken multiplikatorn multipliceras.</span><span class="sxs-lookup"><span data-stu-id="c4c8c-111">Constant by which multiplier is being multiplied.</span></span> <span data-ttu-id="c4c8c-112">Måste vara co-primtal till Modulus.</span><span class="sxs-lookup"><span data-stu-id="c4c8c-112">Must be co-prime to modulus.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="c4c8c-113">Modulus: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c4c8c-113">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c4c8c-114">Multiplikations åtgärden utförs med modulo `modulus` .</span><span class="sxs-lookup"><span data-stu-id="c4c8c-114">The multiplication operation is performed modulo `modulus`.</span></span>


### <a name="multiplier--littleendian"></a><span data-ttu-id="c4c8c-115">multiplikator: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c4c8c-115">multiplier : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="c4c8c-116">Talet multipliceras med en konstant.</span><span class="sxs-lookup"><span data-stu-id="c4c8c-116">The number being multiplied by a constant.</span></span>
<span data-ttu-id="c4c8c-117">Detta är en matris med qubits som kodar ett heltal i format med liten endian.</span><span class="sxs-lookup"><span data-stu-id="c4c8c-117">This is an array of qubits encoding an integer in little-endian format.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c4c8c-118">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c4c8c-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="c4c8c-119">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="c4c8c-119">Remarks</span></span>

- <span data-ttu-id="c4c8c-120">För krets diagrammet och förklaring, se figur 7 på [sidan 8 av arXiv: Quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=8)</span><span class="sxs-lookup"><span data-stu-id="c4c8c-120">For the circuit diagram and explanation see Figure 7 on [Page 8 of arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=8)</span></span>
- <span data-ttu-id="c4c8c-121">Den här åtgärden motsvarar U ₐ i [arXiv: Quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)</span><span class="sxs-lookup"><span data-stu-id="c4c8c-121">This operation corresponds to Uₐ in [arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)</span></span>