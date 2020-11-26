---
uid: Microsoft.Quantum.Arithmetic.ReversedOpLE
title: Funktionen ReversedOpLE
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpLE
qsharp.summary: Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.
ms.openlocfilehash: 91b98663028b8a1d54c546e70d8bfe603d71d041
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222260"
---
# <a name="reversedople-function"></a>Funktionen ReversedOpLE

Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Med en åtgärd som tar lite-endian-indatamängd returnerar en ny åtgärd som tar en big-endian-indatamängd.

```qsharp
function ReversedOpLE (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit)) : (Microsoft.Quantum.Arithmetic.BigEndian => Unit)
```


## <a name="input"></a>Indata

### <a name="op--littleendian--unit"></a>OP: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) 

Åtgärden vars indatatyper ska ångras.



## <a name="output--bigendian--unit"></a>Utdata: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) 

En ny åtgärd som accepterar indatatypen som en big-endian-registrering.

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. aritmetiska. ApplyReversedOpLE](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLE)
- [Microsoft. Quantum. aritmetiska. ReversedOpLEA](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEA)
- [Microsoft. Quantum. aritmetiska. ReversedOpLEC](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEC)
- [Microsoft. Quantum. aritmetiska. ReversedOpLECA](xref:Microsoft.Quantum.Arithmetic.ReversedOpLECA)