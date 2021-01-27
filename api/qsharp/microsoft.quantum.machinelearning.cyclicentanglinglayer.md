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
# <a name="cyclicentanglinglayer-function"></a>Funktionen CyclicEntanglingLayer

Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Paket: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Returnerar en matris med enstaka kontrollerade rotationer längs en viss axel, som ordnas cykliskt över ett register över qubits och parametriserade av distinkta modell parametrar.

```qsharp
function CyclicEntanglingLayer (nQubits : Int, axis : Pauli, stride : Int) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a>Indata

### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

Antalet qubits som har åtgärd ATS av det aktuella skiktet.


### <a name="axis--pauli"></a>Axel: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Rotations axeln för varje rotation i det aktuella lagret.


### <a name="stride--int"></a>Kliv: [int](xref:microsoft.quantum.lang-ref.int)

Separeringen mellan mål-och kontroll index för varje rotation.



## <a name="output--controlledrotation"></a>Utdata: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]

En matris med två-qubit kontrollerade rotationer som fastställs i sidled i ett register över `nQubits` qubits.

## <a name="example"></a>Exempel

Följande är likvärdiga:

```qsharp
let layer = CyclicEntanglingLayer(3, PauliX, 2);
let layer = [
    ControlledRotation((0, [2]), PauliX, 0),
    ControlledRotation((1, [0]), PauliX, 1),
    ControlledRotation((2, [1]), PauliX, 2)
];
```