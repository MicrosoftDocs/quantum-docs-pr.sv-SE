---
uid: Microsoft.Quantum.Arithmetic.MultiplySI
title: MultiplySI-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplySI
qsharp.summary: Multiply signed integer `xs` by signed integer `ys` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: 4e7f43f88654f10ece4f9c30c5bfde9a779b18ba
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222447"
---
# <a name="multiplysi-operation"></a>MultiplySI-åtgärd

Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. Quantum. numeric](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Multiplicera signerat heltal `xs` med signerat heltal `ys` och lagra resultatet i `result` , vilket måste vara noll först.

```qsharp
operation MultiplySI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, ys : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Microsoft.Quantum.Arithmetic.SignedLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Indata

### <a name="xs--signedlittleendian"></a>XS: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)

n-bitars multiplicand (SignedLittleEndian)


### <a name="ys--signedlittleendian"></a>gar: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)

n-bitars multiplikator (SignedLittleEndian)


### <a name="result--signedlittleendian"></a>resultat: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)

2N-bitars resultat (SignedLittleEndian) måste vara i tillstånd $ \ket {0} $ initialt.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)

