---
uid: Microsoft.Quantum.Arithmetic.SquareSI
title: Kvadratmetoden-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareSI
qsharp.summary: Square signed integer `xs` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: 161b45766c6f4d500d25def24aa509ee7fdc8628
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842931"
---
# <a name="squaresi-operation"></a>Kvadratmetoden-åtgärd

Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. Quantum. numeric](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Fyrkantigt signerat heltal `xs` och lagra resultatet i `result` , vilket måste vara noll först.

```qsharp
operation SquareSI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Microsoft.Quantum.Arithmetic.SignedLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Indata

### <a name="xs--signedlittleendian"></a>XS: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)

n-bitars heltal till kvadrat (SignedLittleEndian)


### <a name="result--signedlittleendian"></a>resultat: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)

2N-bitars resultat (SignedLittleEndian) måste vara i tillstånd $ \ket {0} $ initialt.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Kommentarer

Implementeringen är beroende av IntegerSquare.