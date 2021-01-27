---
uid: Microsoft.Quantum.MachineLearning.LocalRotationsLayer
title: Funktionen LocalRotationsLayer
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LocalRotationsLayer
qsharp.summary: Returns an array of uncontrolled (single-qubit) rotations along a given axis, with one rotation for each qubit in a register, parameterized by distinct model parameters.
ms.openlocfilehash: a3658bbf62068c9eea2d9b763cbff5596f426135
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854984"
---
# <a name="localrotationslayer-function"></a><span data-ttu-id="f961e-102">Funktionen LocalRotationsLayer</span><span class="sxs-lookup"><span data-stu-id="f961e-102">LocalRotationsLayer function</span></span>

<span data-ttu-id="f961e-103">Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="f961e-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="f961e-104">Paket: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="f961e-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="f961e-105">Returnerar en matris med okontrollerade (Single-qubit) rotationer längs en viss axel, med en rotation för varje qubit i ett register, med parametrar av distinkta modell parametrar.</span><span class="sxs-lookup"><span data-stu-id="f961e-105">Returns an array of uncontrolled (single-qubit) rotations along a given axis, with one rotation for each qubit in a register, parameterized by distinct model parameters.</span></span>

```qsharp
function LocalRotationsLayer (nQubits : Int, axis : Pauli) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a><span data-ttu-id="f961e-106">Indata</span><span class="sxs-lookup"><span data-stu-id="f961e-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="f961e-107">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f961e-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f961e-108">Antalet qubits som har åtgärd ATS av det aktuella skiktet.</span><span class="sxs-lookup"><span data-stu-id="f961e-108">The number of qubits acted on by the given layer.</span></span>


### <a name="axis--pauli"></a><span data-ttu-id="f961e-109">Axel: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="f961e-109">axis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="f961e-110">Rotations axeln för varje rotation i det aktuella lagret.</span><span class="sxs-lookup"><span data-stu-id="f961e-110">The rotation axis for each rotation in the given layer.</span></span>



## <a name="output--controlledrotation"></a><span data-ttu-id="f961e-111">Utdata: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="f961e-111">Output : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="f961e-112">En matris med kontrollerade rotationer om den aktuella axeln, en på varje `nQubits` qubits.</span><span class="sxs-lookup"><span data-stu-id="f961e-112">An array of controlled rotations about the given axis, one on each of `nQubits` qubits.</span></span>