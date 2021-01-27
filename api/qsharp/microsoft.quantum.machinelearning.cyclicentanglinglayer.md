---
uid: Microsoft.Quantum.MachineLearning.CyclicEntanglingLayer
title: Funktionen CyclicEntanglingLayer
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: CyclicEntanglingLayer
qsharp.summary: Returns an array of singly controlled rotations along a given axis, arranged cyclically across a register of qubits, and parameterized by distinct model parameters.
ms.openlocfilehash: 5d0af0a60217b69dc7eb8ece8952f2a7f0c09280
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847384"
---
# <a name="cyclicentanglinglayer-function"></a><span data-ttu-id="b00fa-102">Funktionen CyclicEntanglingLayer</span><span class="sxs-lookup"><span data-stu-id="b00fa-102">CyclicEntanglingLayer function</span></span>

<span data-ttu-id="b00fa-103">Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="b00fa-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="b00fa-104">Paket: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="b00fa-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="b00fa-105">Returnerar en matris med enstaka kontrollerade rotationer längs en viss axel, som ordnas cykliskt över ett register över qubits och parametriserade av distinkta modell parametrar.</span><span class="sxs-lookup"><span data-stu-id="b00fa-105">Returns an array of singly controlled rotations along a given axis, arranged cyclically across a register of qubits, and parameterized by distinct model parameters.</span></span>

```qsharp
function CyclicEntanglingLayer (nQubits : Int, axis : Pauli, stride : Int) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a><span data-ttu-id="b00fa-106">Indata</span><span class="sxs-lookup"><span data-stu-id="b00fa-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="b00fa-107">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b00fa-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b00fa-108">Antalet qubits som har åtgärd ATS av det aktuella skiktet.</span><span class="sxs-lookup"><span data-stu-id="b00fa-108">The number of qubits acted on by the given layer.</span></span>


### <a name="axis--pauli"></a><span data-ttu-id="b00fa-109">Axel: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="b00fa-109">axis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="b00fa-110">Rotations axeln för varje rotation i det aktuella lagret.</span><span class="sxs-lookup"><span data-stu-id="b00fa-110">The rotation axis for each rotation in the given layer.</span></span>


### <a name="stride--int"></a><span data-ttu-id="b00fa-111">Kliv: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b00fa-111">stride : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b00fa-112">Separeringen mellan mål-och kontroll index för varje rotation.</span><span class="sxs-lookup"><span data-stu-id="b00fa-112">The separation between the target and control indices for each rotation.</span></span>



## <a name="output--controlledrotation"></a><span data-ttu-id="b00fa-113">Utdata: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="b00fa-113">Output : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="b00fa-114">En matris med två-qubit kontrollerade rotationer som fastställs i sidled i ett register över `nQubits` qubits.</span><span class="sxs-lookup"><span data-stu-id="b00fa-114">An array of two-qubit controlled rotations laid out cyclically across a register of `nQubits` qubits.</span></span>

## <a name="example"></a><span data-ttu-id="b00fa-115">Exempel</span><span class="sxs-lookup"><span data-stu-id="b00fa-115">Example</span></span>

<span data-ttu-id="b00fa-116">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="b00fa-116">The following are equivalent:</span></span>

```qsharp
let layer = CyclicEntanglingLayer(3, PauliX, 2);
let layer = [
    ControlledRotation((0, [2]), PauliX, 0),
    ControlledRotation((1, [0]), PauliX, 1),
    ControlledRotation((2, [1]), PauliX, 2)
];
```