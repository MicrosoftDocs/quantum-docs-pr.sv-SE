---
uid: Microsoft.Quantum.Chemistry.JordanWigner._JordanWignerClusterOperatorImpl
title: _JordanWignerClusterOperatorImpl åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _JordanWignerClusterOperatorImpl
qsharp.summary: >-
  Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.

  See [Dynamical Generator Modeling](../libraries/data-structures#dynamical-generator-modeling) for more details.
ms.openlocfilehash: d8301934beedf715c533e00f32a50e76c11875f5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851624"
---
# <a name="_jordanwignerclusteroperatorimpl-operation"></a>_JordanWignerClusterOperatorImpl åtgärd

Namnrymd: [Microsoft. Quantum. kemi. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

Paket: [Microsoft. Quantum. kemi](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Representerar en dynamisk generator som en uppsättning simulerade grindar och en expansion i JordanWigner-basen.

Mer information finns i [modeller för dynamisk Generator](../libraries/data-structures#dynamical-generator-modeling) .

```qsharp
operation _JordanWignerClusterOperatorImpl (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Indata

### <a name="generatorindex--generatorindex"></a>generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

Ett Generator index som återges som en enhetlig utveckling i JordanWigner.


### <a name="stepsize--double"></a>stepSize: [dubbel](xref:microsoft.quantum.lang-ref.double)

Dummy-variabel som matchar signaturen för simulerings algoritmer.


### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registrera dig efter tids utvecklings operatören.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)

