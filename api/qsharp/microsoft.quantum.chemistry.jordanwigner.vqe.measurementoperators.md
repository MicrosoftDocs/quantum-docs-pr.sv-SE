---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.MeasurementOperators
title: Funktionen MeasurementOperators
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: MeasurementOperators
qsharp.summary: Computes all the measurement operators required to compute the expectation of a Jordan-Wigner term.
ms.openlocfilehash: 204ae621b77559a894f0bce14e494824d58e4ad6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98835399"
---
# <a name="measurementoperators-function"></a>Funktionen MeasurementOperators

Namnrymd: [Microsoft. Quantum. kemi. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)

Paket: [Microsoft. Quantum. kemi](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Beräknar alla mått operatörer som krävs för att beräkna förväntat en Jordan-Wigners period.

```qsharp
function MeasurementOperators (nQubits : Int, indices : Int[], termType : Int) : Pauli[][]
```


## <a name="input"></a>Indata

### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

Antalet qubits som krävs för att simulera molekyl systemet.


### <a name="indices--int"></a>index: [int](xref:microsoft.quantum.lang-ref.int)[]

En matris som innehåller index för qubit varje Pauli-operator tillämpas på.


### <a name="termtype--int"></a>termType: [int](xref:microsoft.quantum.lang-ref.int)

Jordan-Wigner termns typ.



## <a name="output--pauli"></a>Utdata: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []

En matris med mått operatorer (var och en är en matris med Pauli).