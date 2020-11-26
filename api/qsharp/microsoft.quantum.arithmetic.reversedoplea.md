---
uid: Microsoft.Quantum.Arithmetic.ReversedOpLEA
title: Funktionen ReversedOpLEA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpLEA
qsharp.summary: Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.
ms.openlocfilehash: 71b6b87a44f541e5379d8de8a3562febbfa49e1d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222175"
---
# <a name="reversedoplea-function"></a>Funktionen ReversedOpLEA

Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Med en åtgärd som tar lite-endian-indatamängd returnerar en ny åtgärd som tar en big-endian-indatamängd.

```qsharp
function ReversedOpLEA (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj)) : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj)
```


## <a name="input"></a>Indata

### <a name="op--littleendian--unit--is-adj"></a>OP: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  rejust

Åtgärden vars indatatyper ska ångras.



## <a name="output--bigendian--unit--is-adj"></a>Utdata: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  rejust

En ny åtgärd som accepterar indatatypen som en big-endian-registrering.

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. aritmetiska. ApplyReversedOpLEA](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA)
- [Microsoft. Quantum. aritmetiska. ReversedOpLE](xref:Microsoft.Quantum.Arithmetic.ReversedOpLE)
- [Microsoft. Quantum. aritmetiska. ReversedOpLEC](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEC)
- [Microsoft. Quantum. aritmetiska. ReversedOpLECA](xref:Microsoft.Quantum.Arithmetic.ReversedOpLECA)