---
uid: Microsoft.Quantum.Canon.ApplyToFirstThreeQubits
title: ApplyToFirstThreeQubits-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstThreeQubits
qsharp.summary: Applies an operation to the first three qubits in the register.
ms.openlocfilehash: 61330f9e9b1f6b9f3965c9240505814b295aaefe
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729220"
---
# <a name="applytofirstthreequbits-operation"></a><span data-ttu-id="b2b25-102">ApplyToFirstThreeQubits-åtgärd</span><span class="sxs-lookup"><span data-stu-id="b2b25-102">ApplyToFirstThreeQubits operation</span></span>

<span data-ttu-id="b2b25-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b2b25-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b2b25-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b2b25-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b2b25-105">Tillämpar en åtgärd på de första tre qubits i registret.</span><span class="sxs-lookup"><span data-stu-id="b2b25-105">Applies an operation to the first three qubits in the register.</span></span>

```qsharp
operation ApplyToFirstThreeQubits (op : ((Qubit, Qubit, Qubit) => Unit), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="b2b25-106">Indata</span><span class="sxs-lookup"><span data-stu-id="b2b25-106">Input</span></span>

### <a name="op--qubitqubitqubit--unit"></a><span data-ttu-id="b2b25-107">OP: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit)) => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b2b25-107">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="b2b25-108">En åtgärd som ska tillämpas på de första tre qubits</span><span class="sxs-lookup"><span data-stu-id="b2b25-108">An operation to be applied to the first three qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="b2b25-109">Registrera: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="b2b25-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="b2b25-110">Qubit-matrisen till de tre första qubits som åtgärden tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="b2b25-110">Qubit array to the first three qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b2b25-111">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b2b25-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="b2b25-112">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="b2b25-112">Remarks</span></span>

<span data-ttu-id="b2b25-113">Detta motsvarar:</span><span class="sxs-lookup"><span data-stu-id="b2b25-113">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1], register[2]);
```

## <a name="see-also"></a><span data-ttu-id="b2b25-114">Se även</span><span class="sxs-lookup"><span data-stu-id="b2b25-114">See Also</span></span>

- [<span data-ttu-id="b2b25-115">Microsoft. Quantum. Canon. ApplyToFirstThreeQubitsC</span><span class="sxs-lookup"><span data-stu-id="b2b25-115">Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsC)
- [<span data-ttu-id="b2b25-116">Microsoft. Quantum. Canon. ApplyToFirstThreeQubitsA</span><span class="sxs-lookup"><span data-stu-id="b2b25-116">Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsA)
- [<span data-ttu-id="b2b25-117">Microsoft. Quantum. Canon. ApplyToFirstThreeQubitsCA</span><span class="sxs-lookup"><span data-stu-id="b2b25-117">Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsCA)