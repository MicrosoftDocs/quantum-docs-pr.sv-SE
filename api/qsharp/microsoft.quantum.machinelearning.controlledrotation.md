---
uid: Microsoft.Quantum.MachineLearning.ControlledRotation
title: ControlledRotation-användardefinierad typ
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ControlledRotation
qsharp.summary: Describes a controlled rotation in terms of its target and control indices, rotation axis, and index into a model parameter vector.
ms.openlocfilehash: 231afe65da3640218cbc97b9d49eae21bf6e1786
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847402"
---
# <a name="controlledrotation-user-defined-type"></a>ControlledRotation-användardefinierad typ

Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Paket: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


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

## <a name="example"></a>Exempel

Nedan visas en rotation om $X $-axeln för den första qubit i ett register, som styrs på den andra qubit och med en vinkel som angetts av den fjärde parametern i en sekventiell modell:

```qsharp
let controlledRotation = ControlledRotation(
    (0, [1]),
    PauliX,
    3
)
```

## <a name="remarks"></a>Kommentarer

En okontrollerad rotation kan representeras genom `ControlIndices` att ställa in en tom matris med index `new Int[0]` .