---
uid: Microsoft.Quantum.Arithmetic.ApplyXorInPlace
title: ApplyXorInPlace-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyXorInPlace
qsharp.summary: Applies a bitwise-XOR operation between a classical integer and an integer represented by a register of qubits.
ms.openlocfilehash: b7fc20ac421d5cff9baa3fe05450c1564f123505
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210121"
---
# <a name="applyxorinplace-operation"></a>ApplyXorInPlace-åtgärd

Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Tillämpar en Bitvis-XOR-åtgärd mellan ett klassiskt heltal och ett heltal som representeras av ett register av qubits.

```qsharp
operation ApplyXorInPlace (value : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Beskrivning

Tillämpar `X` åtgärder på qubits i ett litet endian-register baserat på 1 bitar i ett heltal.

Låt oss ange `value` ett och låt y vara ett osignerat heltal som är kodat i `target` och `InPlaceXorLE` utför sedan en åtgärd som anges av följande karta: $ \ket{y}\rightarrow \ket{y\oplus a} $, där $ \oplus $ är den bitvisa eller operatorn.

## <a name="input"></a>Indata

### <a name="value--int"></a>värde: [int](xref:microsoft.quantum.lang-ref.int)

Ett heltal som antas vara icke-negativt.


### <a name="target--littleendian"></a>mål: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Ett Quantum-register som används för att lagra `value` i lite endian-kodning.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)

