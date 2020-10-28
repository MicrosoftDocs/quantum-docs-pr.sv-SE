---
uid: Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTable
title: ApplyXControlledOnTruthTable-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyXControlledOnTruthTable
qsharp.summary: Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.
ms.openlocfilehash: 73d63936f02a52dfbbad7b8575110177a9e4463d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733931"
---
# <a name="applyxcontrolledontruthtable-operation"></a>ApplyXControlledOnTruthTable-åtgärd

Namnrymd: [Microsoft. Quantum. syntes](xref:Microsoft.Quantum.Synthesis)

Paketfilerna [](https://nuget.org/packages/)


Tillämpar @"microsoft.quantum.intrinsic.x" åtgärden på `target` , om den booleska funktionen `func` utvärderas som sant för den klassiska den klassiska tilldelningen i `controlRegister` .

```qsharp
operation ApplyXControlledOnTruthTable (func : BigInt, controlRegister : Qubit[], target : Qubit) : Unit
```


## <a name="description"></a>Beskrivning

Åtgärden implementerar den enhetliga åtgärden \begin{align} U\ket {x} \ ket {y} = \ket{x}\ket{y \oplus f (x)} \end{align} där $x $ och $y $ representerar respektive `controlRegister` `target` .

Den booleska funktionen $f $ representeras som en sanningen-tabell i termer av ett stort heltal.
Till exempel representeras majoriteten-funktionen på tre indata av bitstring `11101000` , där den mest signifikanta biten `1` motsvarar tilldelningen `(1, 1, 1)` och den minst signifikanta biten `0` motsvarar den angivna tilldelningen `(0, 0, 0)` .
Den kan representeras av det stora heltalet `0xE8L` i hexadecimal notation eller som `232L` Decimal form.  `L`Suffixet anger att konstanten är av typen `BigInt` .
Det går även att hitta mer information om den här åter givningen i [sanningen-tabellerna Kata](https://github.com/microsoft/QuantumKatas/tree/main/TruthTables).

Implementeringen använder @"microsoft.quantum.intrinsic.cnot" och @"microsoft.quantum.intrinsic.r1" portar.

## <a name="input"></a>Indata

### <a name="func--bigint"></a>FUNC: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Boolesk sanningen tabell representeras som ett stort heltal


### <a name="controlregister--qubit"></a>controlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Register över kontroll qubits


### <a name="target--qubit"></a>mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Mål qubit



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Referenser

- [*N. Schuch* , *J. Siewert* , PRL 91, no. 027902, 2003, arXiv: Quant-pH/0303063](https://arxiv.org/abs/quant-ph/0303063)
- [*Mathias Soeken* , *Martin Roetteler* , arXiv: 2005.12310](https://arxiv.org/abs/2005.12310)

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. syntes. ApplyXControlledOnTruthTableWithCleanTarget](xref:Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTableWithCleanTarget)