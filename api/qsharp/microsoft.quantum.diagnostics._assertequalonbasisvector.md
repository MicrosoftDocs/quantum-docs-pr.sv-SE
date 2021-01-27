---
uid: Microsoft.Quantum.Diagnostics._assertEqualOnBasisVector
title: _assertEqualOnBasisVector åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _assertEqualOnBasisVector
qsharp.summary: Checks if the result of applying two operations `givenU` and `expectedU` to a basis state is the same. The basis state is described by `basis` parameter. See <xref:microsoft.quantum.extensions.fliptobasis> function for more details on this description.
ms.openlocfilehash: 041fecfa27ae5bd17fa8fdc89ce964f985f6124b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853585"
---
# <a name="_assertequalonbasisvector-operation"></a>_assertEqualOnBasisVector åtgärd

Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Kontrollerar om resultatet av att tillämpa två åtgärder `givenU` och `expectedU` till gång till ett delstats tillstånd är detsamma. Bas status beskrivs av `basis` parameter.
Se <xref:microsoft.quantum.extensions.fliptobasis> funktion för mer information om den här beskrivningen.

```qsharp
operation _assertEqualOnBasisVector (basis : Int[], givenU : (Qubit[] => Unit), expectedU : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a>Indata

### <a name="basis--int"></a>bas: [int](xref:microsoft.quantum.lang-ref.int)[]

Det grundläggande tillstånd som anges av ett ID för en enskild qubit-basis (0 <= ID <= 3) för var och en av $n $ qubits.


### <a name="givenu--qubit--unit"></a>givenU: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhet](xref:microsoft.quantum.lang-ref.unit) 

Åtgärden på $n $ qubits ska kontrol leras.


### <a name="expectedu--qubit--unit--is-adj"></a>expectedU: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just

Referens åtgärd på $n $ qubits som givenU ska jämföras med.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)

