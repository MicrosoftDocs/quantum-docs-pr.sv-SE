---
uid: Microsoft.Quantum.Arithmetic.AddFxP
title: AddFxP-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AddFxP
qsharp.summary: Adds two fixed-point numbers stored in quantum registers.
ms.openlocfilehash: 60b7cad3d0bd8800e67830ca921f8e2d705b8f39
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843858"
---
# <a name="addfxp-operation"></a>AddFxP-åtgärd

Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. Quantum. numeric](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Lägger till två värden för fasta punkter som lagras i Quantum-registren.

```qsharp
operation AddFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

Med två register med fasta punkter i stat $ \ket{f_1} $ och $ \ket{f_2} $, utför åtgärden $ \ket{f_1} \ket{f_2} \mapsto \ket{f_1} \ket{f_1 + f_2} $.

## <a name="input"></a>Indata

### <a name="fp1--fixedpoint"></a>FP1: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Första fasta punkts nummer


### <a name="fp2--fixedpoint"></a>FP2: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Det andra fasta punkt numret kommer att uppdateras så att det innehåller summan av de två indatana.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Kommentarer

Den aktuella implementeringen kräver att två fasta nummer måste ha samma positions position i beräkningen från den minst signifikanta biten, d.v.s. $n _i $ och $p _i $ måste vara lika.