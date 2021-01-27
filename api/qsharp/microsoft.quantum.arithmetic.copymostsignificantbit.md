---
uid: Microsoft.Quantum.Arithmetic.CopyMostSignificantBit
title: CopyMostSignificantBit-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CopyMostSignificantBit
qsharp.summary: Copies the most significant bit of a qubit register `from` representing an unsigned integer into the qubit `target`.
ms.openlocfilehash: 609e937a03bebf45aa9398225bd1b7e2b717807a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843274"
---
# <a name="copymostsignificantbit-operation"></a>CopyMostSignificantBit-åtgärd

Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Kopierar den mest signifikanta biten i ett qubit-register `from` som representerar ett osignerat heltal till qubit `target` .

```qsharp
operation CopyMostSignificantBit (from : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit is Adj
```


## <a name="input"></a>Indata

### <a name="from--littleendian"></a>från: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Det osignerade heltalet som den högsta biten kopieras från.
heltalet är kodat i litet endian-format.


### <a name="target--qubit"></a>mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit som den högsta biten kopieras till. Bit kodningen används i beräknings basen.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Se även

- [Microsoft. Quantum. aritmetiska. LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)