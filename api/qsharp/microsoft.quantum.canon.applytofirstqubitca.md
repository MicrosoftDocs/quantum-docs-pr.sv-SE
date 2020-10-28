---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubitCA
title: ApplyToFirstQubitCA-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubitCA
qsharp.summary: Applies operation op to the first qubit in the register. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 2e1db23ad819a85df99a826f406d9b0fbcc7a175
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729226"
---
# <a name="applytofirstqubitca-operation"></a><span data-ttu-id="d55d9-102">ApplyToFirstQubitCA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="d55d9-102">ApplyToFirstQubitCA operation</span></span>

<span data-ttu-id="d55d9-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d55d9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d55d9-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d55d9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d55d9-105">Tillämpar åtgärden op på den första qubit i registret.</span><span class="sxs-lookup"><span data-stu-id="d55d9-105">Applies operation op to the first qubit in the register.</span></span>
<span data-ttu-id="d55d9-106">Modifieraren `CA` anger att åtgärden är kontrollerbar och adjointable.</span><span class="sxs-lookup"><span data-stu-id="d55d9-106">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToFirstQubitCA (op : (Qubit => Unit is Adj + Ctl), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="d55d9-107">Indata</span><span class="sxs-lookup"><span data-stu-id="d55d9-107">Input</span></span>

### <a name="op--qubit--unit-adj--ctl"></a><span data-ttu-id="d55d9-108">OP: [qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit) rejust + CTL</span><span class="sxs-lookup"><span data-stu-id="d55d9-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="d55d9-109">En åtgärd som ska tillämpas på den första qubit</span><span class="sxs-lookup"><span data-stu-id="d55d9-109">An operation to be applied to the first qubit</span></span>


### <a name="register--qubit"></a><span data-ttu-id="d55d9-110">Registrera: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="d55d9-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="d55d9-111">Qubit-matris till den första qubit som åtgärden tillämpas på</span><span class="sxs-lookup"><span data-stu-id="d55d9-111">Qubit array to the first qubit of which the operation is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="d55d9-112">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d55d9-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="d55d9-113">Se även</span><span class="sxs-lookup"><span data-stu-id="d55d9-113">See Also</span></span>

- [<span data-ttu-id="d55d9-114">Microsoft. Quantum. Canon. ApplyToFirstQubit</span><span class="sxs-lookup"><span data-stu-id="d55d9-114">Microsoft.Quantum.Canon.ApplyToFirstQubit</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstQubit)