---
uid: Microsoft.Quantum.MachineLearning.CyclicEntanglingLayer
title: Funktionen CyclicEntanglingLayer
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: CyclicEntanglingLayer
qsharp.summary: Returns an array of singly controlled rotations along a given axis, arranged cyclically across a register of qubits, and parameterized by distinct model parameters.
ms.openlocfilehash: 5421765e36ef3e8e744e118206dafcb2bb582cc2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211941"
---
# <a name="cyclicentanglinglayer-function"></a><span data-ttu-id="61263-102">Funktionen CyclicEntanglingLayer</span><span class="sxs-lookup"><span data-stu-id="61263-102">CyclicEntanglingLayer function</span></span>

<span data-ttu-id="61263-103">Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="61263-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="61263-104">Paket: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="61263-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="61263-105">Returnerar en matris med enstaka kontrollerade rotationer längs en viss axel, som ordnas cykliskt över ett register över qubits och parametriserade av distinkta modell parametrar.</span><span class="sxs-lookup"><span data-stu-id="61263-105">Returns an array of singly controlled rotations along a given axis, arranged cyclically across a register of qubits, and parameterized by distinct model parameters.</span></span>

```qsharp
function CyclicEntanglingLayer (nQubits : Int, axis : Pauli, stride : Int) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a><span data-ttu-id="61263-106">Indata</span><span class="sxs-lookup"><span data-stu-id="61263-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="61263-107">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="61263-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="61263-108">Antalet qubits som har åtgärd ATS av det aktuella skiktet.</span><span class="sxs-lookup"><span data-stu-id="61263-108">The number of qubits acted on by the given layer.</span></span>


### <a name="axis--pauli"></a><span data-ttu-id="61263-109">Axel: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="61263-109">axis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="61263-110">Rotations axeln för varje rotation i det aktuella lagret.</span><span class="sxs-lookup"><span data-stu-id="61263-110">The rotation axis for each rotation in the given layer.</span></span>


### <a name="stride--int"></a><span data-ttu-id="61263-111">Kliv: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="61263-111">stride : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="61263-112">Separeringen mellan mål-och kontroll index för varje rotation.</span><span class="sxs-lookup"><span data-stu-id="61263-112">The separation between the target and control indices for each rotation.</span></span>



## <a name="output--controlledrotation"></a><span data-ttu-id="61263-113">Utdata: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="61263-113">Output : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="61263-114">En matris med två-qubit kontrollerade rotationer som fastställs i sidled i ett register över `nQubits` qubits.</span><span class="sxs-lookup"><span data-stu-id="61263-114">An array of two-qubit controlled rotations laid out cyclically across a register of `nQubits` qubits.</span></span>