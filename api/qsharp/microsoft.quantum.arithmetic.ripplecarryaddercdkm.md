---
uid: Microsoft.Quantum.Arithmetic.RippleCarryAdderCDKM
title: RippleCarryAdderCDKM-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: RippleCarryAdderCDKM
qsharp.summary: Reversible, in-place ripple-carry addition of two integers.
ms.openlocfilehash: b08d8823fd539263205aca1ee15ee69adcb163b7
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222107"
---
# <a name="ripplecarryaddercdkm-operation"></a><span data-ttu-id="9264b-102">RippleCarryAdderCDKM-åtgärd</span><span class="sxs-lookup"><span data-stu-id="9264b-102">RippleCarryAdderCDKM operation</span></span>

<span data-ttu-id="9264b-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="9264b-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="9264b-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9264b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9264b-105">Reversibel, "på plats"-tillägg av två heltal.</span><span class="sxs-lookup"><span data-stu-id="9264b-105">Reversible, in-place ripple-carry addition of two integers.</span></span>

```qsharp
operation RippleCarryAdderCDKM (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, carry : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="9264b-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="9264b-106">Description</span></span>

<span data-ttu-id="9264b-107">Med två $n $-bitars heltal som är kodade i `xs` LittleEndian `ys` -registren och, och en qubit-aktivitet, beräknar åtgärden summan av de två heltalen där $n $ minst signifikanta bitar av resultatet hålls i `ys` och den sammanställda biten är XoReD till qubit `carry` .</span><span class="sxs-lookup"><span data-stu-id="9264b-107">Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, and a qubit carry, the operation computes the sum of the two integers where the $n$ least significant bits of the result are held in `ys` and the carry out bit is xored to the qubit `carry`.</span></span>

## <a name="input"></a><span data-ttu-id="9264b-108">Indata</span><span class="sxs-lookup"><span data-stu-id="9264b-108">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="9264b-109">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="9264b-109">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="9264b-110">LittleEndian qubit register encoding First Integer summand.</span><span class="sxs-lookup"><span data-stu-id="9264b-110">LittleEndian qubit register encoding the first integer summand.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="9264b-111">gar: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="9264b-111">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="9264b-112">LittleEndian qubit register encoding det andra heltalet summand har ändrats för att innehålla de n minsta signifikanta bitarna av summan.</span><span class="sxs-lookup"><span data-stu-id="9264b-112">LittleEndian qubit register encoding the second integer summand, is modified to hold the n least significant bits of the sum.</span></span>


### <a name="carry--qubit"></a><span data-ttu-id="9264b-113">bär: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="9264b-113">carry : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="9264b-114">Bär qubit, är XoReD med den mest signifikanta biten av summan.</span><span class="sxs-lookup"><span data-stu-id="9264b-114">Carry qubit, is xored with the most significant bit of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9264b-115">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9264b-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="9264b-116">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="9264b-116">Remarks</span></span>

<span data-ttu-id="9264b-117">Den här åtgärden har samma funktioner som RippleCarryAdderD, men använder bara en hjälp qubit i stället för $n $.</span><span class="sxs-lookup"><span data-stu-id="9264b-117">This operation has the same functionality as RippleCarryAdderD, but only uses one auxiliary qubit instead of $n$.</span></span>

## <a name="references"></a><span data-ttu-id="9264b-118">Referenser</span><span class="sxs-lookup"><span data-stu-id="9264b-118">References</span></span>

- <span data-ttu-id="9264b-119">Stefan A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "A New Quantum krusning-Drive-extra kretsen", 2004.</span><span class="sxs-lookup"><span data-stu-id="9264b-119">Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "A new quantum ripple-carry addition circuit", 2004.</span></span>
  https://arxiv.org/abs/quant-ph/0410184v1