---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder
title: ApplyPermutationUsingDecompositionWithVariableOrder-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingDecompositionWithVariableOrder
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.
ms.openlocfilehash: a5ca9b366f7ff477070e21fea047ff04b425439c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203441"
---
# <a name="applypermutationusingdecompositionwithvariableorder-operation"></a>ApplyPermutationUsingDecompositionWithVariableOrder-åtgärd

Namnrymd: [Microsoft. Quantum. syntes](xref:Microsoft.Quantum.Synthesis)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Permutes amplituderna i ett Quantum-tillstånd med en permutation med hjälp av nedbrytnings syntes.

```qsharp
operation ApplyPermutationUsingDecompositionWithVariableOrder (perm : Int[], variableOrder : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Beskrivning

Den här åtgärden är en mer allmän version av @"microsoft.quantum.synthesis.applypermutationusingdecomposition" där variabeln kan anges. En annan variabel ordning ändrar insammansättnings ordningen och de sanningen-tabeller som används för de kontrollerade @"microsoft.quantum.intrinsic.x" grindarna.  Därför ändrar variabel ordningen antalet allmänna grindar som används för att realisera permutationen.

## <a name="input"></a>Indata

### <a name="perm--int"></a>behörighet: [int](xref:microsoft.quantum.lang-ref.int)[]

En permutation av $2 ^ n $ elementen börjar från 0.


### <a name="variableorder--int"></a>variableOrder: [int](xref:microsoft.quantum.lang-ref.int)[]

En permutation av $n $-element som börjar från 0.


### <a name="qubits--littleendian"></a>qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

En lista med $n $ qubits som permutationen tillämpas på.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Se även

- [Microsoft. Quantum. syntes. ApplyPermutationUsingDecomposition](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition)
- [Microsoft. Quantum. syntes. ApplyPermutationUsingTransformation](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation)