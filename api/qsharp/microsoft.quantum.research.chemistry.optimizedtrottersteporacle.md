---
uid: Microsoft.Quantum.Research.Chemistry.OptimizedTrotterStepOracle
title: Funktionen OptimizedTrotterStepOracle
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: OptimizedTrotterStepOracle
qsharp.summary: Returns optimized Trotter step operation and the parameters necessary to run it.
ms.openlocfilehash: f78d80f7ab71f4fc759d8045c9a134d7178aaa15
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726379"
---
# <a name="optimizedtrottersteporacle-function"></a>Funktionen OptimizedTrotterStepOracle

Namnrymd: [Microsoft. Quantum. Research. kemi](xref:Microsoft.Quantum.Research.Chemistry)

Paketfilerna [](https://nuget.org/packages/)


Returnerar optimerad Trotter steg-åtgärd och de parametrar som krävs för att köra den.

```qsharp
function OptimizedTrotterStepOracle (qSharpData : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData, trotterStepSize : Double, trotterOrder : Int) : (Int, (Double, (Qubit[] => Unit is Adj + Ctl)))
```


## <a name="input"></a>Indata

### <a name="qsharpdata--jordanwignerencodingdata"></a>qSharpData: [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)

Hamiltonian som beskrivs i `JordanWignerEncodingData` format.


### <a name="trotterstepsize--double"></a>trotterStepSize: [dubbel](xref:microsoft.quantum.lang-ref.double)

Steg storlek för Trotter Integrator.


### <a name="trotterorder--int"></a>trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)

Ordning för Trotter Integrator.



## <a name="output--intdoublequbit--unit-adj--ctl"></a>Utdata: ([int](xref:microsoft.quantum.lang-ref.int), ([Double](xref:microsoft.quantum.lang-ref.double),[qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhets](xref:microsoft.quantum.lang-ref.unit) justering + CTL))

En tupel där: `Int` är antalet allokerade qubits, `Double` är `1.0/trotterStepSize` och åtgärden är Trotter-steget.