---
uid: Microsoft.Quantum.Arithmetic.MultiplyByModularInteger
title: MultiplyByModularInteger-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyByModularInteger
qsharp.summary: Performs modular multiplication by an integer constant on a qubit register.
ms.openlocfilehash: 080414d208a2a0c114857db8e93efb4cd74a4d8d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222583"
---
# <a name="multiplybymodularinteger-operation"></a><span data-ttu-id="9c583-102">MultiplyByModularInteger-åtgärd</span><span class="sxs-lookup"><span data-stu-id="9c583-102">MultiplyByModularInteger operation</span></span>

<span data-ttu-id="9c583-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="9c583-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="9c583-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9c583-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9c583-105">Utför modulär multiplikation med en heltalskonstant i ett qubit-register.</span><span class="sxs-lookup"><span data-stu-id="9c583-105">Performs modular multiplication by an integer constant on a qubit register.</span></span>

```qsharp
operation MultiplyByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="9c583-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="9c583-106">Description</span></span>

<span data-ttu-id="9c583-107">Låt oss ange `modulus` $N $ och `constMultiplier` $a $.</span><span class="sxs-lookup"><span data-stu-id="9c583-107">Let us denote `modulus` by $N$ and `constMultiplier` by $a$.</span></span>
<span data-ttu-id="9c583-108">Den här åtgärden implementerar sedan en enhetlig åtgärd som definieras av följande karta i beräknings basen: $ $ \begin{align} \ket{y} \mapsto \ket{(a \cdot y) \operatorname{mod} N} \end{align} $ $ för alla $y $ mellan $0 $ och $N-$1.</span><span class="sxs-lookup"><span data-stu-id="9c583-108">Then this operation implements a unitary operation defined by the following map on the computational basis: $$ \begin{align} \ket{y} \mapsto \ket{(a \cdot y) \operatorname{mod} N} \end{align} $$ for all $y$ between $0$ and $N - 1$.</span></span>

## <a name="input"></a><span data-ttu-id="9c583-109">Indata</span><span class="sxs-lookup"><span data-stu-id="9c583-109">Input</span></span>

### <a name="constmultiplier--int"></a><span data-ttu-id="9c583-110">constMultiplier: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9c583-110">constMultiplier : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9c583-111">Konstant enligt vilken multiplikatorn multipliceras.</span><span class="sxs-lookup"><span data-stu-id="9c583-111">Constant by which multiplier is being multiplied.</span></span> <span data-ttu-id="9c583-112">Måste vara co-primtal till Modulus.</span><span class="sxs-lookup"><span data-stu-id="9c583-112">Must be co-prime to modulus.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="9c583-113">Modulus: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9c583-113">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9c583-114">Multiplikations åtgärden utförs med modulo `modulus` .</span><span class="sxs-lookup"><span data-stu-id="9c583-114">The multiplication operation is performed modulo `modulus`.</span></span>


### <a name="multiplier--littleendian"></a><span data-ttu-id="9c583-115">multiplikator: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="9c583-115">multiplier : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="9c583-116">Talet multipliceras med en konstant.</span><span class="sxs-lookup"><span data-stu-id="9c583-116">The number being multiplied by a constant.</span></span>
<span data-ttu-id="9c583-117">Detta är en matris med qubits som kodar ett heltal i format med liten endian.</span><span class="sxs-lookup"><span data-stu-id="9c583-117">This is an array of qubits encoding an integer in little-endian format.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9c583-118">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9c583-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="9c583-119">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="9c583-119">Remarks</span></span>

- <span data-ttu-id="9c583-120">För krets diagrammet och förklaring, se figur 7 på [sidan 8 av arXiv: Quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=8)</span><span class="sxs-lookup"><span data-stu-id="9c583-120">For the circuit diagram and explanation see Figure 7 on [Page 8 of arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=8)</span></span>
- <span data-ttu-id="9c583-121">Den här åtgärden motsvarar U ₐ i [arXiv: Quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)</span><span class="sxs-lookup"><span data-stu-id="9c583-121">This operation corresponds to Uₐ in [arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)</span></span>