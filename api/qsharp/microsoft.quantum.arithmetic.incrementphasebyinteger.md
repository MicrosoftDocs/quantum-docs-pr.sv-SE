---
uid: Microsoft.Quantum.Arithmetic.IncrementPhaseByInteger
title: IncrementPhaseByInteger-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementPhaseByInteger
qsharp.summary: Increments an unsigned quantum register by a classical integer, using phase rotations.
ms.openlocfilehash: cc7922b2940cb979394958d5eb4e9933144eb062
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843149"
---
# <a name="incrementphasebyinteger-operation"></a>IncrementPhaseByInteger-åtgärd

Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Ökar en osignerad Quantum-registrering med ett klassiskt heltal med hjälp av fas rotationer.

```qsharp
operation IncrementPhaseByInteger (increment : Int, target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

Anta att `target` koda ett osignerat heltal $x $ i en lite-endian-kodning och att det `increment` motsvarar $a $.
Den här åtgärden implementerar sedan den enhetliga $ \ket{x} \mapsto \ket{x + a} $, där additionen utförs med modulo $2 ^ n $, där $n = \texttt{Length (Target!)} $.

## <a name="input"></a>Indata

### <a name="increment--int"></a>ökning: [int](xref:microsoft.quantum.lang-ref.int)

Det heltal som `target` ökar med.


### <a name="target--phaselittleendian"></a>mål: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)

Ett Quantum-register som kodar ett osignerat heltal med lite endian-kodning i dubbel (QFT)-grunden.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Kommentarer

Observera att vi har förenklat kretsen eftersom ökningen är en klassisk konstant, inte ett Quantum-register.

Se figuren på [ sidan 6 i arXiv: Quant-pH/0008033v1 ](https://arxiv.org/pdf/quant-ph/0008033.pdf#page=6) för krets diagrammet och förklaringen.

## <a name="references"></a>Referenser

- [*Thomas G. Draper*, arXiv: Quant-pH/0008033](https://arxiv.org/pdf/quant-ph/0008033v1.pdf)

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. aritmetiska. IncrementByInteger](xref:Microsoft.Quantum.Arithmetic.IncrementByInteger)