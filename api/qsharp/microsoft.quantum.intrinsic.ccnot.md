---
uid: Microsoft.Quantum.Intrinsic.CCNOT
title: CCNOT-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: CCNOT
qsharp.summary: Applies the doubly controlled–NOT (CCNOT) gate to three qubits.
ms.openlocfilehash: 715796ddd915d80036933e3f1ceefa97aa62cecf
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96212485"
---
# <a name="ccnot-operation"></a><span data-ttu-id="ea8bb-102">CCNOT-åtgärd</span><span class="sxs-lookup"><span data-stu-id="ea8bb-102">CCNOT operation</span></span>

<span data-ttu-id="ea8bb-103">Namnrymd: [Microsoft. Quantum. inbyggt](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="ea8bb-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="ea8bb-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="ea8bb-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="ea8bb-105">Använder den dubbla styrda, inte (CCNOT) porten till tre qubits.</span><span class="sxs-lookup"><span data-stu-id="ea8bb-105">Applies the doubly controlled–NOT (CCNOT) gate to three qubits.</span></span>

```qsharp
operation CCNOT (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="ea8bb-106">Indata</span><span class="sxs-lookup"><span data-stu-id="ea8bb-106">Input</span></span>

### <a name="control1--qubit"></a><span data-ttu-id="ea8bb-107">control1: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ea8bb-107">control1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="ea8bb-108">Första kontrollen qubit för CCNOT-porten.</span><span class="sxs-lookup"><span data-stu-id="ea8bb-108">First control qubit for the CCNOT gate.</span></span>


### <a name="control2--qubit"></a><span data-ttu-id="ea8bb-109">control2: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ea8bb-109">control2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="ea8bb-110">Den andra kontrollen qubit för CCNOT-porten.</span><span class="sxs-lookup"><span data-stu-id="ea8bb-110">Second control qubit for the CCNOT gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="ea8bb-111">mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ea8bb-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="ea8bb-112">Mål-qubit för CCNOT-porten.</span><span class="sxs-lookup"><span data-stu-id="ea8bb-112">Target qubit for the CCNOT gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ea8bb-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ea8bb-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="ea8bb-114">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="ea8bb-114">Remarks</span></span>

<span data-ttu-id="ea8bb-115">Motsvarar:</span><span class="sxs-lookup"><span data-stu-id="ea8bb-115">Equivalent to:</span></span>

```qsharp
Controlled X([control1, control2], target);
```