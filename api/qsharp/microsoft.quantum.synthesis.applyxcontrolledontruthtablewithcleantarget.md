---
uid: Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTableWithCleanTarget
title: ApplyXControlledOnTruthTableWithCleanTarget-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyXControlledOnTruthTableWithCleanTarget
qsharp.summary: Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.
ms.openlocfilehash: a54544cd026f26784bb0c41cb12187a8885ed9db
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855536"
---
# <a name="applyxcontrolledontruthtablewithcleantarget-operation"></a><span data-ttu-id="94540-102">ApplyXControlledOnTruthTableWithCleanTarget-åtgärd</span><span class="sxs-lookup"><span data-stu-id="94540-102">ApplyXControlledOnTruthTableWithCleanTarget operation</span></span>

<span data-ttu-id="94540-103">Namnrymd: [Microsoft. Quantum. syntes](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="94540-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="94540-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="94540-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="94540-105">Tillämpar @"microsoft.quantum.intrinsic.x" åtgärden på `target` , om den booleska funktionen `func` utvärderas som sant för den klassiska den klassiska tilldelningen i `controlRegister` .</span><span class="sxs-lookup"><span data-stu-id="94540-105">Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.</span></span>

```qsharp
operation ApplyXControlledOnTruthTableWithCleanTarget (func : BigInt, controlRegister : Qubit[], target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="94540-106">Description</span><span class="sxs-lookup"><span data-stu-id="94540-106">Description</span></span>

<span data-ttu-id="94540-107">Den här åtgärden implementerar ett specialfall av @"microsoft.quantum.synthesis.applyxcontrolledontruthtable" , där mål-qubit är känt i $ \ket {0} $-tillstånd.</span><span class="sxs-lookup"><span data-stu-id="94540-107">This operation implements a special case of @"microsoft.quantum.synthesis.applyxcontrolledontruthtable", in which the target qubit is known to be in the $\ket{0}$ state.</span></span>

<span data-ttu-id="94540-108">Implementeringen använder @"microsoft.quantum.intrinsic.cnot" och @"microsoft.quantum.intrinsic.r1" portar.</span><span class="sxs-lookup"><span data-stu-id="94540-108">The implementation makes use of @"microsoft.quantum.intrinsic.cnot" and @"microsoft.quantum.intrinsic.r1" gates.</span></span>  <span data-ttu-id="94540-109">Implementeringen av den angränsande åtgärden är optimerad och använder mätnings-baserad avberäkning.</span><span class="sxs-lookup"><span data-stu-id="94540-109">The implementation of the adjoint operation is optimized and uses measurement-based uncomputation.</span></span>

## <a name="input"></a><span data-ttu-id="94540-110">Indata</span><span class="sxs-lookup"><span data-stu-id="94540-110">Input</span></span>

### <a name="func--bigint"></a><span data-ttu-id="94540-111">FUNC: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="94540-111">func : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="94540-112">Boolesk sanningen tabell representeras som ett stort heltal</span><span class="sxs-lookup"><span data-stu-id="94540-112">Boolean truth table represented as big integer</span></span>


### <a name="controlregister--qubit"></a><span data-ttu-id="94540-113">controlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="94540-113">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="94540-114">Register över kontroll qubits</span><span class="sxs-lookup"><span data-stu-id="94540-114">Register of control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="94540-115">mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="94540-115">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="94540-116">Mål-qubit (måste vara i $ \ket {0} $ State)</span><span class="sxs-lookup"><span data-stu-id="94540-116">Target qubit (must be in $\ket{0}$ state)</span></span>



## <a name="output--unit"></a><span data-ttu-id="94540-117">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="94540-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="94540-118">Se även</span><span class="sxs-lookup"><span data-stu-id="94540-118">See Also</span></span>

- [<span data-ttu-id="94540-119">Microsoft. Quantum. syntes. ApplyXControlledOnTruthTable</span><span class="sxs-lookup"><span data-stu-id="94540-119">Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTable</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTable)