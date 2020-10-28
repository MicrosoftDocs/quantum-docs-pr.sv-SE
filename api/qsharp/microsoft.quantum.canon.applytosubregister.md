---
uid: Microsoft.Quantum.Canon.ApplyToSubregister
title: ApplyToSubregister-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToSubregister
qsharp.summary: Applies an operation to a subregister of a register, with qubits specified by an array of their indices.
ms.openlocfilehash: c9181b8962d36b20f7a9140eb7aaef11aee7faa0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729070"
---
# <a name="applytosubregister-operation"></a><span data-ttu-id="69e81-102">ApplyToSubregister-åtgärd</span><span class="sxs-lookup"><span data-stu-id="69e81-102">ApplyToSubregister operation</span></span>

<span data-ttu-id="69e81-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="69e81-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="69e81-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="69e81-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="69e81-105">Tillämpar en åtgärd på ett under register i ett register, där qubits anges av en matris med sina index.</span><span class="sxs-lookup"><span data-stu-id="69e81-105">Applies an operation to a subregister of a register, with qubits specified by an array of their indices.</span></span>

```qsharp
operation ApplyToSubregister (op : (Qubit[] => Unit), idxs : Int[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="69e81-106">Indata</span><span class="sxs-lookup"><span data-stu-id="69e81-106">Input</span></span>

### <a name="op--qubit--unit"></a><span data-ttu-id="69e81-107">OP: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="69e81-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="69e81-108">Åtgärd att tillämpa på under registrering.</span><span class="sxs-lookup"><span data-stu-id="69e81-108">Operation to apply to subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="69e81-109">idxs: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="69e81-109">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="69e81-110">En matris med index som anger vilka qubits som åtgärden ska tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="69e81-110">Array of indices, indicating to which qubits the operation will be applied.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="69e81-111">mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="69e81-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="69e81-112">Registrera på vilken åtgärden fungerar.</span><span class="sxs-lookup"><span data-stu-id="69e81-112">Register on which the operation acts.</span></span>



## <a name="output--unit"></a><span data-ttu-id="69e81-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="69e81-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="69e81-114">Se även</span><span class="sxs-lookup"><span data-stu-id="69e81-114">See Also</span></span>

- [<span data-ttu-id="69e81-115">Microsoft. Quantum. Canon. ApplyToSubregisterA</span><span class="sxs-lookup"><span data-stu-id="69e81-115">Microsoft.Quantum.Canon.ApplyToSubregisterA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregisterA)
- [<span data-ttu-id="69e81-116">Microsoft. Quantum. Canon. ApplyToSubregisterC</span><span class="sxs-lookup"><span data-stu-id="69e81-116">Microsoft.Quantum.Canon.ApplyToSubregisterC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregisterC)
- [<span data-ttu-id="69e81-117">Microsoft. Quantum. Canon. ApplyToSubregisterCA</span><span class="sxs-lookup"><span data-stu-id="69e81-117">Microsoft.Quantum.Canon.ApplyToSubregisterCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregisterCA)