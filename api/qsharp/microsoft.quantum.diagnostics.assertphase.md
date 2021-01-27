---
uid: Microsoft.Quantum.Diagnostics.AssertPhase
title: AssertPhase-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertPhase
qsharp.summary: Asserts that the phase of an equal superposition state has the expected value.
ms.openlocfilehash: 59fa0f2f68b4de271b972aef776ee5097fd5c201
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830081"
---
# <a name="assertphase-operation"></a>AssertPhase-åtgärd

Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Förutsätter att fasen för ett Equal-positions läge har det förväntade värdet.

```qsharp
operation AssertPhase (expected : Double, qubit : Qubit, tolerance : Double) : Unit
```


## <a name="description"></a>Description

Den här åtgärden förutsätter att fasen $ \phi $ i ett Quantum-tillstånd som kan uttryckas som $ \frac{e ^ {i t}} {\sqrt {2} } (e ^ {i\phi} \ ket {0} + e ^ {-i\phi} \ ket {1} ) $ för vissa valfria verkliga $t $ har det förväntade värdet.

## <a name="input"></a>Indata

### <a name="expected--double"></a>förväntat: [dubbel](xref:microsoft.quantum.lang-ref.double)

Det förväntade värdet för $ \phi \in (-\pi, \pi] $.


### <a name="qubit--qubit"></a>qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit som lagrar det förväntade läget.


### <a name="tolerance--double"></a>tolerans: [dubbel](xref:microsoft.quantum.lang-ref.double)

Absolut tolerans för skillnaden mellan faktiskt och förväntat värde.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>Exempel

Följande kontroll lyckas: `qubit` är i läget $ \ket{\psi} = e ^ {i 0,5} \ sqrt {1/2} \ ket {0} + e ^ {i 0,5} \ sqrt {1/2} \ ket {1} $;

- `AssertPhase(0.0,qubit,10e-10);`

`qubit` är i tillstånd $ \ket{\psi} = e ^ {i 0,5} \ sqrt {1/2} \ ket {0} + e ^ {-i 0,5} \ sqrt {1/2} \ ket {1} $;

- `AssertPhase(0.5,qubit,10e-10);`

`qubit` är i tillstånd $ \ket{\psi} = e ^ {-i 2,2} \ sqrt {1/2} \ ket {0} + e ^ {i 0,2} \ sqrt {1/2} \ ket {1} $;

- `AssertPhase(-1.2,qubit,10e-10);`