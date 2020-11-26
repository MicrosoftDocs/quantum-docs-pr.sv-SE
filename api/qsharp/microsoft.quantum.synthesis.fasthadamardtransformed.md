---
uid: Microsoft.Quantum.Synthesis.FastHadamardTransformed
title: Funktionen FastHadamardTransformed
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: FastHadamardTransformed
qsharp.summary: Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method
ms.openlocfilehash: 3e48701f22ddf154721355866e15a85fca0bc7df
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203101"
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