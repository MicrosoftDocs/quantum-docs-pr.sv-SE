---
uid: Microsoft.Quantum.Arithmetic.DivideI
title: Dela uppi-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: DivideI
qsharp.summary: Divides two quantum integers.
ms.openlocfilehash: 73c4e394ca38b8089b2990f8a8b6a3ee50f644d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846688"
---
# <a name="dividei-operation"></a>Dela uppi-åtgärd

Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. Quantum. numeric](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Dividerar två Quantum-heltal.

```qsharp
operation DivideI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

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