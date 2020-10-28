---
uid: Microsoft.Quantum.Arithmetic.AddFxP
title: AddFxP-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AddFxP
qsharp.summary: Adds two fixed-point numbers stored in quantum registers.
ms.openlocfilehash: cf1f1379b7e1c32aefb0fccb55f4d13c95c78d8f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731902"
---
# <a name="addfxp-operation"></a>AddFxP-åtgärd

Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)

Paketfilerna [](https://nuget.org/packages/)


Lägger till två värden för fasta punkter som lagras i Quantum-registren.

```qsharp
operation AddFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
```


## <a name="description"></a>Beskrivning

Med två register med fasta punkter i stat $ \ket{f_1} $ och $ \ket{f_2} $, utför åtgärden $ \ket{f_1} \ket{f_2} \mapsto \ket{f_1} \ket{f_1 + f_2} $.

## <a name="input"></a>Indata

### <a name="fp1--fixedpoint"></a>FP1: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Första fasta punkts nummer


### <a name="fp2--fixedpoint"></a>FP2: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Det andra fasta punkt numret kommer att uppdateras så att det innehåller summan av de två indatana.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Kommentarer

Den aktuella implementeringen kräver att två fasta nummer måste ha samma positions position i beräkningen från den minst signifikanta biten, d.v.s. $n _i $ och $p _i $ måste vara lika.