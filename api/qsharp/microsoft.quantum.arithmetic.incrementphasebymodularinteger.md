---
uid: Microsoft.Quantum.Arithmetic.IncrementPhaseByModularInteger
title: IncrementPhaseByModularInteger-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementPhaseByModularInteger
qsharp.summary: Performs a modular increment of a qubit register by an integer constant.
ms.openlocfilehash: 6a39ce49dfa28c1f1cbe6b29e526144c3ac19e53
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222889"
---
# <a name="incrementphasebymodularinteger-operation"></a>IncrementPhaseByModularInteger-åtgärd

Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Utför en modulär ökning av ett qubit-register med en heltalskonstant.

```qsharp
operation IncrementPhaseByModularInteger (increment : Int, modulus : Int, target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Beskrivning

Låt oss ange `increment` $a $, `modulus` genom att $N $ och Integer som är kodat i `target` $y $.
Åtgärden utför sedan följande omvandling: \begin{align} \ket{y} \mapsto \ket{(y + a) \operatorname{mod} N} \end{align} heltal kodas i litet endian-format i QFT.

## <a name="input"></a>Indata

### <a name="increment--int"></a>ökning: [int](xref:microsoft.quantum.lang-ref.int)

Heltals ökning $a $ som ska läggas till i $y $.


### <a name="modulus--int"></a>Modulus: [int](xref:microsoft.quantum.lang-ref.int)

Integer $N $ som mods $y + a $.


### <a name="target--phaselittleendian"></a>mål: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)

Integer $y $ i fas-kodat litet endian-format som `increment` $a $ läggs till i.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Kommentarer

Förutsätter att `target` har den högsta bit inställningen 0.
Förutsätter också att målets värde är mindre än $N $.

För krets diagrammet och förklaringen, se figur 5 på [sidan 5 i arXiv: Quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=5).

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. aritmetiska. IncrementByModularInteger](xref:Microsoft.Quantum.Arithmetic.IncrementByModularInteger)