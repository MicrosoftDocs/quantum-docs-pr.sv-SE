---
uid: Microsoft.Quantum.Arithmetic.AssertProbInt
title: AssertProbInt-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertProbInt
qsharp.summary: Asserts that the probability of a specific state of a quantum register has the expected value.
ms.openlocfilehash: 85ff04bbad9dc2ed0f803db65508fdfbb0d22c56
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843408"
---
# <a name="assertprobint-operation"></a>AssertProbInt-åtgärd

Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Förutsätter att sannolikheten för ett enskilt tillstånd för ett Quantum-register har det förväntade värdet.

```qsharp
operation AssertProbInt (stateIndex : Int, expected : Double, qubits : Microsoft.Quantum.Arithmetic.LittleEndian, tolerance : Double) : Unit
```


## <a name="description"></a>Description

Med en $n $-qubit Quantum State $ \ket{\psi} = \sum ^ {2 ^ n-1} _ {j = 0} \ alpha_j \ket{j} $, förutsätter att sannolikheten $ | \ alpha_j | ^ 2 $ för tillstånd $ \ket{j} $ som har indexerats av $j $ har det förväntade värdet.

## <a name="input"></a>Indata

### <a name="stateindex--int"></a>stateIndex: [int](xref:microsoft.quantum.lang-ref.int)

Index $j $ för tillstånd $ \ket{j} $ som representeras av ett `LittleEndian` register.


### <a name="expected--double"></a>förväntat: [dubbel](xref:microsoft.quantum.lang-ref.double)

Det förväntade värdet för $ | \ alpha_j | ^ 2 $.


### <a name="qubits--littleendian"></a>qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Qubit-register som lagrar $ \ket{\psi} $ i litet endian-format.


### <a name="tolerance--double"></a>tolerans: [dubbel](xref:microsoft.quantum.lang-ref.double)

Absolut tolerans för skillnaden mellan faktiskt och förväntat värde.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>Exempel

Anta att `qubits` registret kodar ett 3-qubit Quantum-tillstånd $ \ket{\psi} = \ sqrt {1/8} \ ket {0} + \ sqrt {7/8} \ ket {6} $ i litet endian-format.
Det innebär att antalet tillstånd $ \ket {0} \equiv\ket {0} \ket {0} \ket {0} $ och $ \ket \equiv\ket {6} \ket \ket {0} {1} {1} $. Följande kontroller lyckades:

```qsharp
AssertProbInt(0, 0.125, qubits, 10e-10);
AssertProbInt(6, 0.875, qubits, 10e-10);
```