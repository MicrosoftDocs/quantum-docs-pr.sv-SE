---
uid: Microsoft.Quantum.Measurement.MeasurePaulis
title: MeasurePaulis-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasurePaulis
qsharp.summary: Given an array of multi-qubit Pauli operators, measures each using a specified measurement gadget, then returns the array of results.
ms.openlocfilehash: 4faaf78f24fa28ae5e4f701b80d9297c910b975e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194227"
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