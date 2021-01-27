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
# <a name="localrotationslayer-function"></a>Funktionen LocalRotationsLayer

Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Paket: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Returnerar en matris med okontrollerade (Single-qubit) rotationer längs en viss axel, med en rotation för varje qubit i ett register, med parametrar av distinkta modell parametrar.

```qsharp
function LocalRotationsLayer (nQubits : Int, axis : Pauli) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a>Indata

### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

Antalet qubits som har åtgärd ATS av det aktuella skiktet.


### <a name="axis--pauli"></a>Axel: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Rotations axeln för varje rotation i det aktuella lagret.



## <a name="output--controlledrotation"></a>Utdata: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]

En matris med kontrollerade rotationer om den aktuella axeln, en på varje `nQubits` qubits.