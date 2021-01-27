---
uid: Microsoft.Quantum.Arithmetic.AssertMostSignificantBit
title: AssertMostSignificantBit-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertMostSignificantBit
qsharp.summary: Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.
ms.openlocfilehash: b0b52a4ba7492d68896669aeb0b6b550d2f27f64
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843428"
---
# <a name="assertmostsignificantbit-operation"></a>AssertMostSignificantBit-åtgärd

Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Förutsätter att den viktigaste qubit i ett qubit-register som representerar ett osignerat heltal är i ett visst tillstånd.

```qsharp
operation AssertMostSignificantBit (value : Result, number : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Indata

### <a name="value--__invalidresult__"></a>värde: __ogiltigt <Result>__

Värdet för den högsta biten som verifieras.


### <a name="number--littleendian"></a>nummer: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Osignerat heltal som den högsta biten är markerad med.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Kommentarer

Den kontrollerade versionen av den här åtgärden ignorerar kontroller.

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. inre. assert](xref:Microsoft.Quantum.Intrinsic.Assert)