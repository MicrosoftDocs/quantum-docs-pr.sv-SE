---
uid: Microsoft.Quantum.Canon.ApplyPauli
title: ApplyPauli-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyPauli
qsharp.summary: Given a multi-qubit Pauli operator, applies the corresponding operation to a register.
ms.openlocfilehash: b3557c6d8b5a90019f6d4cfa7b405475a3ab39fb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844741"
---
# <a name="applypauli-operation"></a>ApplyPauli-åtgärd

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Med en qubit Pauli-operatör tillämpas motsvarande åtgärd i en register.

```qsharp
operation ApplyPauli (pauli : Pauli[], target : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Indata

### <a name="pauli--pauli"></a>Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

En qubit Pauli-operatör som representeras som en matris med qubit Pauli-operatörer.


### <a name="target--qubit"></a>mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registrera dig för att tillämpa den aktuella Pauli-åtgärden på.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>Exempel

Följande är likvärdiga:

```qsharp
ApplyPauli([PauliY, PauliZ, PauliX], target);
```

och

```qsharp
Y(target[0]);
Z(target[1]);
X(target[2]);
```