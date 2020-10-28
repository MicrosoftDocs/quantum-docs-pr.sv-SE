---
uid: Microsoft.Quantum.Diagnostics.AssertPhase
title: AssertPhase-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertPhase
qsharp.summary: Asserts that the phase of an equal superposition state has the expected value.
ms.openlocfilehash: e042c03d2a72d9ce4816a8cdb56603e175b22807
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727321"
---
# <a name="assertphase-operation"></a>AssertPhase-åtgärd

Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paketfilerna [](https://nuget.org/packages/)


Förutsätter att fasen för ett Equal-positions läge har det förväntade värdet.

```qsharp
operation AssertPhase (expected : Double, qubit : Qubit, tolerance : Double) : Unit
```


## <a name="description"></a>Beskrivning

Den här åtgärden förutsätter att fasen $ \phi $ i ett Quantum-tillstånd som kan uttryckas som $ \frac{e ^ {i t}} {\sqrt {2} } (e ^ {i\phi} \ ket {0} + e ^ {-i\phi} \ ket {1} ) $ för vissa valfria verkliga $t $ har det förväntade värdet.

## <a name="input"></a>Indata

### <a name="expected--double"></a>förväntat: [dubbel](xref:microsoft.quantum.lang-ref.double)

Det förväntade värdet för $ \phi \in (-\pi, \pi] $.


### <a name="qubit--qubit"></a>qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit som lagrar det förväntade läget.


### <a name="tolerance--double"></a>tolerans: [dubbel](xref:microsoft.quantum.lang-ref.double)

Absolut tolerans för skillnaden mellan faktiskt och förväntat värde.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)

