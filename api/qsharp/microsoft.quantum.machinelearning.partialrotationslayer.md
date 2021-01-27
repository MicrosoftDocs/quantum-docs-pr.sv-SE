---
uid: Microsoft.Quantum.MachineLearning.PartialRotationsLayer
title: Funktionen PartialRotationsLayer
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: PartialRotationsLayer
qsharp.summary: Returns an array of single-qubit rotations along a given axis, parameterized by distinct model parameters.
ms.openlocfilehash: e230df9b28c59e1d532d5b36adf90efa01f0f33e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852923"
---
# <a name="partialrotationslayer-function"></a><span data-ttu-id="4ea2f-102">Funktionen PartialRotationsLayer</span><span class="sxs-lookup"><span data-stu-id="4ea2f-102">PartialRotationsLayer function</span></span>

<span data-ttu-id="4ea2f-103">Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="4ea2f-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="4ea2f-104">Paket: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="4ea2f-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="4ea2f-105">Returnerar en matris med en qubit rotationer längs en viss axel, parametriserade av distinkta modell parametrar.</span><span class="sxs-lookup"><span data-stu-id="4ea2f-105">Returns an array of single-qubit rotations along a given axis, parameterized by distinct model parameters.</span></span>

```qsharp
function PartialRotationsLayer (idxsQubits : Int[], axis : Pauli) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a><span data-ttu-id="4ea2f-106">Indata</span><span class="sxs-lookup"><span data-stu-id="4ea2f-106">Input</span></span>

### <a name="idxsqubits--int"></a><span data-ttu-id="4ea2f-107">idxsQubits: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="4ea2f-107">idxsQubits : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="4ea2f-108">Index för qubits som ska användas som mål för varje rotation.</span><span class="sxs-lookup"><span data-stu-id="4ea2f-108">Indices for the qubits to be used as the targets for each rotation.</span></span>


### <a name="axis--pauli"></a><span data-ttu-id="4ea2f-109">Axel: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="4ea2f-109">axis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="4ea2f-110">Rotations axeln för varje rotation i det aktuella lagret.</span><span class="sxs-lookup"><span data-stu-id="4ea2f-110">The rotation axis for each rotation in the given layer.</span></span>



## <a name="output--controlledrotation"></a><span data-ttu-id="4ea2f-111">Utdata: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="4ea2f-111">Output : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="4ea2f-112">En matris med kontrollerade rotationer om den aktuella axeln, en på varje `nQubits` qubits.</span><span class="sxs-lookup"><span data-stu-id="4ea2f-112">An array of controlled rotations about the given axis, one on each of `nQubits` qubits.</span></span>