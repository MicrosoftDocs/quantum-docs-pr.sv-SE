---
uid: Microsoft.Quantum.MachineLearning.LocalRotationsLayer
title: Funktionen LocalRotationsLayer
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LocalRotationsLayer
qsharp.summary: Returns an array of uncontrolled (single-qubit) rotations along a given axis, with one rotation for each qubit in a register, parameterized by distinct model parameters.
ms.openlocfilehash: 8a3557f76d5d7a7b6375e5640cf6d11172cd38a6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732915"
---
# <a name="localrotationslayer-function"></a>Funktionen LocalRotationsLayer

Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Paketfilerna [](https://nuget.org/packages/)


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