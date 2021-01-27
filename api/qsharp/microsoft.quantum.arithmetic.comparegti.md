---
uid: Microsoft.Quantum.Arithmetic.CompareGTI
title: CompareGTI-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGTI
qsharp.summary: 'Wrapper for integer comparison: `result = x > y`.'
ms.openlocfilehash: e9c245fb7c0cf3a6b1b98eb01cd582c325917602
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843303"
---
# <a name="comparegti-operation"></a>CompareGTI-åtgärd

Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. Quantum. numeric](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Wrapper för heltals jämförelse: `result = x > y` .

```qsharp
operation CompareGTI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>Indata

### <a name="xs--littleendian"></a>XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Första $n $-bit Number


### <a name="ys--littleendian"></a>gar: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Andra $n $-bit Number


### <a name="result--qubit"></a>resultat: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Kommer att vändas om $x > y $



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)

