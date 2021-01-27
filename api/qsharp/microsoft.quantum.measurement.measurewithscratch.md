---
uid: Microsoft.Quantum.Measurement.MeasureWithScratch
title: MeasureWithScratch-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureWithScratch
qsharp.summary: Measures the given Pauli operator using an explicit scratch qubit to perform the measurement.
ms.openlocfilehash: 4173aa9daac08a3febdfcbf12dc236f797685436
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854664"
---
# <a name="measurewithscratch-operation"></a>MeasureWithScratch-åtgärd

Namnrymd: [Microsoft. Quantum. mått](xref:Microsoft.Quantum.Measurement)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Mäter den tilldelade Pauli-operatorn med hjälp av en explicit Scratch-qubit för att utföra mätningen.

```qsharp
operation MeasureWithScratch (pauli : Pauli[], target : Qubit[]) : Result
```


## <a name="input"></a>Indata

### <a name="pauli--pauli"></a>Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

En Pauli-operator med flera qubit anges som en matris med qubit Pauli-operatörer.


### <a name="target--qubit"></a>mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubit-register som ska mätas.



## <a name="output--__invalidresult__"></a>Utdata: __ogiltig <Result>__

Resultatet av att mäta den tilldelade Pauli-operatorn i `target` registret.