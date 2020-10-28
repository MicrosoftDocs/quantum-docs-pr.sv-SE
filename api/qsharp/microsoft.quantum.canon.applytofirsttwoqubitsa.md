---
uid: Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsA
title: ApplyToFirstTwoQubitsA-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstTwoQubitsA
qsharp.summary: Applies an operation to the first two qubits in the register. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 911e9bc3d02bf6c0395c30fa167a6cb730dc666e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729187"
---
# <a name="applytofirsttwoqubitsa-operation"></a><span data-ttu-id="5c97c-102">ApplyToFirstTwoQubitsA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="5c97c-102">ApplyToFirstTwoQubitsA operation</span></span>

<span data-ttu-id="5c97c-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5c97c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5c97c-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5c97c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5c97c-105">Tillämpar en åtgärd på de två första qubits i registret.</span><span class="sxs-lookup"><span data-stu-id="5c97c-105">Applies an operation to the first two qubits in the register.</span></span>
<span data-ttu-id="5c97c-106">Modifieraren `A` anger att åtgärden är adjointable.</span><span class="sxs-lookup"><span data-stu-id="5c97c-106">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
operation ApplyToFirstTwoQubitsA (op : ((Qubit, Qubit) => Unit is Adj), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="5c97c-107">Indata</span><span class="sxs-lookup"><span data-stu-id="5c97c-107">Input</span></span>

### <a name="op--qubitqubit--unit-adj"></a><span data-ttu-id="5c97c-108">OP: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [enhets](xref:microsoft.quantum.lang-ref.unit) justering</span><span class="sxs-lookup"><span data-stu-id="5c97c-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="5c97c-109">En åtgärd som ska tillämpas på de två första qubits</span><span class="sxs-lookup"><span data-stu-id="5c97c-109">An operation to be applied to the first two qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="5c97c-110">Registrera: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="5c97c-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="5c97c-111">Qubit-matrisen till de två första qubits som åtgärden tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="5c97c-111">Qubit array to the first two qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5c97c-112">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5c97c-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="5c97c-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="5c97c-113">Remarks</span></span>

<span data-ttu-id="5c97c-114">Detta motsvarar:</span><span class="sxs-lookup"><span data-stu-id="5c97c-114">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1]);
```

## <a name="see-also"></a><span data-ttu-id="5c97c-115">Se även</span><span class="sxs-lookup"><span data-stu-id="5c97c-115">See Also</span></span>

- [<span data-ttu-id="5c97c-116">Microsoft. Quantum. Canon. ApplyToFirstTwoQubits</span><span class="sxs-lookup"><span data-stu-id="5c97c-116">Microsoft.Quantum.Canon.ApplyToFirstTwoQubits</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubits)