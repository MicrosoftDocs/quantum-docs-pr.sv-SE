---
uid: Microsoft.Quantum.Arithmetic.ApplyInnerTTKAdderWithoutCarry
title: ApplyInnerTTKAdderWithoutCarry-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyInnerTTKAdderWithoutCarry
qsharp.summary: Implements the inner addition function for the operation RippleCarryAdderNoCarryTTK. This is the inner operation that is conjugated with the outer operation to construct the full adder.
ms.openlocfilehash: 0c1626c788215181b5ed45dc98bed928b5e4848a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843812"
---
# <a name="applyinnerttkadderwithoutcarry-operation"></a><span data-ttu-id="ed8fd-102">ApplyInnerTTKAdderWithoutCarry-åtgärd</span><span class="sxs-lookup"><span data-stu-id="ed8fd-102">ApplyInnerTTKAdderWithoutCarry operation</span></span>

<span data-ttu-id="ed8fd-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="ed8fd-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="ed8fd-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ed8fd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ed8fd-105">Implementerar funktionen inre addition för åtgärden RippleCarryAdderNoCarryTTK.</span><span class="sxs-lookup"><span data-stu-id="ed8fd-105">Implements the inner addition function for the operation RippleCarryAdderNoCarryTTK.</span></span> <span data-ttu-id="ed8fd-106">Det här är den inre åtgärd som är konjugaten med den yttre åtgärden för att skapa en fullständig egenskapsangivning.</span><span class="sxs-lookup"><span data-stu-id="ed8fd-106">This is the inner operation that is conjugated with the outer operation to construct the full adder.</span></span>

```qsharp
operation ApplyInnerTTKAdderWithoutCarry (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="ed8fd-107">Indata</span><span class="sxs-lookup"><span data-stu-id="ed8fd-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="ed8fd-108">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="ed8fd-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="ed8fd-109">LittleEndian qubit registrera det första heltalet summand inmatat på RippleCarryAdderNoCarryTTK.</span><span class="sxs-lookup"><span data-stu-id="ed8fd-109">LittleEndian qubit register encoding the first integer summand input to RippleCarryAdderNoCarryTTK.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="ed8fd-110">gar: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="ed8fd-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="ed8fd-111">LittleEndian qubit registrera det andra heltalet summand inmatat på RippleCarryAdderNoCarryTTK.</span><span class="sxs-lookup"><span data-stu-id="ed8fd-111">LittleEndian qubit register encoding the second integer summand input to RippleCarryAdderNoCarryTTK.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ed8fd-112">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ed8fd-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="ed8fd-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="ed8fd-113">Remarks</span></span>

<span data-ttu-id="ed8fd-114">Den angivna kontrollerade åtgärden använder symmetri och ömsesidig annullering av åtgärder för att förbättra standard implementeringen som lägger till en kontroll i varje åtgärd.</span><span class="sxs-lookup"><span data-stu-id="ed8fd-114">The specified controlled operation makes use of symmetry and mutual cancellation of operations to improve on the default implementation that adds a control to every operation.</span></span>

## <a name="references"></a><span data-ttu-id="ed8fd-115">Referenser</span><span class="sxs-lookup"><span data-stu-id="ed8fd-115">References</span></span>

- <span data-ttu-id="ed8fd-116">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum addition-kretsar och obegränsade fläktning", Quantum information och beräkning, Vol. 10, 2010.</span><span class="sxs-lookup"><span data-stu-id="ed8fd-116">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Addition Circuits and Unbounded Fan-Out", Quantum Information and Computation, Vol. 10, 2010.</span></span>
  https://arxiv.org/abs/0910.2530