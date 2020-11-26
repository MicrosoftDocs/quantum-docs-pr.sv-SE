---
uid: Microsoft.Quantum.Arithmetic.RippleCarryAdderTTK
title: RippleCarryAdderTTK-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: RippleCarryAdderTTK
qsharp.summary: Reversible, in-place ripple-carry addition of two integers. Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, and a qubit carry, the operation computes the sum of the two integers where the $n$ least significant bits of the result are held in `ys` and the carry out bit is xored to the qubit `carry`.
ms.openlocfilehash: 45ba1b644166029ee548307cc1a7290c48e48a4b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221953"
---
# <a name="ripplecarryadderttk-operation"></a><span data-ttu-id="7c67a-102">RippleCarryAdderTTK-åtgärd</span><span class="sxs-lookup"><span data-stu-id="7c67a-102">RippleCarryAdderTTK operation</span></span>

<span data-ttu-id="7c67a-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="7c67a-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="7c67a-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7c67a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7c67a-105">Reversibel, "på plats"-tillägg av två heltal.</span><span class="sxs-lookup"><span data-stu-id="7c67a-105">Reversible, in-place ripple-carry addition of two integers.</span></span>
<span data-ttu-id="7c67a-106">Med två $n $-bitars heltal som är kodade i `xs` LittleEndian `ys` -registren och, och en qubit-aktivitet, beräknar åtgärden summan av de två heltalen där $n $ minst signifikanta bitar av resultatet hålls i `ys` och den sammanställda biten är XoReD till qubit `carry` .</span><span class="sxs-lookup"><span data-stu-id="7c67a-106">Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, and a qubit carry, the operation computes the sum of the two integers where the $n$ least significant bits of the result are held in `ys` and the carry out bit is xored to the qubit `carry`.</span></span>

```qsharp
operation RippleCarryAdderTTK (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, carry : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="7c67a-107">Indata</span><span class="sxs-lookup"><span data-stu-id="7c67a-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="7c67a-108">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="7c67a-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="7c67a-109">LittleEndian qubit register encoding First Integer summand.</span><span class="sxs-lookup"><span data-stu-id="7c67a-109">LittleEndian qubit register encoding the first integer summand.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="7c67a-110">gar: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="7c67a-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="7c67a-111">LittleEndian qubit register encoding det andra heltalet summand har ändrats för att innehålla $n $ minst signifikanta bitar av summan.</span><span class="sxs-lookup"><span data-stu-id="7c67a-111">LittleEndian qubit register encoding the second integer summand, is modified to hold the $n$ least significant bits of the sum.</span></span>


### <a name="carry--qubit"></a><span data-ttu-id="7c67a-112">bär: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="7c67a-112">carry : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="7c67a-113">Bär qubit, är XoReD med den mest signifikanta biten av summan.</span><span class="sxs-lookup"><span data-stu-id="7c67a-113">Carry qubit, is xored with the most significant bit of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7c67a-114">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7c67a-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="7c67a-115">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="7c67a-115">Remarks</span></span>

<span data-ttu-id="7c67a-116">Den här åtgärden har samma funktioner som RippleCarryAdderD och RippleCarryAdderCDKM men använder inte några Ancilla-qubits.</span><span class="sxs-lookup"><span data-stu-id="7c67a-116">This operation has the same functionality as RippleCarryAdderD and, RippleCarryAdderCDKM but does not use any ancilla qubits.</span></span>

## <a name="references"></a><span data-ttu-id="7c67a-117">Referenser</span><span class="sxs-lookup"><span data-stu-id="7c67a-117">References</span></span>

- <span data-ttu-id="7c67a-118">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum addition-kretsar och obegränsade fläktning", Quantum information och beräkning, Vol. 10, 2010.</span><span class="sxs-lookup"><span data-stu-id="7c67a-118">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Addition Circuits and Unbounded Fan-Out", Quantum Information and Computation, Vol. 10, 2010.</span></span>
  https://arxiv.org/abs/0910.2530