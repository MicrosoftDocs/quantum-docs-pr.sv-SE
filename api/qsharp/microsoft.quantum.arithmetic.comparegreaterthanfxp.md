---
uid: Microsoft.Quantum.Arithmetic.CompareGreaterThanFxP
title: CompareGreaterThanFxP-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGreaterThanFxP
qsharp.summary: Compares two fixed-point numbers stored in quantum registers, and controls a flip on the result.
ms.openlocfilehash: f49c713c8a1e8a6451f2c54fa59a72f00bfbb4c4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843312"
---
# <a name="comparegreaterthanfxp-operation"></a>CompareGreaterThanFxP-åtgärd

Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. Quantum. numeric](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Jämför två tal med fasta punkter som lagras i Quantum-registren och styr en vändning på resultatet.

```qsharp
operation CompareGreaterThanFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint, result : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>Indata

### <a name="fp1--fixedpoint"></a>FP1: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Första fasta punkts nummer som ska jämföras.


### <a name="fp2--fixedpoint"></a>FP2: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Andra fasta punkts nummer som ska jämföras.


### <a name="result--qubit"></a>resultat: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Resultatet av jämförelsen. Kommer att vändas om `fp1 > fp2` .



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Kommentarer

Den aktuella implementeringen kräver att de två fasta punkternas nummer har samma punkt position och samma antal qubits.