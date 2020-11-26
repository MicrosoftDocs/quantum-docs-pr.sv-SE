---
uid: Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTableWithCleanTarget
title: ApplyXControlledOnTruthTableWithCleanTarget-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyXControlledOnTruthTableWithCleanTarget
qsharp.summary: Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.
ms.openlocfilehash: 904ff7e2e7e81ee966846af120e9427f4e92301c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203271"
---
# <a name="applyxcontrolledontruthtablewithcleantarget-operation"></a>ApplyXControlledOnTruthTableWithCleanTarget-åtgärd

Namnrymd: [Microsoft. Quantum. syntes](xref:Microsoft.Quantum.Synthesis)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Tillämpar @"microsoft.quantum.intrinsic.x" åtgärden på `target` , om den booleska funktionen `func` utvärderas som sant för den klassiska den klassiska tilldelningen i `controlRegister` .

```qsharp
operation ApplyXControlledOnTruthTableWithCleanTarget (func : BigInt, controlRegister : Qubit[], target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>Beskrivning

Den här åtgärden implementerar ett specialfall av @"microsoft.quantum.synthesis.applyxcontrolledontruthtable" , där mål-qubit är känt i $ \ket {0} $-tillstånd.

Implementeringen använder @"microsoft.quantum.intrinsic.cnot" och @"microsoft.quantum.intrinsic.r1" portar.  Implementeringen av den angränsande åtgärden är optimerad och använder mätnings-baserad avberäkning.

## <a name="input"></a>Indata

### <a name="func--bigint"></a>FUNC: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Boolesk sanningen tabell representeras som ett stort heltal


### <a name="controlregister--qubit"></a>controlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Register över kontroll qubits


### <a name="target--qubit"></a>mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Mål-qubit (måste vara i $ \ket {0} $ State)



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Se även

- [Microsoft. Quantum. syntes. ApplyXControlledOnTruthTable](xref:Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTable)