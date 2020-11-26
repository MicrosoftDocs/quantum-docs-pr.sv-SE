---
uid: Microsoft.Quantum.Bitwise.ZBits
title: Funktionen ZBits
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: ZBits
qsharp.summary: Returns an integer representing the Z bits of an array of Pauli operators.
ms.openlocfilehash: 3ded981dc53236a48f1fb8f6ae12e39c17469447
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219455"
---
# <a name="zbits-function"></a>Funktionen ZBits

Namnrymd: [Microsoft. Quantum. bitvis](xref:Microsoft.Quantum.Bitwise)

Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Returnerar ett heltal som representerar Z-bitarna för en matris med Pauli-operatorer.

```qsharp
function ZBits (paulis : Pauli[]) : Int
```


## <a name="input"></a>Indata

### <a name="paulis--pauli"></a>Paulis: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

En matris med Pauli-operatorer som ska representeras som ett heltal.



## <a name="output--int"></a>Utdata: [int](xref:microsoft.quantum.lang-ref.int)

Ett heltal $x $ med binär representation $ (p_ {62} \, p_ {61} \, \dots \, p_0) $, där $p _i = $0 om `paulis[i]` är `PauliI` eller `PauliX` och där $p _i = $1 om `paulis[i]` är `PauliY` eller `PauliZ` .

## <a name="remarks"></a>Kommentarer

Funktionen kommer att utlösa om längden på `paulis` matrisen är större än 63.

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. bitvis. XBits](xref:Microsoft.Quantum.Bitwise.XBits)