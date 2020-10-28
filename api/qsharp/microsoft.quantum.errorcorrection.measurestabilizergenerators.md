---
uid: Microsoft.Quantum.ErrorCorrection.MeasureStabilizerGenerators
title: MeasureStabilizerGenerators-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: MeasureStabilizerGenerators
qsharp.summary: Measures the given set of generators of a stabilizer group.
ms.openlocfilehash: a3f48ff24a39d13a57f7a144e21d4e41bb8a8b49
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727027"
---
# <a name="measurestabilizergenerators-operation"></a>MeasureStabilizerGenerators-åtgärd

Namnrymd: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Paketfilerna [](https://nuget.org/packages/)


Mäter den angivna uppsättningen generatorer för en stabiliserings grupp.

```qsharp
operation MeasureStabilizerGenerators (stabilizerGroup : Pauli[][], logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister, gadget : ((Pauli[], Qubit[]) => Result)) : Microsoft.Quantum.ErrorCorrection.Syndrome
```


## <a name="input"></a>Indata

### <a name="stabilizergroup--pauli"></a>stabilizerGroup: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []

En matris med multiqubit Pauli-operatörer.
Är till exempel `stabilizerGroup[0]` en lista med enqubite Pauli-matriser, som är en stabiliserings Generator.


### <a name="logicalregister--logicalregister"></a>logicalRegister: [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)

En matris med qubits där stabiliserings koden definieras.


### <a name="gadget--pauliqubit--__invalidresult__"></a>gadget: ( [Pauli](xref:microsoft.quantum.lang-ref.pauli)[], [qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __ogiltig <Result>__ 

En åtgärd som anger hur en multiqubit Pauli-operator ska mätas.



## <a name="output--syndrome"></a>Utdata: [Syndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)

Resultatet av mätningar.

## <a name="remarks"></a>Kommentarer

Detta kontrollerar inte om den angivna uppsättningen generatorer förfaller.
Om de inte återkommer kan resultatet av måtten vara godtyckligt.