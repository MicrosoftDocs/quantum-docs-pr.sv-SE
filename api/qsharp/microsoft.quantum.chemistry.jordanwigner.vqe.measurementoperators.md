---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.MeasurementOperators
title: Funktionen MeasurementOperators
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: MeasurementOperators
qsharp.summary: Computes all the measurement operators required to compute the expectation of a Jordan-Wigner term.
ms.openlocfilehash: 24d752c4f198764b6e7c6ea6c49669c020c1a502
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727633"
---
# <a name="measurementoperators-function"></a>Funktionen MeasurementOperators

Namnrymd: [Microsoft. Quantum. kemi. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)

Paketfilerna [](https://nuget.org/packages/)


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