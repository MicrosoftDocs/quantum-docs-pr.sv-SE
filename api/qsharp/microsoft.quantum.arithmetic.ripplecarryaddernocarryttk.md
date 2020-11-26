---
uid: Microsoft.Quantum.Arithmetic.RippleCarryAdderNoCarryTTK
title: RippleCarryAdderNoCarryTTK-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: RippleCarryAdderNoCarryTTK
qsharp.summary: Reversible, in-place ripple-carry addition of two integers without carry out.
ms.openlocfilehash: a539d85a4800c2f4452a1c6fe2c4f88a6296c3e1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222005"
---
# <a name="ripplecarryaddernocarryttk-operation"></a><span data-ttu-id="c5b47-102">RippleCarryAdderNoCarryTTK-åtgärd</span><span class="sxs-lookup"><span data-stu-id="c5b47-102">RippleCarryAdderNoCarryTTK operation</span></span>

<span data-ttu-id="c5b47-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="c5b47-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="c5b47-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c5b47-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c5b47-105">Reversibel, på plats krusning – tillsats av två heltal utan att utföra.</span><span class="sxs-lookup"><span data-stu-id="c5b47-105">Reversible, in-place ripple-carry addition of two integers without carry out.</span></span>

```qsharp
operation RippleCarryAdderNoCarryTTK (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="c5b47-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="c5b47-106">Description</span></span>

<span data-ttu-id="c5b47-107">Med två $n $-bitars heltal som är kodade i LittleEndian registrerar `xs` och `ys` beräknar åtgärden summan av de två heltalen modulo $2 ^ n $, där $n $ är bit storleken för indata `xs` och `ys` .</span><span class="sxs-lookup"><span data-stu-id="c5b47-107">Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, the operation computes the sum of the two integers modulo $2^n$, where $n$ is the bit size of the inputs `xs` and `ys`.</span></span> <span data-ttu-id="c5b47-108">Den utför inte den framfattande biten.</span><span class="sxs-lookup"><span data-stu-id="c5b47-108">It does not compute the carry out bit.</span></span>

## <a name="input"></a><span data-ttu-id="c5b47-109">Indata</span><span class="sxs-lookup"><span data-stu-id="c5b47-109">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="c5b47-110">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c5b47-110">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="c5b47-111">LittleEndian qubit register encoding First Integer summand.</span><span class="sxs-lookup"><span data-stu-id="c5b47-111">LittleEndian qubit register encoding the first integer summand.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="c5b47-112">gar: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c5b47-112">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="c5b47-113">LittleEndian qubit register encoding det andra heltalet summand har ändrats för att innehålla $n $ minst signifikanta bitar av summan.</span><span class="sxs-lookup"><span data-stu-id="c5b47-113">LittleEndian qubit register encoding the second integer summand, is modified to hold the $n$ least significant bits of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c5b47-114">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c5b47-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="c5b47-115">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="c5b47-115">Remarks</span></span>

<span data-ttu-id="c5b47-116">Den här åtgärden har samma funktioner som RippleCarryAdderTTK, men returnerar inte den andra biten.</span><span class="sxs-lookup"><span data-stu-id="c5b47-116">This operation has the same functionality as RippleCarryAdderTTK but does not return the carry bit.</span></span>

## <a name="references"></a><span data-ttu-id="c5b47-117">Referenser</span><span class="sxs-lookup"><span data-stu-id="c5b47-117">References</span></span>

- <span data-ttu-id="c5b47-118">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum addition-kretsar och obegränsade fläktning", Quantum information och beräkning, Vol. 10, 2010.</span><span class="sxs-lookup"><span data-stu-id="c5b47-118">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Addition Circuits and Unbounded Fan-Out", Quantum Information and Computation, Vol. 10, 2010.</span></span>
  https://arxiv.org/abs/0910.2530