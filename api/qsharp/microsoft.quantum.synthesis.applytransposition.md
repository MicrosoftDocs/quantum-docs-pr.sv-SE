---
uid: Microsoft.Quantum.Synthesis.ApplyTransposition
title: ApplyTransposition-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyTransposition
qsharp.summary: ''
ms.openlocfilehash: ca22b090f2b2613f07caef698941ea608374ab1e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203322"
---
# <a name="applytransposition-operation"></a>ApplyTransposition-åtgärd

Namnrymd: [Microsoft. Quantum. syntes](xref:Microsoft.Quantum.Synthesis)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)




```qsharp
operation ApplyTransposition (a : Int, b : Int, qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Beskrivning

Den här åtgärden byter till amplituden vid indexet `a` med amplituden vid indexet `b` i det aktuella tillståndets vektor med `register` längden $n $.  Om `a` det är lika med `b` ändras inte tillstånds vektorn.

## <a name="input"></a>Indata

### <a name="a--int"></a>a: [int](xref:microsoft.quantum.lang-ref.int)

Första index (måste vara ett värde mellan 0 och $2 ^ n-$1)


### <a name="b--int"></a>b: [int](xref:microsoft.quantum.lang-ref.int)

Andra indexet (måste vara ett värde mellan 0 och $2 ^ n-$1)


### <a name="qubits--littleendian"></a>qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

En lista över $n $ qubits som införlivaren tillämpas på.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)

