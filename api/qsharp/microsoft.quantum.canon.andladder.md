---
uid: Microsoft.Quantum.Canon.AndLadder
title: AndLadder-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: AndLadder
qsharp.summary: Performs a controlled "AND ladder" on a register of target qubits.
ms.openlocfilehash: d44c462c7a9fc9521bdecfe2ca7f607e90482baf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845230"
---
# <a name="andladder-operation"></a>AndLadder-åtgärd

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Utför en kontrollerad "och stege" i ett register över mål qubits.

```qsharp
operation AndLadder (ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit is Adj
```


## <a name="description"></a>Description

Den här åtgärden använder en omvandling som beskrivs i följande mappning av beräknings basen, $ $ \begin{align} \ket{x \_ 1, \dots, x \_ n} \ket{y \_ 1, \dots, y \_ {n-1}} \mapsto \ket{x \_ 1, \dots, x \_ n} \ket{y \_ 1 \oplus (x \_ 1 \land x \_ 2). \dots, y \_ {n-1} \oplus (x \_ 1 \land x \_ 2 \land \cdots \land x \_ {n-1}}, \end{align} $ $ där $ \ket{x \_ 1, \dots, x \_ n} $ refererar till beräknings bas tillstånden för `controls` och där $ \ket{y \_ 1, \dots, y \_ {n-1}} $ refererar till beräknings bas tillstånden för `targets` .

## <a name="input"></a>Indata

### <a name="ccnot--ccnotop"></a>ccnot: [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)

CCNOT-porten som ska användas för byggnaden.


### <a name="controls--qubit"></a>kontroller: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Ett register över qubits som ska användas som kontroller för och steg-för-steg-exempel.
Den här åtgärden lämnar beräknings bas tillstånd för `controls` invariant.
Längden `controls` måste vara minst 2 och måste vara lika med en plus längden `targets` .


### <a name="targets--qubit"></a>mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Längden `targets` måste vara minst 1 och lika med längden på `controls` minus ett.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Kommentarer

- Används som en del av <xref:microsoft.quantum.canon.applymulticontrolledc> och <xref:microsoft.quantum.canon.applymulticontrolledca> .
- För förklarings diagrammet och krets diagrammet ser du bild 4,10, avsnitt 4,3 i Nielsen & Chuang.

## <a name="references"></a>Referenser

- [*Michael A. Nielsen, Isak L. Chuang*, Quantum-beräkning och Quantum-information](http://doi.org/10.1017/CBO9780511976667)