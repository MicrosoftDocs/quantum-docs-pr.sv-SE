---
uid: Microsoft.Quantum.Arithmetic.ReversedOpBECA
title: Funktionen ReversedOpBECA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpBECA
qsharp.summary: Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.
ms.openlocfilehash: da21b09110400ad4ee862f662d45e166a49e7bd8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222209"
---
# <a name="reversedopbeca-function"></a>Funktionen ReversedOpBECA

Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Med en åtgärd som tar big-endian-indatamängd returnerar en ny åtgärd som tar lite-endian-indatamängd.

```qsharp
function ReversedOpBECA (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj + Ctl)) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a>Indata

### <a name="op--bigendian--unit--is-adj--ctl"></a>OP: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  rejusts + CTL

Åtgärden vars indatatyper ska ångras.



## <a name="output--littleendian--unit--is-adj--ctl"></a>Utdata: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  rejusts + CTL

En ny åtgärd som accepterar indatatypen som ett litet endian-register.

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. aritmetiska. ApplyReversedOpBECA](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA)
- [Microsoft. Quantum. aritmetiska. ReversedOpBE](xref:Microsoft.Quantum.Arithmetic.ReversedOpBE)
- [Microsoft. Quantum. aritmetiska. ReversedOpBEA](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEA)
- [Microsoft. Quantum. aritmetiska. ReversedOpBEC](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEC)