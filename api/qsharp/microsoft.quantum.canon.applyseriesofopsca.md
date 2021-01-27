---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsCA
title: ApplySeriesOfOpsCA-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsCA
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Adjoint + Controlled)
ms.openlocfilehash: 9a1f6189428b086c38b1d0f289afb18c2cf1be40
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850872"
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



## <a name="example"></a>Exempel

Följande gäller exp ([PauliX, PauliY], 0,5) till qubits 0, 1//sedan X till qubit 2 låt Ops = [exp ([PauliX, PauliY], 0,5, _), ApplyToFirstQubitCA (X, _)]; Låt index = [[0, 1], [2]]; ApplySeriesOfOpsCA (OPS, index, qubitArray)

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Canon. ApplyOpRepeatedlyOver](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)