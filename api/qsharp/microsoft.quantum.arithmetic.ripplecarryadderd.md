---
uid: Microsoft.Quantum.Arithmetic.RippleCarryAdderD
title: RippleCarryAdderD-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: RippleCarryAdderD
qsharp.summary: Reversible, in-place ripple-carry addition of two integers. Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, and a qubit carry, the operation computes the sum of the two integers where the $n$ least significant bits of the result are held in `ys` and the carry out bit is xored to the qubit `carry`.
ms.openlocfilehash: c4466feebb8ff6afcdcb5bf385ec10e807c00537
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730494"
---
# <a name="ripplecarryadderd-operation"></a><span data-ttu-id="47e0d-102">RippleCarryAdderD-åtgärd</span><span class="sxs-lookup"><span data-stu-id="47e0d-102">RippleCarryAdderD operation</span></span>

<span data-ttu-id="47e0d-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="47e0d-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="47e0d-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="47e0d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="47e0d-105">Reversibel, "på plats"-tillägg av två heltal.</span><span class="sxs-lookup"><span data-stu-id="47e0d-105">Reversible, in-place ripple-carry addition of two integers.</span></span>
<span data-ttu-id="47e0d-106">Med två $n $-bitars heltal som är kodade i `xs` LittleEndian `ys` -registren och, och en qubit-aktivitet, beräknar åtgärden summan av de två heltalen där $n $ minst signifikanta bitar av resultatet hålls i `ys` och den sammanställda biten är XoReD till qubit `carry` .</span><span class="sxs-lookup"><span data-stu-id="47e0d-106">Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, and a qubit carry, the operation computes the sum of the two integers where the $n$ least significant bits of the result are held in `ys` and the carry out bit is xored to the qubit `carry`.</span></span>

```qsharp
operation RippleCarryAdderD (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, carry : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="47e0d-107">Indata</span><span class="sxs-lookup"><span data-stu-id="47e0d-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="47e0d-108">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="47e0d-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="47e0d-109">LittleEndian qubit register encoding First Integer summand.</span><span class="sxs-lookup"><span data-stu-id="47e0d-109">LittleEndian qubit register encoding the first integer summand.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="47e0d-110">gar: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="47e0d-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="47e0d-111">LittleEndian qubit register encoding det andra heltalet summand har ändrats för att innehålla $n $ minst signifikanta bitar av summan.</span><span class="sxs-lookup"><span data-stu-id="47e0d-111">LittleEndian qubit register encoding the second integer summand, is modified to hold the $n$ least significant bits of the sum.</span></span>


### <a name="carry--qubit"></a><span data-ttu-id="47e0d-112">bär: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="47e0d-112">carry : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="47e0d-113">Bär qubit, är XoReD med den mest signifikanta biten av summan.</span><span class="sxs-lookup"><span data-stu-id="47e0d-113">Carry qubit, is xored with the most significant bit of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="47e0d-114">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="47e0d-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="47e0d-115">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="47e0d-115">Remarks</span></span>

<span data-ttu-id="47e0d-116">Den angivna kontrollerade åtgärden använder symmetri och ömsesidig annullering av åtgärder för att förbättra standard implementeringen som lägger till en kontroll i varje åtgärd.</span><span class="sxs-lookup"><span data-stu-id="47e0d-116">The specified controlled operation makes use of symmetry and mutual cancellation of operations to improve on the default implementation that adds a control to every operation.</span></span>

## <a name="references"></a><span data-ttu-id="47e0d-117">Referenser</span><span class="sxs-lookup"><span data-stu-id="47e0d-117">References</span></span>

- <span data-ttu-id="47e0d-118">Thomas G. Draper: "addition på en Quantum-dator", 2000.</span><span class="sxs-lookup"><span data-stu-id="47e0d-118">Thomas G. Draper: "Addition on a Quantum Computer", 2000.</span></span>
  https://arxiv.org/abs/quant-ph/0008033