---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubitA
title: ApplyToFirstQubitA-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubitA
qsharp.summary: Applies an operation to the first qubit in the register. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 00dbff0b562f90653c8569589e838f11e6c938e8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729229"
---
# <a name="applytofirstqubita-operation"></a><span data-ttu-id="8b811-102">ApplyToFirstQubitA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="8b811-102">ApplyToFirstQubitA operation</span></span>

<span data-ttu-id="8b811-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8b811-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8b811-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8b811-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8b811-105">Tillämpar en åtgärd på den första qubit i registret.</span><span class="sxs-lookup"><span data-stu-id="8b811-105">Applies an operation to the first qubit in the register.</span></span>
<span data-ttu-id="8b811-106">Modifieraren `A` anger att åtgärden är adjointable.</span><span class="sxs-lookup"><span data-stu-id="8b811-106">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
operation ApplyToFirstQubitA (op : (Qubit => Unit is Adj), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="8b811-107">Indata</span><span class="sxs-lookup"><span data-stu-id="8b811-107">Input</span></span>

### <a name="op--qubit--unit-adj"></a><span data-ttu-id="8b811-108">OP: [qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit) just</span><span class="sxs-lookup"><span data-stu-id="8b811-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="8b811-109">En åtgärd som ska tillämpas på den första qubit</span><span class="sxs-lookup"><span data-stu-id="8b811-109">An operation to be applied to the first qubit</span></span>


### <a name="register--qubit"></a><span data-ttu-id="8b811-110">Registrera: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="8b811-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="8b811-111">Qubit-matris till den första qubit som åtgärden tillämpas på</span><span class="sxs-lookup"><span data-stu-id="8b811-111">Qubit array to the first qubit of which the operation is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="8b811-112">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8b811-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="8b811-113">Se även</span><span class="sxs-lookup"><span data-stu-id="8b811-113">See Also</span></span>

- [<span data-ttu-id="8b811-114">Microsoft. Quantum. Canon. ApplyToFirstQubit</span><span class="sxs-lookup"><span data-stu-id="8b811-114">Microsoft.Quantum.Canon.ApplyToFirstQubit</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstQubit)