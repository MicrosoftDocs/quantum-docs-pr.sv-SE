---
uid: Microsoft.Quantum.Arithmetic.MultiplyFxP
title: MultiplyFxP-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyFxP
qsharp.summary: Multiplies two fixed-point numbers in quantum registers.
ms.openlocfilehash: 776ccb7a9e1ba1a34b28da6e1cf3a0aafe9da76b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843055"
---
# <a name="multiplyfxp-operation"></a>MultiplyFxP-åtgärd

Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. Quantum. numeric](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Multiplicerar två fasta nummer i Quantum-registren.

```qsharp
operation MultiplyFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a>Indata

### <a name="fp1--fixedpoint"></a>FP1: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Första fasta punkts nummer.


### <a name="fp2--fixedpoint"></a>FP2: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Andra fasta punkt nummer.


### <a name="result--fixedpoint"></a>resultat: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Resulterande fast punkt nummer måste vara i tillstånd $ \ket {0} $ initialt.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Kommentarer

För den aktuella implementeringen krävs tre fasta punkt nummer för samma punkt position och samma antal qubits.