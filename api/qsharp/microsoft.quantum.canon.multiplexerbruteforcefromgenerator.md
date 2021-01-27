---
uid: Microsoft.Quantum.Canon.MultiplexerBruteForceFromGenerator
title: Funktionen MultiplexerBruteForceFromGenerator
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexerBruteForceFromGenerator
qsharp.summary: >-
  Returns a multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.

  $U = \sum^{2^n-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: d3606ff4f45765fd3aaf1e6a3078288b214349d0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852559"
---
# <a name="multiplexerbruteforcefromgenerator-function"></a>Funktionen MultiplexerBruteForceFromGenerator

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Returnerar en multiplicering-kontrollerad enhetlig åtgärd $U $ som tillämpar en enhetlig $V _j $ när den styrs av n-qubit Number State $ \ket{j} $.

$U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j}\otimes V_j $.

```qsharp
function MultiplexerBruteForceFromGenerator (unitaryGenerator : (Int, (Int -> (Qubit[] => Unit is Adj + Ctl)))) : ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl)
```


## <a name="input"></a>Indata

### <a name="unitarygenerator--intint---qubit--unit--is-adj--ctl"></a>unitaryGenerator: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int) -> [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL)

En tupel där det första elementet `Int` är antalet unitaries $N $, och det andra elementet `(Int -> ('T => () is Adj + Ctl))` är en funktion som tar ett heltal $j $ i $ [0, N-1] $ och utvärderar den enhetliga åtgärden $V _J $.



## <a name="output--littleendianqubit--unit--is-adj--ctl"></a>Utdata: ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL

En multiplicering-kontrollerad enhetlig åtgärd $U $ som tillämpar unitaries som beskrivs i `unitaryGenerator` .

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Canon. MultiplexerBruteForceFromGenerator](xref:Microsoft.Quantum.Canon.MultiplexerBruteForceFromGenerator)