---
uid: Microsoft.Quantum.ErrorCorrection.MeasureStabilizerGenerators
title: MeasureStabilizerGenerators-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: MeasureStabilizerGenerators
qsharp.summary: Measures the given set of generators of a stabilizer group.
ms.openlocfilehash: a3f48ff24a39d13a57f7a144e21d4e41bb8a8b49
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727027"
---
# <a name="measurestabilizergenerators-operation"></a><span data-ttu-id="92964-102">MeasureStabilizerGenerators-åtgärd</span><span class="sxs-lookup"><span data-stu-id="92964-102">MeasureStabilizerGenerators operation</span></span>

<span data-ttu-id="92964-103">Namnrymd: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="92964-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="92964-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="92964-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="92964-105">Mäter den angivna uppsättningen generatorer för en stabiliserings grupp.</span><span class="sxs-lookup"><span data-stu-id="92964-105">Measures the given set of generators of a stabilizer group.</span></span>

```qsharp
operation MeasureStabilizerGenerators (stabilizerGroup : Pauli[][], logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister, gadget : ((Pauli[], Qubit[]) => Result)) : Microsoft.Quantum.ErrorCorrection.Syndrome
```


## <a name="input"></a><span data-ttu-id="92964-106">Indata</span><span class="sxs-lookup"><span data-stu-id="92964-106">Input</span></span>

### <a name="stabilizergroup--pauli"></a><span data-ttu-id="92964-107">stabilizerGroup: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="92964-107">stabilizerGroup : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="92964-108">En matris med multiqubit Pauli-operatörer.</span><span class="sxs-lookup"><span data-stu-id="92964-108">An array of multiqubit Pauli operators.</span></span>
<span data-ttu-id="92964-109">Är till exempel `stabilizerGroup[0]` en lista med enqubite Pauli-matriser, som är en stabiliserings Generator.</span><span class="sxs-lookup"><span data-stu-id="92964-109">For example, `stabilizerGroup[0]` is a list of single-qubit Pauli matrices, the tensor product of which is a stabilizer generator.</span></span>


### <a name="logicalregister--logicalregister"></a><span data-ttu-id="92964-110">logicalRegister: [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="92964-110">logicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="92964-111">En matris med qubits där stabiliserings koden definieras.</span><span class="sxs-lookup"><span data-stu-id="92964-111">An array of qubits where the stabilizer code is defined.</span></span>


### <a name="gadget--pauliqubit--__invalidresult__"></a><span data-ttu-id="92964-112">gadget: ( [Pauli](xref:microsoft.quantum.lang-ref.pauli)[], [qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __ogiltig <Result>__</span><span class="sxs-lookup"><span data-stu-id="92964-112">gadget : ( [Pauli](xref:microsoft.quantum.lang-ref.pauli)[], [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __invalid<Result>__</span></span> 

<span data-ttu-id="92964-113">En åtgärd som anger hur en multiqubit Pauli-operator ska mätas.</span><span class="sxs-lookup"><span data-stu-id="92964-113">An operation that specifies how to measure a multiqubit Pauli operator.</span></span>



## <a name="output--syndrome"></a><span data-ttu-id="92964-114">Utdata: [Syndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)</span><span class="sxs-lookup"><span data-stu-id="92964-114">Output : [Syndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)</span></span>

<span data-ttu-id="92964-115">Resultatet av mätningar.</span><span class="sxs-lookup"><span data-stu-id="92964-115">The result of measurements.</span></span>

## <a name="remarks"></a><span data-ttu-id="92964-116">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="92964-116">Remarks</span></span>

<span data-ttu-id="92964-117">Detta kontrollerar inte om den angivna uppsättningen generatorer förfaller.</span><span class="sxs-lookup"><span data-stu-id="92964-117">This does not check if the given set of generators are commuting.</span></span>
<span data-ttu-id="92964-118">Om de inte återkommer kan resultatet av måtten vara godtyckligt.</span><span class="sxs-lookup"><span data-stu-id="92964-118">If they are not commuting, the result of measurements may be arbitrary.</span></span>