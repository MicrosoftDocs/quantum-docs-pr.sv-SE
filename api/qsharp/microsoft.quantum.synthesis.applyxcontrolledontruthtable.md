---
uid: Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTable
title: ApplyXControlledOnTruthTable-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyXControlledOnTruthTable
qsharp.summary: Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.
ms.openlocfilehash: 73d63936f02a52dfbbad7b8575110177a9e4463d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733931"
---
# <a name="applyxcontrolledontruthtable-operation"></a><span data-ttu-id="4f23f-102">ApplyXControlledOnTruthTable-åtgärd</span><span class="sxs-lookup"><span data-stu-id="4f23f-102">ApplyXControlledOnTruthTable operation</span></span>

<span data-ttu-id="4f23f-103">Namnrymd: [Microsoft. Quantum. syntes](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="4f23f-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="4f23f-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4f23f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4f23f-105">Tillämpar @"microsoft.quantum.intrinsic.x" åtgärden på `target` , om den booleska funktionen `func` utvärderas som sant för den klassiska den klassiska tilldelningen i `controlRegister` .</span><span class="sxs-lookup"><span data-stu-id="4f23f-105">Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.</span></span>

```qsharp
operation ApplyXControlledOnTruthTable (func : BigInt, controlRegister : Qubit[], target : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="4f23f-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="4f23f-106">Description</span></span>

<span data-ttu-id="4f23f-107">Åtgärden implementerar den enhetliga åtgärden \begin{align} U\ket {x} \ ket {y} = \ket{x}\ket{y \oplus f (x)} \end{align} där $x $ och $y $ representerar respektive `controlRegister` `target` .</span><span class="sxs-lookup"><span data-stu-id="4f23f-107">The operation implements the unitary operation \begin{align} U\ket{x}\ket{y} = \ket{x}\ket{y \oplus f(x)} \end{align} where $x$ and $y$ represent `controlRegister` and `target`, respectively.</span></span>

<span data-ttu-id="4f23f-108">Den booleska funktionen $f $ representeras som en sanningen-tabell i termer av ett stort heltal.</span><span class="sxs-lookup"><span data-stu-id="4f23f-108">The Boolean function $f$ is represented as a truth table in terms of a big integer.</span></span>
<span data-ttu-id="4f23f-109">Till exempel representeras majoriteten-funktionen på tre indata av bitstring `11101000` , där den mest signifikanta biten `1` motsvarar tilldelningen `(1, 1, 1)` och den minst signifikanta biten `0` motsvarar den angivna tilldelningen `(0, 0, 0)` .</span><span class="sxs-lookup"><span data-stu-id="4f23f-109">For example, the majority function on three inputs is represented by the bitstring `11101000`, where the most significant bit `1` corresponds to the input assignment `(1, 1, 1)`, and the least significant bit `0` corresponds to the input assignment `(0, 0, 0)`.</span></span>
<span data-ttu-id="4f23f-110">Den kan representeras av det stora heltalet `0xE8L` i hexadecimal notation eller som `232L` Decimal form.</span><span class="sxs-lookup"><span data-stu-id="4f23f-110">It can be represented by the big integer `0xE8L` in hexadecimal notation or as `232L` in decimal notation.</span></span>  <span data-ttu-id="4f23f-111">`L`Suffixet anger att konstanten är av typen `BigInt` .</span><span class="sxs-lookup"><span data-stu-id="4f23f-111">The `L` suffix indicates that the constant is of type `BigInt`.</span></span>
<span data-ttu-id="4f23f-112">Det går även att hitta mer information om den här åter givningen i [sanningen-tabellerna Kata](https://github.com/microsoft/QuantumKatas/tree/main/TruthTables).</span><span class="sxs-lookup"><span data-stu-id="4f23f-112">More details on this representation can also be found in the [truth tables kata](https://github.com/microsoft/QuantumKatas/tree/main/TruthTables).</span></span>

<span data-ttu-id="4f23f-113">Implementeringen använder @"microsoft.quantum.intrinsic.cnot" och @"microsoft.quantum.intrinsic.r1" portar.</span><span class="sxs-lookup"><span data-stu-id="4f23f-113">The implementation makes use of @"microsoft.quantum.intrinsic.cnot" and @"microsoft.quantum.intrinsic.r1" gates.</span></span>

## <a name="input"></a><span data-ttu-id="4f23f-114">Indata</span><span class="sxs-lookup"><span data-stu-id="4f23f-114">Input</span></span>

### <a name="func--bigint"></a><span data-ttu-id="4f23f-115">FUNC: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="4f23f-115">func : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="4f23f-116">Boolesk sanningen tabell representeras som ett stort heltal</span><span class="sxs-lookup"><span data-stu-id="4f23f-116">Boolean truth table represented as big integer</span></span>


### <a name="controlregister--qubit"></a><span data-ttu-id="4f23f-117">controlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="4f23f-117">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="4f23f-118">Register över kontroll qubits</span><span class="sxs-lookup"><span data-stu-id="4f23f-118">Register of control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="4f23f-119">mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="4f23f-119">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="4f23f-120">Mål qubit</span><span class="sxs-lookup"><span data-stu-id="4f23f-120">Target qubit</span></span>



## <a name="output--unit"></a><span data-ttu-id="4f23f-121">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4f23f-121">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="4f23f-122">Referenser</span><span class="sxs-lookup"><span data-stu-id="4f23f-122">References</span></span>

- [<span data-ttu-id="4f23f-123">*N. Schuch* , *J. Siewert* , PRL 91, no. 027902, 2003, arXiv: Quant-pH/0303063</span><span class="sxs-lookup"><span data-stu-id="4f23f-123">*N. Schuch* , *J. Siewert* , PRL 91, no. 027902, 2003, arXiv:quant-ph/0303063</span></span>](https://arxiv.org/abs/quant-ph/0303063)
- [<span data-ttu-id="4f23f-124">*Mathias Soeken* , *Martin Roetteler* , arXiv: 2005.12310</span><span class="sxs-lookup"><span data-stu-id="4f23f-124">*Mathias Soeken* , *Martin Roetteler* , arXiv:2005.12310</span></span>](https://arxiv.org/abs/2005.12310)

## <a name="see-also"></a><span data-ttu-id="4f23f-125">Se även</span><span class="sxs-lookup"><span data-stu-id="4f23f-125">See Also</span></span>

- [<span data-ttu-id="4f23f-126">Microsoft. Quantum. syntes. ApplyXControlledOnTruthTableWithCleanTarget</span><span class="sxs-lookup"><span data-stu-id="4f23f-126">Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTableWithCleanTarget</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTableWithCleanTarget)