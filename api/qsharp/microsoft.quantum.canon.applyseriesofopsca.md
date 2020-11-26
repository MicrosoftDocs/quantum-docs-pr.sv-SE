---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsCA
title: ApplySeriesOfOpsCA-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsCA
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Adjoint + Controlled)
ms.openlocfilehash: 9dd1343b3ebcc75592441f150eee822cfe83f9a1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217891"
---
# <a name="applyseriesofopsca-operation"></a>ApplySeriesOfOpsCA-åtgärd

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Använder en lista med OPS och deras mål sekventiellt i en matris. (Angränsande + styrd)

```qsharp
operation ApplySeriesOfOpsCA<'T> (listOfOps : ('T[] => Unit is Adj + Ctl)[], targets : Int[][], register : 'T[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Indata

### <a name="listofops--t--unit--is-adj--ctl"></a>listOfOps: ' t [] => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL []

En lista med OPS, vart och ett som tar en matris som ska tillämpas. De tillämpas sekventiellt, lägsta index först.
Varje måste ha både ett överfunctort och kontrollerat.


### <a name="targets--int"></a>mål: [int](xref:microsoft.quantum.lang-ref.int)[] []

Kapslade matriser som beskriver målen för op. Varje matris ska innehålla en lista över InTS som beskriver de index som ska användas.


### <a name="register--t"></a>Registrera: ' ' []

Qubit-register att du ska handla på.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte



## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Canon. ApplyOpRepeatedlyOver](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)