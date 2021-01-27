---
uid: Microsoft.Quantum.Arithmetic.ApplyInnerTTKAdder
title: ApplyInnerTTKAdder-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyInnerTTKAdder
qsharp.summary: Implements the inner addition function for the operation RippleCarryAdderTTK. This is the inner operation that is conjugated with the outer operation to construct the full adder.
ms.openlocfilehash: c822933340d592061eb039af7c6e438212abc265
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843838"
---
# <a name="applyinnerttkadder-operation"></a><span data-ttu-id="0821e-102">ApplyInnerTTKAdder-åtgärd</span><span class="sxs-lookup"><span data-stu-id="0821e-102">ApplyInnerTTKAdder operation</span></span>

<span data-ttu-id="0821e-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="0821e-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="0821e-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0821e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0821e-105">Implementerar funktionen inre addition för åtgärden RippleCarryAdderTTK.</span><span class="sxs-lookup"><span data-stu-id="0821e-105">Implements the inner addition function for the operation RippleCarryAdderTTK.</span></span> <span data-ttu-id="0821e-106">Det här är den inre åtgärd som är konjugaten med den yttre åtgärden för att skapa en fullständig egenskapsangivning.</span><span class="sxs-lookup"><span data-stu-id="0821e-106">This is the inner operation that is conjugated with the outer operation to construct the full adder.</span></span>

```qsharp
operation ApplyInnerTTKAdder (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, carry : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="0821e-107">Indata</span><span class="sxs-lookup"><span data-stu-id="0821e-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="0821e-108">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="0821e-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="0821e-109">LittleEndian qubit registrera det första heltalet summand inmatat på RippleCarryAdderTTK.</span><span class="sxs-lookup"><span data-stu-id="0821e-109">LittleEndian qubit register encoding the first integer summand input to RippleCarryAdderTTK.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="0821e-110">gar: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="0821e-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="0821e-111">LittleEndian qubit registrera det andra heltalet summand inmatat på RippleCarryAdderTTK.</span><span class="sxs-lookup"><span data-stu-id="0821e-111">LittleEndian qubit register encoding the second integer summand input to RippleCarryAdderTTK.</span></span>


### <a name="carry--qubit"></a><span data-ttu-id="0821e-112">bär: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="0821e-112">carry : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="0821e-113">Bär qubit, är XoReD med den mest signifikanta biten av summan.</span><span class="sxs-lookup"><span data-stu-id="0821e-113">Carry qubit, is xored with the most significant bit of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0821e-114">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0821e-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="0821e-115">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="0821e-115">Remarks</span></span>

<span data-ttu-id="0821e-116">Den angivna kontrollerade åtgärden använder symmetri och ömsesidig annullering av åtgärder för att förbättra standard implementeringen som lägger till en kontroll i varje åtgärd.</span><span class="sxs-lookup"><span data-stu-id="0821e-116">The specified controlled operation makes use of symmetry and mutual cancellation of operations to improve on the default implementation that adds a control to every operation.</span></span>

## <a name="references"></a><span data-ttu-id="0821e-117">Referenser</span><span class="sxs-lookup"><span data-stu-id="0821e-117">References</span></span>

- <span data-ttu-id="0821e-118">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum addition-kretsar och obegränsade fläktning", Quantum information och beräkning, Vol. 10, 2010.</span><span class="sxs-lookup"><span data-stu-id="0821e-118">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Addition Circuits and Unbounded Fan-Out", Quantum Information and Computation, Vol. 10, 2010.</span></span>
  https://arxiv.org/abs/0910.2530