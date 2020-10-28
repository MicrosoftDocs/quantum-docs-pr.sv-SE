---
uid: Microsoft.Quantum.Canon.ApplyToFirstTwoQubits
title: ApplyToFirstTwoQubits-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstTwoQubits
qsharp.summary: Applies an operation to the first two qubits in the register.
ms.openlocfilehash: aad07889c0dbf2329304c98b06dbd0c225df8a81
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729190"
---
# <a name="applytofirsttwoqubits-operation"></a><span data-ttu-id="39b5a-102">ApplyToFirstTwoQubits-åtgärd</span><span class="sxs-lookup"><span data-stu-id="39b5a-102">ApplyToFirstTwoQubits operation</span></span>

<span data-ttu-id="39b5a-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="39b5a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="39b5a-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="39b5a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="39b5a-105">Tillämpar en åtgärd på de två första qubits i registret.</span><span class="sxs-lookup"><span data-stu-id="39b5a-105">Applies an operation to the first two qubits in the register.</span></span>

```qsharp
operation ApplyToFirstTwoQubits (op : ((Qubit, Qubit) => Unit), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="39b5a-106">Indata</span><span class="sxs-lookup"><span data-stu-id="39b5a-106">Input</span></span>

### <a name="op--qubitqubit--unit"></a><span data-ttu-id="39b5a-107">OP: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="39b5a-107">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="39b5a-108">En åtgärd som ska tillämpas på de två första qubits</span><span class="sxs-lookup"><span data-stu-id="39b5a-108">An operation to be applied to the first two qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="39b5a-109">Registrera: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="39b5a-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="39b5a-110">Qubit-matrisen till de två första qubits som åtgärden tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="39b5a-110">Qubit array to the first two qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="39b5a-111">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="39b5a-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="39b5a-112">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="39b5a-112">Remarks</span></span>

<span data-ttu-id="39b5a-113">Detta motsvarar:</span><span class="sxs-lookup"><span data-stu-id="39b5a-113">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1]);
```

## <a name="see-also"></a><span data-ttu-id="39b5a-114">Se även</span><span class="sxs-lookup"><span data-stu-id="39b5a-114">See Also</span></span>

- [<span data-ttu-id="39b5a-115">Microsoft. Quantum. Canon. ApplyToFirstTwoQubitsA</span><span class="sxs-lookup"><span data-stu-id="39b5a-115">Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsA)
- [<span data-ttu-id="39b5a-116">Microsoft. Quantum. Canon. ApplyToFirstTwoQubitsC</span><span class="sxs-lookup"><span data-stu-id="39b5a-116">Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsC)
- [<span data-ttu-id="39b5a-117">Microsoft. Quantum. Canon. ApplyToFirstTwoQubitsCA</span><span class="sxs-lookup"><span data-stu-id="39b5a-117">Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsCA)