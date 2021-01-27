---
uid: Microsoft.Quantum.Arithmetic.IncrementByInteger
title: IncrementByInteger-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementByInteger
qsharp.summary: Increments an unsigned quantum register by a classical integer, using phase rotations.
ms.openlocfilehash: 9c7ff6947964a4dbe07106d1def9be46f631f5cc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843160"
---
# <a name="incrementbyinteger-operation"></a>IncrementByInteger-åtgärd

Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Ökar en osignerad Quantum-registrering med ett klassiskt heltal med hjälp av fas rotationer.

```qsharp
operation IncrementByInteger (increment : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

Anta att `target` koda ett osignerat heltal $x $ i en lite-endian-kodning och att det `increment` motsvarar $a $.
Den här åtgärden implementerar sedan den enhetliga $ \ket{x} \mapsto \ket{x + a} $, där additionen utförs med modulo $2 ^ n $, där $n = \texttt{Length (Target!)} $.

## <a name="input"></a>Indata

### <a name="increment--int"></a>ökning: [int](xref:microsoft.quantum.lang-ref.int)

Det heltal som `target` ökar med.


### <a name="target--littleendian"></a>mål: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Ett Quantum-register som kodar ett osignerat heltal med lite-endian-kodning.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)

