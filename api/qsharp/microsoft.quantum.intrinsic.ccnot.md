---
uid: Microsoft.Quantum.Intrinsic.CCNOT
title: CCNOT-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: CCNOT
qsharp.summary: Applies the doubly controlled–NOT (CCNOT) gate to three qubits.
ms.openlocfilehash: a9186269a868c2ac9d2f15727a3b0ed1bfec3fa4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98819032"
---
# <a name="ccnot-operation"></a><span data-ttu-id="76aeb-102">CCNOT-åtgärd</span><span class="sxs-lookup"><span data-stu-id="76aeb-102">CCNOT operation</span></span>

<span data-ttu-id="76aeb-103">Namnrymd: [Microsoft. Quantum. inbyggt](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="76aeb-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="76aeb-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="76aeb-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="76aeb-105">Använder den dubbla styrda, inte (CCNOT) porten till tre qubits.</span><span class="sxs-lookup"><span data-stu-id="76aeb-105">Applies the doubly controlled–NOT (CCNOT) gate to three qubits.</span></span>

```qsharp
operation CCNOT (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="76aeb-106">Indata</span><span class="sxs-lookup"><span data-stu-id="76aeb-106">Input</span></span>

### <a name="control1--qubit"></a><span data-ttu-id="76aeb-107">control1: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="76aeb-107">control1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="76aeb-108">Första kontrollen qubit för CCNOT-porten.</span><span class="sxs-lookup"><span data-stu-id="76aeb-108">First control qubit for the CCNOT gate.</span></span>


### <a name="control2--qubit"></a><span data-ttu-id="76aeb-109">control2: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="76aeb-109">control2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="76aeb-110">Den andra kontrollen qubit för CCNOT-porten.</span><span class="sxs-lookup"><span data-stu-id="76aeb-110">Second control qubit for the CCNOT gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="76aeb-111">mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="76aeb-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="76aeb-112">Mål-qubit för CCNOT-porten.</span><span class="sxs-lookup"><span data-stu-id="76aeb-112">Target qubit for the CCNOT gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="76aeb-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="76aeb-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="76aeb-114">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="76aeb-114">Remarks</span></span>

<span data-ttu-id="76aeb-115">Motsvarar:</span><span class="sxs-lookup"><span data-stu-id="76aeb-115">Equivalent to:</span></span>

```qsharp
Controlled X([control1, control2], target);
```