---
uid: Microsoft.Quantum.Synthesis.FastHadamardTransformed
title: Funktionen FastHadamardTransformed
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: FastHadamardTransformed
qsharp.summary: Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method
ms.openlocfilehash: be54413ef2d3fdaf7ddc726bc0906adb4ec382ff
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855455"
---
# <a name="fasthadamardtransformed-function"></a>Funktionen FastHadamardTransformed

Namnrymd: [Microsoft. Quantum. syntes](xref:Microsoft.Quantum.Synthesis)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Beräknar Hadamard-transformering av en boolesk funktion i {-1,1} encoding med Yates-metoden

```qsharp
function FastHadamardTransformed (func : Int[]) : Int[]
```


## <a name="input"></a>Indata

### <a name="func--int"></a>FUNC: [int](xref:microsoft.quantum.lang-ref.int)[]

Sanningen-tabell i {-1,1} kodning



## <a name="output--int"></a>Utdata: [int](xref:microsoft.quantum.lang-ref.int)[]

Spectral-koefficienter för funktionen

## <a name="example"></a>Exempel

```qsharp
FastHadamardTransformed([1, 1, 1, -1]); // [2, 2, 2, -2]
```