---
uid: Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver
title: ApplyOpRepeatedlyOver-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyOpRepeatedlyOver
qsharp.summary: Applies the same op over a qubit register multiple times.
ms.openlocfilehash: 263eff8ec31f5ee36485eb1d2ed52bf15cef4bef
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844804"
---
# <a name="applyoprepeatedlyover-operation"></a>ApplyOpRepeatedlyOver-åtgärd

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Använder samma OP över ett qubit-register flera gånger.

```qsharp
operation ApplyOpRepeatedlyOver (op : (Qubit[] => Unit), targets : Int[][], register : Qubit[]) : Unit
```


## <a name="input"></a>Indata

### <a name="op--qubit--unit"></a>OP: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhet](xref:microsoft.quantum.lang-ref.unit) 

En åtgärd som ska tillämpas flera gånger på qubit-registreringen


### <a name="targets--int"></a>mål: [int](xref:microsoft.quantum.lang-ref.int)[] []

Kapslade matriser som beskriver målen för op. Varje matris ska innehålla en lista över InTS som beskriver de qubits som ska användas.


### <a name="register--qubit"></a>Registrera: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubit-register att du ska handla på.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Canon. ApplySeriesOfOps](xref:Microsoft.Quantum.Canon.ApplySeriesOfOps)