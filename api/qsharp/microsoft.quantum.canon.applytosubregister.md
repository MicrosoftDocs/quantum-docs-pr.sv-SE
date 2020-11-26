---
uid: Microsoft.Quantum.Canon.ApplyToSubregister
title: ApplyToSubregister-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToSubregister
qsharp.summary: Applies an operation to a subregister of a register, with qubits specified by an array of their indices.
ms.openlocfilehash: d4589edaadf59bbfff432bf49be2ce14fcff6ed1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208116"
---
# <a name="applytosubregister-operation"></a><span data-ttu-id="1e094-102">ApplyToSubregister-åtgärd</span><span class="sxs-lookup"><span data-stu-id="1e094-102">ApplyToSubregister operation</span></span>

<span data-ttu-id="1e094-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1e094-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1e094-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1e094-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1e094-105">Tillämpar en åtgärd på ett under register i ett register, där qubits anges av en matris med sina index.</span><span class="sxs-lookup"><span data-stu-id="1e094-105">Applies an operation to a subregister of a register, with qubits specified by an array of their indices.</span></span>

```qsharp
operation ApplyToSubregister (op : (Qubit[] => Unit), idxs : Int[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="1e094-106">Indata</span><span class="sxs-lookup"><span data-stu-id="1e094-106">Input</span></span>

### <a name="op--qubit--unit"></a><span data-ttu-id="1e094-107">OP: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1e094-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="1e094-108">Åtgärd att tillämpa på under registrering.</span><span class="sxs-lookup"><span data-stu-id="1e094-108">Operation to apply to subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="1e094-109">idxs: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="1e094-109">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="1e094-110">En matris med index som anger vilka qubits som åtgärden ska tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="1e094-110">Array of indices, indicating to which qubits the operation will be applied.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="1e094-111">mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="1e094-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="1e094-112">Registrera på vilken åtgärden fungerar.</span><span class="sxs-lookup"><span data-stu-id="1e094-112">Register on which the operation acts.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1e094-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1e094-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="1e094-114">Se även</span><span class="sxs-lookup"><span data-stu-id="1e094-114">See Also</span></span>

- [<span data-ttu-id="1e094-115">Microsoft. Quantum. Canon. ApplyToSubregisterA</span><span class="sxs-lookup"><span data-stu-id="1e094-115">Microsoft.Quantum.Canon.ApplyToSubregisterA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregisterA)
- [<span data-ttu-id="1e094-116">Microsoft. Quantum. Canon. ApplyToSubregisterC</span><span class="sxs-lookup"><span data-stu-id="1e094-116">Microsoft.Quantum.Canon.ApplyToSubregisterC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregisterC)
- [<span data-ttu-id="1e094-117">Microsoft. Quantum. Canon. ApplyToSubregisterCA</span><span class="sxs-lookup"><span data-stu-id="1e094-117">Microsoft.Quantum.Canon.ApplyToSubregisterCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregisterCA)