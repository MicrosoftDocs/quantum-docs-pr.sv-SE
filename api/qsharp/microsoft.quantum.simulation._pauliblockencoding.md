---
uid: Microsoft.Quantum.Simulation._PauliBlockEncoding
title: _PauliBlockEncoding funktion
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: _PauliBlockEncoding
qsharp.summary: >-
  Creates a block-encoding unitary for a Hamiltonian.

  The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.
ms.openlocfilehash: 6ad3e692f68ec2d405e19a7e467ef8fe33d449fc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225575"
---
# <a name="_pauliblockencoding-function"></a>_PauliBlockEncoding funktion

Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Skapar en typ av block kodning för en Hamiltonian.

Hamiltonian $H = \ sum_ {j} \ alpha_j P_j $ beskrivs av en summa av Pauli-termer $P _j $, var och en med verklig koefficient $ \ alpha_j $.

```qsharp
function _PauliBlockEncoding (generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem, statePrepUnitary : (Double[] -> (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)), multiplexer : ((Int, (Int -> (Qubit[] => Unit is Adj + Ctl))) -> ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl))) : (Double, Microsoft.Quantum.Simulation.BlockEncodingReflection)
```


## <a name="input"></a>Indata

### <a name="generatorsystem--generatorsystem"></a>generatorSystem: [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

En `GeneratorSystem` som beskriver $H $ som en summa av Pauli villkor


### <a name="stateprepunitary--double---littleendian--unit--is-adj--ctl"></a>statePrepUnitary: [Double](xref:microsoft.quantum.lang-ref.double)[]-> [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) - => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL

En enhetlig åtgärd $V $ som tillämpar den enhetliga $V _j $ som styrs av index $ \ket{j} $, med en funktion $f: j\rightarrow V_j $.


### <a name="multiplexer--intint---qubit--unit--is-adj--ctl---littleendianqubit--unit--is-adj--ctl"></a>multiplexor: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int) -> [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL)-> ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL





## <a name="output--doubleblockencodingreflection"></a>Utdata: ([dubbel](xref:microsoft.quantum.lang-ref.double),[BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection))

## <a name="first-parameter"></a>Första parametern

En-norm för koefficienter $ \alpha = \ sum_ {j} | \ alpha_j | $.

## <a name="second-parameter"></a>Andra parameter

En `BlockEncodingReflection` enhetlig $U $ Hamiltonian $U $. Eftersom den här lösningen uppfyller $U ^ 2 = I $, är det också en reflektion.

## <a name="remarks"></a>Kommentarer

Exempel åtgärder för att förbereda och avförbereda statusen $ \ sum_ {j} \sqrt{\ alpha_j/\alpha}\ket{j} $ och skapa en multiplicering-kontrollerad enhetlighet är <xref:microsoft.quantum.canon.statepreparationpositivecoefficients> och <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator> .