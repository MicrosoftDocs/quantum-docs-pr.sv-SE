---
uid: Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsCA
title: ApplyToFirstTwoQubitsCA-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstTwoQubitsCA
qsharp.summary: Applies an operation to the first two qubits in the register. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 0c5e29fbca8449f8122f2a9f988797e94e27da60
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729169"
---
# <a name="applytofirsttwoqubitsca-operation"></a><span data-ttu-id="c839b-102">ApplyToFirstTwoQubitsCA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="c839b-102">ApplyToFirstTwoQubitsCA operation</span></span>

<span data-ttu-id="c839b-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c839b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c839b-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c839b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c839b-105">Tillämpar en åtgärd på de två första qubits i registret.</span><span class="sxs-lookup"><span data-stu-id="c839b-105">Applies an operation to the first two qubits in the register.</span></span>
<span data-ttu-id="c839b-106">Modifieraren `CA` anger att åtgärden är kontrollerbar och adjointable.</span><span class="sxs-lookup"><span data-stu-id="c839b-106">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToFirstTwoQubitsCA (op : ((Qubit, Qubit) => Unit is Adj + Ctl), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="c839b-107">Indata</span><span class="sxs-lookup"><span data-stu-id="c839b-107">Input</span></span>

### <a name="op--qubitqubit--unit-adj--ctl"></a><span data-ttu-id="c839b-108">OP: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [enhet](xref:microsoft.quantum.lang-ref.unit) just + CTL</span><span class="sxs-lookup"><span data-stu-id="c839b-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="c839b-109">En åtgärd som ska tillämpas på de två första qubits</span><span class="sxs-lookup"><span data-stu-id="c839b-109">An operation to be applied to the first two qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="c839b-110">Registrera: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c839b-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="c839b-111">Qubit-matrisen till de två första qubits som åtgärden tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="c839b-111">Qubit array to the first two qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c839b-112">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c839b-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="c839b-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="c839b-113">Remarks</span></span>

<span data-ttu-id="c839b-114">Detta motsvarar:</span><span class="sxs-lookup"><span data-stu-id="c839b-114">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1]);
```

## <a name="see-also"></a><span data-ttu-id="c839b-115">Se även</span><span class="sxs-lookup"><span data-stu-id="c839b-115">See Also</span></span>

- [<span data-ttu-id="c839b-116">Microsoft. Quantum. Canon. ApplyToFirstTwoQubits</span><span class="sxs-lookup"><span data-stu-id="c839b-116">Microsoft.Quantum.Canon.ApplyToFirstTwoQubits</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubits)