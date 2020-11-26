---
uid: Microsoft.Quantum.Arithmetic.MultiplyI
title: Multiplicerai-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyI
qsharp.summary: Multiply integer `xs` by integer `ys` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: 96922f0147788b37cc9bace5154288a722d4ba95
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222515"
---
# <a name="multiplyi-operation"></a>Multiplicerai-åtgärd

Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. Quantum. numeric](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Multiplicera Heltal `xs` med heltal `ys` och lagra resultatet i `result` , som först måste vara noll.

```qsharp
operation MultiplyI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Indata

### <a name="xs--littleendian"></a>XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n $-bit multiplicand (LittleEndian)


### <a name="ys--littleendian"></a>gar: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n $-bit multiplikator (LittleEndian)


### <a name="result--littleendian"></a>resultat: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$2N $-bit result (LittleEndian) måste ha statusen $ \ket {0} $ initialt.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Kommentarer

Använder en vanlig Shift-och-Lägg-metod för att implementera multiplikationen.
Den kontrollerade versionen har förbättrats genom att du kopierade $x _i $ till en Ancilla-qubit som är villkorlig på kontrollen qubits och sedan styr additionen av Ancilla qubit.