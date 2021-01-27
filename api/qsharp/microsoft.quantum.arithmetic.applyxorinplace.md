---
uid: Microsoft.Quantum.Arithmetic.ApplyXorInPlace
title: ApplyXorInPlace-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyXorInPlace
qsharp.summary: Applies a bitwise-XOR operation between a classical integer and an integer represented by a register of qubits.
ms.openlocfilehash: 8f338d6638d554f3ead1f3c0e7b6605c7937abd8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843477"
---
# <a name="applyxorinplace-operation"></a>ApplyXorInPlace-åtgärd

Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Tillämpar en Bitvis-XOR-åtgärd mellan ett klassiskt heltal och ett heltal som representeras av ett register av qubits.

```qsharp
operation ApplyXorInPlace (value : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

Tillämpar `X` åtgärder på qubits i ett litet endian-register baserat på 1 bitar i ett heltal.

Låt oss ange `value` ett och låt y vara ett osignerat heltal som är kodat i `target` och `InPlaceXorLE` utför sedan en åtgärd som anges av följande karta: $ \ket{y}\rightarrow \ket{y\oplus a} $, där $ \oplus $ är den bitvisa eller operatorn.

## <a name="input"></a>Indata

### <a name="value--int"></a>värde: [int](xref:microsoft.quantum.lang-ref.int)

Ett heltal som antas vara icke-negativt.


### <a name="target--littleendian"></a>mål: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Ett Quantum-register som används för att lagra `value` i lite endian-kodning.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)

