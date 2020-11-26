---
uid: Microsoft.Quantum.Diagnostics.AssertMeasurementProbability
title: AssertMeasurementProbability-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertMeasurementProbability
qsharp.summary: Asserts that measuring the given qubits in the given Pauli basis will have the given result with the given probability, within some tolerance.
ms.openlocfilehash: 032b9224ad728f0637596668c2928a889deeba55
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202370"
---
# <a name="assertmeasurementprobability-operation"></a>AssertMeasurementProbability-åtgärd

Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Förutsätter att mätningen av den aktuella qubits i den aktuella Pauli-grunden har det resultat som har givit den sannolikheten, inom viss tolerans.

```qsharp
operation AssertMeasurementProbability (bases : Pauli[], qubits : Qubit[], result : Result, prob : Double, msg : String, tol : Double) : Unit is Adj + Ctl
```


## <a name="input"></a>Indata

### <a name="bases--pauli"></a>Bases: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

En mätnings funktion som försäkrar sannolikheten för, uttryckt som en Pauli-operatör med flera qubit.


### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

En register som ska göra försäkran.


### <a name="result--__invalidresult__"></a>resultat: __ogiltigt <Result>__

Ett förväntat resultat av `Measure(bases, qubits)` .


### <a name="prob--double"></a>sannolikhet: [dubbel](xref:microsoft.quantum.lang-ref.double)

Sannolikheten med vilken det aktuella resultatet förväntas.


### <a name="msg--string"></a>Msg: [sträng](xref:microsoft.quantum.lang-ref.string)

Ett meddelande som ska rapporteras om kontrollen Miss lyckas.


### <a name="tol--double"></a>TOL: [dubbel](xref:microsoft.quantum.lang-ref.double)





## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Kommentarer

Observera att det inte går att kontrol lera villkoret i intilliggande och kontrollerade versioner av den här åtgärden.

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Diagnostics. AssertMeasurement](xref:Microsoft.Quantum.Diagnostics.AssertMeasurement)