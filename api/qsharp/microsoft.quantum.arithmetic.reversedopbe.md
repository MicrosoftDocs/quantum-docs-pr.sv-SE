---
uid: Microsoft.Quantum.Arithmetic.ReversedOpBE
title: Funktionen ReversedOpBE
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpBE
qsharp.summary: Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.
ms.openlocfilehash: 3c39a90ed4b5df09b90d8b5020d8b824285b50eb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222328"
---
# <a name="reversedopbe-function"></a>Funktionen ReversedOpBE

Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Med en åtgärd som tar big-endian-indatamängd returnerar en ny åtgärd som tar lite-endian-indatamängd.

```qsharp
function ReversedOpBE (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit)) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit)
```


## <a name="input"></a>Indata

### <a name="op--bigendian--unit"></a>OP: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) 

Åtgärden vars indatatyper ska ångras.



## <a name="output--littleendian--unit"></a>Utdata: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) 

En ny åtgärd som accepterar indatatypen som ett litet endian-register.

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. aritmetiska. ApplyReversedOpBE](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBE)
- [Microsoft. Quantum. aritmetiska. ReversedOpBEA](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEA)
- [Microsoft. Quantum. aritmetiska. ReversedOpBEC](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEC)
- [Microsoft. Quantum. aritmetiska. ReversedOpBECA](xref:Microsoft.Quantum.Arithmetic.ReversedOpBECA)