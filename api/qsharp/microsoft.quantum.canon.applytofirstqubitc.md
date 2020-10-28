---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubitC
title: ApplyToFirstQubitC-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubitC
qsharp.summary: Applies operation op to the first qubit in the register. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: e2c137ad4a8252731acf94d6f2343f8fd386b8e3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729232"
---
# <a name="applytofirstqubitc-operation"></a><span data-ttu-id="273dc-102">ApplyToFirstQubitC-åtgärd</span><span class="sxs-lookup"><span data-stu-id="273dc-102">ApplyToFirstQubitC operation</span></span>

<span data-ttu-id="273dc-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="273dc-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="273dc-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="273dc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="273dc-105">Tillämpar åtgärden op på den första qubit i registret.</span><span class="sxs-lookup"><span data-stu-id="273dc-105">Applies operation op to the first qubit in the register.</span></span>
<span data-ttu-id="273dc-106">Modifieraren `C` anger att åtgärden är kontrollerbar.</span><span class="sxs-lookup"><span data-stu-id="273dc-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
operation ApplyToFirstQubitC (op : (Qubit => Unit is Ctl), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="273dc-107">Indata</span><span class="sxs-lookup"><span data-stu-id="273dc-107">Input</span></span>

### <a name="op--qubit--unit-ctl"></a><span data-ttu-id="273dc-108">OP: [qubit](xref:microsoft.quantum.lang-ref.qubit) => [enhet](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="273dc-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="273dc-109">En åtgärd som ska tillämpas på den första qubit</span><span class="sxs-lookup"><span data-stu-id="273dc-109">An operation to be applied to the first qubit</span></span>


### <a name="register--qubit"></a><span data-ttu-id="273dc-110">Registrera: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="273dc-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="273dc-111">Qubit-matris till den första qubit som åtgärden tillämpas på</span><span class="sxs-lookup"><span data-stu-id="273dc-111">Qubit array to the first qubit of which the operation is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="273dc-112">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="273dc-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="273dc-113">Se även</span><span class="sxs-lookup"><span data-stu-id="273dc-113">See Also</span></span>

- [<span data-ttu-id="273dc-114">Microsoft. Quantum. Canon. ApplyToFirstQubit</span><span class="sxs-lookup"><span data-stu-id="273dc-114">Microsoft.Quantum.Canon.ApplyToFirstQubit</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstQubit)