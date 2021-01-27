---
uid: Microsoft.Quantum.ErrorCorrection.MeasureStabilizerGenerators
title: MeasureStabilizerGenerators-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: MeasureStabilizerGenerators
qsharp.summary: Measures the given set of generators of a stabilizer group.
ms.openlocfilehash: d7c8df079e49b2ce0a5106e430ef4060df85cdc4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98825760"
---
# <a name="measurestabilizergenerators-operation"></a><span data-ttu-id="64854-102">MeasureStabilizerGenerators-åtgärd</span><span class="sxs-lookup"><span data-stu-id="64854-102">MeasureStabilizerGenerators operation</span></span>

<span data-ttu-id="64854-103">Namnrymd: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="64854-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="64854-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="64854-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="64854-105">Mäter den angivna uppsättningen generatorer för en stabiliserings grupp.</span><span class="sxs-lookup"><span data-stu-id="64854-105">Measures the given set of generators of a stabilizer group.</span></span>

```qsharp
operation MeasureStabilizerGenerators (stabilizerGroup : Pauli[][], logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister, gadget : ((Pauli[], Qubit[]) => Result)) : Microsoft.Quantum.ErrorCorrection.Syndrome
```


## <a name="input"></a><span data-ttu-id="64854-106">Indata</span><span class="sxs-lookup"><span data-stu-id="64854-106">Input</span></span>

### <a name="stabilizergroup--pauli"></a><span data-ttu-id="64854-107">stabilizerGroup: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="64854-107">stabilizerGroup : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="64854-108">En matris med multiqubit Pauli-operatörer.</span><span class="sxs-lookup"><span data-stu-id="64854-108">An array of multiqubit Pauli operators.</span></span>
<span data-ttu-id="64854-109">Är till exempel `stabilizerGroup[0]` en lista med enqubite Pauli-matriser, som är en stabiliserings Generator.</span><span class="sxs-lookup"><span data-stu-id="64854-109">For example, `stabilizerGroup[0]` is a list of single-qubit Pauli matrices, the tensor product of which is a stabilizer generator.</span></span>


### <a name="logicalregister--logicalregister"></a><span data-ttu-id="64854-110">logicalRegister: [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="64854-110">logicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="64854-111">En matris med qubits där stabiliserings koden definieras.</span><span class="sxs-lookup"><span data-stu-id="64854-111">An array of qubits where the stabilizer code is defined.</span></span>


### <a name="gadget--pauliqubit--__invalidresult__"></a><span data-ttu-id="64854-112">gadget: ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __ogiltig <Result>__</span><span class="sxs-lookup"><span data-stu-id="64854-112">gadget : ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __invalid<Result>__</span></span> 

<span data-ttu-id="64854-113">En åtgärd som anger hur en multiqubit Pauli-operator ska mätas.</span><span class="sxs-lookup"><span data-stu-id="64854-113">An operation that specifies how to measure a multiqubit Pauli operator.</span></span>



## <a name="output--syndrome"></a><span data-ttu-id="64854-114">Utdata: [Syndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)</span><span class="sxs-lookup"><span data-stu-id="64854-114">Output : [Syndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)</span></span>

<span data-ttu-id="64854-115">Resultatet av mätningar.</span><span class="sxs-lookup"><span data-stu-id="64854-115">The result of measurements.</span></span>

## <a name="remarks"></a><span data-ttu-id="64854-116">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="64854-116">Remarks</span></span>

<span data-ttu-id="64854-117">Detta kontrollerar inte om den angivna uppsättningen generatorer förfaller.</span><span class="sxs-lookup"><span data-stu-id="64854-117">This does not check if the given set of generators are commuting.</span></span>
<span data-ttu-id="64854-118">Om de inte återkommer kan resultatet av måtten vara godtyckligt.</span><span class="sxs-lookup"><span data-stu-id="64854-118">If they are not commuting, the result of measurements may be arbitrary.</span></span>