---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsA
title: ApplySeriesOfOpsA-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsA
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Adjoint)
ms.openlocfilehash: e5b3527507f79dcc77803ce01472856145df0e9f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217976"
---
# <a name="applyseriesofopsa-operation"></a>ApplySeriesOfOpsA-åtgärd

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Använder en lista med OPS och deras mål sekventiellt i en matris. (Angränsande)

```qsharp
operation ApplySeriesOfOpsA<'T> (listOfOps : ('T[] => Unit is Adj)[], targets : Int[][], register : 'T[]) : Unit is Adj
```


## <a name="input"></a>Indata

### <a name="listofops--t--unit--is-adj"></a>listOfOps: ' t [] => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just []

En lista med OPS, vart och ett som tar en matris som ska tillämpas. De tillämpas sekventiellt, lägsta index först.
Varje måste ha ett angränsande Functor


### <a name="targets--int"></a>mål: [int](xref:microsoft.quantum.lang-ref.int)[] []

Kapslade matriser som beskriver målen för op. Varje matris ska innehålla en lista över InTS som beskriver de index som ska användas.


### <a name="register--t"></a>Registrera: ' ' []

Qubit-register att du ska handla på.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte



## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Canon. ApplyOpRepeatedlyOver](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)