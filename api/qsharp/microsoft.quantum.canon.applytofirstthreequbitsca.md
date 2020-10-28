---
uid: Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsCA
title: ApplyToFirstThreeQubitsCA-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstThreeQubitsCA
qsharp.summary: Applies an operation to the first three qubits in the register. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: bd7a3ac260d370aae9da8691fcd34a8b6221d451
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729205"
---
# <a name="applytofirstthreequbitsca-operation"></a><span data-ttu-id="015ed-102">ApplyToFirstThreeQubitsCA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="015ed-102">ApplyToFirstThreeQubitsCA operation</span></span>

<span data-ttu-id="015ed-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="015ed-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="015ed-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="015ed-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="015ed-105">Tillämpar en åtgärd på de första tre qubits i registret.</span><span class="sxs-lookup"><span data-stu-id="015ed-105">Applies an operation to the first three qubits in the register.</span></span>
<span data-ttu-id="015ed-106">Modifieraren `CA` anger att åtgärden är kontrollerbar och adjointable.</span><span class="sxs-lookup"><span data-stu-id="015ed-106">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToFirstThreeQubitsCA (op : ((Qubit, Qubit, Qubit) => Unit is Adj + Ctl), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="015ed-107">Indata</span><span class="sxs-lookup"><span data-stu-id="015ed-107">Input</span></span>

### <a name="op--qubitqubitqubit--unit-adj--ctl"></a><span data-ttu-id="015ed-108">OP: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit)) => [enhet](xref:microsoft.quantum.lang-ref.unit) just + CTL</span><span class="sxs-lookup"><span data-stu-id="015ed-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="015ed-109">En åtgärd som ska tillämpas på de första tre qubits</span><span class="sxs-lookup"><span data-stu-id="015ed-109">An operation to be applied to the first three qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="015ed-110">Registrera: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="015ed-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="015ed-111">Qubit-matrisen till de tre första qubits som åtgärden tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="015ed-111">Qubit array to the first three qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="015ed-112">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="015ed-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="015ed-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="015ed-113">Remarks</span></span>

<span data-ttu-id="015ed-114">Detta motsvarar:</span><span class="sxs-lookup"><span data-stu-id="015ed-114">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1], register[2]);
```

## <a name="see-also"></a><span data-ttu-id="015ed-115">Se även</span><span class="sxs-lookup"><span data-stu-id="015ed-115">See Also</span></span>

- [<span data-ttu-id="015ed-116">Microsoft. Quantum. Canon. ApplyToFirstThreeQubits</span><span class="sxs-lookup"><span data-stu-id="015ed-116">Microsoft.Quantum.Canon.ApplyToFirstThreeQubits</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubits)