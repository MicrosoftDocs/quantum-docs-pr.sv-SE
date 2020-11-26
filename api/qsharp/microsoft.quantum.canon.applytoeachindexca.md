---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexCA
title: ApplyToEachIndexCA-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexCA
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `CA` indicates that the single-qubit operation is adjointable and controllable.
ms.openlocfilehash: abb616498a8ff9c3348df81cf0ca1a1669561eec
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208949"
---
# <a name="applytoeachindexca-operation"></a>ApplyToEachIndexCA-åtgärd

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Tillämpar en enskild qubit-åtgärd på varje indexerat element i en register.
Modifieraren `CA` anger att en qubit-åtgärd är adjointable och kan kontrol leras.

```qsharp
operation ApplyToEachIndexCA<'T> (singleElementOperation : ((Int, 'T) => Unit is Adj + Ctl), register : 'T[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Indata

### <a name="singleelementoperation--intt--unit--is-adj--ctl"></a>singleElementOperation: ([int](xref:microsoft.quantum.lang-ref.int), t) => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL

Åtgärd att tillämpa på varje qubit.


### <a name="register--t"></a>Registrera: ' ' []

Matris för qubits som den aktuella åtgärden ska tillämpas på.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

Målet som varje åtgärd agerar på.

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Canon. ApplyToEachIndex](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)