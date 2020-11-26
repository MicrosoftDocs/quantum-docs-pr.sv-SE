---
uid: Microsoft.Quantum.Bitwise.XBits
title: Funktionen XBits
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: XBits
qsharp.summary: Returns an integer representing the X bits of an array of Pauli operators.
ms.openlocfilehash: 969be01204bad497496ff24cb64213f5fe1f089b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209765"
---
# <a name="xbits-function"></a>Funktionen XBits

Namnrymd: [Microsoft. Quantum. bitvis](xref:Microsoft.Quantum.Bitwise)

Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Returnerar ett heltal som representerar X-bitarna för en matris med Pauli-operatorer.

```qsharp
function XBits (paulis : Pauli[]) : Int
```


## <a name="input"></a>Indata

### <a name="paulis--pauli"></a>Paulis: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

En matris med Pauli-operatorer som ska representeras som ett heltal.



## <a name="output--int"></a>Utdata: [int](xref:microsoft.quantum.lang-ref.int)

Ett heltal $x $ med binär representation $ (p_ {62} \, p_ {61} \, \dots \, p_0) $, där $p _i = $0 om `paulis[i]` är `PauliI` eller `PauliZ` och där $p _i = $1 om `paulis[i]` är `PauliX` eller `PauliY` .

## <a name="remarks"></a>Kommentarer

Funktionen kommer att utlösa om längden på `paulis` matrisen är större än 63.

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. bitvis. ZBits](xref:Microsoft.Quantum.Bitwise.ZBits)