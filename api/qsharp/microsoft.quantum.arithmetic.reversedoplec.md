---
uid: Microsoft.Quantum.Arithmetic.ReversedOpLEC
title: Funktionen ReversedOpLEC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpLEC
qsharp.summary: Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.
ms.openlocfilehash: 8c91391691b23786df02ae2a35264b578dccad41
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222090"
---
# <a name="reversedoplec-function"></a>Funktionen ReversedOpLEC

Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Med en åtgärd som tar lite-endian-indatamängd returnerar en ny åtgärd som tar en big-endian-indatamängd.

```qsharp
function ReversedOpLEC (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Ctl)) : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Ctl)
```


## <a name="input"></a>Indata

### <a name="op--littleendian--unit--is-ctl"></a>OP: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  är CTL

Åtgärden vars indatatyper ska ångras.



## <a name="output--bigendian--unit--is-ctl"></a>Utdata: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  är CTL

En ny åtgärd som accepterar indatatypen som en big-endian-registrering.

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. aritmetiska. ApplyReversedOpLEC](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC)
- [Microsoft. Quantum. aritmetiska. ReversedOpLE](xref:Microsoft.Quantum.Arithmetic.ReversedOpLE)
- [Microsoft. Quantum. aritmetiska. ReversedOpLEA](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEA)
- [Microsoft. Quantum. aritmetiska. ReversedOpLECA](xref:Microsoft.Quantum.Arithmetic.ReversedOpLECA)