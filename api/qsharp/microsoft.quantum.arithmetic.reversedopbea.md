---
uid: Microsoft.Quantum.Arithmetic.ReversedOpBEA
title: Funktionen ReversedOpBEA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpBEA
qsharp.summary: Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.
ms.openlocfilehash: 69fd4401e6862a3a6afaa51fb5b8a3592768bb42
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222311"
---
# <a name="reversedopbea-function"></a>Funktionen ReversedOpBEA

Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Med en åtgärd som tar big-endian-indatamängd returnerar en ny åtgärd som tar lite-endian-indatamängd.

```qsharp
function ReversedOpBEA (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj)) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj)
```


## <a name="input"></a>Indata

### <a name="op--bigendian--unit--is-adj"></a>OP: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  rejust

Åtgärden vars indatatyper ska ångras.



## <a name="output--littleendian--unit--is-adj"></a>Utdata: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  rejust

En ny åtgärd som accepterar indatatypen som ett litet endian-register.

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. aritmetiska. ApplyReversedOpBEA](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA)
- [Microsoft. Quantum. aritmetiska. ReversedOpBE](xref:Microsoft.Quantum.Arithmetic.ReversedOpBE)
- [Microsoft. Quantum. aritmetiska. ReversedOpBEC](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEC)
- [Microsoft. Quantum. aritmetiska. ReversedOpBECA](xref:Microsoft.Quantum.Arithmetic.ReversedOpBECA)