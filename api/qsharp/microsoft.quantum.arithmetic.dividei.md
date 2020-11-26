---
uid: Microsoft.Quantum.Arithmetic.DivideI
title: Dela uppi-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: DivideI
qsharp.summary: Divides two quantum integers.
ms.openlocfilehash: 4cff191e1f9d42659768b4059e477f1a07948ba1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223314"
---
# <a name="dividei-operation"></a>Dela uppi-åtgärd

Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. Quantum. numeric](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Dividerar två Quantum-heltal.

```qsharp
operation DivideI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Beskrivning

`xs` kommer att hålla resten `xs - floor(xs/ys) * ys` och `result` hållas kvar `floor(xs/ys)` .

## <a name="input"></a>Indata

### <a name="xs--littleendian"></a>XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n $-bitars utdelning ersätts av resten.


### <a name="ys--littleendian"></a>gar: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n $-bit divisor


### <a name="result--littleendian"></a>resultat: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n $-bit-resultatet måste vara i tillstånd $ \ket {0} $ initialt och kommer att ersättas av resultatet av heltals divisionen.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Kommentarer

Använder en standard metod för att Shift-och-subtrahera för att implementera divisionen.
Den kontrollerade versionen är specialiserad så att subtraktionen inte kräver ytterligare kontroller.