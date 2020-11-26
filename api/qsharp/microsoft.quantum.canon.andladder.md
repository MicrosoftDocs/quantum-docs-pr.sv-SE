---
uid: Microsoft.Quantum.Canon.AndLadder
title: AndLadder-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: AndLadder
qsharp.summary: Performs a controlled "AND ladder" on a register of target qubits.
ms.openlocfilehash: 2c6114ec8a5caabdeea8ab7e26a4877e1633671c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209731"
---
# <a name="andladder-operation"></a>AndLadder-åtgärd

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Utför en kontrollerad "och stege" i ett register över mål qubits.

```qsharp
operation AndLadder (ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit is Adj
```


## <a name="description"></a>Beskrivning

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