---
uid: Microsoft.Quantum.Arithmetic.ReversedOpLECA
title: Funktionen ReversedOpLECA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpLECA
qsharp.summary: Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.
ms.openlocfilehash: c058243db2b4cee3a72e025b084b4f98f7020a6b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222073"
---
# <a name="reversedopleca-function"></a>Funktionen ReversedOpLECA

Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Med en åtgärd som tar lite-endian-indatamängd returnerar en ny åtgärd som tar en big-endian-indatamängd.

```qsharp
function ReversedOpLECA (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)) : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj + Ctl)
```


## <a name="input"></a>Indata

### <a name="op--littleendian--unit--is-adj--ctl"></a>OP: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  rejusts + CTL

Åtgärden vars indatatyper ska ångras.



## <a name="output--bigendian--unit--is-adj--ctl"></a>Utdata: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  rejusts + CTL

En ny åtgärd som accepterar indatatypen som en big-endian-registrering.

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. aritmetiska. ApplyReversedOpLECA](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA)
- [Microsoft. Quantum. aritmetiska. ReversedOpLE](xref:Microsoft.Quantum.Arithmetic.ReversedOpLE)
- [Microsoft. Quantum. aritmetiska. ReversedOpLEA](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEA)
- [Microsoft. Quantum. aritmetiska. ReversedOpLEC](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEC)