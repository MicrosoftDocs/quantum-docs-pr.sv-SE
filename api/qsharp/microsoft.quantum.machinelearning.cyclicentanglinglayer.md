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