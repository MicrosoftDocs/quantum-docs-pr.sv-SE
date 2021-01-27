---
uid: Microsoft.Quantum.Measurement.MeasurePaulis
title: MeasurePaulis-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasurePaulis
qsharp.summary: Given an array of multi-qubit Pauli operators, measures each using a specified measurement gadget, then returns the array of results.
ms.openlocfilehash: 1bc14ec8e7c608d1195a03a354c71e870594f86d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853773"
---
# <a name="measurepaulis-operation"></a>MeasurePaulis-åtgärd

Namnrymd: [Microsoft. Quantum. mått](xref:Microsoft.Quantum.Measurement)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Med en matris med qubit Pauli-operatörer, mäter varje användning av en angiven mått-gadget och returnerar sedan mat ris resultatet.

```qsharp
operation MeasurePaulis (paulis : Pauli[][], target : Qubit[], gadget : ((Pauli[], Qubit[]) => Result)) : Result[]
```


## <a name="input"></a>Indata

### <a name="paulis--pauli"></a>Paulis: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []

Matris med multi-qubit Pauli-operatörer att mäta.


### <a name="target--qubit"></a>mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registrera dig för att mäta de tilldelade operatörerna.


### <a name="gadget--pauliqubit--__invalidresult__"></a>gadget: ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __ogiltig <Result>__ 

Åtgärd som utför mätningen av en specifik multi-qubit-operator.



## <a name="output--__invalidresult__"></a>Utdata: __ogiltigt <Result>__[]

Matrisen med resultat som erhålls från mätning av varje element i `paulis` på `target` .