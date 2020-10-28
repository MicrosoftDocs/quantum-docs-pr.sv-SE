---
uid: Microsoft.Quantum.MachineLearning.ControlledRotation
title: ControlledRotation-användardefinierad typ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ControlledRotation
qsharp.summary: Describes a controlled rotation in terms of its target and control indices, rotation axis, and index into a model parameter vector.
ms.openlocfilehash: afc425c16ab550fd414e656484c9ff6f0f8f3ef4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726640"
---
# <a name="controlledrotation-user-defined-type"></a>ControlledRotation-användardefinierad typ

Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Paketfilerna [](https://nuget.org/packages/)


Beskriver en kontrollerad rotation i termer av mål-och kontroll index, rotations axel och index i en modell parameter vektor.

```qsharp

newtype ControlledRotation = ((TargetIndex : Int, ControlIndices : Int[]), Axis : Pauli, ParameterIndex : Int);
```



## <a name="named-items"></a>Namngivna objekt

### <a name="targetindex--int"></a>TargetIndex: [int](xref:microsoft.quantum.lang-ref.int)

Index för mål-qubit för den här kontrollerade rotationen.
### <a name="controlindices--int"></a>ControlIndices: [int](xref:microsoft.quantum.lang-ref.int)[]

En matris med kontrollens qubit index för den här rotationen.
### <a name="axis--pauli"></a>Axel: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Axeln för den här rotationen.
### <a name="parameterindex--int"></a>ParameterIndex: [int](xref:microsoft.quantum.lang-ref.int)

Ett index i en modell parameter vektor som beskriver vinkeln för den här rotationen.

## <a name="remarks"></a>Kommentarer

En okontrollerad rotation kan representeras genom `ControlIndices` att ställa in en tom matris med index `new Int[0]` .