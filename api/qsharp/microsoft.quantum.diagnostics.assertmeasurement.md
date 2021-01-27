---
uid: Microsoft.Quantum.Diagnostics.AssertMeasurement
title: AssertMeasurement-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertMeasurement
qsharp.summary: Asserts that measuring the given qubits in the given Pauli basis will always have the given result.
ms.openlocfilehash: 8f5113f1d6b8e4f104af10ca330e244e95793418
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853508"
---
# <a name="assertmeasurement-operation"></a>AssertMeasurement-åtgärd

Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Förutsätter att mätningen av den aktuella qubits i den aktuella Pauli-basen alltid har det aktuella resultatet.

```qsharp
operation AssertMeasurement (bases : Pauli[], qubits : Qubit[], result : Result, msg : String) : Unit is Adj + Ctl
```


## <a name="input"></a>Indata

### <a name="bases--pauli"></a>Bases: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

En mätnings funktion som försäkrar sannolikheten för, uttryckt som en Pauli-operatör med flera qubit.


### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

En register som ska göra försäkran.


### <a name="result--__invalidresult__"></a>resultat: __ogiltigt <Result>__

Det förväntade resultatet av `Measure(bases, qubits)` .


### <a name="msg--string"></a>Msg: [sträng](xref:microsoft.quantum.lang-ref.string)

Ett meddelande som ska rapporteras om kontrollen Miss lyckas.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Kommentarer

Observera att det inte går att kontrol lera villkoret i intilliggande och kontrollerade versioner av den här åtgärden.

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Diagnostics. AssertMeasurementProbability](xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability)