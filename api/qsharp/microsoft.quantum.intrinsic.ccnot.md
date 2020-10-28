---
uid: Microsoft.Quantum.Intrinsic.CCNOT
title: CCNOT-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: CCNOT
qsharp.summary: Applies the doubly controlled–NOT (CCNOT) gate to three qubits.
ms.openlocfilehash: bf20ff1e9d25d72e7e8e0207ab947a57dc394cf4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726715"
---
# <a name="ccnot-operation"></a><span data-ttu-id="ae3af-102">CCNOT-åtgärd</span><span class="sxs-lookup"><span data-stu-id="ae3af-102">CCNOT operation</span></span>

<span data-ttu-id="ae3af-103">Namnrymd: [Microsoft. Quantum. inbyggt](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="ae3af-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="ae3af-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ae3af-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ae3af-105">Använder den dubbla styrda, inte (CCNOT) porten till tre qubits.</span><span class="sxs-lookup"><span data-stu-id="ae3af-105">Applies the doubly controlled–NOT (CCNOT) gate to three qubits.</span></span>

```qsharp
operation CCNOT (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="ae3af-106">Indata</span><span class="sxs-lookup"><span data-stu-id="ae3af-106">Input</span></span>

### <a name="control1--qubit"></a><span data-ttu-id="ae3af-107">control1: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ae3af-107">control1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="ae3af-108">Första kontrollen qubit för CCNOT-porten.</span><span class="sxs-lookup"><span data-stu-id="ae3af-108">First control qubit for the CCNOT gate.</span></span>


### <a name="control2--qubit"></a><span data-ttu-id="ae3af-109">control2: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ae3af-109">control2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="ae3af-110">Den andra kontrollen qubit för CCNOT-porten.</span><span class="sxs-lookup"><span data-stu-id="ae3af-110">Second control qubit for the CCNOT gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="ae3af-111">mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ae3af-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="ae3af-112">Mål-qubit för CCNOT-porten.</span><span class="sxs-lookup"><span data-stu-id="ae3af-112">Target qubit for the CCNOT gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ae3af-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ae3af-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="ae3af-114">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="ae3af-114">Remarks</span></span>

<span data-ttu-id="ae3af-115">Motsvarar:</span><span class="sxs-lookup"><span data-stu-id="ae3af-115">Equivalent to:</span></span>

```qsharp
Controlled X([control1, control2], target);
```