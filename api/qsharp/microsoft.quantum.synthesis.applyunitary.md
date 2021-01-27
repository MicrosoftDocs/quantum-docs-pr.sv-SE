---
uid: Microsoft.Quantum.Synthesis.ApplyUnitary
title: ApplyUnitary-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyUnitary
qsharp.summary: >-
  Applies gate defined by 2^n x 2^n unitary matrix.

  Fails if matrix is not unitary, or has wrong size.
ms.openlocfilehash: 58215d3b05b8c6974e979d21a13869f27b436310
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98859264"
---
# <a name="applyunitary-operation"></a>ApplyUnitary-åtgärd

Namnrymd: [Microsoft. Quantum. syntes](xref:Microsoft.Quantum.Synthesis)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Tillämpar den grind som definieras av 2 ^ n x 2 ^ n, enhetlig matris.

Miss lyckas om matrisen inte är enhetlig eller har fel storlek.

```qsharp
operation ApplyUnitary (unitary : Microsoft.Quantum.Math.Complex[][], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Indata

### <a name="unitary--complex"></a>enhetligt: [komplex](xref:Microsoft.Quantum.Math.Complex)[] []

2 ^ n x 2 ^ n en enhetlig matris som beskriver åtgärden.
Om matrisen inte är enhetlig eller inte av lämplig storlek, utlöses ett undantag.


### <a name="qubits--littleendian"></a>qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Qubits som använder åtgärden-registrera för längd n.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)

