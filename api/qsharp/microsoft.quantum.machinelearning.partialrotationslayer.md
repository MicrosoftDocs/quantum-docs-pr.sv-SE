---
uid: Microsoft.Quantum.MachineLearning.PartialRotationsLayer
title: Funktionen PartialRotationsLayer
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: PartialRotationsLayer
qsharp.summary: Returns an array of single-qubit rotations along a given axis, parameterized by distinct model parameters.
ms.openlocfilehash: ade0640b07f633982e98d5d02239fa205909bcce
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196250"
---
# <a name="partialrotationslayer-function"></a>Funktionen PartialRotationsLayer

Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Paket: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Returnerar en matris med en qubit rotationer längs en viss axel, parametriserade av distinkta modell parametrar.

```qsharp
function PartialRotationsLayer (idxsQubits : Int[], axis : Pauli) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a>Indata

### <a name="idxsqubits--int"></a>idxsQubits: [int](xref:microsoft.quantum.lang-ref.int)[]

Index för qubits som ska användas som mål för varje rotation.


### <a name="axis--pauli"></a>Axel: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Rotations axeln för varje rotation i det aktuella lagret.



## <a name="output--controlledrotation"></a>Utdata: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]

En matris med kontrollerade rotationer om den aktuella axeln, en på varje `nQubits` qubits.